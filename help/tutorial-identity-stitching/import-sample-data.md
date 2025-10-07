---
title: Importar datos CRM de muestra en el conjunto de datos de perfil de AEP
description: Importe registros de muestra (por ejemplo, con CRMID, correo electrónico, ingresos, código postal) para validar si AEP puede unir correctamente esos perfiles con visitantes web anónimos en función de identificadores compartidos como ECID.
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: 33c8c386-f417-45a8-83cf-7312d415b47a
source-git-commit: 83b23f54594b796ec528526a360c5c40164fb5cb
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 5%

---

# Importar datos CRM de muestra en el conjunto de datos de perfil de AEP

Para comenzar la vinculación de identidad, importe datos de perfil de CRM de muestra a un conjunto de datos vinculado a un esquema habilitado para perfiles en Adobe Experience Platform

## Crear un área de nombres personalizada

* Vaya a Cliente -> Identidades -> Crear área de nombres de identidad
* Seleccione ID individual entre dispositivos y proporcione el nombre para mostrar y el símbolo de identidad como se muestra en la captura de pantalla siguiente.
  ![espacio de nombres personalizado](assets/custom-namespace.png)

## Creación de un esquema habilitado para el perfil

Cree un esquema de perfil individual denominado **_FinWiseProfileSchema_**. Incluya campos como annualIncome, email, firstName, lastName y loyaltyStatus.
Agregue un campo de identidad **_crmid_** como se muestra. Marque el campo crmid como identidad y principal.
Agregue el grupo de campos _**Detalles de consentimientos y preferencias**_ al esquema. [Consentimientos y preferencias](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/field-groups/profile/consents) es un grupo de campos estándar para la clase de perfil individual de XDM que captura información de preferencias y consentimiento de un cliente individual. Las preferencias almacenadas aquí determinan las preferencias de comunicación a nivel de canal.


![perfil-esquema](assets/finwise-profile-schema.png)

## Preparar datos de ejemplo

Actualice las direcciones de correo electrónico ficticias a direcciones reales. Se utilizarán más adelante al enviar mensajes con Adobe Journey Optimizer. Establezca emailConsent en y para habilitar la entrega por correo electrónico para los perfiles.

|   | crmId | firstName | lastName | correo electrónico | loyaltyStatus | zipCode | annualIncome | emailConsent |
|---|--------|-----------|----------|-------------------------|---------------|---------|--------------|--------------|
|   | FIN001 | Alice | Wong | alice.wong@example.com | Oro | 92128 | 120000 | y |
|   | FIN002 | Bob | Smith | bob.smith@example.com | Plata | 92126 | 85000 | y |
|   | FIN003 | Charlie | Kim | charlie.kim@example.com | Platino | 60614 | 175000 | y |
|   | FIN004 | Diana | Lee | diana.lee@example.com | Oro | 30303 | 98000 | y |
|   | FIN005 | Ethan | Marrón | ethan.brown@example.com | Bronce | 75201 | 60000 | y |

## Ingesta del archivo CSV

* Cree un conjunto de datos llamado **_FinWiseCustomerDataSetWithAnnualIncome_** basado en el **_FinWiseProfileSchema_** creado en el paso anterior

* Vaya a Conexiones -> Fuentes -> Sistema local
* Seleccione **_Agregar datos_** en la carga de archivo local. Asegúrese de seleccionar _**FinWiseCustomerDataSetWithAnnualIncome**_ como conjunto de datos de destino.
  ![ingesta-csv](assets/ingest-csv-into-dataset.png)
* Vaya a la pantalla siguiente. Cargue el [archivo csv](assets/finwise_profiles.csv) y verifique las asignaciones
  ![asignaciones](assets/mappings.png)

* Haga clic en Finish para iniciar el proceso de ingesta de datos

## Verificar perfil

* Vaya a Cliente ->Perfiles y busque ID de FinWise CRM igual a FIN001 o cualquier otro valor válido
  ![perfil de verificación](assets/verify-profiles.png)
