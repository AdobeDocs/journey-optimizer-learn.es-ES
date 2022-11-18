---
title: 'Crear un anuncio de colección de verano: Desafío'
description: Envíe un anuncio de colección de verano a un segmento de los clientes existentes para promocionar la nueva colección de verano de Luma.
kt: 8109
role: User
level: Beginner
last-substantial-update: 2022-11-16T00:00:00Z
hide: true
source-git-commit: d1b4aa69e323d9a6112d2273ea5770c42b044d13
workflow-type: tm+mt
source-wordcount: '1250'
ht-degree: 2%

---


# Crear un anuncio de colección de verano: Desafío

![Cartel de anuncio de colección de verano de AJO](/help/challenges/assets/email-assets/luma-transactional-onboarding-3.png)

| Desafío | Crear un anuncio de colección de verano |
|---|---|
| Grupo de usuarios | Administrador de recorridos |
| Capacidades necesarias | <ul><li>[Creación de segmentos](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=en)</li><li> [Importación y creación de contenido de correo electrónico HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html?lang=en)</li><li>[Caso de uso: Segmento de lectura](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=en)</li> |
| Recursos que se van a descargar | [Archivos de correo electrónico de recopilación estacional](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip) |

>[!NOTE]
> Los ejercicios se desarrollaron sobre la base de los datos de la muestra de Luma. Se recomienda configurar un simulador para pruebas de formación, configurado con los datos de ejemplo. Visite el tutorial [Importación de datos de ejemplo en Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/import-sample-data.html?lang=es) para obtener instrucciones detalladas.

## La historia

Luma, una empresa de ropa deportiva ficticia, busca promocionar su última colección de ropa y equipo y dirigir las ventas a los clientes existentes. Luma lanza la nueva colección de verano y desea dirigirse específicamente a diferentes segmentos de clientes.

## Su desafío

El equipo de marketing de Luma le pedirá que implemente una campaña de marketing de recopilación de verano en Journey Optimizer.

Su desafío es crear un recorrido en Journey Optimizer. Específicamente, debe crear el segmento requerido, crear cuatro mensajes y crear el recorrido.

>[!NOTE]
> Si está trabajando en un simulador para pruebas de formación compartido, se recomienda añadir el nombre o las iniciales como prefijo al nombre de cualquier elemento que cree.

### Paso 1: Definir el segmento: clientes activos

>[!BEGINTABS]

>[!TAB Tarea]

Cree un segmento en Journey Optimizer llamado **su nombre: Clientes activos**.

* El segmento solo debe incluir clientes de Luma activos.
* Los clientes activos se definen como clientes que tienen un nivel en el programa de fidelidad de Luma (plata, oro, platino o diamante).


>[!TAB Criterios de éxito]

En el generador de segmentos, puede ver el número estimado de perfiles cualificados. Si está trabajando en un simulador para pruebas de formación que utiliza datos de ejemplo de Luma, la variable [!UICONTROL perfiles cualificados estimados] debe tener unos 292 perfiles de 500.

**Se ha añadido un perfil correspondiente al segmento:**

Puede comprobar que los perfiles que se han agregado al segmento cumplen los requisitos navegando a uno de los perfiles enumerados en la vista de detalles del segmento.

En la página de perfil, marque la casilla [!UICONTROL Atributos] para confirmar que cumplen los requisitos: El nivel debe ser plata, oro, platino o diamante.

![Atributos de perfil](assets/C1-S1-profile-attributes.png)

También puede marcar la [!UICONTROL Pertenencia a segmentos] pestaña: El segmento debe aparecer en la lista.

>[!NOTE]
>Puede tardar hasta 24 horas en aparecer la pertenencia al segmento para los perfiles existentes, ya que los perfiles existentes deben rellenarse.

![Pertenencia a segmentos](assets/C1-S1-profile-segment-membership.png)

>[!TAB Comprobar su trabajo]

Campos de segmento: [!UICONTROL Atributos] > [!UICONTROL Perfil individual XDM] > [!UICONTROL Fidelidad] > [!UICONTROL Nivel]

Este es el aspecto que debería tener el segmento:

![Segmento: clientes activos](/help/challenges/assets/C1-S1.png)

Compruebe el código en la esquina inferior derecha de la pantalla Editar segmento, en Eventos.

El código debería tener este aspecto:

```javascript
loyalty.tier.equals("diamond", false) or loyalty.tier.equals("gold", false) or loyalty.tier.equals("platinum", false) or loyalty.tier.equals("silver", false)
```

>[!ENDTABS]


### Paso 2: Crear el Recorrido: anuncio de la colección de verano

>[!BEGINTABS]

>[!TAB Tarea]

Envíe un anuncio de recopilación de verano a un segmento de los correos electrónicos de los clientes existentes que promocionen la nueva colección de verano de Luma.&quot;

Una agencia le proporcionó cuatro archivos HTML con el diseño de los correos electrónicos: [Descargar los archivos de correo electrónico de la colección estacional](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip)

Cree un recorrido llamado `(your name) - Summer collection announcement` en función de las siguientes directrices:

1. Enviar Luma: Nuevo mensaje de correo electrónico de anuncio de recopilación estacional al segmento Clientes activos de Luma, que contiene el 10 % de la audiencia como grupo de control
   * Título del mensaje `(your name)_Luma New Seasonal Collection Announcement`.
   * Línea de asunto `(recipient's first name), the new Luma collection is here!`.
   * Utilice el archivo de HTML proporcionado *SeasonalCollectionEmail.html* para el cuerpo del correo electrónico.
2. Espere dos días y envíe un mensaje de correo electrónico de seguimiento con contenido de destino más específico:
   * Los clientes varones deben recibir la variable **Correo electrónico de recopilación de Luma Men**
      * Título del mensaje: **(su nombre) Colección de hombres de Luma**
      * Línea de asunto: **(nombre del destinatario), explorar el nuevo equipo atlético masculino!**
      * Cuerpo del correo electrónico: *MensCollectionEmail.html* para el cuerpo del correo electrónico.
   * Las clientes femeninas deben recibir el **Correo electrónico de la colección de mujeres de Luma**
      * Título del mensaje: **(su nombre) Colección de mujeres de Luma**
      * Línea de asunto: **(nombre del destinatario), explore Luma&#39;s Women Collection!**
      * Cuerpo del correo electrónico: *WomensCollectionEmail.html*
   * Otros clientes deben recibir la variable **Luma: 20 % de descuento en el correo electrónico de recopilación**
      * Título del mensaje: **(su nombre)_Luma - 20 % de descuento en Collection**
      * Línea de asunto:**(nombre del destinatario), disfrute de un 20% de descuento en las ventas.**
      * Cuerpo del correo electrónico: *20OOffCollectionEmail.html*
3. Después de enviar los correos electrónicos de destino anteriores, espere dos días para que se abra el correo electrónico
4. Si el correo electrónico de destino no se abre en un plazo de 2 días, envíe la variable **Luma - 20 %off Correo electrónico de recopilación** como un intento final de retargeting


>[!TAB Criterios de éxito]

#### Vista previa de los correos electrónicos

**Mensaje de correo electrónico n.º 1 - Nuevo anuncio de recopilación estacional**

Obtenga una vista previa del correo electrónico mediante el área de nombres de identidad: *Correo electrónico* y el valor de identidad: *Jenna_Palmer9530@emailsim.io*

* La línea de asunto debe decir: Jenna, la nueva colección Luma está aquí!
* El cuerpo del correo electrónico debe coincidir con lo que se ha visto en la vista previa: [Nuevo anuncio de colección estacional](/help/challenges/assets/SeasonalCollectionEmail.html)


**Mensaje de correo electrónico n.º 2 - Colección de hombres de Luma**

Envíe una prueba a usted mismo

* Escriba su dirección de correo electrónico
* Seleccione el perfil de prueba: Chris_Scott1244@emailsim.io

Debe recibir un correo electrónico. La línea del asunto debería decir &quot;Chris, ¡explora el nuevo equipo atlético masculino!&quot; y el cuerpo del correo electrónico debe coincidir con lo que se ha visto en la vista previa: [Colección Luma Men](/help/challenges/assets/email-assets/MensCollectionEmail.html)

**Mensaje de correo electrónico 3 - Colección de mujeres de Luma**

Obtenga una vista previa del correo electrónico mediante el área de nombres de identidad: *Correo electrónico* y el valor de identidad: *Jenna_Palmer9530@emailsim.io*

* La línea de asunto debe decir: *Jenna, ¡explora la colección de mujeres de Luma!*
* El cuerpo del correo electrónico debe coincidir con lo que se ha visto en la vista previa: [Colección de mujeres de Luma](/help/challenges/assets/email-assets/WomensCollectionEmail.html)


**Mensaje de correo electrónico 4 - Luma 20 % de la recopilación**

Obtenga una vista previa del correo electrónico mediante el área de nombres de identidad: *Correo electrónico* y el valor de identidad: *Benny_Steer4909@emailsim.io*

* La línea de asunto debe decir: *Benny, disfruta 20% de descuento!*
* El cuerpo del correo electrónico debe coincidir con lo que se ha visto en la vista previa: [Luma 20 % de descuento en la recogida](/help/challenges/assets/email-assets/20OOffCollectionEmail.html)

**¡No olvides publicar tus correos electrónicos!**

#### Prueba del recorrido

>[!IMPORTANT]
>
>Antes de configurar el recorrido en modo de prueba:
>
>1. Asegúrese de que la actividad Leer segmento tenga el espacio de nombres establecido en Correo electrónico
>1. Para cada correo electrónico, anule los parámetros de correo electrónico predeterminados para los correos electrónicos de modo que se envíen a su dirección de correo electrónico:
>1. Muestre los valores ocultos haciendo clic en el símbolo de ojo.
>1. En los parámetros de correo electrónico, haga clic en el símbolo T (habilitar anulación de parámetros)

   >
   >      ![Anular parámetros de correo electrónico](/help/challenges/assets/c3-override-email-paramters.jpg)
> 
>1. Haga clic en el campo Dirección
>1. En la siguiente pantalla, añada su dirección de correo electrónico entre paréntesis: *yourname@yourdomain* en el editor de expresiones y haga clic en aceptar.

>


Pruebe el recorrido y envíe los correos electrónicos a su propia cuenta:

1. Poner el recorrido en modo de prueba
2. Seleccionar un solo perfil a la vez
3. Tiempo de espera: Establezca el temporizador en 120 segundos (escríbalo en el campo ).
4. entrada de perfil de déclencheur
5. Puede probar cada rama utilizando una de las siguientes direcciones de correo electrónico como identificadores de perfil:
   * Mujeres: Jenna Palmer: Jenna_Palmer9530@emailsim.io
   * Hombre: Chris Scott: Chris_Scott1244@emailsim.io
   * Sexo no especificado: Benny Steer: Benny_Steer4909@emailsim.io

6. Una vez que déclencheur la entrada del perfil, debe recibir el primer correo electrónico, el encabezado debe personalizarse según el perfil que elija.
7. El recorrido debe continuar en la rama respectiva y usted debe recibir el correo electrónico relacionado (por ejemplo, si elige Jenna, debe recibir el correo electrónico &quot;Colección de mujeres de Luma&quot;).
8. Abra el segundo correo electrónico y el recorrido debería finalizar
9. Puede repetir el paso 4. - 7. para que los tres perfiles comprueben si todas las ramas funcionan correctamente.
10. Para probar los tiempos de espera, establezca el tiempo de espera en 30 segundos y vuelva a almacenar en déclencheur la entrada.
11. No abra los correos electrónicos que reciba (no previsualice el correo electrónico (!)) y deje que transcurra el tiempo de espera.

Debe recibir los siguientes correos electrónicos:

* Luma: Nuevo anuncio de recopilación estacional
* Según el perfil de prueba que haya utilizado, debe recibir uno de los siguientes correos electrónicos:
   * Jenna: Colección de mujeres de Luma
   * Chris: Colección Luma Men
   * Benny: Luma: 20 % de descuento en la recopilación
* Si no ha abierto el segundo correo electrónico: La recopilación de Luma (20 % de descuento)

>[!TAB Compruebe su trabajo]

Este es el aspecto que debería tener el recorrido:

![ Recorrido ](/help/challenges/assets/c3-j1-journey.png)

**Condición - Grupo de control:**

![Grupo de control](/help/challenges/assets/c3-j1-condition-control-group.png)

**Condición - Sexo:**\

![Condición - Sexo](/help/challenges/assets/c3-j1-condition-gender.png)
>[!ENDTABS]
