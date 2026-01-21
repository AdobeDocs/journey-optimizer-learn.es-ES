---
title: Habilitar el límite de frecuencia para una campaña de AJO
description: El límite de frecuencia en Adobe Journey Optimizer se aplica al nivel de oferta individual y depende de la captura de eventos de impresión de oferta y de clics. Esto requiere el seguimiento de los eventos decisioning.propositionDisplay y decisioning.propositionInteract mediante Adobe Web SDK y su asignación a un esquema de evento de experiencia XDM actualizado en Adobe Experience Platform.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00Z
jira: KT-18526
source-git-commit: bef6d831c639d40514552dae3ff20132626a4a09
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 0%

---

# Habilitar el límite de frecuencia para una campaña de AJO

Para aplicar un límite de frecuencia a las ofertas, complete los siguientes pasos:

## Actualización del esquema de evento

* Actualice el esquema de evento existente agregando el grupo de campos como se muestra
* ![esquema de evento](assets/schema.png)

## Actualizar el límite de frecuencia de la oferta


* ![oferta](assets/offer-capping.png)

## Añadir token de seguimiento a la oferta

Editar la política de decisión utilizada en la campaña añadiendo una oferta de reserva
![reserva](assets/fallback.png)

El trackingToken y el ItemID se pueden agregar haciendo clic en el icono de directiva Decisión en la navegación izquierda y desglosando el árbol de decisiones para seleccionar el itemID y el trackingToken.

Añada el ID del elemento y el token de seguimiento al div que contiene la oferta, como se muestra a continuación
![id-and-tracking-token](assets/id-and-tracking-token.png)

Esto garantiza que cada oferta procesada incluya un token de seguimiento de datos, que es esencial para lograr un seguimiento preciso de los eventos de impresión y clics.


Active la campaña modificada.


## Envío de eventos de impresión y seguimiento

Modifique el código JavaScript existente para capturar y enviar eventos de impresión e interacción de ofertas a Adobe Experience Platform mediante el SDK web de Adobe. Consulte el [código de ejemplo proporcionado aquí.](capture-impression-click-events.md)


