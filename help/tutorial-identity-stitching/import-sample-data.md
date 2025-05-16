---
title: Importar datos CRM de muestra en el conjunto de datos de perfil de AEP
description: Importe registros de muestra (por ejemplo, con CRMID, correo electrónico, ingresos, código postal) para validar si AEP puede unir correctamente esos perfiles con visitantes web anónimos en función de identificadores compartidos como ECID.
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
jira: KT-18089
source-git-commit: 502cdc41b666959141ff4dfc63608cc463009811
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 4%

---

# Importar datos CRM de muestra en el conjunto de datos de perfil de AEP

Para comenzar la vinculación de identidad, importe datos de perfil de CRM de muestra a un conjunto de datos vinculado a un esquema habilitado para perfiles en Adobe Experience Platform

## Crear un área de nombres personalizada

* Vaya a Cliente -> Identidades -> Crear área de nombres de identidad
* Seleccione ID individual entre dispositivos y proporcione el nombre para mostrar y el símbolo de identidad como se muestra en la captura de pantalla siguiente.
  ![espacio de nombres personalizado](assets/custom-namespace.png)

## Creación de un esquema habilitado para el perfil

Cree un esquema de perfil individual denominado **_FinWiseProfileSchema_**. Incluya campos como annualIncome, email, firstName, lastName y loyaltyStatus.
Agregue un campo de identidad **_crmid_** bajo el objeto SystemIdentifier. Marcar el campo crmid como identidad y principal


![perfil-esquema](assets/finwise-profile-schema.png)

## Preparar datos de ejemplo

| crmId | firstName | lastName | Correo electrónico | loyaltyStatus | annualIncome |
|--------|-----------|----------|---------------------------|---------------|--------------|
| FIN001 | Alice | Wong | alice.wong@example.com | Oro | 336104 |
| FIN002 | Brian | Smith | brian.smith@example.com | Plata | 191065 |
| FIN003 | Cathy | Johnson | cathy.johnson@example.com | Bronce | 117015 |
| FIN004 | David | Lee | david.lee@example.com | Bronce | 61869 |
| FIN005 | Eva | Martínez | eva.martinez@example.com | Plata | 191371 |
| FIN006 | Frank | Marrón | frank.brown@example.com | Plata | 196132 |
| FIN007 | Gracia | Kim | grace.kim@example.com | Oro | 309851 |
| FIN008 | Henry | Davis | henry.davis@example.com | Oro | 318378 |
| FIN009 | Isla | Clark | isla.clark@example.com | Plata | 181776 |
| FIN010 | Jack | López | jack.lopez@example.com | Plata | 186643 |

## Ingesta del archivo CSV

* Cree un conjunto de datos llamado **_FinWiseCustomerDataSetWithAnnualIncome_** basado en el **_FinWiseProfileSchema_** creado en el paso anterior

* Vaya a Conexiones -> Fuentes -> Sistema local
* Seleccione **_Agregar datos_** en la carga de archivo local. Asegúrese de seleccionar _&#x200B;**FinWiseCustomerDataSetWithAnnualIncome**&#x200B;_ como conjunto de datos de destino.
  ![ingesta-csv](assets/ingest-csv-into-dataset.png)
* Vaya a la pantalla siguiente. Cargue el [archivo csv](assets/sample_crm_data.csv) y verifique las asignaciones
  ![asignaciones](assets/mappings.png)

* Haga clic en Finish para iniciar el proceso de ingesta de datos

## Verificar perfil

* Vaya a Cliente ->Perfiles y busque ID de FinWise CRM igual a FIN001 o cualquier otro valor válido
  ![perfil de verificación](assets/verify-profiles.png)
