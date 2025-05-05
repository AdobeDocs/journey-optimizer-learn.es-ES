---
title: Reto de reposición de productos
description: Aplique lo que ha aprendido sobre la creación de segmentos y pruebe sus habilidades.
jira: KT-8417
feature: Segments
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 305aaf4c-7f5d-4f6f-abeb-466208f1fe48
source-git-commit: 5c763ec877c75c07132f4cc714d63695e12638dc
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 100%

---

# Reto de reposición de productos

| Reto | Reposición de productos |
|---|---|
| Grupo de usuarios | Administrador de recorridos |
| Capacidades necesarias | <ul><li>[Creación de segmentos](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=es)</li><li> [Importación y creación de contenido de correo electrónico HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/import-and-author-html-email-content.html?lang=es)</li><li>[Caso de uso: Segmento de lectura](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=es& lang=es)</li> |
| Recursos que se van a descargar | [Archivo de correo electrónico de reserva de producto](/help/challenges/assets/email-assets/ProductRestockEmail.html.zip) |

## La historia

Al navegar por el sitio web de Luma, los clientes pueden añadir productos en los que estén interesados en una lista de deseos, lo que permite a Luma enviar a los clientes mensajes de marketing dirigidos e información sobre los productos.

## Su reto

Luma le pide que implemente un recorrido en Journey Optimizer que notifique a los clientes, quienes tienen un producto en su lista de deseos que está agotado, cuando este vuelva a estar disponible. El equipo creativo le proporciona el [Archivo de correo electrónico de reserva de producto](/help/challenges/assets/email-assets/ProductRestockEmail.html.zip).

>[!BEGINTABS]

>[!TAB Tarea]

## 1. Defina el segmento: productos agotados en la lista de deseos

Para dirigirse a los clientes potenciales interesados cuando los productos vuelvan a estar disponibles, cree un público que esté formado por los siguientes clientes:

* que han agregado al menos un producto a su lista de deseos (use el tipo de evento: [!UICONTROL Comercio Guardar para más tarde])
* Que ha estado agotado durante los últimos tres meses (utilizar cantidad de existencias = 0)
* Y desde entonces no han comprado el producto.

>[!TIP]
>Excluya los tipos de eventos de Compras donde el SKU coincida con el del *evento Guardar para más tarde*. Puede encontrar el campo en la sección *Examinar variables*.

Asigne un nombre a este segmento: `Out-of-stock-Wishlist`


### 2. Creación del recorrido: notificación de reabastecimiento de producto

Cuando un producto que antes estaba agotado vuelva a estar disponible, notifique a los clientes que lo hayan añadido con una llamada para que puedan comprar ahora que el producto está disponible.

1. Llame al recorrido: `Product Restock`
2. El recorrido tiene que activarse cuando el producto vuelva a estar disponible
3. Envíe el *Correo electrónico de repuesta de productos* a
4. Usuarios que habían añadido este producto a la lista de deseos mientras estaba agotado

>[!TAB Requisitos de éxito]

Prueba del recorrido:

1. Asegúrese de que el evento de segmento leído tenga el Área de nombres = `Luma CRM ID`
1. Anule los parámetros de correo electrónico predeterminados y configúrelos en su propia dirección de correo electrónico (consulte el correo electrónico n.º 1 para obtener instrucciones)
1. Establezca el recorrido en modo de prueba
1. Active un evento. Introduzca los siguientes datos:

   * Descripción: olvídese de las máquinas elegantes y las suscripciones costosas, el Harmony Lumaflex Strength Band Kit es todo lo que necesita para un entrenamiento increíble. El kit tiene todo lo necesario para una amplia gama de ejercicios de fortalecimiento y tonificación.
   * Nombre: Harmony Lumaflex Strength Band Kit
   * Precio: 22
   * ID del producto: 24-UG03
   * URL de la imagen del producto: https://publish1034.adobedemo.com/content/dam/luma/en/products/gear/fitness-equipment/ug03-bk-0.jpSKU: 24-UG03
   * Tipo de evento de stock: reabastecimiento
   * Identificador del perfil: Jenna_Palmer9530@emailsim.io

Tiene que recibir el correo electrónico “Reabastecimiento de productos por correo electrónico de Luma” con la información del producto y la personalización para Jenna.

>[!TAB Compruebe su trabajo]

Este es el aspecto que debería tener el segmento:

![Segmento: productos agotados en la lista de deseos](/help/challenges/assets/C1-S2.png)


Este es el aspecto que debería tener el recorrido:

![Recorrido de reabastecimiento de productos](/help/challenges/assets/c3-j3-journey.png)

Condición: en la lista de deseos

![Condición: en la lista de deseos](/help/challenges/assets/c3-j3-condition.png)

Código de condición:

```in(@{LumaProductRestock._wwfovlab065.sku},#{ExperiencePlatform.ExperienceEvents.experienceevent.all(currentDataPackField.eventType=="commerce.saveForLaters").productListItems.all().SKU})```


>[!TIP]
> * Seleccione el SKU en Guardar para más tarde en la sección *Examinar variables*
> * Utilice la opción de comparación al soltar el SKU en Guardar para más tarde en el campo de evento

Compruebe el código en la esquina inferior derecha de la pantalla Editar segmento, en Eventos. El código debería tener este aspecto:

Código:
```(Include have at least 1 Save For Laters event where ((Stock Quantity equals 0)) THENExclude all  Purchases events where ((SKU equals Save For Laters1 SKU)) ) and occurs in last 3 month(s)```

>[!ENDTABS]

### Crear correo electrónico: reabastecimiento de productos de Luma

Notifique a los clientes que hayan añadido un producto agotado con una llamada para empezar a comprar ahora que el producto está disponible.



>[!TIP]
>
> Utilice el evento empresarial existente. Añadir una condición que compruebe que el SKU de reabastecimiento está incluido en (cualquier) tipo de evento guardar para más tarde.
>




