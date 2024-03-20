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
source-git-commit: c509c768d07984d07ed2ec65634e000c54bb6ff1
workflow-type: tm+mt
source-wordcount: '1395'
ht-degree: 0%

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

   ![Pantalla de inicio](/help/summit/l820-lab-workbook/assets/2-1-1-ajo-sign-in.png)
   <br>
3. Puede omitir las dos pantallas siguientes:
   <br>
   ![Número de teléfono](/help/summit/l820-lab-workbook/assets/2-1-3-ajo-add-phone.png)
   <br>
   ![Ventana emergente de personalización](/help/summit/l820-lab-workbook/assets/2-1-4-ajo-personalization-pop-up.png)


>[!SUCCESS]
>
>Debe iniciar sesión en Journey Optimizer y acceder a la página principal de:
>
>![Página principal de AJO](/help/summit/l820-lab-workbook/assets/2-1-5-ajo-homepage.png)


## Ejercicio 2.2 Creación de una campaña móvil en la aplicación

En este ejercicio, crea una campaña de mensajería en la aplicación, que se activa al abrir la aplicación.

1. En Journey Optimizer, en el panel de navegación izquierdo, seleccione **[!UICONTROL Campañas]**.

1. Clic **[!UICONTROL Crear campaña]**.

   ![Crear campaña](/help/summit/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. En el **[!UICONTROL Crear campaña]** , en la  **[!UICONTROL Acción]** , seleccione la **[!UICONTROL Mensaje en la aplicación]** casilla de verificación.

1. Desde el **[!UICONTROL Enviar a]** menú desplegable, seleccione **[!DNL Mobile]**.

1. Desde el **[!UICONTROL Superficie de aplicación]** menú desplegable, seleccione **[!DNL Frecopa Mobile App]**.

1. Haga clic en **[!UICONTROL Crear]**.

   ![Superficie de aplicación](/help/summit/l820-lab-workbook/assets/3-1-1-1-create.png)

>[!SUCCESS]
>
>Ahora debería estar en las propiedades de Campaign:
>
> ![Propiedades de Campaign](/help/summit/l820-lab-workbook/assets/3-1-1-2-campaign-properties.png)

## Ejercicio 2.3 Configuración de la campaña

### 2.3.1. [!UICONTROL Sección Propiedades]

Dé un nombre a su campaña. Asegúrese de comenzar el nombre con el número de asiento para que pueda encontrar fácilmente la campaña de nuevo.

Por ejemplo, si el número de puestos es 99:  `99 - Welcome Campaign`.

![sección de propiedades](/help/summit/l820-lab-workbook/assets/3-1-2-1-properties-section.png)

### 2.3.2 Configurar la regla de déclencheur personalizada

1. Desplácese hacia abajo hasta el **[!UICONTROL sección déclencheur]**, luego haga clic en **[!UICONTROL Editar déclencheur]**.

   ![modificar](/help/summit/l820-lab-workbook/assets/3-2-1-2-edit-triggers.png)

1. En el generador de reglas, haga clic en **[!UICONTROL Inicio de aplicación]** y en la lista desplegable, seleccione  *Datos enviados a Platform*.
   ![Enviado a la plataforma de datos](/help/summit/l820-lab-workbook/assets/trigger-drop-down-sent-to-platform.png)

1. Añada una condición haciendo clic en **[!UICONTROL Añadir condición]**.

   ![botón añadir condición](/help/summit/l820-lab-workbook/assets/3-2-1-3-add-condition.png)

1. Desde el **[!UICONTROL Seleccionar un rasgo]** menú desplegable, seleccione **[!UICONTROL Tipo de evento de XDM]**.

   ![Tipo de evento de XDM](/help/summit/l820-lab-workbook/assets/4-1-2-dropdown-xdm-event.png)

1. En el siguiente campo de texto, añada un *`<custom string value>`* que puedas recordar.

1. Para guardar el valor, haga clic en **[!UICONTROL Agregar**] `<custom string value>`.

   Este valor de cadena personalizado se utiliza más adelante para activar el mensaje.

   >[!TIP]
   > Añadir el número de asiento al valor de cadena personalizado hace que sea único y fácil de recordar.
   > 
   > Por ejemplo: `99exerciseTrigger`

   ![añadir valor de cadena de déclencheur personalizado](/help/summit/l820-lab-workbook/assets/3-1-2-2-add-custom-trigger.png)

1. Clic **[!UICONTROL Listo]** en la parte superior derecha.

>[!SUCCESS]
>
>Ahora ha definido el mensaje en la aplicación con un evento de déclencheur personalizado.
>
>![Campaña con déclencheur personalizado definido](/help/summit/l820-lab-workbook/assets/3-1-2-2-campaign-with-custom-trigger.png)


### 2.3.3 Editar el contenido del mensaje en la aplicación

En el **[!UICONTROL Acción]** , haga clic en **[!UICONTROL Editar contenido]**.

![Botón Editar contenido](/help/summit/l820-lab-workbook/assets/3-1-3-1-edit-content-button.png)

El [!UICONTROL Mensaje en la aplicación] aparece el editor, donde puede configurar el contenido de los mensajes en la aplicación.

#### 2.3.3.1 Diseño

Seleccione qué diseño debe aplicarse al mensaje.

Por ejemplo, haga clic en **[!UICONTROL Modal]** para que su mensaje en la aplicación tenga un diseño modal.

![botón modal](/help/summit/l820-lab-workbook/assets/3-1-3-2-modal-button.png)

#### 2.3.3.2 Creación del mensaje y publicación de la campaña

1. En la sección de medios, pegue la siguiente URL:  `https://t3.ftcdn.net/jpg/02/79/42/52/240_F_279425217_Hr9VBkknMr4fTpuZbxZXfcYdC7jSvGl2.jpg`
   <br>
Cuando haga clic fuera del campo de valor, la imagen debería aparecer.

   ![medios mostrados en la vista previa](/help/summit/l820-lab-workbook/assets/3-1-3-2-media.png)

2. En lo siguiente **[!UICONTROL Contenido]** , agregue su propio texto personalizado que desee que se muestre en el mensaje para **[!UICONTROL Header]** y **[!UICONTROL Cuerpo]**.

   ![Encabezado y cuerpo](/help/summit/l820-lab-workbook/assets/3-1-3-2-content.png)

3. Opciones adicionales:
   1. **Botones:**

      ![Sección Botones](/help/summit/l820-lab-workbook/assets/3-1-3-2-buttons.png)

      1. En esta sección del editor, puede personalizar el texto del botón CTA editando el campo Texto del botón.

      2. El **[!UICONTROL Evento Interact]** se utiliza para definir el valor que se pasa al SDK cuando el usuario presiona la CTA.

      3. El **[!UICONTROL Target]** se utiliza para definir adónde desea que la CTA lleve al usuario. Esto incluye direcciones URL y vínculos profundos. Por ejemplo, puede agregar este vínculo profundo a una página de producto como `dxdemo://exoticVibes`.

      4. Puede añadir botones adicionales pulsando **[!UICONTROL + Botón Agregar]**.

      5. Cuando se añade un segundo botón al mensaje, tiene la opción de cambiar el diseño del botón con el cuadro desplegable.


   2. **Formato avanzado**

      ![alternancia de formato avanzado](/help/summit/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-toggle.png)

      Al habilitar esta opción, se proporcionan opciones de personalización adicionales en el editor.

      1. Tamaño del medio
      1. Fuente
      1. Tamaño de punto
      1. Color de fuente
      1. Alineación

      ![opciones de formato avanzadas](/help/summit/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-options.png)

   3. **Pestaña Configuración**

      Al cambiar a esta pestaña y en el **[!UICONTROL Previsualizar]** , puede cambiar la sección **Vista previa de aplicación**.
      <br>\
      ![Pestaña Configuración](/help/summit/l820-lab-workbook/assets/3-1-3-1-settings-tab.png)
      <br>

      1. El **[!UICONTROL Diseño]** Esta sección le da la opción de utilizar una imagen como fondo o un color sólido.

      2. El **[!UICONTROL Mensaje]** proporciona interacciones personalizadas que se pueden habilitar para su mensaje:
         1. Gestos personalizados
         2. Adquisición de IU
         3. Adquisición de IU personalizada
         4. Tamaño personalizado
         5. Posición personalizada
         6. Animación personalizada
         7. Esquina redonda del mensaje
   <br>
4. Cuando haya terminado de crear el contenido y esté satisfecho con el mensaje, haga clic en **[!UICONTROL Revisar para activar] botón**.

   >[!SUCCESS]
   >
   > Ya ha completado la creación del mensaje en la aplicación para móviles. Ahora debería estar en la campaña **[!UICONTROL Revisar para activar]** página.
   >
   >![revisar y activar](/help/summit/l820-lab-workbook/assets/3-1-4-1-review-and-activate.png)
   >
   > Aquí puede ver un resumen completo del mensaje.
   >
   > *Tome nota del valor personalizado que utilizó como regla de déclencheur. Este valor se utilizará para activar el mensaje en la aplicación. El valor que se ha utilizado se puede encontrar en, en el área de resaltado de la página de resumen.*

   >[!NOTE]
   >El déclencheur actual para el mensaje en la aplicación es el predeterminado **Evento de inicio de aplicación**, lo que significa que el mensaje en la aplicación se activa cuando se inicia la aplicación. Puede ver esto en la **[!UICONTROL Sección Programar]**.

5. Si ha terminado de revisar la campaña, pulse el botón Activar para publicarla.
   <br>
   ![activar](/help/summit/l820-lab-workbook/assets/3-1-4-2-activate.png)


>[!SUCCESS]
>
> Ahora debería ver el panel Campañas. Busque la campaña desplazándose o utilizando la función de búsqueda. Cuando la campaña cambie el estado a **[!UICONTROL Activo]** (~1 min), la campaña se ha publicado.
>
> ![Campaña publicada](/help/summit/l820-lab-workbook/assets/3-1-3-2-published-campaign.png)
>


## Ejercicio 2.4 Déclencheur del mensaje móvil en la aplicación

Para actualizar la carga útil y descargar la campaña recién publicada:

1. En tu dispositivo móvil, cierra completamente la aplicación Fréscopa.
2. Vuelva a abrir la aplicación Fréscopa.
3. Ahora, vaya a la pestaña Ejercicio en la aplicación.

   ![Botón Ejercicio](/help/summit/l820-lab-workbook/assets/3-2-3-app-exercise-button.png)

4. En el campo de texto, escriba el valor de déclencheur personalizado que definió en la campaña. A continuación, pulse Enviar.


   ![modificar](/help/summit/l820-lab-workbook/assets/3-2-2-1-app-condition.PNG){width="250" align="center" zoomable="yes"}

>[!SUCCESS]
>
>Al hacer clic en enviar, activó manualmente un déclencheur y la notificación en la aplicación que creó apareció:
>
>![Mensaje en la aplicación](/help/summit/l820-lab-workbook/assets/3-1-3-3-in-app-message.png)
>
> *Si tiene problemas para activar el mensaje, compruebe lo siguiente:*
> 
> * *En el campo Nombre del evento de la aplicación móvil, asegúrese de escribir en el valor de la regla de déclencheur exactamente como lo tenía en la campaña.*
> * *Asegúrese de que las mayúsculas y minúsculas son correctas y de que no hay espacios iniciales o finales.*
> * *Puede buscar el valor de regla de déclencheur que utilizó si vuelve a la página de revisión de Campaign haciendo clic en Volver a la campaña en el panel de campañas.*

Acaba de crear y publicar su primer mensaje en la aplicación de Journey Optimizer.


## Ejercicio extra: duplicar campaña y previsualizar en el dispositivo

El **Duplicar campaña** y **Vista previa en el dispositivo** Las funciones de son funciones integradas que le permiten duplicar sus campañas y probar y revisar los mensajes en la aplicación directamente en el dispositivo antes de activarlos. En este ejercicio aprenderá a utilizar esta función y previsualizará el mensaje que creó en el ejercicio 3.1.

1. Abra la campaña que acaba de crear haciendo clic en el nombre de la campaña en la página del panel Campañas para abrirla. Esto lo llevará de vuelta a la **[!UICONTROL Revisar campaña]** página.
1. Pulse el botón **[!UICONTROL Botón Duplicar]**. Se abrirá una nueva solicitud para asignar un nombre a la nueva campaña que se está duplicando. Añada un nuevo nombre que recuerde fácilmente o donde utilice el nombre predeterminado **[!DNL _copy]** se añade de forma predeterminada.

   ![campaña duplicada](/help/summit/l820-lab-workbook/assets/3-2-duplicate-campaign.png)

1. Una vez que pulse el botón de duplicado, se creará la campaña duplicada y se le redirigirá al panel de campañas.
1. Una vez duplicada la campaña, abra la nueva campaña.

1. Puede acceder a la función Vista previa en el dispositivo en el **[!UICONTROL Revisión de campaña]** o en la **[!UICONTROL Autor de campaña]** paso.

   ![botón previsualizar en el dispositivo](/help/summit/l820-lab-workbook/assets/3-3-1-1-preview-on-device-button.png)
   <br>

1. Haga clic en el botón **[!UICONTROL botón inicio]** en la pantalla conectar con el dispositivo.

   ![botón inicio](/help/summit/l820-lab-workbook/assets/3-3-1-2-connect-to-device-start.png)
   <br>

1. Introduzca la URL base que se ha configurado para iniciar la aplicación Fréscopa: `dxdemo://`

   ![url de previsualización](/help/summit/l820-lab-workbook/assets/3-3-1-3-preview-url.png)

   <br>

1. Siga las instrucciones que aparecen en la pantalla:
   1. Escanee el código QR con su dispositivo móvil, y la aplicación Fréscopa se abre con una pantalla que le permite introducir un pin mostrado.
   2. Introduzca el pin que se muestra en AJO en la pantalla Assurance de su dispositivo y haga clic en el botón Connect que aparece en la parte inferior derecha una vez que haya introducido el pin.


   ![pin de entrada](/help/summit/l820-lab-workbook/assets/3-3-1-5-enter-pin.PNG){width="250" align="center" zoomable="yes"}
   <br>
1. Esta ventana emergente aparece en la pantalla del equipo

   ![ventana emergente](/help/summit/l820-lab-workbook/assets/3-3-pop-up.png)

1. Haga clic en el botón Listo. Esto cerrará el cuadro de diálogo y el teléfono estará conectado a la Vista previa en el dispositivo.


>[!SUCCESS]
>
> El mensaje en la aplicación aparecerá en el dispositivo.
>
> *Una vez conectado, el mensaje en la aplicación debería mostrarse cada vez que haga clic en **[!UICONTROL Vista previa en el dispositivo] botón**.*