---
title: 'Lección 4: Creación de una campaña push'
description: Revise los datos de perfil y aprenda a crear y enviar audiencias mediante una notificación push en Journey Optimizer.
feature: Push
role: User
level: Intermediate
doc-type: Tutorial
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-14980
source-git-commit: c590b47ad3dfc54badbac0d8fcaff6b9dd053cc1
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 0%

---


# Lección 4: Creación de una campaña push

En el ejercicio anterior, eras un entusiasta del café, un cliente de Fréscopa. Interactuó con la marca a través de su sitio web y la aplicación Fréscopa y recibió muchos mensajes transaccionales. Estos mensajes se activan mediante la interacción del usuario con el sitio web o la aplicación.

En este ejercicio, pondrá su sombrero de experto en marketing e implementará una campaña de marketing para Frésopa, que utilizará el canal push para dirigirse a los usuarios de la aplicación Fréscopa. Las notificaciones push se utilizan para mantener informados a los usuarios de la aplicación, incluso cuando no están utilizando la aplicación, pero también para reactivarlos. El objetivo es incentivar al cliente para que compre la mezcla de la casa, ofreciendo un 10% de descuento.

## Objetivos de aprendizaje

* Obtenga información sobre cómo crear una campaña push.
* Obtenga información sobre cómo diseñar un mensaje push.

<br>

## Ejercicio 4.1: crear una campaña push

En este ejercicio, crea la campaña push, diseña y personaliza la notificación push y la envía a su propio dispositivo.

1. En Journey Optimizer, en el panel de navegación izquierdo, en el **[!UICONTROL ADMINISTRACIÓN DE RECORRIDO]** , seleccione **Campañas**.

1. Clic **[!UICONTROL Crear campaña]**.

   ![Crear campaña](/help/summit/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. En el **[!UICONTROL Crear campaña]** , en la  **[!UICONTROL Acción]** , seleccione la **[!UICONTROL Notificación push]** casilla de verificación.

1. Desde el **[!UICONTROL Superficie de aplicación]** menú desplegable, seleccione *[!DNL Frecopa-Push]*.

1. Clic **[!UICONTROL Crear]** para crear una campaña push.

   ![Superficie de aplicación](/help/summit/l820-lab-workbook/assets/2-3-1-2-app-surface.png)

>[!SUCCESS]
>
>Ahora debería estar en la página de propiedades de Campaign:
> ![Propiedades de Campaign](/help/summit/l820-lab-workbook/assets/2-3-1-2-campaign-properties.png)

## Ejercicio 4.2: Configuración de la campaña

En esta página, puede configurar las propiedades, la audiencia, las acciones y la programación de la campaña.

### 4.2.1 [!UICONTROL Sección Propiedades]

Dé un nombre a su campaña. Asegúrese de comenzar el nombre con el número de asiento para que pueda encontrar fácilmente la campaña cuando la busque.

Por ejemplo, si el número de puestos es 99: `99 - 10% Discount Campaign`.

### 4.2.2 **[!UICONTROL Sección Audiencia]**

1. En la sección de audiencia, haga clic en **[!UICONTROL Seleccionar audiencia]**.

   ![sección de audiencia](/help/summit/l820-lab-workbook/assets/2-3-2-5-audience-section.png)

1. En el **[!UICONTROL Seleccionar audiencia]** , busque la audiencia:

   **Lab - Asiento`your seat number`**

1. Seleccione la audiencia y haga clic en **[!UICONTROL Guardar]**.

   ![selección de audiencia](/help/summit/l820-lab-workbook/assets/2-3-2-7-select-audience.png)

### 4.2.3 Editar el contenido de la notificación push

En este ejercicio, se diseña y personaliza la notificación push.

1. En el **[!UICONTROL Acción]** , haga clic en **[!UICONTROL Editar contenido] botón**.

   ![Botón Editar contenido](/help/summit/l820-lab-workbook/assets/2-3-action-edit-content-button.png)

1. En la pantalla siguiente, según el dispositivo móvil que tenga, seleccione la opción [!DNL iOS™] o [!DNL Android™] para configurar el contenido.

>[!BEGINTABS]

>[!TAB iOS]

![Pestaña iOS](/help/summit/l820-lab-workbook/assets/2-3-ios-tab.png)

>[!TAB Android]

![Pestaña Android](/help/summit/l820-lab-workbook/assets/2-3-android-tab.png)

>[!ENDTABS]

#### 4.2.3.1 [!UICONTROL Escribir mensaje] sección

1. **Componga el mensaje:** No dude en añadir cualquier texto que desee. Estos son ejemplos que puede utilizar:

   * Título: `Get 10% off today!`
   * Texto independiente: `Today only! Get 10% off on your House Blend coffee purchase!`

     ![Escribir mensaje](/help/summit/l820-lab-workbook/assets/2-3-compose-message.png)

#### 4.2.3.2 Cambiar el comportamiento al hacer clic del mensaje a **abrir una página de producto**

1. En el **[!UICONTROL Comportamiento al hacer clic]** , seleccione **[!UICONTROL Vínculo profundo]** desde el **[!UICONTROL Comportamiento de clic en cuerpo]** desplegable.

1. Copie y pegue la siguiente dirección URL en **Campo de URL**:

   `dxdemo://exoticVibes`

   ![vínculo profundo](/help/summit/l820-lab-workbook/assets/2-3-deeplink.png)

#### 4.2.3.3 Añadir una imagen al mensaje

1. En el **[!UICONTROL Añadir medios]** , haga clic en **[!UICONTROL Añadir medios]**.

   ![añadir botones multimedia](/help/summit/l820-lab-workbook/assets/2-3-3-3-add-media-buttons.png)

1. En el **[!UICONTROL Seleccionar recursos]** pantalla, en el panel de navegación izquierdo, abra **Carpeta Fréscopa** y seleccione una imagen de esa carpeta.

   Por ejemplo: `HouseBlend.png`

1. Haga clic en la imagen y en **[!UICONTROL Seleccionar] botón** para añadir la imagen a la notificación push.

   ![seleccionar imagen](/help/summit/l820-lab-workbook/assets/2-3-3-3-select-image.png)

   >[!SUCCESS]
   >
   > 1. En la pantalla de vista previa, haga clic en **[!UICONTROL Expandir vista]**.
   > 1. Previsualice el mensaje.
   > <br>
   >
   > ![expandir vista](/help/summit/l820-lab-workbook/assets/2-3-3-expand-view.png)

### Ejercicio extra

Si ha completado esta parte del ejercicio y todavía tiene tiempo, pruebe el ejercicio extra:

+++ Ejercicio extra

#### Personalice el mensaje que está enviando añadiendo el nombre del destinatario

1. Clic **diálogo de personalización** junto al **[!UICONTROL Cuerpo]** field.

   ![botón de personalización](/help/summit/l820-lab-workbook/assets/2-3-personalization-button.png)

1. En el **diálogo de personalización** , coloque el cursor donde desee añadir el nombre en el texto.

1. Asegúrese de que la variable **Atributos de perfil** están seleccionados en el panel de navegación izquierdo.

   ![Atributo de perfil](/help/summit/l820-lab-workbook/assets/2-3-personalize-body-profile-attributes.png)

1. En el **Campo de búsqueda**, busque: `first name`.

1. Clic **+** junto al **Nombre (Atributos de perfil>Persona>Nombre completo)** para añadir el campo de personalización al texto.

   ![Buscar el nombre](/help/summit/l820-lab-workbook/assets/2-3-personalize-search-first-name.png)

   >[!SUCCESS]
   >
   > Este es el aspecto que debería tener el texto:
   > 
   >![Token de personalización](/help/summit/l820-lab-workbook/assets/2-3-personalization-token.png)

1. Clic **[!UICONTROL Guardar]** para guardar la personalización.


   >[!SUCCESS]
   >
   > 1. En la pantalla de vista previa, haga clic en **[!UICONTROL Expandir vista]**.
   > 1. Previsualice el mensaje.
   > 
   > ![expandir vista](/help/summit/l820-lab-workbook/assets/2-3-3-expand-view.png)

+++

### 4.2.4. Revisión y activación

Si está satisfecho con el contenido del mensaje, puede activar el mensaje:

1. Clic **[!UICONTROL Revisar para activar]**.

   ![botón revisar y activar](/help/summit/l820-lab-workbook/assets/2-3-4-review-and-activate-button.png)

1. En el **[!UICONTROL Revisar para activar]** , haga clic en **[!UICONTROL Activar]**.

   ![revisar para activar la pantalla](/help/summit/l820-lab-workbook/assets/2-3-4-review-to-activate.png)

>[!SUCCESS]
> En el **Página de información general de campañas**, busque la campaña y compruebe el estado.
>
> ![estado de campaña](/help/summit/l820-lab-workbook/assets/2-3-push-completed.png)
> 
> El estado cambia de Procesamiento a Activo, a Completado: esto puede tardar un par de minutos.
> Una vez que el estado haya cambiado a completado:
>
> ![resultados push](/help/summit/l820-lab-workbook/assets/2-3-push-notification-result.png)


**¡Gracias!**

Gracias por su participación. Por favor, envíenos sus comentarios, sobre cómo lo hicimos y si el laboratorio cumplió con sus expectativas, completando la encuesta Lab 820 Session en la aplicación Summit.
