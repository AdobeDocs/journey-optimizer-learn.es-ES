---
title: 'Configuración de una zona protegida para pruebas de formación: introducción'
description: Obtenga información sobre cómo configurar una zona protegida con fines de formación. Siga los pasos necesarios para configurar los esquemas, ingerir datos de muestra y crear eventos.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
jira: KT-9382
role: Admin
level: Beginner
last-substantial-update: 2023-02-01T00:00:00.000Z
exl-id: 8fa673de-9be9-4ab2-94cf-cfa8ac518223
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: aeebb91a-f216-4d5f-8da1-3a7e6f696ed0
    internal-label: Data management activity
  - id: d556b755-390a-43f0-be32-a08cf6236126
    internal-label: Configuration
  - id: bb359667-ec7d-4d4b-8663-5850fc219d32
    internal-label: Administration
subfeature_v2:
  - id: d2e8a157-b3b0-4143-9ff3-809bf400be56
    internal-label: Sandboxes
  - id: efb19423-4da4-4fd1-88d8-5ee8c71ae766
    internal-label: Application settings
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 100%
---
# Configuración de una zona protegida para pruebas de formación: introducción y requisitos previos

![Tutorial de banner: Configuración de una zona protegida para pruebas de formación](./assets/ajo-banner-configure-training-sandbox.png)

Este tutorial está diseñado para administradores e ingenieros de datos responsables de proporcionar un [!DNL Journey Optimizer] entorno de formación de Adobe. Conozca los pasos necesarios para configurar los esquemas, introducir datos de muestra y crear eventos. También puede crear tres perfiles de prueba que permitan a los alumnos verificar su trabajo.

Los datos de muestra proporcionados se basan en una empresa ficticia de ropa deportiva denominada _[!DNL Luma]_. [!DNL Luma] tiene tiendas en varios países, presencia en línea con un sitio web y aplicaciones móviles. [!DNL Luma] utiliza Adobe Journey Optimizer para ofrecer experiencias conectadas, contextuales y personalizadas a sus clientes.

Al final de este tutorial, tiene una zona protegida que admite casos de uso [!DNL Luma] que se tratan en los ejercicios prácticos en la sección de [Retos de Journey Optimizer](/help/challenges/introduction-and-prerequisites.md).

## Requisitos previos

Antes de empezar a configurar la zona protegida para pruebas de formación, asegúrese de lo siguiente:

1. Un desarrollo de la [zona protegida](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/access-control/create-and-manage-sandboxes.html?lang=es) específica.

1. [Ajustes preestablecidos de los mensajes de correo electrónico](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/set-up-email-channel.html?lang=es) configurados para marketing y mensajería transaccional.

1. **[!UICONTROL Administrador de recorrido]** y derechos del **[!UICONTROL Administrador de datos]** para la zona protegida para pruebas de formación.

1. Su [ID de organización](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=es).

1. Los archivos JSON con los datos de muestra, configurados en la instancia de Journey Optimizer:

   1. Descargue el `luma-sample-data.zip` archivo [aquí](/help/tutorial-configure-a-training-sandbox/assets/luma-data/luma-sample-data.zip), que contiene todos los archivos JSON necesarios para este tutorial.

   1. Desde la carpeta de descargas, mueva el archivo `luma-data.zip` a la ubicación deseada en el equipo y descomprímalo.

      Estos archivos contienen los datos de muestra de su zona protegida para pruebas de formación.

   1. Abra cada archivo, busque **`yourOrganizationID`** y reemplácelo por su [ID de organización](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=es).

   1. Guarde los archivos.

## ¡Empecemos!

Comience con la [Configuración manual de los datos](/help/tutorial-configure-a-training-sandbox/manual-data-set-up.md).

En este paso, se define la estructura de datos requerida. Una vez completada la configuración de datos, puede introducir datos en su zona protegida y, a continuación, configurar eventos.
