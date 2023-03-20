---
title: 'Crear un correo electrónico de bienvenida con estado de fidelidad: reto'
description: Cree un recorrido que envíe automáticamente un correo electrónico de bienvenida a los clientes cuando lleguen al nivel de fidelidad.
kt: 8109
feature: Journeys
role: User
level: Beginner
last-substantial-update: 2023-02-01T00:00:00Z
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: aaf273b8b6fe0a5f33c132cc0113ec2460152349
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---

# Crear un correo electrónico de bienvenida con estado de fidelidad: reto

![Correo electrónico de bienvenida del estado de fidelidad: titular del reto](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| Reto | Crear un correo electrónico de bienvenida de estado de fidelidad |
|---|---|
| Grupo de usuarios | Administrador de recorridos |
| Capacidades necesarias | <ul><li>[Creación de segmentos](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=es)</li> <li>[Clasificación del segmento](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment-qualification.html?lang=es)</li><li>[Importar contenido HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/import-and-author-html-email-content.html?lang=es)</li></ul> |
| Recursos que se van a descargar | [StatusUpgradeEmail.zip](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip) |

{style="table-layout:auto"}

## La historia

Luma ofrece un programa de fidelidad como una forma de atraer y conservar a sus clientes. El programa ofrece cuatro niveles diferentes: bronce, plata, oro y platino. Cada nivel de fidelidad recibe diferentes recompensas, descuentos y otros incentivos especiales como recompensa por su negocio habitual.

Para subrayar el estado especial de platino, Luma quiere enviar un correo electrónico de bienvenida a los clientes cuando lleguen al nivel de platino.

## Su reto

Se le ha pedido que configure un recorrido que envíe automáticamente un correo electrónico de bienvenida a los clientes cuando lleguen al nivel de fidelidad de platino.

>[!BEGINTABS]

>[!TAB Tarea]

Cuando un cliente fiel cumple los requisitos del nivel de platino, debe recibir un correo electrónico para felicitarlo e informarle de sus nuevas ventajas. El equipo creativo ha proporcionado un archivo HTML de **[Luma: actualización de estado; correo electrónico de bienvenida](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip)** con el cuerpo del correo electrónico.

1. Cree un [!UICONTROL segmento] en Journey Optimizer llamado `Luma - platinum status`.

1. Cree un recorrido llamado `Luma - New Status - platinum`.

   1. Un cliente se traslada al recorrido cuando cumple los requisitos para el nivel de fidelidad de platino.

   1. El cliente tiene que recibir un mensaje de correo electrónico etiquetado como `Luma - Platinum Status - Welcome`, con la línea de asunto `Welcome to Platinum Status, {firstName}!` y con el cuerpo del correo electrónico proporcionado por el equipo creativo. Esto es un correo electrónico [!UICONTROL transaccional].

   1. Al cargar el archivo HTML, se da cuenta de que el correo electrónico se refiere al estado “diamante” en lugar de “platino”. En vez de solicitar un nuevo archivo al equipo creativo, actualice el correo electrónico en el [!UICONTROL Diseñador de correo electrónico].

>[!TAB Requisitos de éxito]

Prueba del recorrido:

1. Asegúrese de que la variable [!UICONTROL Leer actividad de segmentos] tiene la variable [!UICONTROL área de nombres] configurada como **[!DNL Luma CRM id(lumaCrmId)]**.

1. Anule el valor predeterminado [!UICONTROL parámetros de correo electrónico] y configúrelo en su propia dirección de correo electrónico:
   * En los **[!UICONTROL parámetros de correo electrónico]**, haga clic en el símbolo T (habilitar anulación de parámetros)

   * Haga clic en el campo **[!UICONTROL Dirección]**.

   * En la siguiente pantalla, añada su dirección de correo electrónico entre paréntesis: `"yourname@yourdomain"`en el editor de expresiones y haga clic en **[!UICONTROL Aceptar]**.

1. Establezca el recorrido en modo de prueba.

1. Seleccionar **[!UICONTROL Activador de un evento]**.

1. Añada lo siguiente `CRM ID` para `Stanleigh Stooke` en el campo **[!UICONTROL Identificador de perfil]**: `4f34057d9d9e792c28ba18ecae378e98`

**Resultado:** debería recibir el correo electrónico de bienvenida personalizado *Luma, estado de platino: correo electrónico* de bienvenida.

Este es el aspecto que debería tener el correo electrónico:

![Luma, actualización de estado: correo electrónico de bienvenida](/help/challenges/assets/status-upgrade-welcome-email.png)

>[!TAB Compruebe su trabajo]

Este es el aspecto que debería tener el segmento:

![Luma - estado de platino - segmento](/help/challenges/assets/segment-luma-platinum-status.png)

Este es el aspecto que debería tener el recorrido:

![platino-estado-actualización-recorrido](/help/challenges/assets/journey-luma-status-upgrade.png)

>[!ENDTABS]
