---
source-git-commit: fc279f2ff41f624e4a6a0c4c930cedfcc2745dc5
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 3%
---
# Actividades en directo

## ¿Qué es?

Las **actividades en vivo** le permiten entregar actualizaciones persistentes en tiempo real que mantienen a los clientes informados a medida que avanza una actividad, como un pedido en preparación, una entrega en tránsito o un viaje en camino. En lugar de enviar una nueva notificación por cada actualización, se crea una sola actividad en directo, que luego se actualiza y finaliza a medida que evoluciona la actividad, manteniendo la pantalla de bloqueo o la notificación del cliente sincronizada con lo que está ocurriendo.

Adobe Journey Optimizer admite actividades activas en las dos plataformas móviles principales:

* **[Actividades de iOS Live](/help/channels/ios-live-activities.md)**: Actualizaciones en tiempo real y enriquecidas en la pantalla de bloqueo de iPhone y Dynamic Island.
* **[Actualizaciones de Android Live](/help/channels/android-live-updates.md)**: actualizaciones persistentes en tiempo real en el sombreado de notificaciones de Android.

Para configurar Mobile SDK y usar las API para iniciar, actualizar y finalizar experiencias en directo en los recorridos de los clientes, consulta [Configurar la actividad en directo](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/live-activity/configure-live-activity/mobile-live-configuration-sdk){target="_blank"}.

## Casos de uso

Elija actividades en directo como su canal preferido cuando necesite:

| # | Ventaja | Por qué | Ejemplos de casos de uso |
|---|---------|-----|-------------------|
| 1 | Progreso continuo de un vistazo | Las actualizaciones aparecen directamente en la pantalla de bloqueo o en la pantalla de notificaciones de Dynamic Island, sin que el usuario abra la aplicación | <ul><li>Seguimiento del envío de alimentos</li><li>Estado de llamada de paseo</li><li>Puntuaciones deportivas en directo</li></ul> |
| 2 | Reducir la fatiga de notificaciones | Se actualiza una sola actividad en lugar de activar notificaciones push repetidas | <ul><li>Fases de preparación y entrega de pedidos</li><li>Actualizaciones de embarque y puerta de vuelo</li></ul> |
| 3 | Contexto de corta duración y tiempo crítico | Ideal para actividades con un comienzo y un final claros | <ul><li>Cuenta atrás de recogida en bordillo</li><li>Sesiones de entrenamiento o temporizador</li></ul> |
| 4 | IU nativa e intuitiva | Utiliza superficies nativas del sistema operativo (Dynamic Island, pantalla de bloqueo, tono de notificación) para una experiencia de alta visibilidad y baja fricción | <ul><li>Seguimiento de paquetes</li><li>Actualizaciones en cola o en tiempo de espera</li></ul> |

## Cuando *no* use actividades activas

* Para estados de larga duración o abiertos sin un final claro: finalice la actividad una vez que se complete el proceso subyacente.
* Para contenido promocional o de marketing: en su lugar, utilice notificaciones push, mensajes en la aplicación o tarjetas de contenido.
* Cuando la cadencia de la actualización es muy alta: el sistema operativo puede limitar las actualizaciones frecuentes o hacer ruido al usuario.
* Si la aplicación no admite las versiones de sistema operativo mínimas requeridas para las actividades de iOS Live o las actualizaciones de Android Live.
