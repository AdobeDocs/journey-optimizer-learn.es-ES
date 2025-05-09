---
title: Crear audiencias con Web SDK
description: En este tutorial, aprenderá a capturar las preferencias de usuario a través de un formulario web, enviar esos datos a Adobe Experience Platform (AEP) en tiempo real y calificar dinámicamente a los usuarios en audiencias segmentadas en función de sus selecciones. Al combinar Adobe Tags (Launch), AEP Web SDK (Alloy.js) y la segmentación de Edge, puede habilitar oportunidades de personalización inmediatas para clientes interesados en acciones, bonos o certificados de depósito (CD).
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
exl-id: ebaa3aa5-0a08-43fd-8d06-8e4b5d8dee05
source-git-commit: 163edfb3367d03729d68c9339ee2af4a0fe3a1b3
workflow-type: tm+mt
source-wordcount: '266'
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
