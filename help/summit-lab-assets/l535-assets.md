---
title: Hoja de características clave L535
description: Esta página contiene texto y vínculos que se están utilizando en el laboratorio L535 Summit.
feature: In App, SMS, Push, Email
doc-type: article
role: User
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
hidefromtoc: true
exl-id: 1c3f4341-1293-463d-bee0-57440fcff23a
source-git-commit: 4ced5e5989b721940b602a06b638485c8db1577f
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 22%

---

# Summit Lab L535 - Hoja de referencia

Esta página contiene texto y vínculos que se están utilizando en el laboratorio L535 Summit. Permite copiar y pegar el contenido en los mensajes de Journey Optimizer.

## Vínculos

* [Sitio web de SecurFinancial](https://dsn.adobe.com/web/hausmann-FTTN?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImFub255bW91cyIsImVtYWlsIjoiYW5vbnltb3VzQGFkb2JlLmNvbSIsIm5hbWUiOiJBbm9ueW1vdXMiLCJpc1N1cGVyVXNlciI6ZmFsc2UsImlzc3VlciI6ImhhdXNtYW5uIiwicHJvamVjdHMiOnsiaGF1c21hbm4tRlRUTiI6InZpZXcifSwiaWF0IjoxNzQwNzU2NTYxLCJleHAiOjE3NDMzNDg1NjF9.ryOTsqDH9B33436RlIo4AHFxx8aGjNEMqv9FAxLZb9U){target="_blank"}
* [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:ajo-summit-lab/journey-optimizer/journeys){target="_blank"}
* [Libro L535](/help/summit-lab-assets/assets/summit_lab_manual_L535-final-v3.pdf){target="_blank"}
* [Descargar la aplicación](https://demo-system-next.s3.amazonaws.com/dxdemo/summit/index.html){target="_blank"}

## Copiar y pegar para ejercicios

### Ejercicio 2.1: inicio de sesión en Journey Optimizer

Inicie sesión con los siguientes detalles:

Correo electrónico:    L535+*su número de asiento*@adobeeventlab.com

Contraseña:       Adobe4Summit


### Ejercicio 2.3: redactar el mensaje de correo electrónico

#### Indicación

```
Generate a welcome email for new SecurFinancial customers who just opened a new checking account. 
Add a call to action to install the SecurFinancial mobile app.
```

### Ejercicio 3.1: Aplicar contenido dinámico al mensaje SMS

#### Código

```
{%#if select _Push_details1 from profile.pushNotificationDetails where
_Push_details1.token.isNotNull()%}
Welcome to your new SecurFinancial checking account! Discover the
SecurFinancial mobile app, designed for effortless banking. Manage accounts,
transfer funds, and monitor transactions securely, anytime, anywhere. Open the
app
{%else%}
Welcome to your new SecurFinancial checking account! Discover the
SecurFinancial mobile app, designed for effortless banking. Manage accounts,
transfer funds, and monitor transactions securely, anytime, anywhere. Click here
to install the app: https://demo-systemnext.
s3.amazonaws.com/dxdemo/summit/index.html
{%/if%} 
```

### Ejercicio 4.2: Configurar los tratamientos

#### Título

```
Welcome to SecurFinancial
```

#### Texto independiente

```
Did you know you can find an ATM near in the SecurFinancial app? Try it now!
```

#### URL

```
dxdemo://atm
```

### Ejercicio 6: Tarjetas de contenido

#### Título

```
Welcome to SecurFinancial!
```

#### Cuerpo

```
Thank you for downloading the app. You can find ATMs, track your spending and more. All within the app.
```

#### URL de medios

```
https://demo-system-next.s3.amazonaws.com/assets/securfinancial/home-loan.jpg
```

#### Título de botón

```
Find ATMs
```

#### URL de destino

```
dxdemo://atm
```

## Imágenes

![Logotipo de SecureFinancial](/help/summit-lab-assets/assets/SecureFinancial-logo.png)


![Teléfono móvil](/help/summit-lab-assets/assets/online-banking-app-01.png)


