---
title: Implementación de límites de frecuencia en ofertas de Adobe Journey Optimizer (AJO) entregadas mediante AJO Decisioning
description: Este tutorial amplía una implementación de Adobe Journey Optimizer (AJO) existente al habilitar el límite de frecuencia en ofertas servidas con AJO Decisioning. Describe cómo capturar los eventos de impresión e interacción utilizados en el límite de frecuencia.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00.000Z
jira: KT-18526
exl-id: ae74485f-9ea1-428d-9c07-5db0c5cf93fb
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
source-wordcount: '214'
ht-degree: 7%
---
# Implementación de límites de frecuencia en ofertas de Adobe Journey Optimizer (AJO) entregadas mediante AJO Decisioning

Este tutorial muestra cómo aplicar un límite de frecuencia a las ofertas de Adobe Journey Optimizer para controlar la frecuencia con la que los usuarios ven la misma oferta a lo largo del tiempo.

En este tutorial se da por hecho que ya ha configurado una campaña de AJO siguiendo el [tutorial sobre la personalización de ofertas según las condiciones meteorológicas](https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/personalizing-offers-with-real-time-weather-data/introduction)

Al capturar los eventos decisioning.propositionDisplay y decisioning.propositionInteract a través de Adobe Web SDK y asignarlos a esquemas XDM en Adobe Experience Platform (AEP), Adobe Journey Optimizer puede rastrear con precisión las impresiones e interacciones de ofertas, lo que permite limitar la frecuencia con la que se muestra una oferta a un usuario.

## Requisitos previos para este tutorial

Antes de continuar, asegúrese de que tiene una campaña de Adobe Journey Optimizer válida que utiliza Decisioning y que sirve activamente ofertas a una superficie web.

Este tutorial supone que la entrega de ofertas ya está funcionando y se centra exclusivamente en la configuración y validación del comportamiento de límite de frecuencia.




