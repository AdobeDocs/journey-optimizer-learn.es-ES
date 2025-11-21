---
title: Configuración e inicio
description: Configure los canales móviles en Adobe Journey Optimizer (AJO) y Adobe Experience Platform (AEP), integre los canales con las aplicaciones móviles y asegúrese de que está preparado para ejecutar campañas de marketing.
feature: Overview
role: Developer, Admin
level: Beginner, Intermediate
hide: true
index: false
last-substantial-update: 2025-08-22T00:00:00Z
exl-id: d8ffe406-b54b-455f-bd41-7d1fef0a4714
source-git-commit: d892f1115045e5bd1cc89dc75e34434b9b5954bd
workflow-type: tm+mt
source-wordcount: '2561'
ht-degree: 15%

---


# Configuración e inicio

Configure los canales móviles en Adobe Journey Optimizer y Adobe Experience Platform, integre con las aplicaciones móviles y garantice la preparación para la ejecución de campañas de marketing.

>[!NOTE]
>
> Si es nuevo en Journey Optimizer y Experience Platform, familiarícese con los conceptos básicos de administración de datos en Journey Optimizer con este curso:
>
> [Datos del ingeniero para la activación inteligente del Recorrido en Adobe Journey Optimizer](https://experienceleague.adobe.com/es/courses/ajo-engineer-data-for-intelligent-journey-activation){target="_blank"}
>*Aprenda a configurar y administrar datos de perfil del cliente en tiempo real para Journey Optimizer mediante Experience Platform. Comprenda el modelado de datos, la asignación de identidades y la ingesta de datos para crear perfiles unificados para recorridos personalizados de clientes.*


## Funciones móviles en Adobe Journey Optimizer

Comprenda qué funciones móviles ofrece Adobe Journey Optimizer para desarrolladores, especialistas en marketing y equipos de productos, incluida la mensajería push, la mensajería en la aplicación y la personalización de contenido.

>[!VIDEO](https://video.tv.adobe.com/v/344614?captions=spa&quality=12&learn=on){transcript=true}


## Configuración de aplicaciones y Mobile SDK

Las implementaciones móviles en Journey Optimizer comienzan con la integración de **Adobe Experience Platform Mobile SDK** en su aplicación. Los SDK son esenciales para la recopilación de datos y la interacción con Adobe Experience Platform (AEP) y sus aplicaciones, como Adobe Journey Optimizer (AJO).

El SDK móvil:

- Recopila eventos de aplicación (vistas de pantalla, toques, compras, eventos de ciclo vital, etc.) y los envía a **Adobe Experience Platform Edge Network**.
- Administra la **identidad** y el **consentimiento**, de modo que Journey Optimizer pueda generar y usar perfiles de clientes de forma segura.
- Registra y actualiza **tokens push** y envía **eventos de seguimiento push y en la aplicación** de vuelta a Adobe Experience Platform.
- Se integra con **Journey Optimizer mobile extensions** (push, en la aplicación, tarjetas de contenido, toma de decisiones) para que los mensajes se puedan enviar, procesar y medir de extremo a extremo.

Sin el SDK móvil integrado en la aplicación, Journey Optimizer no puede hacer lo siguiente de forma fiable:

- Entrega y seguimiento de mensajes push móviles y en la aplicación.
- Procesar y rastrear tarjetas de contenido.
- Use el comportamiento en tiempo real en la aplicación para almacenar en déclencheur los recorridos y personalizar las experiencias.


>[!PREREQUISITES]
>
>Asegúrese de que dispone de:
>
> - Adobe Journey Optimizer (AJO) aprovisionado para su organización.
> - Acceso a Adobe Experience Platform con permisos de recopilación de datos y Journey Optimizer.
> - Derechos de administrador en AJO para la configuración de canales y configuraciones.
> - Acceso al código fuente de la aplicación móvil (iOS, Android o plataforma multiplataforma).
> - Su aplicación tiene habilitadas las funciones de nivel de sistema operativo necesarias (por ejemplo, permisos push, extensiones de servicio de notificaciones y modos de fondo).


### Componentes móviles de SDK necesarios para Journey Optimizer

Para usar canales móviles de Journey Optimizer (push, en la aplicación, tarjetas de contenido y experiencias basadas en código), debe instalar y configurar un conjunto de extensiones **core** y **channel-specific** en su aplicación móvil:

>[!BEGINTABS]

>[!TAB Principal]

#### Extensiones principales (necesarias para todos los casos de uso móvil)

| Objetivo | Ejemplos de extensiones (iOS/Android) | Notas |
|----------------------|-----------------------------------------------|-------|
| Centro de eventos y servicios | Mobile Core / AEP Core, AEP Services | Base para todas las demás extensiones. Proporciona el estado compartido, el almacenamiento, la red y el centro de eventos. |
| Edge Network | Adobe Experience Platform Edge Network | Envía eventos de aplicación al Edge Network de Adobe Experience Platform. |
| Identidad | Identidad de Edge Network | Administra el ECID y otras identidades utilizadas para el perfil y la segmentación. |
| Consentimiento | Consentimiento para Edge Network | Recopila y aplica las preferencias de consentimiento de usuario. |
| Assurance | Adobe Experience Platform Assurance | Se utiliza para validar y depurar la configuración de SDK y de canal de principio a fin. |

>[!TAB Específico del canal]

#### Extensiones específicas de canal para Journey Optimizer

| Canal/capacidad | Extensiones de clave adicionales (en la parte superior del núcleo) | Qué habilitan |
|------------------------|---------------------------------------------------------------------|------------------|
| Notificaciones push | Extensión móvil de Journey Optimizer (push) | Registre y actualice tokens push, envíe eventos de seguimiento push y conecte con la configuración push de AJO. |
| Mensajería en la aplicación | Extensión móvil de Journey Optimizer (en la aplicación), componentes de la interfaz de usuario de mensajería | Busque y muestre mensajes en la aplicación en contexto, envíe impresiones y eventos de interacción. |
| Tarjetas de contenido | SDK de mensajería compatible con tarjetas de contenido | Busque, procese y rastree tarjetas de contenido para obtener informes precisos de Journey Optimizer. |
| Experiencias basadas en código | Extensiones de Journey Optimizer/Decisioning o API de servidor de Edge | Recupere decisiones para &quot;superficies&quot; específicas en la aplicación; la aplicación controla cómo se procesa el contenido. |

>[!ENDTABS]

#### Propiedad y configuración de etiquetas móviles

Estas extensiones se configuran en una **[propiedad de etiquetas móviles](https://developer.adobe.com/client-sdks/home/getting-started/create-a-mobile-property/){target="_blank"}** en la recopilación de datos de AEP -> Etiquetas.

Esta propiedad controla:

- Qué extensiones de Mobile SDK están instaladas.
- Qué eventos del déclencheur de la aplicación llaman a Edge Network.
- Asignación de datos en XDM y reenvío a soluciones de Adobe (Journey Optimizer, Analytics, etc.).

Puede [crear y configurar esta propiedad móvil manualmente](https://experienceleague.adobe.com/es/docs/platform-learn/data-collection/tags/create-a-property){target="_blank"}, o para la aplicación móvil y la funcionalidad push puede usar la **[configuración guiada de canal](https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup){target="_blank"}** para crear automáticamente la propiedad de etiquetas, la secuencia de datos y la configuración de canal necesarias para iOS y Android.

>[!TIP]
>  
> Para nuevas implementaciones, el punto de partida recomendado es **[Configuración guiada del canal](https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup){target="_blank"}**. Reduce el riesgo de flujos de datos mal configurados o extensiones faltantes y le explica la validación de SDK con Assurance.

#### Introducción a Mobile SDK:

<!-- CARDS
* https://experienceleague.adobe.com/es/docs/platform-learn/data-collection/mobile-sdk/overview
    {description = Learn how Adobe Experience Platform Mobile SDK powers end-to-end engagement in your mobile applications.}
* https://experienceleague.adobe.com/es/docs/platform-learn/implement-mobile-sdk/overview
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Adobe Experience Platform Mobile SDK overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/es/docs/platform-learn/data-collection/mobile-sdk/overview" title="Información general de Adobe Experience Platform Mobile SDK" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/33545?captions=spa&format=jpeg&nocache=1763661968458" alt="Información general de Adobe Experience Platform Mobile SDK"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/platform-learn/data-collection/mobile-sdk/overview" target="_blank" rel="referrer" title="Información general de Adobe Experience Platform Mobile SDK">Información general sobre Adobe Experience Platform Mobile SDK</a>
                    </p>
                    <p class="is-size-6">Descubra cómo Adobe Experience Platform Mobile SDK potencia la participación integral en sus aplicaciones móviles.</p>
                </div>
                <a href="https://experienceleague.adobe.com/es/docs/platform-learn/data-collection/mobile-sdk/overview" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ver</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Implement Adobe Experience Cloud in mobile apps tutorial">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/es/docs/platform-learn/implement-mobile-sdk/overview" title="Tutorial de implementación de Adobe Experience Cloud en aplicaciones móviles" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/es/docs/platform-learn/implement-mobile-sdk/overview./media_1c75750ec1be623e56a379ca69ef6c495799e52a5.png?width=400&format=png&optimize=medium" alt="Tutorial de implementación de Adobe Experience Cloud en aplicaciones móviles"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" title="Tutorial de implementación de Adobe Experience Cloud en aplicaciones móviles">Tutorial de implementación de Adobe Experience Cloud en aplicaciones móviles</a>
                    </p>
                    <p class="is-size-6">Obtenga información sobre cómo implementar las aplicaciones móviles de Adobe Experience Cloud. Este tutorial le guía a través de una implementación de aplicaciones de Experience Cloud en una aplicación Swift o Android de ejemplo.</p>
                </div>
                <a href="https://experienceleague.adobe.com/es/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Más información</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

#### Referencias del desarrollador:

<!-- CARDS
* https://developer.adobe.com/client-sdks/home/
* https://developer.adobe.com/client-sdks/home/current-sdk-versions/
* https://developer.adobe.com/client-sdks/home/getting-started/create-a-mobile-property/
* https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk/
* https://developer.adobe.com/client-sdks/home/getting-started/track-events/
* https://developer.adobe.com/client-sdks/home/base/assurance/
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Mobile SDK overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://developer.adobe.com/client-sdks/home/" title="Información general de Mobile SDK" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://developer.adobe.com/shared/images/adobe-social-share.png" alt="Información general de Mobile SDK"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://developer.adobe.com/client-sdks/home/" target="_blank" rel="referrer" title="Información general de Mobile SDK">Descripción general de Mobile SDK</a>
                    </p>
                    <p class="is-size-6">La página de información general de la documentación de Adobe Experience Platform Mobile SDK.</p>
                </div>
                <a href="https://developer.adobe.com/client-sdks/home/" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Más información</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Current SDK versions">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://developer.adobe.com/client-sdks/home/current-sdk-versions/" title="Versiones actuales de SDK" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://developer.adobe.com/shared/images/adobe-social-share.png" alt="Versiones actuales de SDK"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://developer.adobe.com/client-sdks/home/current-sdk-versions/" target="_blank" rel="referrer" title="Versiones actuales de SDK">Versiones actuales de SDK</a>
                    </p>
                    <p class="is-size-6">Información general que muestra las extensiones móviles disponibles actualmente, junto con sus versiones, para cada plataforma.</p>
                </div>
                <a href="https://developer.adobe.com/client-sdks/home/current-sdk-versions/" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Más información</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up a mobile property">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://developer.adobe.com/client-sdks/home/getting-started/create-a-mobile-property/" title="Configuración de una propiedad móvil" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://developer.adobe.com/shared/images/adobe-social-share.png" alt="Configuración de una propiedad móvil"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://developer.adobe.com/client-sdks/home/getting-started/create-a-mobile-property/" target="_blank" rel="referrer" title="Configuración de una propiedad móvil">Configurar una propiedad móvil</a>
                    </p>
                    <p class="is-size-6">Una guía que explica cómo configurar una propiedad móvil mediante la creación de la propiedad, la instalación de extensiones y la publicación de la configuración. Completar este proceso le permite utilizar Mobile SDK.</p>
                </div>
                <a href="https://developer.adobe.com/client-sdks/home/getting-started/create-a-mobile-property/" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Más información</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Get the Adobe Experience Platform Mobile SDK">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk/" title="Obtenga Adobe Experience Platform Mobile SDK" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://developer.adobe.com/shared/images/adobe-social-share.png" alt="Obtenga Adobe Experience Platform Mobile SDK"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk/" target="_blank" rel="referrer" title="Obtenga Adobe Experience Platform Mobile SDK">Obtener Adobe Experience Platform Mobile SDK</a>
                    </p>
                    <p class="is-size-6">Una guía que explica cómo instalar Adobe Experience Platform Mobile SDK en la aplicación.</p>
                </div>
                <a href="https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk/" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Más información</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Track events">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://developer.adobe.com/client-sdks/home/getting-started/track-events/" title="Seguimiento de eventos" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://developer.adobe.com/shared/images/adobe-social-share.png" alt="Seguimiento de eventos"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://developer.adobe.com/client-sdks/home/getting-started/track-events/" target="_blank" rel="referrer" title="Seguimiento de eventos">Rastrear eventos</a>
                    </p>
                    <p class="is-size-6">Una guía que explica cómo rastrear eventos mediante Adobe Experience Platform Mobile SDK.</p>
                </div>
                <a href="https://developer.adobe.com/client-sdks/home/getting-started/track-events/" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Más información</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Adobe Experience Platform Assurance overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://developer.adobe.com/client-sdks/home/base/assurance/" title="Información general de Adobe Experience Platform Assurance" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://developer.adobe.com/shared/images/adobe-social-share.png" alt="Información general de Adobe Experience Platform Assurance"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://developer.adobe.com/client-sdks/home/base/assurance/" target="_blank" rel="referrer" title="Información general de Adobe Experience Platform Assurance">Información general de Adobe Experience Platform Assurance</a>
                    </p>
                    <p class="is-size-6">Información general sobre la extensión móvil de Adobe Experience Platform Assurance.</p>
                </div>
                <a href="https://developer.adobe.com/client-sdks/home/base/assurance/" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Más información</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

>[!SUCCESS]
>
>**lista de comprobación de preparación para SDK móvil**
>
> [ ] Core SDK instalado (Core, Edge, Identity, Consent, Assurance).
> [ Se agregaron ] extensiones de Journey Optimizer Mobile para los canales que usará (push, en la aplicación, tarjetas de contenido, basadas en código).
> [ ] Flujo de datos configurado correctamente para los conjuntos de datos de evento y perfil.
> [ ]: identidad y consentimiento implementados y validados con Assurance.
> [ ]: el registro y el seguimiento de tokens push validados de extremo a extremo.
> [ ]: las tarjetas de contenido o en la aplicación se muestran validadas en un dispositivo.
> [ ] Configuración de canal guiada usada para nuevas implementaciones o configuración alineada manualmente a los pasos documentados.


## Configuración de canal de Adobe Journey Optimizer

### En la aplicación, push y WhatsApp

Configure sus **canales móviles** mediante la funcionalidad de configuración guiada de canales. Entender cómo configurar el **canal de WhatsApp**:

<!-- CARDS
* https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup
 {description = Learn how to quickly set up and validate web and mobile channels across Experience Platform, Journey Optimizer, and Data Collection, and configure a push notification for a sample iOS marketing app.}
* https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Guided channel setup">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup" title="Configuración de canales guiada" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3449625/?captions=spa&format=jpeg&nocache=1763661970550" alt="Configuración de canales guiada"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup" target="_blank" rel="referrer" title="Configuración de canales guiada">Configuración de canales guiada</a>
                    </p>
                    <p class="is-size-6">Obtenga información sobre cómo configurar y validar rápidamente canales web y móviles en Experience Platform, Journey Optimizer y recopilación de datos, y configurar una notificación push para una aplicación de marketing de iOS de ejemplo.</p>
                </div>
                <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ver</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up the WhatsApp channel">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" title="Configuración del canal de WhatsApp" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3470271/?captions=spa&format=jpeg&nocache=1763661970579" alt="Configuración del canal de WhatsApp"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" target="_blank" rel="referrer" title="Configuración del canal de WhatsApp">Configuración del canal de WhatsApp</a>
                    </p>
                    <p class="is-size-6">Este tutorial le guía a través de la configuración del canal WhatsApp en Adobe Journey Optimizer para habilitar la mensajería de empresa en tiempo real.</p>
                </div>
                <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ver</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

### SMS/MMS/RCS

Configure **canales SMS/MMS/RCS** con los proveedores estándar (Twilio, Synch o Infobip) o usando un proveedor de SMS personalizado:

<!-- CARDS
* https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel
* https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider
{description = Learn how to configure custom SMS providers in Journey Optimizer, set up API credentials and webhooks, manage opt-in/opt-out keywords, and launch personalized campaigns.}
* https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces
* https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure SMS API credentials and channel surfaces">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" title="Configuración de credenciales de API de SMS y superficies de canal" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3418544?captions=spa&format=jpeg&nocache=1763661971419" alt="Configuración de credenciales de API de SMS y superficies de canal"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" target="_blank" rel="referrer" title="Configuración de credenciales de API de SMS y superficies de canal">Configurar credenciales de API de SMS y superficies de canal</a>
                    </p>
                    <p class="is-size-6">Obtenga información sobre cómo conectar Journey Optimizer a un proveedor de servicios SMS y cómo crear una superficie de canal SMS.</p>
                </div>
                <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ver</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure a custom SMS provider">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" title="Configuración de un proveedor de SMS personalizado" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3431625/?format=jpeg&nocache=1763661971435" alt="Configuración de un proveedor de SMS personalizado"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" target="_blank" rel="referrer" title="Configuración de un proveedor de SMS personalizado">Configuración de un proveedor de SMS personalizado</a>
                    </p>
                    <p class="is-size-6">Obtenga información sobre cómo configurar proveedores de SMS personalizados en Journey Optimizer, configurar credenciales de API y webhooks, administrar palabras clave de inclusión/exclusión e iniciar campañas personalizadas.</p>
                </div>
                <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ver</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure MMS API credentials and channel surfaces">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" title="Configuración de credenciales de API de MMS y superficies de canal" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3438049/?captions=spa&format=jpeg&nocache=1763661971338" alt="Configuración de credenciales de API de MMS y superficies de canal"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" target="_blank" rel="referrer" title="Configuración de credenciales de API de MMS y superficies de canal">Configuración de credenciales de API de MMS y superficies de canal</a>
                    </p>
                    <p class="is-size-6">Aprenda a conectar Journey Optimizer a un proveedor de servicios MMS y a crear una superficie de canal MMS.</p>
                </div>
                <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ver</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up RCS in Journey Optimizer">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" title="Configuración de RCS en Journey Optimizer" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3464758/?captions=spa&format=jpeg&nocache=1763661971296" alt="Configuración de RCS en Journey Optimizer"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" target="_blank" rel="referrer" title="Configuración de RCS en Journey Optimizer">Configuración de RCS en Journey Optimizer</a>
                    </p>
                    <p class="is-size-6">Aprenda a configurar y enviar mensajes RCS interactivos de marca en Adobe Journey Optimizer mediante un proveedor de SMS personalizado. Este tutorial explica cómo configurar las credenciales de la API, los webhooks y las configuraciones de canal y, a continuación, crear un recorrido para ofrecer experiencias de mensajería enriquecidas y personalizadas, todo ello dentro de la aplicación de mensajería nativa.</p>
                </div>
                <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ver</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## Asegúrese de cumplir las leyes de privacidad y las directrices de la plataforma.

<!-- CARDS
* https://experienceleague.adobe.com/es/docs/journey-optimizer/using/privacy/privacy-landing-page{image=../mobile-learning-hub/assets/privacy.webp}{title = Privacy Features in Adobe Journey Optimizer}{description = Learn how to process privacy requests, audit user actions, manage consent, apply governance rules, and leverage advanced security options like Customer Managed Keys.}
* https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework
* https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables{cta = Watch}
* https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Privacy Features in Adobe Journey Optimizer">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer/using/privacy/privacy-landing-page" title="Funciones de privacidad en Adobe Journey Optimizer" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="../mobile-learning-hub/assets/privacy.webp" alt="Funciones de privacidad en Adobe Journey Optimizer"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer/using/privacy/privacy-landing-page" target="_blank" rel="referrer" title="Funciones de privacidad en Adobe Journey Optimizer">Características de privacidad en Adobe Journey Optimizer</a>
                    </p>
                    <p class="is-size-6">Obtenga información sobre cómo procesar solicitudes de privacidad, auditar acciones de los usuarios, administrar el consentimiento, aplicar reglas de gobernanza y aprovechar opciones de seguridad avanzadas como Claves administradas por el cliente.</p>
                </div>
                <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer/using/privacy/privacy-landing-page" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Más información</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Data Governance Framework Overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" title="Información general sobre el marco de gobernanza de datos" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/32682/?captions=spa&format=jpeg&nocache=1763661972554" alt="Información general sobre el marco de gobernanza de datos"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" target="_blank" rel="referrer" title="Información general sobre el marco de gobernanza de datos">Información general sobre el marco de gobernanza de datos</a>
                    </p>
                    <p class="is-size-6">Comprenda las funciones de gobernanza de Adobe Experience Platform.</p>
                </div>
                <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ver</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Classify data using labels">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" title="Clasificación de datos mediante etiquetas" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3422794?captions=spa&format=jpeg&nocache=1763661972557" alt="Clasificación de datos mediante etiquetas"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" target="_blank" rel="referrer" title="Clasificación de datos mediante etiquetas">Clasificación de datos mediante etiquetas</a>
                    </p>
                    <p class="is-size-6">Aprenda a aplicar etiquetas a los esquemas y conjuntos de datos. </p>
                </div>
                <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ver</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Create Data Usage Policies">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" title="Creación de políticas de uso de datos" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/37128/?captions=spa&format=jpeg&nocache=1763661972555" alt="Creación de políticas de uso de datos"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" target="_blank" rel="referrer" title="Creación de políticas de uso de datos">Creación de políticas de uso de datos</a>
                    </p>
                    <p class="is-size-6">Obtenga información sobre la creación y administración de las políticas de uso de datos.</p>
                </div>
                <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ver</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## Peligros comunes de la implementación y cómo evitarlos

La mayoría de los problemas de dispositivos móviles se originan en **SDK o en la configuración de recopilación de datos**, no en los propios recorridos o campañas de Journey Optimizer. Utilice la siguiente tabla para identificar qué está pasando mal y, a continuación, expanda la sección correspondiente para obtener más detalles.

### Resumen de los inconvenientes

| # | Problema/síntoma | Escollo común | Solucionar de un vistazo |
|---|----------------------------------------------|-----------------------------------------------------|------------------------------------------|
| 1 | La configuración del canal guiado falla; sin tráfico o bajo | [Las versiones o extensiones de SDK no están alineadas](#1-sdk-versions-and-extensions-not-aligned-with-channel-requirements) | Actualizar versiones de SDK/extensión; validar en Assurance |
| 2 | Error de seguimiento de lotes; errores en AEP | [Flujos de datos o conjuntos de datos mal configurados](#2-misconfigured-datastreams-or-datasets) | Asignación de eventos a conjuntos de datos de eventos y perfiles a conjuntos de datos de perfil |
| 3 | Los recorridos no se activan; una personalización extraña | [Falta identidad o consentimiento / inconsistente](#3-missing-or-inconsistent-identity-and-consent) | Implementación de Edge ID y consentimiento; comprobar en Assurance |
| 4 | No hay envíos push ni aperturas en los informes | [Registro o seguimiento de token push interrumpido](#4-push-token-registration-and-tracking-not-wired-correctly) | Corrección del registro de tokens y el seguimiento de interacciones mediante SDK |
| 5 | No hay impresiones en la aplicación a pesar de las campañas activas | [No se muestran mensajes en la aplicación ni tarjetas de contenido](#5-in-app-messages-or-content-cards-not-displaying) | Compruebe las extensiones de mensajería, los déclencheur y las respuestas de decisión de Assurance |

### Directrices detalladas por escollos

Abra la dificultad que coincida con sus síntomas para ver qué comprobar y cómo solucionarlo.

<details id="1-sdk-versions-and-extensions-not-aligned-with-channel-requirements">
<summary><strong>1. Las versiones y extensiones de SDK no están alineadas con los requisitos del canal </strong></summary>

**Lo que notará**

- Las actividades push o en la aplicación no llegan al dispositivo.
- La configuración guiada del canal o la validación del canal fallan.
- Assurance muestra las extensiones de Journey Optimizer, Edge o Identity que faltan.

**Qué comprobar**

- ¿Está usando las versiones de extensión mínima de **Mobile Core** y **Journey Optimizer** que requiere la configuración guiada del canal?
- En **Assurance**, en extensiones y eventos:
   - ¿Ve cargadas las extensiones esperadas?
   - ¿Los eventos se envían a Edge Network y se reconocen?

**Cómo corregir**

- Actualice a las versiones de extensión de Mobile SDK y Journey Optimizer compatibles.
- Vuelva a compilar la aplicación, conéctese de nuevo a Assurance y ejecute de nuevo la configuración del canal guiado.

Ver: [Configurar móvil y web](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config){target="_blank"}

</details>


<details id="2-misconfigured-datastreams-or-datasets">
<summary><strong>2. Flujos de datos o conjuntos de datos mal configurados</strong></summary>

**Lo que notará**

- Los lotes de seguimiento push o de eventos fallan en los conjuntos de datos de Platform.
- Errores de ingesta de datos (por ejemplo, &quot;Las actualizaciones no son compatibles con eventos&quot;).
- Los informes push o en la aplicación muestran poco o ningún seguimiento.

**Qué comprobar**

- ¿Alguien cambió **esquemas del sistema o conjuntos de datos** creados para el seguimiento de Journey Optimizer?
- En su **secuencia de datos**:
   - ¿Los eventos de experiencia están asignados a un **conjunto de datos de evento**?
   - ¿Los atributos de perfil están asignados a un **conjunto de datos de perfil**?

**Cómo corregir**

- No edite los conjuntos de datos/esquemas del sistema creados por AJO.
- Corrija la asignación de la secuencia de datos (eventos → conjunto de datos de evento, perfiles → conjunto de datos de perfil).
- Prefiera la configuración guiada del canal o los pasos documentados del flujo de datos en lugar de los cambios específicos.

Ver: [Flujo de notificaciones push en Adobe Journey Optimizer](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/channels/push/push-config/push-gs){target="_blank"}

</details>


<details id="3-missing-or-inconsistent-identity-and-consent">
<summary><strong>3. Falta identidad y consentimiento o es incoherente</strong></summary>

**Lo que notará**

- Los recorridos no entran en déclencheur como se espera para los usuarios de la aplicación.
- Personalization no coincide con el comportamiento del usuario en otros canales.
- Los eventos aparecen en Experience Platform, pero los perfiles parecen fragmentados.

**Qué comprobar**

- ¿Se ha implementado la identidad **para Edge Network** y se está enviando un ID principal estable (por ejemplo, un ID de inicio de sesión)?
- ¿Se ha implementado y actualizado el **consentimiento para Edge Network** cuando cambian las preferencias?
- En **Assurance**:
   - ¿Los eventos salientes incluyen valores de consentimiento?
   - ¿Incluyen ECID y sus ID principales de forma coherente?

**Cómo corregir**

- Implemente o corrija la identidad **para Edge Network** en la aplicación.
- Implemente **Consentimiento para Edge Network** y conéctelo a la interfaz de usuario de consentimiento de su aplicación.
- Vuelva a realizar la prueba en Assurance hasta que la identidad y el consentimiento aparezcan en todos los eventos relevantes.

Ver: [Implementar el consentimiento para implementaciones de Platform Mobile SDK](https://experienceleague.adobe.com/es/docs/platform-learn/implement-mobile-sdk/app-implementation/consent){target="_blank"}

</details>


<details id="4-push-token-registration-and-tracking-not-wired-correctly">
<summary><strong>4. El registro y seguimiento del token push no están conectados correctamente</strong></summary>

**Lo que notará**

- Los usuarios nunca reciben notificaciones push, aunque se ejecuten las campañas o los recorridos.
- Los informes push no muestran aperturas, rechazos ni interacciones.

**Qué comprobar**

- ¿La aplicación registra el token push con la extensión de Journey Optimizer?
   - ¿En la primera instalación?
   - ¿Después de cada actualización de aplicación?
   - ¿Cada vez que el sistema operativo actualiza el token?
- Cuando un usuario abre o descarta una notificación, ¿ve el seguimiento de eventos en Assurance?

**Cómo corregir**

- Añada o corrija el código que:
   - Registra el token mediante la extensión móvil de Journey Optimizer cada vez que se crea o actualiza.
   - Envía eventos de interacción push (abrir, descartar, acciones personalizadas) mediante Mobile SDK.
- Utilice Assurance para confirmar que los eventos de registro y seguimiento se activan según lo esperado.

Ver: [Flujo de notificaciones push en Adobe Journey Optimizer](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/channels/push/push-config/push-gs){target="_blank"}

</details>


<details id="5-in-app-messages-or-content-cards-not-displaying">
<summary><strong>5. Mensajes en la aplicación o tarjetas de contenido que no muestran </strong></summary>

**Lo que notará**

- Los mensajes en la aplicación o las tarjetas de contenido nunca aparecen, a pesar de las campañas o los recorridos activos.
- El informe muestra 0 impresiones.

**Qué comprobar**

- ¿Están **Journey Optimizer mobile messaging / in-app extension** y **Messaging SDK** instalados y registrados en la aplicación?
- En su configuración de **tags**:
   - ¿Tiene reglas que almacenan en déclencheur las solicitudes en los eventos correctos (por ejemplo, vistas de pantalla o eventos personalizados)?
- En **Assurance**:
   - Cuando se activan esos eventos, ¿ve que se emiten solicitudes de decisión en la aplicación o en la tarjeta de contenido?
   - ¿Ve respuestas procedentes de Edge Network?

**Cómo corregir**

- Instale y registre las extensiones de mensajería necesarias.
- Añada o corrija reglas que almacenen en déclencheur las decisiones en los eventos de destino (pantallas, eventos personalizados).
- Para las tarjetas de contenido, asegúrese de lo siguiente:
   - Buscar tarjetas mediante las API de mensajería de SDK.
   - Procesarlos en la interfaz de usuario.
   - Rastree las interacciones a través de SDK.

Consulte:
- [Crear y enviar mensajes en la aplicación](https://experienceleague.adobe.com/es/docs/platform-learn/implement-mobile-sdk/experience-cloud/journey-optimizer/journey-optimizer-inapp){target="_blank"}
- [Configuración de la compatibilidad con tarjetas de contenido en Mobile SDK](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp){target="_blank"}

</details>

>[!SUCCESS]
>
> **Lista de comprobación de preparación en una línea**
>
> Antes de entregar la aplicación a los especialistas en marketing, confirme en **[Assurance](https://developer.adobe.com/client-sdks/home/base/assurance/){target="_blank"}** que:
> 
> [ Se han cargado ] extensiones de Core SDK + Journey Optimizer,\
> [ ] eventos fluyen en el conjunto de datos y la secuencia de datos correctos,\
> [ ]La identidad y el consentimiento están presentes en todos los eventos clave,\
> [ Se hace un seguimiento de los tokens de inserción y las interacciones de ], y\
> [ ] Al menos un mensaje o una tarjeta de contenido de prueba en la aplicación se ha mostrado y registrado como una impresión.

## Publicaciones de blog

- [Uso de personalización del lado del cliente (ODD) basada en CDN en dispositivos móviles para realizar personalizaciones más rápidas.](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/using-cdn-based-client-side-personalization-odd-on-mobile-for/ba-p/761626?profile.language=es){target="_blank"}
- [Mobile Activation para Adobe Experience Cloud](https://experienceleaguecommunities.adobe.com/t5/adobe-target-blogs/mobile-activation-for-adobe-experience-cloud/ba-p/541595?profile.language=es){target="_blank"}
