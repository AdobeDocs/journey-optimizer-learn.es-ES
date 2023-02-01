---
title: Crear un correo electrónico de confirmación del pedido
description: Pruebe su conocimiento sobre cómo crear y personalizar mensajes transaccionales
kt: 7531
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: ec86e2ac-081d-47aa-a948-007107baa2b4
source-git-commit: 70815c3cd30de22aad7ec667b8baf9b4c8642491
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 82%

---


# Crear un correo electrónico de confirmación del pedido

![Confirmación del pedido](/help/challenges/assets/email-assets/luma-transactional-order-confirmation.png)

| Desafío | Crear un correo electrónico transaccional de confirmación de pedido |
|---|---|
| Grupo de usuarios | Administrador de recorridos |
| Capacidades necesarias | <ul><li>[Creación de contenido de correo electrónico con el editor de mensajes](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-email-content-with-the-message-editor.html? lang=es)</li> <li>[Uso de información de evento contextual para la personalización](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html? lang=es)</li><li>[Uso de funciones de ayuda para la personalización](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html? lang=es)</li></ul> |
| Recursos que se van a descargar | [Recursos de confirmación de pedido](/help/challenges/assets/email-assets/order-confirmation-assets.zip) |

## La historia

Luma va a lanzar su tienda en línea y quiere garantizar una buena experiencia del cliente proporcionando un correo electrónico de confirmación de pedido cuando el cliente haya hecho uno.



## Su reto

Crear un recorrido que envíe un correo electrónico de confirmación de pedido cuando un cliente de Luma complete un pedido en línea.

>[!BEGINTABS]

>[!TAB Tarea]

1. Cree un recorrido llamado `Luma - Order Confirmation`
2. Utilice el evento : `LumaOnlinePurchase`
3. Cree el correo electrónico de confirmación de pedido llamado `Luma - Order Confirmation`:

* Categoría transaccional: asegúrese de seleccionar la superficie de correo electrónico transaccional
* La línea de asunto debe estar personalizada con el nombre de los destinatarios e incluir la frase “gracias por su compra”
* Utilice la plantilla `Luma - Order summary` y modifíquela:
   * Elimine el `You may also like` secciones
   * Añada el vínculo unsubscribe en la parte inferior del correo electrónico

El correo electrónico debe estructurarse de la siguiente manera:
<table>
<tr>
<td>
  <div>
     <strong> Sección de encabezado</strong>
      </div>
  </td>
  <td>
      <p>
     <li>luma_logo.png</li>
    <li>Debe tener un vínculo al sitio web de luma: https://publish1034.adobedemo.com/content/luma/us/en.html?lang=es</li>
    <p>
    </td>
  </tr>
  <tr>
  <td>
  <div>
    <strong>Sección de confirmación de pedido
    </strong>
  </td>
  <td>
    <p>
    <strong>Texto</strong><p>
    <em>Oye {firstName}</em><p>
   <div>
    <p>
     <em>Se ha hecho el pedido.
    <p>Cuando el paquete se envíe, le mandaremos un correo electrónico con un número de seguimiento para que pueda hacer un seguimiento del pedido.</p></em>
    </strong>
    </tr>
  </td>
 <td>
  <div>
     <strong> Enviar a sección</strong>
      </div>
      <p>
      <li>El nombre y los apellidos proceden del perfil
      <li>Reemplace la dirección codificada en la plantilla por la <b>dirección de envío</b>
      <li>Los detalles de dirección son atributos contextuales del evento (calle 1, ciudad, código postal, estado)
      <li> Eliminar el descuento, el total, la llegada</p>
  </td>
  <td>
  <p> Enviar a:</p>
      <em>{firstName} {lastName}<br>
     {Calle 1}<br>
     {City}, {State} {postalCode}<br></em></p>
  </td>
 <tr>
<td>
  <div>
     <strong>Sección Detalles del pedido</strong>
      </div>
       <p><li>Agregue esta sección debajo de <b>Enviar a</b> para obtener más información.
      </p><br>
      <p><b>Sugerencias:</b>
      <li>Utilice el componente de estructura "1:2 columna izquierda" para esta sección
      <li>Se trata de información contextual del evento.
      <li>Utilice la [!UICONTROL helper function]: [!UICONTROL Each]
      <li>Cambie al formato del editor de código para añadir los datos contextuales.
  </td>
  <td>
    <strong>Encabezado</strong>
    <p>
    <em>Pedido: `purchaseOrderNumber`</em>
    </p>
    <strong>Lista de productos pedidos:
  </strong>
  <p>Cada uno de los elementos debe tener el siguiente formato:
 <img alt="pedido" src="./assets/c2-order.png"> 
</p>
</td>
  </tr>
</table>


>[!TIP]
>
>Para permitirle solucionar problemas sobre sus recorridos, la práctica recomendada es añadir una ruta alternativa a todas las acciones de mensajes en caso de tiempo de espera o error.

>[!TAB Requisitos de éxito]

Active el recorrido que ha creado en el modo de prueba y envíeselo a sí mismo por correo electrónico:

1. Muestre los valores ocultos haciendo clic en el símbolo del ojo:
   1. En Parámetros de correo electrónico, haga clic en el símbolo T (habilitar anulación de parámetros)
      ![Anular parámetros de correo electrónico](/help/challenges/assets/c3-override-email-paramters.jpg)
   2. Haga clic en el campo Dirección
   3. En la siguiente pantalla, añada su dirección de correo electrónico entre paréntesis: *yourname@yourdomain* en el editor de expresiones y haga clic en OK.
2. Poner el recorrido en modo de prueba
3. Active el evento con estos parámetros:
   * Establezca el identificador de perfil en: Valor de identidad:`a8f14eab3b483c2b96171b575ecd90b1`
   * Tipo de evento: commerce.purchases
   * `Quantity`: 1
   * `Price Total:` 69
   * `Purchase Order Number:` 6253728
   * `SKU:` LLMH09
   * `City:` Washington
   * `Postal Code:` 20099
   * `State`: DC
   * `Street:` Terraza más estrecha

Tiene que recibir el correo electrónico de confirmación de compra personalizado con el producto especificado.

* La línea de asunto debe tener el nombre del perfil de prueba: Leora
* La sección de detalles del pedido tiene que rellenarse con los detalles del pedido introducidos durante la prueba

>[!TAB Compruebe su trabajo]

**Recorrido**

![Recorrido](/help/challenges/assets/c2-journey.png)


**Correo electrónico**

**Línea de asunto:**

Gracias por su compra, {{ profile.person.name.firstName }}!

Este es el aspecto que debería tener su cuerpo de correo electrónico:

![Correo electrónico](//help/challenges/assets/c2-email.png)

**Enviar a la sección:**

Este es el aspecto que debería tener el código:

```javascript
{{ profile.person.name.firstName }} {{ profile.person.name.lastName }}
{{context.journey.events.454181416.commerce.shipping.address.street1}}
{{context.journey.events.454181416.commerce.shipping.address.city}}, {{context.journey.events.454181416.commerce.shipping.address.state}} {{context.journey.events.454181416.commerce.shipping.address.postalCode}}
```

*event.45481416* será un número diferente para usted.

SUGERENCIA: Personalice cada línea por separado

**Sección de detalles del pedido:**

Este es el aspecto que debería tener el código:

Encabezado:

```javascript
Order #: {{context.journey.events.1627840522.commerce.order.purchaseOrderNumber}}
```

**Lista de productos:**

Utilice la función de ayuda “cada uno” para crear la lista de productos. Visualizarlos en una tabla. Este es el aspecto que debería tener el código (con variables específicas como su ID de evento), en lugar de `454181416` y su ID de organización en lugar de `techmarketingdemos` ):

```javascript
{{#each context.journey.events.454181416.productListItems as |product|}}<tr> <th class="colspan33"><div class="acr-fragment acr-component image-container" data-component-id="image" style="width:100%;text-align:center;" contenteditable="false"><!--[if mso]><table cellpadding="0" cellspacing="0" border="0" width="100%"><tr><td style="text-align: center;" ><![endif]--><img src="{{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.imageUrl}}" style="height:auto;width:100%;" height="233" width="233"><!--[if mso]></td></tr></table><![endif]--></div></th> <th class="colspan66"><div class="acr-fragment acr-component" data-component-id="text" contenteditable="false"><div class="text-container" contenteditable="true"><p><span style="font-weight:700;">{{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.name}}</span></p></div></div><div class="acr-fragment acr-component" data-component-id="text" contenteditable="false"><div class="text-container" contenteditable="true"><p>${{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.price}}.00</p><p>Quantity: {{context.journey.events.454181416.productListItems.quantity}}</p></div></div></th></tr> {{/each}}
```

**Precio total:**

Total:`${{context.journey.events.1627840522.commerce.order.priceTotal}}.00`


>[!ENDTABS]