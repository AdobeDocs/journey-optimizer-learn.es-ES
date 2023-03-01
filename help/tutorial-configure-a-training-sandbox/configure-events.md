---
title: Configuración de eventos
description: Configure tres eventos necesarios para los desafíos prácticos de Journey Optimizer
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
exl-id: c7826818-c28a-493b-8aba-9d8a8102336d
source-git-commit: 4df1bdca81a585f728aa68519aa7ec7cd0c2f014
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 10%

---

# Configuración de eventos

En esta sección, configure los tres eventos necesarios para los ejercicios prácticos en la [Desafíos de Journey Optimizer](/help/challenges/introduction-and-prerequisites.md).

En el siguiente vídeo se explica cómo crear eventos:

>[!VIDEO](https://video.tv.adobe.com/v/336253?quality=12)

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

1. Añada el [!UICONTROL Condición de ID de evento]: `LumaOnlinePurchase.eventType is commerce.purchases`:

   1. Seleccione el icono de lápiz para editar el campo.

   1. En el **[!UICONTROL Añadir una condición de ID de evento]** modal, arrastre y suelte el `eventType` en el lienzo.
   1. Seleccione `commerce.purchases`.
   1. Seleccionar **[!UICONTROL Ok]** en el lienzo.
   1. Seleccionar **[!UICONTROL Ok]** en el modal.

   ![Añadir condición de evento](/help/tutorial-configure-a-training-sandbox/assets/Event-lumaOnlinePurchase-condition-1.png)

1. Seleccionar [!UICONTROL NAMESPACE]: `Luma CRM ID (lumaCrmId)`

1. Seleccione **[!UICONTROL Guardar]**.

## Crear *[!DNL Luma Wishlist Add]* evento

| [!UICONTROL Parámetro] | [!UICONTROL Valor] |
|-------------|-----------|
| [!UICONTROL NOMBRE] | `LumaWishlistAdd` |
| [!UICONTROL TIPO] | [!UICONTROL Unitario] |
| [!UICONTROL Tipo de ID de evento] | [!UICONTROL Basado en reglas] |
| [!UICONTROL Esquema] | `Luma Product Interactions` |
| [!UICONTROL Campos] | EventType<br>productListItem.quantity<br><b>En Lista de productos Artículos > Productos de Luma > _*[!DNL yourOrganizationID]* > Producto:</b> <br>Nombre<br>Precio<br> ProductImageURL<br>ProductURL |
| [!UICONTROL Condición] | [!DNL LumaWishlistAdd.eventType is commerce.saveForLaters] |
| [!UICONTROL Área de nombres] | Correo electrónico (correo electrónico) |

## Crear *[!DNL Luma Product Restock]* evento

| [!UICONTROL Parámetro] | [!UICONTROL Valor] |
|-------------|-----------|
| [!UICONTROL NOMBRE] | `LumaProductRestock` |
| [!UICONTROL TIPO] | [!UICONTROL Business] |
| [!UICONTROL Esquema] | [!DNL Luma Product Inventory Events] |
| [!UICONTROL Campos] | SKU <br> stockEventType<br><b> yourOrganizationID > product:</b> <br>name<br>precio<br> ImageURL<br>description |
| [!UICONTROL Condición] | LumaProductRestock._`your organization's ID`.inventoryEvent.stockEventType es reabastecimiento |

¡Felicidades! La zona protegida ya está lista para su uso.
