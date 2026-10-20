---
title: "Popup Slider - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Popup Slider para PrestaShop de MyPresta.eu."
sidebar:
  label: "Popup Slider - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Popup Slider en MyPresta.eu](https://mypresta.eu/modules/front-office-features/popup-slider.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/popup-slider/)
>
> ---


# Popup Slider

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.4.x, 1.5.x, 1.6.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal para el módulo Popup Slider, donde definirá cómo se ve y se comporta su ventana emergente.

#### Ajustes generales

- **Ancho del Popup (px):**

  - **Qué hace este ajuste:** Define el ancho de la ventana emergente en píxeles.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece un valor específico (por ejemplo, 800):* La ventana emergente aparecerá exactamente 800 píxeles de ancho en pantallas de escritorio.
    - *Cuando se establece un valor diferente:* La ventana emergente se redimensionará en consecuencia.
  - **Valor recomendado:** 800px (o ajuste según el tamaño de sus imágenes y diseño).
  - **Escenario/ejemplo de comerciante:** Si las imágenes de su slider tienen 800px de ancho, establecer esto en 800px asegura que encajen perfectamente sin problemas de escala.
- **Altura del Popup (px):**

  - **Qué hace este ajuste:** Define la altura de la ventana emergente en píxeles.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece un valor específico (por ejemplo, 500):* La ventana emergente aparecerá exactamente 500 píxeles de alto.
    - *Cuando se establece un valor diferente:* La ventana emergente se redimensionará en consecuencia.
  - **Valor recomendado:** 500px (o ajuste según el tamaño de sus imágenes y diseño).
  - **Escenario/ejemplo de comerciante:** Si las imágenes de su slider tienen 500px de alto, establecer esto en 500px asegura que encajen perfectamente.
- **Color de fondo del Popup:**

  - **Qué hace este ajuste:** Establece el color de fondo de la propia ventana emergente (el área detrás de las imágenes de su slider). Puede usar un selector de color para seleccionar.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece un color específico (por ejemplo, #FFFFFF para blanco):* El fondo de la ventana emergente mostrará ese color.
    - *Cuando se establece un color diferente:* El color de fondo cambia.
  - **Valor recomendado:** #FFFFFF (blanco) o un color que complemente el diseño de su tienda.
  - **Escenario/ejemplo de comerciante:** Si su tienda tiene un tema oscuro, podría elegir un gris claro (#F5F5F5) para el fondo de la ventana emergente para que el contenido destaque.
- **Color del borde del Popup:**

  - **Qué hace este ajuste:** Establece el color del borde alrededor de la ventana emergente.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece un color específico (por ejemplo, #CCCCCC para gris claro):* La ventana emergente tendrá un borde de ese color.
    - *Cuando se establece un color diferente:* El color del borde cambia.
  - **Valor recomendado:** #CCCCCC (gris claro) o un color que coincida con su marca.
  - **Escenario/ejemplo de comerciante:** Un borde sutil puede ayudar a definir la ventana emergente contra un fondo ocupado.
- **Ancho del borde del Popup (px):**

  - **Qué hace este ajuste:** Define el grosor del borde de la ventana emergente en píxeles.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 1:* El borde tendrá 1 píxel de grosor.
    - *Cuando se establece en 0:* No se verá ningún borde.
  - **Valor recomendado:** 1px o 0px.
  - **Escenario/ejemplo de comerciante:** Un borde de 0px puede crear un aspecto más fluido y moderno si su diseño no requiere un borde visible.
- **Radio del borde del Popup (px):**

  - **Qué hace este ajuste:** Controla la redondez de las esquinas de la ventana emergente. Un valor más alto significa esquinas más redondeadas.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 0:* La ventana emergente tendrá esquinas afiladas y cuadradas.
    - *Cuando se establece en 10:* Las esquinas estarán ligeramente redondeadas.
  - **Valor recomendado:** 5px o 0px.
  - **Escenario/ejemplo de comerciante:** Las esquinas redondeadas pueden darle a su ventana emergente una estética más suave y moderna.
- **Sombra del Popup:**

  - **Qué hace este ajuste:** Agrega un efecto de sombra alrededor de la ventana emergente, haciéndola parecer que flota sobre la página.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* Aparecerá una sombra sutil alrededor de la ventana emergente.
    - *Cuando está deshabilitado (NO):* La ventana emergente no tendrá sombra.
  - **Valor recomendado:** SÍ.
  - **Escenario/ejemplo de comerciante:** Una sombra ayuda a que la ventana emergente destaque del contenido de fondo, mejorando la visibilidad y la profundidad percibida.
- **Color de la superposición del Popup:**

  - **Qué hace este ajuste:** Establece el color de la superposición semitransparente que cubre el resto del contenido de su tienda cuando la ventana emergente está activa.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece un color específico (por ejemplo, #000000 para negro):* La superposición será de ese color.
  - **Valor recomendado:** #000000 (negro).
  - **Escenario/ejemplo de comerciante:** Una superposición oscura ayuda a enfocar la atención del visitante únicamente en el contenido de la ventana emergente.
- **Opacidad de la superposición del Popup (0-1):**

  - **Qué hace este ajuste:** Controla la transparencia de la superposición. 0 es completamente transparente, 1 es completamente opaco.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 0.5:* La superposición será 50% transparente, permitiendo ver parte del contenido de la tienda de fondo.
    - *Cuando se establece en 0.8:* La superposición será 80% opaca, haciendo que el contenido de fondo sea muy tenue.
  - **Valor recomendado:** 0.7 o 0.8.
  - **Escenario/ejemplo de comerciante:** Una opacidad más alta asegura que la ventana emergente sea el foco principal, mientras que una opacidad más baja podría usarse si desea insinuar sutilmente el contenido detrás de la ventana emergente.
- **Tiempo de re-visualización del Popup (horas):**

  - **Qué hace este ajuste:** Determina cuántas horas deben pasar antes de que la ventana emergente se muestre nuevamente al mismo visitante después de que la haya cerrado.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 0:* La ventana emergente aparecerá cada vez que el visitante cargue una página (no recomendado para la experiencia del usuario).
    - *Cuando se establece en 24:* La ventana emergente reaparecerá después de 24 horas.
    - *Cuando se establece un número muy alto (por ejemplo, 8760 para 1 año):* La ventana emergente solo se mostrará una vez por visitante.
  - **Valor recomendado:** 24 (para promociones diarias) o 168 (para promociones semanales) o un número muy alto como 8760 (para una vez al año o efectivamente una vez en la vida).
  - **Escenario/ejemplo de comerciante:** Si tiene ofertas diarias, establecer esto en 24 horas asegura que los visitantes vean la nueva oferta cada día. Si solo desea mostrar un mensaje de bienvenida una vez, configúrelo con un número muy alto.
- **Mostrar botón de cierre:**

  - **Qué hace este ajuste:** Alterna la visibilidad del botón de cierre 'X' en la ventana emergente.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* Un botón de cierre será visible, permitiendo a los visitantes descartar fácilmente la ventana emergente.
    - *Cuando está deshabilitado (NO):* No se mostrará ningún botón de cierre. Los visitantes tendrán que hacer clic fuera de la ventana emergente o navegar para cerrarla.
  - **Valor recomendado:** SÍ.
  - **Escenario/ejemplo de comerciante:** Siempre proporcione una forma clara para que los usuarios cierren la ventana emergente para evitar la frustración y mejorar la experiencia del usuario.
- **Cerrar al hacer clic en la superposición:**

  - **Qué hace este ajuste:** Determina si al hacer clic en la superposición semitransparente (fuera del contenido de la ventana emergente) se cerrará la ventana emergente.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* Al hacer clic en la superposición se cerrará la ventana emergente.
    - *Cuando está deshabilitado (NO):* Solo el botón de cierre (si está habilitado) o la navegación cerrarán la ventana emergente.
  - **Valor recomendado:** SÍ.
  - **Escenario/ejemplo de comerciante:** Esto proporciona una forma intuitiva y común para que los usuarios descarten las ventanas emergentes, mejorando la usabilidad.

#### Configuración de imágenes del Slider

Esta sección le permite agregar, editar y administrar las imágenes que aparecerán en su slider emergente. Puede agregar un número ilimitado de imágenes.

Para cada ranura de imagen, encontrará típicamente:

- **Campo de carga de imagen:**

  - **Qué hace este ajuste:** Le permite cargar un archivo de imagen desde su ordenador para que se muestre en el slider.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se carga una imagen:* Reemplaza cualquier imagen existente en esa ranura o agrega una nueva al slider.
  - **Valor recomendado:** Utilice imágenes de alta calidad y optimizadas que coincidan con la relación de aspecto del ancho/alto de su ventana emergente.
  - **Escenario/ejemplo de comerciante:** Suba su última foto de producto, un banner para una oferta o un gráfico que promocione una nueva característica.
- **Enlace de imagen (URL):**

  - **Qué hace este ajuste:** Especifica la URL a la que se redirigirá a los visitantes cuando hagan clic en esta imagen específica del slider.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se introduce una URL:* Al hacer clic en la imagen, el visitante será llevado a esa página.
    - *Cuando se deja vacío:* La imagen no será clicable.
  - **Valor recomendado:** Siempre enlace a páginas relevantes (producto, categoría, entrada de blog, página de contacto).
  - **Escenario/ejemplo de comerciante:** Enlace un banner de "Novedades" a la página de categoría de sus nuevos productos, o un banner de "Rebajas de Verano" a su página de destino de rebajas.
- **Título/Texto Alt de la imagen:**

  - **Qué hace este ajuste:** Proporciona una descripción de texto para la imagen. Este texto es importante para el SEO (motores de búsqueda) y la accesibilidad (lectores de pantalla para usuarios con discapacidad visual).
  - **Efecto de cambiar este ajuste:**
    - *Cuando se introduce texto:* Este texto será utilizado por los motores de búsqueda para comprender el contenido de la imagen y por los lectores de pantalla para describir la imagen.
  - **Valor recomendado:** Una frase concisa y descriptiva que describa con precisión el contenido de la imagen e incluya palabras clave relevantes.
  - **Escenario/ejemplo de comerciante:** Para una imagen de un vestido nuevo, use "Vestido de Nueva Colección de Verano - ¡Compre Ahora!".
- **Botón Eliminar imagen:**

  - **Qué hace este ajuste:** Elimina la imagen seleccionada del slider.
  - **Efecto de cambiar este ajuste:**
    - *Al hacer clic:* La imagen y sus ajustes asociados se eliminan de la configuración del slider.
  - **Valor recomendado:** Utilice esto para eliminar promociones o imágenes desactualizadas.
  - **Escenario/ejemplo de comerciante:** Después de que termine una oferta, elimine la imagen del banner que promocionaba esa oferta.
- **Botón Añadir nueva imagen:**

  - **Qué hace este ajuste:** Agrega una nueva ranura vacía para que pueda subir otra imagen al slider.
  - **Efecto de cambiar este ajuste:**
    - *Al hacer clic:* Aparece un nuevo conjunto de campos para subir imagen, enlace y título.
  - **Valor recomendado:** Utilice esto para expandir el contenido de su slider.
  - **Escenario/ejemplo de comerciante:** Agregue una nueva diapositiva para una próxima promoción festiva.

#### Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Ancho del Popup (px) | 800 | Establece el ancho de la ventana emergente. |
| Configuración del módulo | Altura del Popup (px) | 500 | Establece la altura de la ventana emergente. |
| Configuración del módulo | Color de fondo del Popup | #FFFFFF | Color de fondo del área de contenido de la ventana emergente. |
| Configuración del módulo | Color del borde del Popup | #CCCCCC | Color del borde alrededor de la ventana emergente. |
| Configuración del módulo | Ancho del borde del Popup (px) | 1 | Grosor del borde de la ventana emergente. |
| Configuración del módulo | Radio del borde del Popup (px) | 5 | Redondez de las esquinas de la ventana emergente. |
| Configuración del módulo | Sombra del Popup | SÍ | Agrega un efecto de sombra para profundidad. |
| Configuración del módulo | Color de la superposición del Popup | #000000 | Color de la superposición de fondo semitransparente. |
| Configuración del módulo | Opacidad de la superposición del Popup (0-1) | 0.7 | Nivel de transparencia de la superposición. |
| Configuración del módulo | Tiempo de re-visualización del Popup (horas) | 24 | Cuánto tiempo antes de que la ventana emergente se muestre de nuevo a un visitante. |
| Configuración del módulo | Mostrar botón de cierre | SÍ | Muestra un botón 'X' para cerrar la ventana emergente. |
| Configuración del módulo | Cerrar al hacer clic en la superposición | SÍ | Permite cerrar la ventana emergente haciendo clic fuera de ella. |
| Configuración del módulo | Campo de carga de imagen | N/A | Sube una imagen para una diapositiva. |
| Configuración del módulo | Enlace de imagen (URL) | N/A | URL a la que navegar al hacer clic en la imagen de la diapositiva. |
| Configuración del módulo | Título/Texto Alt de la imagen | N/A | Texto descriptivo para SEO y accesibilidad. |
| Configuración del módulo | Botón Eliminar imagen | N/A | Elimina una diapositiva del slider. |
| Configuración del módulo | Botón Añadir nueva imagen | N/A | Agrega una nueva ranura de diapositiva vacía. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mi ventana emergente no aparece en absoluto. ¿Qué debo verificar?**
R1:

- **Módulo habilitado:** Primero, asegúrese de que el módulo esté habilitado en **Módulos > Gestor de módulos**.
- **Configuración guardada:** Asegúrese de haber guardado sus ajustes de configuración después de realizar cambios.
- **Imágenes añadidas:** ¿Ha subido al menos una imagen a la configuración del slider? El slider no aparecerá si no hay imágenes.
- **Caché:** Borre la caché de su PrestaShop (**Parámetros avanzados > Rendimiento > Borrar caché**) y la caché de su navegador. A veces, los archivos de caché antiguos impiden que se cargue el nuevo contenido del módulo.
- **Tiempo de re-visualización:** Si ha visitado su sitio antes, el "Tiempo de re-visualización del Popup" podría estar impidiendo que se muestre de nuevo. Intente abrir su tienda en una ventana de incógnito/privada del navegador para simular un visitante por primera vez.

**P2: Mi ventana emergente se ve extraña o no está centrada correctamente en mi tema personalizado.**
R2:

- **Conflictos de tema:** Los temas personalizados a veces tienen estilos CSS conflictivos.
- **Ajustes de ancho/alto:** Vuelva a verificar sus ajustes de "Ancho del Popup" y "Altura del Popup" en la configuración del módulo. Asegúrese de que sean apropiados para sus imágenes y tamaños de pantalla.
- **Asistencia del desarrollador:** Si el problema persiste, podría requerir un pequeño ajuste de CSS por parte de un desarrollador web familiarizado con su tema. Pueden inspeccionar los elementos y aplicar estilos personalizados para resolver conflictos.

**P3: Las imágenes de mi slider están borrosas o distorsionadas.**
R3:

- **Calidad de imagen:** Asegúrese de que las imágenes que está subiendo sean de alta resolución y no estén pixeladas.
- **Relación de aspecto:** Las imágenes deben coincidir idealmente con la relación de aspecto (relación ancho-alto) que ha establecido para su "Ancho del Popup" y "Altura del Popup". Si sus imágenes tienen una relación diferente, podrían estirarse o comprimirse para ajustarse.
- **Optimización de imagen:** Si bien la alta resolución es buena, los tamaños de archivo excesivamente grandes pueden ralentizar su sitio. Optimice sus imágenes para uso web (por ejemplo, comprímalas) antes de subirlas.

**P4: ¿Puedo tener diferentes ventanas emergentes para diferentes páginas o grupos de clientes?**
R4: El módulo Popup Slider, en su versión actual, muestra una única ventana emergente global a todos los visitantes basándose en la lógica de re-visualización. No admite de forma nativa diferentes ventanas emergentes para páginas específicas o grupos de clientes. Para una funcionalidad tan avanzada, normalmente necesitaría un módulo más complejo o un desarrollo personalizado.

**Q5: ¿Cómo traduzco el texto del módulo (por ejemplo, el texto del botón de cierre, si lo hay)?**
A5: Aunque este módulo utiliza principalmente imágenes, cualquier elemento de texto predeterminado sería traducible a través del sistema de traducción de PrestaShop:

- Navegue a **Internacional > Traducciones**.
- Seleccione "Traducciones de módulos instalados".
- Elija su tema, su idioma y luego busque "Popup Slider" en la lista de módulos.
- Luego podrá editar cualquier cadena traducible.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión técnica profunda en la arquitectura del módulo Popup Slider, destinada a desarrolladores y webmasters.

### 4.1 Visión general de la arquitectura

El módulo Popup Slider (`popupslider/cz.php`) es un módulo clásico de PrestaShop 1.4-1.6, que aprovecha principalmente la clase `Module` para su funcionalidad principal. Se integra en el front-office a través de un hook (típicamente `displayHeader` o `displayFooter` implícitamente, aunque la documentación menciona `Header, Columns, Product, or Footer` como posibles áreas de visualización, la plantilla proporcionada `header.tpl` sugiere que `displayHeader` es el punto de integración principal). La configuración se gestiona a través del método `getContent()`, almacenando los ajustes en `ps_configuration`. La interacción con el front-office se maneja inyectando JavaScript y CSS, que luego renderiza el slider utilizando la biblioteca bxSlider.

### 4.2 Controladores (`controllers/`)

Este módulo no contiene ningún controlador personalizado de Front-Office o Back-Office. Toda la configuración se maneja dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no define ninguna clase personalizada o instancias de `ObjectModel`. Todos los datos de configuración se almacenan directamente en la tabla `ps_configuration` utilizando los métodos estándar `Configuration::get()` y `Configuration::updateValue()`.

### 4.4 Activos JavaScript (`views/js/`)

El módulo depende en gran medida de JavaScript para su funcionalidad de front-office, específicamente para el comportamiento de la ventana emergente y el slider.

- **`popupslider/jscolor/jscolor.js`**:

  - **Alcance:** Back-office (utilizado dentro de la página de configuración del módulo).
  - **Responsabilidad:** Proporciona una funcionalidad de selector de color JavaScript para el formulario de configuración del módulo, permitiendo a los comerciantes seleccionar fácilmente colores para el fondo, el borde y la superposición de la ventana emergente.
  - **Detalles:** Esta es una biblioteca de terceros integrada para la mejora de la interfaz de usuario en el panel de administración.
- **`popupslider/js/bxslider.js`**:

  - **Alcance:** Front-office.
  - **Responsabilidad:** Esta es la biblioteca principal para el slider de imágenes animado dentro de la ventana emergente. Maneja las transiciones, los controles de navegación (flechas, puntos) y el comportamiento responsivo de la presentación de diapositivas.
  - **Detalles:** Un slider de contenido jQuery ampliamente utilizado. El módulo inicializa este slider en las imágenes dentro de la ventana emergente.
- **`popupslider/js/script.js`**:

  - **Alcance:** Front-office.
  - **Responsabilidad:** Este script personalizado orquesta la apariencia y el comportamiento de la ventana emergente.
    - **Gestión de cookies:** Comprueba si existe una cookie para determinar si el usuario es un visitante por primera vez o si ha transcurrido el tiempo de re-visualización.
    - **Visualización del Popup:** Activa la visualización de la superposición de la ventana emergente y el contenido del slider.
    - **Manejo de eventos:** Vincula eventos para cerrar la ventana emergente (por ejemplo, haciendo clic en el botón de cierre, haciendo clic en la superposición).
    - **Inicialización de bxSlider:** Inicializa `bxslider.js` en el elemento DOM apropiado que contiene las imágenes del slider.
  - **Detalles:** Este script es crucial para la lógica de visualización "inteligente" del módulo y la interacción del usuario.

### 4.5 Hojas de estilo CSS (`views/css/`)

El módulo no lista explícitamente archivos CSS personalizados en el inventario proporcionado. Sin embargo, es muy probable que la biblioteca `bxslider.js` incluya su propio CSS (por ejemplo, `jquery.bxslider.css` o similar) que se cargaría, y el `header.tpl` o `cz.php` del módulo podría inyectar estilos en línea basados en la configuración (colores, dimensiones).

Si hubiera algún archivo CSS presente, típicamente:

- **Alcance:** Front-office (para el estilo de la ventana emergente y el slider).
- **Componentes principales de la interfaz de usuario:** Estilizan el contenedor de la ventana emergente, la superposición, el botón de cierre, la navegación del slider (flechas, puntos) y las imágenes de las diapositivas individuales.
- **Selectores de clase CSS clave:** Los desarrolladores deben buscar clases como `.popupslider-overlay`, `.popupslider-container`, `.popupslider-close`, `.bx-wrapper`, `.bx-viewport`, `.bx-controls`, etc., para sobrescribir en el `custom.css` de su tema o tema hijo.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**:
  - **`popupslider/header.tpl`**:
    - **Hook:** Probablemente `displayHeader` (o similar, dado el nombre). Esta plantilla es responsable de renderizar la estructura HTML de la superposición de la ventana emergente, el contenedor de la ventana emergente y el propio slider de imágenes.
    - **Salida:** Genera los elementos `div` necesarios para la superposición, el cuadro principal de la ventana emergente, el botón de cierre y la lista `ul` que `bxslider.js` transformará en una presentación de diapositivas interactiva. También es probable que incluya estilos en línea derivados de la configuración del módulo (ancho, alto, colores, etc.) e incluya los activos JavaScript y CSS necesarios.

### 4.7 Esquema de la base de datos y mapa de Hooks

- **Tablas de la base de datos**:

  - Este módulo no crea tablas de base de datos personalizadas. Todos los ajustes de configuración se almacenan en la tabla estándar `ps_configuration` de PrestaShop.
  - **Claves de configuración (Ejemplos):**
    - `POPUP_SLIDER_WIDTH`
    - `POPUP_SLIDER_HEIGHT`
    - `POPUP_SLIDER_BG_COLOR`
    - `POPUP_SLIDER_BORDER_COLOR`
    - `POPUP_SLIDER_BORDER_WIDTH`
    - `POPUP_SLIDER_BORDER_RADIUS`
    - `POPUP_SLIDER_SHADOW`
    - `POPUP_SLIDER_OVERLAY_COLOR`
    - `POPUP_SLIDER_OVERLAY_OPACITY`
    - `POPUP_SLIDER_REDISPLAY_TIME`
    - `POPUP_SLIDER_SHOW_CLOSE_BTN`
    - `POPUP_SLIDER_CLOSE_ON_OVERLAY_CLICK`
    - `POPUP_SLIDER_IMAGE_X` (donde X es un ID incremental para cada imagen, almacenando URL, enlace, texto alternativo).
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | Se ejecuta en la sección `<head>` de cada página del front-office. | Se utiliza para inyectar los archivos CSS y JavaScript del módulo, y potencialmente la estructura HTML inicial de la ventana emergente (aunque la ventana emergente en sí suele estar oculta hasta que se activa por JS). |
| `displayFooter` (Potencial) | Se ejecuta al final de la sección `<body>` de cada página del front-office. | Podría usarse como alternativa a `displayHeader` para inyectar el HTML y JS de la ventana emergente, a menudo preferido por rendimiento ya que no bloquea la renderización de la página. |
| `displayRightColumn` (Potencial) | Se ejecuta en la columna derecha del front-office. | Aunque se menciona en la descripción del comerciante, es poco probable que una ventana emergente de página completa se renderice aquí. Más probable para un pequeño banner o un disparador. |
| `displayLeftColumn` (Potencial) | Se ejecuta en la columna izquierda del front-office. | Similar a `displayRightColumn`, poco probable para una ventana emergente de página completa. |
| `displayProductButtons` (Potencial) | Se ejecuta en la página del producto, cerca del botón de añadir al carrito. | Poco probable para una ventana emergente global, pero podría usarse para una ventana emergente específica del producto si el módulo tuviera tales características avanzadas. |

Dado el archivo `header.tpl`, `displayHeader` es el hook más probable para inyectar los activos del módulo y la estructura inicial de la ventana emergente.

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo Popup Slider, consulte su cuenta de cliente en MyPresta.eu. Nuestro equipo se dedica a brindar asistencia y garantizar que su módulo funcione de manera óptima.

- **Historial de pedidos y descargas de MyPresta.eu:** <https://mypresta.eu/my-account/orders/>
- **Contacto de soporte de MyPresta.eu:** <https://mypresta.eu/contact>
