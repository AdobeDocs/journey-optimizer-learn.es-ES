---
title: 'Crear un anuncio de colección de verano: desafío'
description: Envíe un anuncio de la colección de verano a un segmento de clientes existentes para promocionar la nueva colección de verano de Luma.
kt: 8109
role: User
level: Beginner
last-substantial-update: 2022-11-16T00:00:00Z
hide: true
exl-id: ae457be7-2c67-4950-a072-1d7030b0e17b
source-git-commit: cfd438e198fdf62859569eed0c6ac22087ddbc75
workflow-type: tm+mt
source-wordcount: '1176'
ht-degree: 2%

---

# Crear un anuncio de colección de verano: desafío

![Cartel de anuncio de colección de verano de AJO](/help/challenges/assets/email-assets/luma-transactional-onboarding-3.png)

| Desafío | Crear un anuncio de colección de verano |
|---|---|
| Grupo de usuarios | Administrador de recorridos |
| Capacidades necesarias | <ul><li>[Creación de segmentos](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=en)</li><li> [Importación y creación de contenido de correo electrónico HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html?lang=en)</li><li>[Caso de uso: Segmento de lectura](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=en)</li> |
| Recursos que se van a descargar | [Archivos de correo electrónico de recopilación estacional](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip) |

## La historia

Luma, una compañía de ropa deportiva ficticia, está promocionando su última colección de ropa y equipo y impulsando ventas para clientes existentes. Luma inicia la nueva colección de verano y desea dirigirse específicamente a diferentes segmentos de clientes.

## Su desafío

El equipo de marketing de Luma le pedirá que implemente una campaña de marketing de la colección de verano en Journey Optimizer. Su desafío es:

* Cree un segmento que defina qué perfiles cumplen los requisitos para recibir la promoción.
* Creación del recorrido.

### Paso 1: Definir el segmento: clientes activos

>[!BEGINTABS]

>[!TAB Tarea]

#### Cree un segmento en [!DNL Journey Optimizer]

* Cree un segmento en [!DNL Journey Optimizer] llamado *Clientes activos*.
* El segmento solo debe incluir clientes de Luma activos.
* Los clientes activos se definen como clientes que tienen un nivel en el programa de fidelidad de Luma (bronce, plata, oro o platino).


>[!TAB Criterios de éxito]

En el generador de segmentos, puede ver el número estimado de perfiles cualificados. Si está trabajando con los datos del simulador para pruebas de formación, tiene unos 753 perfiles cualificados de 1,29 K.

>[!NOTE]
>Puede tardar hasta 24 horas en aparecer la pertenencia al segmento para los perfiles existentes, ya que los perfiles existentes deben rellenarse.

**Se ha añadido un perfil correspondiente al segmento:**

Puede comprobar que los perfiles que se han agregado al segmento cumplen los requisitos navegando a uno de los perfiles enumerados en la vista de detalles del segmento.

En la página de perfil, marque la casilla [!UICONTROL Atributos] para confirmar que cumplen los requisitos: El nivel debe ser plata, oro, platino o diamante.

![Atributos de perfil](assets/C1-S1-profile-attributes.png)

También puede marcar la [!UICONTROL Pertenencia a segmentos] pestaña: El segmento debe aparecer en la lista.

![Pertenencia a segmentos](assets/C1-S1-profile-segment-membership.png)

>[!TAB Compruebe su trabajo]

Campos de segmento: [!UICONTROL Atributos] > [!UICONTROL Perfil individual XDM] > [!UICONTROL Fidelidad] > [!UICONTROL Nivel]

Este es el aspecto que debería tener el segmento:

![Segmento: clientes activos](/help/challenges/assets/C1-S1.png)

El código debería tener este aspecto:

```javascript
stringCompare("equals", loyalty.tier, ["diamond", "gold", "platinum", "silver"], false)
```

>[!ENDTABS]


### Paso 2: Creación del anuncio Recorrido - Colección de verano

>[!BEGINTABS]

>[!TAB Tarea]

#### Enviar el anuncio de la colección de verano

Una agencia le proporcionó cuatro archivos HTML con el diseño de los correos electrónicos:

* `SeasonalCollectionEmail.html`
* Correo electrónico de recopilación de Luma Men
* Correo electrónico de la colección de mujeres de Luma
* Luma: 20 % de descuento en el correo electrónico de recopilación

1. [Descargar los archivos de correo electrónico de la colección estacional](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip).

2. Cree un recorrido llamado *Luma: Anuncio de la colección de verano* en función de las siguientes directrices:

   1. Enviar *Luma: Nuevo anuncio de colección de verano* envíe un correo electrónico a la *Clientes activos* segmento, mantener el 10 % de la audiencia como grupo de control
      * Título del mensaje *Luma - Anuncio de colección de verano*
      * Línea de asunto *(nombre del destinatario), la nueva colección de verano de Luma está aquí!*
      * Utilice el archivo de HTML proporcionado `SeasonalCollectionEmail.html` para el cuerpo del correo electrónico.
   2. Espere dos días y envíe un mensaje de correo electrónico de seguimiento con contenido de destino más específico:
      * Los clientes varones deben recibir la variable **Colección Luma Men** correo electrónico.
         * Título del mensaje: *Colección Luma Men*
         * Línea de asunto: *(nombre del destinatario), explorar el nuevo equipo atlético masculino!*
         * Cuerpo del correo electrónico: `MensCollectionEmail.html` para el cuerpo del correo electrónico.
      * Las clientes femeninas deben recibir el **Colección de mujeres de Luma** correo electrónico.
         * Título del mensaje: *Colección de mujeres de Luma*
         * Línea de asunto: *(nombre del destinatario), explore Luma&#39;s Women Collection!*
         * Cuerpo del correo electrónico: `WomensCollectionEmail.html`
      * Otros clientes deben recibir la variable **Luma - 20 % de descuento en la recogida** correo electrónico.
         * Título del mensaje: *Luma - 20 % de descuento en la recogida*
         * Línea de asunto: *(nombre del destinatario), disfrute de un 20% de descuento en las ventas.*
         * Cuerpo del correo electrónico: `20OOffCollectionEmail.html`
   3. Después de enviar los correos electrónicos de destino anteriores, espere dos días para que se abra el correo electrónico
   4. Si el correo electrónico de destino no se abre en un plazo de 2 días, envíe la variable **Luma - 20 %off Correo electrónico de recopilación** como un intento final de retargeting


>[!TAB Criterios de éxito]

#### Vista previa de los correos electrónicos

**Mensaje de correo electrónico 1 - Luma - Anuncio de recopilación de verano**

Previsualice el correo electrónico:

1. Añadir un perfil de prueba: Louise Petti:
   1. Área de nombres de identidad: *ID de Luma CRM*
   2. Valor de identidad: *d1f132f9f9502bba047a6ec86c4b61f9*

Resultado:
* La línea de asunto debe decir: Louise, la nueva colección Luma está aquí!
* El cuerpo del correo electrónico debe coincidir con lo que se ha visto en la vista previa: [Nuevo anuncio de colección estacional](/help/challenges/assets/email-assets/SeasonalCollectionEmail.html)


**Mensaje de correo electrónico n.º 2 - Colección de hombres de Luma**

Envíe una prueba a usted mismo:

1. Añadir un perfil de prueba: Stanleigh Stooke:
   1. Área de nombres de identidad: *ID de Luma CRM*
   1. Valor de identidad: `4f34057d9d9e792c28ba18ecae378e98`
1. Seleccione el perfil de prueba: Stanleigh Stooke.
1. Envíe una prueba a usted mismo.

Resultado:\
Debe recibir un correo electrónico. La línea de asunto debe decir *Stanleigh, explorar el nuevo equipo atlético masculino!* y el cuerpo del correo electrónico debe coincidir con lo que se ha visto en la vista previa: [Colección Luma Men](/help/challenges/assets/email-assets/MensCollectionEmail.html)

>[!NOTE]
>Puede tardar un par de minutos en recibir la prueba.

**Mensaje de correo electrónico 3 - Colección de mujeres de Luma**

Vista previa del correo electrónico con el perfil de prueba *Louise Petti.*

* La línea de asunto debe decir: *Louise, explora la colección de mujeres de Luma.*
* El cuerpo del correo electrónico debe coincidir con lo que se ha visto en la vista previa: [Colección de mujeres de Luma](/help/challenges/assets/email-assets/WomensCollectionEmail.html)


**Mensaje de correo electrónico 4 - Luma 20 % de la recopilación**

Vista previa del correo electrónico con el perfil de prueba *Louise Petti.*

* La línea de asunto debe decir: *Louise, disfruta de un 20% de descuento en las ventas!*
* El cuerpo del correo electrónico debe coincidir con lo que se ha visto en la vista previa: [Luma 20 % de descuento en la recogida](/help/challenges/assets/email-assets/20OOffCollectionEmail.html)


#### Prueba del recorrido

>[!IMPORTANT]
>
>Antes de configurar el recorrido en modo de prueba:
>
>1. Asegúrese de que la variable [!UICONTROL Leer Actividad de segmentos] tiene el espacio de nombres establecido en **ID de Luma CRM (lumaCrmId)**
>1. Para cada correo electrónico, anule los parámetros de correo electrónico predeterminados para los correos electrónicos de modo que se envíen a su dirección de correo electrónico:
   >    * Muestre los valores ocultos haciendo clic en el símbolo de ojo.
   >    * En los parámetros de correo electrónico, haga clic en el símbolo T (habilitar anulación de parámetros).

      >
      >      ![Anular parámetros de correo electrónico](/help/challenges/assets/c3-override-email-paramters.jpg)
   > 
   >    * Haga clic en [!UICONTROL Dirección] field
   >    * En la siguiente pantalla, añada su dirección de correo electrónico entre paréntesis: `"yourname@yourdomain"` en el editor de expresiones y haga clic en aceptar.

>


Pruebe el recorrido y envíe los correos electrónicos a su propia cuenta:

1. Ponga el recorrido en modo de prueba.
1. Seleccione un solo perfil a la vez.
1. Tiempo de espera: Establezca el temporizador en 120 segundos (escríbalo en el campo ).
1. entrada de perfil de déclencheur
1. Puede probar cada rama utilizando una de las siguientes *ID de Luma CRM* como identificadores de perfil:
   * Mujeres: Leora Dietsche, valor de identidad:`a8f14eab3b483c2b96171b575ecd90b1`
   * Hombre: Existencia de código, valor de identidad: `4f34057d9d9e792c28ba18ecae378e98`
   * Sexo no especificado: Louise Petti, valor de identidad: `d1f132f9f9502bba047a6ec86c4b61f9`

1. Después de almacenar en déclencheur la entrada del perfil, debe recibir el primer correo electrónico. El encabezado debe personalizarse según el perfil que elija.
1. El recorrido debe continuar en la rama correspondiente y debe recibir el correo electrónico relacionado (por ejemplo, si elige *Jenna*, debe recibir la variable *Colección de mujeres de Luma* correo electrónico).
1. Abra el segundo correo electrónico y el recorrido debería finalizar.
1. Puede repetir el paso 4. - 7. para que los tres perfiles comprueben si las ramas funcionan correctamente.
1. Para probar los tiempos de espera, establezca el tiempo de espera en 30 segundos y vuelva a almacenar en déclencheur la entrada.
1. No abra los correos electrónicos que reciba (no previsualice el correo electrónico (!)) y deje que transcurra el tiempo de espera.

Debe recibir los siguientes correos electrónicos:

* Luma: Nuevo anuncio de recopilación estacional
* Según el perfil de prueba que haya utilizado, debe recibir uno de los siguientes correos electrónicos:
   * Leora: Colección de mujeres de Luma
   * Stanleigh: Colección Luma Men
   * Louise: Luma: 20 % de descuento en la recopilación
* Si no ha abierto el segundo correo electrónico: La recopilación de Luma (20 % de descuento)

>[!TAB Compruebe su trabajo]

Este es el aspecto que debería tener el recorrido:

![ Recorrido ](/help/challenges/assets/c3-j1-journey.png)

**Condición - Grupo de control:**

![Grupo de control](/help/challenges/assets/c3-j1-condition-control-group.png)

**Condición - Sexo:**\

![Condición - Sexo](/help/challenges/assets/c3-j1-condition-gender.png)
>[!ENDTABS]
