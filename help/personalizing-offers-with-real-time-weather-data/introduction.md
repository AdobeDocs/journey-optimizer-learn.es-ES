---
title: Personalización de ofertas con datos meteorológicos en tiempo real en Adobe Journey Optimizer mediante SDK web
description: Este tutorial muestra cómo presentar ofertas dinámicas y adaptadas a las condiciones meteorológicas en Adobe Journey Optimizer utilizando datos contextuales en tiempo real y la API de personalización del SDK web de Adobe. Aprenderá a pasar atributos meteorológicos (como temperatura y condiciones) de su sitio web a Adobe Experience Platform, asignarlos a su esquema de evento y utilizarlos en reglas de decisión y fórmulas de clasificación para personalizar ofertas en el momento de cargar la página. Ideal para especialistas en marketing y desarrolladores que buscan mejorar las experiencias digitales con un contexto ambiental en tiempo real.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10
jira: KT-18258
exl-id: f40dd541-470c-4f42-8181-eb1c277ebaa3
source-git-commit: b4cf9b677c6bc142e1013649db16b3a70b405052
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 42%
---
# Descripción del caso de uso

El uso de datos relacionados con el tiempo en Adobe Journey Optimizer (AJO) para ofrecer ofertas permite a las empresas personalizar las experiencias de los clientes en función de las condiciones ambientales en tiempo real. El tiempo es una poderosa señal contextual. Las necesidades y el comportamiento de la gente cambian dependiendo del clima. Mediante los datos meteorológicos:

Ofrezca ofertas relevantes que se alineen con el estado de ánimo y el entorno del cliente

En un día caluroso, mostrar una oferta de bebidas frías o unidades de aire acondicionado. En un día lluvioso, promociona chaquetas o paraguas

Ejemplo de una oferta basada en el tiempo


![ofertas meteorológicas](assets/offers-use-case.png)



## Requisitos previos para este tutorial

* Acceso a Experience Platform.

* Comprensión básica de las etiquetas de Adobe Experience Platform.

* Comprensión básica de los conceptos de Experience Platform (perfiles, audiencias, conjuntos de datos).

* Familiaridad con Journey Optimizer.

* Conocimientos básicos de JavaScript (leer y escribir funciones simples).

* Capacidad para utilizar las herramientas de desarrollo del explorador (pestañas Consola y Red).
