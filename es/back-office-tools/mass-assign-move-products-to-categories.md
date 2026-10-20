---
title: "Asignar / mover productos masivamente a categorías - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Asignar / mover productos masivamente a categorías' de MyPresta.eu."
sidebar:
  label: "Asignar / mover productos masivamente a categorías - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Mass assign / move products to categories en MyPresta.eu](https://mypresta.eu/modules/administration-tools/mass-assign-move-products-to-categories.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/mass-assign-move-products-to-categories/)
>
> ---


# Asignar / mover productos masivamente a categorías

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 9.x, 8.x, 1.7.x, 1.6.x, 1.5.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se requieren configuraciones de servidor especiales más allá de un entorno de alojamiento PrestaShop estándar.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

El módulo "Asignar / mover productos masivamente a categorías" proporciona una interfaz tipo asistente para guiarle a través del proceso de gestión masiva de categorías de productos.

### 2.1 Página de configuración del módulo (Back Office > Módulos > Gestor de módulos > Configurar "Asignar / mover productos masivamente a categorías")

Al hacer clic en "Configurar", accederá a la página de configuración principal del módulo, que actúa como un asistente paso a paso.

#### Paso 1: Seleccionar productos para gestionar

Esta sección le permite definir qué productos desea modificar.

-   **Qué hace este ajuste:** Este es el primer paso crucial donde identifica el grupo de productos que se verán afectados por la acción masiva.
-   **Efecto de cambiar este ajuste:** Los productos que seleccione aquí serán los únicos procesados en los pasos subsiguientes.
-   **Valor recomendado:** Utilice la barra de búsqueda para encontrar productos por nombre. Puede añadir varios productos a la lista.
-   **Escenario / ejemplo de comerciante:**
    -   *Escenario 1: Productos específicos:* Desea mover "Producto A", "Producto B" y "Producto C" a una nueva categoría. Buscaría cada producto y los añadiría a la lista.
    -   *Escenario 2: Productos de una categoría existente:* Desea mover todos los productos actualmente en su categoría "Colección Antigua" a una nueva categoría "Artículos Archivados". Primero seleccionaría todos los productos de "Colección Antigua" aquí.

#### Paso 2: Seleccionar categorías para asignar/mover productos

Esta sección le permite elegir las categorías de destino para sus productos seleccionados.

-   **Qué hace este ajuste:** Aquí, especifica las categorías donde se asignarán o moverán los productos del Paso 1.
-   **Efecto de cambiar este ajuste:** Los productos seleccionados se vincularán a estas categorías.
-   **Valor recomendado:** Utilice el árbol de categorías para seleccionar una o más categorías de destino.
-   **Escenario / ejemplo de comerciante:**
    -   *Escenario 1: Asignar a una nueva categoría:* Ha seleccionado 5 productos en el Paso 1. Ahora selecciona "Novedades" y "Más vendidos" aquí. Los 5 productos se asignarán tanto a "Novedades" como a "Más vendidos".
    -   *Escenario 2: Mover a una sola categoría:* Ha seleccionado 10 productos. Selecciona "Oferta de temporada" aquí. Dependiendo de su elección en el Paso 3, estos productos se añadirán a "Oferta de temporada" o se moverán exclusivamente a ella.

#### Paso 3: ¿Qué hacer con los productos seleccionados?

Este es el paso más crítico, que determina la naturaleza de la acción masiva.

-   **Qué hace este ajuste:** Esta selección de botón de radio dicta si los productos se *asignan* (se añaden a nuevas categorías manteniendo las existentes) o se *mueven* (se eliminan de las categorías existentes y se colocan solo en las nuevas).
-   **Efecto de cambiar este ajuste:**
    -   **Asignar productos a las categorías seleccionadas:**
        -   *Cuando se selecciona:* Los productos elegidos en el Paso 1 se *añadirán* a las categorías seleccionadas en el Paso 2. Conservarán todas sus asociaciones de categoría actuales. Esto es útil para listar productos en varias categorías o añadirlos a categorías promocionales sin alterar su ubicación principal.
        -   *Escenario de comerciante:* Tiene un producto en "Electrónica" y "Gadgets". Quiere añadirlo a "Ofertas de Vacaciones" sin eliminarlo de "Electrónica" o "Gadgets". Seleccionaría "Asignar".
    -   **Mover productos a las categorías seleccionadas (eliminar de las categorías actuales):**
        -   *Cuando se selecciona:* Los productos elegidos en el Paso 1 se *eliminarán* de todas las categorías a las que están asignados actualmente, y luego *solo* se asignarán a las categorías seleccionadas en el Paso 2. Esta es una recategorización completa.
        -   *Escenario de comerciante:* Tiene un producto en "Colección Antigua" y "Artículos Descatalogados". Quiere que *solo* aparezca en "Productos Archivados". Seleccionaría "Mover".
-   **Valor recomendado:** Esto depende completamente de su objetivo específico. Considere cuidadosamente si desea *añadir* categorías o *reemplazarlas*.
-   **Escenario / ejemplo de comerciante:**
    -   *Asignar:* Está realizando una venta de "Black Friday". Selecciona todos los productos en oferta y los "Asigna" a la categoría "Ofertas de Black Friday". Siguen apareciendo en sus categorías originales (por ejemplo, "Camisetas", "Portátiles"), pero ahora también en "Ofertas de Black Friday".
    -   *Mover:* Ha decidido reestructurar su sección de "Ropa de Mujer". Selecciona todos los productos de "Vestidos" y "Faldas" y los "Mueve" a una nueva categoría "Partes de abajo y Vestidos de Mujer". Ya no aparecerán en las antiguas categorías "Vestidos" o "Faldas".

#### Botón "Ejecutar"

-   **Qué hace este ajuste:** Este botón inicia la operación masiva basándose en sus selecciones en los pasos anteriores.
-   **Efecto de cambiar este ajuste:** Una vez hecho clic, el módulo procesará todos los productos seleccionados de acuerdo con la acción elegida (asignar o mover) y las categorías de destino. Normalmente aparecerá un mensaje de confirmación o éxito.
-   **Valor recomendado:** Haga clic en esto solo cuando esté absolutamente seguro de sus selecciones.
-   **Escenario / ejemplo de comerciante:** Después de revisar cuidadosamente sus selecciones de productos y categorías y confirmar la acción deseada (asignar o mover), haga clic en "Ejecutar" para aplicar los cambios al catálogo de productos de su tienda.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración principal | **Paso 1: Seleccionar productos** | N/A (entrada del usuario) | Define los productos específicos que se verán afectados por la acción masiva. |
| Configuración principal | **Paso 2: Seleccionar categorías** | N/A (entrada del usuario) | Define las categorías de destino donde se asignarán o moverán los productos. |
| Configuración principal | **Paso 3: ¿Qué hacer?** | N/A (elección del usuario) | **Asignar:** Añade productos a nuevas categorías, manteniendo las existentes. **Mover:** Elimina de todas las categorías actuales, asigna solo a las nuevas. |
| Configuración principal | **Botón Ejecutar** | N/A (acción del usuario) | Activa la operación masiva de asignación/movimiento de categorías. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Hice clic en "Ejecutar", pero no pasó nada o no veo los cambios.**
R:

1.  **Borrar caché:** Después de cualquier cambio significativo en PrestaShop, especialmente asignaciones de categorías o productos, siempre debe borrar la caché de su tienda. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).
2.  **Verificar estado del producto:** Asegúrese de que los productos que intenta asignar/mover estén activos y visibles.
3.  **Verificar estado de la categoría:** Asegúrese de que las categorías de destino estén activas y visibles.
4.  **Volver a ejecutar el módulo:** Vuelva al módulo, vuelva a seleccionar sus productos y categorías, e inténtelo de nuevo.

**P: ¡Mis productos desaparecieron de sus categorías originales después de usar el módulo!**
R: Esto probablemente significa que seleccionó "Mover productos a las categorías seleccionadas (eliminar de las categorías actuales)" en el Paso 3. Esta opción está diseñada para *reemplazar* las asignaciones de categorías existentes con las nuevas. Si esto fue involuntario, deberá reasignar manualmente los productos a sus categorías originales o usar el módulo nuevamente con la opción "Asignar productos" para volver a añadirlos. ¡Siempre verifique el Paso 3 antes de ejecutar!

**P: ¿Puedo deshacer una asignación/movimiento masivo?**
R: El módulo no tiene un botón "deshacer". Por eso es crucial **siempre hacer una copia de seguridad de su base de datos antes de realizar cualquier acción masiva** en su tienda. Si cometió un error, restaurar una copia de seguridad es la forma más segura de revertir. De lo contrario, deberá corregir manualmente las asignaciones de categorías o usar el módulo nuevamente para reasignar productos según sea necesario.

**P: La búsqueda de productos no encuentra mis productos.**
R:

1.  **Verificar ortografía:** Asegúrese de escribir el nombre del producto correctamente.
2.  **Estado del producto:** Asegúrese de que el producto esté activo en su catálogo.
3.  **Borrar caché del navegador:** A veces, la caché del navegador puede interferir con las funciones de búsqueda AJAX. Intente borrar la caché de su navegador o usar una ventana de incógnito.

**P: ¿Este módulo afecta la categoría predeterminada de un producto?**
R: El módulo gestiona principalmente las categorías *asociadas*. Si bien mover un producto podría cambiar implícitamente su categoría predeterminada si la antigua predeterminada se elimina y solo se asigna una nueva categoría, es una buena práctica verificar y establecer manualmente la categoría predeterminada en la página de edición del producto si tiene requisitos específicos de SEO o navegación para la categoría predeterminada.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una visión técnica para desarrolladores y webmasters que buscan comprender, depurar o extender el módulo "Asignar / mover productos masivamente a categorías".

### 4.1 Visión general de la arquitectura

El módulo `masspc` (Mass Product Categories) es un módulo estándar de PrestaShop que opera principalmente dentro del Back Office. Aprovecha AJAX para la búsqueda de productos y la selección de categorías, proporcionando una experiencia de usuario tipo asistente. La lógica central para la manipulación de productos y categorías se maneja dentro de la clase principal del módulo, que extiende `Module`. No introduce clases `ObjectModel` personalizadas ni Controladores de Administración dedicados más allá de su página de configuración principal.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza Controladores de Administración dedicados de Front-Office o Back-Office en el directorio `controllers/`. Toda la lógica se maneja directamente dentro del archivo principal del módulo `masspc.php` (o `ajax_products_list.php` según el dossier, lo cual es una convención de nombres inusual para el archivo principal del módulo, pero implica que maneja la lógica central y las solicitudes AJAX).

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no introduce ninguna clase o modelo personalizado en un directorio `classes/`. Toda la lógica central está encapsulada dentro del archivo principal del módulo. La manipulación de datos de productos y categorías se basa en las clases `ObjectModel` nativas de PrestaShop `Product` y `Category` y sus métodos asociados (por ejemplo, `Product::updateCategories()`).

### 4.4 Activos JavaScript (`views/js/`)

-   **`masspc/lib/searchTool/views/js/autocomplete.js`**
    -   **Alcance:** Back-office (utilizado dentro de la página de configuración del módulo).
    -   **Descripción:** Este script probablemente proporciona la funcionalidad principal para una función de búsqueda de autocompletado basada en AJAX, específicamente para encontrar productos por nombre. Escucha la entrada del usuario en un campo de búsqueda, envía solicitudes AJAX al backend del módulo (probablemente el propio `ajax_products_list.php` o un método dentro de él), y muestra sugerencias. Maneja la selección de productos y su adición a la lista para su procesamiento.
-   **`masspc/views/js/jquery.autocomplete.js`**
    -   **Alcance:** Back-office (utilizado dentro de la página de configuración del módulo).
    -   **Descripción:** Parece ser un plugin de jQuery o un script personalizado que implementa o mejora la funcionalidad de autocompletado. Podría ser una dependencia para `autocomplete.js` o una implementación alternativa/anterior. Manejaría la representación visual de las sugerencias de autocompletado y la interacción cuando un usuario selecciona un elemento.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   **`masspc/lib/searchTool/views/css/autocomplete.css`**
    -   **Alcance:** Back-office (estiliza la página de configuración del módulo).
    -   **Descripción:** Esta hoja de estilo proporciona el estilo visual para el campo de entrada de búsqueda de autocompletado, el menú desplegable de sugerencias y, potencialmente, la lista de productos seleccionados dentro de la interfaz de configuración del módulo. Los desarrolladores pueden anular estos estilos en su tema de administración personalizado o añadiendo reglas CSS más específicas.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **`masspc/lib/searchTool/views/scripts.tpl`**
    -   **Alcance:** Back-office (incluido en la página de configuración del módulo).
    -   **Descripción:** Esta plantilla probablemente incluye código JavaScript o enlaces a archivos JS (`autocomplete.js`, `jquery.autocomplete.js`) y potencialmente archivos CSS (`autocomplete.css`) necesarios para la interfaz de búsqueda y selección de productos. Se utiliza típicamente para inyectar activos en el `<head>` o `<body>` de la página de administración.
-   **`masspc/views/templates/admin/cselection.tpl`**
    -   **Alcance:** Back-office (página de configuración de administración).
    -   **Descripción:** Esta plantilla renderiza la sección "Paso 2: Seleccionar categorías para asignar/mover productos" del módulo. Muestra la estructura del árbol de categorías, permitiendo al administrador seleccionar categorías de destino. Probablemente utiliza una estructura recursiva para mostrar categorías padre e hijo.
-   **`masspc/views/templates/admin/target_products.tpl`**
    -   **Alcance:** Back-office (página de configuración de administración).
    -   **Descripción:** Esta plantilla renderiza la sección "Paso 1: Seleccionar productos para gestionar". Incluye el campo de entrada de búsqueda de productos (donde opera `autocomplete.js`) y muestra la lista de productos que han sido seleccionados para la acción masiva.
-   **`masspc/views/templates/admin/wtd.tpl`**
    -   **Alcance:** Back-office (página de configuración de administración).
    -   **Descripción:** Esta plantilla renderiza la sección "Paso 3: ¿Qué hacer con los productos seleccionados?". Contiene los botones de radio para "Asignar productos a las categorías seleccionadas" y "Mover productos a las categorías seleccionadas", junto con sus descripciones.
-   **`masspc/views/templates/hook/form.tpl`**
    -   **Alcance:** Back-office (página de configuración de administración).
    -   **Descripción:** Esta es probablemente la plantilla principal de envoltura para el formulario de configuración del módulo, que incluye las otras plantillas `admin/` (`target_products.tpl`, `cselection.tpl`, `wtd.tpl`) para construir la interfaz completa del asistente. Contendría la estructura general del formulario y el botón "Ejecutar".

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:
    -   Este módulo no crea ninguna tabla de base de datos personalizada. Interactúa directamente con las tablas principales de PrestaShop:
        -   `ps_product_category`: Para gestionar las asociaciones de productos a categorías.
        -   `ps_product_shop`: Para datos específicos de la tienda del producto, incluida la categoría predeterminada.
        -   `ps_category`: Para recuperar nombres y estructura de categorías.
        -   `ps_product`: Para recuperar nombres y detalles de productos para la búsqueda.
-   **Tabla de Hooks registrados**:
    -   La funcionalidad principal del módulo se accede a través de su página de configuración, no a través de hooks de front-office.
    -   Probablemente utiliza el hook `displayBackOfficeHeader` para inyectar sus activos CSS y JavaScript en el encabezado del Back Office.

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayBackOfficeHeader` | Se renderiza en el `<head>` de las páginas del Back Office. | Inyecta archivos CSS y JavaScript específicos del módulo para la página de configuración. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Asignar / mover productos masivamente a categorías", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.
