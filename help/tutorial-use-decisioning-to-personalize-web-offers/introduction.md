---
title: Utilice Decisioning para personalizar ofertas web
description: Aprenda a utilizar Journey Optimizer (AJO) Decisioning para ofrecer ofertas personalizadas en una página web aprovechando la segmentación de audiencia integrada en Experience Platform (AEP).
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17728
exl-id: 382ee746-e8cd-4843-bfe9-913df8914136
source-git-commit: 71c406e7a06c49f01245970c280c6a7beb84da5f
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 1%

---

# Utilice Decisioning para personalizar ofertas web

Este tutorial se basa en una configuración de segmentación de audiencia creada anteriormente con Adobe Experience Platform (AEP) Web SDK. En el [tutorial anterior](https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/create-audiences-using-web-sdk/introduction), las preferencias del usuario, como el interés en acciones, bonos o certificados de depósito (CD), se capturaron y se usaron para segmentar a individuos en audiencias segmentadas dentro de Experience Platform. Este tutorial se basa en esa base al utilizar Adobe Journey Optimizer (AJO) Decisioning para ofrecer ofertas financieras personalizadas a esas audiencias en tiempo real, lo que mejora tanto la participación como los resultados de conversión.

Puede probar las ofertas personalizadas de AJO en directo mediante el vínculo siguiente.
[Haga clic aquí para ver la demostración en vivo](https://gbedekar489.github.io/finwise/welcome.html). La página muestra ofertas en tiempo real basadas en las preferencias de inversión del usuario.

## Requisitos previos para este tutorial

* Acceso a Experience Platform

* Comprensión básica de los conceptos de Experience Platform (perfiles, audiencias, conjuntos de datos)

* Familiaridad con Journey Optimizer

* Conocimientos básicos de JavaScript (leer y escribir funciones sencillas)

* Capacidad para utilizar las herramientas de desarrollo del explorador (pestañas Consola y Red)


## Meta

Este tutorial le guía a través del envío de ofertas de inversión personalizadas, como acciones, bonos o CD, en un sitio web mediante Journey Optimizer. Al aprovechar la segmentación de audiencia y las estrategias de toma de decisiones, aprenderá a asegurarse de que cada visitante vea la oferta más relevante en función de sus preferencias.

## Herramientas utilizadas

* Adobe Experience Platform (AEP)
* Adobe Journey Optimizer (AJO)
* Etiquetas de Adobe Experience Platform
* AEP Web SDK (`Alloy.js`)
* Segmentación de AEP Edge
* Una página web para mostrar las ofertas
