---
title: "Notas Adhesivas en el Front Office - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Notas Adhesivas en el Front Office' de MyPresta.eu."
sidebar:
  label: "Notas Adhesivas en el Front Office - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Front office Sticky Notes en MyPresta.eu](https://mypresta.eu/modules/front-office-features/front-office-sticky-notes.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/front-office-sticky-notes/)
>
> ---


# Notas Adhesivas en el Front Office

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) son típicamente requeridas para PrestaShop y suelen estar disponibles en cualquier entorno de alojamiento moderno.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" accederás a la pantalla de configuración principal del módulo Notas Adhesivas en el Front Office. Aquí es donde gestionas todas tus notas adhesivas.

La página de configuración mostrará una lista de todas las notas adhesivas que has creado. Desde aquí, puedes:

-   **Añadir Nueva Nota Adhesiva:** Haz clic en un botón (normalmente "Añadir nuevo" o un icono de más) para crear una nueva nota.
-   **Editar Nota Adhesiva Existente:** Haz clic en un icono de "Editar" junto a una nota en la lista para modificar sus ajustes.
-   **Eliminar Nota Adhesiva:** Haz clic en un icono de "Eliminar" junto a una nota para eliminarla de tu tienda.

Al añadir o editar una nota adhesiva, normalmente verás un formulario con los siguientes ajustes:

-   **Contenido de la Nota (Texto):**

    -   **Qué hace este ajuste:** Este es el mensaje o texto real que aparecerá dentro de tu nota adhesiva. Puedes usar etiquetas HTML básicas (como `<b>` para negrita, `<i>` para cursiva, `<br>` para saltos de línea o `<a>` para enlaces) para formatear tu texto e incluir enlaces clicables.
    -   **Efecto de cambiar este ajuste:** El texto que introduzcas aquí se mostrará a tus clientes.
    -   **Valor recomendado:** Mantenlo conciso e impactante. Por ejemplo, "¡Stock Limitado!", "¡Novedades!", "¡Envío Gratuito a partir de 75 $!".
    -   **Escenario / ejemplo de comerciante:** Quieres anunciar una venta flash. Introducirías: `<b>¡Venta Flash!</b> ¡20% de descuento en todos los vestidos! <a href="/20-off-dresses">¡Comprar Ahora!</a>`
-   **Color de la Nota (Color de Fondo):**

    -   **Qué hace este ajuste:** Esto te permite elegir el color de fondo de tu nota adhesiva. Normalmente se proporciona una herramienta de selección de color para facilitar la elección.
    -   **Efecto de cambiar este ajuste:** La nota adhesiva aparecerá con el color de fondo elegido. Esto es crucial para hacer que destaque o que coincida con tu marca.
    -   **Valor recomendado:** Elige un color que contraste bien con el fondo de tu tienda y el color del texto, haciendo que la nota sea fácilmente legible y visible. Los colores brillantes y cálidos (amarillo, naranja, verde claro) suelen funcionar bien para llamar la atención.
    -   **Escenario / ejemplo de comerciante:** Para un mensaje de advertencia, podrías elegir un rojo brillante o naranja. Para un anuncio general, un amarillo clásico o azul claro.
-   **Color del Texto:**

    -   **Qué hace este ajuste:** Esto establece el color del texto dentro de tu nota adhesiva.
    -   **Efecto de cambiar este ajuste:** El texto se mostrará en el color seleccionado.
    -   **Valor recomendado:** Elige siempre un color que proporcione un alto contraste con el color de fondo elegido para una legibilidad óptima. El negro o gris oscuro sobre un fondo claro, o el blanco sobre un fondo oscuro, suelen ser los mejores.
    -   **Escenario / ejemplo de comerciante:** Si el fondo de tu nota es amarillo, elegirías negro o gris oscuro para el texto. Si el fondo es azul oscuro, el texto blanco sería ideal.
-   **Posición (Coordenada X / Desplazamiento Izquierdo):**

    -   **Qué hace este ajuste:** Esto determina la posición horizontal de la nota adhesiva en la página, medida desde el borde izquierdo de la pantalla o su contenedor padre. Normalmente se especifica en píxeles (px).
    -   **Efecto de cambiar este ajuste:** Un valor más alto mueve la nota más a la derecha. Un valor más bajo la mueve más cerca de la izquierda.
    -   **Valor recomendado:** Experimenta para encontrar una posición que no obstruya el contenido importante pero que siga siendo visible. Empieza con valores como `20px` o `50px` y ajusta.
    -   **Escenario / ejemplo de comerciante:** Quieres que una nota aparezca ligeramente a la derecha de tu logotipo principal en la cabecera. Podrías establecer esto en `200px`.
-   **Posición (Coordenada Y / Desplazamiento Superior):**

    -   **Qué hace este ajuste:** Esto determina la posición vertical de la nota adhesiva en la página, medida desde el borde superior de la pantalla o su contenedor padre. Normalmente se especifica en píxeles (px).
    -   **Efecto de cambiar este ajuste:** Un valor más alto mueve la nota más abajo en la página. Un valor más bajo la mueve más cerca de la parte superior.
    -   **Valor recomendado:** Considera dónde será más efectiva la nota sin ser intrusiva. Para mensajes en la cabecera, un valor pequeño como `10px` o `20px` podría funcionar. Para notas en la página de producto, es posible que necesites desplazarte para ver el efecto.
    -   **Escenario / ejemplo de comerciante:** Quieres que una nota aparezca justo debajo de tu barra de navegación principal. Podrías establecer esto en `100px`.
-   **Ancho:**

    -   **Qué hace este ajuste:** Esto controla el ancho del contenedor de la nota adhesiva. Normalmente se especifica en píxeles (px).
    -   **Efecto de cambiar este ajuste:** Un ancho mayor permite más texto en una sola línea, mientras que un ancho menor hará que el texto se ajuste más frecuentemente.
    -   **Valor recomendado:** Elige un ancho que se ajuste cómodamente a tu mensaje sin ser excesivamente grande o demasiado estrecho. `200px` a `300px` es un rango común.
    -   **Escenario / ejemplo de comerciante:** Si tu mensaje es corto, `200px` podría ser suficiente. Si es una frase un poco más larga, `280px` podría ser mejor.
-   **Altura:**

    -   **Qué hace este ajuste:** Esto controla la altura del contenedor de la nota adhesiva. Normalmente se especifica en píxeles (px).
    -   **Efecto de cambiar este ajuste:** Una altura mayor permite más líneas de texto. Si el texto excede la altura, podría cortarse o desbordarse, dependiendo del CSS de tu tema.
    -   **Valor recomendado:** A menudo, puedes dejarlo vacío o establecerlo en `auto` si el módulo lo soporta, permitiendo que la altura se ajuste al contenido. Si necesitas un tamaño fijo, `100px` a `150px` es un rango común.
    -   **Escenario / ejemplo de comerciante:** Si tienes un mensaje de varias líneas, es posible que necesites aumentar la altura para asegurar que todo el texto sea visible.
-   **Rotación (Ángulo):**

    -   **Qué hace este ajuste:** Esto te permite rotar la nota adhesiva un cierto grado, dándole una apariencia más natural de "pegada".
    -   **Efecto de cambiar este ajuste:** La nota aparecerá inclinada según el ángulo especificado. Los valores positivos rotan en el sentido de las agujas del reloj, los valores negativos en sentido contrario.
    -   **Valor recomendado:** Pequeñas rotaciones como `3deg`, `-5deg` o `7deg` suelen verse mejor, proporcionando un efecto sutil y realista sin dificultar la lectura del texto.
    -   **Escenario / ejemplo de comerciante:** Para que una nota parezca pegada casualmente a la página, podrías establecer esto en `5deg`.
-   **Z-Index:**

    -   **Qué hace este ajuste:** Esta propiedad CSS determina el orden de apilamiento de los elementos. Un elemento con un valor `z-index` más alto se coloca delante de los elementos con valores más bajos.
    -   **Efecto de cambiar este ajuste:** Si tu nota adhesiva aparece detrás de otros elementos (como ventanas emergentes, menús o banners), aumentar su `z-index` la traerá al frente.
    -   **Valor recomendado:** Empieza con un valor relativamente alto como `999` o `9999`. Si sigue oculta, auméntalo aún más.
    -   **Escenario / ejemplo de comerciante:** Tu nota adhesiva está oculta detrás de un banner de consentimiento de cookies. Aumentarías su `Z-Index` a `9999` para asegurar que siempre esté encima.
-   **Activo / Habilitado:**

    -   **Qué hace este ajuste:** Este es un simple interruptor (Sí/No) para habilitar o deshabilitar la nota adhesiva sin eliminarla.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* La nota adhesiva será visible en tu front office según sus otros ajustes.
        -   *Cuando está deshabilitado:* La nota adhesiva estará oculta de tu front office, pero su configuración se guardará, permitiéndote reactivarla más tarde.
    -   **Valor recomendado:** "Sí" cuando quieras que la nota sea visible; "No" cuando quieras ocultarla temporalmente.
    -   **Escenario / ejemplo de comerciante:** Tienes una nota de promoción de temporada. Puedes deshabilitarla después de que termine la temporada y volver a habilitarla el próximo año sin recrearla.

#### 2.1.1 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Contenido de la Nota (Texto) | Varía | El mensaje que se muestra en la nota adhesiva. Soporta HTML básico. |
| Configuración del Módulo | Color de la Nota (Fondo) | Varía (ej., Amarillo) | Establece el color de fondo de la nota. Elige para el contraste. |
| Configuración del Módulo | Color del Texto | Varía (ej., Negro) | Establece el color del texto. Asegura un alto contraste con el fondo. |
| Configuración del Módulo | Posición (Coordenada X) | Varía (ej., 50px) | Posición horizontal desde la izquierda. Ajusta para la colocación. |
| Configuración del Módulo | Posición (Coordenada Y) | Varía (ej., 50px) | Posición vertical desde la parte superior. Ajusta para la colocación. |
| Configuración del Módulo | Ancho | Varía (ej., 250px) | Ancho de la nota adhesiva. Afecta el ajuste del texto. |
| Configuración del Módulo | Altura | Varía (ej., auto o 120px) | Altura de la nota adhesiva. Afecta la visibilidad del contenido. |
| Configuración del Módulo | Rotación (Ángulo) | Varía (ej., 5deg) | Inclina la nota para un efecto "pegado" realista. |
| Configuración del Módulo | Z-Index | Varía (ej., 9999) | Orden de apilamiento. Los valores más altos aparecen encima de otros elementos. |
| Configuración del Módulo | Activo / Habilitado | Sí | Alterna la visibilidad de la nota adhesiva en el front office. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P: Mi nota adhesiva no aparece en el front office.**
R:

1.  **Verifica el estado "Activo":** Ve a la configuración del módulo y asegúrate de que el interruptor "Activo" para esa nota específica esté en "Sí".
2.  **Borrar Caché:** PrestaShop a menudo almacena contenido en caché. Ve a **Parámetros Avanzados > Rendimiento** y haz clic en "Borrar caché".
3.  **Z-Index:** Si el `Z-Index` de la nota es demasiado bajo, podría estar oculta detrás de otros elementos. Intenta aumentar el valor del `Z-Index` (por ejemplo, a `9999`).
4.  **Posicionamiento:** Vuelve a verificar las coordenadas X e Y. Si son muy altas, la nota podría estar fuera de la pantalla. Intenta establecer valores pequeños como `10px` para ambos para ver si aparece.
5.  **Instalación del Módulo:** Asegúrate de que el módulo esté correctamente instalado y habilitado en **Módulos > Gestor de Módulos**.

**P: El texto de mi nota adhesiva está cortado o se desborda.**
R:

1.  **Ajusta Ancho/Altura:** Aumenta los ajustes de "Ancho" y/o "Altura" para esa nota adhesiva específica en la configuración del módulo.
2.  **Verifica HTML:** Si estás usando HTML, asegúrate de que todas las etiquetas estén correctamente cerradas (por ejemplo, `<b>` tiene su correspondiente `</b>`). Un HTML incorrecto a veces puede romper la renderización.

**P: La nota adhesiva se ve diferente en el móvil que en el escritorio.**
R: El módulo busca la capacidad de respuesta, pero la ubicación exacta puede variar debido a los diferentes tamaños de pantalla y al CSS de tu tema.

1.  **Prueba en el Dispositivo:** Siempre prueba la apariencia de la nota en dispositivos móviles reales o utiliza las herramientas de desarrollador de tu navegador (F12) para simular vistas móviles.
2.  **Ajusta el Posicionamiento:** Es posible que necesites ajustar las coordenadas X e Y para una colocación específica en móviles, aunque el módulo podría no ofrecer ajustes móviles separados. Si es un problema importante, considera si la nota es realmente esencial en el móvil o si se necesita un enfoque diferente.
3.  **Conflictos de Tema:** Ocasionalmente, el CSS de tu tema podría entrar en conflicto. Si sospechas esto, contacta con el soporte de MyPresta.eu con los detalles de tu tema.

**P: ¿Cómo hago que el texto sea un enlace?**
R: Puedes usar etiquetas de anclaje HTML estándar dentro del campo "Contenido de la Nota".
Ejemplo: `<a href="https://tutienda.com/nuevos-productos">¡Haz clic aquí para Novedades!</a>`
Recuerda incluir la URL completa, incluyendo `https://`.

**P: ¿Puedo tener diferentes notas adhesivas para diferentes idiomas?**
R: Sí, el módulo es compatible con las funciones multilingües de PrestaShop. Al editar una nota adhesiva, deberías ver pestañas de idioma junto al campo "Contenido de la Nota" (y potencialmente otros campos basados en texto). Selecciona la pestaña de idioma deseada e introduce el contenido traducido para esa nota.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una visión técnica para desarrolladores y webmasters que buscan comprender, personalizar o depurar el módulo "Notas Adhesivas en el Front Office".

### 4.1 Visión General de la Arquitectura

El módulo "Notas Adhesivas en el Front Office" sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente la clase `Module` para su funcionalidad principal y `ModuleFrontController` para las interacciones AJAX. Almacena los datos de configuración directamente en `ps_configuration` y renderiza su contenido a través de una plantilla Smarty enganchada en el front office. El módulo utiliza JavaScript del lado del cliente para un comportamiento dinámico y un archivo CSS dedicado para el estilo.

### 4.2 Controladores (`controllers/`)

El módulo utiliza controladores frontales para manejar las solicitudes AJAX relacionadas con la gestión de notas adhesivas (añadir, editar, eliminar). Estos no son controladores de página completa, sino puntos finales para interacciones dinámicas.

-   **Controladores del Front Office**:

    -   `controllers/front/add.php`
        -   **Nombre de la Clase y Clase Padre**: `StickynotesfoAddModuleFrontController` que extiende `ModuleFrontController`
        -   **Responsabilidad**: Maneja las solicitudes AJAX para añadir una nueva nota adhesiva. Probablemente recibe datos POST que contienen el contenido de la nota, posición, colores, etc., los valida y los guarda en la base de datos (a través de la clase `Configuration` o un `ObjectModel` personalizado si existiera). Devuelve una respuesta JSON que indica éxito o fracaso.
    -   `controllers/front/delete.php`
        -   **Nombre de la Clase y Clase Padre**: `StickynotesfoDeleteModuleFrontController` que extiende `ModuleFrontController`
        -   **Responsabilidad**: Maneja las solicitudes AJAX para eliminar una nota adhesiva existente. Espera un identificador (por ejemplo, `id_note`) en la solicitud, elimina los datos correspondientes de la base de datos y devuelve una respuesta JSON.
    -   `controllers/front/edit.php`
        -   **Nombre de la Clase y Clase Padre**: `StickynotesfoEditModuleFrontController` que extiende `ModuleFrontController`
        -   **Responsabilidad**: Maneja las solicitudes AJAX para actualizar una nota adhesiva existente. Recibe datos POST con el ID de la nota y las propiedades actualizadas, modifica el registro de la base de datos y devuelve una respuesta JSON.
    -   `controllers/front/index.php`
        -   **Nombre de la Clase y Clase Padre**: `StickynotesfoIndexModuleFrontController` que extiende `ModuleFrontController`
        -   **Responsabilidad**: Este controlador podría servir como un punto de entrada general para solicitudes AJAX o podría ser un respaldo. Dados los controladores específicos `add`, `delete`, `edit`, `index.php` podría manejar la lista de notas u otras interacciones generales no cubiertas por las operaciones CRUD específicas.
-   **Controladores de Administración del Back Office**: Ninguno detectado. Toda la configuración del back office se maneja dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

No se detectaron definiciones de `classes/` o `ObjectModel` personalizadas. El módulo probablemente almacena su configuración directamente en la tabla `ps_configuration` de PrestaShop, utilizando claves únicas para las propiedades de cada nota adhesiva. Este enfoque es común para módulos más simples que gestionan un número limitado de configuraciones.

### 4.4 Activos JavaScript (`views/js/`)

-   `js/advajax.js`
    -   **Alcance**: Probablemente Front office.
    -   **Descripción**: Este archivo sugiere un script de utilidad AJAX personalizado o de terceros. Probablemente proporciona funciones de ayuda para realizar solicitudes asíncronas a los controladores frontales del módulo (`add.php`, `delete.php`, `edit.php`). Podría encapsular patrones AJAX comunes, manejo de errores o serialización de datos. Los desarrolladores deben revisar este archivo para comprender cómo se estructuran e inician las llamadas AJAX dentro del módulo.
-   `js/jscolor/jscolor.js`
    -   **Alcance**: Back office (para configuración).
    -   **Descripción**: Esta es una biblioteca JavaScript de terceros para un selector de color. Se utiliza en el formulario de configuración del back office del módulo para proporcionar una interfaz fácil de usar para seleccionar los colores de la nota y del texto. Se vincula a campos de entrada de una clase o ID específica, transformándolos en herramientas interactivas de selección de color.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   `css/stickynotes.css`
    -   **Alcance**: Estilo del cliente del Front office.
    -   **Descripción**: Esta es la hoja de estilo principal para las notas adhesivas que se muestran en el front office. Define la apariencia visual de las notas, incluyendo:
        -   Estilo base para el contenedor de la nota adhesiva (por ejemplo, `position: absolute;`, `background-color`, `border-radius`).
        -   Estilo del texto dentro de la nota (`font-size`, `color`, `line-height`).
        -   El efecto "despegado" o rotado (probablemente usando `transform: rotate()`).
        -   `z-index` para asegurar la visibilidad.
        -   Posibles ajustes responsivos para diferentes tamaños de pantalla usando media queries.
    -   **Selectores de clase CSS clave que los desarrolladores pueden sobrescribir**: Los desarrolladores deben inspeccionar el HTML renderizado para identificar la clase del contenedor principal (por ejemplo, `.sticky-note`, `.stickynotesfo-item`) y sus elementos hijos para aplicar estilos personalizados en el `custom.css` o `theme.css` de su tema.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/front/`)**:
    -   `views/templates/front/sticky-notes-front-office.tpl`
        -   **Hook**: Esta plantilla probablemente se renderiza en un hook general del front office como `displayHeader`, `displayFooter` o potencialmente `displayBeforeBodyClosingTag`. El método `hookDisplayHeader` o `hookDisplayFooter` del módulo normalmente recuperaría todas las notas adhesivas activas de la base de datos y las asignaría a esta plantilla.
        -   **Salida de Bloque Visual**: Esta plantilla es responsable de iterar a través de la lista de notas adhesivas activas y renderizar la estructura HTML para cada una. Insertará dinámicamente el contenido de la nota, colores, posiciones, ancho, alto, rotación y `z-index` como estilos en línea o atributos de datos, que luego son recogidos por `stickynotes.css` y potencialmente `advajax.js` para actualizaciones dinámicas. Cada nota probablemente será un elemento `div` con IDs o clases únicas.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:

    -   El módulo no crea tablas SQL personalizadas. En su lugar, almacena sus datos de configuración en la tabla `ps_configuration` de PrestaShop. Las propiedades de cada nota adhesiva (contenido, color, posición, etc.) se almacenan como claves de configuración individuales, probablemente con el prefijo `STICKYNOTESFO_NOTE_` seguido de un identificador único (por ejemplo, `STICKYNOTESFO_NOTE_1_CONTENT`, `STICKYNOTESFO_NOTE_1_COLOR`). Los campos multilingües usarían sufijos `_LANG_ID`.
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Se ejecuta al final de la sección `<head>` de cada página del front office. | Ideal para inyectar CSS, JavaScript y, potencialmente, la estructura HTML inicial de las notas adhesivas, asegurando que estén disponibles temprano en el DOM. |
| `displayFooter` | Se ejecuta al final de la sección `<body>` de cada página del front office. | Puede usarse para inyectar el HTML de las notas adhesivas, especialmente si están destinadas a flotar o posicionarse absolutamente en relación con la ventana gráfica. |
| `displayLeftColumn` | Se ejecuta dentro de la columna izquierda de las páginas que la tienen. | Permite la colocación de notas adhesivas específicamente dentro de la barra lateral izquierda. |
| `displayRightColumn` | Se ejecuta dentro de la columna derecha de las páginas que la tienen. | Permite la colocación de notas adhesivas específicamente dentro de la barra lateral derecha. |
| `displayProductAdditionalInfo` (o hook similar de página de producto) | Se ejecuta en la página del producto, típicamente cerca de la descripción del producto o del botón de añadir al carrito. | Permite la colocación de notas adhesivas específicas para páginas de productos individuales. |
| `actionFrontControllerSetMedia` | Se ejecuta cuando un controlador frontal está configurando sus medios (CSS/JS). | Utilizado por el módulo para registrar sus archivos `stickynotes.css` y `advajax.js` para la visualización en el front office. |
| `actionAdminControllerSetMedia` | Se ejecuta cuando un controlador de administración está configurando sus medios (CSS/JS). | Utilizado por el módulo para registrar `jscolor.js` y cualquier otro CSS/JS específico de administración para su página de configuración. |

## 5. Soporte Oficial y Actualizaciones

Para actualizaciones oficiales, soporte técnico y cualquier asistencia adicional con el módulo "Notas Adhesivas en el Front Office", consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a proporcionar soporte oportuno y asegurar que tu módulo funcione de manera óptima.
