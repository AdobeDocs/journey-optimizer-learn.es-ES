---
title: Configuración de eventos
description: Configure tres eventos necesarios para los retos prácticos de Journey Optimizer
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
jira: KT-9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
exl-id: c7826818-c28a-493b-8aba-9d8a8102336d
source-git-commit: fd9d277be00449155c49b3809fe647d7342b6acd
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 100%

---

# Configuración de eventos

En esta sección, configure los tres eventos necesarios para los ejercicios prácticos en la sección de [Retos de Journey Optimizer](/help/challenges/introduction-and-prerequisites.md).

En el siguiente vídeo se explica cómo crear eventos:

>[!VIDEO](https://video.tv.adobe.com/v/336253?quality=12&learn=on){transcript=true}

## Creación del evento de compra en línea de Luma

Al utilizar este evento, Journey Optimizer recibe información cuando una persona compra productos de Luma en línea.

1. Cree un evento con los siguientes parámetros:

   | [!UICONTROL Parámetro] | [!UICONTROL Valor] |
   |-------------|-----------|
   | [!UICONTROL NOMBRE] | `LumaOnlinePurchase` |
   | [!UICONTROL TIPO] | [!UICONTROL Unitario] |
   | [!UICONTROL Tipo de ID de evento] | [!UICONTROL Basado en reglas] |
   | [!UICONTROL Esquema] | `Luma Web Events Schema` |
   | [!UICONTROL Campos] | `eventType` <br>`commerce.order.priceTotal`<br>`commerce.order.purchaseOrderNumber`<br>`commerce.shipping.adress.street1`<br>`commerce.shipping.adress.city`<br>`commerce.shipping.adress.postalCode`<br>`commerce.shipping.adress.state`<br>`productListItems.quantity`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.name`<br>`productListItems.Luma Product Catalog Schema._your Organization_IDprice`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.imageURL`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.url` |

1. Añada la [!UICONTROL Condición de ID de evento]: `LumaOnlinePurchase.eventType is commerce.purchases`:

   1. Seleccione el icono de lápiz para editar el campo.

   1. En el modal **[!UICONTROL Añadir una condición de ID de evento]**, arrastre y suelte el `eventType` en el lienzo.
   1. Seleccione `commerce.purchases`.
   1. Seleccione **[!UICONTROL Ok]** en el lienzo.
   1. Seleccione **[!UICONTROL Ok]** en el modal.

   ![Añadir condición de evento](/help/tutorial-configure-a-training-sandbox/assets/Event-lumaOnlinePurchase-condition-1.png)

1. Seleccione [!UICONTROL ÁREA DE NOMBRES]: `Luma CRM ID (lumaCrmId)`

1. Seleccione **[!UICONTROL Guardar]**.

## Crear *[!DNL Luma Product Restock]* evento

| [!UICONTROL Parámetro] | [!UICONTROL Valor] |
|-------------|-----------|
| [!UICONTROL NOMBRE] | `LumaProductRestock` |
| [!UICONTROL TIPO] | [!UICONTROL Business] |
| [!UICONTROL Esquema] | [!DNL Luma Product Inventory Event Schema] |
| [!UICONTROL Campos] | SKU <br> stockEventType<br><b>LumaProductCatalogSchema._yourOrganizationID.product :</b> <br>nombre<br>precio<br> ImageURL<br>descripción |
| [!UICONTROL Condición] | LumaProductRestock._`your organization's ID`.inventoryEvent.stockEventType está en reposición |

¡Felicidades! La zona protegida ya está lista para su uso.
