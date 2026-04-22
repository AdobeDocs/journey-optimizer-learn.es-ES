---
title: Capturar permiso de usuario
description: Cree una página web para registrar el consentimiento del usuario para recibir notificaciones push.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 45f86aeb8fca071436785cc55225d853bb21998f
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---

# Capturar permiso de usuario

Esta página web registra el consentimiento del usuario para recibir notificaciones push. Solicita al usuario que habilite las notificaciones mediante la API de notificaciones del explorador y, al aceptarlas, registra la suscripción push con Adobe Experience Platform mediante Web SDK. Esto garantiza que solo los usuarios seleccionados puedan recibir notificaciones push a través de campañas y recorridos en Adobe Journey Optimizer.

Para habilitar las notificaciones push web, la página carga primero un archivo de configuración llamando a fetch(&quot;/config&quot;) dentro de una función de inicialización. Esta configuración la proporciona una aplicación Node.js e incluye valores clave como el ID del conjunto de datos, el ID de organización, la clave pública VAPID, el ID de aplicación y el ID del conjunto de datos de seguimiento. Una vez cargada la configuración, Adobe Web SDK se inicializa y el service worker se registra para admitir la mensajería push. Cuando un usuario hace clic en Habilitar notificaciones, el explorador le solicita permiso mediante la API de notificaciones web. Si se concede el permiso, Web SDK envía la suscripción push a Adobe Experience Platform y el usuario se marca como &quot;Opted in&quot; durante 24 horas para evitar peticiones de datos repetidas. Puede probar este flujo en la página web local shop-smart.html incluida en la [aplicación de ejemplo](http://localhost:3000/) después de iniciar el servidor.

![permisos-solicitud](assets/request-notifications.png)

