---
title: Configuración manual de la estructura de datos
description: Cree las áreas de nombres de identidad necesarias y defina la estructura de datos de ejemplo de Luma.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
hide: true
recommendations: noDisplay, noCatalog
exl-id: de870229-d9a6-4051-9f76-13d402cce3b4
source-git-commit: 4df1bdca81a585f728aa68519aa7ec7cd0c2f014
workflow-type: tm+mt
source-wordcount: '1020'
ht-degree: 11%

---

# Configuración manual de datos

En esta sección, se crean las áreas de nombres de identidad necesarias y se define la variable [!DNL Luma] estructura de datos de ejemplo creando el [[!UICONTROL esquemas]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=es).

>[!TIP]
>Vea el tutorial en vídeo [Asignación de identidades](/help/set-up-data/map-identities.md) antes de empezar.

## Paso 1: Crear áreas de nombres de identidad

En este paso, creará áreas de nombres de identidad para [!DNL Luma] campos de identidad personalizados con nombre `lumaLoyaltyId`, `lumaCrmId`, y `lumaProductSKU`. Las áreas de nombres de identidad desempeñan un papel fundamental en la creación de perfiles de clientes en tiempo real, ya que dos valores coincidentes en la misma área de nombres permiten que dos fuentes de datos formen un gráfico de identidad.

Comience creando un [!UICONTROL namespace] para el [!DNL Luma Loyalty ID] esquema:

1. En la interfaz de usuario de Journey Optimizer, vaya a **[!UICONTROL Cliente]** > **[!UICONTROL Identidades]** en el panel de navegación izquierdo.

1. Seleccionar **[!UICONTROL Crear área de nombres de identidad]**.

1. Proporcione los siguientes detalles:

   | Nombre para mostrar | Símbolo de identidad | Tipo |
   |---|---|---|
   | `Luma Loyalty ID` | `lumaLoyaltyId` | [!UICONTROL ID entre dispositivos] |

1. Seleccione **[!UICONTROL Crear]**.

   ![Crear áreas de nombres](assets/createNamespace.png)

1. Cree dos áreas de nombres más siguiendo los mismos pasos:

   | Nombre para mostrar | Símbolo de identidad | Tipo |
   |---|---|---|
   | `Luma CRM ID` | `lumaCrmId` | [!UICONTROL ID entre dispositivos] |
   | `Luma Product SKU` | `lumaProductSKU` | [!UICONTROL Identificador de no personas] |

## Paso 2: Crear esquemas

En este paso, defina la estructura de los datos de ejemplo creando seis [[!UICONTROL esquemas]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=es):

* [[!DNL Luma Loyalty Schema]](#create-luma-loyalty-schema)

* [[!DNL Luma Product Catalog Schema]](#create-luma-product-catalog-schema)

* [[!DNL Luma Product Inventory Events] Esquema](#create-luma-product-inventory-event-schema)

* [[!DNL Luma CRM Schema]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Web Events Schema]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Offline Purchase Events Schema]](#create-additional-schemas)

* [[!DNL Luma Test Profiles Schema]](#create-additional-schemas)

>[!TIP]
>
>Vea el tutorial de vídeo: [Creación de un esquema](/help/set-up-data/create-schema.md) antes de empezar.

### Crear [!DNL Luma Loyalty Schema] {#create-luma-loyalty-schema}

En esta sección se describe cómo crear el [!DNL Luma Loyalty] esquema y configuración de grupos de campos.

#### Creación del esquema

1. Ir a **[!UICONTROL ADMINISTRACIÓN DE DATOS]** > **[!UICONTROL Esquemas]** en el panel de navegación izquierdo.

1. Seleccionar **[!UICONTROL Crear esquema]** en la parte superior derecha.

1. En el menú desplegable, seleccione **[!UICONTROL Perfil individual de XDM]**.

   Seleccione esta opción porque está modelando atributos de un cliente individual (puntos, estado, etc.).

#### Adición de grupos de campos existentes

A continuación, se le pedirá que añada grupos de campos al esquema mediante grupos. Debe agregar grupos de campos existentes y crear un grupo de campos.

1. En el [!UICONTROL Esquema] , si el modal Grupos de campos no se ha abierto automáticamente, seleccione **[!UICONTROL Añadir]**.

   ![Agregar grupo de campos](assets/add_field_group.png)

1. En el **[!UICONTROL Agregar grupos de campos]** , habilite los siguientes grupos de campos:

   * **[!UICONTROL Datos demográficos]** para datos básicos del cliente, como nombre y fecha de nacimiento.

   * **[!UICONTROL Datos personales de contacto]** para obtener información básica de contacto, como dirección de correo electrónico y número de teléfono.

   * **[!UICONTROL Detalles de fidelización]** para obtener detalles de fidelidad, como puntos, fecha de unión o estado. El grupo de campos de fidelización está muy por debajo de la lista, por lo que es más fácil buscarlo.

1. Seleccionar **[!UICONTROL Agregar grupo de campos]** para agregar los tres grupos de campos al esquema.

   ![Seleccionar grupos de campos estándar](assets/addstandardFieldGroups.png)

1. Seleccione el nodo superior del esquema.

1. Entrar `Luma Loyalty Schema` como el **[!UICONTROL Nombre para mostrar]**.

#### Crear un [!UICONTROL grupo de campos] {#create-field-group}

Para garantizar la coherencia en todos los esquemas, Adobe recomienda administrar todos los identificadores del sistema en un solo grupo:

1. Desde el **[!UICONTROL Composición]** sección debajo de [!UICONTROL Grupos de campos], seleccione **[!UICONTROL Añadir]**.

1. Seleccionar **[!UICONTROL Crear nuevo grupo de campos]**.

1. Añadir `Luma Identity Profile Field Group` como el **[!UICONTROL Nombre para mostrar]**.

1. Añadir `system identifiers for XDM Individual Profile class` como el **[!UICONTROL Descripción]**.

1. Seleccione **[!UICONTROL Agregar grupos de campos]**.

   ![Crear nuevo grupo de campos](assets/addnewfieldgroup.png)

#### Añadir campos al nuevo [!UICONTROL grupo de campos]

El nuevo grupo de campos vacío se agrega al esquema. Con los botones +, puede agregar nuevos campos a cualquier ubicación de la jerarquía. En este caso, debe agregar campos en el nivel raíz:

1. Seleccionar **[!UICONTROL +]** junto al nombre del esquema.

   Este paso agrega un campo debajo de **su id de inquilino** , para administrar los conflictos entre los campos personalizados y los campos estándar.

1. En el **[!UICONTROL Propiedades del campo]** En la barra lateral, añada los detalles del nuevo campo:

   * **Nombre del campo:** `systemIdentifier`

   * **[!UICONTROL Nombre para mostrar]:** `System Identifier`

   * **Tipo:** Objeto

   * **[!UICONTROL Asignar grupo de campos]:** [!DNL Luma identifiers]

1. Seleccione **[!UICONTROL Aplicar]**.

   ![Agregar identificador del sistema](assets/addsysteidentifier.png)

   Agregue dos campos debajo de la variable `systemIdentifier` objeto:

   | [!UICONTROL Fieldname] | [!UICONTROL Nombre para mostrar] | [!UICONTROL Tipo] |
   |-------------|-----------|----------|
   | `loyaltyId` | `Loyalty Id` | [!UICONTROL Cadena] |
   | `crmId` | `CRM Id` | [!UICONTROL Cadena] |

![campos](./assets/add_fields.png)

#### Establecer identidades

Ahora tiene el [!UICONTROL namespace] y el [!DNL Luma Loyalty schema] configurado. Para poder introducir datos, debe etiquetar los campos de identidad. Cada esquema utilizado con [!UICONTROL Perfil del cliente en tiempo real] es necesario para tener una identidad principal especificada y cada registro introducido debe tener un valor para ese campo.

1. Configure las variables **identidad principal**:

   Desde el **[!DNL Luma Loyalty Schema]**:

   1. Seleccione el **[!DNL Luma Identity Profile Field Group]**.

   2. Seleccione el campo **[!DNL loyaltyId]**.

   3. En el **[!UICONTROL Propiedades del campo]**, habilite la opción **[!UICONTROL Identidad]** cuadro.

   4. Habilite la **[!UICONTROL Identidad principal]** cuadro.

   5. Seleccione el `Luma Loyalty Id` área de nombres de **[!UICONTROL Áreas de nombres de identidad]** menú desplegable.

   6. Seleccione **[!UICONTROL Aplicar]**.

      ![identidad principal](/help/tutorial-configure-a-training-sandbox/assets/primary_identity.png)

2. Establezca un **identidad secundaria**:

   Desde el **[!DNL Luma Loyalty Schema]**:

   1. Seleccione el **[!DNL Luma Identity Profile Field Group]**.

   2. Seleccione el campo `crmId`.

   3. En el **[!UICONTROL Propiedades del campo]**, habilite la opción **[!UICONTROL Identidad]** cuadro.

   4. Seleccione el `Luma CRM Id` área de nombres de **[!UICONTROL Áreas de nombres de identidad]** desplegable.

   5. Seleccione **[!UICONTROL Aplicar]**.

#### Habilite para el perfil y guarde el esquema

1. Seleccione el nodo superior del esquema.

1. En el [!UICONTROL Propiedades del campo], habilitar **[!UICONTROL Perfil]**.

   El esquema debe tener un aspecto similar al siguiente:

   ![Esquema de fidelización de Luma](assets/lumaloyaltyschema.png)

1. Seleccione **[!UICONTROL Guardar]**.

### Crear [!DNL Luma Product Catalog Schema] {#create-luma-product-catalog-schema}

1. Ir a **[!UICONTROL ADMINISTRACIÓN DE DATOS]** > **[!UICONTROL Esquemas]** en el panel de navegación izquierdo.

1. Seleccionar **[!UICONTROL Crear esquema]** (parte superior derecha).

1. Para crear una clase, seleccione **[!UICONTROL Examinar todos los tipos de esquemas]** en el menú desplegable.

1. Seleccionar **[!UICONTROL Crear nueva clase]**.

1. Añada el nombre para mostrar: `Luma Product Catalog Class`.

1. Asignar clase.

1. Crear un [!UICONTROL Grupo de campos]:

   * Nombre para mostrar: `Luma Product Catalog Field Group`

1. Añada el siguiente campo a **[!DNL Luma Product Catalog Field Group]**.

   * Nombre del campo: `product`

   * Nombre para mostrar: `Product`

   * Tipo: [!UICONTROL Objeto]

   * Grupo de campos: [!DNL Luma Product Catalog Field Group]

1. Seleccione **[!UICONTROL Aplicar]**.

1. Añada los campos siguientes a **[!DNL Product]** objeto:

   | [!UICONTROL Fieldname] | [!UICONTROL Nombre para mostrar] | [!UICONTROL Tipo] |
   |-------------|-----------|----------|
   | `sku` | `Product SKU` | [!UICONTROL Cadena] |
   | `name` | `Product Name` | [!UICONTROL Cadena] |
   | `category` | `Product Category` | [!UICONTROL Cadena] |
   | `color` | `Product Color` | [!UICONTROL Cadena] |
   | `size` | `Product Size` | [!UICONTROL Cadena] |
   | `price` | `Product Price` | [!UICONTROL Doble] |
   | `description` | `Product Description` | [!UICONTROL Cadena] |
   | `imageURL` | `Product Image URL` | [!UICONTROL Cadena] |
   | `stockQuantity` | `Product Stock Quantity` | [!UICONTROL Cadena] |
   | `url` | `Product URL` | [!UICONTROL Cadena] |

1. Configure las variables **[!DNL SKU]** como identidad principal.
1. Añada el **[!UICONTROL Nombre para mostrar]** `Luma Product Catalog Field Group` a la [!UICONTROL grupo de campos].

1. Seleccione **[!UICONTROL Guardar]**.

### Crear [!DNL Luma Product Inventory Event Schema] {#create-luma-product-inventory-event-schema}

1. Ir a **[!UICONTROL ADMINISTRACIÓN DE DATOS]** > **[!UICONTROL Esquemas]** en el panel de navegación izquierdo.

1. Seleccione el **[!UICONTROL Crear esquema]** botón en la parte superior derecha.

1. En el menú desplegable, seleccione **[!UICONTROL Examinar todos los tipos de esquemas]**.

1. Seleccionar **[!UICONTROL Crear nueva clase]**.

1. Añada el nombre para mostrar: `Luma Business Event Class`.

1. Seleccionar tipo: *[!UICONTROL Serie temporal]*.

1. Asignar clase.

1. Crear un [!UICONTROL grupo de campos]:

   * Nombre para mostrar: `Luma Product Inventory Event Details Field Group`

1. Añada el **[!UICONTROL Nombre para mostrar]** `Luma Product Inventory Event Schema` al esquema.

1. Añada el siguiente campo a **[!DNL Luma Product Inventory Event Details Field Group]**:

   * Nombre del campo: `inventoryEvent`

   * Nombre para mostrar: `Inventory Event`

   * Tipo: [!UICONTROL Objeto]

   * Grupo de campos: `Luma Product Inventory Event Details Field Group`

1. Añada los campos siguientes a `Product Inventory Event Details` objeto:

   | [!UICONTROL Fieldname] | [!UICONTROL Nombre para mostrar] | [!UICONTROL Tipo] |
   |-------------|-----------|----------|
   | `sku` | `SKU` | [!UICONTROL Cadena] |
   | `stockEventType` | `Stock Event Type` | [!UICONTROL Cadena] |

   1. para establecer la variable `stockEventType` para Enumerar, seleccione el tipo: `string`.

   2. Desplácese hacia abajo hasta la parte inferior de **[!UICONTROL Propiedades del campo]**.

   3. Activar **[!UICONTROL Enumeración]**.

   4. Entrar **[!UICONTROL values] ([!UICONTROL label)]**: `restock` (`Restock`).

   5. Seleccionar **[!UICONTROL Añadir fila]**.

   6. Entrar **[!UICONTROL values] ([!UICONTROL label)]**: `outOfStock` (`Out of Stock`).

   7. Seleccione **[!UICONTROL Aplicar]**.

      ![enum](assets/enum.png)

1. Establecer `inventory.Event.sku` campo como **[!UICONTROL identidad principal]** uso del **[!DNL LumaProductSKU namespace]**.

1. Seleccione el `sku` y defina una relación con el `product.sku` en el campo **[!DNL Luma Product catalog Schema]** Esquema:

   1. Desplácese hacia abajo hasta la parte inferior de **[!UICONTROL Propiedades del campo]**.

   2. Activar **[!UICONTROL Relación]**.

      1. **[!UICONTROL Esquema de referencia]**: [!DNL Luma Product Catalog Schema].

      2. **[!UICONTROL Área de nombres de identidad]**: [!DNL LumaProductSKU].
   3. Seleccione **[!UICONTROL Aplicar]**.

      El esquema debe tener un aspecto similar al siguiente:

      ![Relación de SKU](assets/sku_relationship.png)


1. Habilitar para **Perfil**.

1. Seleccionar [!UICONTROL Guardar] para guardar el esquema.

### Creación de esquemas adicionales {#create-additional-schemas}

Cree las siguientes opciones adicionales [!UICONTROL esquemas]:

| [!UICONTROL Nombre para mostrar] | [!DNL Luma CRM Schema] | [!DNL Luma Web Events Schema] | [!DNL Luma Test Profiles schema] | [!DNL Luma Offline Purchase Events Schema] |
|  ---| ------- | ---- |----|----|
| **[!UICONTROL Clase]** | [!UICONTROL Perfil individual de XDM] | [!UICONTROL Evento de experiencia XDM] | [!UICONTROL Perfil individual de XDM] | [IUICONTROL XDM ExperienceEvent] |
| **[!UICONTROL Agregar un grupo de campos existente]** | `Luma Identity Profile Field Group`<br>`Demographic Details`<br>`Personal Contact Details` | `Orchestration eventID`<br>`Consumer Experience Event`<br>`AEP Web SDK ExperienceEvent` | `Luma Identity Profile Field Group`<br>`Demographic Details`<br>`Personal Contact Details`<br>`Profile test details` | `Luma Identity Profile Field Group` <br>`Commerce Details` |
| **[!UICONTROL Relación]** |  | `productListItems.SKU`:<br> Esquema de referencia `Luma Product Catalog Schema` <br>[!DNL Reference identity namespace] `lumaProductSKU` |  | `productListItems.SKU`:<br> Esquema de referencia `Luma Product Catalog Schema` <br>[!DNL Reference identity namespace] `lumaProductSKU` |
| **[!UICONTROL Identidad principal] [!UICONTROL namespace])** | `systemIdentifier.crmId` |  | `systemIdentifier.crmId` | `systemIdentifier.LoyaltyId` |
| **[!UICONTROL Habilitar para el perfil]** | sí | sí | sí | sí |

## Pasos siguientes

Ahora que ha creado la estructura de datos, puede hacer lo siguiente [crear conjuntos de datos e introducir datos de ejemplo](/help/tutorial-configure-a-training-sandbox/manual-data-ingestion.md).
