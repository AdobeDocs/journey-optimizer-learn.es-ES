---
title: Configuración de esquemas XDM, conjuntos de datos, flujos de datos y audiencias en AEP
description: Creación de esquemas, conjuntos de datos, flujos de datos y audiencias XDM
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-17923
exl-id: 0efa418a-5b4f-4012-a6fc-afaa34a59285
source-git-commit: 163edfb3367d03729d68c9339ee2af4a0fe3a1b3
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# Configuración de esquemas, conjuntos de datos, flujos de datos y audiencias XDM en AEP

* Iniciar sesión en Adobe Experience Platform

* Cree un esquema basado en eventos XDM llamado Asesores financieros en Journey Optimizer. Si no está familiarizado con la creación de un esquema, siga esta [documentación](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui)

* Añada la siguiente estructura al esquema. El elemento PreferredFinancialInstrument almacena la preferencia del usuario por Stocks, Bonds, CD
  ![xdm-schema](assets/xdm-schema.png)

* El elemento PreferredFinancialInstrument tiene valores de enumeración definidos como se muestra a continuación
  ![enum-values](assets/enum-values.png)

* Asegúrese de que el esquema esté habilitado para el perfil.

## Crear un conjunto de datos basado en el esquema

Un conjunto de datos **en Adobe Experience Platform (AEP)** es un contenedor de almacenamiento estructurado que se usa para ingerir, almacenar y activar datos basados en un esquema XDM definido.

* Cree un conjunto de datos llamado _Conjunto de datos de asesores financieros_ basado en el esquema XDM (asesores financieros) creado en el paso anterior.

* Asegúrese de que el conjunto de datos esté habilitado para el perfil

## Crear una secuencia de datos

Un conjunto de datos en Adobe Experience Platform es como un canal seguro (o autopista) que conecta su sitio web o aplicación a los servicios de Adobe, lo que permite que los datos ingresen y que el contenido personalizado regrese.

* Vaya a AEP > Flujo de datos y haga clic en Nuevo flujo de datos. Asigne un nombre a la secuencia de datos _Financial Advisors DataStream_

* Proporcione los siguientes detalles como se muestra en la captura de pantalla siguiente
  ![secuencia de datos](assets/datastream.png)
* Haga clic en Guardar y, a continuación, haga clic en Agregar asignación y agregue el servicio Adobe Experience Platform y el conjunto de datos de evento como se muestra
  ![asignación de secuencia de datos](assets/datastream-service.png)

* Elija el conjunto de datos de evento adecuado (creado anteriormente).

* Guarde la secuencia de datos

## Crear audiencias

Las audiencias en Adobe Experience Platform son grupos de usuarios creados en función de sus acciones, preferencias o información de perfil para ofrecer experiencias personalizadas.

* Vaya a Cliente -> Audiencias
* Crear audiencias mediante el método de generación de reglas

* Cree las tres audiencias siguientes en AJO utilizando el elemento PreferredFinancialInstrument del esquema de eventos.

   * Clientes interesados en las acciones

   * Clientes interesados en bonos

   * Clientes interesados en el CD

Asegúrese de que el método de evaluación de cada audiencia esté configurado en Edge para la calificación en tiempo real.

Las siguientes capturas de pantalla le ayudarán a crear Audiencias.

![audiencia](assets/rule-based-audience.png)

![evento](assets/event-attribute.png)


![PreferredFinancialInstrument](assets/stock-customers.png)

![audiencia de Edge](assets/audience-edge.png)
