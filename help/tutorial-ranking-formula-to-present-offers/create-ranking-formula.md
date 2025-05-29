---
title: Crear fórmula de clasificación
description: Durante la toma de decisiones de oferta se utiliza una fórmula de clasificación en Adobe Journey Optimizer, específicamente dentro de una estrategia de selección para determinar el orden de prioridad de las ofertas aptas.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00Z
jira: KT-18188
source-git-commit: 58d2964644bc199b9db212040676d87d54f767b9
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---


# Crear fórmula de clasificación

Durante la toma de decisiones de oferta se utiliza una fórmula de clasificación en Adobe Journey Optimizer, específicamente dentro de una estrategia de selección para determinar el orden de prioridad de las ofertas aptas. La fórmula de clasificación entra en juego después del filtrado de elegibilidad, cuando varias ofertas cumplen los requisitos para un perfil determinado, pero solo la principal (o pocas) debe presentarse en función de la lógica empresarial o el contexto del perfil.

* Iniciar sesión en Journey Optimizer

* Decisioning ->Configuración de estrategia ->Fórmulas de clasificación ->Crear fórmula

Fórmula de clasificación
![nombre_descripción](assets/formuala-ranking.png)

Un criterio en una fórmula de clasificación hace referencia a una regla condicional utilizada para asignar una puntuación a una oferta. Estos criterios comparan atributos de la oferta y el perfil o contexto para determinar la relevancia de una oferta para un individuo específico.



Criterios 1
![criterio_uno](assets/criteria1.png)

Criterios 1 contiene tres criterios:

* oferta._techmarketingdemos.offerDetails.zipCode == &quot;92128&quot;: comprueba el código postal asociado a la oferta.

* _techmarketingdemos.zipCode == &quot;92128&quot;: comprueba el código postal en el perfil del usuario.

* _techmarketingdemos.annualIncome > 100000: comprueba el nivel de ingresos desde el perfil del usuario.

Si se cumplen todos estos criterios, la oferta obtiene una puntuación de 40.






Criterios 2
![criterio_dos](assets/criteria2.png)

Criterios 2 contiene tres criterios:

* oferta._techmarketingdemos.offerDetails.zipCode == &quot;92126&quot;: comprueba el código postal asociado a la oferta.

* _techmarketingdemos.zipCode == &quot;92126&quot;: comprueba el código postal en el perfil del usuario.

* _techmarketingdemos.annualIncome &lt; 100000 - comprueba el nivel de ingresos a partir del perfil del usuario.

Si se cumplen todos estos criterios, la oferta obtiene una puntuación de 30.




