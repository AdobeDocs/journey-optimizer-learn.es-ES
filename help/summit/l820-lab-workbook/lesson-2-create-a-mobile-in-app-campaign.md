---
title: 'Lección 2: Creación de una campaña móvil en la aplicación'
description: Cree y déclencheur una campaña móvil en la aplicación.
feature: In App
role: User
level: Intermediate
doc-type: Article
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-14983
thumbnail: KT-14983.jpeg
exl-id: fe18eca7-229c-4867-ab34-1862bad63124
source-git-commit: 4f5c92f79eba3651b3633b7850e993160cb1f72c
workflow-type: tm+mt
source-wordcount: '1434'
ht-degree: 1%

---

# Lección 2: Creación de una campaña móvil en la aplicación

En esta lección, crea y almacena en déclencheur mensajes móviles en la aplicación.

## Objetivos de aprendizaje

* Comprenda cómo se activan los mensajes en la aplicación.
* Obtenga información sobre cómo crear una campaña móvil en la aplicación.
* Déclencheur de un mensaje en la aplicación.

## Ejercicio 2.1: iniciar sesión en Journey Optimizer

1. Abrir [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-ajo-lab/journey-optimizer/home){target="_blank"}
2. Inicie sesión con los siguientes detalles:
   <br>
   **Nombre de usuario:** L820+**`<your seat number>`**@adobeeventlab.com
   **Contraseña:**   ¡Adobe 2024!
   <br>
Puede encontrar los detalles de su inicio de sesión en el escritorio de su máquina de laboratorio. Utilice Adobe ID y la contraseña.
   ![escritorio](/help/summit/l820-lab-workbook/assets/desk-top.png)

   ![Pantalla de inicio de sesión](/help/summit/l820-lab-workbook/assets/2-1-1-ajo-sign-in.png)
   <br>
3. Puede omitir las dos pantallas siguientes:
   <br>
   ![Número de teléfono](/help/summit/l820-lab-workbook/assets/2-1-3-ajo-add-phone.png)
   <br>
   ![ventana emergente de Personalization](/help/summit/l820-lab-workbook/assets/2-1-4-ajo-personalization-pop-up.png)


>[!SUCCESS]
>
>Debe iniciar sesión en Journey Optimizer y acceder a la página principal de:
>
>![Página principal de AJO](/help/summit/l820-lab-workbook/assets/2-1-5-ajo-homepage.png)


## Ejercicio 2.2 Creación de una campaña móvil en la aplicación

En este ejercicio, crea una campaña de mensajería en la aplicación, que se activa al abrir la aplicación.

1. En Journey Optimizer, en el panel de navegación izquierdo, seleccione **[!UICONTROL Campañas]**.

1. Haga clic en **[!UICONTROL Crear campaña]**.

   ![Crear campaña](/help/summit/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. En la página **[!UICONTROL Crear campaña]**, en la sección **[!UICONTROL Acción]**, active la casilla **[!UICONTROL Mensaje en la aplicación]**.

1. En el menú desplegable **[!UICONTROL Enviar a]**, seleccione **[!DNL Mobile]**.

1. En el menú desplegable **[!UICONTROL Superficie de la aplicación]**, seleccione **[!DNL Frecopa Mobile App]**.

1. Haga clic en **[!UICONTROL Crear]**.

   ![Superficie de aplicación](/help/summit/l820-lab-workbook/assets/3-1-1-1-create.png)

>[!SUCCESS]
>
>Ahora debería estar en las propiedades de Campaign:
>
> ![Propiedades de la campaña](/help/summit/l820-lab-workbook/assets/3-1-1-2-campaign-properties.png)

## Ejercicio 2.3 Configuración de la campaña

### 2.3.1 [!UICONTROL Sección de propiedades]

Dé un nombre a su campaña. Asegúrese de comenzar el nombre con el número de asiento para que pueda encontrar fácilmente la campaña de nuevo.

Por ejemplo, si el número de puesto es 99: `99 - Welcome Campaign`.

![sección de propiedades](/help/summit/l820-lab-workbook/assets/3-1-2-1-properties-section.png)

### 2.3.2 Configurar la regla de déclencheur personalizada

1. Desplácese hacia abajo hasta la **[!UICONTROL sección de Déclencheur]** y, a continuación, haga clic en **[!UICONTROL Editar déclencheur]**.

   ![modificar](/help/summit/l820-lab-workbook/assets/3-2-1-2-edit-triggers.png)

1. En el generador de reglas, haga clic en **[!UICONTROL Inicio de la aplicación]** y, en la lista desplegable, seleccione *Datos enviados a la plataforma*.
   ![Enviado a la plataforma de datos](/help/summit/l820-lab-workbook/assets/trigger-drop-down-sent-to-platform.png)

1. Agregue una condición haciendo clic en **[!UICONTROL Agregar condición]**.

   ![botón de añadir condición](/help/summit/l820-lab-workbook/assets/3-2-1-3-add-condition.png)

1. En el menú desplegable **[!UICONTROL Seleccionar un rasgo]**, seleccione **[!UICONTROL tipo de evento XDM]**.

   ![Tipo de evento XDM](/help/summit/l820-lab-workbook/assets/4-1-2-dropdown-xdm-event.png)

1. En el siguiente campo de texto, agregue un *`<custom string value>`* que pueda recordar.

1. Para guardar el valor, haga clic en **[!UICONTROL Agregar**] `<custom string value>`.

   Este valor de cadena personalizado se utiliza más adelante para activar el mensaje.

   >[!TIP]
   > Añadir el número de asiento al valor de cadena personalizado hace que sea único y fácil de recordar.
   > 
   > Por ejemplo: `99exerciseTrigger`

   ![agregar valor de cadena de déclencheur personalizado](/help/summit/l820-lab-workbook/assets/3-1-2-2-add-custom-trigger.png)

1. Haga clic en **[!UICONTROL Listo]** en la parte superior derecha.

>[!SUCCESS]
>
>Ahora ha definido el mensaje en la aplicación con un evento de déclencheur personalizado.
>
>![Campaña con déclencheur personalizado definido](/help/summit/l820-lab-workbook/assets/3-1-2-2-campaign-with-custom-trigger.png)


### 2.3.3 Editar el contenido del mensaje en la aplicación

En la sección **[!UICONTROL Acción]**, haga clic en **[!UICONTROL Editar contenido]**.

![Botón Editar contenido](/help/summit/l820-lab-workbook/assets/3-1-3-1-edit-content-button.png)

Se muestra el editor de [!UICONTROL mensajes en la aplicación], donde puede configurar el contenido de los mensajes en la aplicación.

#### 2.3.3.1 Diseño

Seleccione qué diseño debe aplicarse al mensaje.

Por ejemplo, haga clic en **[!UICONTROL Modal]** para que su mensaje en la aplicación sea un diseño modal.

![botón modal](/help/summit/l820-lab-workbook/assets/3-1-3-2-modal-button.png)

#### 2.3.3.2 Creación del mensaje y publicación de la campaña

1. En la sección de medios, pegue la siguiente URL: `https://t3.ftcdn.net/jpg/02/79/42/52/240_F_279425217_Hr9VBkknMr4fTpuZbxZXfcYdC7jSvGl2.jpg`
   <br>
Cuando haga clic fuera del campo de valor, la imagen debería aparecer.

   ![medios mostrados en la vista previa](/help/summit/l820-lab-workbook/assets/3-1-3-2-media.png)

2. En la siguiente sección **[!UICONTROL Contenido]**, agrega tu propio texto personalizado que quieras que se muestre en tu mensaje para **[!UICONTROL Encabezado]** y **[!UICONTROL Cuerpo]**.

   ![Encabezado y cuerpo](/help/summit/l820-lab-workbook/assets/3-1-3-2-content.png)

3. Opciones adicionales:
   1. **Botones:**

      ![Sección de botones](/help/summit/l820-lab-workbook/assets/3-1-3-2-buttons.png)

      1. En esta sección del editor, puede personalizar el texto del botón CTA editando el campo Texto del botón.

      2. El campo **[!UICONTROL Interact event]** se usa para definir el valor que se pasa al SDK cuando el usuario presiona la CTA.

      3. El campo **[!UICONTROL Target]** se usa para definir adónde desea que lleve el CTA al usuario. Esto incluye direcciones URL y vínculos profundos. Por ejemplo, puede agregar este vínculo profundo a una página de producto como `dxdemo://exoticVibes`.

      4. Puede agregar botones adicionales al presionar **[!UICONTROL + Agregar botón]**.

      5. Cuando se añade un segundo botón al mensaje, tiene la opción de cambiar el diseño del botón con el cuadro desplegable.


   2. **Formato avanzado**

      ![cambio de formato avanzado](/help/summit/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-toggle.png)

      Al habilitar esta opción, se proporcionan opciones de personalización adicionales en el editor.

      1. Tamaño del medio
      1. Fuente
      1. Tamaño de publicación
      1. Color de fuente
      1. Alineación

      ![opciones de formato avanzadas](/help/summit/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-options.png)

   3. **Ficha Configuración**

      Si cambia a esta ficha y en la sección **[!UICONTROL Vista previa]**, puede cambiar la **Vista previa de la aplicación**.
      <br>\
      ![Ficha Configuración](/help/summit/l820-lab-workbook/assets/3-1-3-1-settings-tab.png)
      <br>

      1. La sección **[!UICONTROL Diseño]** le da la opción de usar una imagen como fondo o un color sólido.

      2. La sección **[!UICONTROL Message]** proporciona interacciones personalizadas que se pueden habilitar para el mensaje:
         1. Gestos personalizados
         2. Adquisición de IU
         3. Adquisición de IU personalizada
         4. Tamaño personalizado
         5. Posición personalizada
         6. Animación personalizada
         7. Esquina redonda del mensaje

   <br>
4. Cuando termine de crear el contenido y esté satisfecho con el mensaje, haga clic en el **[!UICONTROL botón Revisar para activar]**.

   >[!SUCCESS]
   >
   > Ya ha completado la creación del mensaje en la aplicación para móviles. Ahora debería estar en la página **[!UICONTROL Revisión para activar]** de la campaña.
   >
   >![revisar y activar](/help/summit/l820-lab-workbook/assets/3-1-4-1-review-and-activate.png)
   >
   > Aquí puede ver un resumen completo del mensaje.
   >
   > *Tome nota del valor personalizado que utilizó como regla de déclencheur. Este valor se utilizará para activar el mensaje en la aplicación. El valor que se utilizó se encuentra en el área resaltada de la página de resumen.*

   >[!NOTE]
   >El déclencheur actual para el mensaje en la aplicación es el evento predeterminado **Application launch se produce**, lo que significa que el mensaje en la aplicación se activa cuando se inicia la aplicación. Puede ver esto en la **[!UICONTROL sección de horario]**.

5. Si ha terminado de revisar la campaña, pulse el botón Activar para publicarla.
   <br>
   ![activar](/help/summit/l820-lab-workbook/assets/3-1-4-2-activate.png)


>[!SUCCESS]
>
> Ahora debería ver el panel Campañas. Busque la campaña desplazándose o utilizando la función de búsqueda. Cuando la campaña cambia de estado a **[!UICONTROL Activa]** (~1 min), la campaña se ha publicado.
>
> ![Campaña publicada](/help/summit/l820-lab-workbook/assets/3-1-3-2-published-campaign.png)
>


## Ejercicio 2.4 Déclencheur del mensaje móvil en la aplicación

Para actualizar la carga útil y descargar la campaña recién publicada:

1. En tu dispositivo móvil, cierra completamente la aplicación Fréscopa.
2. Vuelva a abrir la aplicación Fréscopa.
3. Ahora, vaya a la pestaña Ejercicio en la aplicación.

   ![Botón de ejercicio](/help/summit/l820-lab-workbook/assets/3-2-3-app-exercise-button.png)

4. En el campo de texto, escriba el valor de déclencheur personalizado que definió en la campaña. A continuación, pulse Enviar.


   ![modificar](/help/summit/l820-lab-workbook/assets/3-2-2-1-app-condition.PNG){width="250" align="center" zoomable="yes"}

>[!SUCCESS]
>
>Al hacer clic en enviar, activó manualmente un déclencheur y la notificación en la aplicación que creó apareció:
>
>![Mensaje en la aplicación](/help/summit/l820-lab-workbook/assets/3-1-3-3-in-app-message.png)
>
> *Si tiene problemas al activar el mensaje, compruebe lo siguiente:*
> 
> * *En el campo Nombre del evento de su aplicación móvil, asegúrese de escribir el valor de la regla de déclencheur exactamente como lo tenía en la campaña.*
> * *Asegúrese de que el uso de mayúsculas es correcto y de que no dispone de espacios iniciales o finales.*
> * *Puede buscar el valor de regla de déclencheur que utilizó si vuelve a la página de revisión de Campaign haciendo clic en Volver a la campaña en el panel de campañas.*

Acaba de crear y publicar su primer mensaje en la aplicación de Journey Optimizer.


## Ejercicio extra: duplicar campaña y previsualizar en el dispositivo

Las características **Duplicar campaña** y **Vista previa en el dispositivo** son funcionalidades predeterminadas que le permiten duplicar sus campañas y probar y revisar los mensajes en la aplicación directamente en su dispositivo antes de activarlos. En este ejercicio aprenderá a utilizar esta función y previsualizará el mensaje que creó en el ejercicio 3.1.

1. Abra la campaña que acaba de crear haciendo clic en el nombre de la campaña en la página del panel Campañas para abrirla. Esto lo llevará de regreso a la página **[!UICONTROL Revisar campaña]**.
1. Presione el botón **[!UICONTROL Duplicar]**. Se abrirá una nueva solicitud para asignar un nombre a la nueva campaña que se está duplicando. Agregue un nuevo nombre que recuerde fácilmente o que utilice el nombre predeterminado donde **[!DNL _copy]** se agrega de manera predeterminada.

   ![campaña duplicada](/help/summit/l820-lab-workbook/assets/3-2-duplicate-campaign.png)

1. Una vez que pulse el botón de duplicado, se creará la campaña duplicada y se le redirigirá al panel de campañas.
1. Una vez duplicada la campaña, abra la nueva campaña.

1. Puede acceder a la función Vista previa en el dispositivo en la página **[!UICONTROL Revisión de campaña]** o en el paso **[!UICONTROL Autor de la campaña]**.

   ![vista previa en el botón del dispositivo](/help/summit/l820-lab-workbook/assets/3-3-1-1-preview-on-device-button.png)
   <br>

1. A continuación, haga clic en el **[!UICONTROL botón de inicio]** desde la pantalla de conexión al dispositivo.

   ![botón de inicio](/help/summit/l820-lab-workbook/assets/3-3-1-2-connect-to-device-start.png)
   <br>

1. Introduzca la URL base que se ha configurado para iniciar la aplicación Fréscopa: `dxdemo://`

   ![url de vista previa](/help/summit/l820-lab-workbook/assets/3-3-1-3-preview-url.png)

   <br>

1. Siga las instrucciones que aparecen en la pantalla:
   1. Escanee el código QR con su dispositivo móvil, y la aplicación Fréscopa se abre con una pantalla que le permite introducir un pin mostrado.
   2. Introduzca el pin que se muestra en AJO en la pantalla Assurance de su dispositivo y haga clic en el botón Connect que aparece en la parte inferior derecha una vez que haya introducido el pin.


   ![introducir anclaje](/help/summit/l820-lab-workbook/assets/3-3-1-5-enter-pin.PNG){width="250" align="center" zoomable="yes"}
   <br>
1. Esta ventana emergente aparece en la pantalla del equipo

   ![elemento emergente](/help/summit/l820-lab-workbook/assets/3-3-pop-up.png)

1. Haga clic en el botón Listo. Esto cerrará el cuadro de diálogo y el teléfono estará conectado a la Vista previa en el dispositivo.


>[!SUCCESS]
>
> El mensaje en la aplicación aparecerá en el dispositivo.
>
> *Una vez conectado, el mensaje en la aplicación debería mostrarse cada vez que hagas clic en el botón **[!UICONTROL Vista previa en el dispositivo]**.

## Recursos adicionales

**Vídeos explicativos:**

* [Creación de una campaña en la aplicación](/help/channels/create-an-in-app-campaign.md)
* [Creación de un mensaje en la aplicación](/help/channels/author-in-app-messages.md)

**Documentación del producto:**

* [Introducción al canal en la aplicación](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/in-app/get-started-in-app)
* [Crear un mensaje en la aplicación móvil](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/in-app/create-in-app)
* [Diseño del contenido en la aplicación](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/in-app/design-in-app)
* [Compruebe y envíe su notificación en la aplicación](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/in-app/send-in-app)
