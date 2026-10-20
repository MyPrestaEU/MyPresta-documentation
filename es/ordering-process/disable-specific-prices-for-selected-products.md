---
title: "Desactivar precios específicos para productos seleccionados - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Desactivar precios específicos para productos seleccionados' de MyPresta.eu."
sidebar:
  label: "Desactivar precios específicos para productos seleccionados - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Disable specific prices for selected products en MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-specific-prices-for-selected-products.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/disable-specific-prices-for-selected-products/)
>
> ---


# Desactivar precios específicos para productos seleccionados

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, haz clic en "Configurar" junto al nombre del módulo para acceder a sus ajustes. Esta es la pantalla de configuración principal y única para este módulo.

#### **Ajustes Generales**

- **Desactivar precios específicos para productos seleccionados**
  - **Qué hace este ajuste:** Este es el interruptor maestro para habilitar o deshabilitar la funcionalidad principal del módulo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está Habilitado (SÍ):* El módulo evitará activamente que se apliquen precios específicos a los productos y categorías que selecciones a continuación.
    - *Cuando está Deshabilitado (NO):* El módulo estará inactivo. Todos los precios específicos y las reglas de precio de catálogo se aplicarán a todos los productos como de costumbre, independientemente de tus selecciones en los campos "Categorías" o "Productos específicos".
  - **Valor recomendado:** **SÍ** si tienes la intención de usar la funcionalidad del módulo para excluir productos de los descuentos. **NO** si deseas deshabilitarlo temporalmente sin perder tus configuraciones guardadas.
  - **Escenario / ejemplo de comerciante:** Acabas de lanzar una nueva línea de productos premium y quieres asegurarte de que nunca se descuenten. Habilitas este ajuste y luego añades esos productos a la lista de exclusión.

#### **Criterios de Exclusión**

- **Categorías**

  - **Qué hace este ajuste:** Este campo te permite seleccionar categorías de productos enteras cuyos productos deben ser excluidos de los precios específicos.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se seleccionan categorías:* Todos los productos que pertenecen a las categorías seleccionadas (incluidas las subcategorías, dependiendo de la estructura de categorías de PrestaShop y cómo se aplican los precios específicos) tendrán los precios específicos deshabilitados.
    - *Cuando no se seleccionan categorías:* Solo los productos explícitamente listados en el campo "Productos específicos" se verán afectados.
  - **Valor recomendado:** Selecciona categorías que contengan productos que quieras proteger consistentemente de los descuentos, como "Novedades", "Artículos de Lujo" o "Liquidación (si solo quieres aplicar descuentos manuales)".
  - **Escenario / ejemplo de comerciante:** Tienes una categoría "Marcas Premium". Al seleccionarla aquí, todos los productos dentro de esa categoría se excluirán automáticamente de los cálculos de precios específicos, ahorrándote tener que listar cada producto individualmente.
- **Productos específicos**

  - **Qué hace este ajuste:** Este campo te permite buscar y seleccionar productos individuales que deben ser excluidos de los precios específicos. Utiliza una herramienta de búsqueda con autocompletado para ayudarte a encontrar productos rápidamente.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se seleccionan productos:* Los productos individuales elegidos tendrán los precios específicos deshabilitados, independientemente de su categoría.
    - *Cuando no se seleccionan productos:* Solo los productos dentro de las "Categorías" seleccionadas se verán afectados.
  - **Valor recomendado:** Utiliza esto para artículos individuales que no encajan en una exclusión de categoría más amplia, o para best-sellers específicos que quieres mantener a precio completo.
  - **Escenario / ejemplo de comerciante:** Tienes algunos gadgets de alta demanda que siempre se venden bien a precio completo. Buscas "iPhone 15" y "Samsung Galaxy S24" y los añades a esta lista para asegurarte de que nunca se descuenten por precios específicos.

#### **Guardar Tus Cambios**

Después de realizar cualquier cambio en la configuración, recuerda hacer clic en el botón **"Guardar"** en la parte inferior de la página de configuración para aplicarlos.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de Configuración del Módulo | Desactivar precios específicos para productos seleccionados | SÍ | Interruptor maestro para habilitar/deshabilitar la funcionalidad del módulo. SÍ significa que las exclusiones están activas. |
| Página de Configuración del Módulo | Categorías | Ninguna seleccionada | Selecciona las categorías cuyos productos serán excluidos de los precios específicos. |
| Página de Configuración del Módulo | Productos específicos | Ninguno seleccionado | Busca y selecciona productos individuales para ser excluidos de los precios específicos. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: He configurado el módulo, pero los precios específicos siguen aplicándose a mis productos excluidos. ¿Qué está mal?**
R1:

-   **Verificar el Estado del Módulo:** Primero, asegúrate de que el ajuste "Desactivar precios específicos para productos seleccionados" en la página de configuración del módulo esté establecido en **SÍ (Habilitado)**.
-   **Verificar Exclusiones:** Vuelve a comprobar que los productos o categorías específicos que deseas excluir estén correctamente seleccionados en la configuración del módulo. Utiliza la función de búsqueda con cuidado para los productos.
-   **Borrar Caché:** PrestaShop a menudo almacena en caché la información de precios. Ve a **Parámetros Avanzados > Rendimiento** y haz clic en "Borrar caché" en la parte superior derecha. Además, borra la caché de tu navegador.
-   **Prioridad de Precios Específicos:** Asegúrate de que la regla de precio específico que estás probando no esté de alguna manera anulando el módulo. Este módulo funciona anulando el cálculo de precios específicos del núcleo de PrestaShop. Si tienes otros módulos que también modifican los precios, podría haber un conflicto. Intenta deshabilitar temporalmente otros módulos relacionados con los precios para diagnosticar el problema.

**P2: ¿Este módulo afectará mis Reglas de Carrito (vales)?**
R2: Sí, indirectamente. Este módulo evita que se apliquen precios específicos a los productos seleccionados. Si una Regla de Carrito (vale) ofrece un descuento que *depende* o interactúa con el mecanismo de precios específicos de PrestaShop (por ejemplo, un descuento porcentual que se calcula en función del precio actual del producto *después* de los precios específicos), entonces los productos excluidos no recibirán esa reducción de precio específica antes de que se aplique el vale. El vale se aplicará entonces al precio base del producto (o a su precio después de otros descuentos no específicos).

**P3: ¿Este módulo funciona con configuraciones de múltiples tiendas?**
R3: La configuración del módulo suele ser global o está vinculada al contexto en el que te encuentras al configurarlo. Si tienes una configuración de múltiples tiendas, prueba a fondo para asegurarte de que las exclusiones se apliquen como se espera en todas las tiendas relevantes. El mecanismo `override` de PrestaShop generalmente se aplica globalmente, pero las reglas de precios específicos en sí mismas pueden ser específicas de la tienda.

**P4: He añadido un nuevo producto a una categoría excluida, pero sigue recibiendo precios específicos. ¿Por qué?**
R4:

-   **Caché:** Siempre borra la caché de PrestaShop (**Parámetros Avanzados > Rendimiento**) después de realizar cambios en categorías o productos, especialmente si estás añadiendo nuevos artículos o moviéndolos entre categorías.
-   **Estructura de Categorías:** Asegúrate de que la regla de precio específico no se esté aplicando de una manera que omita la exclusión de la categoría (por ejemplo, una regla para "todos los productos" que no respeta la jerarquía de categorías). El módulo debería interceptar el cálculo del precio específico de todos modos, pero la caché suele ser la culpable.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo "Desactivar precios específicos para productos seleccionados" aprovecha el sistema de sobrescritura (override) de PrestaShop para modificar la lógica central de precios. Específicamente, sobrescribe las clases `Product` y `SpecificPrice` para inyectar su lógica de exclusión directamente en el proceso de cálculo de precios. Esto asegura que cuando PrestaShop intenta determinar el precio de un producto, el módulo primero verifica si el producto o su categoría está en la lista de exclusión, y si es así, evita que se apliquen precios específicos. El módulo utiliza una estructura de módulo estándar de PrestaShop, con un archivo de módulo principal, sobrescrituras y `views` para activos y plantillas.

### 4.2 Controladores (`controllers/`)

Este módulo no contiene ningún controlador de Front-Office o Back-Office Admin personalizado. Su configuración se maneja directamente dentro del método `getContent()` del archivo principal del módulo, y su funcionalidad principal se implementa a través de sobrescrituras de clases.

### 4.3 Clases y Modelos Principales (`classes/`)

-   **`exsp/override/classes/index.php`**:

    -   **Nombre de la Clase y Clase Padre**: Este es un archivo `index.php` vacío estándar, típicamente colocado en directorios para evitar la lista de directorios. No tiene impacto funcional en la lógica del módulo.
-   **`exsp/override/classes/Product.php`**:

    -   **Nombre de la Clase y Clase Padre**: `Product` (sobrescribe la clase `Product` del núcleo de PrestaShop).
    -   **Responsabilidad**: Esta sobrescritura es el mecanismo principal para interceptar los cálculos de precios de productos. Modifica el método `getPrice()` (o métodos relacionados) para verificar si el producto actual (o su categoría) está configurado para exclusión. Si lo está, el componente de precio específico del cálculo se omite, asegurando que se devuelva el precio base del producto sin ninguna reducción de precio específico. Esto es crucial para evitar que se apliquen precios específicos a nivel de producto.
    -   **Métodos Públicos Clave**: El método `getPrice()` sobrescrito (o métodos de cálculo de precios similares dentro de la clase `Product`) contendrá la lógica para verificar los valores de configuración `exsp_categories` y `exsp_products`.
-   **`exsp/override/classes/SpecificPrice.php`**:

    -   **Nombre de la Clase y Clase Padre**: `SpecificPrice` (sobrescribe la clase `SpecificPrice` del núcleo de PrestaShop).
    -   **Responsabilidad**: Esta sobrescritura impacta directamente en cómo se obtienen y aplican los precios específicos. Modifica métodos como `getSpecificPrice()` o `getSpecificPrices()` para filtrar o ignorar las reglas de precios específicos para los productos que están en la lista de exclusión. Esto actúa como una capa secundaria de defensa, asegurando que incluso si existe una regla de precio específico, no se considerará para los productos excluidos.
    -   **Métodos Públicos Clave**: Los métodos sobrescritos relacionados con la obtención o aplicación de precios específicos incorporarán verificaciones contra las listas de exclusión del módulo.

### 4.4 Activos JavaScript (`views/js/`)

-   **`exsp/lib/searchTool/views/js/autocomplete.js`**:

    -   **Alcance**: Back-office (página de configuración del módulo).
    -   **Descripción**: Este script proporciona la funcionalidad de autocompletado para el campo de entrada "Productos específicos" en la página de configuración del módulo. Probablemente utiliza AJAX para consultar la base de datos de productos de PrestaShop a medida que el usuario escribe, sugiriendo nombres de productos coincidentes. Maneja la visualización de sugerencias y la selección de productos para añadir a la lista de exclusión.
    -   **Detectores de Eventos**: Eventos `keyup` en la entrada de búsqueda de productos, eventos `click` en las sugerencias de autocompletado.
    -   **Manipulación del DOM**: Crea y actualiza dinámicamente la lista de sugerencias, añade los productos seleccionados a una entrada oculta o área de visualización.
-   **`exsp/views/js/exsp.js`**:

    -   **Alcance**: Back-office (página de configuración del módulo).
    -   **Descripción**: Este es el archivo JavaScript principal para la interfaz de configuración del módulo. Maneja la inicialización de la herramienta de búsqueda de autocompletado, gestiona la visualización y eliminación de productos/categorías seleccionados, y potencialmente realiza otras interacciones de UI específicas de la configuración del módulo.
    -   **Detectores de Eventos**: Eventos `click` para eliminar productos/categorías seleccionados, potencialmente eventos `change` para el interruptor principal de habilitar/deshabilitar.
    -   **Manipulación del DOM**: Gestiona la representación visual de las categorías y productos seleccionados, actualiza los campos de entrada ocultos que almacenan los valores de configuración.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   **`exsp/lib/searchTool/views/css/autocomplete.css`**:
    -   **Alcance**: Back-office (página de configuración del módulo).
    -   **Descripción**: Esta hoja de estilo proporciona el estilo visual para la entrada de búsqueda de autocompletado y su lista de sugerencias. Define la apariencia del cuadro de búsqueda, las sugerencias desplegables y, potencialmente, los estados `hover`/`active` para una mejor experiencia de usuario.
    -   **Componentes principales de la UI**: `.autocomplete-container`, `.autocomplete-suggestions`, `.autocomplete-suggestion`.
    -   **Selectores de clases CSS clave**: `.exsp-product-search-input`, `.exsp-selected-item`, `.exsp-remove-item`.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **`exsp/lib/searchTool/views/scripts.tpl`**:

    -   **Alcance**: Back-office (página de configuración del módulo).
    -   **Descripción**: Esta plantilla probablemente incluye los archivos JavaScript y CSS necesarios para la herramienta de búsqueda de autocompletado, o podría contener JavaScript en línea para inicializar el widget de autocompletado con parámetros específicos (por ejemplo, URL AJAX para la búsqueda de productos).
    -   **Renderizado en**: Hook `ActionAdminControllerSetMedia` o directamente dentro de `getContent()`.
-   **`exsp/views/script.tpl`**:

    -   **Alcance**: Back-office (página de configuración del módulo).
    -   **Descripción**: Esta plantilla es responsable de renderizar el formulario de configuración principal del módulo. Incluye la estructura HTML para el interruptor de habilitar/deshabilitar, el campo de selección de categoría y la entrada de búsqueda de productos con su visualización asociada para los productos seleccionados. También es probable que incluya los scripts `exsp.js` y `autocomplete.js`.
    -   **Renderizado en**: Método `getContent()` de `exsp.php`.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:

    -   Este módulo no crea ninguna tabla SQL personalizada.
    -   Almacena sus ajustes de configuración (estado habilitado, categorías excluidas, productos excluidos) en la tabla `ps_configuration` de PrestaShop.
        -   `exsp_categories`: Almacena un array serializado o una lista de IDs de categoría separados por comas para ser excluidos.
        -   `exsp_products`: Almacena un array serializado o una lista de IDs de producto separados por comas para ser excluidos.
        -   `exsp_enabled`: Almacena el estado habilitado/deshabilitado del módulo (por ejemplo, `1` para habilitado, `0` para deshabilitado).
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Se ejecuta cuando se carga un controlador de administración, antes de que se renderice su contenido. | Se utiliza para registrar e incluir los activos JavaScript y CSS del módulo (por ejemplo, para la herramienta de búsqueda de autocompletado) en la página de configuración del módulo. |
| (Hooks Implícitos a través de Sobrescrituras) | Durante el cálculo del precio del producto (`Product::getPrice()`) y la obtención de precios específicos (`SpecificPrice::getSpecificPrices()`). | La funcionalidad principal del módulo se implementa sobrescribiendo las clases `Product` y `SpecificPrice` de PrestaShop. Esto significa que la lógica del módulo se ejecuta cada vez que se llaman estos métodos principales, "enganchándose" efectivamente al proceso de cálculo de precios sin registrar explícitamente un hook `display` o `action`. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Desactivar precios específicos para productos seleccionados", consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema técnico o pregunta que puedas tener sobre la funcionalidad del módulo.
"""
