---
title: Hoja de características clave L731
description: Esta página tiene texto y enlaces que están siendo utilizados en L731 Summit Lab.
feature: In App, SMS, Push, Email
doc-type: article
role: User
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
hidefromtoc: true
exl-id: ffc5e8c8-8729-4e7e-aa51-d74f91b0cf29
source-git-commit: c0b7fa47fac1ad16121d0f568de358c83de44a90
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 53%

---

# Summit Lab L731 - Hoja de Cheat

Esta página tiene texto y enlaces que están siendo utilizados en L731 Summit Lab. Permite copiar y pegar el contenido en los mensajes de Journey Optimizer.

## Ejercicio 1.1: descargar e instalar la aplicación

Escanee el código QR para descargar la aplicación

>[!BEGINTABS]

>[!TAB iOS]

![Código QR para iOS](/help/assets/lab731-ios-qr-code.png)

>[!TAB Android]

![Código QR para Android](/help/assets/lab731-android-qr-code.png)

>[!ENDTABS]

## Ejercicio 1.3: Iniciar sesión en Adobe Journey Optimizer

[Haga clic aquí para iniciar sesión en Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-2023-ajo-lab/journey-optimizer/home)

**Detalles de inicio de sesión:**

* **Nombre de usuario:** `L731+<your seat number>@summitlab.us` (ejemplo: L731+001@summitlab.us)
* **Contraseña:** ¡Adobe 2023!


## Ejercicio 2.1 Creación de una campaña en la aplicación

| Campo | Texto | Vínculos |
|----|----|----|
| Nombre de campaña | `<your seat number> March Vegas Campaign` |  |
| Coincidencia | conoce bien |  |
| Opción URL de medios |  | https://mcfadyen.com/wp-content/uploads/2023/01/Adobe-Summit-2023-Banner.png |
| Título | ¡Está sucediendo y en vivo! |  |
| Cuerpo | Adobe Summit vuelve a Las Vegas del 21 al 23 de marzo de 2023. Prepárese para ponentes motivadores, sesiones de perfeccionamiento de habilidades y nuevas conexiones. |  |
| Botón | Reserve ahora el hotel y ahórrese un 10 % | lab://booking?suite=presidential&amp;discount=10 |
| Botón: evento interactivo | CTA en la aplicación |  |
| Dirección URL base |  | iOS: lab:// <br>Android: https://lab |


## Lección 3: Creación de un recorrido omnicanal

>[!BEGINTABS]

>[!TAB Mensaje push]

**Título:**\
Bienvenido a Vegas Stay!

**Cuerpo:**\
Omita la línea y regístrese con la aplicación móvil

**Vínculo profundo:** lab://checkin

**Medios:**

https://experienceleague.adobe.com/docs/journey-optimizer-learn/assets/vegas_online_check_in.jpg?lang=en


Esta es la imagen que utilizamos para la notificación push:

![Registro en línea](/help/assets/vegas_online_check_in.jpg)

>[!TAB Mensaje SMS]

**Mensaje:**
Bienvenido a Vegas Stay. Omita la línea y regístrese con la aplicación móvil: lab://checkin

>[!TAB Mensaje de correo electrónico]

**Línea de asunto:**
{{profile.person.name.firstName}}, ya está registrado, ahora consulte nuestras ofertas para su estancia!

>[!ENDTABS]