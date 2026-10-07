---
title: Crear flujo de datos
description: Esta página le guía a través del proceso de creación de un conjunto de datos en Adobe Experience Platform, que es necesario para recopilar datos de Web SDK y enrutarlos a AEP y Adobe Journey Optimizer. La secuencia de datos actúa como conexión entre la aplicación web y los servicios de Adobe, lo que permite procesar la suscripción push y los datos de evento.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00.000Z
jira: KT-20879
exl-id: d419f6a4-67d5-46b5-9ae7-5a317300d1ad
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
source-wordcount: '298'
ht-degree: 0%
---
# Crear flujo de datos

Un conjunto de datos en Adobe Experience Platform (AEP) actúa como el extremo que recibe los datos enviados desde Web SDK. Enruta estos datos a servicios configurados como AEP, Adobe Analytics o Adobe Journey Optimizer. En este tutorial, la secuencia de datos se utiliza para enviar datos de suscripción push web y eventos price.drop a AEP para su activación.

## Crear esquema de eventos para rastrear notificaciones push

Cree un nuevo esquema XDM ExperienceEvent denominado `SchemaForPushNotification`. Agregar los grupos de campos `Push Notification Tracking` y `Commerce Details` a este esquema. Los campos del grupo de campos Detalles de Commerce se utilizarán para recopilar información del producto y almacenar en déclencheur el evento personalizado price.drop.

![esquema de evento](assets/event-schema.png)

## Crear esquema de perfil para guardar el consentimiento del usuario

Para este tutorial, utilizamos el `AJO Push Profile Schema` listo para usar. Este esquema almacena los detalles de la suscripción push del usuario, incluido el token push necesario para enviar notificaciones push web.

![perfil_esquema](assets/profile-schema.png)

## Crear conjuntos de datos para el esquema

Cree un conjunto de datos con el nombre `DataSetForPushNotification` mediante el esquema de eventos creado anteriormente. Para los datos de perfil, use el `AJO Push Profile Dataset` predeterminado, que está asociado con el esquema del perfil push. Anote el ID de `DataSetForPushNotification`, ya que será necesario más adelante en el tutorial al configurar la aplicación mediante el archivo .env.

## Creación de una secuencia de datos con el conjunto de datos de evento y perfil

Cree una nueva secuencia de datos denominada WebPushDataStream con los conjuntos de datos de evento y perfil creados en el paso anterior. Anote el ID de la secuencia de datos, ya que será necesario más adelante en el tutorial al configurar la aplicación mediante el archivo .env.

![secuencia de datos](assets/datastream.png)
