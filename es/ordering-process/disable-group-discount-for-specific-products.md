---
title: "Desactivar descuento por grupo para productos específicos - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Desactivar descuento por grupo para productos específicos' de MyPresta.eu."
sidebar:
  label: "Desactivar descuento por grupo para productos específicos - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Disable group discount for specific products en MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-group-discount-for-specific-products.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/disable-group-discount-for-specific-products/)
>
> ---


# Desactivar descuento por grupo para productos específicos

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo de configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal y única para el módulo "Desactivar descuento por grupo para productos específicos". Aquí encontrará todos los ajustes para controlar qué productos se excluyen de los descuentos por grupo.

**Ubicación del menú:** Back Office > Módulos > Gestor de módulos > "Desactivar descuento por grupo para productos específicos" > Configurar

#### 2.1.1 Sección "Desactivar descuentos por grupo para productos específicos"

Esta sección contiene los ajustes principales para habilitar o deshabilitar la funcionalidad del módulo y definir qué productos se ven afectados.

- **Ajuste: Interruptor Habilitado / Deshabilitado**

  - **Qué hace este ajuste:** Este es el interruptor maestro del módulo. Determina si la lógica del módulo para deshabilitar los descuentos por grupo está activa o inactiva.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está Habilitado:* El módulo verificará activamente si un producto o su categoría está listado en sus reglas de exclusión. Si es así, cualquier descuento por grupo será ignorado para ese producto.
    - *Cuando está Deshabilitado:* El módulo no interferirá con los cálculos de descuento por grupo predeterminados de PrestaShop. Todos los productos estarán sujetos a descuentos por grupo si corresponde.
  - **Valor recomendado:** "Habilitado" si tiene la intención de usar la funcionalidad del módulo.
  - **Escenario / ejemplo de comerciante:** Si está configurando el módulo por primera vez o realizando mantenimiento, lo habilitaría. Si desea que todos los descuentos por grupo se apliquen temporalmente sin desinstalar el módulo, lo deshabilitaría.
- **Ajuste: Categorías (Cuadro de selección)**

  - **Qué hace este ajuste:** Esto le permite seleccionar categorías de productos enteras cuyos productos deben ser excluidos de los descuentos por grupo. Cualquier producto que pertenezca a una categoría seleccionada no recibirá descuentos por grupo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se seleccionan categorías:* Todos los productos dentro de las categorías elegidas (y sus subcategorías, dependiendo de la estructura de categorías de PrestaShop y cómo se asignan los productos) tendrán los descuentos por grupo deshabilitados.
    - *Cuando no se seleccionan categorías:* Los productos no se excluyen en función de su categoría.
  - **Valor recomendado:** Seleccione las categorías que contienen productos que desea excluir de los descuentos por grupo.
  - **Escenario / ejemplo de comerciante:** Usted vende productos electrónicos. Su categoría "Novedades" a menudo contiene artículos de alta demanda. Quiere asegurarse de que incluso sus clientes mayoristas paguen el precio completo por estos nuevos productos durante el primer mes. Seleccionaría la categoría "Novedades" aquí.
- **Ajuste: Productos específicos (Entrada de búsqueda y selección)**

  - **Qué hace este ajuste:** Esto le permite buscar y seleccionar productos individuales que deben ser excluidos de los descuentos por grupo. Esto proporciona un control más granular que las categorías.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se seleccionan productos específicos:* Solo los productos explícitamente elegidos tendrán los descuentos por grupo deshabilitados, independientemente de su categoría.
    - *Cuando no se seleccionan productos específicos:* Los productos no se excluyen en función de la selección individual.
  - **Valor recomendado:** Seleccione productos específicos que desea excluir de los descuentos por grupo.
  - **Escenario / ejemplo de comerciante:** Tiene una impresión de arte de edición limitada (ID de producto 123) y una oferta de paquete especial (ID de producto 456) que nunca desea descontar para ningún grupo de clientes. Buscaría y agregaría "Impresión de arte (Edición limitada)" y "Oferta de paquete especial" a esta lista.

#### 2.1.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Habilitado / Deshabilitado | Habilitado | Interruptor maestro para activar/desactivar la funcionalidad del módulo. |
| Configuración del módulo | Categorías | Seleccionar categorías relevantes | Excluir todos los productos dentro de las categorías seleccionadas de los descuentos por grupo. |
| Configuración del módulo | Productos específicos | Seleccionar productos relevantes | Excluir productos seleccionados individualmente de los descuentos por grupo. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: He configurado el módulo, pero los descuentos por grupo todavía se aplican a mis productos excluidos. ¿Qué está mal?**
R:

- **¿Está habilitado el módulo?** Verifique dos veces el interruptor "Habilitado / Deshabilitado" en la página de configuración del módulo. Debe estar configurado en "Habilitado".
- **¿Guardó sus cambios?** Siempre haga clic en el botón "Guardar" después de realizar cualquier cambio en la configuración.
- **Borre la caché de PrestaShop:** A veces, la caché de PrestaShop puede evitar que los cambios aparezcan inmediatamente. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).
- **Verifique la asignación de producto/categoría:** Asegúrese de que el producto esté correctamente asignado a la categoría que ha excluido, o que haya seleccionado el producto exacto que desea excluir.
- **Verifique otros módulos:** Otro módulo de precios o descuentos podría estar en conflicto. Intente deshabilitar temporalmente otros módulos relacionados con descuentos para ver si el problema se resuelve.

**P2: ¿Este módulo afectará mis reglas de precio de catálogo regulares o precios específicos?**
R: No, este módulo se dirige específicamente a los *descuentos por grupo*. No interfiere con las reglas de precio del catálogo, los precios específicos que establece para productos individuales o las reglas del carrito (vales). Solo evita el descuento porcentual adicional aplicado en función del grupo de un cliente.

**P3: ¿Cómo maneja este módulo los productos en múltiples categorías?**
R: Si un producto está en varias categorías, y *cualquiera* de esas categorías se selecciona para exclusión en el módulo, el producto se excluirá de los descuentos por grupo. El módulo verifica si el producto *pertenece* a una categoría excluida.

**P4: Estoy usando un tema personalizado. ¿Funcionará este módulo correctamente?**
R: Sí, este módulo funciona a nivel de cálculo de precios central y no introduce ningún elemento nuevo en el front-office ni un estilo complejo que normalmente entraría en conflicto con los temas. Debería ser totalmente compatible con cualquier tema de PrestaShop.

**P5: ¿Puedo excluir productos para *algunos* grupos pero no para otros?**
R: No, este módulo deshabilita los descuentos por grupo para los productos/categorías seleccionados *para todos los grupos de clientes*. Si un producto está en la lista de exclusión, ningún grupo de clientes recibirá un descuento en él. La funcionalidad principal de PrestaShop le permite establecer descuentos por grupo por grupo, pero este módulo actúa como una anulación para productos específicos, haciéndolos exentos de *cualquier* descuento por grupo.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters que buscan comprender, depurar o extender el módulo "Desactivar descuento por grupo para productos específicos".

### 4.1 Descripción general de la arquitectura

El módulo funciona principalmente anulando una clase central de PrestaShop (`Product.php`) para modificar la lógica de cálculo de precios. Se engancha al método `Product::getPriceStatic()`, que es central para cómo PrestaShop determina el precio final de un producto. Cuando se llama a este método, el módulo verifica si el producto actual o sus categorías asociadas están configuradas para su exclusión de los descuentos por grupo. Si lo están, se asegura de que el componente de descuento por grupo del cálculo del precio se omita.

El módulo utiliza la clase `Module` estándar de PrestaShop para su interfaz de configuración y se basa en entradas de la tabla `Configuration` para almacenar sus ajustes. También incluye una herramienta de búsqueda simple para la selección de productos en el back office.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce ningún controlador personalizado de front-office o back-office. Su lógica se implementa principalmente a través de una anulación de clase y el método `getContent()` del archivo principal del módulo para la configuración.

### 4.3 Clases y modelos principales (`classes/`)

- **`exgdisc/override/classes/Product.php`**
  - **Responsabilidad:** Este es el archivo más crítico del módulo. Anula la clase `Product` central para modificar el método `getPriceStatic()`.
  - **Nombre de la clase:** `Product` (anula la clase `Product` original)
  - **Clase padre:** `ProductCore`
  - **Lógica clave:**
    - El método `getPriceStatic()` anulado primero llama al `getPriceStatic()` del padre para obtener el precio base.
    - Luego recupera la configuración del módulo (`exgdisc_categories`, `exgdisc_products`) de `Configuration::get()`.
    - Verifica si el ID del producto actual (`$id_product`) está en la lista `exgdisc_products`.
    - También verifica si alguna de las categorías asociadas con `$id_product` está en la lista `exgdisc_categories`.
    - Si alguna de las condiciones es verdadera, significa que el producto debe ser excluido de los descuentos por grupo. El método luego recalcula el precio, ignorando efectivamente el componente de descuento por grupo que normalmente aplicaría el método `getPriceStatic()` del padre.
    - El método `Product::getPriceStatic()` original tiene un parámetro `$use_group_reduction`. La anulación asegura que incluso si esto es `true`, la reducción de grupo no se aplica si el producto es excluido por el módulo.

### 4.4 Activos de JavaScript (`views/js/`)

- **`exgdisc/lib/searchTool/views/js/autocomplete.js`**
  - **Alcance:** Back-office (utilizado en la página de configuración del módulo).
  - **Propósito:** Proporciona la funcionalidad de autocompletado para seleccionar productos específicos en el formulario de configuración del módulo.
  - **Lógica clave:**
    - Inicializa un campo de entrada de autocompletado (probablemente apuntando a un elemento con un ID específico, por ejemplo, `#product_autocomplete_input`).
    - Envía solicitudes AJAX a un controlador de administración de PrestaShop (por ejemplo, `AdminProducts` o un controlador de búsqueda personalizado) para obtener sugerencias de productos basadas en la entrada del usuario.
    - Maneja la selección de productos, agregándolos a un campo de entrada oculto o a una lista visual en la página de configuración.
    - Gestiona la eliminación de productos seleccionados de la lista.

### 4.5 Hojas de estilo CSS (`views/css/`)

- **`exgdisc/lib/searchTool/views/css/autocomplete.css`**
  - **Alcance:** Back-office (estiliza la herramienta de búsqueda de autocompletado).
  - **Propósito:** Proporciona estilo para la entrada de búsqueda de productos y la lista de productos seleccionados en la página de configuración del módulo.
  - **Selectores clave:** Probablemente incluye estilos para el menú desplegable de autocompletado, las etiquetas/insignias de elementos seleccionados y posiblemente el propio campo de entrada de búsqueda. Los desarrolladores pueden anular estas clases en sus temas de administración personalizados si es necesario.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **`exgdisc/lib/searchTool/views/scripts.tpl`**

  - **Alcance:** Back-office (incluido en la página de configuración del módulo).
  - **Propósito:** Renderiza la estructura HTML para la entrada de búsqueda de productos y el área donde se muestran los productos seleccionados. También es probable que incluya las llamadas JavaScript necesarias para inicializar el script `autocomplete.js`.
  - **Elementos clave:** Campo de entrada para buscar productos, un contenedor para mostrar productos seleccionados (por ejemplo, como etiquetas o elementos de lista) y campos de entrada ocultos para almacenar los ID de los productos seleccionados.
- **`exgdisc/views/script.tpl`**

  - **Alcance:** Back-office (incluido en la página de configuración del módulo).
  - **Propósito:** Esta plantilla probablemente se usa para generar JavaScript o CSS adicional que es específico del formulario de configuración del módulo principal, potencialmente relacionado con la validación del formulario o elementos dinámicos de la interfaz de usuario. Dado el hook `ActionAdminControllerSetMedia`, podría usarse para registrar activos.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - El módulo no crea ninguna tabla de base de datos personalizada.
  - Todos los ajustes de configuración se almacenan en la tabla `ps_configuration`:
    - `exgdisc_categories`: Almacena una cadena serializada o una lista de ID de categorías separadas por comas para excluir.
    - `exgdisc_products`: Almacena una cadena serializada o una lista de ID de productos separadas por comas para excluir.
    - `mypresta_updates`, `update_`, `updatev_`: Relacionado con el mecanismo de actualización de MyPresta.eu.
    - `exgdisc_groups`: (No se usa explícitamente en la información proporcionada, pero podría ser una configuración heredada o futura para exclusiones específicas de grupo).
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Se ejecuta cuando se carga un controlador de administración y se están configurando sus medios (JS/CSS). | Utilizado por el módulo para cargar su JavaScript (`autocomplete.js`) y CSS (`autocomplete.css`) del back-office para la página de configuración, asegurando que la herramienta de búsqueda de productos funcione. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Desactivar descuento por grupo para productos específicos", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a garantizar que el módulo funcione de manera óptima con su tienda PrestaShop.
