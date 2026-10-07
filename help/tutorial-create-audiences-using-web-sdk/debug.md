---
title: Prueba de la solución
description: Métodos para depurar la solución
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-17923
exl-id: 33b084ea-e712-4de0-8836-8795efaac7e2
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: b32bb433-f8c6-4931-8e52-e657230a3bf2
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 0%
---
# Prueba de la solución

Para validar la implementación de, abra la página web que contiene el formulario de preferencias. Utilice las herramientas de desarrollo del explorador (pestañas Consola y Red) para monitorizar el proceso de envío del formulario. Después de enviar una preferencia (por ejemplo, seleccionando &quot;Existencias&quot;), confirme que AEP Web SDK (alloy.sendEvent) realiza correctamente el déclencheur y que se envían los datos correctos a Adobe Experience Platform. En AEP, vaya a la sección Audiencias y compruebe que su perfil cumple los requisitos de la audiencia esperada (por ejemplo, &quot;Interesado en acciones&quot;) en unos momentos, mediante la segmentación de Edge. También puede inspeccionar los datos de evento entrantes en el conjunto de datos asociado para asegurarse de que contienen el valor de preferencia correcto. Repetir este proceso para cada clase de recurso (acciones, bonos, CD) para garantizar que el flujo de trabajo completo funcione correctamente.

## Sugerencias de resolución de problemas

Si no ve que el perfil cumple los requisitos para la audiencia deseada inmediatamente, compruebe lo siguiente:


### Validar inserción de capa de datos de Adobe

* Abra la consola de → Herramientas para desarrolladores del explorador
* Escriba console.log(window.adobeDataLayer);
* Confirme que aparece un evento con el evento: &quot;assetClassSelection&quot; y el valor correcto de PreferredFinancialInstrument después del envío del formulario

### Confirmar ejecución de regla de Launch

* Abra Adobe Experience Platform Debugger (extensión de Chrome)
* Inicio de sesión en Debugger
* Enviar el formulario
* Compruebe que se captura el evento DataPushing para assetClassSelection

La siguiente captura de pantalla del depurador debería ayudarle
![aep-debugger](assets/aep-debugger.png)

### Obtención del ECID

El ECID (Experience Cloud ID) es el identificador único y persistente de Adobe que se utiliza para reconocer y unificar a los usuarios en todas las soluciones y sesiones de Experience Cloud.

* Pestaña Herramientas para desarrolladores de Chrome → Red

* Filtrar por &quot;interactuar&quot; o &quot;recopilar&quot;

* Enviar el formulario
* Haga clic en la pestaña Respuesta y anote el ECID

![get-ecid](assets/get-ecid.png)

### Comprobación del perfil en tiempo real y la calificación de audiencias

* Iniciar sesión en Journey Optimizer
* Vaya a Clientes->Perfiles->Examinar.
* Busque el ECID que obtuvo en el paso anterior, como se muestra en la captura de pantalla
  ![ecid-profile](assets/ecid-profile.png)
* Haga clic en el perfil y seleccione la pestaña de eventos para comprobar si investment_preferences_event aparece en la lista
  ![events-tab](assets/profile-events.png)
* Abra el json asociado al evento y compruebe si contiene los datos de evento correctos.

### Sugerencias adicionales de solución de problemas

* Asegúrese de que el esquema y el perfil del conjunto de datos estén habilitados.
* Asegúrese de que la segmentación de Edge esté habilitada para la audiencia de modo que la calificación se produzca en tiempo casi real.
* Esperar unos minutos y actualizar la vista Audiencias también puede ser útil, especialmente si realiza pruebas justo después de publicar los cambios.
* Asegúrese de que las reglas de audiencia estén definidas correctamente y hagan referencia a los nombres de campo y valores exactos capturados desde el envío del formulario.
