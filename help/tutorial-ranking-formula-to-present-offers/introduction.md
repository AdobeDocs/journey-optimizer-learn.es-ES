---
title: Personalice ofertas con fórmulas de clasificación basadas en el código postal y los ingresos
description: Utilice las fórmulas de clasificación de Adobe Journey Optimizer para ofrecer dinámicamente las ofertas financieras más relevantes (adaptadas al código postal y al nivel de ingresos de cada usuario) y lograr una mayor participación y una personalización más inteligente.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-27T00:00:00Z
jira: KT-18188
exl-id: 11685f7c-8048-4318-9c28-71bd7da8f7ff
source-git-commit: 85d3def3afb1d073b133df40e4cbf32d00a3a5c9
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 0%

---

# Personalice ofertas con fórmulas de clasificación basadas en el código postal del usuario y los ingresos

Este caso de uso muestra cómo ofrecer ofertas financieras personalizadas mediante el uso de atributos de usuario como código postal e ingresos anuales dentro de Adobe Journey Optimizer. Mediante fórmulas de clasificación, las ofertas se clasifican y priorizan de forma inteligente en función de las promociones específicas de la ubicación y la idoneidad basada en los ingresos. Por ejemplo, los CD de alto rendimiento pueden promocionarse a usuarios con códigos postales acomodados, mientras que a inversores emergentes se les muestran opciones de inversión diversificadas. Las fórmulas de clasificación garantizan que cada usuario reciba ofertas relevantes y apropiadas desde el punto de vista financiero. Los criterios de clasificación se definen mediante atributos de perfil, señales contextuales y modelos de IA opcionales para mejorar aún más la precisión de la decisión. Las ofertas se entregan en tiempo real a través de canales web o de correo electrónico, lo que aumenta la participación y la conversión. Este enfoque combina la lógica empresarial con la personalización basada en datos para aumentar la experiencia del usuario y el impacto del marketing.

## Requisitos previos

Este tutorial se basa en conceptos clave de Adobe Journey Optimizer y Adobe Experience Platform. Antes de continuar, asegúrese de que se cumplen los siguientes requisitos previos:

* [Se ha completado el tutorial de vinculación de identidad](https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorial-on-identity-stitching-in-aep/introduction), con los ID de CRM asociados correctamente a los ECID en Adobe Experience Platform.

* Familiarizado con la creación de elementos de oferta en AJO, incluida la definición de contenido, la configuración de metadatos y las reglas de idoneidad.

* Familiarizado con la configuración de canales (como la web o el correo electrónico) para la entrega de ofertas.

* Familiarizado con la creación y activación de campañas en AJO.

* Familiarizarse con el uso de Adobe Launch (Etiquetas) para implementar Web SDK y enviar eventos que contengan datos de identidad y perfil.

Este tutorial cubre los siguientes pasos de Offer Decisioning:

* Creación de un método de clasificación mediante atributos de perfil como código postal e ingresos anuales.

* Definición de una estrategia de selección para agrupar y priorizar ofertas.

* Creación de una política de decisión para entregar la oferta más relevante a cada individuo.
