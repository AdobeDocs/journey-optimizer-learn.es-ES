---
title: Crear propiedad de etiqueta
description: La propiedad tag envía los datos del explorador a AEP a través de Web SDK.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00.000Z
jira: KT-20879
exl-id: 108de002-f033-4b88-bee5-2b50463c345c
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: 66e1fd99-672d-5d64-aa58-eca107f0fbae
    internal-label: Push
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%
---
# Crear propiedad de etiqueta

En la segunda parte de este tutorial, aprenderá a almacenar en déclencheur las notificaciones push en tiempo real enviando manualmente un evento personalizado price.drop. Este método utiliza la recopilación de datos de AEP (etiquetas) para capturar el evento desde la página web y enviarlo a Adobe Experience Platform. Una vez introducido el evento, almacena en déclencheur un recorrido en Adobe Journey Optimizer, lo que le permite enviar notificaciones push bajo demanda en función de las acciones del usuario o los eventos empresariales.

Esta propiedad se configura con AEP Web SDK, que está conectado al `WebPushDataStream` creado anteriormente en el tutorial. La propiedad tag escucha el evento `price.drop` en la capa de datos de Adobe y asigna los detalles de producto relevantes actualizando el elemento de datos ProductListItems. Una vez preparados los datos, se activa una regla en la propiedad tag y se envía el evento price.drop a AEP a través de Web SDK. A continuación, este evento sirve como punto de entrada para un recorrido en Adobe Journey Optimizer, lo que permite enviar notificaciones push inmediatamente en función de la caída de precios.

## Elementos de etiqueta

ProductListItems para contener detalles del producto

![elementos-etiqueta](assets/product-list-items-element.png)

asignación de la variable xdm a `schemaForPushNotification`

![xdm-variable](assets/xdmvariable-data-element.png)

## Crear regla

Escucha el evento price.drop
![evento-insertado-datos](assets/tag-rule-event.png)

Actualizar productListItems mediante la variable de actualización
![variable-actualización](assets/update-variable.png)
Finalmente, envíe el evento price.drop a AEP con la variable xml actualizada
![send-event](assets/send-event.png)

El siguiente código JavaScript envía el evento price.drop a las etiquetas de AEP desde la página web

```javascript
 <script>
      window.adobeDataLayer.push({
        event: "price.drop",
        productListItems: productListItems
      });
  </script>
```
