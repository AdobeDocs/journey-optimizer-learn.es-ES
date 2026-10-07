---
title: Envío de CRMID a Adobe Experience Platform
description: Cree Etiquetas de Adobe Experience Platform para enviar el CRMID recibido del explorador a Adobe Experience Platform
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: 894ad6b7-c4b4-465e-8535-3fdcd77e00eb
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: ef9a83ca-eefa-47cf-aa34-f1a34715583a
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 9%
---
# Envío de CRMID a Adobe Experience Platform

Las etiquetas de Adobe Experience Platform se utilizan para enviar el CRMID a Adobe Experience Platform (AEP), ya que ofrece un mecanismo flexible basado en eventos para transmitir datos de identidad directamente desde el explorador. El envío de CRMID después del inicio de sesión del usuario permite a AEP vincular el ECID anónimo con el perfil de CRM conocido, lo que permite vincular con precisión la identidad. Este vínculo forma la base para crear perfiles unificados de clientes, calificar audiencias y ofrecer experiencias personalizadas en tiempo real en Adobe Journey Optimizer (AJO).

Se crea una propiedad de etiquetas de Experience Platform llamada _&#x200B;**FinWise**&#x200B;_. Se han añadido las siguientes extensiones a la propiedad Etiquetas

![etiquetas-extensiones](assets/tags-extensions.png)

Configure la extensión AEP Web SDK mediante el flujo de datos de Financial Advisors creado en el paso anterior.
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

Cree una regla denominada LoginEvent con los eventos y las acciones siguientes

Evento
![evento](assets/data-pushed-event1.png)

Acción de actualizar variable
![variable-actualización](assets/update-variable1.png)
Acción Enviar evento
![send-event](assets/send-event1.png)

## Guardar y crear

Guarde los cambios, cree y cree la biblioteca.
