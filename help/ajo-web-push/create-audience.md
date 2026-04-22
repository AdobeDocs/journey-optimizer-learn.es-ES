---
title: Creación de público
description: Defina un segmento en Adobe Experience Platform dirigido a los usuarios aptos para recibir notificaciones push.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 3d342c5c4de4dda221ce4427b1e4aef7ef8c22cc
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 3%

---

# Creación de público

Para crear una audiencia para la campaña, defina un segmento en Adobe Experience Platform para los usuarios aptos para recibir notificaciones push. En este tutorial, los usuarios que tienen una suscripción push activa (el token push existe), no se han excluido de las notificaciones (el indicador de Lista de bloqueados de la es falso) y están asociados a la configuración de la aplicación especificada (el identificador de aplicación es igual a `my-first-push`). Estos usuarios pueden recibir notificaciones push web a través de campañas o recorridos en Adobe Journey Optimizer. Después de crear la audiencia, asegúrese de que se ha evaluado para que los perfiles se rellenen y estén listos para la segmentación.
A continuación, esta audiencia se utiliza en la campaña para enviar mensajes push web programados solo a los usuarios suscritos.

![create-audience](assets/push-audience.png)

