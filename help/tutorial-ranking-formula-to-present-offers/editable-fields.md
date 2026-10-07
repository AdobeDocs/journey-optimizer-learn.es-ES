---
title: Uso de campos de formulario editables en experiencias basadas en código de AJO
description: Aprenda a crear bloques de contenido editable mediante campos de formulario en línea en las plantillas de experiencia basadas en código de Adobe Journey Optimizer para ofrecer a los especialistas en marketing contenido de campaña dinámico y reutilizable.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-22T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18416
exl-id: 0ba695d6-becb-440d-b0d0-de5b51b42562
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: a984631b-2bae-4860-9b15-69c41a799dcb
    internal-label: APIs and SDKs
subfeature_v2:
  - id: a7a194a0-75e2-4913-8a83-14714fbf68e6
    internal-label: Decisioning API
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 22%
---
# Uso de campos de formulario editables en experiencias basadas en código de AJO

En muchos recorridos de marketing, especialmente en las industrias reguladas, es esencial incluir un descargo de responsabilidad legal que puede variar según la campaña, la ubicación geográfica o el producto. Mediante el uso de un [campo editable](https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/channels/code-based-experience-channel/form-fields-in-code-based-experiences) directamente en el editor de Personalization de AJO, los especialistas en marketing y los equipos legales pueden mantener un control total sobre el texto de exención de responsabilidad sin involucrar a los desarrolladores ni modificar la lógica de decisión.

Esto permite actualizaciones rápidas y garantiza el cumplimiento de las normas en todas las campañas, al tiempo que aprovecha el contenido decidido como ofertas.

## Insertar campo editable en el editor de personalización

- Abra la campaña creada en el paso anterior.
- Haga clic en _**Modificar campaña**_
- Vaya a la pestaña _**Contenido**_
- Haga clic en _**Editar código**_ e inserte un campo editable llamado legalDisclaimer con un valor predeterminado utilizando la siguiente sintaxis en el editor de personalización

- `{{#inline "legalDisclaimer" name="Legal Disclaimer"}} Legal Disclaimer will go here {{/inline}}`

- Utilizar la variable `{{{legalDisclaimer}}}` en la plantilla como se muestra a continuación

- ![campos editables](assets/editable-fields.png)

- Los especialistas en marketing pueden editar fácilmente el campo Descargo de responsabilidad legal sin tener que abrir el editor de personalización.
- ![editable-field-marketer](assets/editable-field-marketer-view.png)



## Publicación de la campaña

Active la campaña para empezar a enviar ofertas personalizadas en tiempo real.
