---
title: Prueba de la solución
description: Cree una página web sencilla para capturar eventos de impresión y clics en las ofertas.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-07-18T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18526
source-git-commit: 69bc8aace3cc502a18e691584824176833413c7e
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 0%

---

# Prueba de la solución

Para probar la solución de principio a fin, los archivos [weather-offers.html](assets/weather-offers.html) y [capture-impressions-click-events.js](assets/capture-impressions-click-events.js) deben alojarse en un servidor web o en un servicio de alojamiento público como Github Pages. Esto es necesario porque la API de geolocalización del explorador solo funciona mediante HTTPS o localhost

## Descargar los archivos proporcionados

[Archivo de HTML](assets/weather-offers.html)

[Archivo Javascript](assets/capture-impressions-click-events.js)

## Actualizar la URL de superficie en el archivo javascript

Abra `capture-impressions-click-events.js` y actualice ` "web://yourdomain.com/weather/weather-offers.html#offerContainer"`reemplazando `yourdomain.com` por el dominio real donde se hospeda el archivo HTML.


## Actualizar la propiedad de etiquetas de Adobe Experience Platform

Abra el archivo weather-offers.html en el editor de texto y reemplace la etiqueta script con la etiqueta script de su propiedad Adobe Experience Platform Tag creada en el paso anterior de este tutorial. Asegúrese de guardar el archivo

```
<script src="https://assets.adobedtm.com/AEM_TAGS/launch-ENabcd1234.min.js" async></script>
```

## Interacción con las ofertas

- Abra la página web en su explorador favorito.

- Permitir _&#x200B;**seguimiento de ubicación**&#x200B;_. Esto es necesario para obtener los detalles del tiempo en función de su ubicación.

- Haga clic en el botón del evento de interacciones de ofertas para almacenar en déclencheur.

## Ver el informe

- Inicie sesión en Journey Optimizer

- Vaya a Administración de Recorrido ->Campañas

- Haga clic en la campaña y luego seleccione el informe correspondiente en el menú del informe.
