---
title: "Shortcodes - Manual para el Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Shortcodes de PrestaShop por MyPresta.eu."
sidebar:
  label: "Shortcodes"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Shortcodes en MyPresta.eu](https://mypresta.eu/modules/front-office-features/shortcodes.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/shortcodes/)
>
> ---


# Shortcodes

## 1. Requisitos y compatibilidad
- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para una instalación de PrestaShop y son suficientes para este módulo.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)
Después de instalar el módulo, navegue a **Módulos > Gestor de módulos** y busque "Shortcodes". Haga clic en el botón "Configurar" para acceder a sus ajustes.

La página de configuración del módulo Shortcodes es sencilla y se centra en un único ajuste crucial:

#### Desactivar todos los shortcodes
-   **Qué hace este ajuste:** Este es un interruptor maestro que controla si el módulo procesa y reemplaza los shortcodes en todo su sitio web.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (establecido en "Sí"):* El módulo escaneará activamente su contenido y archivos de tema en busca de shortcodes reconocidos (por ejemplo, `[products]`, `[categories]`, `[html]`) y los reemplazará con el contenido dinámico correspondiente. Este es el modo de operación previsto para el módulo.
    -   *Cuando está deshabilitado (establecido en "No"):* El módulo dejará de procesar todos los shortcodes. Cualquier shortcode que haya colocado en su contenido o archivos de tema simplemente aparecerá como texto sin formato (por ejemplo, `[products]` será visible como `[products]` para sus clientes) y no será reemplazado por contenido dinámico.
-   **Valor recomendado:** **Sí**
-   **Escenario / ejemplo del comerciante:**
    -   Lo establecería en "Sí" para activar la funcionalidad de shortcode y mostrar su contenido dinámico.
    -   Podría establecerlo temporalmente en "No" si está depurando un problema, realizando mantenimiento o si desea deshabilitar todo el contenido dinámico generado por los shortcodes en su tienda sin desinstalar el módulo. Recuerde guardar sus cambios después de alternar este ajuste.

:::tip
Después de cambiar cualquier configuración, haga clic siempre en el botón "Guardar" para aplicar sus modificaciones.
:::

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|---|
| Página de configuración del módulo | Desactivar todos los shortcodes | Sí | Controla si el módulo procesa y reemplaza los shortcodes con contenido dinámico. Establezca en "Sí" para activar, "No" para deshabilitar. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P1: Mis shortcodes aparecen como texto sin formato (por ejemplo, `[products]`) en lugar de contenido dinámico. ¿Qué está mal?**
**R1:**
1.  **Verificar el estado del módulo:** Vaya a **Módulos > Gestor de módulos** y asegúrese de que el módulo "Shortcodes" esté instalado y habilitado.
2.  **Verificar la configuración del módulo:** Vaya a la página de configuración del módulo y asegúrese de que "Desactivar todos los shortcodes" esté configurado en **"Sí"**.
3.  **Borrar caché:** A veces, la caché de PrestaShop puede evitar que los cambios aparezcan inmediatamente. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).
4.  **Sintaxis correcta del shortcode:** Verifique que haya escrito el shortcode exactamente como se requiere, incluidos los corchetes `[]` y cualquier parámetro (por ejemplo, `[products type="new"]`). Cualquier error tipográfico evitará que se procese.

**P2: El contenido dinámico (por ejemplo, el carrusel de productos) no tiene el estilo correcto o se ve roto en mi tema.**
**R2:**
Esto generalmente indica un conflicto de CSS o una falta de estilo específico de su tema.
1.  **Compatibilidad del tema:** Si bien el módulo proporciona un estilo básico, los temas personalizados pueden anular o carecer de estilos para ciertos elementos.
2.  **Asistencia del desarrollador:** Es posible que necesite un desarrollador web para inspeccionar la página utilizando las herramientas de desarrollo del navegador (F12) para identificar conflictos de CSS y agregar reglas CSS personalizadas a su tema para garantizar que la salida del shortcode se integre visualmente. El archivo CSS del módulo (`cmsproductspro.css`) puede ser un punto de partida como referencia.

**P3: ¿Puedo usar shortcodes en tiendas multiidioma?**
**R3:** Sí, los shortcodes en sí mismos son independientes del idioma. El contenido que generan (por ejemplo, nombres de productos, descripciones) se mostrará automáticamente en el idioma seleccionado por el cliente, siempre que sus productos y categorías tengan traducciones para ese idioma. Al colocar shortcodes en páginas CMS o descripciones de productos, asegúrese de editar el contenido para el idioma correcto en el back office.

**P4: He agregado un shortcode a una nueva página CMS, pero no aparece en el front office.**
**R4:**
1.  **Estado de la página:** Asegúrese de que su página CMS esté habilitada y visible en su menú de navegación o vinculada desde otra página.
2.  **Caché:** Borre la caché de su PrestaShop (**Parámetros avanzados > Rendimiento**).
3.  **Ubicación del shortcode:** Verifique que el shortcode esté colocado en un área de contenido que realmente sea renderizada por su tema para esa página CMS. Algunos temas pueden tener bloques de contenido específicos.

**P5: ¿Qué shortcodes están disponibles y qué parámetros puedo usar?**
**R5:** La documentación del módulo (esta guía) o la página de configuración del módulo (si los enumera) deben detallar los shortcodes disponibles. Los shortcodes comunes incluyen:
-   `[products]` (para varias listas de productos como nuevos, más vendidos, IDs específicos)
-   `[categories]` (para mostrar listas de categorías)
-   `[html]` (para incrustar HTML personalizado)
-   `[imageManufacturer]` (para mostrar imágenes de fabricantes)
Deberá consultar la implementación específica del módulo para conocer los parámetros exactos (por ejemplo, `limit`, `carousel`, `id`, `type`).

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica para desarrolladores y webmasters que buscan comprender, depurar o extender el módulo Shortcodes.

### 4.1 Descripción general de la arquitectura
El módulo Shortcodes (`cmsproductspro`) funciona principalmente como un filtro de contenido. Se engancha en el proceso de renderizado de salida de PrestaShop para interceptar el contenido HTML antes de que se envíe al navegador. Luego utiliza expresiones regulares para encontrar y reemplazar patrones de shortcode predefinidos con contenido HTML generado dinámicamente. La configuración del módulo es mínima, centrándose en un interruptor global de habilitar/deshabilitar. La lógica de generación de contenido está encapsulada dentro de la clase principal del módulo, aprovechando las funcionalidades principales de PrestaShop para la recuperación de datos (productos, categorías, fabricantes).

### 4.2 Controladores (`controllers/`)
Este módulo **no** contiene ningún controlador de administración de Front-Office o Back-Office personalizado. Toda la lógica de configuración y procesamiento de contenido se maneja dentro del archivo principal del módulo (`cmsproductspro.php`).

### 4.3 Clases y modelos principales (`classes/`)
Este módulo **no** define ninguna clase personalizada u `ObjectModel` en un directorio `classes/`. Toda la lógica principal reside dentro del archivo `cmsproductspro.php`.

### 4.4 Activos de JavaScript (`views/js/`)
Este módulo **no** contiene ningún archivo JavaScript personalizado. Cualquier comportamiento dinámico (como carruseles) normalmente dependería de las bibliotecas JavaScript existentes de PrestaShop o del tema (por ejemplo, Owl Carousel, Slick Carousel) si la salida del shortcode incluye dichos componentes.

### 4.5 Hojas de estilo CSS (`views/css/`)
-   **`cmsproductspro/cmsproductspro.css`**
    *   **Alcance:** Estilo del front-office para el cliente.
    *   **Principales componentes de la interfaz de usuario y contenedores que estiliza:** Esta hoja de estilo proporciona un estilo básico para la salida HTML generada por los shortcodes. Esto incluye:
        *   Cuadrículas y carruseles de productos (por ejemplo, `.cmsproductspro-products-grid`, `.cmsproductspro-carousel`).
        *   Elementos de productos individuales (por ejemplo, `.cmsproductspro-product-item`, `.cmsproductspro-product-image`, `.cmsproductspro-product-name`, `.cmsproductspro-product-price`).
        *   Listas de categorías (por ejemplo, `.cmsproductspro-categories-list`, `.cmsproductspro-category-item`).
        *   Imágenes de fabricantes (por ejemplo, `.cmsproductspro-manufacturer-image`).
        *   Diseño general y capacidad de respuesta para estos elementos.
    *   **Selectores de clase CSS clave que los desarrolladores pueden anular:** Los desarrolladores pueden apuntar a clases como `.cmsproductspro-products-grid`, `.cmsproductspro-product-item`, `.cmsproductspro-product-name`, `.cmsproductspro-product-price`, `.cmsproductspro-categories-list`, `.cmsproductspro-category-item`, `.cmsproductspro-manufacturer-image` para personalizar la apariencia del contenido generado por el shortcode dentro de su tema.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)
El módulo utiliza varias plantillas Smarty para renderizar el contenido dinámico de varios shortcodes. Estas plantillas se encuentran en `views/templates/`.

-   **Plantillas de hook (`views/templates/hook/`)**: Este módulo no utiliza explícitamente un subdirectorio `hook/` para sus plantillas. Las plantillas están directamente dentro de `views/templates/` y se renderizan en función del shortcode detectado.

-   **Plantillas de administración (`views/templates/admin/`)**: Este módulo no contiene ninguna plantilla de administración específica más allá del formulario de configuración estándar manejado por `getContent()`.

-   **Plantillas de front-office (`views/templates/front/`)**:
    *   **`cmsproductspro/categories.tpl`**:
        *   **Propósito:** Renderiza una lista de categorías, típicamente utilizada por un shortcode `[categories]`.
        *   **Variables:** Espera variables como `$categories` (un array de objetos de categoría), `$display_subcategories`, `$image`, etc.
        *   **Salida:** Genera HTML para una cuadrícula o lista de categorías, potencialmente con imágenes y enlaces.
    *   **`cmsproductspro/html.tpl`**:
        *   **Propósito:** Renderiza contenido HTML sin procesar, utilizado por un shortcode `[html]`.
        *   **Variables:** Espera una variable `$content` que contenga la cadena HTML a mostrar.
        *   **Salida:** Muestra directamente el contenido HTML proporcionado.
    *   **`cmsproductspro/imageManufacturer.tpl`**:
        *   **Propósito:** Muestra la imagen de un fabricante, utilizada por un shortcode `[imageManufacturer]`.
        *   **Variables:** Espera `$manufacturer` (un objeto con detalles del fabricante, incluida la ruta de la imagen) y potencialmente `$link` para la página del fabricante.
        *   **Salida:** Genera una etiqueta `<img>` para el logotipo del fabricante, a menudo envuelta en un enlace.
    *   **`cmsproductspro/productGallery.tpl`**:
        *   **Propósito:** Renderiza una galería de productos, potencialmente con un diseño o características específicas. Esta podría ser una plantilla de visualización de productos más genérica.
        *   **Variables:** Espera `$products` (un array de objetos de producto) y otras opciones de visualización.
        *   **Salida:** Estructura HTML para una galería de productos.
    *   **`cmsproductspro/products-carousel.tpl`**:
        *   **Propósito:** Renderiza una lista de productos específicamente diseñada para ser utilizada dentro de un componente de carrusel.
        *   **Variables:** Espera `$products` (array de objetos de producto) y potencialmente opciones específicas del carrusel.
        *   **Salida:** Estructura HTML para una lista de productos, a menudo con clases adecuadas para una biblioteca de carrusel JavaScript.
    *   **`cmsproductspro/products.tpl`**:
        *   **Propósito:** Renderiza una lista o cuadrícula general de productos, utilizada por un shortcode `[products]`.
        *   **Variables:** Espera `$products` (array de objetos de producto) y otras opciones de visualización como `$grid_class`, `$item_class`.
        *   **Salida:** Estructura HTML para una cuadrícula o lista de productos.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**: Este módulo **no** crea ninguna tabla de base de datos personalizada. Su configuración se almacena en la tabla `ps_configuration` utilizando claves como `CMSPRODUCTSPRO_HIDE` (para el ajuste "Desactivar todos los shortcodes").

-   **Tabla de hooks registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
|---|---|---|
| `actionOutputHTMLBefore` | Se ejecuta justo antes de que la salida HTML final se envíe al navegador. | Este es el hook principal donde el módulo intercepta todo el contenido de la página, busca shortcodes y realiza reemplazos. |
| `displayHeader` | Se ejecuta en la sección `<head>` del HTML. | Se utiliza para incluir los archivos CSS necesarios (`cmsproductspro.css`) para el contenido generado por el shortcode. |
| `actionAjaxDieProductControllerdisplayAjaxQuickviewBefore` | Se ejecuta antes del método `displayAjaxQuickview` en `ProductController` (para modales de vista rápida). | Este hook asegura que los shortcodes también se procesen y reemplacen dentro del contenido cargado a través de AJAX para las vistas rápidas de productos, manteniendo la coherencia. |

## 5. Soporte oficial y actualizaciones
Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Shortcodes", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.
