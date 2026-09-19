---
title: Prueba de la solución
description: Crear recorrido para enviar correo electrónico al enviar el formulario
feature: Journeys
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-12-25
jira: KT-20014
exl-id: 9b4a3e0c-d153-4a6b-a7de-b926bd669f6a
source-git-commit: d4cc60f4448caec92f704026783e2bbe029427f5
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 0%
---
# Prueba de la solución


Prueba de la solución
>[!VIDEO](https://video.tv.adobe.com/v/3478549?captions=spa)

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
