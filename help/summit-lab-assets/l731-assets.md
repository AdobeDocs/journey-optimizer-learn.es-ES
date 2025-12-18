---
title: Hoja de ejercicios L731
description: Esta página tiene texto y enlaces que están siendo utilizados en L731 Summit Lab.
feature: In App, SMS, Push, Email
doc-type: article
role: User
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
hidefromtoc: true
exl-id: ffc5e8c8-8729-4e7e-aa51-d74f91b0cf29
source-git-commit: 55ba1a46c1473d94847e7fccc69ed2a33badb54c
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 98%

---

# Summit Lab L731 - Hoja de referencia

Esta página tiene texto y enlaces que están siendo utilizados en L731 Summit Lab. Permite copiar y pegar el contenido en los mensajes de Journey Optimizer.

## Lección 1.1: Descargar e instalar la aplicación

Analizar el código QR para descargar la aplicación

>[!BEGINTABS]

>[!TAB iOS]

![Código QR para iOS](/help/assets/lab731-ios-qr-code.png)

>[!IMPORTANT]
>
>Si se le pide el código de canje, cierre la aplicación TestFlight y escanee el código QR una vez más.
>
>Permita notificaciones.
>

Se le pedirá que instale Testflight, pasos del 1 al 4. Una vez que haya instalado Testflight, siga los pasos 5 al 8 para instalar la aplicación Vegas Stay:

<table>
<tr>
</tr>
<tr>
<td>
 <div>
      <p>
      <b>Paso 1 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-1.png"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>Paso 2 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-2.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>Paso 3 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-3.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>Paso 4 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-4.PNG"/>
      </a>
      </div>
  </td>
  </tr>
  <tr>
<td>
 <div>
      <p>
      <b>Paso 5 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-5.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <a>
      <b>Paso 6 </b>
      <p>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-6.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <a>
      <b>Paso 7 </b>
      <p>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-7.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <a>
      <b>Paso 8 </b>
      <p>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-8.PNG"/>
      </a>
      </div>
  </td>
  </tr>
</table>

>[!TAB Android]

![Código QR para Android](/help/assets/lab731-android-qr-code.png)

Como la aplicación no está registrada en la tienda Google Play, recibirá un mensaje de advertencia:

![Pantalla de advertencia de Android](/help/assets/lab731-install-android.png)

Haga clic en **Instalar de todas formas**

>[!ENDTABS]

## Ejercicio 1: Iniciar sesión en Adobe Journey Optimizer

[Haga clic aquí para iniciar sesión en Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-2023-ajo-lab/journey-optimizer/home){target="_blank"}

**Detalles de inicio de sesión**

* **Nombre de usuario:** `L731+<your seat number>@summitlab.us` (ejemplo: L731+001@summitlab.us)
* **Contraseña:** Adobe2023!


## Ejercicio 2: Creación de una campaña en la aplicación

| Sección | Campo | Texto | Vínculos |
|----|----|----|----|
| **Propiedades** | Nombre de la campaña | `<your seat number> Vegas Stay Campaign` |  |
| **Activadores** | Estado | reserva ahora |  |
| **Editar contenido:** medios | Opción URL de medios |  | https://i.ibb.co/NstLhjW/Firefly-Poster-with-heading-Adobe-Max-84773.jpg |
| **Editar contenido:** contenido | Título | Obtenga su descuento por anticipado. |  |
| **Editar contenido:** contenido | Cuerpo | Adobe Max vuelve a Las Vegas. Prepárese para ponentes motivadores, sesiones de perfeccionamiento de habilidades y nuevas conexiones. Reserve su suite ahora y obtenga un 10 % de descuento. |  |
| **Editar contenido:** botones | Botón | Consiga su 10 % de descuento. | lab://booking?suite=presidential&amp;discount=10 |
| **Editar contenido:** botones | Evento Interactivo | CTA en la aplicación |  |
| **Vista previa en el dispositivo** | URL base que se utilizará en la vista previa en el dispositivo |  | **iOS:** lab:// <br>**Android**: https://lab |

## Ejercicio 3: Creación de una notificación push

| Campo | Texto | Vínculos |
|----|----|----|
| Nombre de la campaña | **`<your seat number> Max Push Campaign`** |  |
| Título | ¡Eh! |  |
| Cuerpo | ¿Sabía que Adobe Max va a volver a Las Vegas? Reserve su habitación ahora y obtenga un 10 % de descuento. |  |
| Opción URL de medios |  | https://i.ibb.co/1M0BnZn/Firefly-Big-conference-big-stage-with-ADBE-text-on-screen-40178.jpg |
