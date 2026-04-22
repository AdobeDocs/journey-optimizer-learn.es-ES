---
title: Envío de mensajes push en un recorrido
description: El límite de frecuencia en Adobe Journey Optimizer se aplica al nivel de oferta individual y depende de la captura de eventos de impresión de oferta y de clics. Esto requiere el seguimiento de los eventos decisioning.propositionDisplay y decisioning.propositionInteract mediante Adobe Web SDK y su asignación a un esquema de evento de experiencia XDM actualizado en Adobe Experience Platform.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00Z
jira: KT-18526
source-git-commit: 3d342c5c4de4dda221ce4427b1e4aef7ef8c22cc
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 0%

---

# Envío de mensajes push en un recorrido

La activación de un recorrido basado en un evento de caída de precios permite una participación de los usuarios en tiempo real basada en el comportamiento. En situaciones reales, este evento suele originarse a partir de un sistema de precios back-end cuando se actualiza el precio de un producto. En este tutorial, simulamos ese comportamiento enviando un evento price.drop personalizado a través de la capa de datos de Adobe mediante etiquetas de AEP, incluidos detalles del producto como nombre y SKU. Este evento se incorpora en Adobe Experience Platform y se utiliza como déclencheur de entrada para un recorrido en Adobe Journey Optimizer. Una vez recibido, el recorrido puede enviar inmediatamente una notificación push personalizada a los usuarios aptos, informándoles sobre la caída de precios y fomentando la acción oportuna.

La activación de un recorrido mediante un evento personalizado implica los siguientes pasos

## Creación de eventos personalizados en Journey Optimizer

Inicie sesión en Adobe Journey Optimizer, vaya a Administración → Configuraciones → Eventos y, a continuación, seleccione Crear evento. Cree un nuevo evento denominado PriceDropEvent y asócielo al esquema de evento SchemaForPushNotification creado anteriormente en el tutorial. Asegúrese de que las propiedades de evento estén configuradas tal como se muestra en la imagen de referencia.

![propiedades de evento](assets/price-drop-event.png)

En el esquema, seleccione los campos obligatorios para que estén disponibles para la personalización. En concreto, incluya `Name` y `SKU` del objeto ProductListItems, así como el identificador del identityMap. A continuación, se podrá acceder a estos campos dentro del editor de personalización, lo que le permitirá crear dinámicamente mensajes de notificación push basados en el contexto del producto y del usuario.

## Creando propiedad de etiqueta

Esta propiedad se configura con AEP Web SDK, que está conectado al objeto WebPushDataStream creado anteriormente en el tutorial. La propiedad tag escucha el evento price.drop de la capa de datos de Adobe y asigna los detalles del producto relevantes actualizando el elemento de datos ProductListItems. Una vez preparados los datos, se activa una regla en la propiedad tag y se envía el evento price.drop a AEP a través de Web SDK. A continuación, este evento sirve como punto de entrada para un recorrido en Adobe Journey Optimizer, lo que permite enviar notificaciones push inmediatamente en función de la caída de precios.



