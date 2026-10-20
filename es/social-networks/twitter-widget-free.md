---
title: "Twitter widget free - Manual para el Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Twitter widget free para PrestaShop de MyPresta.eu."
sidebar:
  label: "Twitter widget free - Manual para el Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Twitter widget free en MyPresta.eu](https://mypresta.eu/modules/social-networks/twitter-widget-free.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/twitter-widget-free/)
>
> ---


# Twitter widget free

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No hay requisitos especiales más allá de un entorno de alojamiento estándar de PrestaShop.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal y única para el módulo "Twitter widget free". Aquí definirá cómo aparece y funciona su línea de tiempo de Twitter en su tienda.

| Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- |
| **Nombre de usuario de Twitter** | `mypresta` (ejemplo) | **Qué hace este ajuste:** Este es el ajuste más crucial. Especifica la cuenta de Twitter (X) cuyos tweets públicos se mostrarán. Debe introducir el nombre de usuario de su cuenta (por ejemplo, `mypresta`, `elnombredesutienda`).   **Efecto de cambiar este ajuste:**   *Cuando se establece con su nombre de usuario:* El widget buscará y mostrará tweets de su cuenta especificada.   *Cuando se deja vacío o es incorrecto:* El widget no mostrará ningún tweet o mostrará un mensaje de error, ya que no sabrá de qué cuenta extraer datos.   **Valor recomendado:** Su nombre de usuario oficial de Twitter (X), sin el símbolo "@".   **Escenario / ejemplo de comerciante:** Si su identificador de Twitter es `@MiTiendaGenial`, introduciría `MiTiendaGenial` aquí. |
| **ID del Widget** | `(vacío)` | **Qué hace este ajuste:** Este es un ajuste avanzado para configuraciones específicas del widget de Twitter. Twitter le permite crear widgets personalizados en su plataforma, que generan una ID única. Esta ID se puede utilizar para mostrar una línea de tiempo altamente personalizada (por ejemplo, una línea de tiempo de listas específicas, resultados de búsqueda o colecciones).   **Efecto de cambiar este ajuste:**   *Cuando se deja vacío:* El módulo generará una línea de tiempo estándar basada en su "Nombre de usuario de Twitter". Esto suele ser suficiente para la mayoría de los comerciantes.   *Cuando se introduce una ID de Widget válida:* El módulo mostrará la línea de tiempo específica y personalizada asociada con esa ID, anulando la línea de tiempo de usuario predeterminada.   **Valor recomendado:** Dejar vacío a menos que haya creado un widget personalizado en la plataforma de desarrolladores de Twitter y desee utilizar específicamente su ID.   **Escenario / ejemplo de comerciante:** Podría crear un widget de Twitter personalizado que solo muestre tweets que contengan un hashtag específico relacionado con una campaña. Luego obtendría la ID de ese widget de Twitter y la introduciría aquí. |
| **Tema** | `light` | **Qué hace este ajuste:** Controla el tema visual del widget de Twitter.   **Efecto de cambiar este ajuste:**   *Cuando se establece en `light` (predeterminado):* El widget tendrá un fondo claro y texto oscuro, adecuado para la mayoría de las tiendas PrestaShop con temas claros.   *Cuando se establece en `dark` (si está disponible):* El widget tendrá un fondo oscuro y texto claro, ideal para tiendas con temas oscuros o para crear un contraste.   **Valor recomendado:** `light` para la mayoría de las tiendas. Elija `dark` si el diseño de su tienda utiliza un esquema de color oscuro.   **Escenario / ejemplo de comerciante:** Si su sitio web tiene un fondo blanco y limpio, el tema `light` se integrará perfectamente. Si su sitio utiliza un fondo gris oscuro o negro sofisticado, el tema `dark` sería más apropiado. |
| **Color del Enlace** | `(vacío)` | **Qué hace este ajuste:** Le permite personalizar el color de los enlaces dentro del widget de Twitter (por ejemplo, hashtags, menciones, URLs).   **Efecto de cambiar este ajuste:**   *Cuando se deja vacío:* El widget utilizará el color de enlace predeterminado de Twitter (normalmente un tono de azul).   *Cuando se introduce un código de color hexadecimal válido (por ejemplo, `#FF0000` para rojo):* Todos los enlaces dentro del widget se mostrarán en ese color personalizado.   **Valor recomendado:** Dejar vacío para el valor predeterminado, o introducir un código de color hexadecimal que coincida con la marca de su tienda.   **Escenario / ejemplo de comerciante:** Si el color principal de su marca es el verde, podría introducir `#008000` para que los enlaces del widget coincidan con su marca. |
| **Color del Borde** | `(vacío)` | **Qué hace este ajuste:** Le permite personalizar el color del borde alrededor del widget de Twitter.   **Efecto de cambiar este ajuste:**   *Cuando se deja vacío:* El widget utilizará el color de borde predeterminado de Twitter.   *Cuando se introduce un código de color hexadecimal válido:* El borde del widget se mostrará en ese color personalizado.   **Valor recomendado:** Dejar vacío para el valor predeterminado, o introducir un código de color hexadecimal que coincida con la marca de su tienda o se integre con su diseño.   **Escenario / ejemplo de comerciante:** Para que el widget destaque con un marco sutil, podría usar un borde gris claro `#CCCCCC`. |
| **Límite de Tweets** | `20` | **Qué hace este ajuste:** Determina el número máximo de tweets que se mostrarán en la línea de tiempo.   **Efecto de cambiar este ajuste:**   *Cuando se establece en un número más bajo (por ejemplo, `3`):* Solo los tweets más recientes serán visibles, haciendo el widget más corto.   *Cuando se establece en un número más alto (por ejemplo, `20`):* Se cargarán más tweets, haciendo el widget más largo y permitiendo más desplazamiento.   **Valor recomendado:** `3` a `7` para columnas laterales para mantenerlo conciso, `10` a `20` para áreas más amplias como el pie de página o el contenido principal.   **Escenario / ejemplo de comerciante:** Si coloca el widget en una columna izquierda estrecha, podría configurarlo en `3` para evitar que la columna sea demasiado larga. En el pie de página, podría configurarlo en `10` para mostrar más actividad. |
| **Altura** | `300` | **Qué hace este ajuste:** Establece la altura fija del widget de Twitter en píxeles.   **Efecto de cambiar este ajuste:**   *Cuando se establece en un número más bajo (por ejemplo, `200`):* El widget será más corto, lo que podría requerir más desplazamiento para ver todos los tweets (hasta el Límite de Tweets).   *Cuando se establece en un número más alto (por ejemplo, `500`):* El widget será más alto, mostrando más tweets a la vez sin desplazamiento.   **Valor recomendado:** `280` a `400` píxeles, dependiendo de la ubicación y el espacio disponible.   **Escenario / ejemplo de comerciante:** Para una columna derecha, una altura de `300px` suele ser un buen equilibrio. Para una ubicación en el pie de página, podría aumentarla a `400px` si tiene un amplio espacio vertical. |
| **Ancho** | `(vacío)` | **Qué hace este ajuste:** Establece el ancho fijo del widget de Twitter en píxeles.   **Efecto de cambiar este ajuste:**   *Cuando se deja vacío:* El widget intentará ajustar automáticamente su ancho para adaptarse al contenedor en el que se encuentra (comportamiento responsivo). Esto generalmente se recomienda.   *Cuando se establece en un número específico (por ejemplo, `250`):* El widget mantendrá ese ancho fijo, lo que podría causar desbordamiento o espacio vacío si el contenedor es más grande o más pequeño.   **Valor recomendado:** Dejar vacío para un comportamiento responsivo, o establecer un ancho específico si necesita un control preciso y comprende las implicaciones para diferentes tamaños de pantalla.   **Escenario / ejemplo de comerciante:** Dejarlo vacío asegura que se vea bien en dispositivos móviles. Si necesita absolutamente un ancho fijo para un diseño muy específico, podría configurarlo en `280px` para una columna estrecha. |
| **Idioma** | `en` | **Qué hace este ajuste:** Determina el idioma en el que se muestra la interfaz del widget de Twitter (por ejemplo, botón "Ver en Twitter", marcas de tiempo).   **Efecto de cambiar este ajuste:**   *Cuando se establece en `en` (inglés):* La interfaz del widget estará en inglés.   *Cuando se establece en otro código de idioma válido (por ejemplo, `fr` para francés, `es` para español):* La interfaz del widget se localizará a ese idioma.   **Valor recomendado:** El idioma principal de su tienda.   **Escenario / ejemplo de comerciante:** Si su tienda atiende principalmente a clientes en Francia, configurarlo en `fr` hará que el widget sea más fácil de usar para ellos. |
| **Mostrar Cabecera** | `SÍ` | **Qué hace este ajuste:** Controla si la sección de la cabecera del widget de Twitter (que muestra el nombre de su cuenta y la etiqueta "Tweets") es visible.   **Efecto de cambiar este ajuste:**   *Cuando está habilitado (SÍ):* La cabecera se mostrará, proporcionando un contexto claro sobre de quién son los tweets que se muestran.   *Cuando está deshabilitado (NO):* La cabecera se ocultará, lo que resultará en un widget más compacto, pero con un contexto potencialmente menos claro.   **Valor recomendado:** `SÍ` para mayor claridad, a menos que necesite un diseño muy minimalista.   **Escenario / ejemplo de comerciante:** Si el widget está en una ubicación prominente, `SÍ` es bueno. Si es un widget pequeño en un área concurrida, `NO` podría ahorrar espacio. |
| **Mostrar Pie de Página** | `SÍ` | **Qué hace este ajuste:** Controla si la sección del pie de página del widget de Twitter (que normalmente muestra el enlace "Ver en Twitter") es visible.   **Efecto de cambiar este ajuste:**   *Cuando está habilitado (SÍ):* El pie de página se mostrará, proporcionando un enlace directo para que los usuarios visiten su perfil completo de Twitter.   *Cuando está deshabilitado (NO):* El pie de página se ocultará, haciendo el widget más compacto.   **Valor recomendado:** `SÍ` para animar a los usuarios a seguirle en Twitter.   **Escenario / ejemplo de comerciante:** Mantener `SÍ` ayuda a dirigir el tráfico a su perfil de Twitter. |
| **Mostrar Borde** | `SÍ` | **Qué hace este ajuste:** Controla si se muestra un borde alrededor del widget de Twitter.   **Efecto de cambiar este ajuste:**   *Cuando está habilitado (SÍ):* Un borde enmarcará el widget, ayudándolo a destacarse del contenido circundante.   *Cuando está deshabilitado (NO):* El widget no tendrá un borde visible, integrándose más perfectamente con el fondo.   **Valor recomendado:** `SÍ` para una mejor separación visual, especialmente en columnas.   **Escenario / ejemplo de comerciante:** Si su página tiene mucho contenido, un borde ayuda a definir el espacio del widget. Si desea un aspecto muy limpio e integrado, `NO` podría ser preferible. |
| **Mostrar Barra de Desplazamiento** | `SÍ` | **Qué hace este ajuste:** Controla si aparece una barra de desplazamiento dentro del widget si el contenido (tweets) excede la altura establecida.   **Efecto de cambiar este ajuste:**   *Cuando está habilitado (SÍ):* Aparecerá una barra de desplazamiento, permitiendo a los usuarios desplazarse por todos los tweets cargados dentro de la altura fija.   *Cuando está deshabilitado (NO):* No aparecerá ninguna barra de desplazamiento. Si los tweets exceden la altura, se cortarán o el widget podría expandirse (dependiendo de otros ajustes y el comportamiento del navegador). Esto generalmente no se recomienda ya que oculta contenido.   **Valor recomendado:** `SÍ` para asegurar que todos los tweets sean accesibles.   **Escenario / ejemplo de comerciante:** Siempre mantenga `SÍ` a menos que solo quiera mostrar 1-2 tweets y nunca quiera desplazamiento. |
| **Fondo Transparente** | `SÍ` | **Qué hace este ajuste:** Controla si el fondo del widget de Twitter es transparente.   **Efecto de cambiar este ajuste:**   *Cuando está habilitado (SÍ):* El fondo del widget será transparente, permitiendo que se muestre el color o la imagen de fondo de su tienda.   *Cuando está deshabilitado (NO):* El widget tendrá un fondo sólido (blanco para el tema `light`, oscuro para el tema `dark`), lo que podría crear una apariencia cuadrada.   **Valor recomendado:** `SÍ` para una mejor integración con su tema.   **Escenario / ejemplo de comerciante:** Si su tienda tiene un fondo texturizado o un color de fondo específico, `SÍ` hará que el widget parezca una parte natural de su diseño. |
| **Mostrar Respuestas** | `SÍ` | **Qué hace este ajuste:** Controla si las respuestas a los tweets se incluyen en la línea de tiempo.   **Efecto de cambiar este ajuste:**   *Cuando está habilitado (SÍ):* Se mostrarán las respuestas, proporcionando un contexto de conversación más completo.   *Cuando está deshabilitado (NO):* Solo se mostrarán los tweets originales y los retweets, lo que hará que la línea de tiempo sea potencialmente más limpia pero menos conversacional.   **Valor recomendado:** `SÍ` para un feed más activo y atractivo.   **Escenario / ejemplo de comerciante:** Si interactúa frecuentemente con los clientes a través de respuestas, `SÍ` es importante para mostrar esa interacción. Si su feed es puramente para anuncios, `NO` podría ser preferible. |
| **Reproducir Videos Automáticamente** | `NO` | **Qué hace este ajuste:** Controla si los videos incrustados en los tweets dentro del widget se reproducirán automáticamente.   **Efecto de cambiar este ajuste:**   *Cuando está habilitado (SÍ):* Los videos comenzarán a reproducirse automáticamente cuando aparezcan en la ventana de visualización. Esto puede ser atractivo, pero podría consumir ancho de banda y molestar a algunos usuarios.   *Cuando está deshabilitado (NO):* Los videos requerirán un clic del usuario para reproducirse.   **Valor recomendado:** `NO` para evitar sorprender a los clientes con sonido o consumir sus datos sin consentimiento.   **Escenario / ejemplo de comerciante:** Generalmente, `NO` es mejor para la experiencia del usuario. Si tiene un video muy específico, silencioso y corto que desea destacar, podría considerar `SÍ`, pero proceda con precaución. |
| **Ocultar Barra de Desplazamiento** | `NO` | **Qué hace este ajuste:** Este ajuste probablemente sea redundante o entre en conflicto con "Mostrar Barra de Desplazamiento". En general, si "Mostrar Barra de Desplazamiento" es SÍ, este ajuste debe ser NO.   **Efecto de cambiar este ajuste:**   *Cuando está habilitado (SÍ):* Intenta ocultar la barra de desplazamiento. Esto puede llevar a que el contenido sea inaccesible si la altura es fija y los tweets la exceden.   *Cuando está deshabilitado (NO):* Permite que la barra de desplazamiento sea visible si "Mostrar Barra de Desplazamiento" también es SÍ.   **Valor recomendado:** `NO` para asegurar que el contenido sea siempre accesible.   **Escenario / ejemplo de comerciante:** Siempre mantenga `NO` junto con `Mostrar Barra de Desplazamiento: SÍ`. |
| **Colocar en hook** | `displayRightColumn` | **Qué hace este ajuste:** Determina dónde se mostrará el widget de Twitter en su tienda PrestaShop.   **Efecto de cambiar este ajuste:**   *Cuando se establece en `displayRightColumn` (predeterminado):* El widget aparecerá en la barra lateral derecha.   *Cuando se establece en `displayLeftColumn` (si está disponible):* El widget aparecerá en la barra lateral izquierda.   *Cuando se establece en `displayFooter` (si está disponible):* El widget aparecerá en la sección del pie de página.   *Cuando se establece en `displayHeader` (si está disponible):* El widget aparecerá en la sección de la cabecera.   *Cuando se establece en `displayProductButtons` o similar (si está disponible):* El widget aparecerá en las páginas de productos.   **Valor recomendado:** `displayRightColumn` o `displayLeftColumn` para visibilidad general, `displayFooter` para una ubicación menos intrusiva. Elija según el diseño de su tema y dónde quiera llamar la atención.   **Escenario / ejemplo de comerciante:** Si su tema tiene una barra lateral derecha prominente, `displayRightColumn` es una buena opción. Si desea que sea visible en cada página pero que no ocupe mucho espacio, `displayFooter` es adecuado. |

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|
| Configuración del Módulo | Nombre de usuario de Twitter | Su nombre de usuario de X | Especifica la cuenta de la que se mostrarán los tweets. |
| Configuración del Módulo | ID del Widget | Vacío | Avanzado: Usar para widgets personalizados generados por Twitter. |
| Configuración del Módulo | Tema | `light` | Tema visual del widget (claro/oscuro). |
| Configuración del Módulo | Color del Enlace | Vacío | Personaliza los colores de los enlaces dentro del widget. |
| Configuración del Módulo | Color del Borde | Vacío | Personaliza el color del borde del widget. |
| Configuración del Módulo | Límite de Tweets | `20` | Número máximo de tweets a mostrar. |
| Configuración del Módulo | Altura | `300` | Altura fija del widget en píxeles. |
| Configuración del Módulo | Ancho | Vacío | Ancho fijo del widget en píxeles (dejar vacío para responsivo). |
| Configuración del Módulo | Idioma | `en` | Idioma de la interfaz del widget. |
| Configuración del Módulo | Mostrar Cabecera | `SÍ` | Mostrar/ocultar la cabecera del widget (nombre de la cuenta). |
| Configuración del Módulo | Mostrar Pie de Página | `SÍ` | Mostrar/ocultar el pie de página del widget (enlace Ver en Twitter). |
| Configuración del Módulo | Mostrar Borde | `SÍ` | Mostrar/ocultar el borde exterior del widget. |
| Configuración del Módulo | Mostrar Barra de Desplazamiento | `SÍ` | Mostrar/ocultar la barra de desplazamiento interna para los tweets. |
| Configuración del Módulo | Fondo Transparente | `SÍ` | Hacer transparente el fondo del widget. |
| Configuración del Módulo | Mostrar Respuestas | `SÍ` | Incluir/excluir respuestas en la línea de tiempo. |
| Configuración del Módulo | Reproducir Videos Automáticamente | `NO` | Reproducir videos automáticamente en los tweets. |
| Configuración del Módulo | Ocultar Barra de Desplazamiento | `NO` | (Redundante con Mostrar Barra de Desplazamiento) Mantener NO. |
| Configuración del Módulo | Colocar en hook | `displayRightColumn` | Dónde aparece el widget en su tienda. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P: Mi widget de Twitter no aparece en mi tienda. ¿Qué debo hacer?**
R:

1. **Verifique la Configuración:** Vaya a **Módulos > Gestor de módulos > Twitter widget free > Configurar**. Asegúrese de haber introducido su "Nombre de usuario de Twitter" correcto y de haber guardado los ajustes.
2. **Verifique la Ubicación del Hook:** Verifique que el ajuste "Colocar en hook" esté configurado en un hook que realmente sea renderizado por su tema (por ejemplo, `displayRightColumn`). Algunos temas podrían no mostrar todos los hooks estándar.
3. **Borre la Caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, la caché de PrestaShop impide que el nuevo contenido del módulo aparezca inmediatamente.
4. **Compatibilidad del Tema:** Aunque el módulo es ampliamente compatible, los temas muy personalizados podrían requerir ajustes menores. Si el problema persiste, póngase en contacto con el soporte de MyPresta.eu.

**P: El widget aparece, pero está vacío o muestra un mensaje de error.**
R:

1. **Nombre de Usuario Incorrecto:** Verifique dos veces su "Nombre de usuario de Twitter" en la configuración del módulo. Incluso un pequeño error tipográfico impedirá que se obtengan los tweets.
2. **Cuenta Privada:** Asegúrese de que su cuenta de Twitter sea pública. El widget no puede mostrar tweets de cuentas privadas (protegidas).
3. **Problemas con la API de Twitter:** Ocasionalmente, puede haber problemas temporales con la propia API de Twitter. Espere un poco y vuelva a verificar.

**P: ¿Cómo cambio el idioma del widget?**
R: En la configuración del módulo, busque el ajuste "Idioma" y seleccione el código de idioma de dos letras apropiado (por ejemplo, `fr` para francés, `es` para español).

**P: El widget se ve demasiado ancho/estrecho o demasiado alto/corto.**
R:

1. **Ancho:** Para un comportamiento responsivo, deje el ajuste "Ancho" vacío. Si ha establecido un valor de píxeles específico, intente eliminarlo.
2. **Altura:** Ajuste el ajuste "Altura" (en píxeles) para hacer el widget más alto o más corto.
3. **Límite de Tweets:** Reduzca el "Límite de Tweets" para hacer el widget más corto si tiene una altura fija y desea que se muestren menos tweets.

**P: ¿Puedo mostrar tweets de un hashtag o lista específica en lugar de mi cuenta principal?**
R: Sí, pero esto requiere una configuración avanzada. Tendría que crear un widget de línea de tiempo incrustada personalizado directamente en la plataforma de desarrolladores de Twitter (developer.twitter.com), configurarlo allí para mostrar un hashtag o una lista, y luego obtener la "ID del Widget" única que proporciona. Luego, introduciría esta "ID del Widget" en la configuración del módulo, dejando el "Nombre de usuario de Twitter" vacío.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo "Twitter widget free" es un módulo sencillo de PrestaShop diseñado para integrar la funcionalidad de línea de tiempo incrustada de Twitter. Principalmente aprovecha la estructura de módulo estándar de PrestaShop, utilizando el archivo principal `index.php` tanto para la instalación/desinstalación como para la configuración (`getContent()`). El módulo inyecta un widget de Twitter basado en JavaScript en el front-office utilizando una plantilla Smarty y un archivo CSS para el estilo básico. Se basa en el propio `widgets.js` de Twitter para renderizar la línea de tiempo, que se carga asincrónicamente.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**: Ninguno. La visualización del front-office del módulo se maneja completamente a través de hooks y una plantilla Smarty.
- **Controladores de Administración de Back-Office**: Ninguno. Toda la configuración se gestiona a través del método `getContent()` de la clase principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

- No hay clases personalizadas ni definiciones de `ObjectModel` presentes en este módulo. Toda la lógica está autocontenida dentro del archivo principal `twitterwidget/index.php`.

### 4.4 Activos JavaScript (`views/js/`)

- No se incluyen archivos JavaScript personalizados directamente dentro del directorio `views/js/` del módulo.
- El módulo se basa en gran medida en el script oficial de Twitter `widgets.js`, que se carga dinámicamente en la plantilla del front-office (`rightcolumn.tpl`) para renderizar la línea de tiempo incrustada. Este script maneja toda la lógica compleja de obtención de tweets y su visualización.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `twitterwidget/twitterwidget.css`:
  - **Alcance**: Estilo del cliente en el front-office.
  - **Componentes de la interfaz de usuario principales y contenedores que estiliza**: Este archivo probablemente contiene un estilo mínimo, principalmente para asegurar que el widget de Twitter se integre bien con varios temas de PrestaShop. Podría incluir reglas para el contenedor `.twitter-widget`, restablecimientos básicos o ajustes responsivos.
  - **Selectores de clase CSS clave que los desarrolladores pueden anular**: Los desarrolladores pueden inspeccionar este archivo para identificar selectores específicos (por ejemplo, `.twitter-widget-container`, `.twitter-timeline`) y anularlos en el `custom.css` o `theme.css` de su tema para personalizar aún más la apariencia del widget.

### 4.6 Estructura de la Plantilla Smarty (`views/templates/`)

- **Plantillas de Hook (`views/templates/hook/`)**:
  - `twitterwidget/rightcolumn.tpl`:
    - **Hook(s) renderizado(s) en**: Esta plantilla está diseñada para ser renderizada en varios hooks de visualización, según lo configure el comerciante (por ejemplo, `displayRightColumn`, `displayLeftColumn`, `displayFooter`, `displayHeader`, `displayProductButtons`). Los métodos `hookDisplay*` del módulo llamarán a esta plantilla.
    - **Salida del bloque visual**: Esta plantilla genera la estructura HTML necesaria para la línea de tiempo incrustada de Twitter. Típicamente incluye una etiqueta `<a>` con atributos `data-` (por ejemplo, `data-tweet-limit`, `data-theme`, `data-link-color`, `data-border-color`, `data-height`, `data-width`, `data-lang`, `data-chrome`, `data-dnt`, `data-show-replies`, `data-autoplay`) que el script `widgets.js` de Twitter lee para renderizar la línea de tiempo. También incluye la etiqueta `<script>` para cargar `widgets.js` asincrónicamente.

### 4.7 Esquema de la Base de Datos y Mapa de Hooks

- **Tablas de la Base de Datos**:
  - Este módulo no crea ninguna tabla SQL personalizada.
  - Los ajustes de configuración se almacenan en la tabla `ps_configuration` utilizando claves de configuración estándar de PrestaShop (por ejemplo, `TWITTERWIDGET_USERNAME`, `TWITTERWIDGET_WIDGETID`, `TWITTERWIDGET_THEME`, etc.).
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Potencialmente utilizado para cargar el script del widget de Twitter globalmente, o para mostrar el widget en el área de la cabecera. |
| `displayRightColumn` | En la barra lateral derecha de las páginas que tienen una. | Muestra el widget de Twitter en la columna derecha. |
| `displayLeftColumn` | En la barra lateral izquierda de las páginas que tienen una. | Muestra el widget de Twitter en la columna izquierda. |
| `displayFooter` | En la sección del pie de página de cada página. | Muestra el widget de Twitter en el pie de página. |
| `displayProductButtons` | En la página del producto, típicamente cerca del botón de añadir al carrito o la descripción del producto. | Muestra el widget de Twitter en las páginas de productos. |
| `actionFrontControllerSetMedia` | Después de que el controlador frontal haya establecido sus medios, permitiendo que los módulos añadan los suyos. | Se utiliza para registrar los archivos CSS y potencialmente JS del módulo (aunque este módulo carga el JS de Twitter directamente en TPL). |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Twitter widget free", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema técnico o pregunta que pueda tener.
