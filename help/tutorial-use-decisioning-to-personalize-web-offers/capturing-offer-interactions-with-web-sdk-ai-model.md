---
title: Captura de interacciones de oferta con Adobe Web SDK para la formación sobre modelos de IA
description: Este artículo se centra en capturar los datos de interacción del usuario (como las impresiones de ofertas y los clics) mediante Adobe Experience Platform Web SDK (alloy.js). Estos datos sirven de base para entrenar modelos de IA en Adobe Journey Optimizer (AJO) para clasificar de forma inteligente ofertas basadas en el comportamiento del usuario y las señales contextuales.
feature: Decisioning
topic: Integrations
role: User
level: Beginner
doc-type: Article
last-substantial-update: 2025-07-08T00:00:00Z
jira: KT-18451
source-git-commit: dfb280df3453e7811dffd95b9af664b873a9af31
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 0%

---


# Captura de interacciones de oferta con Adobe Web SDK para la formación sobre modelos de IA

Este artículo muestra cómo capturar eventos de interacción de ofertas (como impresiones o clics) mediante Adobe Experience Platform Web SDK llamando a alloy(&quot;sendEvent&quot;, ...) directamente en el código de JavaScript. Los datos se incorporarán en AEP y se utilizarán para entrenar modelos de IA en Adobe Journey Optimizer (AJO) para una clasificación de ofertas más inteligente basada en el comportamiento en tiempo real.

## Requisitos previos

Antes de empezar, asegúrese de que se cumplan las siguientes condiciones:

- Una propiedad de Adobe Launch en funcionamiento con la extensión Adobe Experience Platform Web SDK instalada.

- Un [conjunto de datos](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/decisioning/experience-decisioning/collect-event-data/create-dataset) configurado y asignado a su zona protegida de AEP.

- Sitio web en el que se implementa Launch.


## Crear esquemas y conjuntos de datos para eventos de interacción de ofertas

Para recopilar eventos de experiencia, primero debe crear un conjunto de datos al que se envíen estos eventos.

Siga los pasos mencionados en este [artículo para crear el esquema y el conjunto de datos necesarios](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/decisioning/experience-decisioning/collect-event-data/create-dataset)

## Creación de una secuencia de datos en AEP

![flujo de datos](assets/ai-model-data-stream.png)
Añadir el servicio Adobe Experience Platform al conjunto de datos
![servicio-flujo-datos](assets/data-stream-service.png)

## Configuración de etiquetas de Adobe Experience Platform con Web SDK

En la configuración de la extensión:

Configurar la extensión de Adobe Experience Platform Web SDK para utilizar la secuencia de datos creada
