---
title: Crear política de decisión
description: Una política de decisión define la lógica utilizada para determinar qué ofertas se entregan a un usuario durante la personalización.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17728
source-git-commit: a675979bc590190e0481e63efbc2cfd30752b7c0
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%

---


# Crear política de decisión

Las políticas de decisión son contenedores para sus ofertas que aprovechan el motor de decisión para elegir el mejor contenido que se ofrece, según la audiencia.

En el editor de personalización, haga clic en el elemento de política Decisión en el panel de navegación izquierdo y, a continuación, haga clic en Añadir política de decisión

![create-decision-policy](assets/decision-policy.png)

Haga clic en Add para seleccionar la estrategia de selección
Haga clic en Seleccionar reserva para seleccionar la oferta de reserva.
Haga clic en Siguiente para revisar la política de decisión y haga clic en Crear para completar el proceso de creación de la política de decisión.


![política de decisión](assets/decision-policy2.png)


## Uso de la política de decisión en el editor de código

En el editor de personalización, haga clic en Insertar política. Se agrega el código correspondiente a la política de decisión.

En este momento, puede incluir cualquier atributo de decisión necesario directamente dentro del código. Estos atributos se definen en el esquema utilizado por el catálogo de ofertas. Los atributos estándar están organizados en el área de nombres __experience&quot;, mientras que cualquier atributo personalizado específico de su organización se almacena en el área de nombres `_<imsOrg>`.

![usando_decision_policy](assets/Insert-policy.png)

Este código pasa por una lista de ofertas personalizadas seleccionadas para el usuario y muestra el texto de cada una en la página web. Muestra el mensaje (denominado offerText) de cada oferta dentro de un párrafo, para que los usuarios puedan ver claramente su contenido personalizado.
Si no hay ninguna oferta personalizada disponible, se muestra una oferta de reserva para garantizar que el espacio no se deje en blanco.

Haga clic en Save y luego en Activate the campaign