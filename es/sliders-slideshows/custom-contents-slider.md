---
title: "Slider de contenido personalizado - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Slider de contenido personalizado' de MyPresta.eu."
sidebar:
  label: "Slider de contenido personalizado - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Custom contents slider en MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/custom-contents-slider.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/sliders-slideshows/custom-contents-slider/)
>
> ---


# Slider de contenido personalizado

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor.

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" accederá a la página de configuración principal del módulo "Slider de contenido personalizado". Aquí es donde se define el contenido, la apariencia y el comportamiento de sus sliders.

La página de configuración está impulsada por la biblioteca `SmartyTemplatesManager`, que le permite crear y gestionar múltiples bloques de contenido personalizado.

#### **Formulario principal (mainForm.tpl)**

Esta sección proporciona una visión general de sus sliders existentes y le permite añadir nuevos.

-   **Qué hace esta sección:** Muestra una lista de todos los sliders de contenido personalizado que ha creado. Cada entrada muestra información básica como el nombre del slider, la posición y el estado.
-   **Efecto de cambiar esta sección:** Desde aquí, puede ver rápidamente qué sliders están activos y dónde se muestran. También puede hacer clic para editar sliders existentes o añadir nuevos.
-   **Acción recomendada:** Revise sus sliders existentes. Si lo está configurando por primera vez, querrá hacer clic en el botón "Añadir nueva plantilla".

#### **Formulario Crear/Editar plantilla (createTemplateForm.tpl / editTemplateForm.tpl)**

Cuando haga clic en "Añadir nueva plantilla" o "Editar" un slider existente, accederá a un formulario donde definirá todos los detalles de ese slider específico.

-   **Nombre de la plantilla:**

    -   **Qué hace esta configuración:** Este es un nombre interno para su slider, visible solo en el back office. Le ayuda a identificar diferentes sliders.
    -   **Efecto de cambiar esta configuración:** Cambiar esto solo afecta cómo lo ve en el panel de administración; no tiene impacto en el front office.
    -   **Valor recomendado:** Un nombre descriptivo, por ejemplo, "Slider izquierdo de rebajas de verano", "Slider inferior de suscripción al boletín".
    -   **Escenario / ejemplo de comerciante:** Si tiene varias promociones, nombrarlas claramente le ayuda a gestionarlas.
-   **Contenido de la plantilla:**

    -   **Qué hace esta configuración:** Este es el núcleo de su slider. Puede introducir cualquier HTML, texto o incluso código Smarty aquí. Este contenido se mostrará dentro del panel deslizante.
    -   **Efecto de cambiar esta configuración:** Esto cambia directamente lo que ven sus clientes cuando el slider se expande. Puede incluir imágenes, enlaces, párrafos, formularios, etc.
    -   **Valor recomendado:** Utilice HTML estándar. Manténgalo conciso y visualmente atractivo. Para las imágenes, utilice URLs absolutas o el asistente de imágenes de PrestaShop.
    -   **Escenario / ejemplo de comerciante:**

        ```
        <h3>¡Oferta por tiempo limitado!</h3><p>¡Obtenga un <strong>15% de descuento</strong> en todos los artículos de la colección de verano!</p><a href="{$link->getPageLink('category', true, null, ['id\_category' => 123])}" class="button btn btn-primary">¡Comprar ahora!</a>
        ```

        (Nota: Las variables Smarty como `{$link->getPageLink(...)` requieren que el procesamiento Smarty esté habilitado para el contenido, lo cual este módulo soporta).
-   **Posición:**

    -   **Qué hace esta configuración:** Determina dónde aparecerá el slider en la pantalla del cliente.
    -   **Efecto de cambiar esta configuración:**
        -   *Izquierda:* El slider aparece desde el borde izquierdo.
        -   *Derecha:* El slider aparece desde el borde derecho.
        -   *Abajo:* El slider aparece desde el borde inferior.
    -   **Valor recomendado:** Elija según su diseño y otros elementos de su página. Derecha y Abajo suelen ser menos intrusivos que Izquierda.
    -   **Escenario / ejemplo de comerciante:** Use "Derecha" para un formulario de contacto rápido, "Abajo" para un banner de consentimiento de cookies o "Izquierda" para un código de descuento especial.
-   **Abrir al:**

    -   **Qué hace esta configuración:** Define cómo se expande el slider para mostrar su contenido.
    -   **Efecto de cambiar esta configuración:**
        -   *Clic:* El slider se expande solo cuando el cliente hace clic en su pestaña de activación.
        -   *Pasar el ratón:* El slider se expande cuando el cliente mueve el cursor del ratón sobre su pestaña de activación.
    -   **Valor recomendado:** "Clic" es generalmente menos intrusivo y evita aperturas accidentales. "Pasar el ratón" puede ser bueno para contenido muy sutil y de vista rápida.
    -   **Escenario / ejemplo de comerciante:** Para anuncios o formularios importantes, "Clic" es mejor. Para un botón de chat rápido "¿Hola, en qué puedo ayudar?", "Pasar el ratón" podría funcionar.
-   **Activo:**

    -   **Qué hace esta configuración:** Activa o desactiva la visibilidad de este slider específico en su front office.
    -   **Efecto de cambiar esta configuración:**
        -   *Habilitado (Sí):* El slider aparecerá en su tienda según su configuración.
        -   *Deshabilitado (No):* El slider se ocultará de su tienda, pero su configuración se guardará.
    -   **Valor recomendado:** "Sí" para sliders activos, "No" para sliders que desea ocultar temporalmente o en los que aún está trabajando.
    -   **Escenario / ejemplo de comerciante:** Podría deshabilitar un slider de promoción navideña después de las vacaciones y luego volver a habilitarlo el próximo año.

#### **Gestor de botones (buttonManager.tpl)**

Esta sección forma parte de `SmartyTemplatesManager` y le permite gestionar los botones o activadores de sus sliders. Aunque el módulo utiliza principalmente la configuración "Abrir al", esta sección podría ofrecer personalización adicional para el propio activador visual.

-   **Qué hace esta sección:** Proporciona opciones para personalizar la apariencia de la pestaña o botón con el que los clientes interactúan para abrir el slider. Esto podría incluir texto, iconos o estilos básicos.
-   **Efecto de cambiar esta sección:** Modifica el aspecto visual del activador del slider en el front office.
-   **Valor recomendado:** Mantenga el activador claro y atractivo. Utilice texto conciso o un icono relevante.
-   **Escenario / ejemplo de comerciante:** Podría establecer el texto del botón en "¡Oferta!", "Contáctenos" o usar un pequeño icono de chat.

#### **Entrada de selección (selectInput.tpl)**

Esta es una plantilla genérica para selecciones desplegables dentro de `SmartyTemplatesManager`. Se utiliza para configuraciones como "Posición" y "Abrir al".

-   **Qué hace esta sección:** Presenta una lista desplegable de opciones predefinidas para una configuración particular.
-   **Efecto de cambiar esta sección:** Le permite elegir entre un conjunto limitado de opciones para una configuración dada.
-   **Valor recomendado:** Seleccione la opción que mejor se adapte al comportamiento deseado del slider.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Formulario principal | (Lista de Sliders) | N/A | Resumen de todos los sliders creados; permite añadir/editar. |
| Crear/Editar plantilla | **Nombre de la plantilla** | Nombre descriptivo | Identificador interno del slider en el back office. |
| Crear/Editar plantilla | **Contenido de la plantilla** | HTML/Texto personalizado | El contenido real que se muestra dentro del slider. |
| Crear/Editar plantilla | **Posición** | Derecha / Abajo | Dónde aparece el slider en la pantalla (Izquierda, Derecha, Abajo). |
| Crear/Editar plantilla | **Abrir al** | Clic | Cómo se expande el slider (Clic o Pasar el ratón). |
| Crear/Editar plantilla | **Activo** | Sí | Alterna la visibilidad del slider en el front office. |
| Gestor de botones | (Opciones de botón) | N/A | Personaliza el activador visual del slider (texto, icono, estilo). |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Mi slider no aparece en el front office. ¿Qué debo verificar?**
R:

1.  **¿Está el slider "Activo"?** Vaya a la configuración del módulo, edite su slider y asegúrese de que la configuración "Activo" esté en "Sí".
2.  **¿Es válido el contenido?** Asegúrese de que no haya etiquetas HTML sin cerrar o errores de JavaScript en su "Contenido de la plantilla" que puedan romper la visualización.
3.  **Borre su caché:** Vaya a **Parámetros avanzados > Rendimiento** en su back office de PrestaShop y borre la caché de Smarty (y opcionalmente toda la caché).
4.  **Verifique si hay conflictos:** Deshabilite temporalmente otros módulos que puedan estar añadiendo elementos flotantes o modificando el diseño de la página para ver si hay un conflicto.

**P: El slider aparece, pero el estilo se ve mal o no coincide con mi tema.**
R:

1.  **CSS predeterminado del módulo:** El módulo viene con su propio CSS. El CSS de su tema podría estar anulándolo, o viceversa.
2.  **Estilo de tema personalizado:** Es posible que deba agregar reglas CSS personalizadas a la hoja de estilo de su tema para ajustar la apariencia del slider. Use las herramientas de desarrollo de su navegador (F12) para inspeccionar los elementos del slider e identificar las clases CSS a las que apuntar.
3.  **Estilo del contenido:** Si está colocando HTML sin formato en el "Contenido de la plantilla", asegúrese de usar clases apropiadas o estilos en línea que funcionen con su tema.

**P: ¿Puedo tener varios sliders activos a la vez?**
R: Sí, el módulo admite varios sliders. Sin embargo, tenga en cuenta la experiencia del usuario. Tener demasiados sliders (por ejemplo, uno a la izquierda, uno a la derecha y uno en la parte inferior) puede saturar la interfaz y abrumar a los clientes. Generalmente, es mejor usar uno o dos estratégicamente.

**P: ¿Cómo añado imágenes o enlaces al contenido de mi slider?**
R: Puede usar etiquetas HTML estándar dentro del campo "Contenido de la plantilla":

-   **Imágenes:** `<img src="url_de_su_imagen.jpg" alt="Descripción" style="width:100px;">` (Use URLs absolutas para las imágenes).
-   **Enlaces:** `<a href="url_de_su_pagina.html">Haga clic aquí</a>` (También puede usar variables Smarty para enlaces de PrestaShop, por ejemplo, `<a href="{$link->getPageLink('contact')}">Contáctenos</a>`).

**P: ¿Funciona con varios idiomas y varias tiendas?**
R: Sí, el módulo está diseñado para funcionar correctamente en entornos multilingües y multi-tienda. Puede crear diferentes sliders o contenido diferente para el mismo slider para cada idioma y tienda, lo que permite una mensajería altamente dirigida.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Slider de contenido personalizado" (`saslider`) está construido como un módulo estándar de PrestaShop, aprovechando principalmente la clase `Module` para su ciclo de vida y `SmartyTemplatesManager` para la creación y gestión dinámica de contenido. Se integra con el sistema de hooks de PrestaShop para inyectar sus activos y contenido de front-office. La lógica central del módulo reside en su archivo `index.php` principal, que maneja la configuración, instalación y renderizado del front-office. No utiliza controladores frontales o de administración dedicados, sino que se basa en el método `getContent()` para su configuración de back-office y el registro directo de hooks para la visualización del front-office.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Ninguno. Todo el renderizado del front-office se maneja directamente a través de hooks registrados dentro del archivo principal del módulo.
-   **Controladores de Back-Office Admin**: Ninguno. Toda la configuración del back-office se gestiona a través del método `getContent()` de la clase principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

El módulo no define clases personalizadas que extiendan `ObjectModel`. Su almacenamiento de datos principal para las configuraciones del slider probablemente se maneja a través de `Configuration::updateValue()` para la configuración a nivel de módulo y potencialmente datos serializados almacenados en `ps_configuration` para el contenido y las propiedades individuales del slider, gestionados por la biblioteca `SmartyTemplatesManager`.

### 4.4 Activos JavaScript (`views/js/`)

El módulo incluye varios archivos JavaScript, principalmente responsables de la animación deslizante y la lógica de interacción (clic/hover) para diferentes posiciones del slider.

-   `saslider/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`

    -   **Alcance**: Back-office.
    -   **Responsabilidad**: Este script forma parte de la biblioteca `SmartyTemplatesManager`. Probablemente maneja la creación, edición y gestión dinámica de plantillas (sliders) dentro de la interfaz de configuración del módulo. Podría gestionar el envío de formularios, las llamadas AJAX para guardar/cargar contenido y las interacciones de la interfaz de usuario para el sistema de gestión de plantillas.
-   `saslider/views/js/saslider-click-bottom.js`

    -   **Alcance**: Front-office.
    -   **Responsabilidad**: Implementa la lógica JavaScript para un slider posicionado en la parte inferior que se expande/contrae al hacer clic. Enlazará los oyentes de clic al elemento activador del slider, alternará las clases CSS o manipulará directamente las propiedades `style` para animar la expansión y contracción del slider.
-   `saslider/views/js/saslider-click-left.js`

    -   **Alcance**: Front-office.
    -   **Responsabilidad**: Similar a `saslider-click-bottom.js`, pero específicamente para un slider posicionado a la izquierda, manejando su expansión/contracción basada en clics.
-   `saslider/views/js/saslider-click-right.js`

    -   **Alcance**: Front-office.
    -   **Responsabilidad**: Similar a `saslider-click-bottom.js`, pero específicamente para un slider posicionado a la derecha, manejando su expansión/contracción basada en clics.
-   `saslider/views/js/saslider-hover-bottom.js`

    -   **Alcance**: Front-office.
    -   **Responsabilidad**: Implementa la lógica JavaScript para un slider posicionado en la parte inferior que se expande/contrae al pasar el ratón. Enlazará los oyentes `mouseenter` y `mouseleave` al elemento activador del slider, alternando su visibilidad y posición.
-   `saslider/views/js/saslider-hover-left.js`

    -   **Alcance**: Front-office.
    -   **Responsabilidad**: Similar a `saslider-hover-bottom.js`, pero específicamente para un slider posicionado a la izquierda, manejando su expansión/contracción basada en el paso del ratón.
-   `saslider/views/js/saslider-hover-right.js`

    -   **Alcance**: Front-office.
    -   **Responsabilidad**: Similar a `saslider-hover-bottom.js`, pero específicamente para un slider posicionado a la derecha, manejando su expansión/contracción basada en el paso del ratón.

### 4.5 Hojas de estilo CSS (`views/css/`)

El módulo incluye varios archivos CSS tanto para el estilo de configuración del back-office como para la apariencia del slider en el front-office.

-   `saslider/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`

    -   **Alcance**: Estilo del formulario de administración del back-office.
    -   **Componentes principales de la interfaz de usuario**: Estiliza los elementos de la interfaz de `SmartyTemplatesManager`, incluidos formularios, botones, campos de entrada y potencialmente tablas de lista para gestionar plantillas.
    -   **Selectores de clase CSS clave**: Probablemente incluye clases para diseños de formularios, grupos de entrada y componentes generales de la interfaz de usuario administrativa.
-   `saslider/views/css/saslider-bottom.css`

    -   **Alcance**: Estilo del cliente del front-office.
    -   **Componentes principales de la interfaz de usuario**: Define el posicionamiento específico, el estado inicial (contraído) y las propiedades de animación para el slider posicionado en la parte inferior.
    -   **Selectores de clase CSS clave**: `body #saslider_bottom`, `.saslider-bottom-tab`, `.saslider-bottom-content`, clases para los estados `open`/`closed`.
-   `saslider/views/css/saslider-left.css`

    -   **Alcance**: Estilo del cliente del front-office.
    -   **Componentes principales de la interfaz de usuario**: Define el posicionamiento específico, el estado inicial y las propiedades de animación para el slider posicionado a la izquierda.
    -   **Selectores de clase CSS clave**: `body #saslider_left`, `.saslider-left-tab`, `.saslider-left-content`, clases para los estados `open`/`closed`.
-   `saslider/views/css/saslider-right.css`

    -   **Alcance**: Estilo del cliente del front-office.
    -   **Componentes principales de la interfaz de usuario**: Define el posicionamiento específico, el estado inicial y las propiedades de animación para el slider posicionado a la derecha.
    -   **Selectores de clase CSS clave**: `body #saslider_right`, `.saslider-right-tab`, `.saslider-right-content`, clases para los estados `open`/`closed`.
-   `saslider/views/css/saslider.css`

    -   **Alcance**: Estilo del cliente del front-office.
    -   **Componentes principales de la interfaz de usuario**: Contiene estilos generales y comunes aplicables a todas las posiciones del slider, como estilos de contenedor base, tamaños de fuente, colores, z-index y propiedades de transición.
    -   **Selectores de clase CSS clave**: `.saslider-container`, `.saslider-tab`, `.saslider-content`, y potencialmente ajustes responsivos.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

El módulo utiliza plantillas Smarty tanto para su interfaz de configuración de back-office como para la renderización de contenido de front-office.

-   **Plantillas de administración (`saslider/lib/smartyTemplatesManager/views/`)**:

    -   `buttonManager.tpl`: Probablemente renderiza la interfaz de usuario para gestionar el botón/pestaña de activación del slider.
    -   `createTemplateForm.tpl`: La plantilla de formulario utilizada al crear un nuevo slider.
    -   `editTemplateForm.tpl`: La plantilla de formulario utilizada al editar un slider existente.
    -   `mainForm.tpl`: La plantilla de la página de configuración principal, que probablemente lista todos los sliders y proporciona el botón "Añadir nuevo".
    -   `selectInput.tpl`: Una plantilla reutilizable para renderizar elementos `<select>` desplegables dentro de los formularios de administración.
-   **Plantillas de hook (`saslider/views/`)**:

    -   `footer-bottom.tpl`: Renderiza la estructura HTML para un slider posicionado en la parte inferior. Esta plantilla probablemente está enganchada a `displayFooter` o un hook global similar. Contiene los `div`s envolventes para el slider, su pestaña de activación y el área de contenido.
    -   `footer-left.tpl`: Renderiza la estructura HTML para un slider posicionado a la izquierda. Probablemente enganchado a `displayFooter` o similar.
    -   `footer-right.tpl`: Renderiza la estructura HTML para un slider posicionado a la derecha. Probablemente enganchado a `displayFooter` o similar.
-   **Plantillas de ejemplo/utilidad (`saslider/lib/smartyTemplatesManager/tpl/`)**:

    -   `example.tpl`: Una plantilla de ejemplo, posiblemente para demostración o prueba interna de `SmartyTemplatesManager`.
    -   `MyShortCode.tpl`: Sugiere que `SmartyTemplatesManager` podría admitir alguna forma de shortcode o inserción de contenido dinámico.

### 4.7 Esquema de la base de datos y mapa de Hooks

-   **Tablas de la base de datos**:

    -   El módulo no define explícitamente tablas SQL personalizadas a través de `install.sql`.
    -   La configuración para sliders individuales (contenido, posición, estado activo, abrir al) se almacena en la tabla `ps_configuration`, probablemente como datos serializados bajo claves de configuración específicas gestionadas por la biblioteca `SmartyTemplatesManager`. Por ejemplo, `PS_SASLIDER_TEMPLATES` o similar.
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Se utiliza para registrar activos CSS y JavaScript (por ejemplo, `saslider.css`, `saslider-click-right.js`) necesarios para la visualización y funcionalidad del slider en el front-office. |
| `displayFooter` | Al final de la sección `<body>` de cada página, antes de la etiqueta de cierre `</body>`. | Se utiliza para renderizar la estructura HTML real del slider (por ejemplo, `footer-bottom.tpl`, `footer-left.tpl`, `footer-right.tpl`) en la página, asegurando que flote correctamente. |
| `displayLeftColumn` | En la columna izquierda de la tienda. | *Potencialmente* utilizado para renderizar el slider, aunque `displayFooter` es más común para elementos flotantes. |
| `displayRightColumn` | En la columna derecha de la tienda. | *Potencialmente* utilizado para renderizar el slider, aunque `displayFooter` es más común para elementos flotantes. |
| `displayProductAdditionalInfo` | En la página del producto, debajo de la información principal del producto. | *Potencialmente* utilizado para renderizar un slider específicamente en las páginas de productos, por ejemplo, para ofertas relacionadas. |
| `actionFrontControllerSetMedia` | Después de que un controlador frontal haya establecido sus medios, permitiendo que los módulos añadan los suyos. | Se utiliza para añadir condicionalmente archivos CSS/JS basados en la página actual u otras condiciones, asegurando una carga óptima. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Slider de contenido personalizado", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a brindar asistencia oportuna y garantizar que su módulo funcione sin problemas con su tienda PrestaShop.
