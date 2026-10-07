---
title: Déclencheur del Recorrido de Adobe Journey Optimizer mediante Adobe Web SDK
description: Obtenga información sobre cómo iniciar un recorrido de Adobe Journey Optimizer desde eventos del sitio como inicios de sesión de usuarios aprovechando el SDK web de AEP configurado mediante etiquetas de Adobe Experience Platform
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-09-24T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-19287
exl-id: c6d4f720-3780-4012-a2bd-8eae23599144
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
source-wordcount: '290'
ht-degree: 10%
---
# Déclencheur del Recorrido de Adobe Journey Optimizer mediante Adobe Web SDK

En esta extensión del tutorial de vinculación de identidad, se activa el recorrido de Adobe Journey Optimizer que envía un correo electrónico al usuario que ha iniciado sesión utilizando su perfil vinculado. **Este artículo supone que está familiarizado con el canal de correo electrónico y la creación de contenido para el canal de correo electrónico.**

## Crear configuración de canal de correo electrónico

* Iniciar sesión en _&#x200B;**Journey Optimizer**&#x200B;_
* Vaya a _&#x200B;**Administración -> Canales -> Crear configuración de canal**&#x200B;_
* Seleccione **Correo electrónico** de la lista de canales. Proporcione un nombre y una descripción significativos.
* Rellene la configuración de correo electrónico.
* Proporcione los detalles de ejecución como se muestra a continuación. El correo electrónico se envía a la dirección de correo electrónico del perfil almacenada en el campo
* ![canal de correo electrónico](assets/email-channel-execution.png)
* Activar la configuración del canal de correo electrónico

## Crear evento

* Iniciar sesión en _&#x200B;**Journey Optimizer**&#x200B;_
* Vaya a _&#x200B;**Administración -> Configuraciones**&#x200B;_
* Haga clic en el botón Administrar de la tarjeta Eventos y haga clic en Crear evento. Especifique los valores como se muestra a continuación
* ![evento de recorrido](assets/journey-event1.png)

* Compruebe si eventType del evento es igual a LoginEvent. El tipo `LoginEvent` se ha definido en la etiqueta Adobe Experience Platform.
* Guarde el evento

## Crear Recorrido

* Iniciar sesión en _&#x200B;**Journey Optimizer**&#x200B;_
* Vaya a _&#x200B;**Administración de Recorrido -> Recorridos -> Crear Recorrido**&#x200B;_
* Arrastre y suelte el evento _&#x200B;**UserLoggedIn**&#x200B;_ en el lienzo
* Arrastre y suelte Correo electrónico desde el menú de acciones. Configure la acción de correo electrónico para utilizar la configuración de canal de correo electrónico creada anteriormente.
* Publique el recorrido.

## Cómo se activa el recorrido

El recorrido se activa cuando la carga útil de evento enviada a través de Web SDK coincide con la configurada en la recorrido. En este ejemplo, el evento es `UserLoggedIn` y el tipo de evento es `LoginEvent`.

* Verifíquelo consultando el informe de recorrido
* ![informe-recorrido](assets/journey-triggered-report.png)
