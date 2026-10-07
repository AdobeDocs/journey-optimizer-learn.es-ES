---
title: Crear audiencias con Web SDK
description: En este tutorial, aprenderá a capturar las preferencias de usuario a través de un formulario web, enviar esos datos a Adobe Experience Platform (AEP) en tiempo real y calificar dinámicamente a los usuarios en audiencias segmentadas en función de sus selecciones. Al combinar Adobe Tags (Launch), AEP Web SDK (Alloy.js) y la segmentación de Edge, puede habilitar oportunidades de personalización inmediatas para clientes interesados en acciones, bonos o certificados de depósito (CD).
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00.000Z
jira: KT-17923
exl-id: ebaa3aa5-0a08-43fd-8d06-8e4b5d8dee05
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
source-wordcount: '268'
ht-degree: 0%
---
# Crear audiencias con Web SDK

En este tutorial, aprenderá a capturar las preferencias de usuario a través de un formulario web, enviar esos datos a Adobe Experience Platform (AEP) en tiempo real y calificar dinámicamente a los usuarios en audiencias segmentadas en función de sus selecciones. Al combinar Adobe Tags (Launch), AEP Web SDK (Alloy.js) y la segmentación de Edge, puede habilitar oportunidades de personalización inmediatas para clientes interesados en acciones, bonos o certificados de depósito (CD).

## Requisitos previos para este tutorial

* Acceso a Adobe Experience Platform

* Comprensión básica de los conceptos de Adobe Experience Platform (perfiles, audiencias, conjuntos de datos)

* Familiaridad con etiquetas de Adobe (Launch): Configuración de elementos de datos y reglas

* Conocimientos básicos de JavaScript (leer y escribir funciones sencillas)

* Capacidad para utilizar las herramientas de desarrollo del explorador (fichas Consola y Red)


## OBJETIVO

El objetivo de este tutorial es crear y clasificar tres audiencias distintas en Adobe Experience Platform (AEP):

* Clientes interesados en las acciones

* Clientes interesados en Bonos

* Clientes interesados en los CD

Los usuarios envían sus preferencias a través de un formulario web y estas se incorporan mediante AEP Web SDK con Adobe Launch, lo que permite la calificación de audiencias en tiempo real.

## Herramientas utilizadas

* Adobe Experience Platform (AEP)

* Etiquetas de Adobe Experience Platform

* AEP Web SDK (Alloy.js)

* Segmentación de AEP Edge

* Una página web con un formulario de preferencias
