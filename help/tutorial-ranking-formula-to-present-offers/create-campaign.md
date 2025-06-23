---
title: Creación de una campaña
description: Descubra cómo una campaña de AJO conecta audiencias, políticas de decisión y canales para ofrecer ofertas personalizadas en el momento adecuado en todos los puntos de contacto de los clientes.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18188
exl-id: deb16dd5-23cd-495a-ac91-d22fd77f49bd
source-git-commit: 640faaf9a316b2ab3e2e7774b2c30612cf1b1dbe
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 0%

---

# Creación de una campaña

Para enviar ofertas personalizadas a los usuarios en la página web, se creó una campaña en Adobe Journey Optimizer y se configuró con el canal correcto, el canal web. Esta configuración garantiza que las ofertas se entreguen mediante decisiones en tiempo real a los usuarios que interactúen con el sitio web.

Dentro de esta campaña, se ha definido una política de decisión para controlar cómo se seleccionan las ofertas. La política de decisión incluye una estrategia de selección, que consiste en:

Una colección de elementos de oferta (por ejemplo, en función del código postal o los ingresos),

Reglas de aceptación que determinan qué ofertas se aplican a un usuario y

Una fórmula de clasificación que asigna puntuaciones a ofertas aptas para priorizar las más relevantes.

Cuando un usuario que ha iniciado sesión visita el sitio, se envía una solicitud de personalización a AJO. En función de la identidad vinculada del usuario y los atributos de perfil (como código postal e ingresos anuales), la política de decisión evalúa todas las ofertas disponibles. Aplica la estrategia de selección y la lógica de clasificación para determinar la mejor coincidencia.

El resultado es un conjunto de ofertas personalizado, devuelto como contenido de HTML y mostrado al usuario en un carrusel en el sitio web, lo que crea una experiencia personalizada sin problemas en tiempo real.


## Pasos de alto nivel para crear una campaña en AJO

1. **Crear una configuración de canal**\
   Defina dónde y cómo aparecen las ofertas (por ejemplo, una página web con experiencia basada en código).
   - Inicie sesión en Recorrido Optimizer
Vaya a _&#x200B;**Administración ->Canales->Crear configuración de canal**&#x200B;_
   - **Nombre**: `finwise-web-personalization`\
     Identifica esta configuración para la entrega de ofertas web personalizadas de FinWise.

   - **Tipo de experiencia**: `Code-based experience`\
     Las ofertas no se insertan directamente en el DOM. En su lugar, AJO devuelve HTML sin procesar que se analiza mediante JavaScript personalizado.

   - **Plataforma**: `Web`\
     Dirigido específicamente a los navegadores web. No hay canales móviles habilitados.


   - **URL de la página**: `http://localhost:3000/formula.html`\
     El canal está configurado para una página de prueba específica utilizada durante el desarrollo.

   - **Ubicación en la página**: `offers-div`\
     Las ofertas devueltas se analizan dinámicamente y se representan en este contenedor mediante la lógica de front-end.

   - **Formato De Contenido**: `HTML`\
     Las ofertas se entregan como fragmentos de HTML sin procesar, lo que permite un control total sobre cómo se diseñan, filtran y muestran.


2. **Iniciar una nueva campaña**\
   Vaya a la sección Campañas y cree una nueva campaña de marketing programada. Asigne un nombre adecuado a la campaña.


3. **Agregar acción**\
   Vaya a la pestaña _&#x200B;**Acciones**&#x200B;_
Añada una acción de experiencia basada en código y vincule la acción a una configuración de canal creada anteriormente.



4. **Audiencia**\
   Vaya a la pestaña _&#x200B;**Audiencia**&#x200B;_
Todos los visitantes (predeterminado).

   Tipo de identidad: ECID (Experience Cloud ID)
Esta configuración utiliza el ECID como identidad principal para reconocer usuarios. Cuando se establece la vinculación de identidad, ECID está vinculado a CRM ID para Personalized Targeting. Seleccione o cree una política de decisión que defina la lógica de oferta.

5. **Directiva de decisión**


   La acción está vinculada a una **Directiva de decisión** que define cómo se seleccionan las ofertas y cuántas ofertas se devuelven para su visualización. Esta directiva usa una **estrategia de selección** que se creó anteriormente en el tutorial.

   Para insertar la directiva de decisión, haga clic en **_Editar contenido_** en la ficha _&#x200B;**Acciones**&#x200B;_ y, a continuación, haga clic en **_Editar código_** para abrir el editor de personalización.

   Seleccione el icono _&#x200B;**Directiva de decisión**&#x200B;_ a la izquierda y haga clic en el botón **Agregar directiva de decisión** para abrir la pantalla **Crear directiva de decisión**. Proporcione un nombre significativo a la política de decisión y seleccione el número de elementos que debe devolver la política de decisión. El valor predeterminado es 1.
Haga clic en **_siguiente_**, agregue la estrategia de selección creada en el paso anterior a la directiva de decisión y haga clic en **siguiente** para completar el proceso de creación de la directiva de decisión. Asegúrese de seleccionar la oferta de reserva adecuada.

6. **Insertar directiva de decisión**

   Inserte la directiva de decisión recién creada haciendo clic en el botón _&#x200B;**Insertar directiva**&#x200B;_. Esto inserta un bucle for en el editor de personalización, en el lado derecho.
Coloque el cursor entre el bucle each de la línea dos e inserte offerText navegando hasta la oferta explorando en profundidad `tenant name`

   Directiva de decisión insertada en el editor de personalización

   ![editor de personalización](assets/personalization-editor.png)



   El código Handlebars recorre las ofertas devueltas por una directiva de decisión específica en Adobe Journey Optimizer y crea un `<div>` para cada oferta. Cada `<div>` utiliza un atributo de etiquetas de datos con el nombre interno de la oferta para ayudar al grupo de carrusel y organizar las ofertas por categoría para facilitar la navegación. El contenido dentro de cada `<div>` muestra el texto de oferta personalizado, lo que permite una presentación dinámica y visualmente segmentada de varias ofertas.

7. **Guardar la campaña**

   Guarde la campaña haciendo clic en el botón _&#x200B;**Revisar para activar**&#x200B;_


