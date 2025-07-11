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
source-git-commit: 7d812f589172c5052a1e9bfcf6a99d0769a6c2c7
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 2%

---

# Utilice Decisioning para personalizar ofertas web

Este tutorial se basa en una configuración de segmentación de audiencia creada anteriormente con Adobe Experience Platform (AEP) Web SDK. En el [tutorial anterior](https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/create-audiences-using-web-sdk/introduction), las preferencias del usuario, como el interés en acciones, bonos o certificados de depósito (CD), se capturaron y se usaron para segmentar a individuos en audiencias segmentadas dentro de Experience Platform. Este tutorial se basa en esa base al utilizar Adobe Journey Optimizer (AJO) Decisioning para ofrecer ofertas financieras personalizadas a esas audiencias en tiempo real, lo que mejora tanto la participación como los resultados de conversión.


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
