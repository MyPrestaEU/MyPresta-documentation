---
title: "Homefeatured multi slider - Manual para el Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Homefeatured multi slider de MyPresta.eu."
sidebar:
  label: "Homefeatured multi slider - Manual para el Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Homefeatured multi slider en MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/homefeatured-multi-slider.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/sliders-slideshows/homefeatured-multi-slider/)
>
> ---


# Homefeatured multi slider

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) son típicamente requeridas para que una tienda PrestaShop funcione correctamente. Este módulo no tiene requisitos de alojamiento inusuales o específicos más allá de un entorno PrestaShop estándar.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

El módulo "Homefeatured multi slider" ofrece dos áreas principales para la configuración: la página de configuración principal del módulo para ajustes generales y una pantalla de administración dedicada para gestionar tus sliders de productos y categorías.

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla principal donde configurarás el comportamiento general y la apariencia de tu slider de productos multi-destacados. Para acceder a ella, ve a **Módulos > Gestor de Módulos**, busca "Homefeatured multi slider" y haz clic en "Configurar".

#### Pestaña de Ajustes Generales

| Ajuste / Opción | Qué hace este ajuste | Efecto de cambiar este ajuste | Valor recomendado | Escenario / ejemplo para el comerciante |
| --- | --- | --- | --- | --- |
| **Mostrar en Hook** | Determina dónde aparecerá el slider en tu sitio web. | *Cuando se establece en `displayHome` (o un hook de contenido principal similar):* El slider será una característica prominente en tu página de inicio. *Cuando se establece en `displayLeftColumn` o `displayRightColumn`:* El slider aparecerá en las barras laterales, generalmente más pequeño. *Cuando se establece en `displayFooter`:* El slider estará en la parte inferior de tus páginas. | `displayHome` para un slider prominente en la página de inicio. | Quieres que tus productos destacados principales sean lo primero que vean los clientes en tu página de inicio. |
| **Número de productos a mostrar** | Controla cuántos productos son visibles en el slider en un momento dado. | *Cuando se establece en `4`:* Se mostrarán cuatro productos uno al lado del otro (si el espacio lo permite). *Cuando se establece en `1`:* Solo un producto será visible, a menudo con imágenes más grandes. | `4` o `5` para la mayoría de los temas, dependiendo del tamaño de las imágenes de tus productos y el diseño. | Tienes imágenes de productos grandes y quieres mostrar menos artículos a la vez para un mejor detalle, o tienes imágenes pequeñas y quieres mostrar más. |
| **Velocidad del Slider (ms)** | Establece la velocidad a la que el slider realiza las transiciones entre productos o diapositivas. Medido en milisegundos (1000ms = 1 segundo). | *Cuando se establece en `500`:* Las transiciones son muy rápidas. *Cuando se establece en `5000`:* Las transiciones son lentas, dando a los clientes más tiempo para ver cada producto. | `3000` (3 segundos) a `5000` (5 segundos) para una experiencia de visualización cómoda. | Quieres una visualización dinámica y rápida de productos, o una experiencia de navegación más relajada y contemplativa. |
| **Reproducción Automática del Slider** | Determina si el slider rota automáticamente los productos sin interacción del usuario. | *Cuando está habilitado (SÍ):* El slider se moverá automáticamente al siguiente producto después de la "Velocidad del Slider" establecida. *Cuando está deshabilitado (NO):* El slider solo cambiará de diapositivas cuando el cliente haga clic en las flechas de navegación. | `SÍ` para mantener el contenido dinámico y atractivo. | Quieres asegurar que todos los productos destacados tengan visibilidad incluso si los clientes no hacen clic activamente. |
| **Mostrar Flechas de Navegación** | Controla la visibilidad de las flechas "siguiente" y "anterior" en el slider. | *Cuando está habilitado (SÍ):* Las flechas aparecen a los lados del slider, permitiendo la navegación manual. *Cuando está deshabilitado (NO):* Los clientes deben depender de la reproducción automática u otros métodos de navegación (si están disponibles). | `SÍ` para un mejor control del usuario y accesibilidad. | Quieres que los clientes puedan navegar fácilmente por los productos a su propio ritmo. |
| **Mostrar Puntos de Paginación** | Controla la visibilidad de pequeños puntos o indicadores, generalmente en la parte inferior del slider, que representan cada diapositiva. | *Cuando está habilitado (SÍ):* Aparecen puntos, mostrando la posición actual de la diapositiva y permitiendo saltar directamente a diapositivas específicas. *Cuando está deshabilitado (NO):* Los puntos están ocultos. | `SÍ` para una mejor orientación del usuario y acceso directo a las diapositivas. | Quieres que los clientes sepan cuántas diapositivas hay y salten directamente a una específica. |
| **Ancho de la Imagen del Producto (px)** | Establece el ancho de las imágenes de los productos dentro del slider. | *Cuando se establece en `200`:* Las imágenes tendrán 200 píxeles de ancho. *Cuando se establece en `300`:* Las imágenes tendrán 300 píxeles de ancho. Esto afecta el tamaño general y el diseño del slider. | `250` a `350` píxeles, dependiendo del diseño de tu tema y del "Número de productos a mostrar". | Tus imágenes de productos son de alta resolución y quieres que aparezcan más grandes, o las necesitas más pequeñas para que quepan más productos. |
| **Altura de la Imagen del Producto (px)** | Establece la altura de las imágenes de los productos dentro del slider. | *Cuando se establece en `200`:* Las imágenes tendrán 200 píxeles de alto. *Cuando se establece en `300`:* Las imágenes tendrán 300 píxeles de alto. Esto funciona en conjunto con el ancho para mantener la relación de aspecto o recortar. | `250` a `350` píxeles, coincidiendo con el ancho elegido para imágenes cuadradas, o ajustado para retrato/paisaje. | Tienes imágenes de productos con diferentes relaciones de aspecto y quieres estandarizar su altura de visualización. |
| **Color de Fondo** | Te permite establecer un color de fondo personalizado para todo el bloque del slider. | *Cuando se establece en `#FFFFFF` (blanco):* El fondo del slider será blanco. *Cuando se establece en `#F0F0F0` (gris claro):* El fondo será gris claro. | Deja vacío para transparente o usa un color que coincida con tu tema. | Quieres que el slider destaque con un color de fondo distintivo, o que se integre perfectamente con el fondo de tu página. |
| **Color del Texto** | Establece el color para los nombres de los productos y otros textos dentro del slider. | *Cuando se establece en `#000000` (negro):* El texto será negro. *Cuando se establece en `#333333` (gris oscuro):* El texto será gris oscuro. | Un color que proporcione un buen contraste con el color de fondo elegido. | Necesitas asegurar que los nombres de los productos sean fácilmente legibles contra el fondo del slider. |
| **Color del Precio** | Establece el color para los precios de los productos mostrados en el slider. | *Cuando se establece en `#FF0000` (rojo):* Los precios serán rojos, a menudo utilizados para ventas. *Cuando se establece en `#008000` (verde):* Los precios serán verdes. | Un color que haga que los precios destaquen, a menudo el color de acento de tu marca o un color de precio estándar. | Quieres que los precios sean muy visibles y atraigan la atención. |

### 2.2 Pantallas de Administración Dedicadas y Vistas del Controlador

Este módulo incluye una sección dedicada en tu Back Office de PrestaShop para gestionar las categorías de tus productos destacados y asignar productos a ellas.

#### Nombre de la Pantalla y Ubicación del Menú: "Multi Featured Slider"

Puedes encontrar esta sección navegando a:
**Módulos > Gestor de Módulos > Homefeatured multi slider > Configurar**
En la página de configuración, verás una pestaña o un enlace que lleva a la interfaz de gestión de "Multi Featured Slider". En PrestaShop 1.7+, esto podría aparecer como un nuevo elemento de menú bajo "Catálogo" o "Módulos" si el módulo registra su propia pestaña.

Esta pantalla es gestionada por el `AdminprosliderController` (ubicado en `multihomefeatured/controllers/admin/adminproslider.php`).

**Acciones y Ajustes Disponibles:**

Esta pantalla típicamente presenta una lista de tus "categorías de productos destacados" creadas (referidas como "opinion" en el código subyacente, pero que funcionalmente actúan como categorías para tu slider).

- **Tabla de Listado:** Verás una tabla que lista todas las categorías personalizadas que has creado para tus productos destacados. Cada fila probablemente mostrará:

  - **# (ID):** Un identificador único para la categoría.
  - **Nombre de la Categoría:** El nombre que le has dado a este grupo de productos destacados (por ejemplo, "Más Vendidos", "Novedades").
  - **Estado:** Si la categoría está activa (visible en el slider) o inactiva.
  - **Acciones:** Botones para "Editar" (modificar el nombre de la categoría, el estado y asignar productos) o "Eliminar" la categoría.
- **Añadir Nueva Categoría:** Habrá un botón (por ejemplo, "Añadir Nueva Categoría" o "Añadir Nuevo") para crear un nuevo grupo de productos destacados. Al añadir o editar una categoría, típicamente encontrarás:

  - **Nombre de la Categoría:** Un campo de entrada para definir el nombre de tu categoría de productos destacados (por ejemplo, "Ofertas de Temporada", "Favoritos del Cliente").
  - **Interruptor Activo/Inactivo:** Un interruptor para habilitar o deshabilitar la visualización de esta categoría específica en el slider del front-office.
  - **Asignación de Productos:** Esta es la funcionalidad principal. Probablemente verás una barra de búsqueda o una lista de productos disponibles. Puedes buscar productos y añadirlos a esta categoría destacada específica. Los productos generalmente se pueden reordenar dentro de la categoría.

**Efecto de los cambios:**

- **Añadir una Nueva Categoría:** Crea una nueva pestaña o sección en tu slider del front-office. Luego puedes poblarla con productos específicos.
- **Editar una Categoría:**
  - Cambiar el **Nombre de la Categoría** actualiza la etiqueta mostrada a los clientes en el slider.
  - Alternar **Activo/Inactivo** muestra u oculta inmediatamente esa categoría completa y sus productos del slider del front-office.
  - **Añadir/Eliminar Productos:** Actualiza directamente qué productos aparecen en esa categoría específica del slider.
  - **Reordenar Productos:** Cambia la secuencia en la que aparecen los productos dentro del slider de esa categoría.
- **Eliminar una Categoría:** Elimina permanentemente la categoría y todos sus productos asignados del slider. Los productos en sí no se eliminan de tu tienda.

**Flujo de trabajo recomendado para la gestión diaria de la tienda:**

1. **Planifica tus categorías:** Antes de crear, decide los grupos lógicos para tus productos destacados (por ejemplo, "Novedades", "En Oferta", "Más Vendidos", "Selecciones de Temporada").
2. **Crea Categorías:** Usa el botón "Añadir Nuevo" para crear cada categoría, dándole un nombre claro y descriptivo.
3. **Asigna Productos:** Para cada categoría, usa la interfaz de asignación de productos para buscar y añadir los productos relevantes. Asegúrate de guardar tus cambios.
4. **Ordena Productos:** Organiza los productos dentro de cada categoría en el orden en que quieres que aparezcan.
5. **Revisa y Activa:** Una vez satisfecho, asegúrate de que la categoría esté configurada como "Activa".
6. **Verifica el Front-Office:** Siempre verifica los cambios en tu tienda en vivo para asegurarte de que el slider se vea y funcione como se espera.
7. **Actualizaciones Regulares:** Actualiza periódicamente tus categorías destacadas con nuevos productos, artículos de temporada o artículos que quieras promocionar. Elimina los artículos más antiguos o agotados para mantener el slider fresco y relevante.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Página de Configuración del Módulo** | Mostrar en Hook | `displayHome` | Controla dónde aparece el slider (página de inicio, columnas, pie de página). |
|  | Número de productos a mostrar | `4` | Cuántos productos son visibles a la vez en el slider. |
|  | Velocidad del Slider (ms) | `3000` - `5000` | Velocidad de las transiciones automáticas de diapositivas. |
|  | Reproducción Automática del Slider | `SÍ` | El slider rota automáticamente los productos. |
|  | Mostrar Flechas de Navegación | `SÍ` | Muestra flechas para la navegación manual. |
|  | Mostrar Puntos de Paginación | `SÍ` | Muestra puntos para la indicación de diapositivas y acceso directo. |
|  | Ancho de la Imagen del Producto (px) | `250` - `350` | Establece el ancho de las imágenes de los productos en el slider. |
|  | Altura de la Imagen del Producto (px) | `250` - `350` | Establece la altura de las imágenes de los productos en el slider. |
|  | Color de Fondo | Dejar vacío / Coincidente con el tema | Establece el color de fondo del bloque del slider. |
|  | Color del Texto | Coincidente con el tema / `#333333` | Establece el color para los nombres y descripciones de los productos. |
|  | Color del Precio | Coincidente con el tema / Color de acento | Establece el color para los precios de los productos. |
| **Pantalla de Administración "Multi Featured Slider"** | Añadir/Editar Nombre de Categoría | Nombre descriptivo (por ejemplo, "Más Vendidos") | Crea/modifica una pestaña/sección en el slider. |
|  | Estado de la Categoría (Activo/Inactivo) | `Activo` | Muestra u oculta una categoría completa de productos destacados. |
|  | Asignar Productos a la Categoría | N/A | Selecciona qué productos aparecen en una categoría específica del slider. |
|  | Reordenar Productos | N/A | Cambia el orden de visualización de los productos dentro de una categoría. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: Mi slider no aparece en la página de inicio después de la configuración.**

- **R:** Primero, verifica si el módulo está habilitado y configurado para mostrarse en el hook correcto (por ejemplo, `displayHome`) en la página de configuración principal del módulo. Segundo, asegúrate de haber creado al menos una categoría de "Multi Featured Slider" y de haberle asignado productos, y que la categoría esté configurada como "Activa" en la pantalla de administración dedicada. Finalmente, borra la caché de PrestaShop (**Parámetros Avanzados > Rendimiento > Borrar caché**).

**P2: El slider se ve roto o desalineado en mi tienda.**

- **R:** Esto a menudo es un conflicto de CSS con tu tema.
  1. **Verifica las Dimensiones de la Imagen:** Ve a la página de configuración del módulo y verifica los ajustes de "Ancho de la Imagen del Producto" y "Altura de la Imagen del Producto". Asegúrate de que sean apropiados para tu tema y el número de productos que deseas mostrar.
  2. **Sobreescrituras del Tema:** Tu tema podría tener estilos conflictivos. Intenta cambiar temporalmente al tema predeterminado de PrestaShop para ver si el problema persiste. Si se resuelve, es probable que el CSS de tu tema esté sobrescribiendo los estilos del módulo. Es posible que necesites un desarrollador web para crear una sobrescritura CSS personalizada en el archivo `custom.css` de tu tema.
  3. **Borrar Caché:** Siempre borra la caché de tu navegador y la caché de Smarty de PrestaShop después de realizar cambios relacionados con el diseño.

**P3: ¿Cómo cambio el orden de los productos dentro de una categoría de slider?**

- **R:** Ve a la pantalla de administración dedicada "Multi Featured Slider". Edita la categoría específica que deseas reordenar. Dentro de la interfaz de asignación de productos, deberías poder arrastrar y soltar productos para cambiar su orden, o podría haber flechas de arriba/abajo junto a cada producto. Recuerda guardar tus cambios.

**P4: ¿Puedo traducir los nombres de las categorías a diferentes idiomas?**

- **R:** Sí, los módulos de PrestaShop suelen admitir la entrada multilingüe para campos como los nombres de las categorías. Cuando estés editando un nombre de categoría en la pantalla de administración "Multi Featured Slider", busca un selector de idioma (normalmente un icono de bandera) junto al campo de entrada. Haz clic en él para introducir el nombre para cada idioma instalado.

**P5: El slider es demasiado rápido/lento, o la reproducción automática no funciona.**

- **R:** Ajusta el ajuste "Velocidad del Slider (ms)" en la página de configuración principal del módulo. Un número más alto significa una transición más lenta. Asegúrate de que "Reproducción Automática del Slider" esté configurado en `SÍ` si quieres que rote automáticamente. Recuerda guardar y borrar tu caché.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una visión técnica detallada del módulo "Homefeatured multi slider" para desarrolladores y webmasters.

### 4.1 Visión General de la Arquitectura

El módulo `Homefeatured multi slider` (nombre interno `multihomefeatured`) sigue una arquitectura de módulo estándar de PrestaShop, aprovechando el patrón MVC. Consiste principalmente en:

- Un archivo de módulo principal (`ajax_multihomefeatured.php`) que maneja la instalación, desinstalación y el formulario de configuración principal (`getContent()`).
- Un controlador frontal (`default.php`) para posibles interacciones AJAX o lógica de renderizado específica del front-office.
- Un controlador de administración (`AdminprosliderController.php`) para gestionar las "categorías de productos destacados" personalizadas (referidas como `opinion` en el contexto de la base de datos, pero que funcionalmente actúan como categorías).
- Plantillas Smarty para renderizar tanto la configuración del back-office como los elementos del slider del front-office.
- JavaScript para la funcionalidad del slider y CSS para el estilo.

El módulo no parece utilizar clases `ObjectModel` personalizadas según el inventario proporcionado, lo que sugiere que podría almacenar sus asignaciones de categorías y productos personalizados directamente en `ps_configuration` o en una tabla personalizada gestionada por el `AdminprosliderController`.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

- `multihomefeatured/controllers/front/default.php`
  - **Nombre de la clase y clase padre**: `MultihomefeaturedDefaultModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad**: Este controlador se utiliza probablemente para manejar solicitudes específicas del front-office, potencialmente para llamadas AJAX relacionadas con el contenido del slider, o para renderizar una página independiente si el módulo ofreciera una. Dada la función principal del módulo como slider, podría manejar la carga dinámica de contenido o la recuperación de datos de productos específicos para el slider.

#### Controladores de Administración del Back-Office

- `multihomefeatured/controllers/admin/adminproslider.php`
  - **Nombre de la pestaña y entidad gestionada**: Este controlador gestiona las categorías personalizadas de "Multi Featured Slider" y sus productos asociados. Probablemente aparece como una subpestaña o una entrada dedicada dentro del menú del Back Office de PrestaShop, a menudo bajo "Catálogo" o "Módulos". La entidad gestionada es conceptualmente una "categoría de productos destacados", a la que el módulo se refiere internamente como `opinion` en sus interacciones con la base de datos.
  - **Responsabilidad**: Este controlador proporciona la interfaz CRUD (Crear, Leer, Actualizar, Eliminar) para estas categorías personalizadas. Maneja:
    - Listado de categorías existentes.
    - Visualización de formularios para añadir nuevas categorías.
    - Visualización de formularios para editar categorías existentes (incluyendo la asignación y reordenación de productos).
    - Procesamiento de envíos de formularios para la creación/actualización de categorías.
    - Manejo de la eliminación de categorías.
    - Gestión de la asociación entre categorías y productos específicos de PrestaShop.

### 4.3 Clases y Modelos Principales (`classes/`)

Según el inventario proporcionado, no hay clases PHP personalizadas explícitamente listadas en el directorio `classes/`. Esto sugiere que:

1. El módulo podría ser más antiguo y manipular directamente las tablas de la base de datos sin un `ObjectModel` dedicado.
2. El `AdminprosliderController` podría manejar directamente las interacciones con la base de datos para su entidad `opinion`.
3. El archivo principal del módulo (`ajax_multihomefeatured.php`) podría contener toda la lógica necesaria para la configuración y el manejo básico de datos.

Si se almacenan datos personalizados (como las "categorías de productos destacados" y sus asignaciones de productos), es en `ps_configuration` (para pares clave-valor simples) o en una tabla de base de datos personalizada que es gestionada directamente por el `AdminprosliderController` sin una definición formal de `ObjectModel` en `classes/`.

### 4.4 Activos JavaScript (`views/js/`)

- `multihomefeatured/js/jquery.catslider.16.js`
  - **Alcance**: Front-office.
  - **Descripción**: Probablemente una versión de un plugin jQuery de "category slider" o "content slider", específicamente adaptado o destinado para PrestaShop 1.6.x. Manejaría la animación central del slider, la navegación y la capacidad de respuesta.
- `multihomefeatured/js/jquery.catslider.js`
  - **Alcance**: Front-office.
  - **Descripción**: Similar al anterior, potencialmente una versión más genérica o para otras versiones de PrestaShop. Este script inicializaría el slider, gestionaría las transiciones, la reproducción automática y la interacción del usuario (clics, deslizamientos).
- `multihomefeatured/js/jscolor/jscolor.js`
  - **Alcance**: Back-office.
  - **Descripción**: Esta es una biblioteca JavaScript para un selector de color. Se utiliza en el formulario de configuración del back-office del módulo para proporcionar una interfaz fácil de usar para seleccionar colores (por ejemplo, para el fondo, el texto, los colores de los precios). Se vincula a campos de entrada específicos para mostrar el selector de color.
- `multihomefeatured/js/modernizr.custom.63321.js`
  - **Alcance**: Front-office.
  - **Descripción**: Modernizr es una biblioteca JavaScript que detecta características de HTML5 y CSS3 en el navegador del usuario. A menudo se utiliza para proporcionar detección de características y mecanismos de respaldo, asegurando que el slider funcione correctamente en diferentes navegadores, especialmente los más antiguos que podrían carecer de ciertas capacidades de transición o animación CSS3.
- `multihomefeatured/js/script.js`
  - **Alcance**: Front-office y/o Back-office.
  - **Descripción**: Este es probablemente el archivo JavaScript personalizado principal para el módulo. Contendría:
    - Lógica de inicialización para el plugin `jquery.catslider`, pasando opciones de configuración de los ajustes del módulo.
    - Escuchadores de eventos para flechas de navegación, puntos de paginación o interacciones personalizadas.
    - Potencialmente llamadas AJAX al controlador frontal `default.php` para la carga dinámica de contenido.
    - Cualquier manipulación específica del DOM o mejoras de la interfaz de usuario relacionadas con el slider.
    - En el back-office, podría contener scripts para la búsqueda y asignación de productos dentro de los formularios del `AdminprosliderController`.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `multihomefeatured/css/style.css`
  - **Alcance**: Front-office.
  - **Descripción**: Esta es la hoja de estilo principal para el slider del front-office. Define la apariencia visual del contenedor del slider, los elementos del producto, las flechas de navegación, los puntos de paginación, los títulos de los productos, los precios y cualquier otro elemento mostrado dentro del slider.
  - **Selectores de clase CSS clave**: Los desarrolladores pueden esperar clases como `.multihomefeatured-slider`, `.slider-item`, `.product-image`, `.product-title`, `.product-price`, `.slider-nav-arrow`, `.slider-pagination`, etc., que pueden ser sobrescritas en el archivo `custom.css` de un tema personalizado o mediante el mecanismo de sobrescritura de temas de PrestaShop.
- `multihomefeatured/js/css/ui-lightness/jquery-ui-1.10.2.custom.css`
  - **Alcance**: Back-office.
  - **Descripción**: Esta hoja de estilo forma parte de la biblioteca jQuery UI, específicamente el tema "UI-lightness". Es probable que se utilice en el back-office para estilizar elementos como selectores de fecha, diálogos u otros componentes interactivos que puedan formar parte de los formularios del `AdminprosliderController` (por ejemplo, para el autocompletado de búsqueda de productos, si se implementa usando jQuery UI).

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de Hook (`views/templates/hook/`)**:
  - `multihomefeatured/header.tpl`
    - **Hook**: Probablemente `displayHeader` o `actionFrontControllerSetMedia`.
    - **Salida**: Incluye archivos CSS y JavaScript específicos del módulo (`jquery.catslider.js`, `modernizr.custom.63321.js`, `style.css`, `script.js`) en la sección `<head>` del front-office, asegurando que se carguen antes de que se renderice el slider.
  - `multihomefeatured/home.tpl`
    - **Hook**: Configurable (por ejemplo, `displayHome`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`).
    - **Salida**: Esta es la plantilla principal para la visualización del slider en el front-office. Contiene la estructura HTML para todo el slider multicategoría, incluyendo las pestañas para diferentes categorías y el contenedor para las diapositivas de productos. Itera a través de las categorías y productos configurados para construir el slider.
  - `multihomefeatured/homeTab.tpl`
    - **Hook**: Renderizado internamente por `home.tpl`.
    - **Salida**: Esta plantilla probablemente renderiza una sola pestaña o elemento de navegación para una de las categorías de productos destacados (por ejemplo, "Más Vendidos", "Novedades"). Es parte de la navegación para cambiar entre diferentes sliders de productos.
  - `multihomefeatured/homeTabContents.tpl`
    - **Hook**: Renderizado internamente por `home.tpl`.
    - **Salida**: Esta plantilla renderiza la lista de productos real para una sola categoría de productos destacados. Contiene el bucle que muestra imágenes de productos individuales, nombres, precios y, potencialmente, botones de "Añadir al carrito", todo envuelto en la estructura requerida por el plugin `jquery.catslider`.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:

  - El módulo no define explícitamente clases `ObjectModel` personalizadas, pero el `AdminprosliderController` gestiona una entidad referida como `opinion`. Esto sugiere fuertemente que el módulo crea al menos una tabla personalizada, probablemente llamada `ps_multihomefeatured_opinion` (o similar, siguiendo la convención de prefijo `ps_` de PrestaShop) para almacenar:
    - `id_multihomefeatured_opinion` (Clave Primaria)
    - `name` (para el nombre de la categoría, potencialmente multilingüe)
    - `active` (booleano para el estado de la categoría)
    - Otros campos relacionados con la configuración de la categoría.
  - Además, habría una tabla de enlace, por ejemplo, `ps_multihomefeatured_opinion_product`, para almacenar la relación muchos a muchos entre estas categorías y las entradas de `ps_product`, incluyendo un campo `position` para el orden.
  - Los ajustes de configuración del módulo (como la velocidad del slider, las dimensiones de la imagen, los colores) se almacenan típicamente en la tabla `ps_configuration` con claves prefijadas por el nombre del módulo (por ejemplo, `MULTIHOMEFEATURED_SLIDER_SPEED`).
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Inyecta los archivos CSS y JavaScript del módulo para la funcionalidad del front-office. |
| `displayHome` | Área de contenido principal de la página de inicio. | Renderiza el slider principal de productos multicategoría en la página de inicio. |
| `displayLeftColumn` | Barra lateral izquierda de las páginas del front-office. | Renderiza una versión más pequeña del slider en la columna izquierda. |
| `displayRightColumn` | Barra lateral derecha de las páginas del front-office. | Renderiza una versión más pequeña del slider en la columna derecha. |
| `displayFooter` | Sección inferior de cada página del front-office. | Renderiza el slider en el área del pie de página. |
| `displayProductExtraContent` (o hook similar de página de producto) | En la página de producto, debajo de los detalles del producto. | Potencialmente utilizado para mostrar productos relacionados en un slider en las páginas de producto. |
| `actionFrontControllerSetMedia` | Antes de que un controlador frontal renderice su salida. | Una forma más robusta de registrar activos (CSS/JS) para páginas específicas o globalmente. |
| `actionModuleInstall` | Durante la instalación del módulo. | Crea tablas de base de datos, establece valores de configuración predeterminados, registra hooks. |
| `actionModuleUninstall` | Durante la desinstalación del módulo. | Limpia tablas de base de datos, elimina valores de configuración, anula el registro de hooks. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Homefeatured multi slider", consulta tu cuenta de cliente en MyPresta.eu. Puedes descargar las versiones más recientes del módulo desde tu historial de pedidos. Para asistencia técnica o consultas específicas, ponte en contacto directamente con el soporte de MyPresta.eu a través de tu cuenta de cliente.
