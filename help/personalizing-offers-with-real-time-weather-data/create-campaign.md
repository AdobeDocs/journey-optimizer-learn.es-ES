---
title: Creación de una campaña
description: Descubra cómo una campaña de AJO conecta audiencias, políticas de decisión y canales para ofrecer ofertas personalizadas en el momento adecuado en todos los puntos de contacto de los clientes.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
source-git-commit: b0b0eba099324d64940a87ecdad872db51dceb55
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 1%

---

# Creación de una campaña

Para enviar ofertas personalizadas a los usuarios en la página web, se creó una campaña en Adobe Journey Optimizer y se configuró con el canal correcto, el canal web. Esta configuración garantiza que las ofertas se entreguen mediante decisiones en tiempo real a los usuarios que interactúen con el sitio web.

Dentro de esta campaña, se ha definido una política de decisión para controlar cómo se seleccionan las ofertas. La política de decisión incluye una estrategia de selección, que consiste en:

- Una colección de elementos de oferta (por ejemplo, basados en etiquetas relacionadas con el tiempo),
- Reglas de aceptación que determinan qué ofertas se aplican a un usuario y
- Una fórmula de clasificación que asigna puntuaciones a ofertas aptas para priorizar las más relevantes.

Cuando un usuario visita el sitio web, el sistema detecta su ubicación y obtiene la temperatura actual mediante una API meteorológica. Estos datos de temperatura se envían a Adobe Experience Platform a través de la SDK web (Alloy). En función de estos datos contextuales en tiempo real, Adobe Journey Optimizer evalúa las ofertas predefinidas que están etiquetadas para condiciones meteorológicas específicas, como caliente, suave o frío. La oferta más relevante mediante la estrategia de selección y la fórmula de clasificación se procesa automáticamente en la página web utilizando el motor de decisión de Adobe, lo que garantiza que el usuario reciba contenido personalizado alineado con el clima actual en su área.


## Pasos de alto nivel para crear una campaña en AJO

- Crear una configuración de canal
   - Defina dónde y cómo aparecen las ofertas (por ejemplo, una página web con experiencia basada en código).
   - Inicie sesión en Recorrido Optimizer
   - Vaya a _&#x200B;**Administración ->Canales->Crear configuración de canal**&#x200B;_
   - **Nombre**: `offers-by-weather`\
     Identifica esta configuración para la entrega de ofertas web personalizadas.
   - **Plataforma**: `Web`\
     Dirigido específicamente a los navegadores web. No hay canales móviles habilitados.
   - **Tipo de experiencia**:

     `Code-based experience`\
     Las ofertas no se insertan directamente en el DOM. En su lugar, AJO devuelve HTML sin procesar que se analiza mediante JavaScript personalizado.
   - **URL de la página**: `https://gbedekar489.github.io/weather/weather-offers.html`\
     El canal está configurado para una página de prueba específica utilizada durante el desarrollo.
   - **Ubicación en la página**: `offerContainer`\
     Las ofertas devueltas se analizan dinámicamente y se representan en este contenedor mediante la lógica de front-end.

   - **Formato De Contenido**: `HTML`\
     Las ofertas se entregan como fragmentos de HTML sin procesar, lo que permite un control total sobre cómo se diseñan, filtran y muestran.


- **Iniciar una nueva campaña**
   - Vaya a la sección Campañas y cree una nueva campaña de marketing programada. Asigne un nombre adecuado a la campaña.
   - **Agregar acción**
      - Añada una acción de experiencia basada en código y vincule la acción a una configuración de canal creada anteriormente.



   - **Audiencia**
      - Todos los visitantes (predeterminado).
      - Tipo de identidad: ECID (Experience Cloud ID)
Esta configuración utiliza el ECID como identidad principal para reconocer usuarios.


- **Crear directiva de decisión**
   - La acción está vinculada a una **Directiva de decisión** que define cómo se seleccionan las ofertas y cuántas ofertas se devuelven para su visualización. Esta directiva usa una **estrategia de selección** que se creó anteriormente en el tutorial.
   - Para insertar la directiva de decisión, haga clic en **_Editar contenido_** en las secciones Acciones y luego haga clic en **_Editar código_** para abrir el editor de personalización.
   - Seleccione el icono _&#x200B;**Directiva de decisión**&#x200B;_ a la izquierda y haga clic en el botón **Agregar directiva de decisión** para abrir la pantalla **Crear directiva de decisión**. Proporcione un nombre significativo a la política de decisión y seleccione el número de elementos que debe devolver la política de decisión. El valor predeterminado es 1.
   - Haga clic en **_siguiente_**, agregue la estrategia de selección creada en el paso anterior a la directiva de decisión y haga clic en **siguiente** para completar el proceso de creación de la directiva de decisión. No se han asociado ofertas de reserva con la política de decisión.



- **Insertar directiva de decisión**
  ![editor de personalización](assets/personalization-editor.png)

  Inserte la directiva de decisión recién creada haciendo clic en el botón _&#x200B;**Insertar directiva**&#x200B;_. Esto inserta un bucle for en el editor de personalización, en el lado derecho.
Coloque el cursor entre el bucle each de la línea dos e inserte offerText navegando hasta la oferta explorando en profundidad `tenant name`

  El código Handlebars recorre las ofertas devueltas por una política de decisión específica en Adobe Journey Optimizer.
  ![barra de control](assets/handlebar-code.png)

- **Publicar la campaña**\
  Active la campaña para empezar a enviar ofertas personalizadas en tiempo real.


