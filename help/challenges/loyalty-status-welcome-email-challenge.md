---
title: 'Crear un correo electrónico de bienvenida con estado de fidelidad: reto'
description: Comprender los conceptos básicos para construir un recorrido en el lienzo del recorrido.
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: 7a178b9c523ead0cf27aaa87d25b3752ef53f519
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 100%

---

# Crear un correo electrónico de bienvenida con estado de fidelidad: reto

![Correo electrónico de bienvenida del estado de fidelidad: titular del reto](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| Desafío | Crear un correo electrónico de bienvenida de estado de fidelidad |
|---|---|
| Grupo de usuarios | Administrador de recorridos |
| Capacidades necesarias | <ul><li>[Creación de segmentos](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=es)</li> <li>[Clasificación del segmento](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment-qualification.html?lang=es)</li><li>[Importar contenido HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html?lang=es)</li></ul> |
| Recursos que se van a descargar | [StatusUpgradeEmail.zip](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip) |

## La historia

Luma ofrece un programa de fidelidad como una forma de atraer y conservar a sus clientes. El programa ofrece cuatro niveles diferentes: bronce, plata, oro y platino. Cada nivel de fidelidad recibe diferentes recompensas, descuentos y otros incentivos especiales como recompensa por su negocio habitual.

Para destacar el estado especial de platino. Luma quiere enviar un correo electrónico de bienvenida a los clientes cuando lleguen al nivel de platino.

## Su reto

Se le ha pedido que configure un recorrido que envíe automáticamente un correo electrónico de bienvenida a los clientes cuando lleguen al nivel de fidelidad de platino.

>[!BEGINTABS]

>[!TAB Tarea]

Cuando un cliente fiel cumple los requisitos del nivel de platino, debe recibir un correo electrónico para felicitarlo e informarle de sus nuevas ventajas. El equipo creativo ha proporcionado un archivo HTML de **[Luma: actualización de estado; correo electrónico de bienvenida](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip)** con el cuerpo del correo electrónico.

1. Cree un [!UICONTROL segmento] en Journey Optimizer llamado `Luma – status upgrade`.
2. Cree un recorrido llamado `Luma – New Status – platinum`.
   1. Un cliente se traslada al recorrido cuando cumple los requisitos para el nivel de fidelidad de platino.
   2. El cliente tiene que recibir un mensaje de correo electrónico etiquetado como `Luma – Platinum Status - Welcome`, con la línea de asunto `Welcome to Platinum Status, (recipient's first name)!` y con el cuerpo del correo electrónico proporcionado por el equipo creativo. Esto es un correo electrónico [!UICONTROL transaccional].
   3. Al cargar el archivo HTML, se da cuenta de que el correo electrónico se refiere al estado “diamante” en lugar de “platino”. En vez de solicitar un nuevo archivo al equipo creativo, actualice el correo electrónico en el Diseñador de correo electrónico.

>[!TAB Requisitos de éxito]

Prueba del recorrido:

1. Asegúrese de que la variable [!UICONTROL Leer actividad de segmentos] tiene la variable [!UICONTROL área de nombres] configurada como **[!DNL Luma CRM id(lumaCrmId)]**
2. Anule el valor predeterminado [!UICONTROL parámetros de correo electrónico] y configúrelo en su propia dirección de correo electrónico
   * Muestre los valores ocultos haciendo clic en el símbolo de ojo.
   * En los [!UICONTROL Parámetros de correo electrónico], haga clic en el símbolo T (habilitar anulación de parámetros)

       ![Anular parámetros de correo electrónico](/help/challenges/assets/c3-override-email-paramters.jpg)
   
   * Haga clic en el [!UICONTROL campo Dirección]
   * En la siguiente pantalla, añada su dirección de correo electrónico entre paréntesis: `"yourname@yourdomain"` en el editor de expresiones y haga clic en OK.


3. Establezca el recorrido en modo de prueba
4. Active un evento
5. Añada [!DNL CRM ID] para `Stanleigh Stooke` en el campo [!UICONTROL Identificador de perfil]: `4f34057d9d9e792c28ba18ecae378e98`

**Resultado:** debería recibir el correo electrónico de bienvenida personalizado *Luma, estado platino*.

>[!TAB Compruebe su trabajo]

Este es el aspecto que debería tener el recorrido:

![platino-estado-actualización-recorrido](/help/challenges/assets/journey-luma-status-upgrade.png)


Este es el aspecto que debería tener el correo electrónico:

![Luma, actualización de estado: correo electrónico de bienvenida](/help/challenges/assets/status-upgrade-welcome-email.png)

>[!ENDTABS]
