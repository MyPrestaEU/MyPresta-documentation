---
title: "Ventana emergente de página de producto - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Ventana emergente de página de producto' de MyPresta.eu."
sidebar:
  label: "Ventana emergente de página de producto - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Product page popup en MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-popup.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/product-page-popup/)
>
> ---


# Ventana emergente de página de producto

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor.

## 2. Recorrido completo por la configuración (cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, será dirigido a la página de configuración principal del módulo. Aquí puede gestionar todas sus ventanas emergentes de página de producto.

La página de configuración se divide en dos secciones principales:

1.  Pestaña **"Añadir nueva ventana emergente"**: Para crear nuevas ventanas emergentes.
2.  Pestaña **"Lista de ventanas emergentes"**: Para ver, editar o eliminar ventanas emergentes existentes.

#### 2.1.1 Pestaña "Añadir nueva ventana emergente"

Esta pestaña le permite definir una nueva ventana emergente y sus ajustes asociados.

-   **Nombre de la ventana emergente:**

    -   **Qué hace este ajuste:** Este es un nombre interno para su ventana emergente, visible solo en su back office de PrestaShop. Le ayuda a identificar y gestionar diferentes ventanas emergentes.
    -   **Efecto de cambiar este ajuste:** Cambiar este nombre solo afecta cómo lo ve en el back office; no tiene impacto en el front office o la experiencia del cliente.
    -   **Valor recomendado:** Use un nombre descriptivo, por ejemplo, "Oferta de verano en camisetas", "Guía de tallas para vaqueros", "Tutorial en video para el producto X".
    -   **Escenario / ejemplo de comerciante:** Si tiene una ventana emergente para un producto específico, nómbrela según ese producto para encontrarla fácilmente más tarde.
-   **Contenido de la ventana emergente:**

    -   **Qué hace este ajuste:** Este es el contenido principal que se mostrará dentro de la ventana emergente. Es un editor de texto enriquecido (TinyMCE) donde puede añadir texto, imágenes, videos, enlaces e incluso HTML personalizado.
    -   **Efecto de cambiar este ajuste:** Esto cambia directamente lo que ven sus clientes cuando aparece la ventana emergente. Puede hacerlo informativo, promocional o interactivo.
    -   **Valor recomendado:** Manténgalo conciso y visualmente atractivo. Use encabezados, viñetas e imágenes relevantes.
    -   **Escenario / ejemplo de comerciante:** Podría añadir un código de descuento, un video de YouTube incrustado que demuestre el producto o una tabla de tallas detallada.
-   **Ancho de la ventana emergente (px):**

    -   **Qué hace este ajuste:** Define el ancho de la ventana emergente en píxeles.
    -   **Efecto de cambiar este ajuste:** Un ancho mayor hará que la ventana emergente sea más ancha, pudiendo acomodar más contenido horizontalmente. Un ancho menor la hará más estrecha.
    -   **Valor recomendado:** Empiece con `600px` y ajuste según su contenido. Asegúrese de que se vea bien en varios tamaños de pantalla.
    -   **Escenario / ejemplo de comerciante:** Si su ventana emergente contiene una imagen ancha o una tabla, es posible que necesite un ancho mayor. Para texto simple, un ancho más estrecho podría ser suficiente.
-   **Altura de la ventana emergente (px):**

    -   **Qué hace este ajuste:** Define la altura de la ventana emergente en píxeles.
    -   **Efecto de cambiar este ajuste:** Una altura mayor hará que la ventana emergente sea más alta, permitiendo más contenido vertical sin desplazamiento. Una altura menor la hará más corta, lo que podría requerir desplazamiento si el contenido excede la altura.
    -   **Valor recomendado:** Empiece con `400px` y ajuste según su contenido.
    -   **Escenario / ejemplo de comerciante:** Si tiene una descripción de texto larga o una imagen alta, aumente la altura. Si el contenido es corto, una altura menor se ve más limpia.
-   **Color de fondo de la ventana emergente:**

    -   **Qué hace este ajuste:** Le permite elegir el color de fondo de la propia ventana emergente. Esto utiliza una herramienta de selección de color.
    -   **Efecto de cambiar este ajuste:** Cambia la apariencia visual de la ventana emergente, ayudándola a coincidir con la marca de su tienda o a destacarse.
    -   **Valor recomendado:** Elija un color que complemente el diseño de su tienda y garantice una buena legibilidad de su contenido.
    -   **Escenario / ejemplo de comerciante:** Use el color principal de su marca para el fondo, o un blanco/gris claro neutro para una máxima legibilidad.
-   **Color del borde de la ventana emergente:**

    -   **Qué hace este ajuste:** Le permite elegir el color del borde alrededor de la ventana emergente.
    -   **Efecto de cambiar este ajuste:** Añade un marco visual a la ventana emergente, definiendo sus bordes.
    -   **Valor recomendado:** A menudo, un color de borde sutil que coincida con la estética de su tienda o un color contrastante para hacer que la ventana emergente destaque.
    -   **Escenario / ejemplo de comerciante:** Un borde gris claro para un aspecto limpio, o un color vibrante si la ventana emergente está destinada a llamar mucho la atención.
-   **Ancho del borde de la ventana emergente (px):**

    -   **Qué hace este ajuste:** Define el grosor del borde de la ventana emergente en píxeles.
    -   **Efecto de cambiar este ajuste:** Un valor más alto hace que el borde sea más grueso y prominente.
    -   **Valor recomendado:** `1px` o `2px` para un borde sutil.
    -   **Escenario / ejemplo de comerciante:** Un borde de `5px` podría usarse para un mensaje muy audaz y urgente, mientras que `1px` es más común para información general.
-   **Radio del borde de la ventana emergente (px):**

    -   **Qué hace este ajuste:** Controla la redondez de las esquinas de la ventana emergente. Un valor de `0` significa esquinas afiladas y cuadradas. Valores más altos crean esquinas más redondeadas.
    -   **Efecto de cambiar este ajuste:** Afecta la estética general de la ventana emergente, haciéndola parecer más suave o más moderna.
    -   **Valor recomendado:** `0px` para esquinas afiladas, `5px` a `10px` para esquinas ligeramente redondeadas.
    -   **Escenario / ejemplo de comerciante:** Si el diseño de su tienda utiliza elementos redondeados, un radio de borde de `10px` haría que la ventana emergente encajara mejor.
-   **Color de la superposición de la ventana emergente:**

    -   **Qué hace este ajuste:** Este es el color de la capa semitransparente que aparece detrás de la ventana emergente, atenuando el resto de la página del producto.
    -   **Efecto de cambiar este ajuste:** Cambia el contraste visual entre la ventana emergente y el fondo. Una superposición más oscura hace que la ventana emergente destaque más.
    -   **Valor recomendado:** Un negro semitransparente (`#000000` con cierta transparencia) es estándar.
    -   **Escenario / ejemplo de comerciante:** Una superposición ligeramente más clara podría usarse si desea que la información del producto de fondo siga siendo algo visible.
-   **Opacidad de la superposición de la ventana emergente (0-100):**

    -   **Qué hace este ajuste:** Controla la transparencia del color de la superposición. `0` es totalmente transparente (invisible), `100` es totalmente opaco (color sólido, oculta completamente el fondo).
    -   **Efecto de cambiar este ajuste:** Determina cuánto de la página del producto subyacente es visible a través de la superposición.
    -   **Valor recomendado:** `70` a `80` es un buen equilibrio, haciendo que la ventana emergente sea prominente sin oscurecer completamente la página.
    -   **Escenario / ejemplo de comerciante:** Si desea que el cliente aún vea débilmente la imagen del producto detrás de la ventana emergente, use una opacidad más baja como `50`.
-   **Productos para esta ventana emergente:**

    -   **Qué hace este ajuste:** Esta es la parte crucial donde selecciona qué productos específicos activarán esta ventana emergente. Puede buscar productos por nombre.
    -   **Efecto de cambiar este ajuste:** La ventana emergente *solo* aparecerá en las páginas de productos que seleccione aquí. Si no se selecciona ningún producto, la ventana emergente no aparecerá en ningún lugar.
    -   **Valor recomendado:** Seleccione todos los productos relevantes para este mensaje específico.
    -   **Escenario / ejemplo de comerciante:** Si ha creado una ventana emergente con una guía de tallas para "Camisetas de hombre", seleccionaría todos sus productos de camisetas de hombre aquí.

Después de configurar todos los ajustes, haga clic en el botón **"Guardar"** para crear su nueva ventana emergente.

#### 2.1.2 Pestaña "Lista de ventanas emergentes"

Esta pestaña muestra una tabla de todas las ventanas emergentes que ha creado.

-   **Columnas de la tabla:**
    -   **ID:** Identificador único para la ventana emergente.
    -   **Nombre:** El nombre interno que le dio a la ventana emergente.
    -   **Productos:** Enumera el número de productos asociados con esta ventana emergente.
    -   **Acciones:**
        -   **Editar:** Haga clic en el icono del lápiz para volver a la pestaña "Añadir nueva ventana emergente" con todos los ajustes de la ventana emergente actual precargados, lo que le permite modificarlos.
        -   **Eliminar:** Haga clic en el icono de la papelera para eliminar permanentemente la ventana emergente. Aparecerá un mensaje de confirmación.
-   **Efecto de los cambios:**
    -   **Edición:** Le permite actualizar el contenido, el estilo o las asociaciones de productos para una ventana emergente existente sin crear una nueva.
    -   **Eliminación:** Elimina permanentemente la ventana emergente de su tienda. Ya no aparecerá en ninguna página de producto.
-   **Flujo de trabajo recomendado:** Revise regularmente esta lista para asegurarse de que todas sus ventanas emergentes estén actualizadas y sean relevantes. Elimine cualquier promoción o información obsoleta.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| **Añadir nueva ventana emergente** | Nombre de la ventana emergente | Nombre descriptivo | Identificación interna para el back office. |
| | Contenido de la ventana emergente | HTML/Texto personalizado | Mensaje principal mostrado al cliente. |
| | Ancho de la ventana emergente (px) | 600px | Tamaño horizontal de la ventana emergente. |
| | Altura de la ventana emergente (px) | 400px | Tamaño vertical de la ventana emergente. |
| | Color de fondo de la ventana emergente | Blanco / Color de marca | Color de fondo del área de contenido de la ventana emergente. |
| | Color del borde de la ventana emergente | Sutil / Color de marca | Color del marco alrededor de la ventana emergente. |
| | Ancho del borde de la ventana emergente (px) | 1px - 2px | Grosor del borde de la ventana emergente. |
| | Radio del borde de la ventana emergente (px) | 0px - 10px | Redondez de las esquinas de la ventana emergente. |
| | Color de la superposición de la ventana emergente | Negro semitransparente | Color del fondo atenuado. |
| | Opacidad de la superposición de la ventana emergente (0-100) | 70 - 80 | Transparencia de la superposición de fondo. |
| | Productos para esta ventana emergente | Seleccionar productos relevantes | Determina en qué páginas de producto aparece la ventana emergente. |
| **Lista de ventanas emergentes** | Acción de edición | N/A | Modificar los ajustes de una ventana emergente existente. |
| | Acción de eliminación | N/A | Eliminar una ventana emergente permanentemente. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Mi ventana emergente no aparece en la página del producto. ¿Qué debo verificar?**
R:

1.  **¿Está la ventana emergente asociada con el producto correcto?** Vaya a la configuración del módulo, edite su ventana emergente y asegúrese de que el producto específico en el que está probando esté seleccionado en el campo "Productos para esta ventana emergente".
2.  **¿Está el módulo habilitado?** En **Módulos > Gestor de módulos**, asegúrese de que "Ventana emergente de página de producto" esté instalado y habilitado.
3.  **Borre la caché de su PrestaShop:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). Es posible que también deba borrar la caché de su navegador (Ctrl+F5 o Cmd+R).
4.  **Verifique si hay errores de JavaScript:** Abra la consola de desarrollador de su navegador (F12) y busque cualquier error en la pestaña "Consola". Si ve errores, podría indicar un conflicto con otro módulo o su tema.

**P: La ventana emergente se ve extraña o no coincide con el estilo de mi tema.**
R:

1.  **Revise la configuración de estilo de la ventana emergente:** Vuelva a verificar los ajustes "Color de fondo de la ventana emergente", "Color del borde de la ventana emergente", "Ancho del borde de la ventana emergente" y "Radio del borde de la ventana emergente" en la configuración del módulo.
2.  **Conflictos de tema:** El CSS de su tema podría estar anulando los estilos del módulo. Si se siente cómodo con CSS, puede inspeccionar los elementos de la ventana emergente utilizando las herramientas de desarrollador de su navegador para identificar estilos en conflicto. Para problemas de estilo complejos, es posible que necesite la ayuda de un desarrollador web.

**P: ¿Puedo tener varias ventanas emergentes en la misma página de producto?**
R: No, el módulo está diseñado para mostrar una ventana emergente específica por página de producto. Si un producto está asociado con varias ventanas emergentes, solo se mostrará una (normalmente la primera que se encuentre o la que tenga el ID más bajo, aunque este comportamiento no está explícitamente garantizado y debe evitarse). La mejor práctica es crear una ventana emergente completa por producto o grupo de productos.

**P: ¿Cómo traduzco el contenido de la ventana emergente a diferentes idiomas?**
R: El campo "Contenido de la ventana emergente" en la configuración del módulo debería ofrecer pestañas de idioma si su tienda PrestaShop tiene varios idiomas habilitados. Simplemente cambie a la pestaña del idioma deseado e introduzca el contenido traducido para ese idioma.

**P: El contenido de la ventana emergente es demasiado largo y requiere desplazamiento. ¿Cómo puedo solucionar esto?**
R:

1.  **Aumente la altura de la ventana emergente:** En la configuración del módulo, aumente el valor de "Altura de la ventana emergente (px)".
2.  **Condense el contenido:** Intente que el contenido de su ventana emergente sea más conciso. Use viñetas, párrafos más cortos y enlace a páginas externas para información muy detallada si es posible.
3.  **Optimice imágenes/videos:** Asegúrese de que cualquier medio en su ventana emergente esté optimizado para uso web para evitar tiempos de carga excesivos y mejorar la visualización.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo `Ventana emergente de página de producto` para PrestaShop 1.5.x y 1.6.x sigue un patrón de diseño monolítico y directo, típico de los módulos de PrestaShop más antiguos. Utiliza principalmente la clase `Module` para su funcionalidad principal, gestionando la instalación, desinstalación y configuración. La visualización en el front-office se gestiona mediante la conexión a puntos de visualización estándar, mientras que la configuración se maneja a través del método `getContent()` dentro del archivo principal del módulo. Los datos se almacenan directamente en `ps_configuration` y se gestionan a través de interacciones estándar de la base de datos de PrestaShop. No hay clases `ObjectModel` personalizadas ni controladores dedicados de front/admin más allá del archivo principal del módulo.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores dedicados de front-office o back-office en el directorio `controllers/`. Toda la lógica del front-office se maneja directamente dentro del archivo principal del módulo a través de hooks, y toda la configuración del back-office se gestiona mediante el método `getContent()` de la clase principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no contiene ninguna clase o modelo PHP personalizado en el directorio `classes/`. Todo el manejo de datos y la lógica de negocio están encapsulados dentro del archivo principal del módulo `ajax_productpopup.php`.

### 4.4 Activos JavaScript (`views/js/`)

-   **`productpopup/js/jscolor/jscolor.js`**
    -   **Alcance:** Back-office.
    -   **Descripción:** Esta es una biblioteca JavaScript de terceros para proporcionar una funcionalidad de selector de color. Se utiliza en el formulario de configuración del módulo para permitir a los comerciantes seleccionar fácilmente colores para el fondo, el borde y la superposición de la ventana emergente. Normalmente funciona adjuntándose a campos de entrada con una clase específica (por ejemplo, `jscolor`).
-   **`productpopup/js/script.js`**
    -   **Alcance:** Front-office.
    -   **Descripción:** Este script contiene la lógica central para mostrar la ventana emergente en el front office.
        -   **Detectores de eventos:** Probablemente escucha el evento `DOMContentLoaded` o similar para asegurarse de que la página esté completamente cargada.
        -   **Manipulación del DOM:** Es responsable de:
            -   Comprobar si el ID del producto actual tiene una ventana emergente asociada.
            -   Crear dinámicamente la estructura HTML de la ventana emergente (superposición, contenedor de la ventana emergente, área de contenido, botón de cierre).
            -   Inyectar el contenido de la ventana emergente (recuperado de la configuración del módulo).
            -   Aplicar los estilos configurados (ancho, alto, colores, borde, opacidad).
            -   Mostrar la ventana emergente con una animación (por ejemplo, fundido de entrada).
            -   Vincular eventos para cerrar la ventana emergente (clic en el botón de cierre, clic en la superposición, pulsación de la tecla ESC).
-   **`productpopup/js/tinymce16.inc.js`**
    -   **Alcance:** Back-office.
    -   **Descripción:** Este archivo es un script de integración para el editor de texto enriquecido TinyMCE, específicamente adaptado para entornos PrestaShop 1.6.x. Inicializa el editor TinyMCE para el área de texto "Contenido de la ventana emergente" en el formulario de configuración del módulo, proporcionando al comerciante una interfaz WYSIWYG para crear contenido HTML enriquecido para las ventanas emergentes. Configura las opciones de TinyMCE, como los botones disponibles, los complementos y la configuración de idioma.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   **`productpopup/css/productpopup.css`**
    -   **Alcance:** Front-office.
    -   **Descripción:** Esta hoja de estilo define la apariencia visual y el diseño predeterminados de la ventana emergente de la página del producto y su superposición.
        -   **Componentes principales de la interfaz de usuario:** Estilos para `.productpopup-overlay` (el fondo atenuado) y `.productpopup-container` (el cuadro real de la ventana emergente).
        -   **Selectores de clase CSS clave:**
            -   `.productpopup-overlay`: Controla `position`, `top`, `left`, `width`, `height`, `background-color`, `opacity`, `z-index`.
            -   `.productpopup-container`: Controla `position`, `top`, `left`, `transform` (para centrar), `background-color`, `border`, `border-radius`, `box-shadow`, `z-index`, `overflow`.
            -   `.productpopup-content`: Estilos para el área de contenido interior, incluyendo `padding`, `font-size`, `line-height`.
            -   `.productpopup-close`: Estilos para el botón de cierre (por ejemplo, `position`, `top`, `right`, `font-size`, `color`, `cursor`).
        -   **Anulación del desarrollador:** Los desarrolladores pueden anular estos estilos en el `global.css` de su tema o creando una hoja de estilo personalizada cargada después de esta, apuntando a estas clases específicas.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**: Este módulo no define explícitamente plantillas para hooks específicos en este directorio. El HTML de la ventana emergente del front-office probablemente se genera dinámicamente por `script.js` basándose en la configuración.
-   **Plantillas de administración (`views/templates/admin/`)**:
    -   **`productpopup/views/templates/admin/tabs-no-product.tpl`**
        -   **Descripción:** Esta plantilla probablemente se utiliza dentro del método `getContent()` del módulo para renderizar el formulario "Añadir nueva ventana emergente" cuando no se está editando ninguna ventana emergente específica, o quizás una versión simplificada del formulario. Contiene los campos de entrada para el nombre de la ventana emergente, el contenido, las dimensiones, los colores y la interfaz de selección de productos.
    -   **`productpopup/views/templates/admin/tabs.tpl`**
        -   **Descripción:** Esta es la plantilla principal para la página de configuración del back-office del módulo. Normalmente renderiza la estructura de pestañas (por ejemplo, "Añadir nueva ventana emergente" y "Lista de ventanas emergentes") e incluye el contenido de otras plantillas de administración (como `tabs-no-product.tpl`) dentro de sus paneles de pestañas. También renderiza la tabla para listar las ventanas emergentes existentes.
-   **Plantillas de front-office (`views/templates/front/`)**:
    -   **`productpopup/views/templates/front/footer.tpl`**
        -   **Descripción:** Esta plantilla probablemente se utiliza para generar un pequeño contenedor HTML oculto o una variable JavaScript que contiene los datos de la ventana emergente (contenido, estilos, ID de productos) para que `script.js` del front-office los recoja y renderice la ventana emergente dinámicamente. Normalmente se engancha a `displayFooter` o `displayHeader` para garantizar que los datos estén disponibles en cada carga de página.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:

    -   Este módulo no crea tablas SQL personalizadas. Todas las configuraciones y datos de las ventanas emergentes se almacenan en la tabla de configuración estándar de PrestaShop: `ps_configuration`.
    -   **Claves de configuración**:
        -   `PRODUCTPOPUP_DATA`: Almacena datos serializados para todas las ventanas emergentes creadas, incluyendo su contenido, estilo e IDs de productos asociados. Esta clave contiene una estructura de array compleja.
        -   Podrían existir otras claves para la configuración global del módulo, si las hubiera, pero los datos principales están en `PRODUCTPOPUP_DATA`.
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | Se ejecuta en la sección `<head>` de cada página. | Probablemente se usa para incluir archivos CSS y JavaScript (`productpopup.css`, `script.js`) para la funcionalidad de la ventana emergente del front-office. |
| `displayFooter` | Se ejecuta al final de la sección `<body>` de cada página. | Podría usarse para generar los datos ocultos para `script.js` o para asegurar que la estructura HTML de la ventana emergente se añada al DOM después de todo el demás contenido. |
| `displayProductTab` (PrestaShop 1.6.x) / `displayProductExtraContent` (PrestaShop 1.7+) | Se ejecuta en la página del producto, típicamente dentro de las pestañas del producto o el área de contenido extra. | Aunque la descripción del módulo implica un modal, podría usar este hook para inyectar un disparador para la ventana emergente, o para asegurar que su JS se cargue específicamente en las páginas de producto. |
| `displayRightColumn` / `displayLeftColumn` | Se ejecuta en las columnas laterales de la tienda. | Menos probable para una ventana emergente de página de producto, pero podría usarse para inyectar un disparador global o un pequeño script si fuera necesario. |
| `actionProductUpdate` / `actionProductAdd` / `actionProductDelete` | Se ejecuta cuando se añade, actualiza o elimina un producto. | Podría usarse para actualizar o limpiar los `PRODUCTPOPUP_DATA` en `ps_configuration` si se elimina un producto asociado a una ventana emergente. |

## 5. Soporte oficial y actualizaciones

Para actualizaciones oficiales, correcciones de errores y soporte técnico dedicado, consulte su cuenta de cliente en MyPresta.eu. Asegúrese de descargar la última versión del módulo "Ventana emergente de página de producto" compatible con su instalación de PrestaShop. Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta relacionada con la funcionalidad e integración del módulo.
