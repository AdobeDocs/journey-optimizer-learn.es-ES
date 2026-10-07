---
title: Depuración de push web en AJO
description: Esta página proporciona sugerencias útiles para depurar el flujo de notificaciones push web, incluida la verificación de solicitudes de Web SDK,
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00.000Z
jira: KT-20879
exl-id: 55cb0875-2953-4d5c-a240-4277aa2f746e
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: 66e1fd99-672d-5d64-aa58-eca107f0fbae
    internal-label: Push
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 2%
---
# Depuración de push web en AJO

Esta página proporciona sugerencias útiles para depurar el flujo de notificaciones push web, incluida la verificación de solicitudes de Web SDK, la comprobación del ECID y el perfil de usuario en AEP y la garantía de que los eventos como price.drop se envían y reciben correctamente.

- **Usar Adobe Experience Platform Debugger (extensión de Chrome)**\
  Instale la extensión [AEP Debugger para Chrome](https://chrome.google.com/webstore/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob) a fin de inspeccionar la actividad de Web SDK con mayor facilidad:

Esta herramienta le permite:
- Ver solicitudes y respuestas de Web SDK\
- Compruebe el ECID (Experience Cloud ID)\
- Validar la configuración del flujo de datos y las cargas útiles

- **Comprobar si se ha identificado al usuario (ECID)**\
  Utilice AEP Debugger o la consola del explorador para confirmar que se ha generado un ECID. Este ID se utiliza para rastrear al usuario en AEP y AJO.

- **Use la ficha Red para comprobar las solicitudes**\
  Abra la **pestaña Red** en las herramientas para desarrolladores del explorador y filtre las solicitudes realizadas por Web SDK (busque `/collect` o `interact`).
  - Las solicitudes de confirmación se envían cuando se carga la página y cuando se activan las acciones
  - Compruebe que el evento `price.drop` esté incluido en la carga útil

- **Buscar el perfil de usuario en AEP**\
  Utilice el ECID para buscar el perfil del usuario en Adobe Experience Platform. Esto ayuda a confirmar que se reconoce al usuario y que sus datos (como la suscripción push) se almacenan correctamente.

- **Verificar que se reciba el evento `price.drop`**\
  Después de activar el evento desde la página web, compruebe en AEP si el evento se ha introducido y asociado con el mismo ECID.
Compruebe el json del evento message.feedback para `feedback.status`. El valor de estado debe ser `sent`
  ![caída de precios](assets/price-drop-profile-event.png)

- **Confirmar que las notificaciones push están habilitadas**\
  Asegúrese de que:
  - El usuario aceptó el mensaje de notificación del explorador
  - Existe un token push en el perfil del usuario

- **Comprobar la configuración del recorrido**\
  Asegúrese de que el recorrido esté publicado y configurado para escuchar el evento `price.drop`.
