---
title: Prueba de la solución
description: Crear recorrido para enviar correo electrónico al enviar el formulario
feature: Journeys
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-12-25T00:00:00.000Z
jira: KT-20014
exl-id: 9b4a3e0c-d153-4a6b-a7de-b926bd669f6a
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 0%
---
# Prueba de la solución


Prueba de la solución
>[!VIDEO](https://video.tv.adobe.com/v/3478546)

## Implementar los recursos de muestra

Si no tiene Node.js instalado, descargue e [instálelo desde aquí](https://nodejs.org/)

Compruebe la instalación ejecutando:

`node -v`

`npm -v`

## Configurar la carpeta del proyecto

Cree un nuevo directorio para la aplicación de ejemplo con los siguientes comandos:

`mkdir trigger-journey `

`cd trigger-journey`

## Inicializar el proyecto

`npm init -y`

## Instalación de los marcos necesarios

`npm install express dotenv axios cors`

## Copiar archivos de recursos

* Descomprima y coloque el contenido de [project-root.zip](assets/project-root.zip) en la carpeta `trigger-journey`.

* Cree una carpeta llamada `public` en la carpeta `trigger-journey`
* actualice el archivo `.env` con los valores apropiados. Estos valores están disponibles desde el comando cURL descargado al crear la conexión HTTP Source.
* Descomprima el contenido de [index.zip](assets/index.zip) en la carpeta `public`

## Ejecutar el servidor

Asegúrese de que está en el directorio `trigger-journey`.
Ejecutar el comando `node server.js`
Dirija su navegador a [página web](http://localhost:3000/)
Rellene y envíe el formulario. El recorrido se activa y se envía un correo electrónico al ID de correo electrónico introducido en el formulario.
