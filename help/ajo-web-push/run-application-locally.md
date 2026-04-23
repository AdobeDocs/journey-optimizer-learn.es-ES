---
title: Ejecutar la aplicación localmente
description: Configuración de la aplicación de ejemplo localmente para explorar el flujo de notificaciones push web mediante AJO.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
exl-id: 2635641b-5ae2-4303-bac7-02c3702950f0
source-git-commit: c339fe796af1e691cd3b1c98cd6ba8a8772551e4
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 0%

---

# Ejecutar la aplicación localmente

Esta página le guía a través de la configuración de la aplicación de ejemplo localmente para que pueda probar y explorar el flujo de notificaciones push web mediante Adobe Journey Optimizer. Clonará el repositorio, configurará las variables de entorno y ejecutará la aplicación en el sistema local.


Siga estos pasos para ejecutar la aplicación de ejemplo en el sistema local.

## &#x200B;1. Instale Node.js

Asegúrese de que tiene **Node.js (versión 16 o superior)** instalado en el sistema.

Puede [descargarlo aquí:](https://nodejs.org/)

Compruebe la instalación

```node -v```

```npm -v```


## &#x200B;2. Clonar el repositorio

```git clone https://github.com/gbedekar489/ajo-web-push.git```

```cd ajo-web-push```

## &#x200B;3. Instalar dependencias

```npm install```

## &#x200B;4. Configurar variables de entorno

Cree un archivo .env en el directorio raíz y agregue lo siguiente:

```
DATASTREAM_ID=your_datastream_id
ORG_ID=your_org_id
VAPID_PUBLIC_KEY=your_vapid_public_key
APP_ID=your_app_id
DATASET_ID=your_event_dataset_id
PORT=3000
```


Cuando se ejecutan localmente, estos valores se leen desde el archivo .env. En la producción (por ejemplo, Procesar), se configuran como variables de entorno.
