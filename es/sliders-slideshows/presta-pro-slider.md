---
title: "Presta Pro Slider - Manual para el Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Presta Pro Slider para PrestaShop de MyPresta.eu."
sidebar:
  label: "Presta Pro Slider - Manual para el Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Presta Pro Slider en MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/presta-pro-slider.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/sliders-slideshows/presta-pro-slider/)
>
> ---


# Presta Pro Slider

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se requieren configuraciones de servidor inusuales.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Presta Pro Slider)

Esta es la pantalla de configuración principal donde gestiona los ajustes generales de su slider y añade/edita diapositivas individuales.

#### Ajustes Generales del Slider

-   **Qué hace este ajuste:** Estos ajustes controlan la apariencia y el comportamiento general de su slider, como sus dimensiones, velocidad de animación y dónde aparece en su sitio.
-   **Efecto de cambiar este ajuste:** Ajustar estos valores impactará directamente en cómo se ve y funciona el slider para sus clientes.

| Ajuste / Opción | Qué hace | Efecto de cambiar | Valor Recomendado | Escenario / Ejemplo para el Comerciante |
| --- | --- | --- | --- | --- |
| **Ancho del Slider (px)** | Establece el ancho total del slider en píxeles. | *Si se establece en 1000:* El slider tendrá 1000 píxeles de ancho. *Si se establece en 500:* El slider tendrá 500 píxeles de ancho. | `100%` (para ancho completo) o un valor de píxel específico como `1170` (común para áreas de contenido). | Desea que su slider ocupe toda el área de contenido de su página de inicio, que tiene 1170px de ancho. Introduciría `1170`. Si desea que sea responsivo y ocupe todo el ancho disponible, use `100%`. |
| **Altura del Slider (px)** | Establece la altura total del slider en píxeles. | *Si se establece en 400:* El slider tendrá 400 píxeles de alto. *Si se establece en 250:* El slider tendrá 250 píxeles de alto. | `350` - `500` (dependiendo del contenido de la imagen). | Tiene imágenes de banner de alta calidad que se ven mejor a una cierta altura. Lo establecería en `450` para asegurarse de que sus imágenes se muestren sin estar demasiado estiradas o aplastadas. |
| **Velocidad de Animación (ms)** | Controla la velocidad de la transición entre diapositivas, en milisegundos. | *Si se establece en 500:* Las diapositivas transicionan rápidamente (0.5 segundos). *Si se establece en 2000:* Las diapositivas transicionan lentamente (2 segundos). | `1000` (1 segundo) | Desea una transición suave y perceptible entre sus diapositivas promocionales, pero no tan lenta como para que los clientes se aburran. Establecerlo en `1000` proporciona un buen equilibrio. |
| **Reproducción Automática** | Determina si el slider avanza automáticamente a la siguiente diapositiva. | *Cuando está habilitado (SÍ):* Las diapositivas cambiarán automáticamente después de un retraso establecido. *Cuando está deshabilitado (NO):* Las diapositivas solo cambiarán cuando un cliente haga clic en las flechas de navegación o los puntos. | `SÍ` | Desea que sus promociones principales se ciclen automáticamente en la página de inicio sin interacción del cliente. |
| **Velocidad de Reproducción Automática (ms)** | Si la Reproducción Automática está habilitada, esto establece el retraso antes de que aparezca la siguiente diapositiva, en milisegundos. | *Si se establece en 5000:* Cada diapositiva se muestra durante 5 segundos. *Si se establece en 3000:* Cada diapositiva se muestra durante 3 segundos. | `5000` (5 segundos) | Tiene mucho texto en sus diapositivas y desea dar a los clientes tiempo suficiente para leerlo antes de que aparezca la siguiente diapositiva. Establecerlo en `7000` (7 segundos) sería apropiado. |
| **Mostrar en Hook** | Selecciona el hook de PrestaShop donde se mostrará el slider. | *Si se establece en `displayHeader`*: El slider aparece en la parte superior de cada página. *Si se establece en `displayLeftColumn`*: El slider aparece en la barra lateral izquierda. | `displayHome` (si está disponible, de lo contrario `displayHeader` o `displayTop`) | Desea que el slider sea una característica prominente en su página de inicio. Seleccionaría `displayHome` o `displayTop`. Si lo desea en las páginas de productos, podría seleccionar `displayProductFooter`. |
| **Color de Fondo** | Establece el color de fondo del contenedor del slider. | *Si se establece en #FFFFFF:* El fondo será blanco. *Si se establece en #000000:* El fondo será negro. | `Dejar vacío` (para transparente) o un color que coincida con su tema. | Su tema tiene un fondo claro y desea que el slider se integre perfectamente. Lo establecería en `#FFFFFF`. |
| **Color del Texto** | Establece el color predeterminado para el texto dentro del slider (títulos, descripciones). | *Si se establece en #000000:* El texto será negro. *Si se establece en #FF0000:* El texto será rojo. | `#333333` (gris oscuro) | Las imágenes de su slider son brillantes y necesita texto oscuro para asegurar la legibilidad. Lo establecería en `#333333`. |

#### Sección de Gestión de Diapositivas

Esta sección le permite añadir, editar y eliminar diapositivas individuales que componen su presentación.

-   **Botón Añadir Nueva Diapositiva:** Haga clic aquí para abrir un formulario para crear una diapositiva completamente nueva.
-   **Lista de Diapositivas Existentes:** Muestra una tabla de todas sus diapositivas actualmente activas, generalmente con opciones para editarlas o eliminarlas.

### 2.2 Pantallas de Administración Dedicadas y Vistas del Controlador

#### AdminprosliderController (Back Office > Módulos > Presta Pro Slider > Configurar > "Añadir Nueva Diapositiva" o "Editar" una diapositiva existente)

Esta pantalla aparece cuando hace clic en "Añadir Nueva Diapositiva" o en el botón "Editar" junto a una diapositiva existente en la configuración principal. Le permite definir el contenido y el comportamiento de cada diapositiva individual.

-   **Nombre de la pantalla y ubicación del menú:** Se accede desde la página de configuración principal del módulo haciendo clic en "Añadir Nueva Diapositiva" o en el icono de edición de una diapositiva existente.
-   **Acciones y ajustes disponibles:** Este formulario le permite introducir todos los detalles de una sola diapositiva.

| Ajuste / Opción | Qué hace | Efecto de cambiar | Valor Recomendado | Escenario / Ejemplo para el Comerciante |
| --- | --- | --- | --- | --- |
| **Título de la Diapositiva (Leyenda)** | El encabezado principal o texto corto que se muestra en la diapositiva. | Este texto aparecerá prominentemente en su diapositiva, generalmente con una fuente más grande. | Manténgalo conciso e impactante. | "¡Rebajas de Verano!" o "Novedades" |
| **Descripción de la Diapositiva** | Texto más largo que proporciona más detalles sobre el contenido de la diapositiva. | Este texto aparecerá debajo del título, ofreciendo más información al cliente. | Proporcione suficientes detalles sin ser abrumador. | "¡Hasta un 50% de descuento en toda la ropa de baño por tiempo limitado!" |
| **Imagen de la Diapositiva** | La imagen de fondo principal para esta diapositiva específica. | Esta imagen será la pieza central visual de su diapositiva. | Imagen de alta calidad, relevante y con buena resolución. | Una imagen atractiva de una modelo vistiendo un nuevo vestido para una promoción de moda. |
| **URL del Enlace** | La dirección web (URL) a la que se dirigirá a los clientes cuando hagan clic en esta diapositiva. | *Si se establece:* Al hacer clic en la diapositiva, el cliente irá a esta URL. *Si está vacío:* La diapositiva no será clicable. | Una URL válida a un producto, categoría o página informativa. | Enlace a su página de categoría "Novedades": `https://sutienda.com/novedades` |
| **Abrir en Nueva Ventana** | Determina si la URL del enlace se abre en una nueva pestaña/ventana del navegador. | *Cuando está habilitado (SÍ):* El enlace se abre en una nueva pestaña, manteniendo su tienda abierta en la pestaña original. *Cuando está deshabilitado (NO):* El enlace se abre en la misma pestaña, navegando fuera de su página actual. | `SÍ` (generalmente recomendado para enlaces externos o promociones) | Está enlazando a una publicación de blog externa o a un perfil de redes sociales. Habilitaría esto para mantener a sus clientes en su tienda PrestaShop. |
| **Activo** | Controla si esta diapositiva es actualmente visible en el slider. | *Cuando está habilitado (SÍ):* La diapositiva formará parte de la presentación. *Cuando está deshabilitado (NO):* La diapositiva estará oculta pero no eliminada, lo que le permite reactivarla más tarde. | `SÍ` para promociones activas. | Tiene una promoción estacional que ha terminado, pero podría volver a ejecutarla el año que viene. La establecería en `NO` en lugar de eliminarla. |
| **Orden / Posición** | Establece el orden de visualización de esta diapositiva en relación con otras. | Las diapositivas con números más bajos aparecen antes en la secuencia. | `1`, `2`, `3`, etc., en el orden deseado. | Desea que su diapositiva de "Rebajas de Verano" aparezca primero, seguida de "Novedades". Establecería "Rebajas de Verano" en `1` y "Novedades" en `2`. |

-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  **Planifique sus promociones:** Decida qué productos, categorías o mensajes desea destacar.
    2.  **Prepare sus imágenes:** Asegúrese de tener imágenes de alta calidad que se ajusten a las dimensiones del slider.
    3.  **Añada nuevas diapositivas:** Utilice el botón "Añadir Nueva Diapositiva" para crear contenido nuevo. Rellene todos los detalles, incluyendo título, descripción, imagen y enlace.
    4.  **Ordene sus diapositivas:** Ajuste el "Orden / Posición" para controlar la secuencia.
    5.  **Active/Desactive:** Utilice el interruptor "Activo" para gestionar la visibilidad sin eliminar contenido.
    6.  **Revise en el front office:** Siempre revise su slider en la tienda en vivo para asegurarse de que se vea y funcione como se espera.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del Módulo** | Ancho del Slider (px) | `100%` o `1170` | Establece el tamaño horizontal del slider. |
| | Altura del Slider (px) | `350` - `500` | Establece el tamaño vertical del slider. |
| | Velocidad de Animación (ms) | `1000` | Controla la velocidad de transición de las diapositivas. |
| | Reproducción Automática | `SÍ` | Avanza las diapositivas automáticamente. |
| | Velocidad de Reproducción Automática (ms) | `5000` | Retraso entre cambios automáticos de diapositivas. |
| | Mostrar en Hook | `displayHome` / `displayHeader` | Dónde aparece el slider en su tienda. |
| | Color de Fondo | `Dejar vacío` / `#FFFFFF` | Color de fondo del área del slider. |
| | Color del Texto | `#333333` | Color de texto predeterminado para títulos/descripciones. |
| **Añadir/Editar Diapositiva** | Título de la Diapositiva (Leyenda) | Conciso e impactante | Encabezado principal de la diapositiva. |
| | Descripción de la Diapositiva | Informativo | Texto detallado de la diapositiva. |
| | Imagen de la Diapositiva | Imagen de alta calidad | Fondo visual de la diapositiva. |
| | URL del Enlace | URL válida | Destino al hacer clic en la diapositiva. |
| | Abrir en Nueva Ventana | `SÍ` | Abre el enlace en una nueva pestaña del navegador. |
| | Activo | `SÍ` | Alterna la visibilidad de la diapositiva. |
| | Orden / Posición | `1, 2, 3...` | Determina la secuencia de las diapositivas. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: Mi slider no aparece en el front office, o aparece en el lugar equivocado.**

-   **R:** Primero, verifique la configuración "Mostrar en Hook" en la configuración del módulo. Asegúrese de haber seleccionado el hook correcto (por ejemplo, `displayHeader`, `displayTop`, `displayHome`). Si su tema tiene nombres de hook personalizados o no soporta explícitamente un hook estándar en esa ubicación, el slider podría no aparecer.
-   **R:** Además, verifique que las diapositivas individuales estén marcadas como "Activas" en sus configuraciones. Si no hay diapositivas activas, no se mostrará nada.
-   **R:** Finalmente, borre la caché de PrestaShop. Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché" en la esquina superior derecha. A veces, los cambios no aparecen hasta que se actualiza la caché.

**P2: Las imágenes de mi slider se ven borrosas o estiradas.**

-   **R:** Esto suele ocurrir si las imágenes que ha subido no coinciden con los ajustes de "Ancho del Slider" y "Altura del Slider", o si tienen baja resolución.
-   **R:** **Solución:** Asegúrese de que sus imágenes sean de alta resolución e idealmente tengan la misma relación de aspecto que las dimensiones configuradas de su slider. Por ejemplo, si su slider tiene 1200px de ancho y 400px de alto, intente subir imágenes que tengan al menos 1200px por 400px. Es posible que necesite redimensionar o recortar sus imágenes antes de subirlas.

**P3: El texto de mis diapositivas es difícil de leer.**

-   **R:** Esto suele ser un problema de contraste entre la "Imagen de la Diapositiva" y el "Color del Texto" que ha elegido.
-   **R:** **Solución:**
    1.  Ajuste el "Color del Texto" en la configuración principal del módulo a un color que contraste bien con sus imágenes (por ejemplo, texto blanco sobre imágenes oscuras, texto negro sobre imágenes claras).
    2.  Considere añadir una superposición sutil a sus imágenes (es posible que necesite un editor gráfico para esto) para oscurecerlas o aclararlas ligeramente, haciendo que el texto resalte más.
    3.  Mantenga el "Título de la Diapositiva" y la "Descripción de la Diapositiva" concisos. Menos texto suele ser más fácil de leer rápidamente.

**P4: ¿Cómo traduzco los títulos y descripciones de las diapositivas a diferentes idiomas?**

-   **R:** Cuando esté editando una diapositiva, debería ver pestañas de selección de idioma junto a los campos "Título de la Diapositiva" y "Descripción de la Diapositiva" (si su tienda PrestaShop tiene varios idiomas habilitados).
-   **R:** **Solución:** Haga clic en el icono de la bandera o en la pestaña del idioma para cada idioma que desee traducir, y luego introduzca el texto correspondiente para ese idioma. Recuerde guardar sus cambios.

**P5: Las animaciones del slider son demasiado rápidas/lentas, o la reproducción automática no funciona.**

-   **R:** Verifique los ajustes de "Velocidad de Animación (ms)", "Reproducción Automática" y "Velocidad de Reproducción Automática (ms)" en la configuración principal del módulo.
-   **R:** **Solución:**
    -   Aumente la "Velocidad de Animación" para transiciones más lentas, disminuya para más rápidas.
    -   Asegúrese de que "Reproducción Automática" esté configurado en `SÍ` si desea que las diapositivas avancen automáticamente.
    -   Ajuste la "Velocidad de Reproducción Automática" para controlar cuánto tiempo se muestra cada diapositiva antes de pasar a la siguiente. Recuerde que estos valores están en milisegundos (1000ms = 1 segundo).

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo Presta Pro Slider sigue una arquitectura de módulo estándar de PrestaShop, aprovechando el patrón MVC cuando es apropiado. Utiliza principalmente un único archivo de módulo principal (`ajax_proslider.php`) para su lógica central y configuración, un controlador administrativo para gestionar las diapositivas y plantillas de front-office para renderizar el slider. Se basa en jQuery y Modernizr para sus animaciones y estilos de front-end. Los datos de las diapositivas se almacenan directamente en la tabla `ps_configuration` de PrestaShop, en lugar de un `ObjectModel` dedicado y una tabla de base de datos personalizada.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**:

    -   `controllers/front/default.php`
        -   **Nombre de la clase y clase padre**: `ProsliderDefaultModuleFrontController` que extiende `ModuleFrontController`.
        -   **Responsabilidad**: Este controlador probablemente está destinado a una ruta predeterminada o una acción específica de front-office, aunque su propósito exacto podría ser mínimo dado que el módulo se engancha principalmente a áreas de plantilla existentes. Manejaría las solicitudes a `sutienda.com/module/proslider/default` y podría usarse para llamadas AJAX o para renderizar una página independiente si el módulo tuviera una. En el contexto de este módulo, podría ser un marcador de posición o usarse para la recuperación de datos específicos si el contenido del slider se cargara dinámicamente.
-   **Controladores de Administración de Back-Office**:

    -   `controllers/admin/adminproslider.php`
        -   **Nombre de la clase y clase padre**: `AdminprosliderController` que extiende `ModuleAdminController`.
        -   **Nombre de la pestaña y entidad gestionada**: Este controlador gestiona las "diapositivas" o "opiniones" (según el dossier, aunque "opinión" parece un error tipográfico y probablemente debería ser "diapositiva" o "proslider_item" si fuera un ObjectModel). Proporciona la interfaz para añadir, editar y eliminar diapositivas individuales. Maneja el envío del formulario para los detalles de la diapositiva (título, descripción, imagen, enlace, etc.) y actualiza la tabla `ps_configuration` o una tabla personalizada si estuviera presente.

### 4.3 Clases y Modelos Principales (`classes/`)

El dossier del módulo indica que no hay clases o modelos personalizados en el directorio `classes/`. Esto sugiere que el módulo almacena sus datos directamente en la tabla `ps_configuration` utilizando arrays serializados o claves de configuración individuales para cada diapositiva, o podría estar utilizando un enfoque más simple y no ORM dentro del `AdminprosliderController` para gestionar los datos. Si estuviera utilizando `ObjectModel`, habría una clase definida aquí (por ejemplo, `ProsliderSlide.php`).

### 4.4 Activos JavaScript (`views/js/`)

-   `proslider/js/jquery.cslider.js`
    -   **Alcance**: Front-office.
    -   **Descripción**: Este es probablemente el plugin principal de jQuery responsable de la funcionalidad del slider animado. Maneja las transiciones de diapositivas, la lógica de reproducción automática, los controles de navegación y la capacidad de respuesta. Los desarrolladores deben consultar este archivo para comprender los tipos de animación del slider y las opciones disponibles.
-   `proslider/js/jscolor/jscolor.js`
    -   **Alcance**: Back-office.
    -   **Descripción**: Una biblioteca JavaScript para un widget de selección de color. Se utiliza en los formularios de configuración del back-office del módulo para permitir a los comerciantes seleccionar fácilmente los colores de fondo y de texto para el slider.
-   `proslider/js/modernizr.custom.28468.js`
    -   **Alcance**: Front-office.
    -   **Descripción**: Modernizr es una biblioteca JavaScript que detecta características de HTML5 y CSS3 en el navegador del usuario. Esta compilación personalizada específica es probablemente utilizada por `jquery.cslider.js` para proporcionar detección de características y potencialmente mecanismos de respaldo para navegadores más antiguos, asegurando animaciones suaves y compatibilidad.
-   `proslider/js/script.js`
    -   **Alcance**: Front-office.
    -   **Descripción**: Este es el archivo JavaScript personalizado principal del módulo. Inicializa el plugin `jquery.cslider.js` con los ajustes específicos configurados en el back office (ancho, alto, velocidad, reproducción automática, etc.). Vincula los oyentes de eventos para la navegación del slider (si se implementan algunos personalizados) y asegura que el slider funcione correctamente dentro del entorno de PrestaShop.
-   `proslider/tinymce16.inc.js`
    -   **Alcance**: Back-office.
    -   **Descripción**: Este archivo es una inclusión para el editor de texto enriquecido TinyMCE, configurado específicamente para PrestaShop 1.6.x. Se utiliza en los formularios del back-office para los campos de "Descripción de la Diapositiva", permitiendo a los comerciantes formatear texto con HTML. Para PrestaShop 1.7.x y 8.x, se podría utilizar la integración nativa de TinyMCE de PrestaShop, o este archivo aún podría cargarse para compatibilidad.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   `proslider/css/style2.css`
    -   **Alcance**: Estilo del cliente de front-office.
    -   **Descripción**: Esta es la hoja de estilo principal para el slider de front-end. Define la apariencia visual del contenedor del slider, las diapositivas individuales, los títulos, las descripciones, las flechas de navegación y los puntos de paginación.
    -   **Selectores de clase CSS clave**: Los desarrolladores pueden inspeccionar este archivo para clases como `.cs-slider`, `.cs-wrapper`, `.cs-bg`, `.cs-caption`, `.cs-description`, `.cs-nav`, `.cs-dots` para anular o extender el estilo en el CSS personalizado de su tema.
-   `proslider/js/css/ui-lightness/jquery-ui-1.10.2.custom.css`
    -   **Alcance**: Estilo del formulario de administración del back-office.
    -   **Descripción**: Esta es una compilación personalizada del framework CSS de jQuery UI, específicamente para el tema "UI-lightness". Es probable que se utilice para estilizar elementos dentro de los formularios de configuración del back-office del módulo, como selectores de fecha (si los hay), botones u otros widgets de UI que puedan formar parte de la interfaz de gestión de diapositivas.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:

    -   `proslider/header.tpl`
        -   **Hook**: Probablemente destinado a `displayHeader` o `displayTop`.
        -   **Salida**: Esta plantilla contendría la estructura HTML principal para el slider, incluyendo los elementos `div` a los que apunta `jquery.cslider.js`, y potencialmente el bucle para renderizar diapositivas individuales basándose en los datos pasados desde el módulo. También podría incluir las inclusiones necesarias de JS y CSS.
    -   `proslider/top.tpl`
        -   **Hook**: Probablemente destinado a `displayTop` o `displayNav`.
        -   **Salida**: Similar a `header.tpl`, esto renderizaría el slider en la sección superior de la tienda, a menudo debajo de la navegación principal.
    -   `proslider/views/templates/hook/left-column.tpl`
        -   **Hook**: `displayLeftColumn` o `displayRightColumn`.
        -   **Salida**: Esta plantilla renderiza una versión potencialmente más pequeña o con un estilo diferente del slider específicamente para las columnas laterales de la tienda.
-   **Plantillas de administración (`views/templates/admin/`)**:

    -   `proslider/views/templates/front/form.tpl`
        -   **Hook**: Esta ruta sugiere que es una plantilla de front-office, pero el contexto de `AdminprosliderController` implica que podría usarse para el *formulario* para añadir/editar diapositivas dentro del administrador. Este es un patrón común donde un módulo podría reutilizar una plantilla de "formulario" tanto para la entrada de datos de front-end (si corresponde) como de back-end.
        -   **Salida**: Esta plantilla definiría la estructura del formulario HTML para añadir o editar una sola diapositiva, incluyendo campos de entrada para título, descripción, carga de imagen, URL, estado activo y posición.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:

    -   El dossier del módulo indica que no hay archivos SQL personalizados. Esto sugiere fuertemente que el módulo almacena su configuración y datos de diapositivas directamente dentro de la tabla `ps_configuration` de PrestaShop. Los datos de cada diapositiva (título, descripción, imagen, enlace, etc.) probablemente se serializarían en una única clave de configuración, o en múltiples claves por diapositiva, por ejemplo, `PROSLIDER_SLIDE_1_TITLE`, `PROSLIDER_SLIDE_1_IMAGE`, etc. Este enfoque es más simple pero menos escalable que usar un `ObjectModel` dedicado.
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Inyectar activos CSS/JS y potencialmente la estructura HTML principal del slider. |
| `displayTop` | Típicamente debajo de la navegación principal, encima del contenido. | Mostrar el slider principal en una posición superior prominente. |
| `displayHome` | En el área de contenido de la página de inicio. | Mostrar el slider como una característica central en la página de inicio. |
| `displayLeftColumn` | En la barra lateral izquierda de las páginas que tienen una. | Mostrar un slider más pequeño y contextual en la columna izquierda. |
| `displayRightColumn` | En la barra lateral derecha de las páginas que tienen una. | Mostrar un slider más pequeño y contextual en la columna derecha. |
| `displayProductFooter` | En la parte inferior de las páginas de productos. | Mostrar un slider relacionado con el producto (por ejemplo, accesorios, artículos relacionados). |
| `displayFooter` | En la sección del pie de página de cada página. | Mostrar un slider para promociones secundarias o contenido de marca. |
| `actionFrontControllerSetMedia` | Antes de que un controlador de front-office renderice su salida, después de que se establezcan los medios. | Registrar archivos CSS y JavaScript específicos del módulo para las páginas de front-office. |
| `actionAdminControllerSetMedia` | Antes de que un controlador de administración renderice su salida, después de que se establezcan los medios. | Registrar archivos CSS y JavaScript específicos del módulo para las páginas de back-office (por ejemplo, para el selector de color o TinyMCE). |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a brindar asistencia y garantizar el buen funcionamiento de su módulo Presta Pro Slider.
