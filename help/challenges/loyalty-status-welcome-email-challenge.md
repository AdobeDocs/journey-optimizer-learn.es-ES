---
title: 'Crear un correo electrónico de bienvenida con estado de fidelidad: desafío'
description: Comprender los conceptos básicos para construir un recorrido en el lienzo del recorrido.
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: e148101f8404c8e2019ee17823bcf1d7a9668bc5
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 4%

---

# Crear un correo electrónico de bienvenida con estado de fidelidad: desafío

![Correo electrónico de bienvenida del estado de fidelidad de AJO: desafiar titular](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| Desafío | Crear un correo electrónico de bienvenida de estado de fidelidad |
|---|---|
| Grupo de usuarios | Administrador de recorridos |
| Capacidades necesarias | <ul><li>[Creación de segmentos](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html)</li> <li>[Clasificación del segmento](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment-qualification.html)</li><li>[Importar contenido del HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html)</li></ul> |
| Recursos que se van a descargar | [platinumStatusEmail.zip](/help/challenges/assets/email-assets/platinumStatusEmail.zip) |

## La historia

Luma ofrece un programa de fidelidad como una forma de atraer y retener a sus clientes. El programa ofrece cuatro niveles diferentes: Bronce, plata, oro y platino. Cada nivel de lealtad recibe diferentes niveles o recompensas, descuentos y otros incentivos especiales como recompensa por su negocio habitual.

Subrayar el estado especial de platino. Luma quiere enviar un correo electrónico de bienvenida a los clientes cuando lleguen al nivel de platino.

## Su desafío

Se le ha pedido que configure un recorrido que envíe automáticamente un correo electrónico de bienvenida a los clientes cuando lleguen al nivel de lealtad de platino.

>[!BEGINTABS]

>[!TAB Tarea]

Cuando un cliente fiel califica para el nivel de platino, debe recibir un correo electrónico para felicitarlo e informarle de sus nuevas ventajas. El equipo creativo ha proporcionado un archivo de HTML **[Luma: actualización de estado: correo electrónico de bienvenida](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip)** con el cuerpo del correo electrónico.

1. Cree un segmento en Journey Optimizer llamado `Luma – status upgrade`.
2. Cree un recorrido llamado &quot;Luma - Nuevo estado - platino&quot;.
   1. Un cliente se traslada al recorrido cuando cumple los requisitos para el nivel de lealtad de platino.
   2. El cliente debe recibir un mensaje de correo electrónico etiquetado `Luma – Platinum Status - Welcome`, con la línea de asunto `Welcome to Platinum Status, (recipient's first name)!` con el cuerpo proporcionado por el equipo creativo.
   3. Al cargar el archivo HTML, se da cuenta de que el correo electrónico se refiere al estado &quot;diamante&quot;, en lugar de al estado &quot;platino&quot;. En lugar de solicitar un nuevo archivo al equipo creativo, actualice el correo electrónico en el diseñador de correo electrónico.

>[¡SUGERENCIA!]
> Asegúrese de que el correo electrónico de Luma - Estado platino - Bienvenida sea transaccional.


>[!TAB Criterios de éxito]

Prueba del recorrido:

1. Asegúrese de que la actividad Leer segmento tiene el espacio de nombres establecido en **ID de Luma CRM (lumaCrmId)**
2. Anule los parámetros de correo electrónico predeterminados y establézcalos en su propia dirección de correo electrónico

+++ Haga clic aquí para obtener más información sobre cómo anular
   * Muestre los valores ocultos haciendo clic en el símbolo de ojo.
   * En los parámetros de correo electrónico, haga clic en el símbolo T (habilitar anulación de parámetros)

   ![Anular parámetros de correo electrónico](/help/challenges/assets/c3-override-email-paramters.jpg)

   * Haga clic en el campo Dirección
   * En la siguiente pantalla, añada su dirección de correo electrónico entre paréntesis: `"yourname@yourdomain"` en el editor de expresiones y haga clic en aceptar.
+++


3. Establecer el recorrido en modo de prueba
4. Déclencheur de un evento
5. Añada el siguiente ID de CRM para la reserva de Stanleigh al campo Identificador de perfil : `4f34057d9d9e792c28ba18ecae378e98`

Debería recibir el *Luma: estado de platino, bienvenida* correo electrónico.

>[!TAB Compruebe su trabajo]

Este es el aspecto que debería tener el recorrido:

![platinum-status-upgrade-recorrido](/help/challenges/assets/journey-luma-status-upgrade.png)


Este es el aspecto que debería tener el correo electrónico:

![Luma: actualización de estado: correo electrónico de bienvenida](/help/challenges/assets/status-upgrade-welcome-email.png)

>[!ENDTABS]
