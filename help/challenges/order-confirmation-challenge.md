---
title: Crear una confirmación de pedido
description: Pruebe sus conocimientos sobre cómo crear y personalizar mensajes transaccionales
kt: 7531
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: ec86e2ac-081d-47aa-a948-007107baa2b4
source-git-commit: 8a2062f0719e799dd2d039488e6bba943fb458c4
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 4%

---

# Crear un correo electrónico transaccional de confirmación de pedido

![Confirmación del pedido](/help/challenges/assets/email-assets/luma-transactional-order-confirmation.png)

| Desafío | Crear un correo electrónico transaccional de confirmación de pedido |
|---|---|
| Grupo de usuarios | Administrador de recorridos |
| Capacidades necesarias | <ul><li>[Creación de contenido de correo electrónico con el editor de mensajes](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-email-content-with-the-message-editor.html?lang=en)</li> <li>[Uso de información de evento contextual para la personalización](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html?lang=en)</li><li>[Uso de funciones de ayuda para la personalización](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html?lang=en)</li></ul> |
| Recursos que se van a descargar | [Recursos de confirmación de pedido](/help/challenges/assets/email-assets/order-confirmation-assets.zip) |

## La historia

Luma, inicia su tienda en línea y desea garantizar una buena experiencia con el cliente, proporcionando un correo electrónico de confirmación de pedido una vez que el cliente ha realizado un pedido.

Cree y personalice un mensaje de confirmación de pedido transaccional.

## ¿Tiene todo lo que necesita?

## Su desafío

Cree un correo electrónico de confirmación de pedido que se active cuando un cliente de Luma complete un pedido en línea.

### Creación del correo electrónico de confirmación de pedido

Cree un nuevo mensaje de correo electrónico llamado &quot;(su nombre)_Luma - Confirmación del pedido&quot;. La línea de asunto debe estar personalizada con el nombre de los destinatarios y debe incluir la frase &quot;gracias por su compra&quot;

Siguiendo la guía de marca Luma, el correo electrónico debe estructurarse de la siguiente manera:

<table>
<tr>
<td>
  <div>
     <strong> Sección Encabezado</strong>
      </div>
  </td>
  <td>
    <strong>Logotipo de Luma</strong>
      <p>
     <li>luma_logo.png</li>
    <li>Tamaño 35%, fondo blanco centrado </li>
    <li>Debe tener un enlace al sitio web de luma: https://publish1034.adobedemo.com/content/luma/us/en.html</li>
    <p>
    Sugerencia: Encontrará todas las imágenes en la carpeta assets denominadas imágenes de mensajes. <p>
    </td>
  </tr>
  <tr>
  <td>
  <div>
    <strong>Sección de confirmación de pedido
    </strong>
  </td>
  <td>
    <strong>Imagen</strong><p>
    <li>luma-transactional-order-confirmation-2.jpg </li>
    <li>Margen: Superior, inferior (10)<div>
    <p>
    <strong>Texto</strong><p>
    <em>¡Gracias por la compra!</em><p>
    <li>Alineación: left  </li>
   <li>Color del texto: rgb(101, 106, 119); tamaño de fuente:14 px</li>
    <li>Relleno: izquierda (95), derecha (95)</li><div>
    <p>
     <em>Se ha realizado el pedido.
    <p>Una vez que el paquete se envíe, le enviaremos un correo electrónico con un número de seguimiento para que pueda realizar un seguimiento de su pedido.</p></em>
    </strong><p>
    <li>Alineación: left  </li>
    <li>Color del texto: rgb(101, 106, 119); tamaño de fuente:14 px </li>
    <li>Relleno: izquierda (95), derecha (95)</li><div>
    </a>
    <p>
    <strong>Botón:</strong>
   <p><em>Ver el pedido</em></p>
      <li>Color de fondo: rgb(25, 121, 195)</li>
      <li>Color del texto: Blanco</li>
      <li>Sin borde</li>
      <li>Altura: 40</li>
      <li>Añada un vínculo a un sitio web de su elección </li>
      <li>Alinea la izquierda con el texto anterior (sugerencia: utilizar el margen del contenedor)</li>
  </td>
 <tr>
<td>
  <div>
     <strong>Sección Detalles del pedido</strong>
      </div>
      <p>Sugerencias:
      <li>Esta es información contextual del evento. Solo podrá añadir en el contexto una vez que añada el mensaje al recorrido (consulte el paso 2). No publique el correo electrónico antes de agregarlo al Recorrido y modificarlo con la información de evento contextual.</li>
      <li>Utilice la función de ayuda: Cada</li>
      <li>Utilice el editor de HTML para dar formato a los datos contextuales. Coloque la información en contenedores utilizando etiquetas DIV.</li>
  </td>
  <td>
    <strong>Header</strong>
    <p>
    <em>Pedido {Número de orden de compra}</em>
    </p>
    <strong>Lista de productos solicitados:
  </strong>
  <p>Cada uno de los elementos debe tener el siguiente formato:
   <img alt="pedido" src="./assets/c2-order.png"> 
</p>
<strong>Imagen del producto:</strong>
<li>Clase : cart-item-chair
<li>estilo: borde: min-height:40px</li>
<li>relleno superior e inferior:20px</li>
<li>relleno-izquierda:80px</li>
<li>radio del borde:0px</li>
<li>Usar como imagen de fondo para el contenedor</li>
<li>background-position: 0 % 50 %</li>
<li>background-size: 60px</li>
<li>background-repeat: no-repeat</li>
<p>
<strong>Precio:</strong>
<li>Formato = H5</li>
<li>style = tamaño del cuadro:border-box</li>
<li>margen inferior:5px</li>
<li>margin-top:0px;</li>
<p>
<strong>Nombre y cantidad:</strong>
<li>class=text-small</li>
<li>style=box-size: cuadro de borde</li>
<li>padding-top: 5px</li>
<li>color: rgb(101, 106, 119)</li>
<li>tamaño de fuente:14 px</li>
<p>
</td>
  </tr>
</table>

### Creación del recorrido

1. Llame al recorrido &quot;su nombre _Luma-Order Confirmation&quot;
1. Utilice el evento : LumaOnlinePurchase
1. Acción: Añada el mensaje que ha creado en el paso 1
1. Vuelva al mensaje y añada los atributos contextuales
1. Publicar el correo electrónico

>[!TIP]
>
>Para permitirle solucionar problemas de sus recorridos, la práctica recomendada es agregar una ruta alternativa a todas las acciones de mensajes en caso de tiempo de espera o error.

+++Criterios de éxito

Déclencheur el Recorrido que ha creado en el modo de prueba y envíelo por correo electrónico:

1. Muestre los valores ocultos haciendo clic en el símbolo de ojo:
   1. En Parámetros de correo electrónico, haga clic en el símbolo T (habilitar anulación de parámetros)
      ![Anular parámetros de correo electrónico](/help/challenges/assets/c3-override-email-paramters.jpg)
   2. Haga clic en el campo Dirección
   3. En la siguiente pantalla, añada su dirección de correo electrónico entre paréntesis: *yourname@yourdomain* en el editor de expresiones y haga clic en aceptar.
2. Poner el recorrido en modo de prueba
3. Déclencheur el evento con los siguientes parámetros:
   * Establezca el identificador de perfil en: Jenna_Palmer9530@emailsim.io
   * Tipo de evento: commerce.purchases
   * Nombre: Kit Sprite Yoga Companion
   * Cantidad: 1
   * Precio total: 61
   * Número de pedido: 6253728
   * SKU: 24-WG080
   * productImageURL: <https://publish1034.adobedemo.com/content/dam/luma/en/products/gear/fitness-equipment/luma-yoga-kit-2.jpg>

Debe recibir el correo electrónico de confirmación de compra personalizado, con el producto especificado.

* La línea de asunto debe comenzar con el nombre del perfil de prueba: Jenna
* La sección de detalles del pedido debe rellenarse con los detalles del pedido introducidos durante la prueba
* La información del cliente debe tener la ciudad y el código postal del perfil de prueba:

   43913 Terraza Thierer, Washington DC 2009

+++

+++Comprobar su trabajo

**Línea de asunto:**

{{ profile.person.name.firstName }}, gracias por su compra!

**Encabezado y sección de confirmación:**

![Confirmación de encabezado y pedido](/help/challenges/assets/c2-header.png)

**Sección de detalles del orden:**

![Sección de detalles del pedido](/help/challenges/assets/c2-order-detail-section.png)

Este es el aspecto que debería tener el código:

Encabezado:

```javascript
Order: {{context.journey.events.1627840522.commerce.order.purchaseOrderNumber}}
```

Lista de productos:

Utilice la función de ayuda &quot;each&quot; para crear la lista de productos. Este es el aspecto que debería tener el código:

```javascript
{{#each context.journey.events.1911672547.productListItems as|product|}}
<div class="cart-item-chair" style="box-sizing:border-box;min-height:40px;padding-top:20px;padding-bottom:20px;padding-left:80px;border-radius:0px;background-image:url({{product._wwfovlab065.productImageURL}});background-position:0% 50%;background-size:60px;background-repeat:no-repeat;">
<h5 style="box-sizing:border-box;margin-bottom:5px;font-size:16px;line-height:20px;margin-top:0px;">${{product.priceTotal}}.00</h5>
<div class="text-small" style="box-sizing:border-box;padding-top:5px;color:rgb(101, 106, 119);font-size:14px;">{{product.name}}</div><div class="text-small" style="box-sizing:border-box;padding-top:5px;color:rgb(101, 106, 119);font-size:14px;">Quantity: {{product.quantity}}</div></div><div class="divider-small" style="box-sizing:border-box;height:1px;margin-top:10px;margin-bottom:10px;background-color:rgb(209, 213, 223);"> </div>
{{/each}}

Total: ${{context.journey.events.1627840522.commerce.order.priceTotal}} 
```

**Sección de información del cliente**

![Dirección del cliente](assets/c2-customer-information.png)

La personalización debería tener este aspecto:

```javascript
{{profile.homeAddress.street1}}
{{profile.homeAddress.city}},{{profile.homeAddress.state}} {{profile.homeAddress.postalCode}}
```

**Pie de página:**
![pie de página](/help/challenges/assets/c2-footer.png)

**Recorrido**

![ Recorrido ](/help/challenges/assets/c2-journey.png)

+++
