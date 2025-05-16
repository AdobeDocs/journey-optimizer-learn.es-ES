---
title: Vinculación de identidad en AEP
description: Establezca la vinculación de identidad entre un usuario conocido (CRMID) y un visitante web anónimo (ECID), lo que permite perfiles unificados para la personalización en tiempo real y Offer Decisioning en Adobe Journey Optimizer (AJO).
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
jira: KT-18089
source-git-commit: 502cdc41b666959141ff4dfc63608cc463009811
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 0%

---


# Descripción del caso de uso

En las experiencias modernas de los clientes, es fundamental unificar las identidades de los usuarios en todos los dispositivos y canales. Este caso de uso muestra cómo implementar la vinculación de identidad en Adobe Experience Platform (AEP) vinculando un CRM ID conocido (capturado durante el inicio de sesión del usuario) con el Experience Cloud ID anónimo (ECID) generado por Adobe Web SDK. Al unir estas identidades en tiempo real, AEP puede crear un perfil de cliente más completo que abarque tanto el comportamiento anónimo como los datos autenticados. Esto permite una segmentación de audiencia, personalización y toma de decisiones más precisas dentro de herramientas como Adobe Journey Optimizer (AJO).

