---
title: Creación de etiquetas de Adobe Experience Platform
description: Creación de audiencias de AJO basadas en las preferencias de inversión del usuario (acciones, bonos, CD)
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
exl-id: 04fad076-e897-4831-9147-768721858a80
source-git-commit: 40690024e5348dd3ac05f350e49a67a99d5e455e
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 0%

---

# Creación de etiquetas de Adobe Experience Platform

Las etiquetas de Adobe Experience Platform (anteriormente Adobe Launch) ayudan a administrar e implementar* tecnologías de marketing y análisis en su sitio web sin necesidad de cambiar el código del sitio.

En este [vídeo se describe el proceso de creación de Adobe Experience Tags](https://experienceleague.adobe.com/en/playlists/experience-platform-get-started-with-tags)

- Iniciar sesión en la recopilación de datos
- Haz clic en _&#x200B;**Etiquetas -> Nueva propiedad**&#x200B;_

- Cree una Adobe Experience Platform Tag llamada _&#x200B;**personalización según el tiempo**&#x200B;_.

- Añada las siguientes extensiones a la etiqueta
  ![etiquetas-extensiones](assets/tags-extensions1.png)
- Agregue un elemento de datos llamado &quot;ECID&quot; como se muestra a continuación. Este elemento de datos se utiliza más adelante en los informes
  ![ecid-data-element](assets/ecid-data-element.png)

- Asegúrese de configurar Adobe Experience Platform Web SDK para que utilice el entorno correcto y la **secuencia de datos relacionada con el tiempo** creada en el paso anterior.
  ![web-sdk-configuration](assets/tags-extensions.png)



## Creación e implementación de etiquetas de AEP


Cree una nueva biblioteca y añádale todos los recursos modificados, como se muestra en las capturas de pantalla siguientes.

**Agregar biblioteca**

![nueva-biblioteca](assets/tag-add-library.png)

**Crear una biblioteca**

En la pantalla Crear biblioteca, especifique el nombre de la biblioteca y el entorno.

Añadir todos los recursos modificados a esta biblioteca
![biblioteca de etiquetas](assets/tag-build-library.png)

A continuación, haga clic en el botón Guardar y crear en desarrollo para crear la biblioteca

## Incluir etiquetas de AEP en la página de HTML

Cuando publica una propiedad de etiquetas de AEP, Adobe le proporciona una etiqueta de script que debe colocar dentro de su HTML ``` <head>``` o en la parte inferior de las etiquetas ``` <body>```.

- Vaya a la propiedad Etiquetas (personalización según el tiempo).

- Haga clic en Entornos y en el icono de instalación del entorno que desee (por ejemplo, Desarrollo, Ensayo, Producción).

- Anote el código incrustado. Se necesita en una etapa posterior de este tutorial.
