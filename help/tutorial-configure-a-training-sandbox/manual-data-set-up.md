---
title: Configuración manual de la estructura de datos
description: Cree los espacios de nombres de identidad necesarios y defina la estructura de datos de ejemplo de Luma.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
exl-id: de870229-d9a6-4051-9f76-13d402cce3b4
source-git-commit: b358ede4a9855b290ce4efa8611173f44e689b61
workflow-type: tm+mt
source-wordcount: '1063'
ht-degree: 8%

---

# Configuración manual de datos

En esta sección, se crean los espacios de nombres de identidad necesarios y se define la variable [!DNL Luma] estructura de datos de ejemplo creando la variable [[!UICONTROL esquemas]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=es).

>[!TIP]
>Ver el tutorial en vídeo [Asigne identidades](/help/set-up-data/map-identities.md) antes de empezar.

## Paso 1: Crear áreas de nombres de identidad

En este paso, se crean áreas de nombres de identidad para la variable [!DNL Luma] campos de identidad personalizados con nombre `lumaLoyaltyId`, `lumaCrmId`y `lumaProductSKU`. Las áreas de nombres de identidad desempeñan un papel fundamental en la creación de perfiles de clientes en tiempo real, ya que dos valores coincidentes en el mismo espacio de nombres permiten que dos fuentes de datos formen un gráfico de identidad.

Comience creando un [!UICONTROL namespace] para el [!DNL Luma Loyalty ID] esquema:

1. En la interfaz de usuario de Journey Optimizer, vaya a ***[!UICONTROL Cliente]** > **[!UICONTROL Identidades]** en el panel de navegación izquierdo.

1. Select **[!UICONTROL Crear área de nombres de identidad]**.

1. Proporcione los siguientes detalles:

   | Nombre para mostrar | Símbolo de identidad | Tipo |
   |---|---|---|
   | `Luma Loyalty ID` | `lumaLoyaltyId` | [!UICONTROL ID entre dispositivos] |

1. Seleccione **[!UICONTROL Crear]**.

   ![Crear espacios de nombres](assets/createNamespace.png)

1. Cree dos áreas de nombres más siguiendo los mismos pasos:

   | Nombre para mostrar | Símbolo de identidad | Tipo |
   |---|---|---|
   | `Luma CRM ID` | `lumaCrmId` | [!UICONTROL ID entre dispositivos] |
   | `Luma Product SKU` | `lumaProductSKU` | [!UICONTROL Identificador de no personas] |

## Paso 2: Crear esquemas

En este paso, se define la estructura de los datos de ejemplo creando seis [[!UICONTROL esquemas]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html):

* [[!DNL Luma Loyalty Schema]](#create-luma-loyalty-schema)

* [[!DNL Luma Product catalog Schema]](-catalog)

* [[!DNL Luma Product Inventory Events]](#create-luma-product-inventory-event-schema)

* [[!DNL Luma CRM]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Product Interactions]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Test Profiles]](#create-luma-crm-and-luma-product-interactions-schemas)

>[!TIP]
>
>Vea el videotutorial: [Crear un esquema](/help/set-up-data/create-schema.md) antes de empezar.

### Crear [!DNL Luma Loyalty] [!UICONTROL Esquema] {#create-luma-loyalty-schema}

#### Creación del esquema

Comience creando la [!DNL Luma Loyalty] esquema:

1. Vaya a **[!UICONTROL ADMINISTRACIÓN DE DATOS]** > **[!UICONTROL Esquemas]** en el panel de navegación izquierdo.

1. Select **[!UICONTROL Crear esquema]** en la parte superior derecha.

1. En el menú desplegable, seleccione **[!UICONTROL Perfil individual XDM]**, ya que está modelando atributos de un cliente individual (puntos, estado, etc.).

   ![Crear esquema](assets/loyaltyCreateSchema.png)

#### Agregar grupos de campos existentes

A continuación, se le pedirá que añada grupos de campos al esquema. Debe añadir todos los campos a los esquemas mediante grupos. Se añaden grupos de campos existentes y se debe crear un grupo de campos.

>[!NOTE]
>
>Si la variable [!UICONTROL Grupos de campo] modal no se abre automáticamente en el [!UICONTROL Esquemas] página, seleccione **[!UICONTROL Agregar]** (como se muestra en la siguiente imagen).

![Agregar grupo de campos](assets/add_field_group.png)

1. En el **[!UICONTROL Agregar grupos de campos]** , habilite los siguientes grupos de campos:

   * **[!UICONTROL Detalles demográficos]** para datos básicos del cliente como nombre y fecha de nacimiento.

   * **[!UICONTROL Detalles de contacto personal]** para obtener detalles básicos de contacto como la dirección de correo electrónico y el número de teléfono.

   * **[!UICONTROL Detalles de fidelidad]** para los detalles de lealtad, como puntos, fecha unida o estado. El grupo de campos de lealtad está muy por debajo de la lista, por lo que es más fácil buscarlo.

1. Select **[!UICONTROL Agregar grupo de campos]** para agregar los tres grupos de campos al esquema.

   ![Seleccionar grupos de campos estándar](assets/addstandardFieldGroups.png)

1. Seleccione el nodo superior del esquema.

1. Entrar `Luma Loyalty Schema` como el [!UICONTROL Nombre para mostrar].

#### Cree un [!UICONTROL grupo de campos]

Para ayudar a garantizar la coherencia en los esquemas, Adobe recomienda administrar todos los identificadores del sistema en un solo grupo:

1. En el **[!UICONTROL Composición]** sección bajo [!UICONTROL Grupos de campo], seleccione **[!UICONTROL Agregar]**.

1. Select **[!UICONTROL Crear nuevo grupo de campos]**.

1. Agregar `Luma Identity Profile Field Group` como el **[!UICONTROL Nombre para mostrar]**.

1. Agregar `system identifiers for XDM Individual Profile class` como el **[!UICONTROL Descripción]**.

1. Select **[!UICONTROL Agregar grupos de campos]**.

   ![Crear nuevo grupo de campos](assets/addnewfieldgroup.png)

#### Añadir campos a la nueva [!UICONTROL grupo de campos]

El nuevo grupo de campos vacío se agrega al esquema . Con los botones +, puede añadir campos nuevos a cualquier ubicación de la jerarquía. En este caso, debe añadir campos en el nivel raíz:

1. Select **[!UICONTROL +]** junto al nombre del esquema.

   Este paso agrega un campo debajo de **su id de inquilino** para administrar los conflictos entre los campos personalizados y los campos estándar.

1. En el **[!UICONTROL Propiedades del campo]** barra lateral, añada los detalles del nuevo campo:

   * **Nombre del campo:** `systemIdentifier`

   * **[!UICONTROL Nombre para mostrar]:** `System Identifier`

   * **Tipo:** Objeto

   * **[!UICONTROL Asignar grupo de campos]:** [!DNL Luma identifiers]

1. Select **[!UICONTROL Aplicar]**.

   ![Agregar identificador de sistema](assets/addsysteidentifier.png)

   Agregue dos campos debajo de la variable `systemIdentifier` objeto:

   | [!UICONTROL Fieldname] | [!UICONTROL Nombre para mostrar] | [!UICONTROL Tipo] |
   |-------------|-----------|----------|
   | `loyaltyId` | `Loyalty ID` | [!UICONTROL Cadena] |
   | `crmId` | `CRM Id` | [!UICONTROL Cadena] |

![campos](./assets/add_fields.png)

#### Establecer identidades

Ahora tiene la variable [!UICONTROL namespace] y [!DNL Luma Loyalty schema] configurado. Para poder introducir datos, debe etiquetar los campos de identidad. Cada esquema utilizado con [!UICONTROL Perfil del cliente en tiempo real] es necesario que se especifique una identidad principal y cada registro ingerido debe tener un valor para ese campo.

1. Configure las variables **identidad principal**:

   En el **[!DNL Luma Loyalty Schema]**:

   1. Seleccione el **[!DNL Luma Identity Profile Field Group]**.

   2. Seleccione el campo **[!DNL loyaltyId]**.

   3. En el **[!UICONTROL Propiedades del campo]**, habilite el **[!UICONTROL Identidad]** en la ventana

   4. Active la variable **[!UICONTROL Identidad principal]** en la ventana

   5. Seleccione el `Luma Loyalty Id` espacio de nombres de **[!UICONTROL Espacios de nombres de identidad]** lista desplegable.

   6. Select **[!UICONTROL Aplicar]**.

      ![identidad principal](/help/tutorial-configure-a-training-sandbox/assets/primary_identity.png)

2. Configure un **identidad secundaria**:

   En el **[!DNL Luma Loyalty Schema]**:

   1. Seleccione el **[!DNL Luma Identity Profile Field Group]**..

   2. Seleccione el campo `crmId`.

   3. En el **[!UICONTROL Propiedades del campo]**, habilite el **[!UICONTROL Identidad]** en la ventana

   4. Seleccione el `Luma CRM Id` espacio de nombres de **[!UICONTROL Espacios de nombres de identidad]** lista desplegable.

   5. Select **[!UICONTROL Aplicar]**.

#### Habilitar para perfil y guardar el esquema

1. Seleccione el nodo superior del esquema.

1. En el [!UICONTROL Propiedades del campo] enable **[!UICONTROL Perfil]**.

   El esquema debería tener este aspecto:

   ![esquema de Lealtad de Luma](assets/lumaloyaltyschema.png)

1. Seleccione **[!UICONTROL Guardar]**.

### Crear [!DNL Luma Product catalog Schema] {#create-luma-product-catalog-schema}


1. Vaya a [!UICONTROL ADMINISTRACIÓN DE DATOS] -> **[!UICONTROL Esquemas]** en el panel de navegación izquierdo.

1. Seleccione el **[!UICONTROL Crear esquema]** en la parte superior derecha.

1. En el menú desplegable, seleccione **[!UICONTROL Examinar todos los tipos de esquema]**, que le permite crear una clase.

1. Seleccione **[!UICONTROL Crear nueva clase].

1. Añada el nombre para mostrar: `Luma Product Catalog Class`.

1. Asignar clase.

1. Cree un [!UICONTROL grupo de campos]:

   * Nombre para mostrar: `Luma Product Catalog Field Group`

2. Agregue el siguiente campo al **[!DNL Luma Product Catalog Field Group]**.

   * Nombre del campo: `product`

   * Nombre para mostrar: `Product`

   * Tipo: [!UICONTROL Objeto]

   * Grupo de campos: [!DNL Luma Product Catalog Field Group]

3. Select **[!UICONTROL Aplicar]**.

4. Agregue los campos siguientes al **[!DNL Product]** objeto:

   | [!UICONTROL Fieldname] | [!UICONTROL Nombre para mostrar] | [!UICONTROL Tipo] |
   |-------------|-----------|----------|
   | `sku` | `SKU` | [!UICONTROL Cadena] |
   | `name` | `Name` | [!UICONTROL Cadena] |
   | `category` | `Category` | [!UICONTROL Cadena] |
   | `color` | `Color` | [!UICONTROL Cadena] |
   | `size` | `Size` | [!UICONTROL Cadena] |
   | `price` | `Price` | [!UICONTROL Duplicada] |
   | `description` | `Description` | [!UICONTROL Cadena] |
   | `ImageURL` | `Image URL` | [!UICONTROL Cadena] |
   | `stockQuantity` | `Stock Quantity` | [!UICONTROL Cadena] |

5. Agregue la variable **[!UICONTROL Nombre para mostrar]** `Luma Product Catalog Field Group` a [!UICONTROL grupo de campos].

6. Seleccione **[!UICONTROL Guardar]**.


### Crear [!DNL Luma Product Inventory Event Schema] {#create-luma-product-inventory-event-schema}


1. Vaya a **[!UICONTROL ADMINISTRACIÓN DE DATOS]** -> **[!UICONTROL Esquemas]** en el panel de navegación izquierdo.

1. Seleccione el **[!UICONTROL Crear esquema]** en la parte superior derecha.

1. En el menú desplegable, seleccione **[!UICONTROL Examinar todos los tipos de esquema]**.

1. Select **[!UICONTROL Crear nueva clase]**.

1. Añada el nombre para mostrar: `Luma Business Event`.

1. Seleccionar tipo: *[!UICONTROL Serie temporal]*.

1. Asignar clase.

1. Cree un [!UICONTROL grupo de campos]:

   * Nombre para mostrar: `Product Inventory Event Details`

1. Agregue la variable **[!UICONTROL Nombre para mostrar]** `Luma Product Inventory Event Schema` al esquema.

1. Agregue el siguiente campo al grupo de campos Información del producto de Luma :

   * Nombre del campo: `inventoryEvent`

   * Nombre para mostrar: `Inventory Event`

   * Tipo: [!UICONTROL Objeto]

   * Grupo de campos: [!DNL Product Inventory Event Details]

1. Agregue los campos siguientes al **[!DNL Product Inventory Event Details]** objeto:

   | [!UICONTROL Fieldname] | [!UICONTROL Nombre para mostrar] | [!UICONTROL Tipo] |
   |-------------|-----------|----------|
   | `productId` | `Product ID` | [!UICONTROL Cadena] |
   | `sku` | `SKU` | [!UICONTROL Cadena] |
   | `stockEventType` | `Stock Event Type` | **[!UICONTROL Enum]** con `restock` y `outOfStock` como valores |

   1. para configurar la variable `stockEventType` a Enum, seleccione el tipo: `string`.

   1. Desplácese hacia abajo hasta la parte inferior del **[!UICONTROL Propiedades del campo]**.

   1. Habilitar **[!UICONTROL Enum]**.

   1. Entrar **[!UICONTROL values] ([!UICONTROL label)]**: `restock` (`restock`).

   1. Select **[!UICONTROL Añadir fila]**.

   1. Entrar **[!UICONTROL values] ([!UICONTROL label)]**: `outOfStock` (`out of stock`).

   1. Select **[!UICONTROL Aplicar]**.

      ![enum](assets/enum.png)

1. Establezca `productId` field como **[!UICONTROL identidad principal]** using **[!DNL Luma Product namespace]**.

1. Seleccione el `sku` y defina una relación con `product.sku` en el campo **[!DNL Luma Product catalog Schema]** Esquema:

   1. Desplácese hacia abajo hasta la parte inferior del **[!UICONTROL Propiedades del campo]**.

   1. Habilitar **[!UICONTROL Relación]**.

      1. **[!UICONTROL Esquema de referencia]**: [!DNL Luma Product catalog Schema].

      1. **[!UICONTROL Área de nombres de identidad de referencia]**: [!DNL Luma Product].
   1. Select **[!UICONTROL Aplicar]**.

      El esquema debería tener este aspecto:

      ![Relación de SKU](assets/sku_relationship.png)


1. Habilitar para **Perfil**.

1. Select [!UICONTROL Guardar] para guardar el esquema.

### Cree la variable [!DNL Luma CRM] y [!DNL Luma Product Interactions] esquemas {#create-luma-crm-and-luma-product-interactions-schemas}

Cree la siguiente [!UICONTROL esquemas]:

| [!UICONTROL Nombre para mostrar] | [!DNL Luma CRM] | [!DNL Luma Product Interactions] | [!DNL Luma Test Profiles] |
|  ---| ------- | ---- |----|
| **[!UICONTROL Tipo]** | [!UICONTROL Perfil individual XDM] | [!UICONTROL Evento de experiencia XDM] | [!UICONTROL Perfil individual XDM] |
| **[!UICONTROL Agregar grupo de campos existente]** | Identificadores De Luma<br>Detalles demográficos<br>Detalles de contacto personal | Mapa de identidad<br>Detalles del comercio | Identificadores De Luma<br>Detalles demográficos<br>Detalles de contacto personal<br>Detalles de la prueba de perfil |
| **[!UICONTROL Relación]** |  | *[!DNL productListItems.SKU]*:<br> Esquema de referencia *[!DNL Luma Product catalog Schema]* <br>[!DNL Reference identity namespace] *[!DNL Luma Product]* esquema |
| **[!UICONTROL Identidad principal] [!UICONTROL namespace])** | systemIdentifier.crmId<br>(Id De Luma CRM) |  | personalEmail.address<br>(Email) |
| **[!UICONTROL Identidad secundaria] [!UICONTROL namespace]** | personalEmail.address (correo electrónico)<br>mobilePhone.number (Phone) |  |
| **[!UICONTROL Habilitar para perfil]** | sí | sí | sí |

## Pasos siguientes

Ahora que ha creado la estructura de datos, [creación de conjuntos de datos e ingesta de datos de ejemplo](/help/tutorial-configure-a-training-sandbox/manual-data-ingestion.md).
