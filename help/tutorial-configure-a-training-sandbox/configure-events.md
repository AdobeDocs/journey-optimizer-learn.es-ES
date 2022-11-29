---
title: Configurar eventos
description: Configure los tres eventos necesarios para los Journey Optimizer Challenges
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
exl-id: c7826818-c28a-493b-8aba-9d8a8102336d
source-git-commit: 8a2062f0719e799dd2d039488e6bba943fb458c4
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 9%

---

# Configurar eventos

En esta sección, se configuran los tres eventos necesarios para los ejercicios prácticos en la variable [Desafíos de Journey Optimizer](/help/challenges/introduction-and-prerequisites.md).

Vea el vídeo [Crear eventos](/help/set-up-journeys/create-events.md) para obtener instrucciones sobre cómo crear eventos.

## Crear el evento de compra en línea de Luma

1. Desde el panel de navegación izquierdo, vaya a [!UICONTROL ADMINISTRACIÓN] y seleccione *[!UICONTROL Configuración]*
1. En el [!UICONTROL Panel], seleccione *[!UICONTROL Administrar*]* Eventos

![Administrar eventos](assets/create-events.png)

1. Haga clic en *[!UICONTROL Crear evento]*
1. Complete los detalles y parámetros del evento:

   | [!UICONTROL Parámetro] | [!UICONTROL Valor] |
   |-------------|-----------|
   | [!UICONTROL NAME] | `LumaOnlinePurchase` |
   | [!UICONTROL TYPE] | [!UICONTROL Unitario] |
   | [!UICONTROL Tipo de ID de evento] | [!UICONTROL Basado en reglas] |
   | [!UICONTROL Esquema] | Interacciones de productos de Luma |
   | [!UICONTROL Campos] | EventType <br>Order.priceTotal<br>purchaseOrderNumber<br>productListItems.quantity<br><b>En Lista de productos Elementos > Productos de Luma > _*[!DNL yourOrganizationID]* > Producto:</b> <br> Nombre<br>Precio<br>ProductImageURL<br>Dirección URL del producto |

1. Agregue la variable [!UICONTROL Condición de ID de evento]: **[!DNL LumaOnlinePurchase.eventType is commerce.purchases]**

   1. Seleccione el icono de lápiz para editar el campo
   2. En el [!UICONTROL Añadir una condición de ID de evento] modal, arrastre y suelte el `eventType` sobre el lienzo
   3. Seleccione `commerce.purchases`
   4. Seleccione aceptar en el lienzo
   5. Seleccione aceptar en el modal

![Añadir condición de evento](/help/tutorial-configure-a-training-sandbox/assets/Event-lumaOnlinePurchase-condition-1.png)

1. Select [!UICONTROL ÁREA DE NOMBRES]: `Email(Email)`

1. Seleccione **[!UICONTROL Guardar]**.

## Crear *[!DNL Luma Wishlist Add]* Evento

| [!UICONTROL Parámetro] | [!UICONTROL Valor] |
|-------------|-----------|
| [!UICONTROL NAME] | `LumaWishlistAdd` |
| [!UICONTROL TYPE] | [!UICONTROL Unitario] |
| [!UICONTROL Tipo de ID de evento] | [!UICONTROL Basado en reglas] |
| [!UICONTROL Esquema] | `Luma Product Interactions` |
| [!UICONTROL Campos] | EventType<br>productListItem.quantity<br><b>En Lista de productos Elementos > Productos de Luma > _*[!DNL yourOrganizationID]* > Producto:</b> <br>Nombre<br>Precio<br> ProductImageURL<br>Dirección URL del producto |
| [!UICONTROL Condición] | [!DNL LumaWishlistAdd.eventType is commerce.saveForLaters] |
| [!UICONTROL Área de nombres] | Correo electrónico (correo electrónico) |

## Crear *[!DNL Luma Product Restock] Evento

| [!UICONTROL Parámetro] | [!UICONTROL Valor] |
|-------------|-----------|
| [!UICONTROL NAME] | `LumaProductRestock` |
| [!UICONTROL TYPE] | [!UICONTROL Business] |
| [!UICONTROL Esquema] | [!DNL Luma Product Inventory Events] |
| [!UICONTROL Campos] | productID <br> stockEventType<br><b>En Producto > Productos de Luma > *[!DNL yourOrganizationID]* > Producto:</b> <br>Nombre<br>Precio<br> ProductImageURL<br>Descripción |
| [!UICONTROL Condición] | LumaProductRestock._`your organization's ID`.inventoryEvent.stockEventType es restock |

## Felicitaciones

El simulador para pruebas ya está listo para usar.
