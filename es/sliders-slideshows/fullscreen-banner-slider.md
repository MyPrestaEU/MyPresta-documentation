---
title: "Fullscreen Banner Slider - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Fullscreen Banner Slider para PrestaShop de MyPresta.eu."
sidebar:
  label: "Fullscreen Banner Slider - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Fullscreen Banner Slider en MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/fullscreen-banner-slider.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/sliders-slideshows/fullscreen-banner-slider/)
>
> ---


# Fullscreen Banner Slider

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "Fullscreen Banner Slider" en su Gestor de Módulos. Esto lo llevará a la pantalla de configuración principal donde puede gestionar todos los aspectos de su slider.

La configuración del módulo se gestiona a través del método `getContent()` en el archivo principal del módulo, presentando un formulario de configuración estándar de PrestaShop.

#### **Configuración General**

- **Qué hace esta configuración:** Estos ajustes controlan el comportamiento general y la apariencia de su slider a pantalla completa.
- **Efecto de cambiar esta configuración:** Ajustar estos valores impactará directamente cómo se muestra el slider a sus clientes, su tamaño, velocidad y si está activo.

| Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- |
| **Habilitar Slider a Pantalla Completa** | SÍ | **Propósito:** Activa o desactiva toda la función del slider.   **Efecto:**   *Cuando está habilitado:* El slider a pantalla completa aparecerá a los nuevos visitantes.   *Cuando está deshabilitado:* El slider no se mostrará en su tienda.   **Recomendado:** SÍ, para activar la función. |
| **Ancho del Slider** | 100% | **Propósito:** Define el ancho del slider.   **Efecto:**   *Establecido en 100% (recomendado):* El slider abarcará todo el ancho de la ventana del navegador.   *Establecido en un valor de píxeles fijo (ej., 1200px):* El slider tendrá un ancho fijo, lo que podría dejar espacio vacío en pantallas muy anchas.   **Recomendado:** 100% para una verdadera experiencia a pantalla completa. |
| **Altura del Slider** | 100% | **Propósito:** Define la altura del slider.   **Efecto:**   *Establecido en 100% (recomendado):* El slider abarcará toda la altura de la ventana del navegador.   *Establecido en un valor de píxeles fijo (ej., 800px):* El slider tendrá una altura fija, lo que podría dejar espacio vacío en pantallas muy altas o cortas.   **Recomendado:** 100% para una verdadera experiencia a pantalla completa. |
| **Tipo de Animación** | (Menú desplegable con varias opciones) | **Propósito:** Selecciona el efecto de transición visual entre banners.   **Efecto:** Cada opción proporciona un estilo de animación diferente (ej., fundido, deslizamiento, cubo, etc.). Experimente para encontrar uno que coincida con su marca.   **Recomendado:** Elija una animación que sea suave y no demasiado distractora. "Fundido" o "Deslizamiento" suelen ser buenos puntos de partida. |
| **Velocidad de Animación (ms)** | 800 | **Propósito:** Controla la rapidez con la que ocurre la transición entre banners, en milisegundos (1000ms = 1 segundo).   **Efecto:**   *Valor más alto (ej., 1500):* Transiciones más lentas y graduales.   *Valor más bajo (ej., 400):* Transiciones más rápidas y ágiles.   **Recomendado:** 800-1000ms para una sensación equilibrada y profesional. |
| **Intervalo entre diapositivas (ms)** | 3000 | **Propósito:** Establece la duración que se muestra cada banner antes de pasar al siguiente, en milisegundos.   **Efecto:**   *Valor más alto (ej., 5000):* Los banners permanecen en pantalla más tiempo, dando a los visitantes más tiempo para leer/ver.   *Valor más bajo (ej., 2000):* Los banners cambian más rápidamente, creando una sensación dinámica.   **Recomendado:** 3000-5000ms, dependiendo de la complejidad del contenido de su banner. |
| **Mostrar Flechas de Navegación** | SÍ | **Propósito:** Determina si las flechas de "siguiente" y "anterior" son visibles para la navegación manual de diapositivas.   **Efecto:**   *Cuando está habilitado:* Las flechas aparecen a los lados del slider, permitiendo a los usuarios hacer clic para pasar los banners.   *Cuando está deshabilitado:* Los banners solo cambian automáticamente según el intervalo.   **Recomendado:** SÍ, para un mejor control del usuario. |
| **Mostrar Puntos de Paginación** | SÍ | **Propósito:** Determina si los pequeños puntos (o miniaturas) que representan cada diapositiva son visibles, generalmente en la parte inferior del slider.   **Efecto:**   *Cuando está habilitado:* Aparecen puntos, permitiendo a los usuarios ver cuántas diapositivas hay y saltar a una específica.   *Cuando está deshabilitado:* No hay indicador visual del número de diapositivas o navegación directa.   **Recomendado:** SÍ, para una mejor orientación y navegación del usuario. |
| **Reproducción Automática del Slider** | SÍ | **Propósito:** Controla si el slider cicla automáticamente a través de los banners.   **Efecto:**   *Cuando está habilitado:* Los banners cambiarán automáticamente después del intervalo establecido.   *Cuando está deshabilitado:* Los banners solo cambiarán si el usuario hace clic en las flechas de navegación o en los puntos de paginación.   **Recomendado:** SÍ, para asegurar que todos sus mensajes sean vistos. |
| **Texto del Botón Cerrar** | Cerrar | **Propósito:** Le permite personalizar el texto que se muestra en el botón que cierra el slider a pantalla completa.   **Efecto:** Cambia el texto del botón.   **Recomendado:** "Cerrar", "Omitir" o "Continuar a la Tienda". |
| **Expiración de la Cookie (días)** | 7 | **Propósito:** Establece cuánto tiempo el módulo recuerda que un usuario ha visto el slider, evitando que se muestre de nuevo.   **Efecto:**   *Establecido en 7 días:* El slider reaparecerá para el mismo usuario después de 7 días.   *Establecido en 0:* El slider aparecerá en cada visita (no recomendado para la experiencia del usuario).   *Establecido en un número alto (ej., 365):* El slider aparecerá solo una vez al año para los visitantes recurrentes.   **Recomendado:** 7 días es un buen equilibrio, lo que le permite volver a interactuar con los visitantes recurrentes con nuevas ofertas periódicamente sin ser intrusivo. |

#### **Gestión de Banners**

Esta sección le permite añadir, editar y eliminar los banners individuales que se mostrarán en su slider.

- **Qué hace esta configuración:** Cada entrada aquí representa una imagen (banner) en su slider. Puede subir la imagen, vincularla a una página específica y establecer su orden de visualización.
- **Efecto de cambiar esta configuración:**
  - *Añadir un nuevo banner:* Introduce una nueva diapositiva en su rotación.
  - *Editar un banner:* Actualiza su imagen, enlace o posición.
  - *Eliminar un banner:* Lo elimina del slider.

Para cada banner, normalmente encontrará campos como:

- **Imagen del Banner:** Suba el archivo de imagen para su diapositiva. Asegúrese de que las imágenes sean de alta resolución y estén optimizadas para la web para mantener tiempos de carga rápidos.
- **Enlace del Banner (URL):** La dirección web (URL) a la que se dirigirán los clientes si hacen clic en este banner. Déjelo vacío si el banner es puramente informativo.
- **Orden de Visualización:** Un valor numérico que determina la secuencia de los banners. Los banners con números más bajos aparecen primero.

#### **Tabla de Referencia Rápida de Configuración**

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|
| Configuración del Módulo | Habilitar Slider a Pantalla Completa | SÍ | Activa/desactiva toda la función del slider. |
| Configuración del Módulo | Ancho del Slider | 100% | Establece el ancho del slider (ej., 100% para ancho completo). |
| Configuración del Módulo | Altura del Slider | 100% | Establece la altura del slider (ej., 100% para altura completa). |
| Configuración del Módulo | Tipo de Animación | (Varios) | Elige el efecto de transición visual entre diapositivas. |
| Configuración del Módulo | Velocidad de Animación (ms) | 800 | Controla la velocidad de las transiciones de diapositivas. |
| Configuración del Módulo | Intervalo entre diapositivas (ms) | 3000 | Establece cuánto tiempo se muestra cada banner. |
| Configuración del Módulo | Mostrar Flechas de Navegación | SÍ | Muestra/oculta las flechas para la navegación manual de diapositivas. |
| Configuración del Módulo | Mostrar Puntos de Paginación | SÍ | Muestra/oculta los puntos/miniaturas para el acceso directo a las diapositivas. |
| Configuración del Módulo | Reproducción Automática del Slider | SÍ | Habilita/deshabilita la progresión automática de las diapositivas. |
| Configuración del Módulo | Texto del Botón Cerrar | Cerrar | Personaliza el texto del botón de cierre del slider. |
| Configuración del Módulo | Expiración de la Cookie (días) | 7 | Determina cuánto tiempo un usuario no verá el slider después de cerrarlo. |
| Configuración del Módulo | Imagen del Banner | (Subir) | Sube la imagen para una diapositiva individual. |
| Configuración del Módulo | Enlace del Banner (URL) | (Vacío) | Establece la URL de destino cuando se hace clic en un banner. |
| Configuración del Módulo | Orden de Visualización | (Número) | Define la secuencia en la que aparecen los banners. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: El slider no aparece en mi tienda. ¿Qué debo hacer?**
R:

1. **Verificar el estado del módulo:** Vaya a **Módulos > Gestor de módulos** y asegúrese de que "Fullscreen Banner Slider" esté instalado y habilitado.
2. **Configuración:** Verifique que "Habilitar Slider a Pantalla Completa" esté configurado en SÍ en la configuración del módulo.
3. **Expiración de la cookie:** Si ya ha visto el slider antes, podría deberse a la cookie. Intente borrar las cookies de su navegador o abrir su tienda en una ventana de incógnito/privada para simular un visitante por primera vez.
4. **Caché:** Borre la caché de PrestaShop en **Parámetros avanzados > Rendimiento**. También, borre la caché de su navegador.
5. **Compatibilidad del tema:** Aunque el módulo está diseñado para ser compatible, a veces los temas personalizados pueden interferir. Cambie temporalmente al tema predeterminado de PrestaShop para ver si aparece el slider. Si lo hace, su tema podría requerir un pequeño ajuste (contacte con el desarrollador de su tema o un webmaster).

**P: Mis imágenes de banner se ven borrosas o estiradas. ¿Cómo puedo solucionar esto?**
R: Esto suele ocurrir si las imágenes que ha subido no tienen suficiente resolución o tienen relaciones de aspecto incorrectas para una visualización a pantalla completa.

1. **Calidad de imagen:** Utilice siempre imágenes de alta resolución.
2. **Relación de aspecto:** Aunque el módulo escala, intente utilizar imágenes que sean anchas y relativamente cortas, adecuadas para un banner a pantalla completa (por ejemplo, 1920x1080 píxeles o formatos anchos similares). Evite imágenes muy altas o estrechas.
3. **Optimización:** Asegúrese de que sus imágenes estén optimizadas para la web (comprimidas) para evitar tiempos de carga lentos, incluso si son de alta resolución.

**P: ¿Puedo tener diferentes sliders para diferentes páginas o grupos de clientes?**
R: Esta versión específica del módulo Fullscreen Banner Slider está diseñada para una única visualización a pantalla completa en todo el sitio que aparece una vez por sesión/cookie del visitante. No ofrece opciones de segmentación avanzadas para páginas o grupos de clientes específicos. Si necesita dicha funcionalidad, es posible que necesite un módulo de gestión de banners más avanzado o un desarrollo personalizado.

**P: ¿Cómo traduzco el texto del botón "Cerrar" a otros idiomas?**
R:

1. Vaya a **Internacional > Traducciones** en su Back Office de PrestaShop.
2. Seleccione "Traducciones de módulos instalados" como Tipo de traducción.
3. Elija su tema.
4. Seleccione el idioma que desea traducir.
5. Busque el módulo "Fullscreen Banner Slider" en la lista. Debería ver el campo "Texto del Botón Cerrar" allí para traducir. Guarde sus cambios.

**P: El slider aparece, pero las animaciones no funcionan o el diseño está desajustado.**
R:

1. **Conflictos de JavaScript:** Esto a menudo se debe a conflictos con el JavaScript de otros módulos o el JavaScript de su tema. Revise la consola de desarrollador de su navegador (tecla F12) en busca de errores de JavaScript.
2. **Conflictos de CSS:** Similar a JS, el CSS de su tema podría estar anulando los estilos del módulo.
3. **Reinstalación del módulo:** A veces, una reinstalación limpia puede resolver problemas inesperados. Desinstale el módulo (sin eliminar datos si se le pregunta), luego reinstálelo.
   Si los errores persisten, consulte a un webmaster o contacte con el soporte de MyPresta.eu con los detalles de la consola de desarrollador de su navegador.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo Fullscreen Banner Slider (`fullscreenslider`) es un módulo estándar de PrestaShop implementado principalmente dentro de su archivo PHP principal, `ajax_fullscreenslider.php`. Aprovecha la clase `Module` de PrestaShop para la instalación, desinstalación y configuración (`getContent()`). La visualización en el front-office se gestiona mediante el enganche a `displayHeader` y la renderización de una plantilla Smarty. La funcionalidad del slider en sí se basa en plugins externos de jQuery (`jquery.skitter.js`, `jquery.easing.1.3.js`) para animaciones y `noconflict.js` para asegurar la compatibilidad con jQuery. Los valores de configuración se almacenan en `ps_configuration`.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores de administración dedicados para el Front-Office o el Back-Office. Toda la configuración se maneja dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

Este módulo no define ninguna clase personalizada o instancias de `ObjectModel` en el directorio `classes/`. Todos los datos (imágenes de banner, enlaces, orden) se gestionan directamente a través de la configuración del módulo, típicamente serializados y almacenados en `ps_configuration`.

### 4.4 Activos JavaScript (`views/js/`)

El módulo incluye varios archivos JavaScript, principalmente para la funcionalidad central y las animaciones del slider. Estos se cargan típicamente en el front-office.

- `fullscreenslider/js/jquery.easing.1.3.js`
  - **Alcance:** Front-office.
  - **Responsabilidad:** Proporciona funciones de easing adicionales para las animaciones de jQuery, permitiendo efectos de transición más diversos y suaves más allá de los predeterminados lineales o de swing. Esta es una dependencia para `jquery.skitter.js`.
- `fullscreenslider/js/jquery.skitter.js`
  - **Alcance:** Front-office.
  - **Responsabilidad:** Este es el plugin principal de jQuery responsable de la funcionalidad del slider. Maneja la carga de imágenes, las transiciones de animación, la navegación (flechas, paginación), la reproducción automática y la vinculación de eventos para la interacción del usuario. Inicializa el slider basándose en la configuración pasada desde el módulo.
- `fullscreenslider/js/noconflict.js`
  - **Alcance:** Front-office.
  - **Responsabilidad:** Este script es crucial para asegurar la compatibilidad cuando se cargan múltiples bibliotecas JavaScript (especialmente diferentes versiones de jQuery) en la misma página. Típicamente envuelve el código jQuery en una expresión de función invocada inmediatamente (IIFE) que pasa `jQuery` como argumento, permitiendo que se le asigne el alias `$` localmente sin entrar en conflicto con otras bibliotecas que también puedan usar `$`.

### 4.5 Hojas de Estilo CSS (`views/css/`)

El módulo incluye un archivo CSS principal para estilizar el slider.

- `fullscreenslider/css/skitter.styles.css`
  - **Alcance:** Estilo del cliente en el front-office.
  - **Responsabilidad:** Contiene todas las reglas CSS necesarias para estilizar el slider a pantalla completa, incluyendo su contenedor, flechas de navegación, puntos de paginación y los efectos visuales del tipo de animación elegido. Define la apariencia predeterminada del slider.
  - **Selectores de clase CSS clave que los desarrolladores pueden anular:**
    - `.box_skitter` (contenedor principal del slider)
    - `.box_skitter ul` (lista de diapositivas)
    - `.box_skitter ul li` (diapositiva individual)
    - `.box_skitter .info_slide` (leyendas/información de la diapositiva, si se usan)
    - `.box_skitter .prev_button`, `.box_skitter .next_button` (flechas de navegación)
    - `.box_skitter .info_slide_dots`, `.box_skitter .info_slide_thumb` (elementos de paginación)
    - Clases específicas para tipos de animación (ej., `.cube`, `.fade`, etc.)

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

El módulo utiliza plantillas Smarty para renderizar su contenido en el front-office.

- **Plantillas de hook (`views/templates/hook/`)**:

  - `fullscreenslider/header.tpl`
    - **Hook:** `displayHeader` (o similar, dependiendo de la implementación del método `hook` del módulo).
    - **Propósito:** Esta plantilla es probablemente responsable de inyectar los archivos CSS y JavaScript necesarios en la sección `<head>` del HTML, y potencialmente la estructura HTML inicial para el contenedor del slider, que luego será poblado y animado por el JavaScript. También podría contener la lógica para verificar la cookie que determina si el slider debe mostrarse.
  - `fullscreenslider/top.tpl`
    - **Hook:** Esta plantilla probablemente se renderiza dentro del hook `displayTop` o se incluye directamente por `header.tpl` para generar la estructura HTML principal del slider a pantalla completa.
    - **Propósito:** Contiene los elementos `div` y la estructura `ul/li` que `jquery.skitter.js` espera encontrar para inicializar el slider. Itera a través de los banners configurados, mostrando cada imagen con su enlace asociado. También incluye el HTML para el botón de cierre.
- **Plantillas de administración (`views/templates/admin/`)**: Este módulo no parece utilizar plantillas de administración dedicadas, ya que la configuración se maneja directamente dentro de `getContent()`.
- **Plantillas de front-office (`views/templates/front/`)**: Este módulo no parece utilizar plantillas de página de front-office independientes dedicadas.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:

  - Este módulo no crea tablas SQL personalizadas.
  - La configuración (incluidos los datos serializados para banners como rutas de imagen, enlaces y orden) se almacena en la tabla `ps_configuration`. Las claves suelen seguir el patrón `FULLSCREENSLIDER_SETTING_NAME`.
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Se ejecuta en la sección `<head>` de cada página del front-office. | Inyecta los archivos CSS y JavaScript del módulo, y potencialmente la estructura HTML inicial para el slider, junto con la lógica de verificación de cookies. |
| `displayTop` (o similar) | Se ejecuta en la sección superior de la página del front-office, a menudo justo debajo del encabezado. | Renderiza la estructura HTML principal del slider a pantalla completa, incluyendo las imágenes de los banners y los elementos de navegación. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo Fullscreen Banner Slider, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar a comerciantes y desarrolladores con cualquier problema o pregunta relacionada con la funcionalidad y compatibilidad del módulo.
