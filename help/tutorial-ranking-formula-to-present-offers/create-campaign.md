---
title: Creación de una campaña
description: Descubra cómo una campaña de AJO conecta audiencias, políticas de decisión y canales para ofrecer ofertas personalizadas en el momento adecuado en todos los puntos de contacto de los clientes.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00Z
jira: KT-18188
source-git-commit: 58d2964644bc199b9db212040676d87d54f767b9
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 1%

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
   - **Nombre**: `finwise-web-personalization`\
     Identifica esta configuración para la entrega de ofertas web personalizadas de FinWise.

   - **Plataforma**: `Web`\
     Dirigido específicamente a los navegadores web. No hay canales móviles habilitados.

   - **Tipo de experiencia**: `Code-based experience`\
     Las ofertas no se insertan directamente en el DOM. En su lugar, AJO devuelve HTML sin procesar que se analiza mediante JavaScript personalizado.

   - **URL de la página**: `http://localhost:3000/formula.html`\
     El canal está configurado para una página de prueba específica utilizada durante el desarrollo.

   - **Ubicación en la página**: `offers-div`\
     Las ofertas devueltas se analizan dinámicamente y se representan en este contenedor mediante la lógica de front-end.

   - **Formato De Contenido**: `HTML`\
     Las ofertas se entregan como fragmentos de HTML sin procesar, lo que permite un control total sobre cómo se diseñan, filtran y muestran.


2. **Iniciar una nueva campaña**\
   Vaya a la sección Campañas y cree una nueva campaña con el canal Web.

3. **Agregar acción**\
   Añada una acción de experiencia basada en código y vincule la acción a una configuración de canal creada anteriormente.



4. **Audiencia**\
   Todos los visitantes (predeterminado).

   Tipo de identidad: ECID (Experience Cloud ID)
Esta configuración utiliza el ECID como identidad principal para reconocer usuarios. Cuando se establece la vinculación de identidad, ECID está vinculado a CRM ID para Personalized Targeting. Seleccione o cree una política de decisión que defina la lógica de oferta.

5. **Directiva de decisión**


   La acción está vinculada a una **Directiva de decisión** que define cómo se seleccionan las ofertas y cuántas ofertas se devuelven para su visualización. Esta directiva usa una **estrategia de selección** que se creó anteriormente en el tutorial.

   La estrategia de selección está **basada en fórmulas**, lo que significa que usa una fórmula de clasificación para asignar puntuaciones a ofertas elegibles y determinar cuáles se deben priorizar.

   La estrategia incluye:

   - **Colección de ofertas**\
     Un conjunto predefinido de ofertas relevantes para la campaña, como ofertas basadas en ingresos o específicas del código postal.

   - **Reglas de elegibilidad**\
     La elegibilidad se estableció en **_Todos los visitantes_**

   - **Fórmula de clasificación**\
     Una expresión lógica que puntúa cada oferta elegible. La oferta con la puntuación más alta se procesa en la experiencia personalizada.



6. **Publicar la campaña**\
   Active la campaña para empezar a enviar ofertas personalizadas en tiempo real.





