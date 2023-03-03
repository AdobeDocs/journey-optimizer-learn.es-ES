---
title: 'Configuración de una zona protegida de formación: introducción'
description: Obtenga información sobre cómo configurar una zona protegida con fines de formación. Siga los pasos necesarios para configurar los esquemas, ingerir datos de ejemplo y crear eventos.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
last-substantial-update: 2023-02-01T00:00:00Z
exl-id: 8fa673de-9be9-4ab2-94cf-cfa8ac518223
source-git-commit: f7bfe367411f2bae23631ac4ecb34ad1d250381c
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 9%

---

# Configuración de una zona protegida de formación: introducción y requisitos previos

![Tutorial del titular: Configurar una zona protegida de formación](./assets/ajo-banner-configure-training-sandbox.png)

Este tutorial está diseñado para administradores e ingenieros de datos responsables de proporcionar un Adobe [!DNL Journey Optimizer] entorno de formación. Conozca los pasos necesarios para configurar los esquemas, ingerir datos de ejemplo y crear eventos. También puede crear tres perfiles de prueba que permitan a los alumnos comprobar su trabajo.

Los datos de muestra proporcionados se basan en una empresa ficticia de ropa deportiva denominada _[!DNL Luma]_. [!DNL Luma] tiene tiendas en varios países, presencia en línea con un sitio web y aplicaciones móviles. [!DNL Luma] utiliza Adobe Journey Optimizer para ofrecer experiencias conectadas, contextuales y personalizadas a sus clientes.

Al final de este tutorial, tiene una zona protegida que admite el [!DNL Luma] casos de uso cubiertos en los ejercicios prácticos en la [Desafíos de Journey Optimizer](/help/challenges/introduction-and-prerequisites.md) sección.

## Requisitos previos

Antes de empezar a configurar la zona protegida de formación, asegúrese de lo siguiente:

1. Un desarrollo dedicado [espacio aislado](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/access-control/create-and-manage-sandboxes.html?lang=en).

1. [Ajustes preestablecidos de mensaje de correo electrónico](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/set-up-email-channel.html?lang=en) configurado para marketing y mensajería transaccional.

1. **[!UICONTROL Administrador de recorrido]** y **[!UICONTROL Administrador de datos]** derechos para la zona protegida de formación.

1. Su [ID de organización](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=es).

1. Los archivos JSON con los datos de ejemplo, configurados en la instancia de Journey Optimizer:

   1. Descargue la `luma-sample-data.zip` archivo [aquí](/help/tutorial-configure-a-training-sandbox/assets/luma-data/luma-sample-data.zip), que contiene todos los archivos JSON necesarios para este tutorial.

   1. Desde la carpeta de descargas, mueva el `luma-data.zip` archivo a la ubicación deseada en el equipo y descomprimirlo.

      Estos archivos contienen los datos de ejemplo de su zona protegida de formación.

   1. Abra cada archivo y busque **`yourOrganizationID`** y reemplácelo por su [ID de organización](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=es).

   1. Guarde los archivos.

## Vamos a empezar.

Comience con [Configuración manual de los datos](/help/tutorial-configure-a-training-sandbox/manual-data-set-up.md).

En este paso, se define la estructura de datos requerida. Una vez completada la configuración de datos, puede introducir datos en su zona protegida y, a continuación, configurar eventos.
