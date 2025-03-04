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
source-git-commit: 51ab40981a42b0df56d3994f1155eb4ae7575b17
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 21%

---

# Summit Lab L535 - Hoja de referencia

Esta página contiene texto y vínculos que se están utilizando en el laboratorio L535 Summit. Permite copiar y pegar el contenido en los mensajes de Journey Optimizer.

## Vínculos

* [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:ajo-summit-lab/journey-optimizer/journeys)
* [Sitio web de SecurFinancial](https://dsn.adobe.com/web/hausmann-FTTN?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImFub255bW91cyIsImVtYWlsIjoiYW5vbnltb3VzQGFkb2JlLmNvbSIsIm5hbWUiOiJBbm9ueW1vdXMiLCJpc1N1cGVyVXNlciI6ZmFsc2UsImlzc3VlciI6ImhhdXNtYW5uIiwicHJvamVjdHMiOnsiaGF1c21hbm4tRlRUTiI6InZpZXcifSwiaWF0IjoxNzQwNzU2NTYxLCJleHAiOjE3NDMzNDg1NjF9.ryOTsqDH9B33436RlIo4AHFxx8aGjNEMqv9FAxLZb9U)
* [Descargar la aplicación](https://demo-system-next.s3.amazonaws.com/dxdemo/summit/index.html)

## Ejercicios

### Ejercicio 2.3

**Mensaje de correo electrónico del paso 12**:

Generar un correo electrónico de bienvenida para el nuevo SecurFinancial
clientes que acaban de abrir una nueva cuenta de ahorros. Añadir un
Llamada a acción para instalar la aplicación móvil SecurFinancial.

### Ejercicio 3.1

**Paso 7**

```javascript
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


![Logotipo de SecureFinancial](/help/summit-lab-assets/assets/SecureFinancial-logo.png)

![Teléfono móvil](/help/summit-lab-assets/assets/online-banking-app-01.png)


