---
title: Creación de audiencias en Adobe Journey Optimizer
description: Aprenda a definir y crear audiencias segmentadas en AJO para potenciar los recorridos personalizados del cliente y la toma de decisiones en tiempo real
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00.000Z
jira: KT-17923
exl-id: d90f1868-0514-49b2-832d-82460883b6e4
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
source-wordcount: '155'
ht-degree: 0%
---
# Creación de audiencias en Adobe Journey Optimizer


Las audiencias en Adobe Experience Platform son grupos de usuarios creados en función de sus acciones, preferencias o información de perfil para ofrecer experiencias personalizadas.

* Iniciar sesión en Journey Optimizer
* Vaya a Cliente -> Audiencias -> Crear audiencia
* Crear audiencias mediante el método de generación de reglas

  ![público](assets/rule-based-audience.png)

* Crear las tres audiencias siguientes

  * Clientes interesados en las acciones

  * Clientes interesados en bonos

  * Clientes interesados en el CD


* Asegúrese de que el método de evaluación de cada audiencia esté establecido en _&#x200B;**Edge**&#x200B;_ para la calificación en tiempo real.
  ![audiencia de Edge](assets/audience-edge.png)

* Utilice el campo PreferredFinancialInstrument para segmentar a los usuarios según su interés de inversión seleccionado, como acciones, bonos o CD

![evento](assets/event-attribute.png)

![PreferredFinancialInstrument](assets/stock-customers.png)




>[!NOTE]
>
>&#x200B;>Si el campo PreferredFinancialInstrument no está visible en la pestaña Eventos, haga clic en el icono de configuración y active Mostrar el esquema XDM completo.



![toggle-full-xdm-schema](assets/show-custom-fields.png)
