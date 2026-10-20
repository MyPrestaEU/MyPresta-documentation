---
title: "Facebook Like Box - Manual del Comerciante y Guía de Configuración"
description: ""
sidebar:
  label: "Facebook Like Box - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Facebook Like Box en MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-like-box.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/facebook-like-box/)
>
> ---


# Facebook Like Box

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y cualquier módulo que interactúe con APIs externas como Facebook.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal para su módulo Facebook Like Box. Aquí definirá cómo se ve y se comporta su Like Box en su tienda.

**Nombre de la pantalla y ubicación del menú:** Back Office > Módulos > Gestor de Módulos > Facebook Like Box > Configurar

| Ajuste / Opción | Qué hace este ajuste | Efecto de cambiar este ajuste | Valor recomendado | Escenario / ejemplo de comerciante |
| --- | --- | --- | --- | --- |
| **URL de la página de Facebook** | Este es el enlace directo a su página oficial de Facebook. | *Cuando se establece:* El Like Box mostrará contenido de esta página específica de Facebook. *Cuando está vacío:* El módulo no funcionará correctamente ya que no sabrá qué página mostrar. | La URL de su página de Facebook (por ejemplo, `https://www.facebook.com/myprestaeu`) | Quiere promocionar la página principal de Facebook de su negocio. |
| **ID de la aplicación (Facebook)** | Su ID de aplicación de Facebook, requerido para algunas funciones avanzadas e integraciones de API. | *Cuando se establece:* Permite que el módulo interactúe con la API Graph de Facebook usando su aplicación. *Cuando está vacío:* Puede resultar en errores de "Aplicación no configurada" si el módulo requiere acceso a la API. | Su ID de aplicación de Facebook (por ejemplo, `123456789012345`) | Necesita resolver un error de "Aplicación no configurada" o habilitar funciones avanzadas de la API de Facebook. |
| **Ancho** | Controla el ancho del Facebook Like Box en píxeles. | *Cuando se establece en un valor específico (por ejemplo, 280):* El Like Box mantendrá ese ancho exacto. *Cuando se deja vacío o se establece en 0:* El Like Box intentará ser responsivo y ajustar su ancho automáticamente para ajustarse a su contenedor. | Dejar vacío para detección automática (comportamiento responsivo) o establecer un valor específico como `280` si necesita un ancho fijo. | Quiere que el Like Box encaje perfectamente en una columna estrecha, por lo que lo establece en `280`. |
| **Altura** | Controla la altura del Facebook Like Box en píxeles. | *Cuando se establece en un valor específico (por ejemplo, 500):* El Like Box mantendrá esa altura exacta. *Cuando se deja vacío o se establece en 0:* El Like Box intentará ser responsivo y ajustar su altura automáticamente. | Dejar vacío para detección automática (comportamiento responsivo) o establecer un valor específico como `500` si quiere mostrar más del flujo de publicaciones. | Quiere mostrar más publicaciones recientes de su página de Facebook, por lo que aumenta la altura a `500`. |
| **Mostrar caras** | Determina si se muestran las fotos de perfil de las personas a las que les gusta su página. | *Cuando está habilitado (SÍ):* Pequeñas fotos de perfil de algunos de sus fans de Facebook aparecerán debajo del botón "Me gusta", añadiendo prueba social. *Cuando está deshabilitado (NO):* Solo se mostrará el botón "Me gusta" y la información de la página, sin caras individuales. | SÍ | Quiere mostrar que a personas reales les gusta su página, animando a otros a unirse. |
| **Mostrar flujo** | Controla si se muestran las publicaciones recientes de su página de Facebook dentro del Like Box. | *Cuando está habilitado (SÍ):* Sus últimas publicaciones de Facebook se desplazarán dentro del Like Box, proporcionando contenido fresco. *Cuando está deshabilitado (NO):* Solo la portada de la página, el perfil y el botón "Me gusta" serán visibles, haciendo que el cuadro sea más compacto. | SÍ | Publica actualizaciones con frecuencia en Facebook y quiere compartirlas directamente en su tienda. |
| **Mostrar cabecera** | Controla si se muestra la cabecera "Facebook" en la parte superior del Like Box. | *Cuando está habilitado (SÍ):* Un pequeño título "Facebook" aparecerá en la parte superior del widget. *Cuando está deshabilitado (NO):* La cabecera se ocultará, haciendo que el widget se vea más limpio y más integrado. | NO | Prefiere un aspecto minimalista para el Like Box y no necesita la cabecera explícita "Facebook". |
| **Cabecera pequeña** | Utiliza una versión más pequeña de la cabecera. | *Cuando está habilitado (SÍ):* La cabecera será más compacta. *Cuando está deshabilitado (NO):* Se utilizará el tamaño de cabecera estándar. | NO | Quiere ahorrar espacio vertical en su diseño. |
| **Ocultar portada** | Oculta la foto de portada de su página de Facebook. | *Cuando está habilitado (SÍ):* Solo la foto de perfil y el nombre de su página serán visibles, haciendo que el widget sea más compacto. *Cuando está deshabilitado (NO):* La foto de portada de su página de Facebook se mostrará en la parte superior del widget. | NO | Tiene un espacio muy estrecho y quiere priorizar el botón "Me gusta" y las publicaciones sobre la foto de portada. |
| **Adaptar al ancho del contenedor** | Permite que el Like Box ajuste automáticamente su ancho para ajustarse al contenedor padre en el que se encuentra. | *Cuando está habilitado (SÍ):* El widget se redimensionará para llenar el ancho disponible, haciéndolo responsivo. *Cuando está deshabilitado (NO):* El widget se mantendrá en la configuración de `Ancho` especificada, lo que podría causar desbordamiento o espacio vacío. | SÍ | Quiere que el Like Box se vea bien en todos los dispositivos y tamaños de pantalla sin ajustes manuales. |
| **CSS personalizado** | Le permite añadir reglas CSS personalizadas para estilizar aún más el Like Box. | *Cuando se rellena con código CSS:* Sus estilos personalizados se aplicarán, anulando los estilos predeterminados. *Cuando está vacío:* El módulo utilizará su estilo predeterminado o el estilo predeterminado de Facebook. | Dejar vacío a menos que tenga necesidades de estilo específicas. | Quiere cambiar el tamaño de fuente o el color del texto dentro del Like Box para que coincida con el tema de su marca. |
| **Hook para mostrar el módulo** | Selecciona dónde aparecerá el Like Box en su tienda. | *Cuando se selecciona un hook:* El módulo renderizará su contenido en esa ubicación específica (por ejemplo, `displayRightColumn`, `displayFooter`). *Cuando no se selecciona ningún hook:* El módulo no será visible en su front office. | `displayRightColumn` o `displayLeftColumn` son comunes, pero elija según el diseño de su tema. | Quiere que el Like Box sea visible en el lateral de sus listados de productos, por lo que elige `displayRightColumn`. |
| **Color de fondo** | Establece el color de fondo del Like Box. | *Cuando se selecciona un color:* El Like Box tendrá ese color de fondo. *Cuando se deja vacío:* El Like Box normalmente heredará el color de fondo de su contenedor padre o usará el predeterminado de Facebook. | Dejar vacío o que coincida con el color de fondo de su tema. | Su tema tiene un fondo oscuro y quiere que el Like Box se integre, por lo que establece un color de fondo oscuro. |
| **Color del borde** | Establece el color del borde alrededor del Like Box. | *Cuando se selecciona un color:* El Like Box tendrá un borde de ese color. *Cuando se deja vacío:* El Like Box normalmente no tendrá borde o un borde predeterminado de Facebook. | Dejar vacío o que coincida con los colores de borde de su tema. | Quiere un sutil borde gris alrededor del Like Box para separarlo de otro contenido. |

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | URL de la página de Facebook | URL de su página de Facebook | Vincula el widget a su página específica de Facebook. |
| Configuración del módulo | ID de la aplicación (Facebook) | Vacío (si no es necesario) | Su ID de aplicación de Facebook para la integración de la API. |
| Configuración del módulo | Ancho | Vacío (Responsivo) | Controla el ancho del widget; vacío para ajuste automático. |
| Configuración del módulo | Altura | Vacío (Responsivo) | Controla la altura del widget; vacío para ajuste automático. |
| Configuración del módulo | Mostrar caras | SÍ | Muestra fotos de perfil de los que dan "Me gusta" para prueba social. |
| Configuración del módulo | Mostrar flujo | SÍ | Muestra publicaciones recientes de su página de Facebook. |
| Configuración del módulo | Mostrar cabecera | NO | Oculta el título "Facebook" para un aspecto más limpio. |
| Configuración del módulo | Cabecera pequeña | NO | Utiliza una cabecera más pequeña si `Mostrar cabecera` es SÍ. |
| Configuración del módulo | Ocultar portada | NO | Muestra la foto de portada de su página de Facebook. |
| Configuración del módulo | Adaptar al ancho del contenedor | SÍ | Asegura que el widget sea responsivo a su contenedor padre. |
| Configuración del módulo | CSS personalizado | Vacío | Permite un estilo avanzado con reglas CSS personalizadas. |
| Configuración del módulo | Hook para mostrar el módulo | `displayRightColumn` (o columna relevante) | Determina dónde aparece el módulo en su tienda. |
| Configuración del módulo | Color de fondo | Vacío | Establece el color de fondo del widget. |
| Configuración del módulo | Color del borde | Vacío | Establece el color del borde del widget. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P1: El Facebook Like Box no aparece en mi tienda. ¿Qué debo hacer?**
R1:

-   **Verificar el estado del módulo:** Vaya a **Módulos > Gestor de Módulos** y asegúrese de que el módulo "Facebook Like Box" esté instalado y habilitado.
-   **Verificar la selección del hook:** En la configuración del módulo, asegúrese de haber seleccionado un "Hook para mostrar el módulo" (por ejemplo, `displayRightColumn`, `displayFooter`). Si su tema no renderiza el hook seleccionado, no aparecerá. Pruebe con un hook común diferente.
-   **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, la caché de PrestaShop impide que los nuevos módulos aparezcan inmediatamente.
-   **URL de la página de Facebook:** Verifique que la "URL de la página de Facebook" en la configuración del módulo sea correcta y accesible.

**P2: El Like Box se ve demasiado ancho/estrecho o no se ajusta correctamente a mi tema.**
R2:

-   **Configuración responsiva:** En la configuración del módulo, asegúrese de que "Adaptar al ancho del contenedor" esté configurado en SÍ, y deje los campos "Ancho" y "Altura" vacíos. Esto permite que Facebook gestione la responsividad.
-   **Conflictos de tema:** El CSS de su tema podría estar anulando los estilos del módulo. Si se siente cómodo con CSS, use las herramientas de desarrollo de su navegador (F12) para inspeccionar el elemento y ver qué reglas CSS se están aplicando.
-   **CSS personalizado:** Utilice el campo "CSS personalizado" en la configuración del módulo para añadir reglas específicas para ajustar su tamaño o apariencia si es necesario. Por ejemplo: `.fb_iframe_widget { max-width: 100% !important; }`.

**P3: El Like Box muestra un error o no carga contenido de mi página de Facebook.**
R3:

-   **URL correcta:** Verifique que la "URL de la página de Facebook" sea absolutamente correcta y apunte a una página pública de Facebook (no a un perfil personal o grupo).
-   **Problemas con la API de Facebook:** Ocasionalmente, la API de Facebook podría experimentar problemas temporales. Espere un poco y vuelva a verificar.
-   **Restricciones de la página:** Asegúrese de que su página de Facebook no tenga restricciones de país o edad que puedan impedir que el widget se cargue para todos los visitantes.

:::caution
\*\*Error "Aplicación no configurada" (Módulo versión 1.8 y superior)\*\*
Si encuentra un error "Aplicación no configurada", especialmente con la versión 1.8 o superior del módulo, que es compatible con la API Graph de Facebook v18.0:
1.  \*\*Introduzca su ID de aplicación de Facebook:\*\* Asegúrese de haber introducido correctamente su ID de aplicación de Facebook en el campo de configuración del módulo.
2.  \*\*Verifique la configuración de dominio en Facebook:\*\* Inicie sesión en su cuenta de desarrollador de Facebook ([developers.facebook.com](https://developers.facebook.com/)). Navegue a la configuración de su aplicación y confirme que el dominio de su tienda (por ejemplo, `sutienda.com`) está correctamente añadido y verificado en la configuración de la aplicación.
:::

**P4: ¿Puedo tener varios Facebook Like Boxes en diferentes páginas?**
R4: Este módulo está diseñado para mostrar un Facebook Like Box configurado globalmente. Si necesita varios Like Boxes distintos (por ejemplo, para diferentes páginas de Facebook o con diferentes configuraciones), normalmente necesitaría instalar el módulo varias veces (si es compatible con el sistema de módulos de PrestaShop, lo cual es raro para módulos de una sola instancia) o usar código personalizado. Para este módulo específico, generalmente es una instancia, una configuración.

**P5: ¿Cómo traduzco el texto dentro del Like Box (por ejemplo, "Me gusta la página")?**
R5: El texto dentro del propio Facebook Like Box (como "Me gusta la página", "Seguir", "Compartir") es controlado por Facebook en función de la configuración de idioma del navegador del usuario y la propia localización de Facebook. Este módulo no traduce directamente estos elementos. Cualquier texto *alrededor* del Like Box que añada en su tema u otros módulos sería traducible a través del sistema de traducción de PrestaShop.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo Facebook Like Box (`likebox`) es un módulo estándar de PrestaShop que sigue un patrón MVC básico. Utiliza principalmente la clase `Module` para la instalación, desinstalación y manejo de la configuración. La funcionalidad principal implica renderizar una plantilla Smarty que incrusta el Facebook Page Plugin (anteriormente Like Box) utilizando el SDK oficial de JavaScript de Facebook. La configuración se almacena en `ps_configuration`.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores de Front-Office o Back-Office Admin personalizados. Toda la configuración se maneja dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no define ninguna clase personalizada ni extiende `ObjectModel`. Toda la lógica está contenida dentro del archivo principal del módulo (`likebox/ar.php`).

### 4.4 Activos de JavaScript (`views/js/`)

-   **`likebox/jscolor/jscolor.js`**

    -   **Alcance:** Back-office (Página de configuración de administración)
    -   **Propósito:** Esta es una biblioteca JavaScript de terceros que proporciona una funcionalidad de selector de color. Se utiliza en la página de configuración del módulo para permitir al comerciante seleccionar visualmente los ajustes de "Color de fondo" y "Color del borde".
    -   **Interacción:** Se enlaza a campos de entrada específicos (probablemente con una clase como `jscolor`) para abrir una paleta de selección de color.
-   **`likebox/script.js`**

    -   **Alcance:** Back-office (Página de configuración de administración)
    -   **Propósito:** Este script maneja las actualizaciones dinámicas y la funcionalidad de vista previa en vivo en la página de configuración del módulo. Toma la configuración de entrada del comerciante (URL de la página de Facebook, ancho, alto, mostrar caras, etc.) y actualiza dinámicamente un `<iframe>` o un área de vista previa para mostrar cómo se verá el Facebook Like Box.
    -   **Interacción:**
        -   Escucha los eventos `change` y `keyup` en varios campos de entrada (por ejemplo, `#facebook_page_url`, `#width`, `#height`, casillas de verificación).
        -   Construye los parámetros de la URL del Facebook Page Plugin basándose en la configuración actual.
        -   Actualiza el atributo `src` de un `<iframe>` de vista previa o genera dinámicamente el código de incrustación del SDK de Facebook para reflejar los cambios en tiempo real.
        -   Probablemente utiliza `jscolor.js` para obtener los valores de color para el fondo y el borde.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   **`likebox/css.css`**

    -   **Alcance:** Back-office (Página de configuración de administración)
    -   **Propósito:** Proporciona estilo para el formulario de configuración del módulo en el Back Office de PrestaShop. Esto podría incluir ajustes de diseño, estilo de campos de entrada o estilo para el área de vista previa en vivo.
    -   **Selectores clave:** Probablemente apunta a elementos dentro de la salida de `getContent()`, como grupos de formularios, etiquetas y el contenedor de vista previa.
-   **`likebox/css/css.css`**

    -   **Alcance:** Front-office (Tienda orientada al cliente)
    -   **Propósito:** Proporciona un estilo mínimo para el propio widget de Facebook Like Box, principalmente para asegurar que se integre bien con el diseño de la tienda. Esto podría incluir relleno predeterminado, márgenes o ajustes responsivos básicos.
    -   **Selectores clave:** Apunta al elemento contenedor donde se incrusta el widget de Facebook (por ejemplo, `.facebook_like_box_container`) y potencialmente aplica `max-width: 100%` para la responsividad. Los desarrolladores pueden anular estos estilos en el `custom.css` o `theme.css` de su tema.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

Las plantillas del módulo se encuentran directamente dentro del directorio raíz del módulo.

-   **`likebox/header.tpl`**

    -   **Alcance:** Front-office
    -   **Hook:** `displayHeader`
    -   **Propósito:** Esta plantilla está diseñada para ser enganchada en `displayHeader`. Su función principal es incluir el SDK de JavaScript de Facebook, que es necesario para que el Facebook Page Plugin se renderice correctamente. También contiene el elemento `div` donde el Like Box será renderizado por el SDK.
    -   **Salida:**

        ```
        <div id="fb-root"></div><script> (function(d, s, id) { var js, fjs = d.getElementsByTagName(s)[0]; if (d.getElementById(id)) return; js = d.createElement(s); js.id = id; js.src = "//connect.facebook.net/en\_US/sdk.js#xfbml=1&version=v2.8&appId={$app\_id}"; // La versión puede variar, appId añadido fjs.parentNode.insertBefore(js, fjs); }(document, 'script', 'facebook-jssdk'));</script><div class="fb-page" data-href="{$facebook\_page\_url}" data-width="{$width}" data-height="{$height}" data-small-header="{$small\_header}" data-adapt-container-width="{$adapt\_container\_width}" data-hide-cover="{$hide\_cover}" data-show-facepile="{$show\_faces}" data-show-posts="{$show\_stream}" data-colorscheme="{$colorscheme}" data-header="{$show\_header}"> <div class="fb-xfbml-parse-ignore"> <blockquote cite="{$facebook\_page\_url}"> <a href="{$facebook\_page\_url}">{$facebook\_page\_url}</a> </blockquote> </div></div>
        ```

        (Nota: La versión real del SDK y los atributos de datos pueden variar ligeramente según la implementación exacta del módulo y los cambios de la API de Facebook).
-   **`likebox/rightcolumn.tpl`**

    -   **Alcance:** Front-office
    -   **Hook:** `displayRightColumn`, `displayLeftColumn`, `displayFooter`, `displayProductButtons`, etc. (dependiendo de la configuración del módulo)
    -   **Propósito:** Esta plantilla actúa como el envoltorio para el Facebook Like Box. Está diseñada para ser flexible y puede ser enganchada en varias posiciones. Normalmente incluye el elemento `div` con la clase `fb-page` que el SDK de Facebook transformará en el Like Box visual.
    -   **Salida:**

        ```
        <div class="block facebook\_like\_box\_container"> <h4>{l s='Síguenos en Facebook' mod='likebox'}</h4> <div class="block\_content"> <div class="fb-page" data-href="{$facebook\_page\_url}" data-width="{$width}" data-height="{$height}" data-small-header="{$small\_header}" data-adapt-container-width="{$adapt\_container\_width}" data-hide-cover="{$hide\_cover}" data-show-facepile="{$show\_faces}" data-show-posts="{$show\_stream}" data-colorscheme="{$colorscheme}" data-header="{$show\_header}"> <div class="fb-xfbml-parse-ignore"> <blockquote cite="{$facebook\_page\_url}"> <a href="{$facebook\_page\_url}">{$facebook\_page\_url}</a> </blockquote> </div> </div> </div></div>
        ```

        Esta plantilla también incluye el título `<h4>` y la estructura `block_content` común para los bloques de columna de PrestaShop.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:

    -   Este módulo no crea tablas SQL personalizadas.
    -   La configuración se almacena en la tabla `ps_configuration` utilizando claves típicamente prefijadas con `LIKEBOX_` (por ejemplo, `LIKEBOX_FACEBOOK_PAGE_URL`, `LIKEBOX_WIDTH`, `LIKEBOX_HEIGHT`, `LIKEBOX_APP_ID`, etc.).
-   **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | Se renderiza en la sección `<head>` de cada página. | Se utiliza para incluir el SDK de JavaScript de Facebook y el div `fb-root` inicial, esencial para que el Like Box funcione. |
| `displayLeftColumn` | Renderiza contenido en la columna lateral izquierda. | Muestra el widget Facebook Like Box en la columna izquierda. |
| `displayRightColumn` | Renderiza contenido en la columna lateral derecha. | Muestra el widget Facebook Like Box en la columna derecha. |
| `displayFooter` | Renderiza contenido en la sección del pie de página de la tienda. | Muestra el widget Facebook Like Box en el pie de página. |
| `displayHome` | Renderiza contenido en la página de inicio. | Muestra el widget Facebook Like Box en la página de inicio. |
| `displayProductButtons` | Renderiza contenido cerca de los botones de acción del producto en la página del producto. | Muestra el widget Facebook Like Box en las páginas de producto. |
| `displayProductExtraContent` | Renderiza contenido adicional en la página del producto, a menudo en una pestaña o debajo del contenido principal. | Muestra el widget Facebook Like Box en las páginas de producto. |
| `displayMyAccountBlock` | Renderiza contenido en el bloque "Mi cuenta" del cliente. | Muestra el widget Facebook Like Box en el área de la cuenta del cliente (menos común para este módulo). |
| `displayMyAccountBlockfooter` | Renderiza contenido en el pie de página del bloque "Mi cuenta". | Muestra el widget Facebook Like Box en el área de la cuenta del cliente. |

(Nota: El método `install()` del módulo registra estos hooks, y los métodos `hook<NombreDelHook>()` en `ar.php` son responsables de renderizar `rightcolumn.tpl` o `header.tpl` según el hook).

## 5. Soporte oficial y actualizaciones

Para las últimas versiones, actualizaciones y soporte dedicado para el módulo Facebook Like Box, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema técnico o pregunta que pueda tener.
