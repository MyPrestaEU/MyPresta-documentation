---
title: "Feed de etiquetas de productos de Instagram - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Feed de etiquetas de productos de Instagram' de MyPresta.eu."
sidebar:
  label: "Feed de etiquetas de productos de Instagram - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Instagram product tag feed en MyPresta.eu](https://mypresta.eu/modules/social-networks/instagram-product-tag-feed.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/instagram-product-tag-feed/)
>
> ---


# Feed de etiquetas de productos de Instagram

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para la comunicación API, las cuales están casi universalmente disponibles en entornos de alojamiento modernos.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Para acceder a la configuración del módulo, vaya a **Módulos > Gestor de módulos** en su Back Office de PrestaShop, busque "Feed de etiquetas de productos de Instagram" y haga clic en el botón "Configurar".

Aquí encontrará las principales opciones de configuración para controlar cómo se muestran sus feeds de Instagram.

#### Configuración general

-   **Token de acceso de Instagram:**

    -   **Qué hace esta configuración:** Este es un código único que otorga a su tienda PrestaShop permiso para acceder a los datos públicos de su cuenta de Instagram (como fotos asociadas con etiquetas específicas). Debe generar este token desde las herramientas de desarrollador de Instagram o una herramienta de terceros que simplifique el proceso.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando se ingresa correctamente:* Su módulo podrá obtener y mostrar fotos de Instagram.
        -   *Cuando es incorrecto o está vacío:* El módulo no podrá conectarse a Instagram y no se mostrarán fotos, lo que resultará en un feed vacío o un mensaje de error.
    -   **Valor recomendado:** Su token de acceso de Instagram válido.
    -   **Escenario / ejemplo de comerciante:** Acaba de configurar su cuenta de Instagram Business. Deberá seguir las instrucciones de Instagram (o usar una herramienta de ayuda) para obtener este token y pegarlo aquí. Sin él, el módulo no puede "ver" sus fotos de Instagram.
-   **ID de usuario de Instagram:**

    -   **Qué hace esta configuración:** Este es el identificador numérico único de su cuenta de Instagram. A menudo se requiere junto con el token de acceso para obtener datos correctamente.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando se ingresa correctamente:* Asegura que el módulo obtenga datos de su cuenta de Instagram específica.
        -   *Cuando es incorrecto o está vacío:* Puede provocar errores al obtener datos o al obtener datos de la cuenta incorrecta, lo que resulta en un feed vacío o incorrecto.
    -   **Valor recomendado:** Su ID de usuario de Instagram válido.
    -   **Escenario / ejemplo de comerciante:** Similar al token de acceso, obtendrá este ID al configurar su acceso a la API de Instagram. Le dice al módulo *de quién* es el feed de Instagram que debe buscar.
-   **Número de fotos a mostrar:**

    -   **Qué hace esta configuración:** Controla cuántas fotos de Instagram se obtienen y se muestran en una sola instancia de feed.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando se establece un número mayor (por ejemplo, 10):* Se cargarán y potencialmente se mostrarán más fotos en el feed, lo que lo hará más rico pero posiblemente más lento de cargar.
        -   *Cuando se establece un número menor (por ejemplo, 3):* Se mostrarán menos fotos, lo que resultará en un feed más conciso y tiempos de carga más rápidos.
    -   **Valor recomendado:** Comience con 6-9 fotos para un buen equilibrio entre contenido y rendimiento. Ajuste según su diseño y pruebas de velocidad de página.
    -   **Escenario / ejemplo de comerciante:** Para una pestaña de página de producto, es posible que desee 6 fotos. Para un carrusel de página de inicio, es posible que desee 12 para dar más variedad a medida que los usuarios se desplazan.
-   **Mostrar en la página de inicio:**

    -   **Qué hace esta configuración:** Un simple interruptor para habilitar o deshabilitar el feed de Instagram en la página de inicio de su tienda.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* El módulo intentará mostrar un feed de Instagram en su página de inicio (generalmente a través del hook `displayHome`).
        -   *Cuando está deshabilitado:* No aparecerá ningún feed de Instagram en su página de inicio.
    -   **Valor recomendado:** SÍ, si desea mostrar su contenido de Instagram de forma destacada. NO, si prefiere una página de inicio más limpia o solo desea feeds en las páginas de productos.
    -   **Escenario / ejemplo de comerciante:** Desea mostrar sus últimas fotos de estilo de vida en la página de inicio para atraer a los visitantes de inmediato. Habilitaría esto.
-   **Mostrar en la página de producto:**

    -   **Qué hace esta configuración:** Un simple interruptor para habilitar o deshabilitar el feed de Instagram en las páginas de productos individuales.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* El módulo intentará mostrar un feed de Instagram específico del producto en sus páginas de productos (generalmente a través de los hooks `displayProductTab` o `displayProductExtraContent`).
        -   *Cuando está deshabilitado:* No aparecerá ningún feed de Instagram en las páginas de productos.
    -   **Valor recomendado:** SÍ, ya que esta es una de las características principales del módulo y una poderosa herramienta de conversión.
    -   **Escenario / ejemplo de comerciante:** Vende zapatos y desea mostrar fotos de Instagram de personas usando *ese modelo de zapato específico* en su página de producto. Habilitaría esto.
-   **Mostrar en la columna izquierda:**

    -   **Qué hace esta configuración:** Controla si el feed de Instagram aparece en la columna de la barra lateral izquierda de su tienda.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Se renderizará un feed en la columna izquierda en las páginas donde esté enganchado.
        -   *Cuando está deshabilitado:* No hay feed en la columna izquierda.
    -   **Valor recomendado:** NO, a menos que tenga una necesidad de diseño muy específica. Las columnas pueden saturarse.
    -   **Escenario / ejemplo de comerciante:** Desea un feed pequeño y persistente visible mientras los clientes navegan por las categorías.
-   **Mostrar en la columna derecha:**

    -   **Qué hace esta configuración:** Controla si el feed de Instagram aparece en la columna de la barra lateral derecha de su tienda.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Se renderizará un feed en la columna derecha en las páginas donde esté enganchado.
        -   *Cuando está deshabilitado:* No hay feed en la columna derecha.
    -   **Valor recomendado:** NO, a menos que tenga una necesidad de diseño muy específica. Las columnas pueden saturarse.
    -   **Escenario / ejemplo de comerciante:** Similar a la columna izquierda, para un feed persistente y más pequeño.
-   **Mostrar en el pie de página:**

    -   **Qué hace esta configuración:** Controla si el feed de Instagram aparece en el área del pie de página de su tienda.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Se renderizará un feed en el pie de página.
        -   *Cuando está deshabilitado:* No hay feed en el pie de página.
    -   **Valor recomendado:** SÍ, para una forma sutil pero efectiva de mostrar su Instagram. Es menos intrusivo que las columnas.
    -   **Escenario / ejemplo de comerciante:** Desea agregar una sección visualmente atractiva en la parte inferior de cada página, animando a los visitantes a explorar su Instagram.
-   **Mostrar en el encabezado (izquierda):**

    -   **Qué hace esta configuración:** Controla si el feed de Instagram aparece en la parte izquierda del encabezado de su tienda.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Se renderizará un feed en la sección izquierda del encabezado.
        -   *Cuando está deshabilitado:* No hay feed en el encabezado.
    -   **Valor recomendado:** NO, los encabezados suelen estar reservados para la navegación y la marca.
    -   **Escenario / ejemplo de comerciante:** Diseño muy específico en el que desea un pequeño icono de Instagram giratorio o una sola imagen en el encabezado.
-   **Mostrar en el encabezado (derecha):**

    -   **Qué hace esta configuración:** Controla si el feed de Instagram aparece en la parte derecha del encabezado de su tienda.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Se renderizará un feed en la sección derecha del encabezado.
        -   *Cuando está deshabilitado:* No hay feed en el encabezado.
    -   **Valor recomendado:** NO, los encabezados suelen estar reservados para la navegación y la marca.
    -   **Escenario / ejemplo de comerciante:** Similar al encabezado (izquierda).
-   **Función de carrusel:**

    -   **Qué hace esta configuración:** Habilita o deshabilita la funcionalidad de carrusel (galería deslizante) para los feeds de Instagram.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Las fotos se mostrarán en un carrusel horizontal y desplazable, ahorrando espacio y permitiendo a los usuarios navegar por muchas imágenes fácilmente.
        -   *Cuando está deshabilitado:* Las fotos probablemente se mostrarán en una cuadrícula o lista estática, dependiendo de la plantilla.
    -   **Valor recomendado:** SÍ, para la mayoría de las ubicaciones (página de inicio, página de producto), ya que es eficiente en el espacio y atractivo.
    -   **Escenario / ejemplo de comerciante:** Tiene 9 fotos para un producto, pero solo espacio para 3 a la vez. Habilitar el carrusel permite a los clientes deslizar las 9.
-   **Función Fancybox:**

    -   **Qué hace esta configuración:** Habilita o deshabilita el efecto "Fancybox", que es una popular biblioteca de JavaScript que muestra imágenes en una ventana emergente superpuesta y elegante al hacer clic.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Al hacer clic en una foto de Instagram en el feed, se abrirá en una ventana emergente grande y elegante, lo que permitirá a los clientes ver los detalles sin salir de la página.
        -   *Cuando está deshabilitado:* Al hacer clic en una imagen, esta podría abrirse directamente en una nueva pestaña del navegador o simplemente no hacer nada, dependiendo del tema.
    -   **Valor recomendado:** SÍ, ya que proporciona una experiencia de usuario mucho mejor para ver imágenes.
    -   **Escenario / ejemplo de comerciante:** Un cliente ve un gran atuendo en Instagram en su feed. Al hacer clic, se abre una vista grande y clara de la foto, lo que facilita la apreciación de los detalles.

#### Configuración específica de la página de producto (Pestaña del Back Office del producto)

Después de instalar el módulo, encontrará un nuevo campo o pestaña al editar un producto en su Back Office de PrestaShop:

-   **Hashtag de Instagram (por producto):**
    -   **Qué hace esta configuración:** Este campo le permite especificar un hashtag de Instagram único para cada producto individual. El módulo utilizará este hashtag para obtener fotos relevantes de su cuenta de Instagram.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando se ingresa un hashtag (por ejemplo, #nombredemiproducto):* El feed de Instagram en esa página de producto específica mostrará fotos de su cuenta de Instagram que estén etiquetadas con `#nombredemiproducto`.
        -   *Cuando se deja vacío:* No se mostrará ningún feed de Instagram específico del producto para ese producto, incluso si "Mostrar en la página de producto" está habilitado.
    -   **Valor recomendado:** Un hashtag único y descriptivo para cada producto. Asegúrese de usar este hashtag de forma consistente en sus publicaciones de Instagram.
    -   **Escenario / ejemplo de comerciante:** Para un producto llamado "Vestido Brisa de Verano", podría ingresar `#VestidoBrisaDeVerano` o `#MiMarcaVestidoVerano`. Luego, cuando publique fotos de este vestido en Instagram, incluya ese hashtag. El módulo luego extraerá esas fotos a la página de producto del vestido.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Token de acceso de Instagram | Su token válido | Se conecta a la API de Instagram para obtener fotos. **CRÍTICO.** |
| Configuración del módulo | ID de usuario de Instagram | Su ID de usuario válido | Identifica su cuenta de Instagram para la obtención de datos. |
| Configuración del módulo | Número de fotos a mostrar | 6-9 | Controla cuántas fotos se muestran en una instancia de feed. |
| Configuración del módulo | Mostrar en la página de inicio | SÍ | Muestra un feed general en la página de inicio de su tienda. |
| Configuración del módulo | Mostrar en la página de producto | SÍ | Muestra un feed específico del producto en las páginas de productos. |
| Configuración del módulo | Mostrar en la columna izquierda | NO | Muestra un feed en la barra lateral izquierda. Puede saturar el diseño. |
| Configuración del módulo | Mostrar en la columna derecha | NO | Muestra un feed en la barra lateral derecha. Puede saturar el diseño. |
| Configuración del módulo | Mostrar en el pie de página | SÍ | Muestra un feed en el pie de página de la tienda. Bueno para una promoción sutil. |
| Configuración del módulo | Mostrar en el encabezado (izquierda) | NO | Muestra un feed en el encabezado izquierdo. Generalmente no recomendado. |
| Configuración del módulo | Mostrar en el encabezado (derecha) | NO | Muestra un feed en el encabezado derecho. Generalmente no recomendado. |
| Configuración del módulo | Función de carrusel | SÍ | Muestra fotos en una galería deslizante, ahorrando espacio. |
| Configuración del módulo | Función Fancybox | SÍ | Abre fotos en una ventana emergente elegante para una mejor visualización. |
| Página de edición de producto | Hashtag de Instagram | Único por producto | Define el hashtag para extraer fotos para *este producto específico*. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Mi feed de Instagram no muestra ninguna foto. ¿Qué debo hacer?**
R:

1.  **Verifique su token de acceso de Instagram y su ID de usuario:** Estos son los culpables más comunes. Asegúrese de que estén ingresados correctamente en la configuración del módulo y que sigan siendo válidos. Los tokens de Instagram pueden caducar, por lo que es posible que deba regenerarlos.
2.  **Verifique los hashtags:** Para las páginas de productos, asegúrese de que el campo "Hashtag de Instagram" esté lleno para el producto específico y de que realmente tenga publicaciones en Instagram que utilicen ese hashtag exacto.
3.  **Cuenta pública:** Asegúrese de que su cuenta de Instagram sea pública. El módulo no puede obtener fotos de cuentas privadas.
4.  **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** en su Back Office de PrestaShop y borre la caché de Smarty (y opcionalmente, todas las cachés). A veces, los datos antiguos en caché impiden que aparezca contenido nuevo.
5.  **Verifique los límites de la API:** Instagram tiene límites de tasa de API. Si está obteniendo datos con demasiada frecuencia o tiene un número muy grande de productos, podría alcanzar estos límites temporalmente.

**P: Las imágenes se muestran, pero se ven extrañas o rompen el diseño de mi tema.**
R:

1.  **Conflictos de tema:** Su tema personalizado de PrestaShop podría tener estilos CSS en conflicto. Este es un problema común con los módulos de terceros.
2.  **CSS del módulo:** El módulo incluye su propio CSS (`instagramfeed/css/css.css`, `instagramfeed/lib/src/css/lightslider.css`). Su webmaster o desarrollador puede inspeccionar la página para identificar estilos en conflicto y escribir anulaciones de CSS personalizadas en la hoja de estilos de su tema.
3.  **Dimensiones de la imagen:** Asegúrese de que las imágenes que publica en Instagram sean de calidad y relación de aspecto razonables. Si bien el módulo intenta adaptarse, las imágenes extremadamente anchas o altas pueden causar problemas de visualización.

**P: ¿Cómo obtengo un token de acceso y un ID de usuario de Instagram?**
R: El acceso a la API de Instagram ha cambiado con el tiempo. Normalmente, necesita una cuenta de Instagram Business y una cuenta de desarrollador de Facebook. El proceso implica crear una aplicación de Facebook, conectarla a su cuenta de Instagram Business y luego generar un token. También hay herramientas de terceros (busque "Generador de tokens de acceso de Instagram") que pueden simplificar este proceso, pero siempre use las de buena reputación.

**P: ¿Puedo mostrar diferentes feeds en diferentes páginas (por ejemplo, un feed general en la página de inicio y feeds específicos de productos)?**
R: ¡Sí, absolutamente! Esa es la funcionalidad principal. Use la configuración "Mostrar en la página de inicio" para un feed general (que normalmente extraerá de un hashtag predeterminado o de su feed de usuario principal), y luego use el campo "Hashtag de Instagram" en las páginas de productos individuales para feeds específicos de productos.

**P: El carrusel o Fancybox no funciona.**
R:

1.  **Habilite las funciones:** Verifique que las funciones "Función de carrusel" y "Función Fancybox" estén habilitadas en la configuración del módulo.
2.  **Conflictos de JavaScript:** Otro módulo o su tema podría estar cargando bibliotecas de JavaScript en conflicto (por ejemplo, otro script de carrusel o lightbox). Su webmaster necesitaría depurar esto usando la consola de desarrollador del navegador (busque errores de JavaScript).
3.  **jQuery:** Asegúrese de que jQuery esté cargado correctamente en su tienda, ya que muchas funciones de JavaScript dependen de él.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Descripción general de la arquitectura

El módulo `Feed de etiquetas de productos de Instagram` sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente la clase `Module` para la configuración y el sistema `Hook` para la visualización en el front-office. Integra una clase personalizada para la interacción con la API de Instagram y utiliza bibliotecas JavaScript externas (lightslider, fancybox) para mejorar la UI/UX. La lógica central del módulo reside en su archivo principal `index.php`, que maneja la configuración, la instalación y el registro de hooks. La renderización del front-office se logra pasando datos a las plantillas Smarty registradas en varios hooks de visualización.

### 4.2 Controladores (`controllers/`)

Este módulo **no** contiene ningún controlador dedicado de front-office o back-office. Toda la configuración se maneja a través del método `getContent()` en el archivo principal del módulo, y la visualización del front-office se gestiona directamente a través de los hooks registrados.

### 4.3 Clases y modelos principales (`classes/`)

-   `instagramfeed/classes/index.php`:

    -   Este suele ser un archivo vacío o un archivo que contiene `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../"); exit;` para evitar la lista directa de directorios. No contiene ninguna lógica de clase funcional.
-   `instagramfeed/classes/instagram_class.php`:

    -   **Nombre de la clase**: `Instagram`
    -   **Clase padre**: Ninguna (clase de utilidad independiente)
    -   **Responsabilidad**: Esta clase encapsula la lógica para interactuar con la API de Instagram. Es responsable de realizar solicitudes HTTP para obtener medios basados en el ID de usuario y los hashtags, manejar los tokens de acceso y analizar las respuestas JSON de Instagram.
    -   **Métodos públicos clave**:
        -   `__construct($access_token, $user_id)`: Constructor, inicializa con el token de acceso de Instagram y el ID de usuario.
        -   `getMediaByHashtag($hashtag, $count)`: Obtiene un número especificado de elementos multimedia de la API de Instagram que están etiquetados con el hashtag dado y asociados con el ID de usuario configurado. Devuelve una matriz de objetos multimedia.
        -   `getMediaByUser($count)`: Obtiene un número especificado de elementos multimedia directamente del feed del usuario (si es compatible con la versión de la API y el alcance del token).
        -   (Potencialmente otros métodos de ayuda para llamadas a la API, manejo de errores, etc.)

### 4.4 Activos de JavaScript (`views/js/`)

-   `instagramfeed/js/if_carousell.js`:
    -   **Alcance**: Front-office.
    -   **Descripción**: Este script probablemente inicializa y configura la funcionalidad del carrusel `lightslider` para los feeds de Instagram. Se vincula a elementos DOM específicos (por ejemplo, `ul` con una determinada clase) y aplica el comportamiento del carrusel, incluida la configuración de la capacidad de respuesta, la reproducción automática, la navegación, etc.
    -   **Dependencias**: Depende de `lightslider.js` y jQuery.
-   `instagramfeed/js/if_fancybox.js`:
    -   **Alcance**: Front-office.
    -   **Descripción**: Este script inicializa y configura la funcionalidad de lightbox Fancybox. Se dirige a los enlaces de imagen dentro del feed de Instagram (por ejemplo, etiquetas `a` que envuelven etiquetas `img`) y les permite abrirse en una ventana emergente de Fancybox al hacer clic, proporcionando una vista más grande e inmersiva de la imagen.
    -   **Dependencias**: Depende de la biblioteca Fancybox (no incluida en este módulo, pero se espera que sea cargada por el tema u otro módulo) y jQuery.
-   `instagramfeed/js/if_sliding.js`:
    -   **Alcance**: Front-office.
    -   **Descripción**: Este archivo podría ser un script alternativo o complementario para la funcionalidad de deslizamiento, posiblemente para versiones anteriores de PrestaShop o diseños específicos. Dados `if_carousell.js` y `lightslider.js`, podría ser un script heredado o un envoltorio para comportamientos de deslizamiento específicos no cubiertos por el carrusel principal.
    -   **Dependencias**: Probablemente jQuery.
-   `instagramfeed/js/ps14.js`:
    -   **Alcance**: Front-office (específicamente para compatibilidad con PrestaShop 1.4).
    -   **Descripción**: Este script probablemente contiene correcciones de compatibilidad o polyfills para entornos antiguos de PrestaShop 1.4, abordando posibles diferencias de JavaScript o versiones/características de jQuery faltantes en comparación con las versiones más nuevas de PrestaShop.
    -   **Dependencias**: jQuery.
-   `instagramfeed/lib/src/js/lightslider.js`:
    -   **Alcance**: Front-office.
    -   **Descripción**: Esta es la biblioteca principal del plugin jQuery `lightslider`. Proporciona la funcionalidad para crear carruseles y deslizadores de contenido responsivos y táctiles. `if_carousell.js` normalmente llamaría a métodos de esta biblioteca.
    -   **Dependencias**: jQuery.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `instagramfeed/css/css.css`:
    -   **Alcance**: Estilo del cliente del Front-office.
    -   **Descripción**: Contiene reglas CSS personalizadas específicas para el diseño del feed de Instagram, el tamaño de las imágenes, el espaciado y la apariencia general dentro de los diversos hooks. Define clases para el contenedor del feed, los elementos de imagen individuales y, potencialmente, los subtítulos o enlaces.
    -   **Selectores de clase CSS clave**: Los desarrolladores pueden inspeccionar el HTML generado para encontrar clases como `.instagram-feed-container`, `.instagram-item`, `.instagram-image`, etc., que se pueden anular en el `custom.css` o `theme.css` del tema.
-   `instagramfeed/lib/src/css/lightslider.css`:
    -   **Alcance**: Estilo del cliente del Front-office.
    -   **Descripción**: Esta es la hoja de estilos predeterminada para el plugin jQuery `lightslider`. Proporciona el estilo esencial para las flechas de navegación del carrusel, los puntos de paginación, las transiciones de diapositivas y el comportamiento responsivo.
    -   **Selectores de clase CSS clave**: Clases como `.lightSlider`, `.lSAction`, `.lSPager`, etc., que se pueden personalizar para que coincidan con la marca de la tienda.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **Plantillas de administración (`views/templates/admin/`)**:

    -   `instagramfeed/views/templates/admin/instagram_feed.tpl`: Esta plantilla es renderizada por el método `getContent()` en el archivo principal del módulo. Muestra el formulario de configuración del back-office del módulo, incluidos los campos de entrada para el token de acceso de Instagram, el ID de usuario, el número de fotos y varios interruptores de visualización (página de inicio, página de producto, columnas, pie de página, encabezado, carrusel, fancybox). Normalmente utiliza los componentes de formulario de ayuda de PrestaShop.
-   **Plantillas de hook (`views/templates/hook/`)**:

    -   `instagramfeed/views/templates/hook/column-feed.tpl`: Renderiza el feed de Instagram cuando se engancha en `displayLeftColumn` o `displayRightColumn`. Normalmente muestra una versión más compacta del feed.
    -   `instagramfeed/views/templates/hook/feed.tpl`: Una plantilla de feed de propósito general, probablemente utilizada para la visualización principal de la página de inicio o el pie de página. Contiene la estructura central para mostrar imágenes de Instagram, potencialmente envueltas en un contenedor de carrusel.
    -   `instagramfeed/views/templates/hook/header-left.tpl`: Renderiza el feed cuando se engancha en `displayHeaderLeft`.
    -   `instagramfeed/views/templates/hook/header-right.tpl`: Renderiza el feed cuando se engancha en `displayHeaderRight`.
    -   `instagramfeed/views/templates/hook/homepage-feed.tpl`: Diseñado específicamente para el hook `displayHome`, a menudo presenta un diseño más prominente o más ancho para la página de inicio.
    -   `instagramfeed/views/templates/hook/tab.tpl`: Renderiza el título de la pestaña para el feed de Instagram en la página del producto (por ejemplo, "Fotos de Instagram"). Esto se engancha típicamente en `displayProductTab` (PrestaShop 1.6) o `displayProductExtraContent` (PrestaShop 1.7+).
    -   `instagramfeed/views/templates/hook/tabcontents.tpl`: Renderiza el contenido real del feed de Instagram dentro de la pestaña de la página del producto. Esta plantilla contendrá la lógica para mostrar las imágenes obtenidas utilizando el hashtag específico del producto, a menudo utilizando las funciones de carrusel y fancybox.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:

    -   El módulo no crea tablas SQL personalizadas.
    -   La configuración (token de acceso, ID de usuario, opciones de visualización, etc.) se almacena en la tabla `ps_configuration` utilizando claves como `INSTAGRAMFEED_ACCESS_TOKEN`, `INSTAGRAMFEED_USER_ID`, `INSTAGRAMFEED_NUM_PHOTOS`, etc.
    -   El hashtag de Instagram específico del producto se almacena en la tabla `ps_product_lang` (o una tabla similar relacionada con el producto) como un nuevo campo agregado por el módulo durante la instalación. Este campo normalmente se llamaría `instagram_hashtag` o similar.
-   **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Se utiliza para cargar los activos CSS y JavaScript (lightslider, fancybox, scripts personalizados) necesarios para los feeds de Instagram. |
| `displayHome` | En la página de inicio de la tienda. | Renderiza el feed general de Instagram en la página de inicio. |
| `displayLeftColumn` | En la barra lateral izquierda de las páginas donde está habilitado. | Renderiza un feed compacto de Instagram en la columna izquierda. |
| `displayRightColumn` | En la barra lateral derecha de las páginas donde está habilitado. | Renderiza un feed compacto de Instagram en la columna derecha. |
| `displayFooter` | En la sección del pie de página de la tienda. | Renderiza un feed general de Instagram en el pie de página. |
| `displayHeaderLeft` | En la parte izquierda del encabezado de la tienda. | Renderiza un pequeño feed de Instagram en el encabezado. |
| `displayHeaderRight` | En la parte derecha del encabezado de la tienda. | Renderiza un pequeño feed de Instagram en el encabezado. |
| `displayProductTab` (PS 1.6) | En la página del producto, para agregar nuevas pestañas. | Renderiza el título de la pestaña del feed de Instagram en la página del producto. |
| `displayProductTabContent` (PS 1.6) | En la página del producto, para agregar contenido a las pestañas. | Renderiza el contenido (el feed real de Instagram) dentro de la pestaña de la página del producto. |
| `displayProductExtraContent` (PS 1.7+) | En la página del producto, para agregar bloques de contenido extra. | Hook alternativo para PrestaShop 1.7+ para mostrar el feed de Instagram en las páginas de productos, a menudo como un nuevo bloque debajo de la información principal del producto. |
| `actionProductUpdate` | Después de que un producto se actualiza en el Back Office. | Se utiliza para guardar el valor del campo `instagram_hashtag` para el producto. |
| `actionProductAdd` | Después de que se agrega un nuevo producto en el Back Office. | Se utiliza para guardar el valor del campo `instagram_hashtag` para el nuevo producto. |
| `displayAdminProductsExtra` | En la página de edición de productos en el Back Office. | Renderiza el campo de entrada para el "Hashtag de Instagram" en la página de configuración del producto. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a brindar asistencia y garantizar que su módulo funcione de manera óptima.
