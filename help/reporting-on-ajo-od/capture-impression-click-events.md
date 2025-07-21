---
title: Captura de impresiones y eventos de interacciones
description: Capture eventos de impresión e interacción y prepare los datos para la creación de informes en Journey Optimizer.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
recommendations: noDisplay, noCatalog
last-substantial-update: 2025-07-18T00:00:00Z
jira: KT-18526
exl-id: 7e6014b5-c5a6-467b-8e31-58c5d966464c
source-git-commit: ab60877bd5cb9eeeea45b1e1f08293d31929fc81
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 0%

---

# Captura de impresiones y eventos de interacciones

Para habilitar la creación de informes sobre impresiones y clics de ofertas desde AJO Decisioning, se deben configurar los siguientes componentes:
>[!NOTE]
>
> Estos requisitos previos ya se cumplimentaron en la sección Crear esquema y conjunto de datos del [tutorial anterior](https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/personalizing-offers-with-real-time-weather-data/create-schema-and-dataset)

## &#x200B;1. Conjunto de datos en Adobe Experience Platform (AEP)

- Un conjunto de datos basado en un esquema **XDM ExperienceEvent**.

El esquema debe incluir `Web Details` grupo de campos que captura la dirección URL de la página, el referente, etc.

## &#x200B;2. Configuración del flujo de datos

- Se debe crear una **secuencia de datos** en Adobe Experience Platform.
- Este conjunto de datos debe vincularse al conjunto de datos configurado anteriormente para garantizar que todos los eventos de Web SDK se incorporen correctamente en el destino correcto.

## &#x200B;3. Propiedad de etiquetas de Adobe Experience Platform

- Extensión de AEP Web SDK configurada para utilizar la secuencia de datos creada en el paso anterior.
- Servicio de Experience Cloud ID configurado
- Se agrega un elemento de datos denominado ECID a la propiedad
- Se implementa en el sitio donde se representan las ofertas.


Para habilitar la creación de informes sobre el rendimiento de las ofertas, el primer paso es capturar cuándo se muestran las ofertas (impresiones) y cuándo se hace clic en ellas (interacciones). Estos eventos proporcionan la base para medir la participación, calcular las tasas de pulsaciones y analizar la eficacia de la oferta dentro de Adobe Experience Platform.

La función alloy(&quot;sendEvent&quot;) se utiliza para registrar las interacciones del usuario con las ofertas devueltas por Adobe Journey Optimizer (AJO).

La carga útil sendEvent captura las interacciones de ofertas incluyendo el tipo de evento (decisioning.propositionDisplay para impresiones o decisioning.propositionInteract para clics), un ID de evento único, una marca de tiempo y la identidad del usuario (identityMap). También incluye la lista de ofertas (propuestas) en las que se muestra o se hace clic, junto con tokens de seguimiento para garantizar una atribución precisa. Esta estructura permite la creación de informes y la optimización del rendimiento de ofertas personalizadas en Adobe Journey Optimizer.

Se capturan dos tipos de eventos de interacción:

## Evento de impresión

Se produce una impresión cuando se procesa una oferta en la página y esta se vuelve visible para el usuario. El seguimiento del evento se realiza mediante el tipo de evento decisioning.propositionDisplay.


```javascript
 alloy("sendEvent", {
            xdm: {
              _id: generateUUID(),
              timestamp: new Date().toISOString(),
              eventType: "decisioning.propositionDisplay",
              identityMap: {
                    ECID: [{
                      id: _satellite.getVar("ECID"),
                      authenticatedState: "authenticated",
                      primary: true
                    }]
                  },
              _experience: {
                decisioning: {
                  propositionEventType: {
                    display: 1
                  },
                  
                   propositions: window.latestPropositions
                  
                }
              }
            }
          });
        }
```

## Interacción de oferta

Se registra una interacción cuando un usuario hace clic en una call-to-action (CTA) dentro de la oferta procesada. El seguimiento del evento se realiza mediante el tipo de evento decisioning.propositionInteract.

```javascript
alloy("sendEvent", {
                xdm: {
                  _id: generateUUID(),
                  timestamp: new Date().toISOString(),
                  eventType: "decisioning.propositionInteract",
                  identityMap: {
                    ECID: [{
                      id: _satellite.getVar("ECID"),
                      authenticatedState: "ambiguous",
                      primary: true
                    }]
                  },
                  _experience: {
                    decisioning: {
                      propositionEventType: {
                        interact: 1
                      },
                      propositionAction: {
                        id: offerId,
                        tokens: [trackingToken]
                      },
                       propositions: window.latestPropositions
                    }
                  }
                }
              })
```

La inclusión de propuestas en eventos de clics e impresiones es esencial para generar informes de ofertas precisos en Adobe Journey Optimizer. Estas propuestas representan las ofertas exactas que se presentaron al usuario, lo que permite a Adobe atribuir las interacciones del usuario (por ejemplo, impresiones o clics) a las decisiones específicas tomadas por el sistema.

Cada oferta de una propuesta incluye un token de seguimiento, que es un identificador único generado por Adobe. Este token debe pasarse exactamente como se recibió (sin alteración) en el evento de clic o impresión correspondiente. La coincidencia de tokens de seguimiento garantiza que Adobe pueda asociar con precisión la acción del usuario con la decisión de oferta correcta, lo que permite la creación de informes descendente y la optimización basada en IA.
