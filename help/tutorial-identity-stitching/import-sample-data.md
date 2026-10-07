---
title: Importar datos CRM de muestra en el conjunto de datos de perfil de AEP
description: Importe registros de muestra (por ejemplo, con CRMID, correo electrónico, ingresos, código postal) para validar si AEP puede unir correctamente esos perfiles con visitantes web anónimos en función de identificadores compartidos como ECID.
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: 33c8c386-f417-45a8-83cf-7312d415b47a
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
source-wordcount: '305'
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
Agregue un campo de identidad **_crmid_** como se muestra. Marque el campo crmid como identidad y principal.


![perfil-esquema](assets/finwise-profile-schema.png)

## Preparar datos de ejemplo

Actualice las direcciones de correo electrónico ficticias a direcciones reales. Se utilizarán más adelante al enviar mensajes con Adobe Journey Optimizer.

|   | crmId | firstName | lastName | correo electrónico | loyaltyStatus | zipCode | annualIncome |
|---|--------|-----------|----------|-------------------------|---------------|---------|--------------|
|   | FIN001 | Alice | Wong | alice.wong@example.com | Oro | 92128 | 120000 |
|   | FIN002 | Bob | Smith | bob.smith@example.com | Plata | 92126 | 85000 |
|   | FIN003 | Charlie | Kim | charlie.kim@example.com | Platino | 60614 | 175000 |
|   | FIN004 | Diana | Lee | diana.lee@example.com | Oro | 30303 | 98000 |
|   | FIN005 | Ethan | Marrón | ethan.brown@example.com | Bronce | 75201 | 60000 |

## Ingesta del archivo CSV

* Cree un conjunto de datos llamado **_FinWiseCustomerDataSetWithAnnualIncome_** basado en el **_FinWiseProfileSchema_** creado en el informe anterior. Asegúrese de que el conjunto de datos esté habilitado para el perfil.

* Vaya a Conexiones -> Fuentes -> Sistema local
* Seleccione **_Agregar datos_** en la carga de archivo local. Asegúrese de seleccionar _&#x200B;**FinWiseCustomerDataSetWithAnnualIncome**&#x200B;_ como conjunto de datos de destino.
  ![ingesta-csv](assets/ingest-csv-into-dataset.png)
* Vaya a la pantalla siguiente. Cargue el [archivo csv](assets/finwise_profiles.csv) y verifique las asignaciones
  ![asignaciones](assets/mappings.png)

* Haga clic en Finish para iniciar el proceso de ingesta de datos

## Verificar perfil

* Vaya a Cliente ->Perfiles y busque ID de FinWise CRM igual a FIN001 o cualquier otro valor válido
  ![perfil de verificación](assets/verify-profiles.png)
