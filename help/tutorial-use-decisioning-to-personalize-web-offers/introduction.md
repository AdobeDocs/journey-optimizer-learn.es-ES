---
title: Utilice Decisioning para personalizar ofertas web
description: Aprenda a utilizar Journey Optimizer (AJO) Decisioning para ofrecer ofertas personalizadas en una página web aprovechando la segmentación de audiencia integrada en Experience Platform (AEP).
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00.000Z
jira: KT-17728
exl-id: 382ee746-e8cd-4843-bfe9-913df8914136
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: a984631b-2bae-4860-9b15-69c41a799dcb
    internal-label: APIs and SDKs
subfeature_v2:
  - id: a7a194a0-75e2-4913-8a83-14714fbf68e6
    internal-label: Decisioning API
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 7%
---
# Utilice Decisioning para personalizar ofertas web

Este tutorial se basa en una configuración de segmentación de audiencia creada anteriormente con Adobe Experience Platform (AEP) Web SDK. En el [tutorial anterior](https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/create-audiences-using-web-sdk/introduction), las preferencias del usuario, como el interés en acciones, bonos o certificados de depósito (CD), se capturaron y se usaron para segmentar a individuos en audiencias segmentadas dentro de Experience Platform. Este tutorial se basa en esa base al utilizar Adobe Journey Optimizer (AJO) Decisioning para ofrecer ofertas financieras personalizadas a esas audiencias en tiempo real, lo que mejora tanto la participación como los resultados de conversión.


## Requisitos previos para este tutorial

* Acceso a Experience Platform

* Comprensión básica de los conceptos de Experience Platform (perfiles, audiencias, conjuntos de datos)

* Familiaridad con Journey Optimizer

* Conocimientos básicos de JavaScript (leer y escribir funciones sencillas)

* Capacidad para utilizar las herramientas de desarrollo del explorador (pestañas Consola y Red)


## Objetivo

Este tutorial le guía a través del envío de ofertas de inversión personalizadas, como acciones, bonos o CD, en un sitio web mediante Journey Optimizer. Al aprovechar la segmentación de audiencia y las estrategias de toma de decisiones, aprenderá a asegurarse de que cada visitante vea la oferta más relevante en función de sus preferencias.

## Herramientas utilizadas

* Adobe Experience Platform (AEP)
* Adobe Journey Optimizer (AJO)
* Etiquetas de Adobe Experience Platform
* AEP Web SDK (`Alloy.js`)
* Segmentación de AEP Edge
* Una página web para mostrar las ofertas
