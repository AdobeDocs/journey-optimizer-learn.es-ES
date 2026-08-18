---
title: Introducción a la fidelización de Journey Optimizer
description: Obtenga información sobre cómo incorporarse a Lealtad de Adobe Journey Optimizer, configurar un desafío, aplicarlo y mostrarlo, y analizar su rendimiento.
topic: Get Started
role: User
level: Beginner
doc-type: Tutorial
jira: KT-21773
last-substantial-update: 2026-07-28T00:00:00Z
source-git-commit: c4e15de254bd2e087938bbe47b11068fa653dcf9
workflow-type: tm+mt
source-wordcount: '965'
ht-degree: 42%

---


# Introducción a la fidelización de Journey Optimizer

Los desafíos de lealtad le permiten crear programas de lealtad atractivos e interactivos que impulsan el comportamiento de los clientes y profundizan las relaciones de marca. Cree desafíos que recompensen a los clientes por acciones específicas, desde hacer compras y escribir críticas hasta interactuar en medios sociales y hacer referencia a amigos.

## Introducción a la lealtad

Esta sección presenta la lealtad de Journey Optimizer: qué es, dónde se encuentra en Adobe Journey Optimizer y el ciclo de vida del desafío, desde la configuración hasta el análisis.

<!--
CARDS

* https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/loyalty/discover-journey-optimizer-loyalty
  {description = Understand what Journey Optimizer Loyalty is, where it sits under AJO, and the challenge lifecycle.}

-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Discover Journey Optimizer Loyalty">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/loyalty/discover-journey-optimizer-loyalty" title="Lealtad de Discover Journey Optimizer" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3496454/?captions=spa&format=jpeg&nocache=1787093383713" alt="Lealtad de Discover Journey Optimizer"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/loyalty/discover-journey-optimizer-loyalty" target="_blank" rel="referrer" title="Lealtad de Discover Journey Optimizer">Descubrir la lealtad de Journey Optimizer</a>
                    </p>
                    <p class="is-size-6">Comprenda qué es la lealtad de Journey Optimizer, dónde se encuentra en AJO y el ciclo vital de los desafíos.</p>
                </div>
                <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/loyalty/discover-journey-optimizer-loyalty" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ver</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## Configurar fidelización

Esta sección trata sobre la configuración inicial única necesaria para empezar a crear un desafío.


<!--
CARDS

* ./set-up-loyalty/set-up-a-loyalty-reward-provider.md
  {description = Learn how to set up a reward provider, create reward definitions, and configure reward payloads so Adobe Journey Optimizer can issue loyalty rewards through your external rewards system.}

-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up a loyalty reward provider">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./set-up-loyalty/set-up-a-loyalty-reward-provider.md" title="Configurar un proveedor de recompensas por fidelidad" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3497412/?captions=spa&format=jpeg&nocache=1787093384202" alt="Configurar un proveedor de recompensas por fidelidad"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./set-up-loyalty/set-up-a-loyalty-reward-provider.md" target="_blank" rel="referrer" title="Configurar un proveedor de recompensas por fidelidad">Configurar un proveedor de recompensas por fidelidad</a>
                    </p>
                    <p class="is-size-6">Aprenda a configurar un proveedor de recompensas, crear definiciones de recompensas y configurar cargas de recompensas para que Adobe Journey Optimizer pueda emitir recompensas de lealtad a través de su sistema de recompensas externo.</p>
                </div>
                <a href="./set-up-loyalty/set-up-a-loyalty-reward-provider.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ver</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## Configurar el desafío

Esta sección le explica cómo crear y configurar un desafío de fidelidad de principio a fin: tipo, estructura y programación, tareas y recompensas.


<!--
CARDS

* ./configure-your-challenge/set-up-a-loyalty-challenge.md
  {description = Learn how to set up a loyalty challenge by selecting the right challenge type, configuring audiences and schedules, defining participation rules, and controlling how progress is tracked and rewarded.}
* ./configure-your-challenge/create-tasks.md
  {description = Learn how to set up tasks: purchase & spend, quantities, eligible items & exclusions, and reuse.}
* ./configure-your-challenge/configure-rewards.md
  {description = Learn how to configure rewards: provider, milestone vs. completion delivery, reward types & coupons.}
* ./configure-your-challenge/create-a-challenge-and-get-insights-with-cx-enterprise-coworker.md
  {description = Learn how to use CX Enterprise Coworker to create, configure, and launch loyalty challenges using natural language, including audiences, rewards, schedules, and automated journey setup.}

-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up a loyalty challenge">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./configure-your-challenge/set-up-a-loyalty-challenge.md" title="Configurar un desafío de fidelidad" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3496474/?captions=spa&format=jpeg&nocache=1787093384582" alt="Configurar un desafío de fidelidad"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./configure-your-challenge/set-up-a-loyalty-challenge.md" target="_blank" rel="referrer" title="Configurar un desafío de fidelidad">Configurar un desafío de fidelidad</a>
                    </p>
                    <p class="is-size-6">Aprenda a configurar un desafío de lealtad seleccionando el tipo de desafío adecuado, configurando audiencias y programaciones, definiendo reglas de participación y controlando cómo se realiza el seguimiento y se recompensa el progreso.</p>
                </div>
                <a href="./configure-your-challenge/set-up-a-loyalty-challenge.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ver</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Create tasks for your loyalty challenge">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./configure-your-challenge/create-tasks.md" title="Cree tareas para el desafío de fidelidad" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3496445/?captions=spa&format=jpeg&nocache=1787093384597" alt="Cree tareas para el desafío de fidelidad"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./configure-your-challenge/create-tasks.md" target="_blank" rel="referrer" title="Cree tareas para el desafío de fidelidad">Cree tareas para el desafío de fidelidad</a>
                    </p>
                    <p class="is-size-6">Aprenda a configurar tareas: compras y gastos, cantidades, artículos aptos y exclusiones, y reutilización.</p>
                </div>
                <a href="./configure-your-challenge/create-tasks.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ver</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure rewards">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./configure-your-challenge/configure-rewards.md" title="Configuración de recompensas" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3496484/?captions=spa&format=jpeg&nocache=1787093384590" alt="Configuración de recompensas"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./configure-your-challenge/configure-rewards.md" target="_blank" rel="referrer" title="Configuración de recompensas">Configurar recompensas</a>
                    </p>
                    <p class="is-size-6">Aprenda a configurar recompensas: proveedor, hito frente a entrega de finalización, tipos de recompensas y cupones.</p>
                </div>
                <a href="./configure-your-challenge/configure-rewards.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ver</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Create a loyalty challenge and surface insights with CX Enterprise Coworker">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./configure-your-challenge/create-a-challenge-and-get-insights-with-cx-enterprise-coworker.md" title="Cree un desafío de fidelidad y perspectivas de superficie con CX Enterprise Coworker" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3496541/?captions=spa&format=jpeg&nocache=1787093384571" alt="Cree un desafío de fidelidad y perspectivas de superficie con CX Enterprise Coworker"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./configure-your-challenge/create-a-challenge-and-get-insights-with-cx-enterprise-coworker.md" target="_blank" rel="referrer" title="Cree un desafío de fidelidad y perspectivas de superficie con CX Enterprise Coworker">Cree un desafío de fidelidad y perspectivas de superficie con CX Enterprise Coworker</a>
                    </p>
                    <p class="is-size-6">Aprenda a utilizar CX Enterprise Coworker para crear, configurar y lanzar desafíos de fidelidad utilizando el lenguaje natural, incluyendo audiencias, recompensas, horarios y configuración automatizada de recorridos.</p>
                </div>
                <a href="./configure-your-challenge/create-a-challenge-and-get-insights-with-cx-enterprise-coworker.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ver</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## Aplicar y mostrar el desafío

Esta sección muestra cómo plantear un desafío a sus clientes a través de tarjetas de contenido y experiencias basadas en código.

<!--
CARDS

* ./apply-and-display-your-challenge/build-a-challenge-content-card.md
  {description = Learn how to build a challenge content card / code-based experience, covering opt-in and dynamic progress across the opt-in, progress, and completed stages, plus rewards and channel configuration.}
* ./apply-and-display-your-challenge/set-up-lifecycle-messaging-for-your-challenge.md
  {description = Learn how to configure multi-channel messaging for every stage of a loyalty challenge, from invitations and engagement messages to completion and reward notifications.}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Build a challenge content card">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./apply-and-display-your-challenge/build-a-challenge-content-card.md" title="Crear una tarjeta de contenido de desafío" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3496532/?captions=spa&format=jpeg&nocache=1787093384966" alt="Crear una tarjeta de contenido de desafío"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./apply-and-display-your-challenge/build-a-challenge-content-card.md" target="_blank" rel="referrer" title="Crear una tarjeta de contenido de desafío">Crear una tarjeta de contenido de desafío</a>
                    </p>
                    <p class="is-size-6">Aprenda a crear una tarjeta de contenido/experiencia basada en código de desafío, que cubra la inclusión y el progreso dinámico en las fases de inclusión, progreso y finalización, además de las recompensas y la configuración de canal.</p>
                </div>
                <a href="./apply-and-display-your-challenge/build-a-challenge-content-card.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ver</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up lifecycle messaging for your challenge">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./apply-and-display-your-challenge/set-up-lifecycle-messaging-for-your-challenge.md" title="Configurar la mensajería del ciclo vital para su desafío" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3497458/?captions=spa&format=jpeg&nocache=1787093384955" alt="Configurar la mensajería del ciclo vital para su desafío"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./apply-and-display-your-challenge/set-up-lifecycle-messaging-for-your-challenge.md" target="_blank" rel="referrer" title="Configurar la mensajería del ciclo vital para su desafío">Configurar la mensajería de ciclo vital para su desafío</a>
                    </p>
                    <p class="is-size-6">Aprenda a configurar la mensajería multicanal para cada fase de un desafío de fidelidad, desde invitaciones y mensajes de participación hasta notificaciones de finalización y recompensa.</p>
                </div>
                <a href="./apply-and-display-your-challenge/set-up-lifecycle-messaging-for-your-challenge.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ver</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## Analizar e informar

Esta sección muestra cómo medir el rendimiento de los desafíos de fidelidad una vez que se activan.

<!--
CARDS

* [./analyze-and-report/measure-performance-with-challenge-reports.md
  {description = Learn how to use challenge reports and performance dashboards to measure participation, completion rates, revenue attribution, and overall loyalty program performance.}
  -->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">

</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->
