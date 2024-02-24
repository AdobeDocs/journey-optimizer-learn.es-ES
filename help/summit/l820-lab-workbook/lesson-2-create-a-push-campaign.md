---
title: 'Lección 2: Creación de una campaña push'
description: Revise los datos de perfil y aprenda a crear y enviar audiencias como notificaciones push en Journey Optimizer.
feature: Push
role: User
level: Intermediate
doc-type: Tutorial
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-14980
thumbnail: KT-14980.jpeg
source-git-commit: fa9fbe66fe020dd1cfb21cfabfce541fa9510293
workflow-type: tm+mt
source-wordcount: '818'
ht-degree: 0%

---


# Lección 2: Creación de una campaña push

En esta lección, revisará el perfil y los atributos de perfil relacionados que se crearon al registrarse en el sitio web de Frescopa y completar la encuesta. A continuación, aprenderá a crear una campaña push y a enviar un mensaje.

## Objetivos de aprendizaje

* Definición de perfiles y atributos de perfil
* Obtenga información sobre cómo crear una campaña push
* Aprenda a diseñar y personalizar un mensaje push

## Ejercicios

>[!BEGINTABS]

>[!TAB Ejercicio 2.1: inicio de sesión en Journey Optimizer]

### Ejercicio 2.1: inicio de sesión en Journey Optimizer

1. Abrir [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-ajo-lab/journey-optimizer/home){target="_blank"}
2. Inicie sesión con los siguientes detalles:

   **Nombre de usuario:**   L820+**su número de asiento**@adobeeventlab.com
   **Contraseña:**   ¡Adobe 2024!

   ![Pantalla de inicio](/help/summit/l820-lab-workbook/assets/2-1-1-ajo-sign-in.png)

3. Puede omitir las dos pantallas siguientes:

   ![Número de teléfono](/help/summit/l820-lab-workbook/assets/2-1-3-ajo-add-phone.png)

   ![Ventana emergente de personalización](/help/summit/l820-lab-workbook/assets/2-1-4-ajo-personalization-pop-up.png)


>[!SUCCESS]
>
>Debe iniciar sesión en Journey Optimizer y acceder a la página principal de:
>
>![Página principal de AJO](/help/summit/l820-lab-workbook/assets/2-1-5-ajo-homepage.png)

>[!TAB Ejercicio 2.2: revisar el perfil]

### Ejercicio 2.2: revisar el perfil

1. En la navegación izquierda de Adobe Journey Optimizer, navegue hasta **[!UICONTROL CLIENTE]** -> **[!UICONTROL Perfiles]**.
2. En el **[!UICONTROL Perfiles]** página de información general, vaya a [!UICONTROL Examinar] pestaña.
3. Desde el **[!UICONTROL Área de nombres de identidad]** menú desplegable, seleccione **[!UICONTROL Correo electrónico]**
   ![Seleccionar área de nombres de identidad](/help/summit/l820-lab-workbook/assets/2-2-1-select-identity-namespace.png)
4. Haga clic en **[!UICONTROL ID de perfil]** vínculo para acceder a los datos de perfil
   ![ID de perfil](/help/summit/l820-lab-workbook/assets/2-2-2-profiles.png)
5. En la página de detalles del perfil: revise la información:

Todos los datos se han recopilado a través de la página web móvil y la aplicación móvil y se han añadido al perfil. Está disponible para su uso para personalizar los mensajes que envía.

1. En el **[!UICONTROL Abono de segmentos]** pestaña:
   1. Comprobar el abono a audiencia
   2. Asegúrese de que el perfil forme parte de una audiencia denominada:

      **Asiento de laboratorio *su número de asiento*** (por ejemplo, Lab-Seat)

      ![Abono a audiencia](/help/summit/l820-lab-workbook/assets/2-2-3-audience-membership.png)

>[!NOTE]
>
>Se necesita la audiencia de laboratorio en los próximos ejercicios. Garantizará que solo envía mensajes push y notificaciones en la aplicación a su propio dispositivo.
>
>Si ve que es miembro de una audiencia con un número de asiento diferente al suyo, podría recibir mensajes del asistente de laboratorio en ese asiento.

>[!TAB Ejercicio 2.3: crear una campaña push]

### Ejercicio 2.3: crear una campaña push

En este ejercicio, debe crear una campaña push, diseñar y personalizar la notificación push y enviarla a su propio dispositivo.

#### 2.3.1: Creación de la campaña

1. En Journey Optimizer, en el panel de navegación izquierdo, seleccione Campañas.
2. Haga clic en **[!UICONTROL Crear campaña]** botón
   ![Crear campaña](/help/summit/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)
3. En el **[!UICONTROL Crear campaña]** , en la  **[!UICONTROL Acción]** , seleccione la **[!UICONTROL Notificación push] casilla de verificación
4. Desde el **[!UICONTROL Superficie de aplicación]** selección desplegable *[!DNL Frecopa-Push]*
5. Haga clic en **[!UICONTROL Crear]** botón
   ![Superficie de aplicación](/help/summit/l820-lab-workbook/assets/2-3-1-2-app-surface.png)

>[!SUCCESS]
>
>Ahora debería estar en las propiedades de Campaign:
> ![Propiedades de Campaign](/help/summit/l820-lab-workbook/assets/2-3-1-2-campaign-properties.png)

#### 2.3.2: Configuración de la campaña

En esta sección configurará las propiedades, la audiencia, las acciones y la programación de la campaña:

##### 1. [!UICONTROL Sección Propiedades]

![sección de propiedades](/help/summit/l820-lab-workbook/assets/2-3-1-4-properties-section.png)

1. Dé un nombre a su campaña. Asegúrese de comenzar el nombre con el número de asiento para que pueda encontrar fácilmente la campaña de nuevo. Por ejemplo, si el número de puestos es 99: `99 - 10% Discount Campaign`.
2. Si lo desea, puede agregar una descripción, pero no es necesaria para este ejercicio.


##### 2. **[!UICONTROL Sección Audiencia]**

![sección de propiedades](/help/summit/l820-lab-workbook/assets/2-3-2-5-audience-section.png)

1. En la sección de audiencia, haga clic en **[!UICONTROL Seleccionar audiencia]** botón.
2. En el **[!UICONTROL Seleccionar audiencia]** pantalla, buscar la audiencia **Lab - Asiento`your seat number`**. Debe ser la audiencia de Lab en la que se haya creado el perfil [!DNL Frescopa] está asignado a.
3. Seleccione la audiencia y haga clic en [!UICONTROL Guardar]

![selección de audiencia](/help/summit/l820-lab-workbook/assets/2-3-2-7-select-audience.png)

#### 2.3.3. - Editar el contenido de la notificación push

1. En el **[!UICONTROL Acción] , haga clic en [!UICONTROL Editar contenido] botón.

En esta sección diseñará y personalizará la notificación push.

1. Según el dispositivo móvil que tenga, seleccione la opción [!DNL iOS] o [!DNL Android] para configurar el contenido.

Siéntase libre de añadir cualquier texto que desee, le daremos ejemplos que puede utilizar:

1. Añada el título al campo de título:
   `10% today!`
2. Añada el texto del cuerpo:
   `Today only! Get 10% off on your House Blend coffee purchase!`
3. Personalice el texto independiente: añada el nombre del destinatario:
   1. Haga clic en **icono del cuadro de diálogo de personalización** junto al **[!UICONTROL Cuerpo]** campo
   2. En la pantalla del cuadro de diálogo de personalización ****, coloque el cursor donde desee agregar el nombre en el texto.
   3. Asegúrese de que la **Atributos de perfil** están seleccionados en el panel de navegación izquierdo.
   4. En el **Campo de búsqueda**, busque:
      `first name`
   5. En la navegación central, haga clic en **+** junto al **Nombre (Atributos de perfil>Persona>Nombre completo)** para añadir el campo de personalización al texto.
   6. Haga clic en **[!UICONTROL Guardar]** para guardar la personalización

   >[!SUCCESS]
   >
   >Este es el aspecto que debería tener el texto
   >

4. **[!UICONTROL Comportamiento al hacer clic]:**
   1. Seleccionar **[!UICONTROL Vínculo profundo]** desde el **[!UICONTROL Comportamiento de clic en cuerpo]** desplegable.
   2. Copie y pegue la siguiente dirección URL en **Campo de URL**: `dxdemo://exoticVibes`
5. **[!UICONTROL Añadir medios]:** Haga clic en **[!UICONTROL Añadir medios] botón**
   1. En el **[!UICONTROL Seleccionar recursos] , desplácese hacia abajo hasta la carpeta Frescopa>Productos y seleccione una imagen.
   2. Haga clic en la imagen y en **[!UICONTROL Seleccionar] botón** para añadir la imagen a la notificación push.

   >[!SUCCESS]
   >
   > 1. En la pantalla de vista previa, haga clic en **[!UICONTROL Expandir vista]**
   > 2. Previsualice el mensaje.
   >

#### 2.3.4. - Revisar y activar

Si está satisfecho con el contenido del mensaje, puede activar el mensaje:

1. Haga clic en **[!UICONTROL Revisar para activar] botón**.
2. En el **[!UICONTROL Revisar para activar] pantalla**, haga clic en **[!UICONTROL Activar] botón**.


>[!ENDTABS]
