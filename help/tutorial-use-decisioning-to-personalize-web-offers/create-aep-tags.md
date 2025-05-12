---
title: Creación de etiquetas de Adobe Experience Platform
description: Creación de audiencias de AJO basadas en las preferencias de inversión del usuario (acciones, bonos, CD)
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17923
exl-id: 6823ce13-bc77-4e2b-89e0-606e403c15f2
source-git-commit: 90f691b1cebb202ead66aafeb2e79087a8ae49ef
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%

---

# Creación de etiquetas de Adobe Experience Platform

Las etiquetas de Experience Platform se configuran en la página web para cargar Adobe Experience Platform Web SDK, lo que permite realizar la llamada de la API sendEvent para almacenar en déclencheur las experiencias personalizadas. Esta configuración garantiza que las bibliotecas del lado del cliente necesarias se inicialicen correctamente, lo que permite la interacción en tiempo real con Adobe Journey Optimizer para la entrega de ofertas.

1. Inicie sesión en Recopilación de datos.
1. Haga clic en **[!UICONTROL Etiquetas]** > **[!UICONTROL Nueva propiedad]**.
1. Cree una etiqueta de Adobe Experience Platform llamada Servicio ECID.
1. Añada las siguientes extensiones a la etiqueta:

   ![etiquetas-extensiones](assets/ecid-tag.png)

1. Configure Adobe Experience Platform Web SDK para utilizar el entorno correcto y el flujo de datos de Financial Advisors creado en el tutorial anterior

   ![web-sdk-configuration](assets/web-sdk-configuration.png)

No se necesita ninguna configuración adicional para la capa de datos del cliente de Adobe y las extensiones principales

## Creación del elemento de datos

El elemento de datos ECID en las etiquetas de Experience Platform se crea únicamente con fines de depuración y prueba. El elemento de datos permite a los desarrolladores ver el Experience Cloud ID asignado a la sesión del explorador de un usuario, lo cual puede ayudar a validar la vinculación de identidad y garantizar que las llamadas de `sendEvent` estén asociadas al perfil correcto. Este elemento no es necesario para que la personalización funcione, pero resulta útil durante la implementación y el control de calidad

![ecid](assets/ecid-data-element.png)


## Incluir etiquetas de AEP en la página de HTML

Cree y publique las etiquetas de Adobe Experience Platform.

Cuando se publica una propiedad Etiquetas de AEP, Adobe le proporciona una etiqueta de script que debe colocar en su HTML ``` <head>``` o en la parte inferior de las etiquetas ``` <body>```.

1. Vaya a la propiedad Etiquetas (servicio ECID).

1. Haga clic en Entornos y, a continuación, haga clic en el icono de instalación del entorno que desee (por ejemplo, Desarrollo, Ensayo, Producción).

1. Observe el código incrustado.

   Este código debe colocarse justo antes de la etiqueta de cierre ```</body>``` en la página de HTML.
