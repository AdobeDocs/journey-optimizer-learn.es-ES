---
title: Configurar y iniciar
description: Configure los canales móviles en Adobe Systems Journey Optimizer (AJO) y Adobe Experience Platform (AEP) integrar con aplicaciones móviles y asegúrese de que está preparado para campaña de marketing ejecución.
feature: Overview
role: Developer, Admin
level: Beginner, Intermediate
hide: true
index: false
last-substantial-update: 2025-08-22T00:00:00Z
exl-id: d8ffe406-b54b-455f-bd41-7d1fef0a4714
source-git-commit: c0d4d95932a9f529442ac3471ee4070398e1bfa5
workflow-type: tm+mt
source-wordcount: '2463'
ht-degree: 17%

---


# Configurar y iniciar

Configure los canales móviles en Adobe Systems Journey Optimizer y Adobe Experience Platform, integrar con aplicaciones móviles y garantice la preparación para la ejecución campaña de marketing.

> **Nota**\
> Si es nuevo en Journey Optimizer y Experience Platform, familiarícese con los conceptos básicos siguiendo estos cursos:
> - [Configurar y administrar Adobe Systems Journey Optimizer](https://experienceleague.adobe.com/es/courses/ajo-configure-and-administrate-ajo-environment)
>*En este curso, aprenderá a configurar y administrar el entorno de Journey Optimizer, incluidos los roles de usuario, permisos, entornos limitados y canales de correo electrónico, lo que garantiza operaciones eficientes y seguras.*
> - [Diseñar datos para el Activation de viaje inteligente en Adobe Systems Journey Optimizer](https://experienceleague.adobe.com/es/courses/ajo-engineer-data-for-intelligent-journey-activation)
>*En este curso, aprenderá a configurar y administrar datos de perfil del cliente en tiempo real para Journey Optimizer utilizando Experience Platform. Comprenda la modelado de datos, la asignación de identidades y la ingesta de datos para crear perfiles unificados para recorridos de clientes personalizados.*


## Capacidades móviles en Adobe Systems Journey Optimizer

Comprenda qué funciones móviles ofrece Adobe Journey Optimizer para desarrolladores, especialistas en marketing y equipos de productos, incluida la mensajería push, la mensajería en la aplicación y la personalización de contenido.

>[!VIDEO](https://video.tv.adobe.com/v/342103?quality=12&learn=on){transcript=true}


## Configuración de aplicaciones y Mobile SDK

Las implementaciones móviles en Journey Optimizer comienzan con la Adobe Experience Platform integración del **SDK** móvil en su aplicación. Los SDK son esenciales para la recopilación de datos y la interacción con Adobe Experience Platform (AEP) y sus aplicaciones, como Adobe Journey Optimizer (AJO).

El SDK de Mobile:

- Recopila eventos de aplicaciones (vistas de pantalla, pulsaciones, compras, eventos del ciclo vital, etc.) y los envía a la **red** de Adobe Experience Platform Edge.
- Gestiona la **identidad** y **el consentimiento**, de modo que Journey Optimizer puede versión y utilizar perfiles de clientes de forma segura.
- Registra y actualiza **tokens push** y envía **eventos de seguimiento push y en la aplicación** de vuelta a Adobe Experience Platform.
- Se integra con **Journey Optimizer mobile extensions** (push, en la aplicación, tarjetas de contenido, toma de decisiones) para que los mensajes se puedan enviar, procesar y medir de extremo a extremo.

Sin el SDK móvil integrado en la aplicación, Journey Optimizer no puede hacer lo siguiente de forma fiable:

- Entrega y seguimiento de mensajes push móviles y en la aplicación.
- Procesar y realizar un seguimiento de tarjetas contenido.
- Use el comportamiento en tiempo real en la aplicación para almacenar en déclencheur los recorridos y personalizar las experiencias.


### Requisitos previos

Asegúrese de que dispone de:

- Adobe Journey Optimizer (AJO) aprovisionado para su organización.
- Acceso a Adobe Experience Platform con permisos de recopilación de datos y Journey Optimizer.
- Derechos de administrador en AJO para la configuración de canal y configuración.
- Acceso al código fuente de su aplicación móvil (iOS, Android o en plataformas múltiples marco de trabajo).
- La aplicación tiene habilitadas las funcionalidades necesarias a nivel de sistema operativo (por ejemplo, permisos de inserción, extensiones de servicio notificación o modos en segundo plano).


### Componentes de Mobile SDK necesarios para Journey Optimizer

Para usar los canales móviles de Journey Optimizer (push, en la aplicación, tarjetas contenido, experiencias basadas en código), debe instalar y configurar un conjunto de extensiones principales **y** específicas **de** canal en su aplicación móvil:

>[!BEGINTABS]

>[!TAB Núcleo]

#### Extensiones principales (necesarias para todos los casos de uso móvil)

| Objetivo | Ejemplos de extensiones (iOS / Android) | Notas |
|----------------------|-----------------------------------------------|-------|
| Centro de eventos y servicios | Mobile Core / AEP Core, Servicios de AEP | Base para todas las demás extensiones. Proporciona evento concentrador, redes, almacenamiento y estado compartido. |
| Red de Edge | Adobe Experience Platform Edge Network | Envía eventos de la aplicación a la red de Adobe Experience Platform Edge. |
| Identidad | Identidad para red perimetral | Administra ECID y otras identidades utilizadas para perfil y segmentación. |
| Consentimiento | Consentimiento para red perimetral | Recopila y aplica las preferencias de consentimiento de usuario. |
| Assurance | Adobe Experience Platform Assurance | Se utiliza para validar y depurar la configuración de SDK y de canal de principio a fin. |

>[!TAB Específico del canal]

#### Extensiones específicas de canal para Journey Optimizer

| Canal / capacidad | Extensiones de clave adicionales (en la parte superior del núcleo) | Qué habilitan |
|------------------------|---------------------------------------------------------------------|------------------|
| Notificaciones push | Extensión móvil de Journey Optimizer (push) | Registre y actualice tokens push, envíe eventos push seguimiento, conéctese a la configuración push de AJO. |
| mensajería en la aplicación | Extensión móvil de Journey Optimizer (en la aplicación), mensajería IU componentes | Obtenga y muestre mensajes en la aplicación en contexto, envíe impresiones y eventos de interacción. |
| Tarjetas de contenido | SDK de mensajería compatible con contenido tarjeta | Recupere, procese y realice un seguimiento de tarjetas de contenido para obtener una sistema de informes precisa de Journey Optimizer. |
| Experiencias basadas en Code | Journey Optimizer/extensiones de toma de decisiones, o API de servidor Edge | Obtenga decisiones para &quot;superficies&quot; específicas en su aplicación; La aplicación controla cómo se representa contenido. |

>[!ENDTABS]

#### Propiedad y configuración de etiqueta móviles

Estas extensiones se configuran en una **[propiedad de etiquetas móviles](https://developer.adobe.com/client-sdks/home/getting-started/create-a-mobile-property/)** en la recopilación de datos de AEP (etiquetas). Esta propiedad controla:

- Qué extensiones de Mobile SDK están instaladas.
- Qué eventos de la aplicación desencadenan llamadas a la red perimetral.
- Cómo se asignan los datos a XDM y se reenvían a Adobe Systems soluciones (Journey Optimizer, Analytics, etc.).

Puede crear y configurar esta Propiedad móvil manualmente o usar **[la configuración](https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup)** de canal guiado para crear automáticamente la configuración necesaria de etiqueta Propiedad, flujo de datos y canal para iOS o Android.

> **Propina**\
> Para nuevas implementaciones, el punto de partida recomendado es **[Configuración guiada del canal](https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup)**. Reduce el riesgo de flujos de datos mal configurados o extensiones faltantes y le explica la validación de SDK con Assurance.

#### Introducción a Mobile SDK:

<!-- CARDS
* https://experienceleague.adobe.com/es/docs/platform-learn/data-collection/mobile-sdk/overview
    {description = Learn how Adobe Experience Platform Mobile SDK powers end-to-end engagement in your mobile applications.}
* https://experienceleague.adobe.com/es/docs/platform-learn/implement-mobile-sdk/overview
* https://experienceleague.adobe.com/es/docs/mobile
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Adobe Experience Platform Mobile SDK overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/es/docs/platform-learn/data-collection/mobile-sdk/overview" title="Información general sobre el SDK de Adobe Experience Platform Mobile" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/28948?format=jpeg&nocache=1763594622398" alt="Información general sobre el SDK de Adobe Experience Platform Mobile"
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
                    <a href="https://experienceleague.adobe.com/es/docs/platform-learn/implement-mobile-sdk/overview" title="Implementar Adobe Experience Cloud en aplicaciones móviles tutorial" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/es/docs/platform-learn/implement-mobile-sdk/overview./media_1c75750ec1be623e56a379ca69ef6c495799e52a5.png?width=400&format=png&optimize=medium" alt="Implementar Adobe Experience Cloud en aplicaciones móviles tutorial"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" title="Implementar Adobe Experience Cloud en aplicaciones móviles tutorial">Tutorial de implementación de Adobe Experience Cloud en aplicaciones móviles</a>
                    </p>
                    <p class="is-size-6">Aprenda a implementar las Adobe Experience Cloud aplicaciones móviles. Este tutorial le guía a través de una implementación de aplicaciones Experience Cloud en una aplicación Swift o Android de ejemplo.</p>
                </div>
                <a href="https://experienceleague.adobe.com/es/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Más información</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Adobe Experience Platform Mobile SDK Documentation">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/es/docs/mobile" title="Documentación del SDK móvil de Adobe Experience Platform" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://cdn.experienceleague.adobe.com/thumb/exl-cards/documentation.png" alt="Documentación del SDK móvil de Adobe Experience Platform"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/mobile" target="_blank" rel="referrer" title="Documentación del SDK móvil de Adobe Experience Platform">Adobe Experience Platform Documentación del SDK móvil</a>
                    </p>
                    <p class="is-size-6">Busque artículos de autoayuda y tutoriales sobre los SDK para móviles de Experience Platform. Conozca las estrategias y prácticas recomendadas de los expertos en eventos de vídeo en directo y bajo demanda.</p>
                </div>
                <a href="https://experienceleague.adobe.com/es/docs/mobile" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Más información</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

Para obtener más información, consulte también el Documentación del SDK de [Mobile de Adobe Experience Platform](https://experienceleague.adobe.com/es/docs/mobile)

#### Referencias para desarrolladores:

- [Portal para desarrolladores de Mobile SDK (inicio)](https://developer.adobe.com/client-sdks/home/)
- [Versiones actuales de SDK](https://developer.adobe.com/client-sdks/home/current-sdk-versions/)
- [Introducción a una propiedad móvil (etiquetas)](https://developer.adobe.com/client-sdks/home/getting-started/create-a-mobile-property/)
- [Obtenga el SDK (instale en su aplicación)](https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk/)
- [Rastrear eventos con el SDK móvil](https://developer.adobe.com/client-sdks/home/getting-started/track-events/)
- [Validar con garantía](https://developer.adobe.com/client-sdks/home/base/assurance/)

#### Lista de comprobación de preparación de SDK móvil

> - [ ] Core SDK instalado (Core, Edge, Identity, Consent, Assurance).
> - [ Se agregaron ] extensiones de Journey Optimizer Mobile para los canales que usará (push, en la aplicación, tarjetas de contenido, basadas en código).
> - [ ] Flujo de datos configurado correctamente para los conjuntos de datos de evento y perfil.
> - [ ]: identidad y consentimiento implementados y validados con Assurance.
> - [ ] El token push registro y seguimiento validado de extremo a extremo.
> - [ ] Las tarjetas en la aplicación o contenido se muestran validadas en un dispositivos.
> - [ ] Configuración guiada de canal utilizada para nuevas implementaciones o configuración alineada manualmente con los pasos documentados.



## Configuración de canal de Adobe Systems Journey Optimizer

### En aplicación, Push y WhatsApp

Configura tus **canales** móviles utilizando la secuencia de canal guiada funcionalidad. Entiende cómo configurar el canal **de** WhatsApp:

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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3433053/?format=jpeg&nocache=1763594622823" alt="Configuración de canales guiada"
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3470268/?format=jpeg&nocache=1763594622814" alt="Configuración del canal de WhatsApp"
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3413355?format=jpeg&nocache=1763594624036" alt="Configuración de credenciales de API de SMS y superficies de canal"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" target="_blank" rel="referrer" title="Configuración de credenciales de API de SMS y superficies de canal">Configurar las credenciales de la API de SMS y canal superficies</a>
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3431625/?format=jpeg&nocache=1763594624067" alt="Configuración de un proveedor de SMS personalizado"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" target="_blank" rel="referrer" title="Configuración de un proveedor de SMS personalizado">Configuración de un proveedor de SMS personalizado</a>
                    </p>
                    <p class="is-size-6">Aprenda a configurar proveedores de SMS personalizados en Journey Optimizer, configurar credenciales de API y webhooks, administrar palabras clave de inclusión/exclusión y iniciar campañas personalizadas.</p>
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3428872/?format=jpeg&nocache=1763594624083" alt="Configuración de credenciales de API de MMS y superficies de canal"
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3464755/?format=jpeg&nocache=1763594624043" alt="Configuración de RCS en Journey Optimizer"
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

## Publicaciones de blog

- [Usar CDN personalización del lado del cliente (ODD) en dispositivos móviles para personalizar más rápido.](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/using-cdn-based-client-side-personalization-odd-on-mobile-for/ba-p/761626?profile.language=es)
- [Mobile Activation para Adobe Experience Cloud](https://experienceleaguecommunities.adobe.com/t5/adobe-target-blogs/mobile-activation-for-adobe-experience-cloud/ba-p/541595?profile.language=es)

## Garantice el cumplimiento de las leyes de privacidad y las directrices de la plataforma.

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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/29708/?format=jpeg&nocache=1763594624934" alt="Información general sobre el marco de gobernanza de datos"
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/29709?format=jpeg&nocache=1763594624932" alt="Clasificación de datos mediante etiquetas"
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/32977/?format=jpeg&nocache=1763594624933" alt="Creación de políticas de uso de datos"
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

## Errores comunes implementación y cómo evitarlos

La mayoría de los problemas móviles se originan en **la configuración** del SDK o del recopilación de datos, no en los recorridos o las campañas de Journey Optimizer. Utilice la siguiente tabla para identificar qué va mal y, a continuación, amplíe la sección correspondiente para obtener más detalles.

### Problemas de un vistazo

| # | Problema/síntoma | Escollo común | Solucionar de un vistazo |
|---|----------------------------------------------|-----------------------------------------------------|------------------------------------------|
| 1 | Se produce un error en la configuración del canal guiado; tráfico nula o baja | [Las versiones o extensiones de SDK no están alineadas](#1-sdk-versions-and-extensions-not-aligned-with-channel-requirements) | Actualizar versiones de SDK/extensión; validar en Assurance |
| 2 | Error de seguimiento de lotes; errores en AEP | [Flujos de datos o conjuntos de datos mal configurados](#2-misconfigured-datastreams-or-datasets) | Asignar eventos a evento conjunto de datos y perfiles a perfil conjunto de datos |
| 3 | Los viajes no disparan; personalización extraño | [Falta identidad o consentimiento o inconsistencia](#3-missing-or-inconsistent-identity-and-consent) | Implementar Edge Identity &amp; Consent; verificar en Aseguramiento |
| 4 | No hay envío push ni se abre en los informes | [El token push registro o seguimiento roto](#4-push-token-registration-and-tracking-not-wired-correctly) | Corregir el registro de tokens y la seguimiento de interacción mediante SDK |
| 5 | No hay impresiones en la aplicación a pesar de las campañas activas | [No se muestran mensajes en la aplicación ni tarjetas de contenido](#5-in-app-messages-or-content-cards-not-displaying) | Compruebe las extensiones de mensajería, los déclencheur y las respuestas de decisión de Assurance |

### Guía detallada por escollo

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
   - ¿Se envían eventos a la red de Edge y se confirma?

**Cómo corregir**

- Actualice a las versiones de extensión de Mobile SDK y Journey Optimizer compatibles.
- Vuelva a compilar la aplicación, conéctese de nuevo a Assurance y ejecute de nuevo la configuración del canal guiado.

Ver: [Configurar móvil y web](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config)

</details>


<details id="2-misconfigured-datastreams-or-datasets">
<summary><strong>2. Flujos de datos o conjuntos de datos mal configurados</strong></summary>

**Lo que notarás**

- Los eventos o lotes de push seguimiento fallan en Platform conjuntos de datos.
- Errores de ingesta de datos (por ejemplo, &quot;Las actualizaciones no son compatibles con los eventos&quot;).
- Los informes push o en la aplicación muestran poca o ninguna seguimiento.

**Qué comprobar**

- ¿Alguien ha cambiado **los esquemas del sistema o los conjuntos** de datos creados para Journey Optimizer seguimiento?
- En el **flujo de** datos:
   - ¿Se asignan experiencia eventos a un **conjunto de datos evento**?
   - ¿Se asignan perfil atributos a una **conjunto de datos perfil**?

**Cómo solucionarlo**

- No edite los datasets/esquemas del sistema creados por AJO.
- Corrija la asignación del flujo de datos (eventos → evento conjunto de datos, perfiles → perfil conjunto de datos).
- Prefiera la configuración del canal guiado o los pasos documentados del flujo de datos en lugar de los cambios anuncios específicos.

Vea: [Flujo de notificaciones push en Adobe Systems Journey Optimizer](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/channels/push/push-config/push-gs)

</details>


<details id="3-missing-or-inconsistent-identity-and-consent">
<summary><strong>3. Identidad y consentimiento faltantes o incoherentes</strong></summary>

**Lo que notarás**

- Los recorridos no se desencadenan como se espera para los usuarios de la aplicación.
- La personalización no coincide con el comportamiento del usuario en otros canales.
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

Vea: [Implementación del consentimiento para implementaciones de SDK Platform Mobile](https://experienceleague.adobe.com/es/docs/platform-learn/implement-mobile-sdk/app-implementation/consent)

</details>


<details id="4-push-token-registration-and-tracking-not-wired-correctly">
<summary><strong>4. El token de inserción registro y seguimiento no está cableado correctamente</strong></summary>

**Lo que notarás**

- Los usuarios nunca reciben notificaciones push, igualado aunque se ejecuten campañas o viajes.
- Los informes push no muestran aperturas, descartes ni interacciones.

**Qué comprobar**

- ¿La aplicación registra el token de inserción con la extensión Journey Optimizer?
   - ¿En la primera instalación?
   - ¿Después de cada actualización de aplicación?
   - ¿Cada vez que el sistema operativo actualiza el token?
- Cuando un usuario abre o descarta una notificación, ¿ve el seguimiento de eventos en Assurance?

**Cómo corregir**

- añadir o corrija el código que:
   - Registra el token a través de la extensión móvil Journey Optimizer cada vez que se crea o se actualiza.
   - Envía eventos de interacción push (abrir, descartar, acciones personalizadas) mediante Mobile SDK.
- Utilice Assurance para confirmar que los eventos de registro y seguimiento se activan según lo esperado.

Ver: [Flujo de notificaciones push en Adobe Journey Optimizer](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/channels/push/push-config/push-gs)

</details>


<details id="5-in-app-messages-or-content-cards-not-displaying">
<summary><strong>5. Mensajes en la aplicación o tarjetas de contenido que no muestran </strong></summary>

**Lo que notará**

- Los mensajes en la aplicación o las tarjetas de contenido nunca aparecen, a pesar de las campañas o los recorridos activos.
- El informe muestra 0 impresiones.

**Qué comprobar**

- ¿Están **Journey Optimizer mobile messaging / in-app extension** y **Messaging SDK** instalados y registrados en la aplicación?
- En la configuración de etiquetas **&#x200B;**:
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
- [Crear y enviar mensajes en la aplicación](https://experienceleague.adobe.com/es/docs/platform-learn/implement-mobile-sdk/experience-cloud/journey-optimizer/journey-optimizer-inapp)
- [Configuración de la compatibilidad con tarjetas de contenido en Mobile SDK](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp)

</details>


## Lista de verificación de preparación de una línea

Antes de entregar la aplicación a los especialistas en marketing, confirme en **[Garantía](https://developer.adobe.com/client-sdks/home/base/assurance/)** que:

- Se cargan las extensiones Core SDK + Journey Optimizer,
- Los eventos fluyen en el flujo de datos y conjuntos de datos correctos,
- La identidad y el consentimiento están presentes en todos los eventos clave.
- Se realiza un seguimiento de los tokens push y de las interacciones, y
- Al menos un mensaje prueba en la aplicación o contenido tarjeta se ha mostrado y registrado como