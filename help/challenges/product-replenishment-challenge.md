---
title: Reto de reposición de productos
description: Aplique lo que ha aprendido sobre la creación de segmentos y pruebe sus habilidades.
kt: 8417
feature: Segments
role: User
level: Beginner
hide: true
exl-id: 305aaf4c-7f5d-4f6f-abeb-466208f1fe48
source-git-commit: 0e83d8fbad6bd87ed25980251970898cb5b94bc0
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 100%

---

# Reto de reposición de productos

| Desafío | Reposición de productos |
|---|---|
| Grupo de usuarios | Administrador de recorridos |
| Capacidades necesarias | <ul><li>[Creación de segmentos](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-segments.html?lang=es)</li><li> [Importación y creación de contenido de correo electrónico HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/import-and-author-html-email-content.html?lang=es)</li><li>[Caso de uso: Segmento de lectura](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html? lang=es)</li> |
| Recursos que se van a descargar | [Archivos de correo electrónico de recopilación estacional](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip) |

## La historia

Al navegar por el sitio web de Luma, los clientes pueden añadir productos que les interesen a una lista de deseos. Esto permite a Luma enviar a los clientes mensajes de marketing dirigidos e información sobre los productos.

## Su reto

Luma le pide que implemente un recorrido en Journey Optimizer que notifique a los clientes, quienes tienen un producto en su lista de deseos que está agotado, cuando este vuelva a estar disponible.

## Defina el segmento: productos agotados en la lista de deseos

Para dirigirse a los clientes potenciales interesados cuando los productos vuelvan a estar disponibles, cree un segmento que esté formado por clientes

* que han agregado al menos un producto a su lista de deseos (use el tipo de evento: [!UICONTROL Comercio Guardar para más tarde])
* Que ha estado **agotado** durante los últimos tres meses (utilizar cantidad de existencias = 0)
* Y desde entonces no han comprado el producto.

Asigne un nombre a este segmento: *su nombre, Lista de deseos sin existencias*

+++**COMPRUEBE SU TRABAJO**

Este es el aspecto que debería tener el segmento:

![Segmento: productos agotados en la lista de deseos](/help/challenges/assets/C1-S2.png)

Clientes que han añadido un producto a su lista de deseos que ha estado agotado durante los últimos tres meses:

* Evento: guardar para más tarde
   * Incluir al menos 1
   * Donde la cantidad de stock es 0

y no han comprado desde entonces el producto:

* Excluya los tipos de eventos de Compras donde el SKU coincida con el del **evento Guardar para más tarde**.

>[!TIP]
> * Seleccione el SKU en Guardar para más tarde en la sección *Examinar variables*
> * Utilice la opción de comparación al soltar el SKU en Guardar para más tarde en el campo de evento


Compruebe el código en la esquina inferior derecha de la pantalla Editar segmento, en Eventos. El código debería tener este aspecto:

Código:
```(Include have at least 1 Save For Laters event where ((Stock Quantity equals 0)) THENExclude all  Purchases events where ((SKU equals Save For Laters1 SKU)) ) and occurs in last 3 month(s)```

+++

### Crear correo electrónico: reabastecimiento de productos de Luma

Notifique a los clientes que hayan añadido un producto agotado con una llamada para empezar a comprar ahora que el producto está disponible.

### Creación del recorrido: notificación de reabastecimiento de producto

Cuando un producto que antes estaba agotado vuelva a estar disponible, notifique a los clientes que lo hayan añadido con una llamada para que puedan comprar ahora que el producto está disponible.

1. Cree un recorrido llamado “su nombre_Luma: reabastecimiento de producto”
1. El recorrido tiene que activarse cuando el producto vuelva a estar disponible
1. Envíe el correo de *reabastecimiento de productos Luma* a
1. Usuarios que habían añadido este producto a la lista de deseos mientras estaba agotado

>[!TIP]
>
> Utilice el evento empresarial existente. Tiene que añadir una condición que compruebe que el SKU de reabastecimiento está incluido en (cualquier) tipo de evento guardar para más tarde.

+++**REQUISITOS DE ÉXITO**

Prueba del recorrido:

1. Asegúrese de que el evento de calificación de segmentos tenga el área de nombres = correo electrónico
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

+++

+++**COMPRUEBE SU TRABAJO**

Este es el aspecto que debería tener el recorrido:

![Recorrido de reabastecimiento de productos](/help/challenges/assets/c3-j3-journey.png)

Condición: en la lista de deseos

![Condición: en la lista de deseos](/help/challenges/assets/c3-j3-condition.png)

Código de condición:

```in(@{LumaProductRestock._wwfovlab065.sku},#{ExperiencePlatform.ExperienceEvents.experienceevent.all(currentDataPackField.eventType=="commerce.saveForLaters").productListItems.all().SKU})```

+++
