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
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: aeebb91a-f216-4d5f-8da1-3a7e6f696ed0
    internal-label: Data management activity
  - id: d556b755-390a-43f0-be32-a08cf6236126
    internal-label: Configuration
  - id: bb359667-ec7d-4d4b-8663-5850fc219d32
    internal-label: Administration
subfeature_v2:
  - id: d2e8a157-b3b0-4143-9ff3-809bf400be56
    internal-label: Sandboxes
  - id: efb19423-4da4-4fd1-88d8-5ee8c71ae766
    internal-label: Application settings
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 100%
---
# Configuración de eventos

En esta sección, configure los tres eventos necesarios para los ejercicios prácticos en la sección de [Retos de Journey Optimizer](/help/challenges/introduction-and-prerequisites.md).

En el siguiente vídeo se explica cómo crear eventos:

>[!VIDEO](https://video.tv.adobe.com/v/3431518?captions=spa&quality=12&learn=on){transcript=true}

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

1. Seleccione [!UICONTROL ESPACIO DE NOMBRES]: `Luma CRM ID (lumaCrmId)`

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
