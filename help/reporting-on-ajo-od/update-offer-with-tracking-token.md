---
title: Seguimiento e informes de ofertas de Adobe Journey Optimizer (AJO) entregadas mediante AJO Offer Decisioning
description: Este tutorial amplía una implementación de Adobe Journey Optimizer (AJO) existente que ofrece ofertas personalizadas basadas en datos contextuales como la temperatura. Describe cómo capturar los eventos de impresión e interacción y preparar los datos para la creación de informes en Journey Optimizer.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
jira: KT-18526
source-git-commit: fa4795d92cf290b867df23277a297c99d6222224
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# Añadir tokens de seguimiento a los artículos de oferta

Para modificar el código en el editor de personalización, siga los pasos:

Vaya a _**Administración de Recorrido ->Campañas**_

Abra la campaña correspondiente y haga clic en el botón _**Detener campaña**_ para detener la campaña.

Abra la campaña detenida y haga clic en el botón _**Modificar campaña**_.

Haga clic en la ficha _**Contenido**_ y, a continuación, haga clic en el botón _**Editar código**_ para abrir el editor de personalización.

Agregue dos nuevos atributos de datos al div como se muestra en la captura de pantalla
![token de seguimiento](assets/offer-item-with-tracking-code.png)

El trackingToken y el ItemID se pueden agregar haciendo clic en el icono de directiva Decisión en la navegación izquierda y desglosando el árbol de decisiones para seleccionar el itemID y el trackingToken.
![token de seguimiento](assets/insert-tracking-token.png)

Esto garantiza que cada oferta procesada incluya un token de seguimiento de datos, que es esencial para lograr un seguimiento preciso de los eventos de impresión y clics.

Guarde los cambios y active la campaña.
