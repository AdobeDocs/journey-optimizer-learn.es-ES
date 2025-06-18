---
title: Entrega de Personalization con contenido JSON en Adobe Journey Optimizer
description: Aproveche el tipo de contenido JSON en Adobe Journey Optimizer (AJO) para crear experiencias de personalización flexibles y basadas en datos.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-18T00:00:00Z
jira: KT-18387
recommendations: noDisplay, noCatalog
source-git-commit: 9f5b52063605832a9b00c05fb1a93bf60ec7686f
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 0%

---

# Entrega de Personalization con contenido JSON en Adobe Journey Optimizer

Esta sección se proporciona como recurso adicional para usuarios avanzados que desean un mayor control sobre cómo se representan las ofertas en el front-end.

El uso del tipo de contenido JSON en una experiencia basada en código (CBE) le permite devolver datos de oferta estructurados y gestionar el procesamiento de forma dinámica mediante JavaScript. El tipo de contenido JSON es especialmente útil en escenarios que requieren diseños personalizados, lógica condicional o integración con datos contextuales, como el tiempo, la ubicación o el tipo de dispositivo.

Aunque no es necesario para la entrega de ofertas básicas, este método ofrece flexibilidad a los desarrolladores para que creen experiencias personalizadas basadas en datos que superen las capacidades del procesamiento estándar de HTML.

## Crear una experiencia basada en código (CBE) con tipo de contenido JSON.

Comience creando una nueva experiencia basada en código (CBE) en Adobe Journey Optimizer y establezca el formato de contenido en JSON. El tipo de contenido indica a AJO que devuelva datos de oferta estructurados (como offerText, imágenes o metadatos) como un objeto JSON en lugar de HTML procesado. Defina la plataforma (por ejemplo, web), la dirección URL de destino donde aparece la oferta y la ubicación en la página (como un ID de contenedor como offerContainer). Esta configuración permite que la aplicación web reciba datos de ofertas y los procese dinámicamente mediante JavaScript.

![json-content-type](assets/cbe-json-content.png)

## Asociar el CBE a una campaña con una política de decisión

Una vez creada la experiencia basada en código (CBE) con tipo de contenido JSON, se vincula a una campaña a través de una directiva de decisión. La política de decisión define la lógica para la idoneidad, la clasificación y la entrega de las ofertas en función del perfil o los datos contextuales.

Al insertar la directiva de decisión en el Editor de Personalization (por ejemplo, para mensajes en la aplicación o correo electrónico), es importante asegurarse de que la salida mantenga una estructura JSON válida.

Al insertar una directiva de decisión en el Editor de Personalization (PE) dentro de una campaña, Adobe Journey Optimizer genera automáticamente un bucle Handlebars basado en la directiva seleccionada. Por ejemplo:
![código predeterminado](assets/handlebar-code-default.png)
Este bucle se repite en todos los elementos de decisión devueltos por la política e inserta el campo offerText desde cada oferta. Esta estructura predeterminada funciona bien para los tipos de contenido de HTML, pero al trabajar con contenido JSON, puede requerir una reestructuración para producir una matriz u objeto JSON válido, especialmente si el resultado se analiza mediante programación.

![código reestructurado](assets/restructured-code.png)

Esta plantilla Handlebars está diseñada para generar una matriz JSON de objetos de oferta, donde cada objeto contiene un único campo offerText. Realiza un bucle de los elementos de decisión devueltos por la directiva de decisión especificada y ajusta cada offerText en un formato de objeto JSON.

## Analizar respuesta de oferta JSON

La respuesta de AJO contiene elementos de decisión personalizados en formato JSON bajo la estructura `propositions[].items[].data.content[]`. Cada elemento de contenido incluye campos como offerText.

```javascript
(response.propositions || []).forEach(p => {
  (p.items || []).forEach(item => {
    const contents = item.data?.content || [];
    contents.forEach(contentItem => {
      const html = contentItem.offerText || "";
      const wrapper = document.createElement("div");
      wrapper.className = "offer";
      wrapper.innerHTML = html;
      document.getElementById("offerContainer").appendChild(wrapper);
    });
  });
});
```

### Recursos de muestra

Para empezar, descargue el archivo HTML de muestra y el archivo JavaScript que muestran cómo utilizar ofertas basadas en JSON y procesarlas dinámicamente en su página web.

[Código JavaScript](assets/weather-related-offers-script-multiple-json.js)
[Archivo HTML](assets/multiple-json.html)