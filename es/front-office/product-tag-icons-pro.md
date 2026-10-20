---
title: "Product Tag Icons Pro - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Product Tag Icons Pro para PrestaShop de MyPresta.eu."
sidebar:
  label: "Product Tag Icons Pro - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Product Tag Icons Pro en MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-tag-icons-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/product-tag-icons-pro/)
>
> ---


# Product Tag Icons Pro

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias y están presentes en la mayoría de los entornos de alojamiento modernos. No se necesita una configuración especial del servidor.

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

El módulo "Product Tag Icons Pro" proporciona un conjunto completo de opciones de configuración distribuidas en varias pantallas dedicadas en el back office de su PrestaShop.

### 2.1 Página de configuración del módulo (Back Office > Módulos > Gestor de módulos > Configurar Product Tag Icons Pro)

Esta es la pantalla de configuración principal para los ajustes generales del módulo.

-   **Qué hace este ajuste:** Controla el comportamiento general y las opciones de visualización predeterminadas para los iconos de sus productos.
-   **Efecto de cambiar este ajuste:** Estos ajustes impactan cómo se muestran los iconos en toda su tienda, o cómo el módulo interactúa con otras partes de PrestaShop.
-   **Valor recomendado:** Varía según el diseño de su tienda y la funcionalidad deseada.

**Tabla de referencia rápida de configuración (Configuración principal del módulo)**

| Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- |
| **Habilitar Módulo** | SÍ | **Propósito:** Activa o desactiva la funcionalidad del módulo.   **Impacto:** Si está deshabilitado, no aparecerán iconos en su front office y las características del módulo estarán inactivas. Manténgalo habilitado para usar el módulo. |
| **Tamaño del Icono (px)** | 32 | **Propósito:** Establece el tamaño predeterminado (ancho y alto) para todos los iconos mostrados en el front office.   **Impacto:** Todos los iconos se renderizarán con este tamaño de píxel especificado. Elija un tamaño que se ajuste bien a las imágenes de sus productos y al diseño general sin ser demasiado pequeño para ver o demasiado grande para ser intrusivo. |
| **Posición del Icono (Hook)** | `displayProductAdditionalInfo` (o hook similar de página de producto) | **Propósito:** Determina dónde se mostrarán los iconos en la página del producto por defecto. Puede elegir de una lista de hooks de PrestaShop disponibles.   **Impacto:** Los iconos aparecerán en la sección seleccionada de la página del producto. Experimente con diferentes hooks para encontrar la mejor ubicación visual para su tema. Las opciones comunes incluyen `displayProductAdditionalInfo`, `displayProductPriceBlock` o `displayAfterProductThumbs`. |
| **Mostrar Iconos en la Lista de Productos** | SÍ | **Propósito:** Controla si los iconos son visibles en las páginas de listado de productos (categorías, resultados de búsqueda, productos destacados de la página de inicio).   **Impacto:** Si está habilitado, los iconos asignados a los productos aparecerán en sus respectivas tarjetas/miniaturas de productos en las listas. Si está deshabilitado, los iconos solo se mostrarán en las páginas de productos individuales. Se recomienda habilitarlo para un impacto máximo. |
| **Tipo de Tooltip** | Light | **Propósito:** Selecciona el tema visual para el tooltip que aparece cuando un cliente pasa el ratón sobre un icono. Las opciones suelen incluir Light, Noir, Punk, Shadow.   **Impacto:** Cambia la apariencia del cuadro del tooltip (fondo, color de texto, borde) que muestra la descripción del icono. Elija uno que coincida con la estética de su tienda. |
| **Posición del Tooltip** | Top | **Propósito:** Determina dónde aparece el tooltip en relación con el icono cuando se pasa el ratón por encima (por ejemplo, Top, Bottom, Left, Right).   **Impacto:** Afecta la experiencia del usuario al interactuar con los iconos. Elija una posición que no oculte otra información importante en la página. |
| **Habilitar Animaciones de Tooltip** | SÍ | **Propósito:** Añade animaciones sutiles (desvanecimiento, deslizamiento) cuando los tooltips aparecen y desaparecen.   **Impacto:** Hace que la interacción del tooltip se sienta más moderna y atractiva. Si prefiere una apariencia estática e instantánea, desactive esta opción. |
| **CSS Personalizado** | (Vacío) | **Propósito:** Le permite añadir reglas CSS personalizadas para estilizar aún más sus iconos o tooltips sin modificar los archivos del módulo.   **Impacto:** Cualquier regla CSS introducida aquí se aplicará a los elementos del módulo, anulando los estilos predeterminados. Utilícelo para ajustar colores, márgenes o comportamientos específicos de los iconos. |

### 2.2 Pantalla de administración dedicada: Gestionar todos los iconos (Back Office > Product Tag Icons Pro > Gestionar todos los iconos)

Esta pantalla le permite crear, editar y eliminar las definiciones de iconos reales que luego asociará con sus productos.

-   **Nombre de la pantalla y ubicación del menú:** Lo encontrará en **Product Tag Icons Pro > Gestionar todos los iconos** en el menú de su back office de PrestaShop.
-   **Acciones y configuraciones disponibles:**
    -   **Añadir nuevo icono:** Haga clic en el botón "Añadir nuevo icono" para crear un nuevo icono.
        -   **Nombre del icono:** Un nombre descriptivo para su icono (por ejemplo, "Envío gratuito", "Nueva llegada"). Esto es para su referencia interna.
        -   **Imagen del icono:** Suba el archivo de imagen para su icono. Debe ser una imagen pequeña y clara (por ejemplo, PNG, JPG, SVG).
        -   **Descripción del icono:** Un texto corto que aparecerá como un tooltip cuando los clientes pasen el ratón sobre el icono en el front office. Explique lo que significa el icono.
        -   **Activo:** Alternar si este icono está actualmente disponible para su uso y visualización.
        -   **Campos específicos del idioma:** Si su tienda es multilingüe, puede proporcionar diferentes nombres y descripciones para cada idioma.
    -   **Editar icono:** Haga clic en el botón "Editar" junto a un icono existente en la lista para modificar sus detalles.
    -   **Eliminar icono:** Haga clic en el botón "Eliminar" para eliminar un icono. Tenga cuidado, ya que esto también eliminará sus asociaciones con cualquier producto.
    -   **Vista de cuadrícula / gestión:** Una tabla que lista todos sus iconos creados, mostrando su nombre, imagen, descripción y estado activo. Puede ordenar y filtrar esta lista.
-   **Efecto de los cambios:**
    -   **Añadir un icono:** Hace que un nuevo icono esté disponible para su asociación con productos.
    -   **Editar un icono:** Actualiza la imagen, el nombre o la descripción para todas las instancias de ese icono en su tienda.
    -   **Eliminar un icono:** Elimina el icono por completo y ya no aparecerá en ningún producto al que se le haya asignado previamente.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Planifique sus iconos: Decida las características clave o promociones que desea destacar.
    2.  Cree imágenes de iconos pequeñas y de alta calidad (por ejemplo, 32x32px o 64x64px) que coincidan con su marca.
    3.  Vaya a "Gestionar todos los iconos" y añada cada icono, proporcionando un nombre claro y una descripción de tooltip útil.
    4.  Asegúrese de que todos los iconos estén "Activos" si tiene intención de utilizarlos.

### 2.3 Pantalla de administración dedicada: Gestionar asociaciones de iconos (Back Office > Product Tag Icons Pro > Gestionar asociaciones de iconos)

Esta pantalla es donde vincula sus iconos creados a productos específicos de su catálogo.

-   **Nombre de la pantalla y ubicación del menú:** Lo encontrará en **Product Tag Icons Pro > Gestionar asociaciones de iconos** en el menú de su back office de PrestaShop.
-   **Acciones y configuraciones disponibles:**
    -   **Búsqueda de productos:** Utilice la barra de búsqueda para encontrar productos por nombre, ID o referencia.
    -   **Lista de productos:** Una vez que haya buscado productos, aparecerán en una lista.
    -   **Asignar iconos:** Para cada producto, verá una sección donde puede seleccionar cuáles de sus iconos creados deben mostrarse para ese producto específico. Esto suele ser un menú desplegable de selección múltiple o una lista de casillas de verificación.
    -   **Guardar cambios:** Después de asignar o desasignar iconos a un producto, recuerde guardar sus cambios.
    -   **Vista de cuadrícula / gestión:** Una tabla que muestra los productos y sus iconos actualmente asociados.
-   **Efecto de los cambios:**
    -   **Asignar un icono a un producto:** El icono seleccionado aparecerá ahora en el front office para ese producto específico (en su página de producto y en las listas de productos, dependiendo de la configuración principal de su módulo).
    -   **Desasignar un icono de un producto:** El icono ya no se mostrará para ese producto.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Después de crear sus iconos (en "Gestionar todos los iconos"), vaya a esta pantalla.
    2.  Busque el producto que desea etiquetar.
    3.  Seleccione los iconos relevantes de la lista para ese producto.
    4.  Repita para todos los productos que desee etiquetar.
    5.  Revise periódicamente sus etiquetas de producto, especialmente al lanzar nuevos productos o promociones.

### 2.4 Tabla de referencia rápida de configuración (Todas las pantallas)

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|
| **Configuración del Módulo** | Habilitar Módulo | SÍ | Activa/desactiva el módulo. |
| | Tamaño del Icono (px) | 32 | Establece el tamaño de visualización predeterminado del icono. |
| | Posición del Icono (Hook) | `displayProductAdditionalInfo` | Ubicación predeterminada en la página del producto. |
| | Mostrar Iconos en la Lista de Productos | SÍ | Muestra iconos en las páginas de categoría/búsqueda. |
| | Tipo de Tooltip | Light | Tema visual para las descripciones de los iconos. |
| | Posición del Tooltip | Top | Dónde aparece el tooltip en relación con el icono. |
| | Habilitar Animaciones de Tooltip | SÍ | Animaciones suaves para los tooltips. |
| | CSS Personalizado | (Vacío) | Añade estilos personalizados para iconos/tooltips. |
| **Gestionar Todos los Iconos** | Añadir Nuevo Icono | N/A | Crea una nueva definición de icono. |
| | Nombre del Icono | (Descriptivo) | Nombre interno del icono. |
| | Imagen del Icono | (Subir archivo) | Representación visual del icono. |
| | Descripción del Icono | (Texto del tooltip) | Texto que se muestra al pasar el ratón. |
| | Activo | SÍ | Habilita/deshabilita el icono para su uso. |
| | Editar Icono | N/A | Modifica los detalles de un icono existente. |
| | Eliminar Icono | N/A | Elimina una definición de icono. |
| **Gestionar Asociaciones de Iconos** | Búsqueda de Productos | N/A | Encuentra productos para etiquetar. |
| | Asignar Iconos | N/A | Vincula los iconos creados a productos específicos. |
| | Guardar Cambios | N/A | Aplica las asignaciones de iconos a los productos. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis iconos no aparecen en el front office, ¿qué debo hacer?**
R:

1.  **Verificar el estado del módulo:** Vaya a **Módulos > Gestor de módulos** y asegúrese de que "Product Tag Icons Pro" esté habilitado.
2.  **Verificar el estado del icono:** Vaya a **Product Tag Icons Pro > Gestionar todos los iconos** y verifique que los iconos específicos que intenta mostrar estén marcados como "Activos".
3.  **Verificar las asociaciones de productos:** Vaya a **Product Tag Icons Pro > Gestionar asociaciones de iconos** y confirme que los iconos están correctamente asignados a los productos en los que espera que aparezcan.
4.  **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché de Smarty" y "Borrar caché" (si está disponible). A veces, los datos antiguos en caché impiden que aparezcan los nuevos cambios del módulo.
5.  **Verificar la posición del hook:** En la configuración principal del módulo, asegúrese de haber seleccionado un hook válido y apropiado para la visualización de iconos (por ejemplo, `displayProductAdditionalInfo`). Algunos temas pueden tener hooks personalizados o no renderizar ciertos hooks estándar.

**P2: Los iconos se ven demasiado grandes/pequeños o no encajan con el diseño de mi tema.**
R:

1.  **Ajustar el tamaño del icono:** En la configuración principal del módulo, cambie el ajuste "Tamaño del icono (px)" a las dimensiones deseadas.
2.  **CSS personalizado:** Si un simple ajuste de tamaño no es suficiente, utilice el campo "CSS personalizado" en la configuración principal del módulo para ajustar el estilo. Puede apuntar a clases de iconos específicas (por ejemplo, `.ticon-image`) para ajustar márgenes, rellenos o incluso aplicar filtros.
3.  **Compatibilidad con el tema:** Aunque el módulo está diseñado para ser compatible, algunos temas altamente personalizados pueden requerir pequeños ajustes de CSS. Si se siente cómodo con CSS, inspeccione los elementos utilizando las herramientas de desarrollo de su navegador para identificar los selectores relevantes.

**P3: Los tooltips no aparecen o se ven extraños.**
R:

1.  **Habilitar tooltips:** Asegúrese de que la función de tooltip esté habilitada en la configuración principal del módulo.
2.  **Verificar el contenido del tooltip:** Verifique que haya introducido una "Descripción" para cada icono en **Product Tag Icons Pro > Gestionar todos los iconos**. Esta descripción es lo que aparece en el tooltip.
3.  **Tema/posición del tooltip:** Experimente con diferentes configuraciones de "Tipo de Tooltip" y "Posición del Tooltip" en la configuración principal del módulo para ver si una opción diferente resuelve el problema o se ve mejor con su tema.
4.  **Conflictos de JavaScript:** En raras ocasiones, el JavaScript de otro módulo podría entrar en conflicto. Revise la consola de desarrollador de su navegador en busca de errores de JavaScript. Si encuentra errores, intente deshabilitar temporalmente otros módulos uno por uno para aislar el conflicto.

**P4: ¿Puedo traducir los nombres y descripciones de los iconos a diferentes idiomas?**
R: ¡Sí! Cuando cree o edite un icono en **Product Tag Icons Pro > Gestionar todos los iconos**, verá pestañas de idioma (por ejemplo, "English", "French", "Spanish") junto a los campos "Nombre del icono" y "Descripción del icono". Simplemente cambie a la pestaña del idioma deseado e introduzca la traducción para ese idioma específico. El módulo mostrará automáticamente la traducción correcta según el idioma seleccionado por el cliente.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo "Product Tag Icons Pro", destinada a desarrolladores, webmasters y agencias técnicas.

### 4.1 Resumen de la arquitectura

El módulo "Product Tag Icons Pro" (`ticons`) sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente el patrón MVC. Extiende `Module` para su funcionalidad principal y utiliza instancias dedicadas de `AdminController` para gestionar los iconos y sus asociaciones. Los datos se almacenan en tablas de base de datos personalizadas, y la visualización en el front-office se logra a través de varios hooks de PrestaShop y plantillas Smarty. El módulo también integra bibliotecas de terceros para una interfaz de usuario mejorada (por ejemplo, Tooltipster para tooltips, un autocompletado personalizado para la búsqueda de productos).

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

Este módulo no define explícitamente controladores personalizados para el front-office. Toda la renderización del front-office se maneja a través de métodos `hook` dentro de la clase principal del módulo (`ajax_ticons.php`) y las plantillas Smarty asociadas.

#### Controladores de administración del Back-Office

-   **`ticons/controllers/admin/AdminTiconsAllController.php`**
    -   **Nombre de la clase:** `AdminTiconsAllController` (extiende `ModuleAdminController`)
    -   **Nombre de la pestaña:** "Gestionar todos los iconos"
    -   **Responsabilidad:** Gestiona la creación, edición y eliminación de definiciones de iconos individuales. Maneja las operaciones CRUD para la entidad `ticon`. Este controlador utiliza `HelperList` para mostrar la lista de iconos y `HelperForm` para el formulario de añadir/editar. Gestiona las cargas de imágenes de iconos.
-   **`ticons/controllers/admin/AdminTiconsAssociationsController.php`**
    -   **Nombre de la clase:** `AdminTiconsAssociationsController` (extiende `ModuleAdminController`)
    -   **Nombre de la pestaña:** "Gestionar asociaciones de iconos"
    -   **Responsabilidad:** Gestiona la asociación de iconos creados con productos específicos. Proporciona una interfaz para buscar productos y luego asignar/desasignar múltiples iconos a ellos. Este controlador también utiliza `HelperList` para la visualización de productos y un formulario personalizado para la selección de iconos. Maneja las solicitudes AJAX para el autocompletado de la búsqueda de productos.
-   **`ticons/controllers/admin/index.php`**
    -   **Responsabilidad:** Este es un archivo `index.php` vacío estándar, típicamente presente en los directorios de PrestaShop para evitar la lista de directorios. No contiene ninguna lógica de controlador funcional.

### 4.3 Clases y modelos principales (`classes/`)

El módulo no define explícitamente archivos PHP separados en un directorio `classes/`. En su lugar, el archivo principal del módulo `ajax_ticons.php` probablemente contiene las definiciones de `ObjectModel` para `Ticon` y `TiconProduct` (o entidades similares) directamente dentro de su ámbito, o se manejan implícitamente a través de interacciones con la base de datos.

-   **`Ticon` (ObjectModel implícito):**
    -   **Tabla de base de datos:** `ps_ticons` (o similar, basado en el método `install()` del módulo).
    -   **Campos:** Probablemente incluye `id_ticon`, `name` (multilenguaje), `description` (multilenguaje), `image`, `active`.
    -   **Propósito:** Representa una definición de icono individual, incluyendo su imagen, nombre y descripción del tooltip.
-   **`TiconProduct` (ObjectModel implícito):**
    -   **Tabla de base de datos:** `ps_ticon_products` (o similar, basado en el método `install()` del módulo).
    -   **Campos:** Probablemente incluye `id_ticon_product`, `id_ticon`, `id_product`.
    -   **Propósito:** Representa la relación muchos a muchos entre iconos y productos.

### 4.4 Activos JavaScript (`views/js/`)

-   **`ticons/lib/searchTool/views/js/autocomplete.js`**
    -   **Ámbito:** Back-office (AdminTiconsAssociationsController).
    -   **Funcionalidad:** Proporciona una funcionalidad de búsqueda con autocompletado para productos dentro de la pantalla "Gestionar asociaciones de iconos". Probablemente envía solicitudes AJAX al controlador de administración para obtener sugerencias de productos a medida que el usuario escribe.
-   **`ticons/lib/tooltipster/js/jquery.tooltipster.js`**
    -   **Ámbito:** Front-office.
    -   **Funcionalidad:** Esta es la biblioteca principal para el plugin Tooltipster. Maneja la creación, posicionamiento y estilo de los tooltips interactivos que aparecen cuando los usuarios pasan el ratón sobre los iconos de los productos. Vincula eventos de hover a elementos con clases específicas (por ejemplo, `.tooltipster`).
-   **`ticons/views/js/ticons-front.js`**
    -   **Ámbito:** Front-office.
    -   **Funcionalidad:** Contiene JavaScript personalizado específico para la visualización de iconos en el front-office. Este script probablemente inicializa el plugin Tooltipster en los elementos de icono relevantes, pasando opciones de configuración (tema, posición, animación) basadas en la configuración del back-office del módulo. Asegura que los iconos se rendericen correctamente y sean interactivos.
-   **`ticons/views/js/ticons.js`**
    -   **Ámbito:** Back-office.
    -   **Funcionalidad:** Contiene JavaScript general para las pantallas de configuración y gestión del back-office del módulo. Esto podría incluir validación de formularios, manipulación dinámica de elementos u otras mejoras de la interfaz de usuario para la interfaz de administración.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   **`ticons/lib/searchTool/views/css/autocomplete.css`**
    -   **Ámbito:** Back-office.
    -   **Funcionalidad:** Estiliza el menú desplegable de autocompletado y el campo de entrada utilizados en la pantalla "Gestionar asociaciones de iconos".
-   **`ticons/lib/tooltipster/css/themes/tooltipster-light.css`**
    -   **Ámbito:** Front-office.
    -   **Funcionalidad:** Define los estilos para el tema "Light" del plugin Tooltipster.
-   **`ticons/lib/tooltipster/css/themes/tooltipster-noir.css`**
    -   **Ámbito:** Front-office.
    -   **Funcionalidad:** Define los estilos para el tema "Noir" del plugin Tooltipster.
-   **`ticons/lib/tooltipster/css/themes/tooltipster-punk.css`**
    -   **Ámbito:** Front-office.
    -   **Funcionalidad:** Define los estilos para el tema "Punk" del plugin Tooltipster.
-   **`ticons/lib/tooltipster/css/themes/tooltipster-shadow.css`**
    -   **Ámbito:** Front-office.
    -   **Funcionalidad:** Define los estilos para el tema "Shadow" del plugin Tooltipster.
-   **`ticons/lib/tooltipster/css/tooltipster.css`**
    -   **Ámbito:** Front-office.
    -   **Funcionalidad:** El CSS principal para el plugin Tooltipster, que proporciona estilos base para todos los tooltips.
-   **`ticons/views/css/ticons-admin.css`**
    -   **Ámbito:** Back-office.
    -   **Funcionalidad:** Contiene CSS personalizado específicamente para las interfaces del back-office del módulo (por ejemplo, estilo para listas de iconos, formularios y elementos personalizados en los controladores de administración).
-   **`ticons/views/css/ticons-fontawesome.css`**
    -   **Ámbito:** Front-office.
    -   **Funcionalidad:** Probablemente incluye o importa iconos de Font Awesome, que podrían usarse como iconos de respaldo o para elementos de interfaz de usuario específicos dentro de la visualización del módulo.
-   **`ticons/views/css/ticons-front-24.css`**, **`ticons/views/css/ticons-front-32.css`**, **`ticons/views/css/ticons-front-48.css`**, **`ticons/views/css/ticons-front-64.css`**, **`ticons/views/css/ticons-front-74.css`**
    -   **Ámbito:** Front-office.
    -   **Funcionalidad:** Estas hojas de estilo probablemente contienen reglas específicas para diferentes tamaños de iconos. Cuando el comerciante selecciona un "Tamaño de icono" en la configuración, el módulo carga dinámicamente el archivo CSS correspondiente para asegurar que los iconos se rendericen con las dimensiones correctas y, potencialmente, con un espaciado optimizado. Definen clases como `.ticon-24`, `.ticon-32`, etc.
-   **`ticons/views/css/ticons.css`**
    -   **Ámbito:** Front-office.
    -   **Funcionalidad:** CSS general del front-office para el módulo, incluyendo estilos base para los contenedores de iconos, imágenes y diseño general. Este archivo podría contener reglas comunes aplicadas independientemente del tamaño de icono seleccionado.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

#### Plantillas de hook (`views/templates/front/`)

Estas plantillas se renderizan cuando el módulo se engancha en varias posiciones del front-office. Normalmente reciben una matriz de datos de iconos de los métodos `hook` del módulo.

-   **`ticons/views/templates/front/deliveryTime.tpl`**
    -   **Hook:** Potencialmente `displayProductDeliveryTime` o similar.
    -   **Salida:** Renderiza iconos relacionados con la información de entrega.
-   **`ticons/views/templates/front/displayActions.tpl`**
    -   **Hook:** `displayProductActions` o similar.
    -   **Salida:** Renderiza iconos cerca de los botones de acción del producto (por ejemplo, "Añadir al carrito").
-   **`ticons/views/templates/front/displayAfterProductThumbs.tpl`**
    -   **Hook:** `displayAfterProductThumbs` (PrestaShop 1.7+).
    -   **Salida:** Renderiza iconos directamente debajo de las imágenes en miniatura del producto en la página del producto.
-   **`ticons/views/templates/front/displayColumns.tpl`**
    -   **Hook:** `displayLeftColumn`, `displayRightColumn`.
    -   **Salida:** Renderiza iconos dentro de los módulos de columna izquierda o derecha.
-   **`ticons/views/templates/front/displayLeftColumn.tpl`**
    -   **Hook:** `displayLeftColumn`.
    -   **Salida:** Renderiza iconos específicamente en la columna izquierda.
-   **`ticons/views/templates/front/displayProductAdditionalInfo.tpl`**
    -   **Hook:** `displayProductAdditionalInfo` (PrestaShop 1.7+).
    -   **Salida:** Renderiza iconos en la sección "Información adicional" de la página del producto, una ubicación común y recomendada.
-   **`ticons/views/templates/front/displayProductPriceBlock.tpl`**
    -   **Hook:** `displayProductPriceBlock`.
    -   **Salida:** Renderiza iconos cerca del bloque de precios del producto.
-   **`ticons/views/templates/front/displayTop.tpl`**
    -   **Hook:** `displayTop` (cabecera).
    -   **Salida:** Renderiza iconos en la sección de la cabecera de la tienda.
-   **`ticons/views/templates/front/listReviews.tpl`**
    -   **Hook:** Potencialmente `displayProductListReviews` o similar.
    -   **Salida:** Renderiza iconos relacionados con reseñas o valoraciones de productos.
-   **`ticons/views/templates/front/productFooter.tpl`**
    -   **Hook:** `displayFooterProduct` o similar.
    -   **Salida:** Renderiza iconos en la sección del pie de página de la página del producto.
-   **`ticons/views/templates/front/showIcons.tpl`**
    -   **Hook:** Esta es probablemente una plantilla genérica incluida por otras plantillas de hook para renderizar la estructura HTML real del icono (por ejemplo, etiquetas `<img>` con clases `tooltipster`). Itera sobre la variable `$icons` que se le pasa.

#### Plantillas de administración (`views/templates/admin/`)

Estas plantillas se utilizan para las pantallas de configuración y gestión del back-office del módulo.

-   **`ticons/lib/searchTool/views/scripts.tpl`**
    -   **Ámbito:** Back-office.
    -   **Salida:** Contiene JavaScript para la herramienta de búsqueda, probablemente incluyendo la inicialización de autocompletado de jQuery UI o similar.
-   **`ticons/views/templates/admin/customHook.tpl`**
    -   **Ámbito:** Back-office.
    -   **Salida:** Una plantilla genérica que podría usarse para renderizar contenido para hooks personalizados definidos dentro de la interfaz de administración del módulo, o para mostrar mensajes específicos.
-   **`ticons/views/templates/admin/tabs.tpl`**
    -   **Ámbito:** Back-office.
    -   **Salida:** Renderiza las pestañas de navegación (por ejemplo, "Gestionar todos los iconos", "Gestionar asociaciones de iconos") para las páginas de configuración del módulo.
-   **`ticons/views/templates/admin/ticonsSelection.tpl`**
    -   **Ámbito:** Back-office (AdminTiconsAssociationsController).
    -   **Salida:** Renderiza la interfaz para seleccionar y asignar iconos a un producto, normalmente un menú desplegable de selección múltiple o una lista de casillas de verificación dentro del formulario de asociación de productos.
-   **`ticons/views/templates/admin/ticons_all/helpers/list/list_content.tpl`**
    -   **Ámbito:** Back-office (AdminTiconsAllController).
    -   **Salida:** Personaliza el contenido de la tabla `HelperList` para mostrar la lista de todos los iconos creados. Podría incluir columnas personalizadas para imágenes de iconos o estado activo.
-   **`ticons/views/templates/admin/ticons_associations/helpers/form/form.tpl`**
    -   **Ámbito:** Back-office (AdminTiconsAssociationsController).
    -   **Salida:** Personaliza el `HelperForm` para la pantalla de asociación de productos. Esta plantilla probablemente incluye la entrada de búsqueda de productos y el `ticonsSelection.tpl` para la asignación de iconos.
-   **`ticons/views/templates/admin/ticons_associations/helpers/list/list_content.tpl`**
    -   **Ámbito:** Back-office (AdminTiconsAssociationsController).
    -   **Salida:** Personaliza el contenido de la tabla `HelperList` para mostrar la lista de productos y sus iconos asociados.

### 4.7 Esquema de la base de datos y mapa de Hooks

#### Tablas de la base de datos

El módulo crea tablas personalizadas durante su método `install()` para almacenar las definiciones de iconos y sus asociaciones:

-   **`ps_ticons`**: Almacena las definiciones principales de los iconos.
    -   `id_ticon` (PK, INT)
    -   `image` (VARCHAR): Nombre del archivo de la imagen del icono.
    -   `active` (TINYINT): 1 si está activo, 0 si está inactivo.
-   **`ps_ticons_lang`**: Almacena campos multilingües para los iconos.
    -   `id_ticon` (PK, INT)
    -   `id_lang` (PK, INT)
    -   `name` (VARCHAR): Nombre del icono para uso interno.
    -   `description` (TEXT): Texto del tooltip para el icono.
-   **`ps_ticon_products`**: Almacena la relación muchos a muchos entre iconos y productos.
    -   `id_ticon_product` (PK, INT)
    -   `id_ticon` (FK, INT)
    -   `id_product` (FK, INT)

La configuración se almacena en `ps_configuration` con claves como `TICONS_ICON_SIZE`, `TICONS_HOOK_POSITION`, `TICONS_SHOW_IN_LIST`, etc.

#### Tabla de Hooks registrados

El módulo registra varios hooks para mostrar iconos en el front office. Los hooks exactos utilizados dependen de la versión de PrestaShop y la configuración del comerciante.

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Encola activos CSS y JS (Tooltipster, JS/CSS personalizado). |
| `displayProductAdditionalInfo` | En la página del producto, dentro del bloque "Información adicional" (PS 1.7+). | Renderiza iconos asociados con el producto actual. |
| `displayProductPriceBlock` | En la página del producto, cerca del precio. | Renderiza iconos asociados con el producto actual. |
| `displayAfterProductThumbs` | En la página del producto, debajo de las imágenes del producto (PS 1.7+). | Renderiza iconos asociados con el producto actual. |
| `displayProductListFunctionalButtons` | En los elementos de la lista de productos (por ejemplo, páginas de categoría). | Renderiza iconos en las tarjetas/miniaturas de los productos. |
| `displayProductListReviews` | En los elementos de la lista de productos, cerca de las reseñas. | Renderiza iconos en las tarjetas/miniaturas de los productos. |
| `displayProductDeliveryTime` | En la página del producto, cerca de la información de entrega. | Renderiza iconos asociados con el producto actual. |
| `displayLeftColumn` | En la columna izquierda de las páginas. | Renderiza iconos si está configurado para visualización general. |
| `displayRightColumn` | En la columna derecha de las páginas. | Renderiza iconos si está configurado para visualización general. |
| `displayFooterProduct` | En la parte inferior de la página del producto. | Renderiza iconos asociados con el producto actual. |
| `actionProductUpdate` | Después de que un producto se actualiza en el back office. | Potencialmente borra la caché o actualiza las asociaciones de iconos. |
| `actionProductDelete` | Después de que un producto se elimina. | Limpia las entradas de iconos asociados de `ps_ticon_products`. |
| `actionObjectLanguageAddAfter` | Después de que se añade un nuevo idioma. | Asegura que los campos específicos del idioma para los iconos se manejen. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto al módulo "Product Tag Icons Pro".
