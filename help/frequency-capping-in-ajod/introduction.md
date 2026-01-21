---
title: Implementación de límites de frecuencia en ofertas de Adobe Journey Optimizer (AJO) entregadas mediante AJO Decisioning
description: Este tutorial amplía una implementación de Adobe Journey Optimizer (AJO) existente al habilitar el límite de frecuencia en ofertas servidas con AJO Decisioning. Describe cómo capturar los eventos de impresión e interacción utilizados en el límite de frecuencia.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00Z
jira: KT-18526
exl-id: ae74485f-9ea1-428d-9c07-5db0c5cf93fb
source-git-commit: bef6d831c639d40514552dae3ff20132626a4a09
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 0%

---

# Implementación de límites de frecuencia en ofertas de Adobe Journey Optimizer (AJO) entregadas mediante AJO Decisioning

Este tutorial muestra cómo aplicar un límite de frecuencia a las ofertas de Adobe Journey Optimizer para controlar la frecuencia con la que los usuarios ven la misma oferta a lo largo del tiempo.

Al capturar los eventos decisioning.propositionDisplay y decisioning.propositionInteract a través de Adobe Web SDK y asignarlos a esquemas XDM en Adobe Experience Platform (AEP), Adobe Journey Optimizer puede rastrear con precisión las impresiones e interacciones de ofertas, lo que permite limitar la frecuencia con la que se muestra una oferta a un usuario.

## Requisitos previos para este tutorial

Antes de continuar, asegúrese de que tiene una campaña de Adobe Journey Optimizer válida que utiliza Decisioning y que sirve activamente ofertas a una superficie web.

Este tutorial supone que la entrega de ofertas ya está funcionando y se centra exclusivamente en la configuración y validación del comportamiento de límite de frecuencia.


