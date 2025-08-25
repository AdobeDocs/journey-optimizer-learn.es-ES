---
source-git-commit: 0ce6d5013bbcf55e49ae920670919f6929a142ec
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---
# Mensajes en la aplicación

## ¿Qué son los mensajes en la aplicación?

Los mensajes en la aplicación son mensajes que aparecen dentro de una aplicación mientras el usuario los está utilizando activamente. Son mensajes de tipo superposición que se encuentran en la parte superior de la aplicación. No aparecen en la pantalla de bloqueo ni fuera de la aplicación; en su lugar, aparecen como titulares, ventanas emergentes o tarjetas pequeñas mientras el usuario explora la aplicación.

Los mensajes en la aplicación se activan mediante acciones o condiciones específicas del usuario, como ver una página determinada, completar una compra o formar parte de un segmento de audiencia segmentado.


Por ejemplo:

* Un juego podría mostrar una ventana emergente que explica una nueva función en el momento en que el usuario la desbloquea.
* Una aplicación de compras puede mostrar un banner con un código de cupón mientras el usuario navega por los artículos.
* Una aplicación de medios sociales puede mostrar un mensaje sugiriendo al usuario que siga las nuevas cuentas.

## Casos de uso

| **Beneficios** | **Por qué** | **Casos de uso de ejemplo** |
|----------------------------------|------------------------------------------------------------------------|----------------------------------------------------------------------------------------|
| Alta participación del usuario | Registra a los usuarios mientras están activos en la aplicación, lo que garantiza una mayor visibilidad y acción | <ul><li>Tutoriales de incorporación</li><li>Anuncios de funcionalidades</li><li>Ventanas emergentes de soporte en tiempo real</li></ul> |
| Relevante desde el contexto | Permite activar mensajes mediante el comportamiento del usuario, para que sean oportunos y personalizados | <ul><li> Ampliar venta después del uso de funciones</li><li> Empujones por inactividad</li><li> Mensajes de error o de éxito</li></ul> |
| Entrega en tiempo real | Habilita la comunicación inmediata para actualizaciones urgentes o críticas | <ul><li> Interrupciones del sistema</li><li>Confirmaciones de transacción</li><li>Errores de pago</li></ul> |
| Sin dependencia de canales externos | Mantiene la experiencia del usuario contenida dentro del producto sin depender del correo electrónico/SMS | <ul><li> Recordatorios de finalización del tutorial</li><li>Alertas de caducidad de prueba</li></ul> |
| Mejor potencial de conversión | Los mensajes colocados en contexto se convierten mejor que los mensajes fuera de la plataforma | <ul><li> Mensajes de actualización después de alcanzar los límites del plan</li><li>Encuestas en la aplicación</li></ul> |
| Personalización y segmentación | Se puede personalizar según los datos de usuario o los eventos de la aplicación | <ul><li> Mensajes adaptados al nivel de usuario o de actividad</li><li> Alertas específicas de funciones </li></ul> |
| No intrusivo (cuando está bien diseñado) | Permite una comunicación sutil pero eficaz sin interrumpir el flujo del usuario | <ul><li> Tooltips</li><li>Slide-ins con actualizaciones</li><li>Empujones del widget de chat</li></ul> |


## Cuando *no* desee usar la comunicación en la aplicación

* **El usuario no está usando activamente la aplicación**\
  Los mensajes en la aplicación no se verán si el usuario no ha iniciado sesión o no participa en el producto en este momento. En su lugar, utilice el correo electrónico o push.
* **Problemas críticos o urgentes que requieren atención inmediata**\
  Para mensajes urgentes (por ejemplo, alertas de seguridad, fallos de pago), utilice canales que puedan llegar al usuario fuera de la aplicación, como SMS o correo electrónico.
* **Comunicaciones reglamentarias o legales**\
  Los mensajes relacionados con el cumplimiento (por ejemplo, actualizaciones de términos, cambios de directivas) pueden requerir confirmación de entrega y lectura, lo que resulta más adecuado para el correo electrónico.
* **Reactivación de cuenta o campañas de recuperación**\
  Si el usuario está inactivo o se pierde, no verá mensajes en la aplicación. Utilice campañas de renovación de la participación por correo electrónico o notificaciones push.
* **Actualizaciones transaccionales de gran volumen**\
  Las notificaciones, como las actualizaciones de envío o los recibos, suelen enviarse mejor por correo electrónico para su archivo y comodidad.
* **El uso excesivo provoca ceguera o molestia en los banners**\
  Bombardear a los usuarios con demasiados mensajes en la aplicación puede dañar el UX y provocar frustración o mensajes ignorados.
* **Sin conectividad / escenarios sin conexión**\
  La aplicación depende de que el usuario esté en línea y en la sesión, y no ayudará en los entornos sin conexión primero.

