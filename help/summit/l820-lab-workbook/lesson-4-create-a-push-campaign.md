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
exl-id: 0f82d6a5-18c0-45f2-968e-a678fc2d5768
source-git-commit: befde57252ebc12c5d6df31fde8078e4535d1261
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 2%

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

1. En Journey Optimizer, en el panel de navegación izquierdo, en la sección **[!UICONTROL ADMINISTRACIÓN DE RECORRIDO]**, seleccione **Campañas**.

1. Haga clic en **[!UICONTROL Crear campaña]**.

   ![Crear campaña](/help/summit/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. En la página **[!UICONTROL Crear campaña]**, en la sección **[!UICONTROL Acción]**, active la casilla **[!UICONTROL Notificación push]**.

1. En el menú desplegable **[!UICONTROL Superficie de la aplicación]**, seleccione *[!DNL Frecopa-Push]*.

1. Haga clic en **[!UICONTROL Crear]** para crear una campaña push.

   ![Superficie de aplicación](/help/summit/l820-lab-workbook/assets/2-3-1-2-app-surface.png)

>[!SUCCESS]
>
>Ahora debería estar en la página de propiedades de Campaign:
> ![Propiedades de la campaña ](/help/summit/l820-lab-workbook/assets/2-3-1-2-campaign-properties.png)

## Ejercicio 4.2: Configuración de la campaña

En esta página, puede configurar las propiedades, la audiencia, las acciones y la programación de la campaña.

### 4.2.1 [!UICONTROL Sección Propiedades]

Dé un nombre a su campaña. Asegúrese de comenzar el nombre con el número de asiento para que pueda encontrar fácilmente la campaña cuando la busque.

Por ejemplo, si el número de puesto es 99: `99 - 10% Discount Campaign`.

### 4.2.2 **[!UICONTROL Sección de audiencias]**

1. En la sección de audiencia, haga clic en **[!UICONTROL Seleccionar audiencia]**.

   ![sección de audiencia](/help/summit/l820-lab-workbook/assets/2-3-2-5-audience-section.png)

1. En la pantalla **[!UICONTROL Seleccionar audiencia]**, busque la audiencia:

   **Laboratorio - Puesto`your seat number`**

1. Seleccione la audiencia y haga clic en **[!UICONTROL Guardar]**.

   ![selección de audiencia](/help/summit/l820-lab-workbook/assets/2-3-2-7-select-audience.png)

### 4.2.3 Editar el contenido de la notificación push

En este ejercicio, se diseña y personaliza la notificación push.

1. En la sección **[!UICONTROL Acción]**, haga clic en el botón **[!UICONTROL Editar contenido]**.

   ![Botón Editar contenido](/help/summit/l820-lab-workbook/assets/2-3-action-edit-content-button.png)

1. En la siguiente pantalla, dependiendo del dispositivo móvil que tenga, seleccione la pestaña [!DNL iOS™] o [!DNL Android™] para configurar el contenido.

>[!BEGINTABS]

>[!TAB iOS]

![Ficha iOS](/help/summit/l820-lab-workbook/assets/2-3-ios-tab.png)

>[!TAB Android]

![Ficha Android](/help/summit/l820-lab-workbook/assets/2-3-android-tab.png)

>[!ENDTABS]

#### 4.2.3.1 [!UICONTROL Escribir mensaje] sección

1. **Escriba su mensaje:** No dude en agregar el texto que desee. Estos son ejemplos que puede utilizar:

   * Título: `Get 10% off today!`
   * Texto del cuerpo: `Today only! Get 10% off on your House Blend coffee purchase!`

     ![Escribir mensaje](/help/summit/l820-lab-workbook/assets/2-3-compose-message.png)

#### 4.2.3.2 Cambiar el comportamiento al hacer clic del mensaje para **abrir una página de producto**

1. En la sección **[!UICONTROL Comportamiento al hacer clic]**, seleccione **[!UICONTROL Vínculo profundo]** en la lista desplegable **[!UICONTROL Comportamiento del clic en el cuerpo]**.

1. Copie y pegue la siguiente dirección URL en el **campo URL**:

   `dxdemo://exoticVibes`

   ![vínculo profundo](/help/summit/l820-lab-workbook/assets/2-3-deeplink.png)

#### 4.2.3.3 Añadir una imagen al mensaje

1. En la sección **[!UICONTROL Agregar medios]**, haga clic en **[!UICONTROL Agregar medios]**.

   ![agregar botones multimedia](/help/summit/l820-lab-workbook/assets/2-3-3-3-add-media-buttons.png)

1. En la pantalla **[!UICONTROL Seleccionar Assets]**, en el panel de navegación izquierdo, abre la **carpeta Fréscopa** y selecciona una imagen de esa carpeta.

   Por ejemplo: `HouseBlend.png`

1. Haga clic en la imagen y luego en el botón **[!UICONTROL Seleccionar]** para agregar la imagen a la notificación de inserción.

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

1. Haga clic en **cuadro de diálogo de personalización** junto al campo **[!UICONTROL Cuerpo]**.

   ![botón de personalización](/help/summit/l820-lab-workbook/assets/2-3-personalization-button.png)

1. En la pantalla **cuadro de diálogo de personalización**, coloque el cursor donde desee agregar el nombre en el texto.

1. Asegúrese de que los **atributos de perfil** estén seleccionados en el panel de navegación izquierdo.

   ![Atributo de perfil](/help/summit/l820-lab-workbook/assets/2-3-personalize-body-profile-attributes.png)

1. En el **campo de búsqueda**, busque: `first name`.

1. Haga clic en **+** junto al **Nombre (atributos de perfil>Persona>Nombre completo)** para agregar el campo de personalización al texto.

   ![Buscar nombre](/help/summit/l820-lab-workbook/assets/2-3-personalize-search-first-name.png)

   >[!SUCCESS]
   >
   > Este es el aspecto que debería tener el texto:
   > 
   >![Token de Personalization](/help/summit/l820-lab-workbook/assets/2-3-personalization-token.png)

1. Haga clic en **[!UICONTROL Guardar]** para guardar la personalización.


   >[!SUCCESS]
   >
   > 1. En la pantalla de vista previa, haga clic en **[!UICONTROL Expandir vista]**.
   > 1. Previsualice el mensaje.
   > 
   > ![expandir vista](/help/summit/l820-lab-workbook/assets/2-3-3-expand-view.png)

+++

### 4.2.4. Revisión y activación

Si está satisfecho con el contenido del mensaje, puede activar el mensaje:

1. Haga clic en **[!UICONTROL Revisar para activar]**.

   ![botón de revisión y activación](/help/summit/l820-lab-workbook/assets/2-3-4-review-and-activate-button.png)

1. En la pantalla **[!UICONTROL Revisar para activar]**, haga clic en **[!UICONTROL Activar]**.

   ![revisar para activar la pantalla](/help/summit/l820-lab-workbook/assets/2-3-4-review-to-activate.png)

>[!SUCCESS]
> En la **página de información general de campañas**, busque su campaña y compruebe el estado.
>
> ![estado de la campaña](/help/summit/l820-lab-workbook/assets/2-3-push-completed.png)
> 
> El estado cambia de Procesamiento a Activo, a Completado: esto puede tardar un par de minutos.
> Una vez que el estado haya cambiado a completado:
>
> ![resultados de inserción](/help/summit/l820-lab-workbook/assets/2-3-push-notification-result.png)

## Recursos adicionales

**Vídeos explicativos:**

* [Configuración y envío de una campaña push](/help/channels/create-a-push-campaign.md)

**Documentación del producto:**

* [Introducción a las notificaciones push](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/get-started-push)
* [Crear una notificación push](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/create-push)
* [Diseñar una notificación push](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/design-push)
* [Comprueba y envía tu notificación push](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/send-push)
