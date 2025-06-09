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
source-git-commit: a9fc14da78e1c67b01aef5dcdd417ce02d36d50a
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---

# Prueba de la solución

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

   Recibe ofertas devueltas por AJO.

   Descodifica el contenido de HTML.

   Inserta de forma dinámica las ofertas en <div id="offerContainer"> Elemento.

7. **Ejemplo de Assets**

   La página web utilizada para probar la solución está disponible para descargar

[Página web](assets/weather-offers.html)

[Código JavaScript](assets/weather-related-offers-script.js)

