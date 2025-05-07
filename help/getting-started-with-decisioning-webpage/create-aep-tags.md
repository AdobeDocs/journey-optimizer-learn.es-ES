---
title: Creación de etiquetas de Adobe Experience Platform
description: Creación de audiencias de AJO basadas en las preferencias de inversión del usuario (acciones, bonos, CD)
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17923
source-git-commit: 9695a4db0d0caa44a8c7d49e069320309ffc40a6
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 0%

---


# Crear Adobe Experience Platform

Adobe Launch se configura en la página web para cargar Adobe Experience Platform Web SDK, lo que permite la llamada de la API sendEvent para almacenar en déclencheur las experiencias personalizadas. Esta configuración garantiza que las bibliotecas del lado del cliente necesarias se inicialicen correctamente, lo que permite la interacción en tiempo real con Adobe Journey Optimizer para la entrega de ofertas.

* Iniciar sesión en la recopilación de datos
* Haga clic en Etiquetas -> Nueva propiedad
* Cree una etiqueta de Adobe Experience Platform llamada Servicio ECID.

* Añada las siguientes extensiones a la etiqueta
  ![etiquetas-extensiones](assets/ecid-tag.png)

* Asegúrese de configurar Adobe Experience Platform Web SDK para que utilice el entorno correcto y el flujo de datos de Financial Advisors creado en el tutorial anterior
  ![web-sdk-configuration](assets/web-sdk-configuration.png)

* No se necesita ninguna configuración adicional para las extensiones principales y de capa de datos del cliente de Adobe

## Crear elemento de datos

El elemento de datos ECID en Adobe Launch se crea únicamente con fines de depuración y prueba. Permite a los desarrolladores ver el Experience Cloud ID asignado a la sesión del explorador de un usuario, lo que puede ayudar a validar la vinculación de identidad y garantizar que las llamadas a sendEvent estén asociadas al perfil correcto. Este elemento no es necesario para que la personalización funcione, pero resulta útil durante la implementación y el control de calidad

![ecid](assets/ecid-data-element.png)


## Incluir etiquetas de AEP en la página de HTML

Creación y publicación de etiquetas de Adobe Experience Platform

Cuando se publica una propiedad Etiquetas de AEP, Adobe le proporciona una etiqueta de script que debe colocar en su HTML ``` <head>``` o en la parte inferior de las etiquetas ``` <body>```.

* Vaya a la propiedad Etiquetas (servicio ECID).

* Haga clic en Entornos y en el icono de instalación del entorno que desee (por ejemplo, Desarrollo, Ensayo, Producción).

* Anote el código incrustado. Este código debe colocarse justo antes de la etiqueta de cierre ```</body>``` en la página de HTML.

