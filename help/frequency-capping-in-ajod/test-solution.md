---
title: Prueba de la solución
description: Cree una página web sencilla para capturar eventos de impresión y clics en las ofertas.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-07-18T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18526
exl-id: 6b6c66d3-218d-4f5b-adb0-a2eca05989ab
source-git-commit: bef6d831c639d40514552dae3ff20132626a4a09
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 1%

---

# Prueba de la solución

## Implementar los recursos de muestra

Si no tiene Node.js instalado, descargue e [instálelo desde aquí](https://nodejs.org/)

Compruebe la instalación ejecutando:

`node -v`

`npm -v`

## Configurar la carpeta del proyecto

Cree un nuevo directorio para la aplicación de ejemplo con los siguientes comandos:

`mkdir frequency-capping `

`cd frequency-capping `

## Inicializar el proyecto

`npm init -y`

## Instalación de los marcos necesarios

`npm install express`

## Copiar archivos de recursos

* Descomprima y coloque el contenido de [server.zip](assets/server.zip) en la carpeta `frequency-capping`.
* Extraiga el contenido de [public.zip](assets/public.zip)en la carpeta &#39;frequency-capping&#39;

## Actualizar la URL de superficie en el archivo javascript

Abra `frequency-capping.js` ubicado en `public\scripts` y actualice la propiedad de superficies para que coincida con la configuración de canal utilizada en la campaña

## Servidor js del nodo de inicio

Vaya a la carpeta `c:\frequency-capping`. Ejecute el comando `node server.js` para iniciar el servidor node js en el puerto 3000


## Actualizar la propiedad de etiquetas de Adobe Experience Platform

Abra el archivo `frequency-capping.html` ubicado en la carpeta `public` en el editor de texto y reemplace la etiqueta script por la etiqueta script de su propiedad Adobe Experience Platform Tag creada en el paso anterior de este tutorial. Asegúrese de guardar el archivo

```
<script src="https://assets.adobedtm.com/AEM_TAGS/launch-ENabcd1234.min.js" async></script>
```

## Interacción con las ofertas

* Abre la [página web](http://localhost:3000) en tu navegador favorito.
* Interacción con la oferta
* Actualizar la página
* Según las reglas de restricción de frecuencia, debería ver una oferta nueva

## Ver el informe

* Inicie sesión en Journey Optimizer
* Vaya a Administración de Recorrido ->Campañas
* Haga clic en la campaña y luego seleccione el informe correspondiente en el menú del informe.
