---
title: Configuración de esquemas, conjuntos de datos y flujos de datos XDM en AEP
description: Creación de esquemas, conjuntos de datos y flujos de datos XDM
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
exl-id: 0efa418a-5b4f-4012-a6fc-afaa34a59285
source-git-commit: 15b2379c251ed0d7583a01fb6af67815322456cf
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---

# Configuración de esquemas, conjuntos de datos y flujos de datos XDM en AEP

## Crear esquema XDM

* Iniciar sesión en Adobe Experience Platform
* Administración de datos -> Esquemas -> Crear esquema

* Cree un esquema basado en eventos XDM llamado _Asesores financieros_. Si no está familiarizado con la creación de un esquema, siga esta [documentación](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/tutorials/create-schema-ui)

* Añada la siguiente estructura al esquema. El elemento PreferredFinancialInstrument almacena la preferencia del usuario por Stocks, Bonds, CD. **__techmarketingdemos_**&#x200B;es el id. del inquilino y será diferente en su entorno.
  ![xdm-schema](assets/xdm-schema.png)

* El elemento PreferredFinancialInstrument tiene valores de enumeración definidos como se muestra a continuación
  ![enum-values](assets/enum-values.png)

* Asegúrese de que el esquema esté habilitado para el perfil.

## Crear un conjunto de datos basado en el esquema

Un conjunto de datos **en Adobe Experience Platform (AEP)** es un contenedor de almacenamiento estructurado que se usa para ingerir, almacenar y activar datos basados en un esquema XDM definido.


* Administración de datos -> Conjuntos de datos -> Crear conjunto de datos
* Cree un conjunto de datos llamado _Conjunto de datos de asesores financieros_ basado en el esquema XDM (asesores financieros) creado en el paso anterior.

* Asegúrese de que el conjunto de datos esté habilitado para el perfil

## Crear una secuencia de datos

Un conjunto de datos en Adobe Experience Platform es como un canal seguro (o autopista) que conecta su sitio web o aplicación a los servicios de Adobe, lo que permite que los datos ingresen y que el contenido personalizado regrese.

* Recopilación de datos > Flujos de datos y, a continuación, haga clic en Nuevo flujo de datos. Asigne un nombre a la secuencia de datos _Financial Advisors DataStream_

* Proporcione los siguientes detalles como se muestra en la captura de pantalla siguiente
  ![secuencia de datos](assets/datastream.png)
* Haga clic en Guardar y, a continuación, haga clic en Agregar asignación y agregue el servicio Adobe Experience Platform y el conjunto de datos de evento como se muestra
  ![asignación de secuencia de datos](assets/datastream-service.png)

* Elija el conjunto de datos de evento adecuado (creado anteriormente).

* Guarde la secuencia de datos

