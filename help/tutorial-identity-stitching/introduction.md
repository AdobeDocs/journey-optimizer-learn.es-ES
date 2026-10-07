---
title: Configuración de identidad en AEP
description: Establezca la vinculación de identidad entre un usuario conocido (CRMID) y un visitante web anónimo (ECID), lo que permite perfiles unificados para la personalización en tiempo real y tomas de decisiones sobre ofertas en Adobe Journey Optimizer (AJO).
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00.000Z
jira: KT-18089
exl-id: d6a1201a-3779-4718-8ea8-b88f925f53b6
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: ef9a83ca-eefa-47cf-aa34-f1a34715583a
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 11%
---
# Vinculación de identidad en AEP

En las experiencias modernas de los clientes, es fundamental unificar las identidades de los usuarios en todos los dispositivos y canales. Este caso de uso muestra cómo implementar la vinculación de identidad en Adobe Experience Platform (AEP) vinculando un CRM ID conocido (capturado durante el inicio de sesión del usuario) con el Experience Cloud ID anónimo (ECID) generado por Adobe Web SDK. Al unir estas identidades en tiempo real, AEP puede crear un perfil de cliente más completo que abarque tanto el comportamiento anónimo como los datos autenticados. Esto permite una segmentación de audiencia, personalización y toma de decisiones más precisas dentro de herramientas como Adobe Journey Optimizer (AJO).

## Aptitudes necesarias para el tutorial de vinculación de identidad

Para sacar el máximo partido a este tutorial, se recomienda estar familiarizado con lo siguiente:

- **Conceptos principales de Adobe Experience Platform (AEP)**\
  Comprensión de esquemas, conjuntos de datos, identidades, políticas de combinación y perfiles en tiempo real.

- **Modelado de esquema e identidad**\
  Capacidad para configurar campos de identidad en esquemas basados en perfiles y eventos.

- **Adobe Launch (Etiquetas) y Web SDK (Alloy.js)**\
  Experiencia en la configuración de elementos de datos y reglas para enviar datos a AEP mediante Web SDK.

- **Conceptos básicos de JavaScript**\
  Es cómodo trabajar con funciones para capturar los datos introducidos por el usuario, los eventos de déclencheur y las llamadas de API de depuración.

- **Herramientas de depuración de AEP**\
  Capacidad para utilizar AEP Debugger y el visualizador de gráficos de identidad para validar la vinculación de identidad.

- **Ingesta de datos en AEP**\
  Familiaridad con la carga de datos de ejemplo en conjuntos de datos y garantía de calidad de los datos.


