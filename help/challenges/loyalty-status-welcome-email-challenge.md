---
title: 'Crear un correo electrónico de bienvenida con estado de fidelidad: desafío'
description: Comprender los conceptos básicos para construir un recorrido en el lienzo del recorrido.
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
source-git-commit: 957515149af1281d29a45b24ca499ef097656eb8
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 8%

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

### Cree un segmento de Estado de diamantes de Luma.

Cree un segmento en Journey Optimizer llamado **su nombre - Luma - Estado de diamante**.

### Crear la Luma: Nuevo estado - Diamante - Mensaje de correo electrónico transaccional

Crear un mensaje de correo electrónico de bienvenida

1. Crear un mensaje de correo electrónico transaccional con el título `(your name)_Luma – New Status – Diamond – Transactional email message`.
2. Dar al correo electrónico una línea de asunto `Welcome to Diamond Status, (recipient's first name)!`.
3. Utilice el archivo de HTML proporcionado **[DiamondStatusEmail.html](/help/challenges/assets/email-assets/DiamondStatusEmail.html)** para el cuerpo del correo electrónico.


### **Recorrido n.º 3 - Correo electrónico de bienvenida de actualización del estado de los diamantes**

Envíe un correo electrónico cuando un cliente fiel se desplace a un nuevo nivel para felicitarlo e informarle de sus nuevas ventajas.

1. Cree un recorrido que se active cuando un cliente se desplace al nuevo nivel de lealtad de Diamante (específicamente cuando el cliente entra en el segmento definido para un nuevo miembro de nivel Diamante) para enviar el correo electrónico &quot;Luma - Nuevo estado - Diamante - Transaccional&quot;
2. Una vez finalizado, ponga el recorrido en modo de prueba y déclencheur el recorrido para enviarse a sí mismo  

CRITERIOS DE ÉXITO

Debe recibir el correo electrónico personalizado &quot;Luma - Nuevo estado - Diamante-transaccional&quot;.
