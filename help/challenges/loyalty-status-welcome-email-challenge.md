---
title: 'Crear un correo electrónico de bienvenida con estado de fidelidad: desafío'
description: Comprender los conceptos básicos para construir un recorrido en el lienzo del recorrido.
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: 0e83d8fbad6bd87ed25980251970898cb5b94bc0
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 7%

---

# Crear un correo electrónico de bienvenida con estado de fidelidad: desafío

![Correo electrónico de bienvenida del estado de fidelidad de AJO: desafiar titular](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| Desafío | Crear un correo electrónico de bienvenida de estado de fidelidad |
|---|---|
| Grupo de usuarios | Administrador de recorridos |
| Capacidades necesarias | <ul><li>[Creación de contenido de correo electrónico con el editor de mensajes](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-email-content-with-the-message-editor.html?lang=en)</li> <li>[Uso de información de evento contextual para la personalización](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html?lang=en)</li><li>[Uso de funciones de ayuda para la personalización](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html?lang=en)</li></ul> |
| Recursos que se van a descargar | [Recursos de confirmación de pedido](/help/challenges/assets/email-assets/order-confirmation-assets.zip) |

## La historia

Luma ofrece un programa de fidelidad como una forma de atraer y retener a sus clientes. El programa ofrece cuatro niveles diferentes: Plata, oro, platino y diamante.

Cada nivel de lealtad recibe diferentes niveles o recompensas, descuentos y otros incentivos especiales como recompensa por su negocio habitual.

Subrayar el carácter especial de los diamantes. Luma quiere enviar un correo electrónico de bienvenida a los clientes cuando llegan al nivel de diamante.

## Su desafío

Se le ha encargado que configure un recorrido que envíe automáticamente un correo electrónico de bienvenida a los clientes cuando lleguen al nivel de lealtad de diamantes.

>[!NOTE]
> Si está trabajando en un simulador para pruebas de formación compartido, se recomienda añadir su nombre o iniciales como un prefijo al nombre de cualquier elemento que cree.

>[!BEGINTABS]

>[!TAB Tarea]

Envíe un correo electrónico cuando un cliente fiel se desplace a un nivel Diamante para felicitarlo e informarle de sus nuevas ventajas. Las

1. Cree un segmento en Journey Optimizer llamado **Luma: estado de diamante**
2. Cree un recorrido que se active cuando un cliente se desplace al nuevo nivel de lealtad de Diamante (específicamente cuando el cliente entra en el segmento definido para un nuevo miembro de nivel Diamante) para enviar el correo electrónico &quot;Luma - Nuevo estado - Diamante - Transaccional&quot;
   1. Crear un mensaje de correo electrónico transaccional con el título `(your name)_Luma – New Status – Diamond – Transactional email message`.
   2. Dar al correo electrónico una línea de asunto `Welcome to Diamond Status, (recipient's first name)!`.
   3. Utilice el archivo de HTML proporcionado **[DiamondStatusEmail.html](/help/challenges/assets/email-assets/DiamondStatusEmail.html)** para el cuerpo del correo electrónico.
3. Una vez finalizado, ponga el recorrido en modo de prueba y déclencheur el recorrido para enviarse a sí mismo  

   1. Crear un mensaje de correo electrónico transaccional con el título `(your name)_Luma – New Status – Diamond – Transactional email message`.
   1. Dar al correo electrónico una línea de asunto `Welcome to Diamond Status, (recipient's first name)!`.
   1. Utilice el archivo de HTML proporcionado **[DiamondStatusEmail.html](/help/challenges/assets/email-assets/DiamondStatusEmail.html)** para el cuerpo del correo electrónico.
4. Una vez finalizado, ponga el recorrido en modo de prueba y déclencheur el recorrido para enviarse a sí mismo  

### Crear la Luma: Nuevo estado - Diamante - Mensaje de correo electrónico transaccional

Crear un mensaje de correo electrónico de bienvenida

### **Recorrido n.º 3 - Correo electrónico de bienvenida de actualización del estado de los diamantes**


>[!TAB Criterios de éxito]

Prueba del recorrido:

1. Asegúrese de que el evento de calificación de segmentos tenga el espacio de nombres = correo electrónico
1. Anule los parámetros de correo electrónico predeterminados y establézcalos en su propia dirección de correo electrónico
1. Establecer el recorrido en modo de prueba
1. Déclencheur de un evento
1. Añada la siguiente dirección de correo electrónico al campo Identificador de perfil : Jenna_Palmer9530@emailsim.io

Debe recibir el correo electrónico personalizado &quot;Luma - Nuevo estado - Diamante-transaccional&quot;.

>[!TAB Compruebe su trabajo]

Este es el aspecto que debería tener el recorrido:

![Diamond-status-upgrade-recorrido](/help/challenges/assets/journey-luma-diamond-status-upgrade.png)

>[!ENDTABS]
