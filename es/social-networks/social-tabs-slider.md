---
title: "Slider de pestañas sociales - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Slider de pestañas sociales' de MyPresta.eu."
sidebar:
  label: "Slider de pestañas sociales - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Social tabs slider en MyPresta.eu](https://mypresta.eu/modules/social-networks/social-tabs-slider.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/social-tabs-slider/)
>
> ---


# Slider de pestañas sociales

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y garantizan una comunicación adecuada con las API de redes sociales.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla principal donde configurará todas las opciones para su Slider de pestañas sociales.

#### Configuración general

- **Plantilla:**

  - **Qué hace este ajuste:** Le permite elegir el estilo visual y el diseño de sus pestañas sociales. El módulo viene con varias plantillas prediseñadas.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en Plantilla 1, 2, 3, etc.:* La apariencia de los iconos sociales, el diseño de la pestaña y, potencialmente, el estilo de animación cambiarán en su front office.
  - **Valor recomendado:** Experimente para encontrar el que mejor se adapte al tema de su tienda.
  - **Escenario / ejemplo de comerciante:** Si su tienda tiene un diseño minimalista, podría elegir una plantilla con iconos limpios y planos. Si prefiere un aspecto más vibrante, otra plantilla podría ofrecer iconos coloridos y brillantes.
- **Posición:**

  - **Qué hace este ajuste:** Determina dónde aparecerá el slider de pestañas sociales en su sitio web.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en "Izquierda":* El slider se fijará en el lado izquierdo de la ventana del navegador.
    - *Cuando se establece en "Derecha":* El slider se fijará en el lado derecho de la ventana del navegador.
  - **Valor recomendado:** "Izquierda" o "Derecha" dependiendo del diseño de su tema y de dónde cause menos interferencia con otros elementos.
  - **Escenario / ejemplo de comerciante:** Si su tema tiene una barra lateral izquierda, podría elegir "Derecha" para evitar el desorden. Si su tema es ancho y centrado, tanto "Izquierda" como "Derecha" podrían funcionar bien.
- **Última pestaña abierta por defecto:**

  - **Qué hace este ajuste:** Controla si una de las pestañas sociales debe abrirse automáticamente cuando un visitante llega por primera vez a su página.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en "SÍ":* La última pestaña social que fue abierta por un visitante anterior (o una predeterminada si no hay historial) se deslizará automáticamente cuando llegue un nuevo visitante.
    - *Cuando se establece en "NO":* Todas las pestañas sociales permanecerán cerradas hasta que el visitante haga clic o pase el ratón activamente por una de ellas.
  - **Valor recomendado:** "NO" para evitar molestar a los visitantes con una pestaña que se abre automáticamente.
  - **Escenario / ejemplo de comerciante:** Podría configurarlo en "SÍ" temporalmente si está ejecutando una campaña especial en una red social y quiere llamar la atención de inmediato, pero generalmente, "NO" proporciona una mejor experiencia de usuario.

#### Configuración del cuadro de "Me gusta" de Facebook

- **Mostrar cuadro de "Me gusta" de Facebook:**

  - **Qué hace este ajuste:** Alterna la visibilidad de la pestaña de Facebook y su cuadro de "Me gusta" incrustado.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* La pestaña de Facebook aparecerá en el slider y, cuando se abra, mostrará su cuadro de "Me gusta" de la página de fans de Facebook.
    - *Cuando está deshabilitado (NO):* La pestaña de Facebook no se mostrará en el slider.
  - **Valor recomendado:** "SÍ" si tiene una página de Facebook activa que desea promocionar.
  - **Escenario / ejemplo de comerciante:** Si Facebook es un canal principal para la interacción con el cliente y el marketing, definitivamente querrá tener esto habilitado.
- **Altura del cuadro de "Me gusta" de Facebook:**

  - **Qué hace este ajuste:** Establece el tamaño vertical del área de contenido del cuadro de "Me gusta" de Facebook cuando la pestaña está abierta.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en un valor más alto (por ejemplo, 500px):* Más contenido (publicaciones, caras) de su página de Facebook será visible dentro de la pestaña.
    - *Cuando se establece en un valor más bajo (por ejemplo, 200px):* Menos contenido será visible, lo que requerirá desplazamiento si el feed es largo.
  - **Valor recomendado:** Comience con `280px` y ajuste según la cantidad de contenido que desee mostrar y cómo se vea en su sitio.
  - **Escenario / ejemplo de comerciante:** Si publica con frecuencia y desea que los visitantes vean más de su actividad reciente, aumente la altura.
- **Esquema de color del cuadro de "Me gusta" de Facebook:**

  - **Qué hace este ajuste:** Cambia el tema de color del propio cuadro de "Me gusta" de Facebook (no el icono de la pestaña).
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en "Claro":* El fondo y el texto del cuadro de "Me gusta" usarán colores más claros.
    - *Cuando se establece en "Oscuro":* El fondo y el texto del cuadro de "Me gusta" usarán colores más oscuros.
  - **Valor recomendado:** Elija "Claro" u "Oscuro" para que coincida mejor con el diseño general de su tienda.
  - **Escenario / ejemplo de comerciante:** Si su sitio web tiene un fondo oscuro, un esquema de color "Oscuro" para el cuadro de "Me gusta" podría integrarse mejor visualmente.
- **Mostrar caras del cuadro de "Me gusta" de Facebook:**

  - **Qué hace este ajuste:** Determina si las fotos de perfil de las personas a las que les gusta su página se muestran en el cuadro de "Me gusta".
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* Se mostrará una fila de fotos de perfil de los fans de su página.
    - *Cuando está deshabilitado (NO):* Las fotos de perfil no se mostrarán.
  - **Valor recomendado:** "SÍ", ya que añade un elemento de prueba social, mostrando que a personas reales les gusta su página.
  - **Escenario / ejemplo de comerciante:** Mostrar caras puede animar a otros a dar "Me gusta" a su página, ya que demuestra popularidad.
- **Color del borde del cuadro de "Me gusta" de Facebook:**

  - **Qué hace este ajuste:** Establece el color del borde alrededor del cuadro de "Me gusta" de Facebook.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en un color específico (por ejemplo, #CCCCCC):* El borde aparecerá en ese color.
  - **Valor recomendado:** Un color que complemente el diseño de su sitio web o que sea transparente/invisible si lo prefiere.
  - **Escenario / ejemplo de comerciante:** Podría usar el color principal de su marca para el borde para reforzar la marca.
- **Mostrar flujo del cuadro de "Me gusta" de Facebook:**

  - **Qué hace este ajuste:** Controla si sus publicaciones recientes de Facebook (el "flujo") se muestran dentro del cuadro de "Me gusta".
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* Sus últimas publicaciones de Facebook serán visibles en la pestaña.
    - *Cuando está deshabilitado (NO):* Solo se mostrará el botón "Me gusta" y, potencialmente, las caras, sin el flujo de publicaciones.
  - **Valor recomendado:** "SÍ" para proporcionar contenido fresco y fomentar la interacción.
  - **Escenario / ejemplo de comerciante:** Si comparte regularmente noticias, promociones o actualizaciones de productos en Facebook, mostrar el flujo mantiene informados a los visitantes.
- **Mostrar encabezado del cuadro de "Me gusta" de Facebook:**

  - **Qué hace este ajuste:** Alterna la visibilidad del encabezado "Encuéntranos en Facebook" en la parte superior del cuadro de "Me gusta".
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* Se mostrará el encabezado.
    - *Cuando está deshabilitado (NO):* El encabezado se ocultará, haciendo que el cuadro de "Me gusta" sea más compacto.
  - **Valor recomendado:** "SÍ" para mayor claridad, o "NO" si desea un aspecto más limpio y asume que los usuarios entienden que es Facebook.
  - **Escenario / ejemplo de comerciante:** Si el espacio es limitado, ocultar el encabezado puede ahorrar espacio vertical.
- **URL de la página de fans de Facebook:**

  - **Qué hace este ajuste:** Este es el ajuste más crucial para Facebook. Debe introducir la URL completa de su página de fans de Facebook.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se introduce correctamente:* La pestaña de Facebook mostrará el cuadro de "Me gusta" para su página especificada.
    - *Cuando es incorrecto o está vacío:* La pestaña de Facebook puede no mostrarse correctamente o mostrará un error.
  - **Valor recomendado:** Su URL exacta de la página de fans de Facebook (por ejemplo, `https://www.facebook.com/MyPresta`).
  - **Escenario / ejemplo de comerciante:** Copie y pegue la URL directamente desde su navegador cuando vea su página de Facebook para asegurar la precisión.

#### Configuración de Google+

- **Mostrar seguimiento de Google+:**

  - **Qué hace este ajuste:** Alterna la visibilidad de la pestaña de Google+ y su botón/perfil de seguimiento incrustado.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* La pestaña de Google+ aparecerá en el slider.
    - *Cuando está deshabilitado (NO):* La pestaña de Google+ no se mostrará.
  - **Valor recomendado:** "SÍ" si utiliza activamente Google+ (aunque su uso ha disminuido, aún podría ser relevante para algunos nichos).
  - **Escenario / ejemplo de comerciante:** Si su negocio tiene una fuerte presencia en Google My Business o estrategias de SEO local específicas que involucran Google+, esto puede ser beneficioso.
- **ID de perfil de Google+:**

  - **Qué hace este ajuste:** Debe proporcionar su ID de perfil de Google+ (una cadena numérica) para que el módulo muestre el perfil correcto.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se introduce correctamente:* La pestaña de Google+ mostrará el botón/perfil de seguimiento para su ID especificada.
    - *Cuando es incorrecto o está vacío:* La pestaña de Google+ puede no mostrarse correctamente.
  - **Valor recomendado:** Su ID de perfil de Google+.
  - **Escenario / ejemplo de comerciante:** Encuentre su ID de Google+ navegando a la página de su perfil de Google+ y mirando la URL (suele ser una cadena larga de números).

#### Configuración de Twitter

- **Mostrar línea de tiempo de usuario de Twitter:**

  - **Qué hace este ajuste:** Alterna la visibilidad de la pestaña de Twitter y su widget de línea de tiempo de usuario incrustado.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* La pestaña de Twitter aparecerá en el slider, mostrando sus tweets recientes.
    - *Cuando está deshabilitado (NO):* La pestaña de Twitter no se mostrará.
  - **Valor recomendado:** "SÍ" si tiene una cuenta de Twitter activa para su negocio.
  - **Escenario / ejemplo de comerciante:** Si utiliza Twitter para el servicio al cliente, anuncios o ventas flash, esta es una excelente manera de mantener a los visitantes actualizados.
- **Nombre de usuario de Twitter:**

  - **Qué hace este ajuste:** Especifica la cuenta de Twitter cuya línea de tiempo se mostrará.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se introduce correctamente (por ejemplo, MyPresta):* La pestaña de Twitter mostrará los tweets de ese nombre de usuario.
    - *Cuando es incorrecto o está vacío:* La pestaña de Twitter puede no mostrarse correctamente.
  - **Valor recomendado:** Su nombre de usuario de Twitter (sin el símbolo "@").
  - **Escenario / ejemplo de comerciante:** Introduzca `MyPresta` si su nombre de usuario de Twitter es `@MyPresta`.
- **ID de widget de Twitter:**

  - **Qué hace este ajuste:** Este es un ID único generado por Twitter cuando crea un widget de línea de tiempo incrustado. Es crucial para que el widget funcione.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se introduce correctamente:* La línea de tiempo de Twitter se cargará y mostrará correctamente.
    - *Cuando es incorrecto o está vacío:* La pestaña de Twitter probablemente mostrará un error o permanecerá en blanco.
  - **Valor recomendado:** Su ID de widget de Twitter.
  - **Escenario / ejemplo de comerciante:** Para obtener esto, vaya a [Twitter Publish](https://publish.twitter.com/), seleccione "Línea de tiempo incrustada", introduzca la URL de su perfil y copie el `data-widget-id` del código generado.

#### Configuración de YouTube

- **Mostrar cuenta de YouTube:**

  - **Qué hace este ajuste:** Alterna la visibilidad de la pestaña de YouTube y su canal/feed de usuario incrustado.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* La pestaña de YouTube aparecerá en el slider.
    - *Cuando está deshabilitado (NO):* La pestaña de YouTube no se mostrará.
  - **Valor recomendado:** "SÍ" si tiene un canal de YouTube con videos de productos, tutoriales o contenido de marca.
  - **Escenario / ejemplo de comerciante:** Si vende productos que se benefician de demostraciones en video, esta es una excelente manera de mostrarlos.
- **Nombre de usuario de YouTube:**

  - **Qué hace este ajuste:** Especifica el canal o usuario de YouTube cuyos videos se mostrarán.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se introduce correctamente:* La pestaña de YouTube mostrará contenido de ese canal/usuario.
    - *Cuando es incorrecto o está vacío:* La pestaña de YouTube puede no mostrarse correctamente.
  - **Valor recomendado:** El nombre de URL personalizado de su canal de YouTube o el nombre de usuario heredado.
  - **Escenario / ejemplo de comerciante:** Si la URL de su canal de YouTube es `youtube.com/user/MyPrestaVideos`, su nombre de usuario sería `MyPrestaVideos`. Si es `youtube.com/c/MyPresta`, es posible que deba encontrar el nombre de usuario heredado o el ID del canal.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | **Plantilla** | (Elija el que mejor se adapte) | Cambia el estilo visual de las pestañas sociales. |
| | **Posición** | Derecha | Determina si las pestañas aparecen en el lado izquierdo o derecho del navegador. |
| | **Última pestaña abierta por defecto** | NO | Controla si una pestaña se abre automáticamente al cargar la página. |
| | **Mostrar cuadro de "Me gusta" de Facebook** | SÍ | Muestra/oculta la pestaña de Facebook. |
| | **Altura del cuadro de "Me gusta" de Facebook** | 280px | Establece la altura del área de contenido de Facebook. |
| | **Esquema de color del cuadro de "Me gusta" de Facebook** | Claro | Cambia el tema de color del cuadro de "Me gusta" de Facebook. |
| | **Mostrar caras del cuadro de "Me gusta" de Facebook** | SÍ | Muestra las fotos de perfil de los fans. |
| | **Color del borde del cuadro de "Me gusta" de Facebook** | (vacío/transparente) | Establece el color del borde del cuadro de "Me gusta". |
| | **Mostrar flujo del cuadro de "Me gusta" de Facebook** | SÍ | Muestra las publicaciones recientes de Facebook. |
| | **Mostrar encabezado del cuadro de "Me gusta" de Facebook** | SÍ | Muestra/oculta el encabezado "Encuéntranos en Facebook". |
| | **URL de la página de fans de Facebook** | (Su URL de Facebook) | **CRÍTICO:** URL de su página de fans de Facebook. |
| | **Mostrar seguimiento de Google+** | NO | Muestra/oculta la pestaña de Google+. |
| | **ID de perfil de Google+** | (Su ID de Google+) | **CRÍTICO:** Su ID numérica de perfil de Google+. |
| | **Mostrar línea de tiempo de usuario de Twitter** | SÍ | Muestra/oculta la pestaña de Twitter. |
| | **Nombre de usuario de Twitter** | (Su nombre de usuario de Twitter) | **CRÍTICO:** Su nombre de usuario de Twitter (por ejemplo, `MyPresta`). |
| | **ID de widget de Twitter** | (Su ID de widget de Twitter) | **CRÍTICO:** ID única para su widget de línea de tiempo de Twitter. |
| | **Mostrar cuenta de YouTube** | SÍ | Muestra/oculta la pestaña de YouTube. |
| | **Nombre de usuario de YouTube** | (Su nombre de usuario de YouTube) | **CRÍTICO:** El nombre de usuario o ID heredado de su canal de YouTube. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Las pestañas sociales no aparecen en mi tienda, o solo se muestran algunas de ellas.**
**R1:**

-   **Verificar el estado del módulo:** Vaya a **Módulos > Gestor de módulos** y asegúrese de que "Slider de pestañas sociales" esté instalado y habilitado.
-   **Verificar la configuración:** Vaya a la página de configuración del módulo. Asegúrese de que "Mostrar cuadro de "Me gusta" de Facebook", "Mostrar seguimiento de Google+", etc., estén configurados en "SÍ" para las pestañas que desea mostrar.
-   **IDs/URLs correctas:** Vuelva a verificar que su URL de la página de fans de Facebook, ID de perfil de Google+, nombre de usuario/ID de widget de Twitter y nombre de usuario de YouTube se hayan introducido *exactamente* como se requiere. Un solo error tipográfico evitará que la pestaña se cargue.
-   **Compatibilidad del tema:** Algunos temas altamente personalizados pueden tener problemas con los hooks del módulo. Intente cambiar temporalmente al tema predeterminado de PrestaShop para ver si aparecen las pestañas. Si lo hacen, su tema podría requerir pequeños ajustes.
-   **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, los archivos de caché antiguos impiden que aparezca el nuevo contenido del módulo.

**P2: Mi pestaña de Facebook/Twitter/YouTube muestra un error o está en blanco cuando se abre.**
**R2:**

-   **IDs/URLs incorrectas:** Esta es la razón más común. Vuelva a verificar cada carácter de su URL de la página de fans de Facebook, ID de perfil de Google+, nombre de usuario de Twitter, ID de widget de Twitter y nombre de usuario de YouTube. Incluso una barra inclinada faltante o un espacio extra pueden causar problemas.
-   **Cambios en la API:** Las plataformas de redes sociales ocasionalmente actualizan sus API o códigos de incrustación. Asegúrese de que su versión del módulo esté actualizada desde MyPresta.eu.
-   **Configuración de privacidad:** Asegúrese de que sus páginas/perfiles de redes sociales sean públicos y accesibles. Si están configurados como privados, el módulo no podrá mostrar su contenido.
-   **Problemas de red:** Deshabilite temporalmente cualquier bloqueador de anuncios o extensiones del navegador que puedan interferir con los widgets de redes sociales.

**P3: Las pestañas sociales se ven extrañas o desalineadas en mi dispositivo móvil.**
**R3:**

-   **Capacidad de respuesta del tema:** Si bien el módulo está diseñado para ser responsivo, su apariencia puede verse afectada por la capacidad de respuesta general del tema de su PrestaShop.
-   **Conflictos de CSS:** El CSS de su tema podría estar anulando el estilo del módulo. Si tiene un webmaster, puede inspeccionar los elementos utilizando las herramientas de desarrollador del navegador para identificar conflictos.
-   **Plantilla del módulo:** Intente cambiar a una "Plantilla" diferente en la configuración del módulo para ver si una se adapta mejor a los dispositivos móviles.
-   **Borrar caché:** Siempre borre la caché de su PrestaShop después de realizar cambios de configuración.

**P4: ¿Cómo obtengo mi ID de widget de Twitter?**
**R4:**

1.  Vaya a [Twitter Publish](https://publish.twitter.com/).
2.  Seleccione "Línea de tiempo incrustada".
3.  Introduzca la URL completa de su perfil de Twitter (por ejemplo, `https://twitter.com/MyPresta`).
4.  Haga clic en la flecha y luego seleccione "Línea de tiempo incrustada".
5.  Twitter generará un código. Busque `data-widget-id="SU_ID_DE_WIDGET_AQUÍ"` dentro de ese código. Copie solo el ID numérico.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Descripción general de la arquitectura

El módulo "Slider de pestañas sociales" es un módulo clásico de PrestaShop implementado como un único archivo PHP (`socialslider.php`) siguiendo la estructura de módulos de PrestaShop. Aprovecha el sistema de hooks de PrestaShop para inyectar su CSS, JavaScript y contenido HTML en el front office. La configuración se gestiona a través del método `getContent()` en la clase principal del módulo, almacenando la configuración en `ps_configuration`. El módulo utiliza bibliotecas JavaScript externas (jscolor) y scripts personalizados para manejar la animación deslizante y la carga de widgets de redes sociales.

### 4.2 Controladores (`controllers/`)

Este módulo **no** utiliza controladores de Front-Office o Back-Office Admin personalizados. Toda la lógica está encapsulada dentro del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo **no** define ninguna clase personalizada ni extiende `ObjectModel`. Toda la lógica principal reside dentro de la clase `Socialslider` en `socialslider.php`. Los valores de configuración se almacenan directamente en la tabla `ps_configuration` utilizando `Configuration::get()` y `Configuration::updateValue()`.

### 4.4 Activos de JavaScript (`views/js/`)

El módulo incluye varios archivos JavaScript para gestionar su funcionalidad:

-   `socialslider/jscolor/jscolor.js`
    -   **Alcance:** Back-office (utilizado en `getContent()` para la entrada del selector de color).
    -   **Responsabilidad:** Proporciona una funcionalidad de selector de color JavaScript para los campos de entrada, específicamente para la configuración del color del borde de Facebook.
-   `socialslider/left.js`
    -   **Alcance:** Front-office.
    -   **Responsabilidad:** Contiene la lógica JavaScript para la animación deslizante y la interacción de las pestañas cuando el slider se posiciona en el lado **izquierdo** de la pantalla. Maneja la apertura/cierre de pestañas, la carga dinámica de contenido de redes sociales y, potencialmente, la gestión de cookies para la función "última pestaña abierta".
-   `socialslider/right.js`
    -   **Alcance:** Front-office.
    -   **Responsabilidad:** Contiene la lógica JavaScript para la animación deslizante y la interacción de las pestañas cuando el slider se posiciona en el lado **derecho** de la pantalla. Similar a `left.js` pero adaptado para el posicionamiento en el lado derecho.

### 4.5 Hojas de estilo CSS (`views/css/`)

El módulo utiliza un enfoque basado en plantillas para su estilo, con archivos CSS separados para cada plantilla y posición.

-   `socialslider/templates/1/css/left.css`
    -   **Alcance:** Front-office (para Plantilla 1, posición izquierda).
    -   **Responsabilidad:** Define los estilos visuales para las pestañas sociales, los iconos y el contenedor del slider cuando se selecciona la Plantilla 1 y el slider está a la izquierda.
    -   **Selectores clave:** `.socialslider_left`, `.socialslider_tab`, `.socialslider_tab_icon`, `.socialslider_content`.
-   `socialslider/templates/1/css/right.css`
    -   **Alcance:** Front-office (para Plantilla 1, posición derecha).
    -   **Responsabilidad:** Define los estilos visuales para las pestañas sociales, los iconos y el contenedor del slider cuando se selecciona la Plantilla 1 y el slider está a la derecha.
    -   **Selectores clave:** `.socialslider_right`, `.socialslider_tab`, `.socialslider_tab_icon`, `.socialslider_content`.
-   `socialslider/templates/2/css/left.css`
    -   **Alcance:** Front-office (para Plantilla 2, posición izquierda).
    -   **Responsabilidad:** Estilo para la Plantilla 2, posición izquierda.
-   `socialslider/templates/2/css/right.css`
    -   **Alcance:** Front-office (para Plantilla 2, posición derecha).
    -   **Responsabilidad:** Estilo para la Plantilla 2, posición derecha.
-   `socialslider/templates/3/css/left.css`
    -   **Alcance:** Front-office (para Plantilla 3, posición izquierda).
    -   **Responsabilidad:** Estilo para la Plantilla 3, posición izquierda.
-   `socialslider/templates/3/css/right.css`
    -   **Alcance:** Front-office (para Plantilla 3, posición derecha).
    -   **Responsabilidad:** Estilo para la Plantilla 3, posición derecha.
-   `socialslider/templates/4/css/left.css`
    -   **Alcance:** Front-office (para Plantilla 4, posición izquierda).
    -   **Responsabilidad:** Estilo para la Plantilla 4, posición izquierda.
-   `socialslider/templates/4/css/right.css`
    -   **Alcance:** Front-office (para Plantilla 4, posición derecha).
    -   **Responsabilidad:** Estilo para la Plantilla 4, posición derecha.
-   `socialslider/templates/5/css/left.css`
    -   **Alcance:** Front-office (para Plantilla 5, posición izquierda).
    -   **Responsabilidad:** Estilo para la Plantilla 5, posición izquierda.
-   `socialslider/templates/5/css/right.css`
    -   **Alcance:** Front-office (para Plantilla 5, posición derecha).
    -   **Responsabilidad:** Estilo para la Plantilla 5, posición derecha.
-   `socialslider/templates/6/css/left.css`
    -   **Alcance:** Front-office (para Plantilla 6, posición izquierda).
    -   **Responsabilidad:** Estilo para la Plantilla 6, posición izquierda.
-   `socialslider/templates/6/css/right.css`
    -   **Alcance:** Front-office (para Plantilla 6, posición derecha).
    -   **Responsabilidad:** Estilo para la Plantilla 6, posición derecha.

Los desarrolladores pueden anular estos estilos en el `custom.css` de su tema o creando un tema hijo.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

El módulo utiliza plantillas Smarty para renderizar su contenido de front-office y para el formulario de configuración del back-office.

-   **Plantillas de hook (`views/templates/hook/`)**:
    -   `socialslider/header.tpl`
        -   **Hook:** `displayHeader`
        -   **Salida:** Esta plantilla es responsable de incluir los archivos CSS y JavaScript necesarios dinámicamente según la configuración del módulo (por ejemplo, cargando `left.js` o `right.js`, y el CSS específico de la plantilla correcta). También incluye los SDK/widgets de Facebook, Twitter y Google+ si están habilitados.
    -   `socialslider/top.tpl`
        -   **Hook:** `displayTop`
        -   **Salida:** Esta es la plantilla principal que renderiza la estructura HTML del propio slider de pestañas sociales. Genera los elementos `div` para el contenedor del slider, las pestañas individuales (Facebook, Google+, Twitter, YouTube) y sus respectivas áreas de contenido, poblándolas con los valores de configuración.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:
    El módulo no crea ninguna tabla SQL personalizada. Todas las configuraciones se almacenan en la tabla estándar `ps_configuration` de PrestaShop.

    -   `ps_configuration` (o `_configuration` con su prefijo): Almacena pares clave-valor para la configuración del módulo, por ejemplo, `SS_TEMPLATE`, `SS_POSITION`, `SS_FCB_FANPAGEURL`.
-   **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Inyecta los archivos CSS y JavaScript del módulo, y los SDK/scripts de widgets de plataformas de redes sociales (SDK de Facebook, script de widget de Twitter, script de Google+). |
| `displayTop` | Típicamente en la parte superior del área de contenido, debajo del encabezado principal. | Renderiza la estructura HTML principal del slider de pestañas sociales (el contenedor fijo, las pestañas individuales y sus áreas de contenido). |
| `header` | (Alias para `displayHeader` en algunas versiones de PrestaShop, o utilizado para temas antiguos) | Igual que `displayHeader`, asegura la compatibilidad para inyectar activos. |

## 5. Soporte oficial y actualizaciones

Para actualizaciones oficiales, correcciones de errores y soporte para desarrolladores del módulo "Slider de pestañas sociales", consulte su cuenta de cliente de MyPresta.eu. Puede descargar las últimas versiones y acceder a los recursos de soporte directamente desde su historial de pedidos.
