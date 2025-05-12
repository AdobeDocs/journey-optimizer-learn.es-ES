---
title: Crear una directiva de decisión
description: Utilice una política de decisión para definir la lógica y determinar qué ofertas se entregan a un usuario durante la personalización.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17728
exl-id: 186e4a7d-6077-401f-9958-2f955214bc35
source-git-commit: 9a35160921988103182815efd3551151c09b9bb4
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 0%

---

# Crear una política de decisión

Las políticas de decisión son contenedores para tus ofertas que aprovechan el motor [!UICONTROL Decisioning] para elegir el mejor contenido para entregar, dependiendo de la audiencia.

1. En el editor de personalización, haga clic en el elemento **[!UICONTROL Directiva de decisión]** en el panel de navegación izquierdo y, a continuación, haga clic en **[!UICONTROL Agregar directiva de decisión]**.

   ![create-decision-policy](assets/decision-policy.png)

1. Haga clic en **[!UICONTROL Agregar]** para seleccionar la estrategia de selección.

   ![política de decisión](assets/decision-policy2.png)

1. Haga clic en **[!UICONTROL Seleccionar reserva]** para seleccionar la oferta de reserva.
1. Haga clic en **[!UICONTROL Siguiente]** para revisar la directiva de decisión.
1. Haga clic en **[!UICONTROL Crear]** para completar el proceso de creación de la directiva de decisión.

## Uso de la política de decisión en el editor de código

1. En el editor de personalización, haga clic en **[!UICONTROL Insertar directiva]**.

   Se agrega el código correspondiente a la política de decisión.

   En este momento, puede incluir cualquier atributo de decisión necesario directamente dentro del código. Estos atributos se definen en el esquema utilizado por el catálogo de ofertas. Los atributos estándar están organizados en el espacio de nombres `__experience`, mientras que cualquier atributo personalizado específico de su organización se almacena en el espacio de nombres `_<imsOrg>`.

   ![usando_decision_policy](assets/Insert-policy.png)

   Este código pasa por una lista de ofertas personalizadas seleccionadas para el usuario y muestra el texto de cada una en la página web. Muestra el mensaje (llamado `offerText`) de cada oferta dentro de un párrafo, para que los usuarios puedan ver claramente su contenido personalizado.

   Si no hay ninguna oferta personalizada disponible, se muestra una oferta de reserva para garantizar que el espacio no se deje en blanco.

1. Haga clic en **[!UICONTROL Guardar]** y active la campaña.
