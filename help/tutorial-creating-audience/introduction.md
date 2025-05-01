---
title: Creación de audiencias
description: Creación de audiencias de AJO basadas en las preferencias de inversión del usuario (acciones, bonos, CD)
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
source-git-commit: f970a1780b1bdf717675cd79c98a38ac422a679f
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---


# Creación de audiencias de AJO basadas en las preferencias de inversión del usuario (acciones, bonos, CD)

En este tutorial, aprenderá a capturar las preferencias de usuario a través de un formulario web, enviar esos datos a Adobe Experience Platform (AEP) en tiempo real y calificar dinámicamente a los usuarios en audiencias segmentadas en función de sus selecciones. Al combinar Adobe Tags (Launch), AEP Web SDK (Alloy.js) y la segmentación de Edge, podrá ofrecer oportunidades de personalización inmediatas para los clientes interesados en acciones, bonos o certificados de depósito (CD).

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

Los usuarios envían sus preferencias a través de un formulario web y estas se incorporan a través de AEP Web SDK mediante Adobe Launch, lo que permite la cualificación de audiencias en tiempo real.

## Herramientas utilizadas

* Adobe Experience Platform (AEP)

* Etiquetas de Adobe Experience Platform

* AEP Web SDK (Alloy.js)

* Segmentación de AEP Edge

* Una página web con un formulario de preferencias





