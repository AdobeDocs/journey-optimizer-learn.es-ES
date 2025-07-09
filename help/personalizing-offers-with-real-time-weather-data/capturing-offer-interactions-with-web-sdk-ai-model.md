---
title: Captura de interacciones de oferta con Adobe Web SDK para la formación sobre modelos de IA
description: En este artículo se explica cómo capturar los datos de interacción del usuario (como las impresiones de ofertas y los clics) mediante Adobe Experience Platform Web SDK (alloy.js). Estos datos sirven como base para entrenar modelos de IA en Adobe Journey Optimizer (AJO) de forma inteligente para clasificar ofertas basadas en el comportamiento del usuario y las señales contextuales.
feature: Decisioning
topic: Integrations
role: User
level: Beginner
doc-type: Article
last-substantial-update: 2025-07-08T00:00:00Z
jira: KT-18451
source-git-commit: 41f0d44fb39c9d187ee8c97d54202387fa9eda56
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 0%

---


# Captura de interacciones de oferta con Adobe Web SDK para la formación sobre modelos de IA

>[!NOTE]
>
> Complete este artículo solo si planea utilizar métodos de clasificación basados en IA en Adobe Journey Optimizer para personalizar qué oferta se muestra en función de la participación prevista.



Este artículo muestra cómo capturar eventos de interacción de ofertas (como impresiones o clics) mediante Adobe Experience Platform Web SDK llamando a alloy(&quot;sendEvent&quot;, ...) directamente en el código de JavaScript. Los datos se incorporan en AEP y se utilizan para entrenar modelos de IA en Adobe Journey Optimizer (AJO) para una clasificación de ofertas más inteligente basada en el comportamiento en tiempo real.

Para crear un modelo de IA para la clasificación de ofertas en Adobe Journey Optimizer, el conjunto de datos debe basarse en un esquema que incluya el grupo de campos Interacciones de propuestas. Este grupo de campos admite eventos de toma de decisiones clave como decisioning.propositionDisplay y decisioning.propositionInteract, junto con campos obligatorios como involedPropositions, display e interaction.

Existen dos enfoques válidos para lograrlo:

- Cree un nuevo esquema, conjunto de datos y flujo de datos configurado específicamente para el seguimiento de interacciones
- Actualizar un esquema existente, que es lo que se hace en este tutorial



## Actualizar esquema existente para capturar eventos de interacción de oferta

En lugar de crear un nuevo esquema, el esquema de Evento de experiencia existente utilizado para las ofertas relacionadas con el tiempo se actualiza para admitir el seguimiento de interacciones.

En Adobe Experience Platform:

- Abra el esquema de evento de experiencia _&#x200B;**Weather-Schema**&#x200B;_ existente que esté usando para ofertas basadas en el clima.

- Añada el grupo de campos:
Evento de experiencia: interacciones de propuesta

No es necesario crear un nuevo conjunto de datos o flujo de datos: siga utilizando la configuración existente para las ofertas meteorológicas. Los eventos que se envían se alinean con las expectativas de Adobe Journey Optimizer para la formación de modelos de IA y el seguimiento del rendimiento de las ofertas.


Continúe utilizando el conjunto de datos actual (no es necesario crear uno nuevo)

La secuencia de datos existente ya está configurada y en uso en la propiedad Adobe Experience Platform Tags; no es necesario realizar cambios en ella.

Web SDK enruta automáticamente los nuevos eventos de interacción al destino correcto.

Esta configuración optimizada garantiza que todos los eventos de decisiones y meteorológicos se incorporen en un único conjunto de datos unificado, lo que es ideal para entrenar modelos de IA en Adobe Journey Optimizer.


## Captura De Eventos De Visualización De Ofertas (Impresiones)

La estructura de HTML de la oferta se modificó para incluir elementos interactivos, específicamente las etiquetas `<a>` y `<button>`, que permitían a los usuarios interactuar con la oferta (por ejemplo, los botones &quot;Reclamar oferta&quot; o &quot;Más información&quot;).

Cada botón incluye un atributo data-offer-id para que se pueda rastrear correctamente la interacción correspondiente.



Para registrar cuándo se muestran las ofertas a los usuarios, se ha actualizado el archivo JavaScript existente utilizado para procesar las ofertas meteorológicas para incluir el seguimiento de eventos de visualización.

Ahora se envía un evento decisioning.propositionDisplay mediante Adobe Web SDK (alloy.sendEvent) cuando se muestran una o más ofertas. Este evento incluye la visualización necesaria: 1 indicador y hace referencia a las propuestas involucradas.


```javascript
if (offerIds.length > 0) {
  alloy("sendEvent", {
    xdm: {
      _id: generateUUID(),
      timestamp: new Date().toISOString(),
      eventType: "decisioning.propositionDisplay",
      _experience: {
        decisioning: {
          propositionEvent: {
            display: 1
          },
          involvedPropositions: offerIds.map(id => ({
            id,
            scope: "web://gbedekar489.github.io/weather/weather-offers.html#offerContainer"
          }))
        }
      }
    }
  });
}
```

## Captura De Eventos De Clic De Ofertas (Interacciones)

Para rastrear cuándo un usuario hace clic en una oferta, hemos actualizado el JavaScript existente para detectar clics en los elementos `<a>` y `<button>` procesados dentro del contenedor de oferta.

Cuando se detecta un clic, se envía un evento decisioning.propositionInteract mediante Adobe Web SDK. El evento incluye el indicador interaction: 1 necesario y hace referencia al ID de oferta y al ámbito de decisión específicos.

```javascript
// Attach click tracking to <a> and <button> elements
wrapper.querySelectorAll("a, button").forEach(el => {
  el.addEventListener("click", () => {
    const offerId = el.getAttribute("data-offer-id") || item.id;
    console.log("Clicked element offerId:", offerId);

    alloy("sendEvent", {
      xdm: {
        _id: generateUUID(),
        timestamp: new Date().toISOString(),
        eventType: "decisioning.propositionInteract",
        _experience: {
          decisioning: {
            propositionEvent: {
              interact: 1
            },
            involvedPropositions: [{
              id: offerId,
              scope: "web://gbedekar489.github.io/weather/weather-offers.html#offerContainer"
            }]
          }
        }
      }
    });
  });
});
```

## Creación de un modelo de IA para la clasificación de ofertas en Adobe Journey Optimizer Offer Decisioning

Con, las impresiones y los clics de las ofertas ahora capturados mediante la SDK web y almacenados en Adobe Experience Platform, estos datos se pueden utilizar para entrenar un modelo de IA que prediga qué ofertas tienen más probabilidades de impulsar la participación.

Se hace referencia a este modelo de IA en una fórmula de clasificación o estrategia de selección para determinar qué ofertas tienen prioridad para cada usuario.
- Iniciar sesión en Journey Optimizer
- Vaya a Decisioning -> Strategy setup -> AI models ->Create AI Model
- Asegúrese de utilizar el conjunto de datos correcto
  ![modelo ai](assets/ai-model.png)
- Guarde y active el modelo de IA.
- Actualice la estrategia de selección creada en el paso anterior para utilizar el modelo de IA para el método de clasificación
  ![actualizar-selección-estrategia](assets/update-selection-strategy.png)

## Prueba de la solución

Incluir el [archivo JavaScript actualizado](assets/ai-model.js) en la [página web existente](assets/weather-offers.html)