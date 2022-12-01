---
title: Desafío de Reposición de Productos
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
ht-degree: 2%

---

# Desafío de Reposición de Productos

| Desafío | Reposición de productos |
|---|---|
| Grupo de usuarios | Administrador de recorridos |
| Capacidades necesarias | <ul><li>[Creación de segmentos](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-segments.html?lang=en)</li><li> [Importación y creación de contenido de correo electrónico HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/import-and-author-html-email-content.html?lang=en)</li><li>[Caso de uso: Segmento de lectura](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=en)</li> |
| Recursos que se van a descargar | [Archivos de correo electrónico de recopilación estacional](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip) |

## La historia

Al navegar por el sitio web de Luma, los clientes pueden añadir productos que estén interesados en una lista de deseos. Lo que permite a Luma enviar a los clientes mensajes de marketing dirigidos e información sobre los productos.

## Su desafío

Luma le pide que implemente un recorrido en Journey Optimizer que notifique a los clientes, que tienen un elemento en su lista de deseos que antes no estaba en existencias, cuando este elemento vuelve a estar en existencias.

## Definir el segmento: elementos de lista de deseos fuera de existencias

Para dirigirse a los clientes potenciales interesados cuando se rebloqueen los productos, cree un segmento que esté formado por clientes

* Que han agregado al menos un elemento a su lista de deseos (use el tipo de evento): [!UICONTROL Ahorro de comercio para versiones más recientes])
* Que era **sin existencias** en los últimos 3 meses (utilizar cantidad de existencias = 0)
* Y desde entonces no han comprado el artículo.

Asigne un nombre a este segmento: *su nombre - Lista de deseos fuera de existencias*

+++**COMPRUEBE SU TRABAJO**

Este es el aspecto que debería tener el segmento:

![Segmento: elementos de lista de deseos fuera de existencias](/help/challenges/assets/C1-S2.png)

Clientes que han agregado un elemento a su lista de deseos que no estaba en existencias en los últimos 3 meses:

* Evento: Guardar para versiones más recientes
   * Incluir al menos 1
   * Donde la cantidad de stock es 0

y no han comprado desde entonces el artículo:

* Excluya todos los tipos de eventos de Purchases donde el SKU coincida con el SKU del **Guardar para evento posterior**.

>[!TIP]
> * Seleccione el SKU en Guardar para versiones más recientes en la sección *Examinar variables* sección
> * Utilice la opción de comparación al soltar el SKU en Guardar para más adelante en el campo de evento


Compruebe el código en la esquina inferior derecha de la pantalla Editar segmento, en Eventos. El código debería tener este aspecto:

Código:
```(Include have at least 1 Save For Laters event where ((Stock Quantity equals 0)) THENExclude all  Purchases events where ((SKU equals Save For Laters1 SKU)) ) and occurs in last 3 month(s)```

+++

### Crear correo electrónico: reabastecimiento de productos de Luma

Notifique a los clientes que hayan agregado un artículo sin existencias con una llamada para iniciar la compra ahora que el artículo ha vuelto a estar en existencias.

### Creación del recorrido: notificación de repuesta de productos

Cuando un artículo que anteriormente no estaba en existencias vuelva a estar en existencias, notifique a los clientes que hayan agregado un artículo que no estaba en existencias con una llamada para iniciar la compra ahora que el artículo ha vuelto a estar en existencias.

1. Cree un recorrido llamado &quot;your name_Luma - Product Restock
1. El recorrido debe activarse cuando un producto vuelva a estar en existencias
1. Envíe el *Reabastecimiento de productos Luma* enviar correo electrónico a
1. Usuarios que habían agregado este elemento a su lista de deseos mientras no estaba en existencias

>[!TIP]
>
> Utilice el evento comercial existente. Debe agregar una condición que compruebe que el SKU de reabastecimiento está incluido en (cualquier) tipo de evento guardado para los posteriores.

+++**CRITERIOS DE ÉXITO**

Prueba del recorrido:

1. Asegúrese de que el evento de calificación de segmentos tenga el espacio de nombres = correo electrónico
1. Anule los parámetros de correo electrónico predeterminados y configúrelos en su propia dirección de correo electrónico (consulte el correo electrónico n.º 1 para obtener instrucciones)
1. Establecer el recorrido en modo de prueba
1. Déclencheur de un evento : introduzca los siguientes datos:

   * Descripción: Olvídense de las máquinas elegantes y las membresías costosas - el Harmony Lumaflex Strength Band Kit es todo lo que usted necesita para un entrenamiento asombroso. El kit tiene todo lo necesario para una amplia gama de ejercicios de fortalecimiento y tonificación.
   * Nombre: Kit de bandas de fuerza de la armónica Lumaflex
   * Precio: 22
   * ID del producto: 24-UG03
   * URL de imagen del producto: https://publish1034.adobedemo.com/content/dam/luma/en/products/gear/fitness-equipment/ug03-bk-0.jpSKU: 24-UG03
   * Tipo de evento de stock: restock
   * Identificador de perfil: Jenna_Palmer9530@emailsim.io

Debe recibir el correo electrónico &quot;Reaprovisionamiento de productos por correo electrónico de Luma&quot; con los detalles del producto y la personalización para Jenna.

+++

+++**COMPRUEBE SU TRABAJO**

Este es el aspecto que debería tener el recorrido:

![Recorrido de reposición de productos](/help/challenges/assets/c3-j3-journey.png)

Condición: En lista de deseos

![Condición - en lista de deseos](/help/challenges/assets/c3-j3-condition.png)

Código de condición:

```in(@{LumaProductRestock._wwfovlab065.sku},#{ExperiencePlatform.ExperienceEvents.experienceevent.all(currentDataPackField.eventType=="commerce.saveForLaters").productListItems.all().SKU})```

+++
