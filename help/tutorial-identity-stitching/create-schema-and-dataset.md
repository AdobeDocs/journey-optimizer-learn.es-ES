---
title: Configuración de esquemas, conjuntos de datos y flujos de datos XDM en AEP
description: Creación de esquemas, conjuntos de datos y flujos de datos XDM
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: 8bb85ba7-3c50-4596-88f8-e112c48a8253
source-git-commit: 82d82b3aac2bf91e259b01fd8c6b4d6065f9640a
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# Configuración de esquemas, conjuntos de datos y flujos de datos XDM en AEP

## Crear esquema XDM

Para utilizar Adobe Experience Platform Web SDK (Alloy.js) en una página web, las etiquetas de AEP deben asociarse a una secuencia de datos asignada a un esquema de eventos XDM. La SDK web (alloy.sendEvent) envía datos a AEP como eventos de experiencia, que deben ajustarse a un esquema XDM basado en la clase XDM ExperienceEvent.

Para crear un esquema XDM

* Iniciar sesión en Adobe Experience Platform
* Administración de datos -> Esquemas -> Crear esquema

* Cree un esquema basado en eventos XDM llamado **_Asesores financieros_**. Si no está familiarizado con la creación de un esquema, siga esta [documentación](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui)


* Asegúrese de que el esquema esté habilitado para el perfil.

## Crear un conjunto de datos basado en el esquema

Un conjunto de datos **en Adobe Experience Platform (AEP)** es un contenedor de almacenamiento estructurado que se usa para ingerir, almacenar y activar datos basados en un esquema XDM definido.


* Administración de datos -> Conjuntos de datos -> Crear conjunto de datos
* Cree un conjunto de datos llamado **_Conjunto de datos de asesores financieros_** basado en el esquema XDM (asesores financieros) creado en el paso anterior.

* Asegúrese de que el conjunto de datos esté habilitado para el perfil

## Crear una secuencia de datos

Un conjunto de datos en Adobe Experience Platform es como un canal seguro (o autopista) que conecta su sitio web o aplicación a los servicios de Adobe, lo que permite que los datos ingresen y que el contenido personalizado regrese.

* Vaya a Recopilación de datos > Flujos de datos y haga clic en Nuevo flujo de datos. Asigne un nombre a la secuencia de datos **_Financial Advisors DataStream_**

* Proporcione los siguientes detalles como se muestra en la captura de pantalla siguiente
  ![secuencia de datos](assets/datastream.png)
* Haga clic en Guardar y, a continuación, haga clic en Agregar asignación y agregue el servicio Adobe Experience Platform y el conjunto de datos de evento como se muestra
  ![asignación de secuencia de datos](assets/datastream-service.png)

* Elija el conjunto de datos de evento adecuado (creado anteriormente).

* Guarde la secuencia de datos.
