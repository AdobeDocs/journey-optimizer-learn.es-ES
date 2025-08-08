---
title: Seguimiento y elaboración de informes de ofertas de Adobe Journey Optimizer (AJO) entregadas mediante AJO Decisioning
description: Este tutorial amplía una implementación de Adobe Journey Optimizer (AJO) existente que ofrece ofertas personalizadas basadas en datos contextuales como la temperatura. Describe cómo capturar los eventos de impresión e interacción y preparar los datos para la creación de informes dentro de Journey Optimizer.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-07-18T00:00:00Z
jira: KT-18526
exl-id: ae74485f-9ea1-428d-9c07-5db0c5cf93fb
source-git-commit: 39376d745d851bf2c3ed3826b9f550efafd9e8f4
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# Seguimiento e informes de ofertas de Journey Optimizer entregadas mediante AJO Decisioning

Este caso de uso se centra en la activación de los informes y el análisis de rendimiento para las ofertas entregadas a través de Adobe Journey Optimizer (AJO). Cuando las ofertas se personalizan y entregan en función de señales contextuales (como el tiempo o la ubicación), es esencial rastrear tanto las impresiones como las interacciones del usuario para evaluar su eficacia.

Al capturar los eventos decisioning.propositionDisplay y decisioning.propositionInteract mediante Adobe Web SDK y asignarlos a esquemas XDM estructurados en Adobe Experience Platform (AEP), los datos de participación a nivel de oferta están disponibles para el análisis. Estos datos se pueden utilizar en Customer Journey Analytics (CJA) para crear paneles, medir métricas clave como la tasa de pulsaciones (CTR) y comparar el rendimiento de las ofertas en diferentes segmentos de audiencia y condiciones contextuales.

El objetivo es proporcionar información clara y basada en datos sobre el rendimiento de las ofertas personalizadas e informar las estrategias de toma de decisiones futuras.



![tablero de informes](assets/dashboard-reporting.png)


## Requisitos previos para este tutorial

Antes de comenzar, complete el tutorial [Personalización de ofertas con datos del tiempo en tiempo real.](https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/personalizing-offers-with-real-time-weather-data/introduction) Establece todos los componentes básicos, incluidos:

- Integración de Web SDK
- Configuración de ofertas en Adobe Journey Optimizer (AJO)
- Toma de decisiones mediante atributos contextuales como tiempo y temperatura
- Representación de ofertas en tiempo real en una página web

Este tutorial se basa directamente en esa implementación y se centra específicamente en capturar impresiones de ofertas e interacciones para la creación de informes y análisis en Journey Optimizer.
