---
title: Crear campaña
description: Cree una campaña para dirigirse a los usuarios que han elegido recibir notificaciones push y envíe el mensaje a la hora programada.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
exl-id: 94fda23f-e26a-494b-8e5c-6c442bae61c4
source-git-commit: c339fe796af1e691cd3b1c98cd6ba8a8772551e4
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 1%

---

# Crear campaña

En este paso, creará una campaña en Adobe Journey Optimizer para enviar notificaciones push web programadas a los usuarios que se han suscrito. La campaña se dirige a un público apto y envía mensajes en un momento predefinido, lo que permite una participación planificada y basada en el público.

* Iniciar sesión en Journey Optimizer
* Vaya a Administración de Recorrido | Campañas | Crear campañas

## Especificar la configuración de campaña


Especifique el nombre de la campaña

![campaign-name](assets/campign-push-notification.png)

## Asociar acción con la campaña

Asocie la configuración del canal push creada anteriormente en este tutorial.

![campaign-action](assets/campign-push-notification-action.png)

## Asociar audiencia con la campaña

Asociar la audiencia `AudienceForPush` con la campaña

![audiencia de campaña](assets/campign-push-notification-audience.png)

## Creación de contenido para la notificación push

Cree contenido push básico para probar la notificación push. Especifique el título y el cuerpo del mensaje como se muestra a continuación

![contenido-para-notificación-push](assets/campign-push-notification-content.png)

## Programación de la campaña

Programe la campaña según sus necesidades

![campaña de programación](assets/campign-push-notification-schedule.png)

Finalmente, asegúrese de activar la campaña.

## Prueba de la campaña

Para probar la campaña, primero habilite las notificaciones en la página web [activando](http://localhost:3000) cuando se le solicite. Una vez que se haya suscrito, espere a que la campaña se ejecute a su hora programada. Cuando se ejecute la campaña, debería recibir la notificación push en el explorador.
