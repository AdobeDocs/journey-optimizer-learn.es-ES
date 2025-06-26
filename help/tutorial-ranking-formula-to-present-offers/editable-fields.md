---
title: Uso de campos de formulario editables en experiencias basadas en código de AJO
description: Aprenda a crear bloques de contenido editable mediante campos de formulario en línea en las plantillas de experiencia basadas en código de Adobe Journey Optimizer para ofrecer a los especialistas en marketing contenido de campaña dinámico y reutilizable.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-22T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18416
exl-id: 0ba695d6-becb-440d-b0d0-de5b51b42562
source-git-commit: 65d91d4fb0e978e62e5d95bf40355dcb8d27efb9
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 1%

---

# Uso de campos de formulario editables en experiencias basadas en código de AJO

En muchos recorridos de marketing, especialmente en las industrias reguladas, es esencial incluir un descargo de responsabilidad legal que puede variar según la campaña, la ubicación geográfica o el producto. Mediante el uso de un [campo editable](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/channels/code-based-experience-channel/form-fields-in-code-based-experiences) directamente en el editor de Personalization de AJO, los especialistas en marketing y los equipos legales pueden mantener un control total sobre el texto de exención de responsabilidad sin involucrar a los desarrolladores ni modificar la lógica de decisión.

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
