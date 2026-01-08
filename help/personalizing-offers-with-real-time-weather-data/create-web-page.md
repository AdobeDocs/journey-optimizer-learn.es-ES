---
title: Prueba de la solución
description: Cree una página web sencilla para probar la personalización de ofertas contextuales con datos de temperatura en tiempo real.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
exl-id: 609a5ddf-d6c6-4f19-bd7f-bca8c266b759
source-git-commit: 6e773afb6bf1770467f9c02739e6b3ede29c81f4
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 0%

---

# Prueba de la solución

Para probar la solución de extremo a extremo, extraiga weather-offers.html y weather-related-offers-script.js de [weather-offers.zip].(assets/weather-offers.zip) Estos archivos deben alojarse en un servidor web o en un servicio de alojamiento público como Github Pages. Esto es necesario porque:
: La API de geolocalización del explorador solo funciona mediante HTTPS o localhost

Para mantener las cosas organizadas y garantizar que las rutas relativas funcionen correctamente, recomendamos la siguiente estructura de carpetas para alojar la solución:

![estructura de carpetas](assets/folder-structure.png)

## Descargar los archivos proporcionados

Descargue y extraiga el HTML y el archivo javascript de [weather-offers.zip].(assets/weather-offers.zip)



## Actualizar la URL de superficie en el archivo javascript

Abra `weather-related-offers-script.js` y actualice ` "web://yourdomain.com/weather/weather-offers.html#offerContainer"`, pero reemplace `yourdomain.com` por el dominio en el que se hospeda el archivo HTML.

## Actualizar la propiedad de etiquetas de Adobe Experience Platform

Abra el archivo weather-offers.html en el editor de texto y reemplace la etiqueta script con la etiqueta script de su propiedad Adobe Experience Platform Tag creada en el paso anterior de este tutorial. Asegúrese de guardar el archivo

```
<script src="https://assets.adobedtm.com/AEM_TAGS/launch-ENabcd1234.min.js" async></script>
```



## Lo que hace la página web

Se crea una página web para probar la personalización de ofertas contextuales mediante datos de temperatura en tiempo real. Cuando un usuario visita la página, el explorador solicita acceso de geolocalización. Tras la aprobación, la página obtiene los detalles del tiempo actual, como la temperatura, las condiciones y la ciudad, mediante la API de OpenWeatherMap. Estos datos contextuales se muestran al usuario y se envían a Adobe Experience Platform mediante Adobe Web SDK (Alloy).

La llamada sendEvent se configura con renderDecisions: false, lo que significa que las ofertas devueltas por Adobe Journey Optimizer se gestionan manualmente. La secuencia de comandos procesa la respuesta de toma de decisiones, descodifica el contenido e inserta dinámicamente la oferta más relevante en un contenedor designado (#offerContainer).

## Qué hace JavaScript

JavaScript recupera dinámicamente información meteorológica en función de la ubicación del usuario y utiliza Adobe Experience Platform (AEP) para ofrecer ofertas personalizadas. Este es un desglose de los pasos:

1. **Espera a que Alloy se cargue**

   La secuencia de comandos garantiza que Adobe Web SDK (Alloy) se cargue completamente antes de realizar cualquier solicitud de personalización.

2. **Obtiene la ubicación del usuario**

   Utiliza la API de geolocalización del explorador para recuperar la latitud y longitud actuales del usuario.

3. **Obtiene Datos Del Tiempo**

   Llama a la API de OpenWeatherMap para obtener los detalles meteorológicos actuales:

   Temperatura (en °F)

   Condiciones meteorológicas (por ejemplo, &quot;Lluvia&quot;, &quot;Despejado&quot;)

   Nombre de ciudad

   Humedad

4. **Mostrar información meteorológica en la página web**

   Actualiza el DOM con un mensaje como:

   &quot;La temperatura actual en San Diego es de 72°F con cielos despejados&quot;.

5. **Envía el contexto meteorológico a AEP**

   Utiliza alloy(&quot;sendEvent&quot;) para enviar datos meteorológicos contextuales a AEP

   ```javascript
   xdm: {
   eventType: "decisioning.request",
   _techmarketingdemos: {
   temperature: temp,
   weatherConditions: condition,
   cityName: city
     }
   }
   ```

6. **Recupera y procesa ofertas**

   Recibe ofertas devueltas por AJO Decisioning.

   Descodifica el contenido de HTML.

   Inserta de forma dinámica las ofertas en <div id="offerContainer"> Elemento.

## Pasos siguientes

[Mida e informe del impacto de AJO Decisioning.](https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/reporting-on-ajo-od/introduction)

