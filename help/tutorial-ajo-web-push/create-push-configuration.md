---
title: Crear canal push
description: La configuración del canal push define cómo se envían las notificaciones push web, incluida la configuración de la aplicación y los detalles específicos de la plataforma. También vincula la configuración push con las credenciales requeridas, como las claves VAPID, lo que permite a AJO enviar notificaciones a los usuarios suscritos.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00Z
jira: KT-20879
exl-id: 0a8be7eb-9962-466a-9fcc-022cb84c7b0a
source-git-commit: 676c21ca09e0df8d404b05081d71b147755d65d5
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 0%

---

# Crear canal push

El primer paso es crear un canal push en Adobe Journey Optimizer. Como parte de esta configuración, deberá generar las claves VAPID, que son necesarias para autenticar y habilitar las notificaciones push web. Estas claves se utilizan en la configuración del canal push, lo que permite a AJO enviar notificaciones de forma segura a los usuarios suscritos.

## Generar claves VAPID

VAPID (identificación voluntaria del servidor de aplicaciones) es un estándar de inserción web que permite que el servidor se identifique ante los servicios push (como Chrome, Edge, etc.) uso de pares de claves públicas/privadas para que el proveedor push sepa quién envía la notificación.

Se genera mediante una herramienta como web-push generate-vapid-keys, que crea una clave pública (compartida con el explorador) y una clave privada (conservada en el servidor) que se utilizan juntas para autenticar y enviar mensajes push de forma segura.

Para este tutorial hemos utilizado Node.js para generar las claves VAPID.

Asegúrese de que tiene instalado Node.js. A continuación, ejecute el siguiente comando

`npm install web-push -g `

![web-push](assets/install-web-push.png)

`web-push generate-vapid-keys`

![vapid](assets/vapid-keys.png)

## Crear credencial push

* Inicie sesión en Journey Optimizer

* Navegar a Administración | Canales | CONFIGURACIÓN DE PUSH | Credenciales push| Crear credencial push

* ![credencial de inserción](assets/push-credential.png)

## Crear configuración de canal

* Inicie sesión en Journey Optimizer

* Navegar a Administración | Canales | Crear configuración de canal
  ![configuración de canal](assets/push-channel.png)
