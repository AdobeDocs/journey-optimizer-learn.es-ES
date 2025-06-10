---
title: Personalización de ofertas con datos meteorológicos en tiempo real en Adobe Journey Optimizer mediante Web SDK
description: Este tutorial muestra cómo ofrecer ofertas dinámicas según el tiempo en Adobe Journey Optimizer utilizando datos contextuales en tiempo real y la API de Personalization de Adobe Web SDK. Aprenderá a pasar atributos meteorológicos (como temperatura y condiciones) de su sitio web a Adobe Experience Platform, asignarlos a su esquema de evento y utilizarlos en reglas de decisión y fórmulas de clasificación para personalizar ofertas en el momento de cargar la página. Ideal para especialistas en marketing y desarrolladores que buscan mejorar las experiencias digitales con un contexto ambiental en tiempo real.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
jira: KT-18258
source-git-commit: c04a15418e31dc82597b7759386907013728bb0d
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---

# Descripción del caso de uso

El uso de datos relacionados con el tiempo en Adobe Journey Optimizer (AJO) para ofrecer ofertas permite a las empresas personalizar las experiencias de los clientes en función de las condiciones ambientales en tiempo real. El tiempo es una poderosa señal contextual. Las necesidades y el comportamiento de la gente cambian dependiendo del clima. Mediante los datos meteorológicos:

Ofrezca ofertas relevantes que se alineen con el estado de ánimo y el entorno del cliente

En un día caluroso, mostrar una oferta de bebidas frías o unidades de aire acondicionado. En un día lluvioso, promociona chaquetas o paraguas

Ejemplo de una oferta basada en el tiempo


![ofertas meteorológicas](assets/offers-use-case.png)



## Requisitos previos para este tutorial

* Acceso a Experience Platform

* Comprensión básica de las etiquetas de Adobe Experience Platform

* Comprensión básica de los conceptos de Experience Platform (perfiles, audiencias, conjuntos de datos)

* Familiaridad con Journey Optimizer

* Conocimientos básicos de JavaScript (leer y escribir funciones sencillas)

* Capacidad para utilizar las herramientas de desarrollo del explorador (pestañas Consola y Red)
