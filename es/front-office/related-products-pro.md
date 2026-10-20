---
title: "Related Products Pro - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Related Products Pro para PrestaShop de MyPresta.eu."
sidebar:
  label: "Related Products Pro - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Related Products Pro en MyPresta.eu](https://mypresta.eu/modules/front-office-features/related-products-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/related-products-pro/)
>
> ---


# Related Products Pro

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop soportadas**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias y normalmente están habilitadas por defecto en la mayoría de los entornos de alojamiento.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Gestor de módulos > Related Products Pro > Configurar)

Esta es la pantalla de configuración principal donde gestionará todos los aspectos de sus listas de productos relacionados. La interfaz está diseñada para ser intuitiva, permitiéndole crear, editar y asignar productos relacionados con facilidad.

La página de configuración normalmente presentará una lista de sus listas de productos relacionados existentes (si las hay) y opciones para crear nuevas o gestionar la configuración global.

#### **Elementos principales de la interfaz:**

-   **Lista de bloques de productos relacionados existentes:** Esta tabla mostrará todas las listas de productos relacionados que ha creado. Para cada lista, verá detalles como su nombre, los productos a los que está asignada y opciones para editarla o eliminarla.
-   **Botón "Añadir nuevo bloque de productos relacionados":** Haga clic aquí para crear un nuevo conjunto de productos relacionados.
-   **Configuración/Preferencias globales:** (Si están disponibles) Estos ajustes podrían controlar las opciones generales de visualización o los comportamientos predeterminados para todos los bloques de productos relacionados.

#### **Al añadir/editar un bloque de productos relacionados:**

Cuando haga clic para añadir un nuevo bloque o editar uno existente, normalmente verá un formulario con los siguientes ajustes:

1.  **Nombre del bloque:**

    -   **Qué hace este ajuste:** Este es el nombre interno de su lista de productos relacionados, visible solo en el Back Office. Le ayuda a identificar diferentes listas.
    -   **Efecto de cambiar este ajuste:** Cambia la etiqueta de este bloque de productos relacionados específico en su panel de administración.
    -   **Valor recomendado:** Use un nombre descriptivo, por ejemplo, "Producto X - Artículos Complementarios", "Categoría Y - Superventas".
    -   **Escenario/ejemplo de comerciante:** Podría nombrar una lista "Vestidos de Verano - Sandalias a juego" para encontrarla fácilmente más tarde.
2.  **Ubicación de visualización (Hook):**

    -   **Qué hace este ajuste:** Determina dónde aparecerá este bloque de productos relacionados específico en la página del producto. Selecciona un "hook" de PrestaShop, que es un área de visualización designada.
    -   **Efecto de cambiar este ajuste:** Los productos relacionados se moverán a la ubicación elegida en la página del producto del front office.
    -   **Valor recomendado:** Experimente con diferentes hooks según su tema. Las opciones comunes incluyen `displayProductExtraContent` (a menudo cerca de la descripción del producto), `displayProductFooter` (en la parte inferior de la página del producto) o `displayRightColumnProduct` (si su tema tiene una columna derecha en las páginas de productos).
    -   **Escenario/ejemplo de comerciante:** Si desea que los productos relacionados aparezcan justo debajo de la imagen y descripción principal del producto, podría elegir `displayProductExtraContent`. Si los prefiere en la parte inferior de la página, `displayProductFooter` sería mejor.
3.  **Productos a mostrar:**

    -   **Qué hace este ajuste:** Aquí es donde define *qué* productos se mostrarán en este bloque de productos relacionados. Normalmente tendrá varias opciones:
        -   **Productos específicos (Selección manual):**
            -   **Qué hace:** Le permite buscar y seleccionar manualmente productos individuales para incluir en la lista.
            -   **Efecto:** Solo aparecerán los productos que elija explícitamente.
            -   **Recomendado:** Use para recomendaciones altamente curadas.
            -   **Escenario:** Para una cámara específica, podría seleccionar manualmente un trípode, una bolsa para la cámara y una lente adicional.
        -   **Productos de categorías seleccionadas:**
            -   **Qué hace:** Muestra productos de una o más categorías que seleccione.
            -   **Efecto:** La lista mostrará dinámicamente productos de esas categorías.
            -   **Recomendado:** Bueno para mostrar artículos relacionados dentro de una línea de productos o departamento.
            -   **Escenario:** Para una "Camisa de Hombre", podría seleccionar las categorías "Pantalones de Hombre" y "Accesorios de Hombre".
        -   **Nuevos productos:**
            -   **Qué hace:** Muestra automáticamente los productos más nuevos añadidos a su tienda.
            -   **Efecto:** La lista siempre mostrará sus últimas incorporaciones.
            -   **Recomendado:** Ideal para promocionar novedades.
            -   **Escenario:** Use este bloque para destacar su última colección de joyas.
        -   **Superventas:**
            -   **Qué hace:** Muestra automáticamente los productos más vendidos de su tienda.
            -   **Efecto:** La lista se actualizará dinámicamente para mostrar sus artículos más populares.
            -   **Recomendado:** Excelente para la prueba social y la promoción de artículos populares.
            -   **Escenario:** Muestre artículos "Los clientes también compraron" basándose en la popularidad general de la tienda.
    -   **Número de productos a mostrar:**
        -   **Qué hace:** Controla cuántos productos relacionados se muestran en el bloque.
        -   **Efecto:** Limita los productos visibles.
        -   **Recomendado:** 4-8 productos para un aspecto limpio, dependiendo de su diseño.
        -   **Escenario:** Muestre 5 artículos relacionados para mantener la sección concisa.
4.  **Asignar a productos:**

    -   **Qué hace este ajuste:** Esto es crucial: determina *en qué páginas de producto* aparecerá este bloque de productos relacionados específico.
    -   **Efecto de cambiar este ajuste:** El bloque de productos relacionados solo será visible en las páginas de producto que seleccione aquí.
    -   **Valor recomendado:** Puede asignarlo a:
        -   **Todos los productos:** Si se trata de un bloque general de "Superventas" o "Novedades".
        -   **Productos específicos (Selección manual):** Para recomendaciones altamente dirigidas.
        -   **Productos de categorías seleccionadas:** Para aplicar el bloque a un rango completo de categorías.
    -   **Escenario/ejemplo de comerciante:** Crea una lista de "Accesorios para iPhone". Luego asignaría este bloque solo a las páginas de productos de su iPhone. O, crea un bloque de "Artículos de Rebajas de Verano" y lo asigna a todos los productos dentro de su categoría "Colección de Verano".
5.  **Tipo de visualización / Plantilla:**

    -   **Qué hace este ajuste:** Le permite elegir el diseño visual o la plantilla para cómo se muestran los productos relacionados (por ejemplo, cuadrícula, carrusel, lista, tabla). El módulo a menudo incluye varias plantillas, algunas de las cuales pueden estar optimizadas para temas específicos (como los temas Panda, Warehouse, Zone).
    -   **Efecto de cambiar este ajuste:** Cambia la presentación visual de los productos relacionados en el front office.
    -   **Valor recomendado:** Experimente para encontrar el mejor ajuste para su tema y el hook elegido. Un carrusel suele ser bueno para ahorrar espacio, mientras que una cuadrícula podría ser mejor para una sección dedicada.
    -   **Escenario/ejemplo de comerciante:** Si desea una visualización elegante y que ahorre espacio, podría elegir una plantilla de "carrusel". Si tiene mucho espacio y desea mostrar más detalles, una "cuadrícula" o "tabla" podría ser mejor. Algunas plantillas podrían estar específicamente nombradas para temas populares (por ejemplo, `panda-blocksProductsCart.tpl`) para asegurar una mejor integración.
6.  **Configuración del carrusel (si aplica):**

    -   **Qué hace este ajuste:** Si elige un tipo de visualización de carrusel, podría tener opciones adicionales como:
        -   **Reproducción automática:** Si el carrusel se desplaza automáticamente.
        -   **Bucle:** Si el carrusel se repite desde el principio después del último elemento.
        -   **Elementos por vista:** Cuántos productos son visibles a la vez en el carrusel.
        -   **Flechas/puntos de navegación:** Si se muestran controles para el desplazamiento manual.
    -   **Efecto de cambiar este ajuste:** Controla el comportamiento y la apariencia del carrusel de productos.
    -   **Valor recomendado:** La reproducción automática puede ser atractiva, pero también puede distraer. Considere a su audiencia. 3-5 elementos por vista es un buen equilibrio común.
    -   **Escenario/ejemplo de comerciante:** Desea un carrusel sutil que se desplace automáticamente cada 5 segundos, mostrando 4 productos a la vez, con flechas de navegación para los usuarios que deseen navegar manualmente.

#### **Guardar sus cambios:**

Recuerde siempre hacer clic en el botón "Guardar" o "Actualizar" después de realizar cualquier cambio en un bloque de productos relacionados para asegurarse de que sus ajustes se apliquen.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Página de Configuración del Módulo** | **Nombre del Bloque** | Descriptivo (ej., "Producto X - Venta Cruzada") | Etiqueta interna para identificar el bloque de productos relacionados en el Back Office. |
| | **Ubicación de Visualización (Hook)** | `displayProductExtraContent` o `displayProductFooter` | Determina dónde aparece el bloque en la página del producto del front-office. |
| | **Productos a Mostrar: Productos Específicos** | Selección manual | Muestra solo productos seleccionados a mano. Ideal para recomendaciones altamente curadas. |
| | **Productos a Mostrar: De Categorías Seleccionadas** | Seleccionar categorías relevantes | Muestra dinámicamente productos de las categorías elegidas. Bueno para líneas de productos relacionadas. |
| | **Productos a Mostrar: Nuevos Productos** | Relleno automático | Muestra automáticamente los últimos productos de su tienda. Ideal para novedades. |
| | **Productos a Mostrar: Superventas** | Relleno automático | Muestra automáticamente los productos más vendidos de su tienda. Excelente para prueba social. |
| | **Número de Productos a Mostrar** | 4-8 | Limita el número de productos mostrados en el bloque para un diseño limpio. |
| | **Asignar a Productos: Todos los Productos** | N/A | Muestra el bloque en cada página de producto. Use para recomendaciones generales. |
| | **Asignar a Productos: Productos Específicos** | Selección manual | Muestra el bloque solo en las páginas de productos seleccionadas. Para ventas cruzadas dirigidas. |
| | **Asignar a Productos: De Categorías Seleccionadas** | Seleccionar categorías relevantes | Muestra el bloque en las páginas de productos dentro de las categorías elegidas. |
| | **Tipo de Visualización / Plantilla** | `accessories.tpl` o específico del tema | Controla el diseño visual (cuadrícula, carrusel, lista). Elija según el tema y el hook. |
| | **Configuración del Carrusel (Reproducción automática, Bucle, Elementos por vista, Navegación)** | Varía, a menudo habilitado | Controla el comportamiento de las visualizaciones de carrusel. Ajuste para la experiencia del usuario. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: Mis productos relacionados no aparecen en el front office.**

-   **R:** Primero, asegúrese de que el módulo esté habilitado y configurado. Verifique que haya *asignado* el bloque de productos relacionados a los productos o categorías específicos que está viendo. Además, verifique que la "Ubicación de visualización (Hook)" que seleccionó sea realmente renderizada por su tema en la página del producto. Finalmente, borre la caché de PrestaShop (Parámetros Avanzados > Rendimiento > Borrar Caché).

**P2: Los productos relacionados se ven extraños o no encajan con el diseño de mi tema.**

-   **R:** Esto suele ser un conflicto de estilo con su tema personalizado.
    -   **Solución 1:** Pruebe diferentes opciones de "Tipo de visualización / Plantilla" en la configuración del módulo. Algunas plantillas están diseñadas para temas populares específicos (por ejemplo, `panda-blocksProductsCart.tpl`).
    -   **Solución 2:** Borre la caché de su navegador y la caché de Smarty de PrestaShop (Parámetros Avanzados > Rendimiento).
    -   **Solución 3:** Si el problema persiste, podría requerir ajustes CSS personalizados. Esta es una tarea para un webmaster o desarrollador (consulte la Sección 7.5).

**P3: ¿Puedo tener varios bloques de productos relacionados en la misma página de producto?**

-   **R:** ¡Sí! El módulo está diseñado para esto. Puede crear varios bloques de productos relacionados distintos, cada uno con sus propios productos, tipo de visualización y ubicación asignada (hook). Solo asegúrese de colocarlos en diferentes hooks para evitar superposiciones.

**P4: ¿Cómo traduzco el texto del módulo (por ejemplo, "Productos Relacionados") a otros idiomas?**

-   **R:** Vaya a **Internacional > Traducciones** en su Back Office de PrestaShop. Seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione "Related Products Pro" del menú desplegable del módulo. Luego podrá editar las cadenas de texto para cada idioma.

**P5: El carrusel no funciona o los productos están apilados verticalmente.**

-   **R:** Esto suele indicar un conflicto de JavaScript o una biblioteca JS faltante.
    -   **Solución 1:** Asegúrese de que su tema esté actualizado.
    -   **Solución 2:** Borre la caché de PrestaShop y la caché del navegador.
    -   **Solución 3:** Busque errores en la consola en las herramientas de desarrollo de su navegador (F12). Si ve errores de JavaScript, podría indicar un conflicto con otro módulo o su tema. Esto requeriría que un desarrollador investigue.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una inmersión técnica profunda en el módulo "Related Products Pro" para desarrolladores, webmasters y agencias técnicas.

### 4.1 Resumen de la Arquitectura

El módulo "Related Products Pro" (`ppb`) sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente la clase `Module` para su funcionalidad principal. Se centra en extender la experiencia de la página de producto del front-office inyectando listas de productos personalizadas en varios hooks de visualización. El módulo gestiona su configuración y los datos de productos relacionados directamente dentro del método `getContent()` del archivo `index.php`, que maneja tanto la renderización del formulario como la persistencia de datos. Utiliza un sistema de plantillas personalizado para una visualización flexible en el front-office, incluyendo plantillas específicas para temas populares. Los activos de JavaScript y CSS se cargan condicionalmente para mejorar la interfaz de usuario y proporcionar la funcionalidad de carrusel.

### 4.2 Controladores (`controllers/`)

El módulo no parece utilizar clases dedicadas `ModuleFrontController` o `AdminController`. Toda la renderización del front-office se maneja a través de hooks, y la configuración del back-office se gestiona dentro del método `getContent()` del archivo `index.php` principal.

### 4.3 Clases y Modelos Principales (`classes/`)

El módulo no define clases personalizadas que extiendan `ObjectModel` en un directorio `classes/` dedicado. La persistencia de datos para las configuraciones de productos relacionados probablemente se maneja directamente a través de `Configuration::updateValue()` o tablas de base de datos personalizadas gestionadas dentro del archivo `index.php` principal.

### 4.4 Activos JavaScript (`views/js/`)

-   **`ppb/lib/searchTool/views/js/autocomplete.js`**:
    -   **Alcance:** Back-office.
    -   **Responsabilidad:** Proporciona funcionalidad de autocompletado para los campos de selección de productos dentro de los formularios de configuración del módulo, probablemente para seleccionar manualmente productos específicos a incluir o asignar. Escucha la entrada del usuario en los campos de texto y sugiere productos basándose en coincidencias parciales.
-   **`ppb/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`**:
    -   **Alcance:** Back-office.
    -   **Responsabilidad:** Probablemente parte de una utilidad genérica para gestionar plantillas Smarty dentro de la interfaz de administración. Podría manejar la carga dinámica, el guardado o la vista previa del código de la plantilla, posiblemente utilizado para funciones de creación o modificación de plantillas personalizadas dentro del módulo.
-   **`ppb/lib/src/js/lightslider.js`**:
    -   **Alcance:** Front-office.
    -   **Responsabilidad:** Esta es una biblioteca de terceros para crear carruseles de contenido responsivos. Se enlaza a elementos HTML específicos (probablemente `<ul>` o `<div>` con una clase designada) para transformarlos en un slider. Maneja eventos táctiles/de deslizamiento, navegación, reproducción automática y ajustes responsivos.
-   **`ppb/views/admin/ppb.js`**:
    -   **Alcance:** Back-office.
    -   **Responsabilidad:** Contiene la lógica JavaScript principal para la página de configuración del Back Office del módulo. Esto incluiría oyentes de eventos para envíos de formularios, actualizaciones dinámicas de la configuración basadas en las elecciones del usuario (por ejemplo, mostrar/ocultar opciones de carrusel), llamadas AJAX para guardar datos y, potencialmente, la gestión de la lista de bloques de productos relacionados.
-   **`ppb/views/admin/ppb8.js`**:
    -   **Alcance:** Back-office.
    -   **Responsabilidad:** Similar a `ppb.js`, pero probablemente contiene adaptaciones específicas o funcionalidades adicionales para entornos PrestaShop 8.x, abordando cambios de API o diferencias de UI en versiones más nuevas de PrestaShop.
-   **`ppb/views/js/accessories.js`**:
    -   **Alcance:** Front-office.
    -   **Responsabilidad:** Contiene JavaScript específico del front-office para los bloques de productos relacionados. Esto podría incluir lógica de inicialización para el carrusel `lightslider.js`, manejo de clics en productos o cualquier interacción dinámica dentro de las listas de productos relacionados mostradas.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   **`ppb/css.css`**:
    -   **Alcance:** Tanto Front-office como Back-office.
    -   **Responsabilidad:** Estilos generales de todo el módulo. Podría contener estilos base para los bloques de productos relacionados o elementos comunes utilizados en todo el módulo.
-   **`ppb/lib/searchTool/views/css/autocomplete.css`**:
    -   **Alcance:** Back-office.
    -   **Responsabilidad:** Estilos para los desplegables de autocompletado y los campos de entrada utilizados en la herramienta de selección de productos del administrador.
-   **`ppb/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`**:
    -   **Alcance:** Back-office.
    -   **Responsabilidad:** Estilo para la interfaz de gestión de plantillas Smarty dentro de la configuración del módulo.
-   **`ppb/lib/src/css/lightslider.css`**:
    -   **Alcance:** Front-office.
    -   **Responsabilidad:** Estilo principal para el carrusel `lightslider.js`, definiendo su estructura, flechas de navegación, puntos y comportamiento responsivo. Los desarrolladores pueden anular estos estilos para que coincidan con su tema.
-   **`ppb/views/admin/ppb.css`**:
    -   **Alcance:** Back-office.
    -   **Responsabilidad:** Estilo específico para la página de configuración del módulo en el panel de administración de PrestaShop, asegurando que se integre bien con la interfaz de usuario del back-office de PrestaShop.
-   **`ppb/views/css/ppb-table.css`**:
    -   **Alcance:** Front-office.
    -   **Responsabilidad:** Estilo para las listas de productos relacionados mostradas en formato de tabla, probablemente utilizado para plantillas específicas de "lista de tabla".
-   **`ppb/views/css/ppb.css`**:
    -   **Alcance:** Front-office.
    -   **Responsabilidad:** Estilo principal del front-office para los bloques de productos relacionados, incluyendo diseños de tarjetas de productos, espaciado y apariencia general.
-   **`ppb/views/css/ppbcarousell.css`**:
    -   **Alcance:** Front-office.
    -   **Responsabilidad:** Estilo adicional o específico para la visualización en carrusel de productos relacionados, potencialmente anulando o extendiendo `lightslider.css` para una estética de módulo personalizada.
-   **`ppb/views/css/ppb_custom.css`**:
    -   **Alcance:** Front-office.
    -   **Responsabilidad:** Probablemente destinado a CSS personalizado definido por el usuario o anulaciones específicas del tema para ajustar la apariencia de los bloques de productos relacionados sin modificar los archivos principales del módulo.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

El módulo proporciona un rico conjunto de plantillas, muchas de las cuales están adaptadas para hooks específicos y temas populares de PrestaShop.

-   **`ppb/lib/searchTool/views/scripts.tpl`**:
    -   **Alcance:** Back-office.
    -   **Propósito:** Contiene la inicialización o configuración de JavaScript para la herramienta de búsqueda de autocompletado utilizada en el administrador.
-   **`ppb/lib/smartyTemplatesManager/tpl/example.tpl`**:
    -   **Alcance:** Back-office.
    -   **Propósito:** Una plantilla de ejemplo, probablemente utilizada como referencia o para demostrar las capacidades del gestor de plantillas Smarty.
-   **`ppb/lib/smartyTemplatesManager/views/buttonManager.tpl`**:
    -   **Alcance:** Back-office.
    -   **Propósito:** Renderiza botones o controles para gestionar plantillas dentro de la interfaz de administración.
-   **`ppb/lib/smartyTemplatesManager/views/createTemplateForm.tpl`**:
    -   **Alcance:** Back-office.
    -   **Propósito:** Renderiza el formulario para crear nuevas plantillas de visualización personalizadas para productos relacionados.
-   **`ppb/lib/smartyTemplatesManager/views/editTemplateForm.tpl`**:
    -   **Alcance:** Back-office.
    -   **Propósito:** Renderiza el formulario para editar plantillas de visualización personalizadas existentes.
-   **`ppb/lib/smartyTemplatesManager/views/mainForm.tpl`**:
    -   **Alcance:** Back-office.
    -   **Propósito:** El formulario principal para el gestor de plantillas Smarty, probablemente listando plantillas y proporcionando opciones.
-   **`ppb/lib/smartyTemplatesManager/views/selectInput.tpl`**:
    -   **Alcance:** Back-office.
    -   **Propósito:** Renderiza un campo de selección desplegable, posiblemente utilizado para elegir plantillas u otras opciones.
-   **`ppb/views/templates/admin/tabs.tpl`**:
    -   **Alcance:** Back-office.
    -   **Propósito:** Renderiza la estructura de navegación por pestañas para la página de configuración del módulo, si utiliza varias pestañas para diferentes ajustes.
-   **Plantillas de hook (`views/templates/hook/`)**: Estas plantillas se renderizan en la página de producto del front-office a través de varios hooks de PrestaShop. Muchas son específicas del tema para garantizar una integración óptima.

    -   **`accessories.tpl`**:
        -   **Hook:** Configurable, a menudo `displayProductExtraContent` o `displayProductFooter`.
        -   **Salida:** Una plantilla genérica para mostrar productos relacionados, típicamente en una cuadrícula o carrusel.
    -   **`blocksProductsCart.tpl`**:
        -   **Hook:** Configurable, a menudo `displayProductExtraContent` o `displayProductFooter`.
        -   **Salida:** Un bloque de productos, potencialmente estilizado para una apariencia similar a un carrito o para recomendaciones generales de productos.
    -   **`blocksProductsOrder.tpl`**:
        -   **Hook:** Configurable.
        -   **Salida:** Similar a `blocksProductsCart.tpl`, pero podría estar estilizado para un contexto o diseño diferente.
    -   **`custom-pictures-only.tpl`**:
        -   **Hook:** Configurable.
        -   **Salida:** Una visualización minimalista que muestra solo imágenes de productos, ideal para espacios compactos o navegación visual.
    -   **`panda-blocksProductsCart.tpl`**, **`panda-blocksProductsOrder.tpl`**, **`panda-ProductExtraContent.tpl`**, **`panda-productFooter.tpl`**, **`panda-productTab.tpl`**, **`panda-productTabContent.tpl`**:
        -   **Hook:** Configurable, diseñado para el tema Panda.
        -   **Salida:** Plantillas específicas del tema que garantizan una integración y un estilo perfectos con el lenguaje de diseño del tema Panda. Renderizarán productos relacionados dentro de las áreas especificadas del tema Panda (por ejemplo, contenido extra del producto, pie de página o pestañas dedicadas).
    -   **`ProductExtraContent.tpl`**:
        -   **Hook:** `displayProductExtraContent`.
        -   **Salida:** Renderiza productos relacionados dentro del hook `displayProductExtraContent`, típicamente un área prominente cerca de los detalles principales del producto.
    -   **`productFooter.tpl`**:
        -   **Hook:** `displayProductFooter`.
        -   **Salida:** Renderiza productos relacionados en la parte inferior de la página del producto.
    -   **`productTab.tpl`**:
        -   **Hook:** Configurable, a menudo `displayProductButtons` o `displayProductExtraContent` (para añadir una nueva pestaña).
        -   **Salida:** Renderiza el *encabezado de la pestaña* para una pestaña dedicada de "Productos Relacionados" en la página del producto.
    -   **`productTabContent.tpl`**:
        -   **Hook:** Configurable, a menudo `displayProductContent` o `displayProductExtraContent` (para añadir contenido para una nueva pestaña).
        -   **Salida:** Renderiza el *contenido* para una pestaña dedicada de "Productos Relacionados", que aparece cuando se hace clic en el encabezado `productTab.tpl`.
    -   **`table-list.tpl`**:
        -   **Hook:** Configurable.
        -   **Salida:** Muestra productos relacionados en formato tabular, potencialmente útil para comparar características o para una lista más estructurada.
    -   **`warehouse-blocksProductsCart.tpl`**, **`warehouse-blocksProductsOrder.tpl`**, etc. (todas las plantillas con prefijo `warehouse-`):
        -   **Hook:** Configurable, diseñado para el tema Warehouse.
        -   **Salida:** Plantillas específicas del tema Warehouse, que garantizan una correcta integración de estilo y diseño.
    -   **`zone-blocksProductsCart.tpl`**, **`zone-blocksProductsOrder.tpl`**, etc. (todas las plantillas con prefijo `zone-`):
        -   **Hook:** Configurable, diseñado para el tema Zone.
        -   **Salida:** Plantillas específicas del tema Zone, que garantizan una correcta integración de estilo y diseño.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**: El módulo probablemente almacena sus datos de configuración (definiciones de bloques de productos relacionados, productos asignados, ajustes de visualización) en tablas de base de datos personalizadas creadas durante la instalación, o podría depender en gran medida de `ps_configuration` para ajustes más simples. Dada la complejidad de múltiples listas de productos relacionados, las tablas personalizadas son más probables. Los desarrolladores necesitarían inspeccionar el método `install()` en `ppb/index.php` para las llamadas a `Db::getInstance()->execute()` para identificar la creación de tablas.

    -   **Tablas Probables (Hipótesis basada en la funcionalidad):**
        -   `ps_ppb_blocks`: Almacena la definición principal de cada bloque de productos relacionados (ID, nombre, hook, tipo de visualización, etc.).
        -   `ps_ppb_block_products`: Una tabla de muchos a muchos que vincula los bloques de productos relacionados con los productos que deben mostrar.
        -   `ps_ppb_block_assignments`: Una tabla de muchos a muchos que vincula los bloques de productos relacionados con las páginas de productos en las que deben aparecer.
        -   `ps_ppb_block_categories`: Una tabla para almacenar asignaciones de categorías para la selección o asignación dinámica de productos.
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Se utiliza para cargar activos CSS y JavaScript (por ejemplo, `lightslider.js`, `ppb.css`) condicionalmente solo en páginas de productos o globalmente. |
| `displayRightColumnProduct` | En la columna derecha de la página del producto. | Renderiza bloques de productos relacionados en la barra lateral derecha. |
| `displayLeftColumnProduct` | En la columna izquierda de la página del producto. | Renderiza bloques de productos relacionados en la barra lateral izquierda. |
| `displayProductExtraContent` | Un hook flexible que a menudo se encuentra cerca de la descripción/imagen del producto. | Un hook común y altamente recomendado para inyectar bloques de productos relacionados directamente en el área de contenido principal. |
| `displayProductFooter` | En la parte inferior de la página del producto, antes del pie de página general. | Renderiza bloques de productos relacionados en una sección dedicada al final del contenido de la página del producto. |
| `displayProductButtons` | Cerca del botón "Añadir al carrito" o de las acciones del producto. | Podría usarse para añadir un encabezado de pestaña "Productos Relacionados". |
| `displayProductContent` | Dentro del área de contenido principal del producto. | Podría usarse para renderizar el contenido de una pestaña "Productos Relacionados". |
| `displayFooter` | En el pie de página global de la tienda. | Menos común para productos relacionados, pero posible para recomendaciones muy amplias. |
| `actionProductUpdate` | Después de que un producto se actualiza en el Back Office. | Potencialmente utilizado para borrar la caché o reindexar los datos de productos relacionados si se utilizan listas dinámicas. |
| `actionProductDelete` | Después de que un producto se elimina. | Para limpiar cualquier asignación de productos relacionados que involucre al producto eliminado. |
| `actionCategoryUpdate` | Después de que una categoría se actualiza. | Para reevaluar las listas de productos relacionados que dependen de las selecciones de categoría. |
| `actionCategoryDelete` | Después de que una categoría se elimina. | Para limpiar las asignaciones de productos relacionados que involucren a la categoría eliminada. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, inicie sesión en su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta relacionada con el módulo "Related Products Pro".
