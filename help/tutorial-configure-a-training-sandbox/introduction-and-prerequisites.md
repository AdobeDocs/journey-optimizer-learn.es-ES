---
title: 'Configuración de un simulador para pruebas de formación: introducción'
description: Aprenda a configurar un simulador para pruebas con fines de formación. Siga los pasos necesarios para configurar los esquemas, ingerir datos de ejemplo y crear eventos.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
exl-id: 8fa673de-9be9-4ab2-94cf-cfa8ac518223
source-git-commit: 8a2062f0719e799dd2d039488e6bba943fb458c4
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 9%

---

# Configuración de un simulador para pruebas de formación: Introducción y requisitos previos

![Tutorial de banner: configuración de un simulador para pruebas de formación](./assets/ajo-banner-configure-training-sandbox.png)

Este tutorial está diseñado para administradores e ingenieros de datos que tienen la tarea de proporcionar un entorno de formación de Adobe Journey Optimizer. Conozca los pasos necesarios para configurar los esquemas, ingerir datos de ejemplo y crear eventos. También creará tres perfiles de prueba que permiten a los alumnos comprobar su trabajo.

Los datos de muestra proporcionados se basan en una empresa ficticia de ropa deportiva llamada _[!DNL Luma]_. [!DNL Luma] tiene tiendas en varios países, una presencia en línea con un sitio web y aplicaciones móviles. [!DNL Luma] utiliza Adobe Journey Optimizer para ofrecer experiencias conectadas, contextuales y personalizadas a sus clientes.

Al final de este tutorial, tendrá un simulador de pruebas que admita el [!DNL Luma] casos de uso cubiertos en los ejercicios prácticos en la [Desafíos de Journey Optimizer](/help/challenges/introduction-and-prerequisites.md) para obtener más información.

## Requisitos previos

Antes de empezar a configurar el simulador para pruebas de formación, asegúrese de que dispone de:

1. Un desarrollo específico [entorno limitado](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/access-control/create-and-manage-sandboxes.html?lang=en).
1. [Ajustes preestablecidos de mensajes de correo electrónico](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/channel-configuration/set-up-email-channel.html?lang=en) configurado para marketing y mensajería transaccional.
1. **[!UICONTROL Administrador de recorridos]** y **[!UICONTROL Administrador de datos]** derechos para el simulador de pruebas de formación.
1. Su [ID de organización](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=es).

1. Los archivos JSON con los datos de ejemplo configurados en su instancia de Journey Optimizer:

   1. Descargue el `luma-data.zip` file [here](/help/tutorial-configure-a-training-sandbox/assets/luma-data.zip), que contiene todos los archivos JSON necesarios para este tutorial.

   1. Desde la carpeta de descargas, mueva la variable `luma-data.zip` en la ubicación deseada del equipo y descomprima el archivo.

      Debe haber tres archivos JSON: `luma-crm.json`, `luma-loyalty.json`, `luma-products.json`.

      Estos archivos contienen los datos de ejemplo que se introducen en el simulador para pruebas.

   1. Abra cada archivo y busque **`yourOrganizationID`** y reemplácelo por su [ID de organización](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=es).

   1. Guarde los archivos.

## Empecemos

Comience con el [Configuración manual de datos](/help/tutorial-configure-a-training-sandbox/manual-data-set-up.md). En este paso, se define la estructura de datos necesaria. Después de completar la configuración de datos, puede ingerir datos en el simulador para pruebas y configurar eventos.
