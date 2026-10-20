---
title: "Prestashop Slider - Manual para el Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Prestashop Slider de MyPresta.eu."
sidebar:
  label: "Prestashop Slider - Manual para el Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Prestashop Slider en MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/prestashop-slider.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/sliders-slideshows/prestashop-slider/)
>
> ---


# Prestashop Slider

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes y generalmente vienen preinstaladas en la mayoría de los entornos de alojamiento web.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Este es el panel de control principal para su Prestashop Slider. Aquí definirá el aspecto, la sensación y el contenido de sus sliders.

#### **Configuración General**

- **Qué hace esta configuración:** Estos ajustes controlan el comportamiento y la apariencia general de su slider.
- **Efecto de cambiar esta configuración:**
  - *Ancho del Slider:* Define qué tan ancho será el slider. Puede ser un valor fijo en píxeles o un porcentaje para la capacidad de respuesta.
  - *Altura del Slider:* Define la altura del slider.
  - *Tipo de Animación:* Selecciona uno de los 40 efectos de transición disponibles entre diapositivas.
  - *Velocidad de Animación:* Controla la rapidez con la que ocurre la transición entre diapositivas.
  - *Intervalo de Diapositivas:* Establece la duración que se muestra cada diapositiva antes de pasar automáticamente a la siguiente.
  - *Flechas de Navegación:* Habilita/deshabilita las flechas izquierda/derecha para la navegación manual de diapositivas.
  - *Puntos/Viñetas de Navegación:* Habilita/deshabilita los pequeños puntos que suelen encontrarse en la parte inferior del slider para la selección directa de diapositivas.
  - *Miniaturas:* Habilita/deshabilita pequeñas imágenes de vista previa de cada diapositiva, a menudo mostradas debajo del slider principal.
  - *Vista Previa de Miniatura:* Si las miniaturas están habilitadas, esta configuración controla si aparece una vista previa más grande al pasar el ratón sobre una miniatura.
  - *Visualización de Subtítulos:* Controla si se muestran y cómo los subtítulos de texto asociados a cada diapositiva.
- **Valor recomendado:**
  - *Ancho del Slider:* `100%` para un slider responsivo de ancho completo, o un valor de píxeles específico como `1140px` para que coincida con el área de contenido principal de su tema.
  - *Altura del Slider:* Empiece con `400px` y ajuste según la relación de aspecto de su imagen y el diseño.
  - *Tipo de Animación:* ¡Experimente! `fade` o `slice` son buenos puntos de partida para un aspecto limpio.
  - *Velocidad de Animación:* `800` (milisegundos) para una transición suave.
  - *Intervalo de Diapositivas:* `5000` (5 segundos) es un buen equilibrio para que los usuarios lean el contenido sin sentirse apurados.
  - *Flechas de Navegación:* `SÍ` para un mejor control del usuario.
  - *Puntos/Viñetas de Navegación:* `SÍ` para una fácil visión general y navegación.
  - *Miniaturas:* `NO` inicialmente, habilite si tiene muchas diapositivas y desea un índice visual.
  - *Vista Previa de Miniatura:* `SÍ` si las miniaturas están habilitadas.
  - *Visualización de Subtítulos:* `SÍ` si planea añadir texto a sus diapositivas.
- **Escenario / ejemplo de comerciante:** Desea un banner de ancho completo en su página de inicio que rote a través de tres nuevas líneas de productos. Establecería el ancho en `100%`, elegiría una animación `fade` y establecería un intervalo de `5 segundos`. Habilitaría las flechas de navegación y los puntos para que los clientes puedan navegar manualmente si lo desean.

#### **Sección de Gestión de Diapositivas**

- **Qué hace esta configuración:** Esta sección le permite añadir, editar y eliminar diapositivas individuales de su slider. Cada diapositiva consta de una imagen y configuraciones asociadas.
- **Efecto de cambiar esta configuración:**
  - *Añadir una nueva diapositiva:* Se añadirá una nueva imagen a la rotación de su slider. Subirá una imagen, definirá su enlace, subtítulo y, potencialmente, una animación única.
  - *Editar una diapositiva existente:* Puede cambiar la imagen, su enlace de destino, el texto del subtítulo o el tipo de animación individual para esa diapositiva específica.
  - *Eliminar una diapositiva:* La diapositiva seleccionada se eliminará de su slider.
  - *Reordenar diapositivas:* Puede arrastrar y soltar diapositivas para cambiar el orden en que aparecen en la rotación.
- **Valor recomendado:** Utilice siempre imágenes de alta calidad y optimizadas que sean consistentes en tamaño y relación de aspecto para una apariencia profesional.
- **Escenario / ejemplo de comerciante:** Está lanzando una nueva colección de verano. Añadiría tres diapositivas: una para vestidos, una para trajes de baño y otra para accesorios. Cada diapositiva presentaría una imagen principal, un subtítulo como "¡Compre Vestidos de Verano Ahora!" y un enlace directo a la página de categoría respectiva. Podría darle a la diapositiva de trajes de baño una animación de "cubo" para una sensación lúdica, mientras que las otras usan "fade".

#### **Selección de Hook**

- **Qué hace esta configuración:** Esto le permite elegir dónde se mostrará el slider en su tienda PrestaShop.
- **Efecto de cambiar esta configuración:** Al seleccionar un hook (por ejemplo, `displayHeader`, `displayLeftColumn`), el módulo inyectará el código del slider en esa área específica de su tema.
- **Valor recomendado:**
  - Para un banner prominente de ancho completo: `displayHeader` o un hook personalizado proporcionado por su tema para banners superiores.
  - Para un slider más pequeño y contextual: `displayLeftColumn` o `displayRightColumn`.
  - Para sliders específicos de productos: `displayProductExtraContent` o `displayProductButtons`.
- **Escenario / ejemplo de comerciante:** Desea que su slider promocional principal aparezca justo debajo del menú principal de su sitio web. Seleccionaría el hook `displayHeader` (o un hook similar específico del tema si está disponible). Si quisiera un slider más pequeño que muestre "productos relacionados" en el lateral, elegiría `displayLeftColumn`.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Ancho del Slider | `100%` / `1140px` | Establece el tamaño horizontal del slider. |
| Configuración del Módulo | Altura del Slider | `400px` | Establece el tamaño vertical del slider. |
| Configuración del Módulo | Tipo de Animación | `fade` / `slice` | Define la transición visual entre diapositivas (40 opciones). |
| Configuración del Módulo | Velocidad de Animación | `800` (ms) | Qué tan rápido ocurre la transición de animación. |
| Configuración del Módulo | Intervalo de Diapositivas | `5000` (ms) | Cuánto tiempo es visible cada diapositiva antes de cambiar. |
| Configuración del Módulo | Flechas de Navegación | `SÍ` | Muestra flechas izquierda/derecha para navegación manual. |
| Configuración del Módulo | Puntos/Viñetas de Navegación | `SÍ` | Muestra puntos/viñetas para selección directa de diapositivas. |
| Configuración del Módulo | Miniaturas | `NO` | Muestra pequeñas imágenes de vista previa de cada diapositiva. |
| Configuración del Módulo | Vista Previa de Miniatura | `SÍ` | Muestra una vista previa más grande al pasar el ratón sobre la miniatura (si está habilitado). |
| Configuración del Módulo | Visualización de Subtítulos | `SÍ` | Controla la visibilidad de los subtítulos de texto en las diapositivas. |
| Configuración del Módulo | Añadir/Editar Diapositiva | N/A | Subir imagen, establecer enlace, subtítulo y animación individual. |
| Configuración del Módulo | Selección de Hook | `displayHeader` | Determina dónde aparece el slider en su tienda. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: Mi slider no aparece después de la configuración. ¿Qué debo hacer?**
R:

1. **Verifique la Selección de Hook:** Vuelva a la configuración del módulo y asegúrese de haber seleccionado al menos un hook (por ejemplo, `displayHeader`).
2. **Borrar Caché:** PrestaShop a menudo almacena contenido en caché. Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).
3. **Verifique Conflictos:** Deshabilite temporalmente otros módulos que puedan estar usando el mismo hook o modificando las mismas áreas de la página (especialmente otros módulos de slider).
4. **Compatibilidad del Tema:** Algunos temas altamente personalizados pueden requerir ajustes menores. Si el problema persiste, contacte al soporte de MyPresta.eu con los detalles de su tema.

**P: Mis imágenes se ven borrosas o estiradas en el slider.**
R: Esto generalmente significa que sus imágenes no tienen las dimensiones o resolución correctas para la configuración de su slider.

1. **Dimensiones Consistentes:** Asegúrese de que todas las imágenes subidas para sus diapositivas tengan el mismo ancho y alto.
2. **Alta Resolución:** Suba imágenes con suficiente resolución. Si su slider tiene `1140px` de ancho, sus imágenes deben tener al menos `1140px` de ancho.
3. **Relación de Aspecto:** Haga coincidir la relación de aspecto de sus imágenes con el ancho y alto configurados del slider. Si su slider es de `1140x400px`, intente usar imágenes con una relación de aspecto similar de 114:40.

**P: ¿Cómo traduzco los subtítulos de mis diapositivas a diferentes idiomas?**
R: El módulo debería ser compatible con el sistema de traducción estándar de PrestaShop.

1. Vaya a **Internacional > Traducciones**.
2. Seleccione "Traducciones de módulos instalados", su tema y el idioma al que desea traducir.
3. Busque el módulo "Prestashop Slider" en la lista. Debería poder editar los subtítulos de cada diapositiva directamente allí. Si no, el módulo podría almacenar los subtítulos directamente en la base de datos, lo que requeriría que edite cada diapositiva para cada idioma en la configuración del módulo.

**P: El slider se ve bien en el escritorio pero está roto en el móvil.**
R:

1. **Verifique la Capacidad de Respuesta:** El módulo está diseñado para ser responsivo. Asegúrese de que su tema sea responsivo.
2. **Conflictos de CSS:** Otro módulo o el CSS de su tema podría estar anulando los estilos responsivos del slider. Use las herramientas de desarrollo de su navegador para inspeccionar el slider en el móvil y buscar reglas CSS conflictivas.
3. **Tamaño de la Imagen:** Las imágenes muy grandes a veces pueden causar problemas en el móvil. Asegúrese de que las imágenes estén optimizadas.

**P: ¿Puedo tener varios sliders en diferentes páginas?**
R: La configuración actual del módulo generalmente gestiona una instancia principal de slider con su conjunto de diapositivas. Si necesita múltiples sliders *distintos* con contenido y configuraciones diferentes en diferentes páginas, es posible que deba duplicar el módulo (si su tema lo permite) o usar una solución de slider más avanzada. Para este módulo, configuraría un slider y elegiría su ubicación a través de hooks.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo Prestashop Slider, destinada a desarrolladores, webmasters y agencias técnicas.

### 4.1 Resumen de la Arquitectura

El módulo `Prestashop Slider` (`pslider`) es un módulo estándar de PrestaShop que aprovecha principalmente la clase `Module`. Gestiona su configuración y datos de diapositivas directamente dentro de la tabla `ps_configuration`. La visualización en el front-office se maneja mediante plantillas Smarty renderizadas a través del sistema de hooks de PrestaShop, inyectando activos JavaScript y CSS para la funcionalidad del slider. El módulo utiliza el plugin jQuery `Skitter` para sus capacidades de animación.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores de administración personalizados para el Front-Office o el Back-Office. Toda la configuración se maneja directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

Este módulo no define clases personalizadas que extiendan `ObjectModel`. Toda la configuración y los datos de las diapositivas se almacenan como arrays serializados dentro de la tabla `ps_configuration`, gestionados directamente por la clase `Configuration`.

### 4.4 Activos JavaScript (`views/js/`)

El módulo se basa en el plugin jQuery Skitter para su funcionalidad de slider.

- `pslider/js/jquery.easing.1.3.js`:
  - **Alcance:** Front-office.
  - **Propósito:** Proporciona funciones de easing avanzadas para animaciones jQuery, mejorando la suavidad visual de las transiciones utilizadas por el plugin Skitter.
- `pslider/js/jquery.skitter.js`:
  - **Alcance:** Front-office.
  - **Propósito:** Este es el plugin principal del slider Skitter. Inicializa el slider, maneja las transiciones de diapositivas, la navegación y la capacidad de respuesta. Lee las opciones de configuración (tipo de animación, velocidad, intervalo, etc.) de los ajustes del módulo y las aplica a la instancia del slider.
- `pslider/js/noconflict.js`:
  - **Alcance:** Front-office.
  - **Propósito:** Asegura que jQuery opere en modo `noConflict()`, evitando conflictos con otras bibliotecas JavaScript (como Prototype.js, que PrestaShop 1.6 y anteriores a veces usaban) que también podrían usar el alias `$`. Esto es crucial para la compatibilidad.

### 4.5 Hojas de Estilo CSS (`views/css/`)

El módulo incluye un único archivo CSS para estilizar el slider Skitter.

- `pslider/css/skitter.styles.css`:
  - **Alcance:** Estilo del cliente del front-office.
  - **Propósito:** Contiene todos los estilos visuales predeterminados para el slider Skitter, incluyendo:
    - Diseño del contenedor del slider (`.box_skitter`).
    - Estilo para los elementos de navegación (flechas, puntos, miniaturas).
    - Apariencia predeterminada de los subtítulos.
    - Ajustes responsivos.
  - **Selectores de clase CSS clave que los desarrolladores pueden anular:**
    - `.box_skitter`: Contenedor principal del slider.
    - `.box_skitter ul`: Lista de diapositivas.
    - `.box_skitter .info_slide`: Contenedor de subtítulos.
    - `.box_skitter .nav_cont`: Contenedor de navegación.
    - `.box_skitter .prev_button`, `.box_skitter .next_button`: Flechas de navegación.
    - `.box_skitter .info_slide_dots`: Puntos de navegación.
    - `.box_skitter .box_thumbs`: Contenedor de miniaturas.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

El módulo utiliza plantillas Smarty para renderizar su contenido de front-office y partes de su configuración de back-office.

- **Plantillas de hook (`views/templates/hook/`)**:

  - `pslider/header.tpl`: Esta plantilla probablemente está destinada a ser enganchada en `displayHeader` o un hook similar en la parte superior de la página. Contiene la estructura HTML principal para el slider y a menudo incluye el código de inicialización JavaScript necesario para el plugin Skitter.
  - `pslider/top.tpl`: Similar a `header.tpl`, esto podría usarse para un hook de nivel superior diferente, potencialmente `displayTop` u otro hook de banner específico del tema. También contendría el HTML y la inicialización JS del slider.
  - `pslider/views/templates/hook/left-column.tpl`: Esta plantilla está diseñada específicamente para su colocación en el hook `displayLeftColumn`. Contendría una instancia más pequeña, potencialmente diferente, del slider o un diseño modificado adecuado para una barra lateral.
- **Plantillas de administración (`views/templates/admin/`)**:

  - `pslider/views/templates/front/form.tpl`: A pesar de estar en `views/templates/front/`, este archivo se utiliza en realidad para el formulario de configuración del módulo en el Back Office. Define la estructura HTML para los campos de configuración (ancho, alto, animación, gestión de diapositivas, etc.) con los que interactúa el comerciante. Esto es renderizado por el método `getContent()` en `ajax_pslider.php`.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:

  - El módulo no crea tablas SQL personalizadas.
  - Todas las configuraciones y los datos de las diapositivas (rutas de imagen, enlaces, subtítulos, tipos de animación individuales) se almacenan como arrays serializados dentro de la tabla `ps_configuration`. Los nombres de las claves seguirían típicamente un patrón como `PSLIDER_WIDTH`, `PSLIDER_SLIDES`, etc.
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Se renderiza en la sección `<head>` de la página del front-office, o en la parte superior del `<body>`. | Inyecta activos CSS y JavaScript, y potencialmente la estructura HTML principal del slider. |
| `displayTop` | Se renderiza en la parte superior del contenido de la página, típicamente encima del área de contenido principal pero debajo de la cabecera. | Muestra el banner principal del slider. |
| `displayLeftColumn` | Se renderiza en la barra lateral izquierda de la página del front-office. | Muestra un slider específico de la barra lateral. |
| `displayRightColumn` | Se renderiza en la barra lateral derecha de la página del front-office. | Muestra un slider específico de la barra lateral. |
| `displayFooter` | Se renderiza en la sección del pie de página de la página del front-office. | Muestra un slider específico del pie de página. |
| `displayProductExtraContent` | Se renderiza en la página del producto, típicamente debajo de la información principal del producto. | Muestra sliders relacionados con el producto (por ejemplo, vistas alternativas, características). |
| `displayProductButtons` | Se renderiza cerca del botón "Añadir al carrito" en la página del producto. | Podría usarse para sliders pequeños y contextuales relacionados con el producto. |
| `actionFrontControllerSetMedia` | Se ejecuta cuando un controlador frontal está configurando sus activos multimedia. | Permite al módulo registrar sus archivos JS y CSS condicionalmente. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo Prestashop Slider, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener.
