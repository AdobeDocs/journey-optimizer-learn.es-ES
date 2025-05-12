---
title: Personalización de ofertas web con Decisioning
description: Aprenda a utilizar Journey Optimizer (AJO) Decisioning para ofrecer ofertas personalizadas en una página web aprovechando la segmentación de audiencia integrada en Experience Platform (AEP).
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17728
exl-id: 382ee746-e8cd-4843-bfe9-913df8914136
source-git-commit: 0c42bf9a9af53bf80a14d904733ae0c1f03be0ee
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 1%

---

# Utilice la toma de decisiones para personalizar ofertas web

Este tutorial se basa en una configuración de segmentación de audiencia creada anteriormente con Adobe Experience Platform (AEP) Web SDK. En el [tutorial anterior](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/create-audiences-using-web-sdk/introduction), las preferencias del usuario, como el interés en acciones, bonos o certificados de depósito (CD), se capturaron y utilizaron para segmentar a individuos en audiencias segmentadas dentro de Adobe Experience Platform (AEP). Este tutorial se basa en esa base al utilizar Adobe Journey Optimizer (AJO) Decisioning para ofrecer ofertas financieras personalizadas a esas audiencias en tiempo real, lo que mejora tanto la participación como los resultados de conversión.

Puede probar las ofertas personalizadas de AJO en directo mediante el vínculo siguiente.
[Haz clic aquí para ver la demostración en vivo](https://gbedekar489.github.io/finwise/welcome.html) — la página mostrará ofertas en tiempo real basadas en tus preferencias de inversión.

## Requisitos previos para este tutorial

* Acceso a Adobe Experience Platform

* Comprensión básica de los conceptos de Adobe Experience Platform (perfiles, audiencias, conjuntos de datos)

* Familiaridad con Adobe Journey Optimizer

* Conocimientos básicos de JavaScript (leer y escribir funciones sencillas)

* Capacidad para utilizar las herramientas de desarrollo del explorador (pestañas Consola y Red)


## Meta

Este tutorial le guía a través del envío de ofertas de inversión personalizadas, como acciones, bonos o CD, en un sitio web mediante Adobe Journey Optimizer (AJO). Al aprovechar la segmentación de audiencia y las estrategias de toma de decisiones, aprenderá a asegurarse de que cada visitante vea la oferta más relevante en función de sus preferencias.

## Herramientas utilizadas

* Adobe Experience Platform (AEP)
* Adobe Journey Optimizer (AJO)
* Etiquetas de Adobe Experience Platform
* AEP Web SDK (Alloy.js)
* Segmentación de AEP Edge
* Una página web para mostrar las ofertas
