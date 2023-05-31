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
source-git-commit: 4c2215615647da8db51914ea48f1af32936ccc57
workflow-type: ht
source-wordcount: '357'
ht-degree: 100%

---

# Summit Lab L731 - Hoja de ejercicios

Esta página tiene texto y enlaces que están siendo utilizados en L731 Summit Lab. Permite copiar y pegar el contenido en los mensajes de Journey Optimizer.

## Lección 1.1: Descargar e instalar la aplicación

Analizar el código QR para descargar la aplicación

>[!BEGINTABS]

>[!TAB iOS]

![Código QR para iOS](/help/assets/lab731-ios-qr-code.png)

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

Si utiliza el simulador de Android, utilice este vínculo: [https://ajolab.s3.amazonaws.com/ajolabapp-release.apk](https://ajolab.s3.amazonaws.com/ajolabapp-release.apk)

Como la aplicación no está registrada en la tienda Google Play, recibirá un mensaje de advertencia:

![Pantalla de advertencia de Android](/help/assets/lab731-install-android.png)

Haga clic en **Instalar de todas formas**

>[!ENDTABS]

## Lección 1.3: Iniciar sesión en Adobe Journey Optimizer

[Haga clic aquí para iniciar sesión en Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-2023-ajo-lab/journey-optimizer/home)

**Detalles de inicio de sesión:**

* **Nombre de usuario:** `L731+<your seat number>@summitlab.us` (ejemplo: L731+001@summitlab.us)
* **Contraseña:** Adobe2023!


## Ejercicio 2.1 Creación de una campaña en la aplicación

| Campo | Texto | Vínculos |
|----|----|----|
| Nombre de la campaña | `<your seat number> March Vegas Campaign` |  |
| Emparejador | reserva ahora |  |
| Opción URL de medios |  | https://mcfadyen.com/wp-content/uploads/2023/01/Adobe-Summit-2023-Banner.png |
| Título | ¡Está ocurriendo y en vivo! |  |
| Cuerpo | Adobe Summit vuelve a Las Vegas del 21 al 23 de marzo de 2023. Prepárese para ponentes motivadores, sesiones de perfeccionamiento de habilidades y nuevas conexiones. |  |
| Botón | Reserve ahora el hotel y ahórrese un 10 % | lab://booking?suite=presidential&amp;discount=10 |
| Botón: evento interactivo | CTA en la aplicación |  |
| Dirección URL base |  | iOS: lab:// <br>Android&amp;: https://lab |


## Lección 3: Creación de un recorrido omnicanal

**Etiqueta de recorrido:**
`<your seat number>` - Recorrido de bienvenida

>[!BEGINTABS]

>[!TAB Mensaje push]

**Etiqueta:**
Mensaje de bienvenida

**Título:**\
Bienvenido a Vegas Stay!

**Cuerpo:**\
Omita la línea y regístrese con la aplicación móvil

**Vínculo profundo:** iOS: lab://, Android&amp;: https://lab

**Medios:**

https://experienceleague.adobe.com/docs/journey-optimizer-learn/assets/vegas_online_check_in.jpg?lang=es


Esta es la imagen que utilizamos para la notificación push:

![Registro en línea](/help/assets/vegas_online_check_in.jpg)

>[!TAB Mensaje SMS]

**Etiqueta:**
Mensaje de bienvenida

**Mensaje:**
Bienvenido a Vegas Stay. Omita la línea y regístrese con la aplicación móvil: lab://checkin

>[!TAB Mensaje de correo electrónico]

**Etiqueta:**
Mensaje de confirmación

**Línea de asunto:**
`{{profile.person.name.firstName}},`, ya se ha registrado, ¡ahora consulte nuestras ofertas para su estancia!

>[!ENDTABS]
