---
title: Crear audiencia
description: Defina un segmento en Adobe Experience Platform dirigido a los usuarios aptos para recibir notificaciones push.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00.000Z
jira: KT-20879
exl-id: 427bb35a-d607-48be-845d-9587c4cad86b
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: 66e1fd99-672d-5d64-aa58-eca107f0fbae
    internal-label: Push
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 3%
---
# Creación de público

Para crear una audiencia para la campaña, defina un segmento en Adobe Experience Platform para los usuarios aptos para recibir notificaciones push. En este tutorial, los usuarios que tienen una suscripción push activa (el token push existe), no se han excluido de las notificaciones (el indicador de Lista de bloqueados de la es falso) y están asociados a la configuración de la aplicación especificada (el identificador de aplicación es igual a `my-first-push`). Estos usuarios pueden recibir notificaciones push web a través de campañas o recorridos en Adobe Journey Optimizer. Después de crear la audiencia, asegúrese de que se ha evaluado para que los perfiles se rellenen y estén listos para la segmentación.
A continuación, esta audiencia se utiliza en la campaña para enviar mensajes push web programados solo a los usuarios suscritos.

![create-audience](assets/push-audience.png)
