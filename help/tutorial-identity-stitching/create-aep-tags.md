---
title: Envío de CRMID a Adobe Experience Platform
description: Cree Etiquetas de Adobe Experience Platform para enviar el CRMID recibido del explorador a Adobe Experience Platform
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
jira: KT-18089
source-git-commit: 68bd0a65e7d7f2d57f9620e76555485a1a79b4ae
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 9%

---

# Envío de CRMID a Adobe Experience Platform

Adobe Launch (Etiquetas) se utiliza para enviar el CRMID a Adobe Experience Platform (AEP) porque ofrece un mecanismo flexible basado en eventos para transmitir datos de identidad directamente desde el explorador. El envío de CRMID después del inicio de sesión del usuario permite a AEP vincular el ECID anónimo con el perfil de CRM conocido, lo que permite vincular con precisión la identidad. Este vínculo forma la base para crear perfiles unificados de clientes, calificar audiencias y ofrecer experiencias personalizadas en tiempo real en Adobe Journey Optimizer (AJO).

Se crea una propiedad de etiquetas de AEP llamada FinWise. Se han añadido las siguientes extensiones a la propiedad Etiquetas

![etiquetas-extensiones](assets/tags-extensions.png)

Configure la extensión AEP Web SDK mediante la secuencia de datos de Financial Advisors creada en el tutorial anterior.
El servicio de Experience Cloud ID es una extensión opcional añadida a la propiedad de etiquetas con fines de depuración.

## Elementos de datos de etiquetas

Cree los siguientes elementos de datos

| Elemento de datos | Extensión | Tipo de elemento de datos | Configuración personalizada |
|--------------|-----------------------------------|---------------------------|----------------------------------------|
| crmid | Capa de datos del cliente de Adobe | Estado calculado de la capa de datos | user.crmid |
| ECID | Servicio de Experience Cloud ID | ECID |                                        |
| identidad | SDK web de Adobe Experience Platform | Mapa de identidad | ![Imagen](assets/identity-settings.png) |
| XDMVariable | SDK web de Adobe Experience Platform | Variable | ![Imagen](assets/xdmvariable.png) |

## Crear regla

Cree una regla denominada userLogin con los eventos y las acciones siguientes

Evento
![evento](assets/data-pushed-event.png)

Acción de actualizar variable
![variable de actualización](assets/update-variable.png)
Acción Enviar evento
![send-event](assets/send-event.png)

## Guardar y crear

Guarde los cambios, cree y cree la biblioteca.

