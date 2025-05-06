---
title: 'Lección 3: Creación de una campaña web en la aplicación'
description: Cree y almacene en déclencheur una campaña web en la aplicación.
feature: In App
role: User
level: Intermediate
doc-type: Article
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-13983
thumbnail: KT-13983.jpeg
exl-id: 0f84adfb-edb1-47fa-b696-58eec2b33bb1
source-git-commit: b5577da9a983594cb34edf5c53e2995024e30e78
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---

# Lección 3: Creación de una campaña web en la aplicación

Ahora que ha creado experiencias móviles para la aplicación, en esta lección, crea una de las experiencias que ha visto en el sitio web de Fréscopa. Puede crear una campaña web en la aplicación. Puede diseñar y personalizar un mensaje y definir un déclencheur que lo active.

## Objetivos de aprendizaje

* Obtenga información sobre cómo crear una campaña web en la aplicación.
* Déclencheur de un mensaje en la aplicación.

## Ejercicio 3.1 Creación de una campaña web en la aplicación

En este ejercicio, crea la campaña y define en qué página web aparece el mensaje en la aplicación.

1. En Journey Optimizer, en el panel de navegación izquierdo, en **ADMINISTRACIÓN DE RECORRIDO**, seleccione **Campañas**.

1. Haga clic en **Crear campaña**.

   ![Crear campaña](/help/summit-lab-2024/l820-lab-workbook/assets/4-1-create-campaign.png)

1. En la página **Crear campaña**, en la sección **Acción**, active la casilla **Mensaje en la aplicación**.

1. En el menú desplegable **Enviar a**, seleccione **Web.**

1. Escriba la siguiente dirección URL: **https://dsn.adobe.com/web/adobe-summit-2024/exercise** - *Esta es la página web en la que aparecerá el mensaje.*

   ![URL en la aplicación](/help/summit-lab-2024/l820-lab-workbook/assets/4-1-1-in-app-url.png)

1. Haga clic en **[!UICONTROL Crear]**.

## Ejercicio 3.2 Configuración de la campaña

En esta página, puede definir las propiedades de la campaña y el evento que déclencheur el mensaje en la aplicación para que aparezca en la página web. Mantenga el resto de configuraciones en la predeterminada. Para este ejercicio no es necesario definir una audiencia específica.

### 3.2.1 [!UICONTROL Sección Propiedades]

1. En la sección **Propiedades**, asigne a tu campaña un **Nombre** único:

   >[!NOTE]
   > Asegúrese de comenzar el nombre con su número de asiento, para que pueda
   > busque la campaña más tarde.
   > 
   > Por ejemplo, si el número de puestos es 99: 
   >
   > ![Nombre de propiedades](/help/summit-lab-2024/l820-lab-workbook/assets/4-1-2-properties-name.png)


### 3.2.2 Configurar la regla de déclencheur personalizada

En esta sección define los déclencheur para que el mensaje aparezca en el sitio web. Usted define un déclencheur único que le permite enviarse el mensaje a sí mismo.

1. Desplácese hacia abajo hasta la **[!UICONTROL sección de Déclencheur]** y, a continuación, haga clic en **[!UICONTROL Editar déclencheur]**.

   ![modificar](/help/summit-lab-2024/l820-lab-workbook/assets/3-2-1-2-edit-triggers.png)

1. En el generador de reglas, haga clic en **[!UICONTROL Inicio de la aplicación]** y, en la lista desplegable, seleccione *Datos enviados a la plataforma*.
   ![Menú desplegable de evento de déclencheur](/help/summit-lab-2024/l820-lab-workbook/assets/trigger-drop-down-sent-to-platform.png)

1. Agregue una condición haciendo clic en **[!UICONTROL + Agregar condición]**.

   ![botón de añadir condición](/help/summit-lab-2024/l820-lab-workbook/assets/3-2-1-3-add-condition.png)

1. En el menú desplegable **[!UICONTROL Seleccionar un rasgo]**, seleccione **[!UICONTROL tipo de evento XDM]**.

   ![Tipo de evento XDM](/help/summit-lab-2024/l820-lab-workbook/assets/4-1-2-dropdown-xdm-event.png)


1. En el siguiente campo de texto, agregue un *`<custom string value>`* que pueda recordar y presione **[!UICONTROL Agregar]** `<custom string value>` para guardar el valor.

   Este valor de cadena personalizado se utiliza más adelante para activar el mensaje.

   >[!TIP]
   > Añadir el número de asiento al valor de cadena personalizado, lo hará único y fácil de recordar.
   > 
   > Por ejemplo: `99web`
   > 

   ![agregar valor de cadena de déclencheur personalizado](/help/summit-lab-2024/l820-lab-workbook/assets/4-1-2-add-custom-trigger-dropdown.png)

1. Presione el botón **[!UICONTROL Listo]** en la parte superior derecha.

>[!SUCCESS]
>
>Ahora ha definido el mensaje web en la aplicación con un evento de déclencheur personalizado.
>
>![Campaña web con déclencheur personalizado definido](/help/summit-lab-2024/l820-lab-workbook/assets/4-1-2-2-web-campaign-with-custom-trigger.png)


### 3.2.3 Editar el contenido del mensaje en la aplicación

En esta sección define el contenido, el diseño y el diseño del mensaje.

1. Haga clic en el botón **Editar contenido** de la sección **Acción** para acceder a la construcción de creación.

   ![Botón Editar contenido](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-3-1-edit-content-button.png)

1. El proceso de creación es el mismo proceso que ha completado en los ejercicios en la aplicación móvil anteriores. Dedique tiempo a editar libremente su mensaje con su propio título, cuerpo y contenido multimedia.

   Si utiliza el diseño modal o de pantalla completa, puede agregar un botón. Puede usar esta dirección URL para abrir la página de producto: **https://dsn.adobe.com/web/adobe-summit-2024/P2WsaDPf_**

1. Cuando termine de editar el mensaje, haga clic en **[!UICONTROL Revisar para activar]**.

1. Si todo parece correcto en la pantalla de revisión, haga clic en **[!UICONTROL Activar]** para publicar el mensaje en la aplicación web.

1. Se le devolverá al Panel de campañas.

   Espere a que su estado de campaña cambie a **Activo** antes de pasar a 4.1.4.

## Ejercicio 3.3 Déclencheur del mensaje web en la aplicación

1. Vaya al sitio web de Fréscopa y navegue hasta la página **Ejercicio** de su explorador.

   ![vínculo de ejercicios web](/help/summit-lab-2024/l820-lab-workbook/assets/4-2-frescopa-web-exercise-link.png)

1. Asegúrese de actualizar la página web.

1. Escriba el valor de cadena único que definió en la campaña.

   ![página de ejercicio](/help/summit-lab-2024/l820-lab-workbook/assets/4-2-exercise-page.png)

1. Haga clic en **[!UICONTROL Enviar]**.

>[!SUCCESS]
>
>Al hacer clic en el botón Enviar con su valor único, se activará el mensaje en la aplicación web en déclencheur. Además, debería ver el mensaje web en la aplicación en la pantalla.
>
>Este ejercicio simuló un evento de envío de XDM personalizado que vio a través de su experiencia de cliente de Fréscopa.


## Recursos adicionales

**Vídeos explicativos:**

* [Creación de una campaña en la aplicación](/help/channels/create-an-in-app-campaign.md)
* [Creación de un mensaje en la aplicación](/help/channels/author-in-app-messages.md)

**Documentación del producto:**

* [Introducción al canal en la aplicación](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/get-started-in-app)
* [Crear un mensaje en la aplicación web](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/create-in-app-web)
* [Diseño del contenido en la aplicación](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/design-in-app)
* [Compruebe y envíe su notificación en la aplicación](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/send-in-app)
