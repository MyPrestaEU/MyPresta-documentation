---
title: "Facebook Fan Slider - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Facebook Fan Slider de MyPresta.eu."
sidebar:
  label: "Facebook Fan Slider - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Facebook Fan Slider en MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-fan-slider.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/facebook-fan-slider/)
>
> ---


# Facebook Fan Slider

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL) para PrestaShop y generalmente están disponibles en todos los entornos de alojamiento modernos. No se necesitan configuraciones de servidor especiales más allá de una configuración estándar de PrestaShop.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Para acceder a la configuración del módulo, vaya a **Módulos > Gestor de módulos**, busque "Facebook Fan Slider" y haga clic en el botón "Configurar".

Aquí tiene un desglose detallado de cada ajuste:

-   **URL de la página de Facebook (fs\_url)**

    -   **Qué hace este ajuste:** Este es el ajuste más crucial. Le dice al módulo qué página de Facebook específica debe mostrar en la caja deslizante.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece la URL de su página de Facebook:* El módulo obtendrá y mostrará el Like Box/Page Plugin para esa página exacta.
        -   *Cuando se deja vacío o se establece incorrectamente:* El módulo no mostrará el contenido de Facebook, o mostrará un error, ya que no sabrá a qué página conectarse.
    -   **Valor recomendado:** Introduzca la URL completa de su página de Facebook (por ejemplo, `https://www.facebook.com/MyPresta.eu`).
    -   **Escenario / ejemplo de comerciante:** Si la página de su negocio es `https://www.facebook.com/MyAwesomeShop`, introduciría esa URL aquí.
-   **Ancho (fs\_width)**

    -   **Qué hace este ajuste:** Controla el ancho del Like Box/Page Plugin de Facebook *dentro* del panel deslizante, en píxeles.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece un valor de píxel específico (por ejemplo, 280):* El contenido de Facebook tendrá exactamente ese ancho.
        -   *Cuando se establece un valor más pequeño:* El contenido podría aparecer apretado o algunos elementos podrían cortarse.
        -   *Cuando se establece un valor más grande:* El contenido se expandirá, pero asegúrese de que no exceda el ancho de la pantalla o parezca desproporcionado.
    -   **Valor recomendado:** Empiece con `280` o `300` píxeles. Ajuste según la cantidad de contenido que muestre (por ejemplo, si muestra publicaciones, es posible que necesite más ancho).
    -   **Escenario / ejemplo de comerciante:** Quiere que la caja deslizante sea lo suficientemente ancha como para mostrar claramente la foto de portada de su página y el botón "Me gusta" sin ser demasiado voluminosa.
-   **Altura (fs\_height)**

    -   **Qué hace este ajuste:** Controla la altura del Like Box/Page Plugin de Facebook *dentro* del panel deslizante, en píxeles.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece un valor de píxel específico (por ejemplo, 400):* El contenido de Facebook tendrá exactamente esa altura.
        -   *Cuando se establece un valor más pequeño:* El contenido podría cortarse, lo que requeriría que los usuarios se desplacen dentro de la caja.
        -   *Cuando se establece un valor más grande:* La caja será más alta, lo que podría ocupar más espacio en la pantalla.
    -   **Valor recomendado:** Empiece con `400` o `500` píxeles. Si habilita "Mostrar publicaciones", es probable que necesite más altura (por ejemplo, `600-700px`) para mostrar algunas publicaciones sin un desplazamiento excesivo.
    -   **Escenario / ejemplo de comerciante:** Quiere mostrar algunas publicaciones recientes de su página de Facebook, por lo que aumenta la altura a `600px` para hacerlas visibles.
-   **Ocultar foto de portada (fs\_hide\_cover)**

    -   **Qué hace este ajuste:** Determina si la foto de portada grande de su página de Facebook se muestra en la parte superior del Like Box/Page Plugin.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (marcado):* La foto de portada no se mostrará, haciendo que el Like Box sea más compacto.
        -   *Cuando está deshabilitado (desmarcado):* La foto de portada se mostrará, haciendo que el Like Box sea visualmente más rico pero también más alto.
    -   **Valor recomendado:** *Deshabilitado* (desmarcado) si desea una caja más atractiva visualmente. *Habilitado* (marcado) si necesita ahorrar espacio vertical.
    -   **Escenario / ejemplo de comerciante:** Tiene una hermosa foto de portada en Facebook y quiere mostrarla, por lo que deja esta opción desmarcada. Si tiene poco espacio, podría marcarla.
-   **Mostrar caras de amigos (fs\_show\_facepile)**

    -   **Qué hace este ajuste:** Controla si se muestran las fotos de perfil de los amigos a los que ya les gusta su página debajo del botón "Me gusta".
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (marcado):* Aparecerá una fila de fotos de perfil de amigos mutuos a los que les gusta su página, añadiendo prueba social.
        -   *Cuando está deshabilitado (desmarcado):* Estas fotos de perfil no se mostrarán.
    -   **Valor recomendado:** *Habilitado* (marcado). La prueba social puede animar a otros a que les guste su página.
    -   **Escenario / ejemplo de comerciante:** Quiere aprovechar la prueba social para fomentar nuevos "me gusta", por lo que habilita esta opción para mostrar a los amigos a los que ya les gusta su página.
-   **Mostrar publicaciones (fs\_show\_posts)**

    -   **Qué hace este ajuste:** Determina si las publicaciones recientes de la línea de tiempo de su página de Facebook se muestran dentro del Like Box/Page Plugin.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (marcado):* Sus últimas publicaciones de Facebook aparecerán, haciendo que la caja sea más dinámica y atractiva. Es probable que necesite aumentar el ajuste `Height`.
        -   *Cuando está deshabilitado (desmarcado):* Solo se mostrará la funcionalidad básica de "Me gusta" y las caras de los amigos (si está habilitado).
    -   **Valor recomendado:** *Habilitado* (marcado) si publica regularmente contenido atractivo y quiere mostrarlo. Recuerde ajustar `Height`.
    -   **Escenario / ejemplo de comerciante:** Publica con frecuencia sobre nuevos productos y promociones en Facebook. Habilitar esto permite a los clientes ver sus últimas actualizaciones directamente desde su tienda.
-   **Ocultar llamada a la acción (fs\_hide\_cta)**

    -   **Qué hace este ajuste:** Controla la visibilidad del botón "Llamada a la acción" (por ejemplo, "Enviar mensaje", "Comprar ahora") que podría haber configurado en su página de Facebook.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (marcado):* El botón CTA no se mostrará en el Like Box.
        -   *Cuando está deshabilitado (desmarcado):* El botón CTA (si está configurado en su página de Facebook) será visible.
    -   **Valor recomendado:** *Deshabilitado* (desmarcado) si su CTA es relevante para los visitantes de su tienda. *Habilitado* (marcado) si prefiere centrarse solo en obtener "me gusta".
    -   **Escenario / ejemplo de comerciante:** Su página de Facebook tiene un botón "Comprar ahora". Quiere que los clientes lo usen, por lo que deja esta opción desmarcada.
-   **Encabezado pequeño (fs\_small\_header)**

    -   **Qué hace este ajuste:** Utiliza una versión más pequeña del encabezado para el Like Box/Page Plugin de Facebook.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (marcado):* El área del encabezado del Like Box será más compacta, ahorrando espacio vertical.
        -   *Cuando está deshabilitado (desmarcado):* Se utilizará el encabezado estándar, más grande.
    -   **Valor recomendado:** *Habilitado* (marcado) si desea un aspecto más aerodinámico o necesita ahorrar espacio.
    -   **Escenario / ejemplo de comerciante:** Quiere que la caja deslizante sea lo más compacta posible sin ocultar información esencial, por lo que habilita el encabezado pequeño.
-   **Deslizar al (fanslider\_slideon)**

    -   **Qué hace este ajuste:** Determina el método de interacción que hace que la caja de Facebook se deslice.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en "Click":* La caja solo se deslizará cuando el cliente haga clic explícitamente en la pestaña.
        -   *Cuando se establece en "Hover":* La caja se deslizará cuando el cliente mueva el cursor del ratón sobre la pestaña.
    -   **Valor recomendado:** "Click" es generalmente menos intrusivo y evita aperturas accidentales. "Hover" puede ser más inmediato pero podría molestar a algunos usuarios.
    -   **Escenario / ejemplo de comerciante:** Quiere asegurarse de que el deslizador solo aparezca cuando un cliente elija activamente verlo, por lo que lo configura en "Click".
-   **Posición (fs\_pos)**

    -   **Qué hace este ajuste:** Controla dónde aparece la pestaña deslizante en su sitio web.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en "Left":* La pestaña aparecerá en el lado izquierdo de la ventana del navegador.
        -   *Cuando se establece en "Right":* La pestaña aparecerá en el lado derecho de la ventana del navegador.
    -   **Valor recomendado:** "Left" o "Right", dependiendo del diseño de su tema y de dónde cause la menor interferencia con otros elementos.
    -   **Escenario / ejemplo de comerciante:** Su tema tiene un widget de chat en vivo a la derecha, por lo que configura el Facebook Fan Slider en "Left" para evitar conflictos.
-   **Color de fondo (fs\_bg\_color)**

    -   **Qué hace este ajuste:** Establece el color de fondo del propio panel deslizante (no el contenido de Facebook, sino el contenedor en el que se desliza).
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece un color específico (por ejemplo, #FFFFFF para blanco, #0000FF para azul):* El fondo de la caja deslizante cambiará a ese color.
    -   **Valor recomendado:** Un color que coincida con la marca de su tienda o un color neutro como blanco (`#FFFFFF`) o gris claro (`#F0F0F0`).
    -   **Escenario / ejemplo de comerciante:** Su marca utiliza un tono específico de azul. Introduce el código hexadecimal de ese azul para asegurarse de que el deslizador coincida con la identidad de su marca.
-   **Color del borde (fs\_br\_color)**

    -   **Qué hace este ajuste:** Establece el color del borde alrededor del panel deslizante.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece un color específico (por ejemplo, #CCCCCC para gris claro):* El borde de la caja deslizante cambiará a ese color.
    -   **Valor recomendado:** Un color sutil que complemente su color de fondo, o un color que coincida con su marca.
    -   **Escenario / ejemplo de comerciante:** Quiere un borde sutil alrededor del deslizador, por lo que elige un color gris claro (`#DDDDDD`).
-   **Idioma (fs\_langarray)**

    -   **Qué hace este ajuste:** Le permite seleccionar el idioma para el Like Box/Page Plugin de Facebook. Esto asegura que el botón "Me gusta" y otros textos generados por Facebook estén en el idioma correcto para su audiencia.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece un idioma específico (por ejemplo, "en\_US" para inglés, "fr\_FR" para francés):* El plugin de Facebook se renderizará en ese idioma.
    -   **Valor recomendado:** Seleccione el idioma principal de su tienda o de su público objetivo.
    -   **Escenario / ejemplo de comerciante:** Su tienda atiende principalmente a clientes en Francia, por lo que selecciona "fr\_FR" para mostrar el contenido de Facebook en francés.
-   **Adaptar ancho del contenedor (fs\_adapt\_container\_width)**

    -   **Qué hace este ajuste:** Le dice al Page Plugin de Facebook que adapte su ancho al ancho de su contenedor padre (la caja deslizante).
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (marcado):* El contenido de Facebook intentará llenar el `Width` que especificó para la caja deslizante, haciéndolo adaptable dentro de ese contenedor.
        -   *Cuando está deshabilitado (desmarcado):* El contenido de Facebook podría usar su ancho predeterminado, lo que podría provocar desbordamiento o espacio vacío si no coincide con su ajuste `Width`.
    -   **Valor recomendado:** *Habilitado* (marcado) para una mejor capacidad de respuesta y para asegurar que el contenido de Facebook se ajuste bien dentro de su `Width` especificado.
    -   **Escenario / ejemplo de comerciante:** Quiere que el contenido de Facebook se ajuste automáticamente al ancho de su deslizador, por lo que habilita esta opción para una apariencia más limpia.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | URL de la página de Facebook (fs\_url) | URL de su página de Facebook | Especifica qué página de Facebook mostrar. **¡CRÍTICO!** |
| Configuración del módulo | Ancho (fs\_width) | 280-300px | Establece el ancho del contenido de Facebook dentro del deslizador. |
| Configuración del módulo | Altura (fs\_height) | 400-500px (más si se muestran publicaciones) | Establece la altura del contenido de Facebook dentro del deslizador. |
| Configuración del módulo | Ocultar foto de portada (fs\_hide\_cover) | Deshabilitado (desmarcado) | Muestra/oculta la foto de portada grande de su página de Facebook. |
| Configuración del módulo | Mostrar caras de amigos (fs\_show\_facepile) | Habilitado (marcado) | Muestra fotos de perfil de amigos a los que les gusta su página (prueba social). |
| Configuración del módulo | Mostrar publicaciones (fs\_show\_posts) | Habilitado (marcado) | Muestra publicaciones recientes de su línea de tiempo de Facebook. Requiere más altura. |
| Configuración del módulo | Ocultar llamada a la acción (fs\_hide\_cta) | Deshabilitado (desmarcado) | Muestra/oculta el botón CTA configurado en su página de Facebook. |
| Configuración del módulo | Encabezado pequeño (fs\_small\_header) | Habilitado (marcado) | Utiliza un encabezado más compacto para el plugin de Facebook. |
| Configuración del módulo | Deslizar al (fanslider\_slideon) | Click | Determina si la caja se desliza al "Click" o al "Hover". "Click" es menos intrusivo. |
| Configuración del módulo | Posición (fs\_pos) | Izquierda / Derecha | Establece el lado de la pantalla donde aparece la pestaña. |
| Configuración del módulo | Color de fondo (fs\_bg\_color) | Coincide con el tema / Blanco (#FFFFFF) | Establece el color de fondo del panel deslizante. |
| Configuración del módulo | Color del borde (fs\_br\_color) | Gris sutil (#DDDDDD) | Establece el color del borde del panel deslizante. |
| Configuración del módulo | Idioma (fs\_langarray) | Idioma principal de su tienda | Establece el idioma para el texto del plugin de Facebook. |
| Configuración del módulo | Adaptar ancho del contenedor (fs\_adapt\_container\_width) | Habilitado (marcado) | Hace que el contenido de Facebook sea adaptable al ancho del deslizador. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: El deslizador de Facebook no aparece en mi tienda. ¿Qué debo comprobar primero?**
R1:

-   **Módulo habilitado:** Vaya a **Módulos > Gestor de módulos** y asegúrese de que el módulo "Facebook Fan Slider" esté instalado y habilitado.
-   **URL de la página de Facebook:** Vuelva a comprobar la `Facebook Page URL (fs_url)` en la configuración del módulo. Asegúrese de que sea la URL *exacta* de su página de Facebook (por ejemplo, `https://www.facebook.com/MyPresta.eu`) y no solo su perfil o un grupo.
-   **Caché:** Borre la caché de su PrestaShop (Vaya a **Parámetros avanzados > Rendimiento**, luego haga clic en "Borrar caché" en la esquina superior derecha). Además, borre la caché de su navegador.
-   **Conflictos de tema:** Cambie temporalmente al tema predeterminado de PrestaShop para ver si aparece el deslizador. Si lo hace, su tema personalizado podría tener conflictos de CSS o JavaScript.

**P2: El contenido de Facebook dentro del deslizador parece cortado o demasiado pequeño/grande.**
R2:

-   **Ancho y altura:** Ajuste los ajustes `Width (fs_width)` y `Height (fs_height)` en la configuración del módulo. Si está mostrando publicaciones, definitivamente necesitará más altura.
-   **Adaptar ancho del contenedor:** Asegúrese de que `Adapt Container Width (fs_adapt_container_width)` esté habilitado (marcado). Esto ayuda a que el contenido de Facebook se ajuste de forma adaptable dentro del deslizador.
-   **Encabezado pequeño:** Si está tratando de ahorrar espacio vertical, intente habilitar `Small Header (fs_small_header)`.

**P3: El idioma del Like Box de Facebook es incorrecto.**
R3:

-   **Configuración de idioma:** Vaya a la configuración del módulo y verifique el ajuste `Language (fs_langarray)`. Seleccione el código de idioma correcto para su público objetivo (por ejemplo, `en_US` para inglés de EE. UU., `fr_FR` para francés).

**P4: Cambié la configuración, pero no pasa nada en el front office.**
R4:

-   **Guardar cambios:** Siempre haga clic en el botón "Guardar" después de realizar cualquier cambio en la configuración del módulo.
-   **Borrar caché:** PrestaShop depende en gran medida del almacenamiento en caché. Después de guardar, siempre borre la caché de su PrestaShop (**Parámetros avanzados > Rendimiento > Borrar caché**) y la caché de su navegador. Esta es la razón más común por la que los cambios no aparecen inmediatamente.

**P5: El deslizador se superpone con otro elemento de mi sitio.**
R5:

-   **Posición:** Ajuste el ajuste `Position (fs_pos)` (Izquierda o Derecha) para ver si mover el deslizador al otro lado resuelve el conflicto.
-   **Ajustes de CSS (se necesita un desarrollador):** Si el problema persiste, podría requerir ajustes de CSS personalizados tanto en el deslizador como en el elemento en conflicto. Esto normalmente implicaría a un webmaster o desarrollador.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Descripción general de la arquitectura

El módulo Facebook Fan Slider (`fanslider`) es un módulo estándar de PrestaShop que implementa la clase `Module`. Principalmente aprovecha el sistema de hooks de PrestaShop para inyectar su HTML, CSS y JavaScript en el front-office. La funcionalidad principal gira en torno a la visualización del Page Plugin oficial de Facebook dentro de un elemento de interfaz de usuario deslizante personalizado. La configuración se gestiona a través del método `getContent()`, almacenando los ajustes en `ps_configuration`. El módulo no utiliza tablas de base de datos personalizadas ni clases `ObjectModel`.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Ninguno. Toda la renderización y lógica del front-office se manejan directamente dentro del archivo principal del módulo (`fanslider.php`) a través de hooks y JavaScript inyectado.
-   **Controladores de administración de Back-Office**: Ninguno. La configuración se maneja mediante el método `getContent()` de la clase principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

-   No hay clases personalizadas ni definiciones de `ObjectModel` presentes en el directorio `classes/`. La lógica del módulo está autocontenida dentro de `fanslider/fanslider.php`.

### 4.4 Activos de JavaScript (`views/js/`)

El módulo incluye varios archivos JavaScript, principalmente para la animación deslizante y la funcionalidad del selector de color.

-   `fanslider/jscolor/jscolor.js`

    -   **Alcance:** Back-office (utilizado en `getContent()` para entradas de selector de color).
    -   **Responsabilidad:** Proporciona una utilidad de selector de color JavaScript, que permite a los administradores seleccionar visualmente los colores para el fondo y el borde del deslizador. Se adjunta a los campos de entrada con la clase `jscolor`.
-   `fanslider/js/fanslider-click.js`

    -   **Alcance:** Front-office.
    -   **Responsabilidad:** Este script maneja la interacción de "clic" para el deslizador. Escucha los eventos de clic en la pestaña del deslizador y alterna la visibilidad y posición del contenedor principal del deslizador (`#fanslider`). También gestiona la clase `fanslider_open` para controlar el estado abierto/cerrado.
-   `fanslider/js/fanslider.js`

    -   **Alcance:** Front-office.
    -   **Responsabilidad:** Este es probablemente el script principal para la animación y configuración inicial del deslizador. Maneja la interacción de "hover" si está configurada, y potencialmente calcula posiciones iniciales o aplica transformaciones CSS para el efecto deslizante. Interactúa con los elementos `#fanslider` y `#fanslider_tab`.
-   `fanslider/script.js`

    -   **Alcance:** Front-office.
    -   **Responsabilidad:** Este script probablemente contiene la lógica central para inicializar el Page Plugin de Facebook (FB.init y FB.XFBML.parse) y potencialmente otra configuración general o enlace de eventos relacionados con el comportamiento del deslizador. Asegura que el SDK de Facebook se cargue y que el plugin se renderice correctamente.

### 4.5 Hojas de estilo CSS (`views/css/`)

El módulo no lista explícitamente archivos CSS en `views/css/`. El estilo del deslizador probablemente está incrustado directamente dentro del método `hookDisplayHeader` del archivo `fanslider.php` o dentro de la plantilla `rightcolumn.tpl`, o generado dinámicamente en función de la configuración. Los desarrolladores deben inspeccionar el HTML generado y el archivo principal del módulo en busca de estilos en línea o bloques `<style>`.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **Plantillas de Hook (`views/templates/hook/`)**:
    -   `fanslider/views/templates/hook/rightcolumn.tpl`
        -   **Hook:** Esta plantilla está diseñada principalmente para ser renderizada en un hook que permite la inyección de contenido en la página, como `displayFooter` o `displayHeader` (aunque su nombre sugiere `displayRightColumn`, la implementación del módulo lo coloca como un elemento fijo).
        -   **Bloque visual:** Esta plantilla genera la estructura HTML principal para el Facebook Fan Slider. Normalmente incluye:
            -   El contenedor principal para el deslizador (`#fanslider`).
            -   La pestaña clicable (`#fanslider_tab`).
            -   El contenedor para el Page Plugin de Facebook (`<div class="fb-page">`).
            -   Recibe variables de configuración del módulo para establecer dinámicamente atributos para el Page Plugin de Facebook (por ejemplo, `data-href`, `data-width`, `data-height`, `data-hide-cover`, `data-show-facepile`, `data-show-posts`, `data-hide-cta`, `data-small-header`, `data-adapt-container-width`).
            -   También incluye el `div` necesario para que el SDK de Facebook renderice el plugin.

### 4.7 Esquema de la base de datos y mapa de Hooks

-   **Tablas de la base de datos**:

    -   El módulo no crea ninguna tabla de base de datos personalizada.
    -   Todos los ajustes de configuración se almacenan en la tabla `ps_configuration` utilizando claves con el prefijo `FS_` o `FANSIDER_` (por ejemplo, `FS_WIDTH`, `FANSIDER_SLIDEON`).
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | Se ejecuta en la sección `<head>` de cada página. | Inyecta los archivos CSS y JavaScript necesarios, y potencialmente el script de inicialización del SDK de Facebook. También puede generar estilos en línea basados en la configuración. |
| `displayFooter` | Se ejecuta en la parte inferior de cada página, antes de la etiqueta de cierre `</body>`. | Renderiza la estructura HTML principal del Facebook Fan Slider (desde `rightcolumn.tpl`) y asegura que el SDK de Facebook se cargue y el Page Plugin se inicialice después de que el DOM esté listo. Aquí es donde se añade el componente visual a la página. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas versiones, actualizaciones y soporte profesional para el módulo Facebook Fan Slider, visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener.
