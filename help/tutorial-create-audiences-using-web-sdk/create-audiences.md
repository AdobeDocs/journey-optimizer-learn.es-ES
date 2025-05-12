---
title: Creación de audiencias en Adobe Journey Optimizer
description: Aprenda a definir y crear audiencias segmentadas en AJO para potenciar los recorridos personalizados del cliente y la toma de decisiones en tiempo real
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
source-git-commit: ba83be3caf214d2daaa8c99556d246686ff3f0cb
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Creación de audiencias en Adobe Journey Optimizer


Las audiencias en Adobe Experience Platform son grupos de usuarios creados en función de sus acciones, preferencias o información de perfil para ofrecer experiencias personalizadas.

* Iniciar sesión en Journey Optimizer
* Vaya a Cliente -> Audiencias -> Crear audiencia
* Crear audiencias mediante el método de generación de reglas

  ![audiencia](assets/rule-based-audience.png)

* Crear las tres audiencias siguientes

   * Clientes interesados en las acciones

   * Clientes interesados en bonos

   * Clientes interesados en el CD


* Asegúrese de que el método de evaluación de cada audiencia esté establecido en _**Edge**_ para la calificación en tiempo real.
  ![audiencia de Edge](assets/audience-edge.png)

* Utilice el campo PreferredFinancialInstrument para segmentar a los usuarios según su interés de inversión seleccionado, como acciones, bonos o CD

![evento](assets/event-attribute.png)

![PreferredFinancialInstrument](assets/stock-customers.png)




>[!NOTE]
>
>>Si el campo PreferredFinancialInstrument no está visible en la pestaña Eventos, haga clic en el icono de configuración y active Mostrar el esquema XDM completo.



![toggle-full-xdm-schema](assets/show-custom-fields.png)


