---
title: Configuración de esquemas, conjuntos de datos y flujos de datos XDM en AEP
description: Creación de esquemas, conjuntos de datos y flujos de datos XDM
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18258
exl-id: 1c7fe9e7-ab72-4d7b-960a-512d0e25808b
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: b32bb433-f8c6-4931-8e52-e657230a3bf2
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 0%
---
# Configuración de esquemas, conjuntos de datos y flujos de datos XDM en AEP

## Crear esquema XDM

Para utilizar Adobe Experience Platform Web SDK (Alloy.js) en una página web, las etiquetas de AEP deben asociarse a una secuencia de datos asignada a un esquema de eventos XDM. La SDK web (alloy.sendEvent) envía datos a AEP como eventos de experiencia, que deben ajustarse a un esquema XDM basado en la clase XDM ExperienceEvent.

Para crear un esquema XDM

- Iniciar sesión en Adobe Experience Platform
- Vaya a _&#x200B;**Administración de datos -> Esquemas -> Crear esquema**&#x200B;_

- Cree un esquema basado en eventos XDM llamado **_Weather-Schema_**. Si no está familiarizado con la creación de un esquema, siga esta [documentación](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/tutorials/create-schema-ui)


- Asegúrese de que el esquema tenga los siguientes campos con el tipo de datos adecuado.

- ![esquema meteorológico](assets/weather-schema.png)

- Agregue el grupo de campos _&#x200B;**Detalles web**&#x200B;_ al esquema. Este grupo de campos es necesario para la creación de informes.

## Crear un conjunto de datos basado en el esquema

Un conjunto de datos **en Adobe Experience Platform (AEP)** es un contenedor de almacenamiento estructurado que se usa para ingerir, almacenar y activar datos basados en un esquema XDM definido.

- Vaya a _&#x200B;**Administración de datos -> Conjuntos de datos -> Crear conjunto de datos**&#x200B;_
- Cree un conjunto de datos llamado **_Weather-schema-dataset_** basado en el esquema XDM(_&#x200B;**Weather-Schema**&#x200B;_) creado en el paso anterior.


## Crear una secuencia de datos

Un conjunto de datos en Adobe Experience Platform es como un canal seguro (o autopista) que conecta su sitio web o aplicación a los servicios de Adobe, lo que permite que los datos ingresen y que el contenido personalizado regrese.

- Vaya a _&#x200B;**Recopilación de datos > Flujos de datos**&#x200B;_ y haga clic en Nuevo flujo de datos. Asigne un nombre a la secuencia de datos **weather-related-datastream**


- Proporcione los siguientes detalles como se muestra en la captura de pantalla siguiente
  ![secuencia de datos](assets/datastream.png)
- Haga clic en Guardar, luego haga clic en Agregar asignación y agregue el servicio de Adobe Experience Platform y el conjunto de datos de evento con las casillas de verificación adecuadas seleccionadas
  ![asignación de secuencia de datos](assets/datastream-service.png)

- Guarde la secuencia de datos.


>[!NOTE]
>
>Tenga en cuenta que los conjuntos de datos recién creados pueden tardar hasta 24 horas en estar disponibles para su selección en el Editor de fórmulas de clasificación o en el Editor de Personalization.
