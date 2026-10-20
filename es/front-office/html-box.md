---
title: "Caja HTML - Manual para el Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Caja HTML de PrestaShop por MyPresta.eu."
sidebar:
  label: "Caja HTML - Manual para el Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Html box en MyPresta.eu](https://mypresta.eu/modules/front-office-features/html-box.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/html-box/)
>
> ---


# Caja HTML

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para una instalación de PrestaShop y son suficientes para este módulo.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > Caja HTML)

Esta es la pantalla de configuración principal donde define el contenido de sus cajas HTML y dónde aparecen.

#### Ajustes Generales

- **¿Habilitar SSL (https) para este módulo?** (`htmlbox_ssl`)

  - **Qué hace este ajuste:** Determina si el contenido del módulo debe cargarse de forma segura a través de HTTPS.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* Asegura que cualquier contenido generado por este módulo se sirva a través de HTTPS, evitando advertencias de "contenido mixto" en los navegadores si su tienda utiliza SSL.
    - *Cuando está deshabilitado (NO):* El contenido podría servirse a través de HTTP, lo que puede causar advertencias de seguridad en tiendas habilitadas para HTTPS.
  - **Valor recomendado:** **SÍ**
  - **Escenario / ejemplo de comerciante:** Si su tienda utiliza HTTPS (¡lo cual debería!), habilitar esto asegura que su contenido personalizado no active alertas de seguridad para sus clientes.
- **¿Deshabilitar el editor TinyMCE?** (`htmlbox_disabletiny`)

  - **Qué hace este ajuste:** Controla si se utiliza el editor de texto enriquecido (TinyMCE) para introducir su contenido HTML.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* Verá un área de texto plano para introducir su HTML, JavaScript o CSS. Esto es útil si está pegando código complejo que TinyMCE podría intentar "limpiar" o si prefiere escribir HTML sin formato.
    - *Cuando está deshabilitado (NO):* Tendrá un editor de texto enriquecido fácil de usar, similar a un procesador de textos, que le permitirá formatear texto, añadir imágenes y crear enlaces sin escribir HTML directamente.
  - **Valor recomendado:** **NO** (a menos que sea un desarrollador o esté pegando código complejo).
  - **Escenario / ejemplo de comerciante:** Si desea añadir rápidamente un anuncio de texto en negrita, manténgalo deshabilitado. Si está pegando un código de widget de Facebook, habilítelo para evitar que el editor altere su código.
- **¿Mostrar solo para clientes registrados?** (`htmlbox_logged`)

  - **Qué hace este ajuste:** Restringe la visibilidad del contenido de la caja HTML solo a los clientes que han iniciado sesión en sus cuentas.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* Solo los clientes registrados y con sesión iniciada verán el contenido de la caja HTML.
    - *Cuando está deshabilitado (NO):* Todos los visitantes, estén o no registrados, verán el contenido.
  - **Valor recomendado:** **NO** (a menos que tenga contenido específico para usuarios registrados).
  - **Escenario / ejemplo de comerciante:** Podría habilitar esto si desea mostrar un mensaje especial del programa de fidelización u ofertas exclusivas solo visibles para su base de clientes existente.
- **¿Mostrar solo para clientes NO registrados?** (`htmlbox_unlogged`)

  - **Qué hace este ajuste:** Restringe la visibilidad del contenido de la caja HTML solo a los clientes que *no* han iniciado sesión en sus cuentas.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* Solo los visitantes que no han iniciado sesión verán el contenido de la caja HTML.
    - *Cuando está deshabilitado (NO):* Todos los visitantes, estén o no registrados, verán el contenido.
  - **Valor recomendado:** **NO** (a menos que tenga contenido específico para invitados).
  - **Escenario / ejemplo de comerciante:** Podría habilitar esto para mostrar un mensaje de "Iniciar sesión o registrarse para ofertas exclusivas" para fomentar nuevas inscripciones o que los clientes recurrentes inicien sesión.

#### Campos de contenido de la caja HTML

Estos campos son donde introduce el contenido HTML, JavaScript o CSS real para cada hook específico. Cada campo corresponde a una ubicación diferente en su tienda.

- **HTML para la cabecera (displayTop, displayNav1, displayNav2)** (`htmlbox_header`)

  - **Qué hace este ajuste:** Este es el contenido que aparecerá en la sección de la cabecera de su tienda. Dependiendo de su tema, esto podría ser `displayTop`, `displayNav1` o `displayNav2`.
  - **Efecto de cambiar este ajuste:** El contenido que introduzca aquí será visible en la parte superior de su sitio web.
  - **Valor recomendado:** Dejar vacío si no es necesario.
  - **Escenario / ejemplo de comerciante:** Un banner de anuncio para todo el sitio ("¡Envío gratuito en todos los pedidos superiores a 50 $!"), una pequeña barra de iconos de redes sociales o una barra de búsqueda personalizada.
- **HTML para la columna superior (displayTopColumn)** (`htmlbox_top`)

  - **Qué hace este ajuste:** Este contenido aparece justo debajo de la cabecera, a menudo abarcando todo el ancho del área de contenido principal.
  - **Efecto de cambiar este ajuste:** El contenido que introduzca aquí se mostrará de forma destacada en la parte superior de su área de contenido principal, normalmente por encima de los listados de productos principales o del contenido de la página de inicio.
  - **Valor recomendado:** Dejar vacío si no es necesario.
  - **Escenario / ejemplo de comerciante:** Un gran banner promocional para una venta estacional, un carrusel de productos destacados o una introducción en vídeo a su marca.
- **HTML para la columna izquierda (displayLeftColumn)** (`htmlbox_leftcol`)

  - **Qué hace este ajuste:** Este contenido aparece en la barra lateral izquierda de su tienda (si su tema tiene una y está habilitada).
  - **Efecto de cambiar este ajuste:** El contenido que introduzca aquí se mostrará en la columna izquierda, junto con otros módulos como filtros de categoría o navegación.
  - **Valor recomendado:** Dejar vacío si no es necesario.
  - **Escenario / ejemplo de comerciante:** Una lista de "Comprar por marca", un formulario de suscripción a un boletín, un pequeño anuncio para una categoría de producto específica o un cuadro de "Me gusta" de Facebook.
- **HTML para la columna derecha (displayRightColumn)** (`htmlbox_rightcol`)

  - **Qué hace este ajuste:** Este contenido aparece en la barra lateral derecha de su tienda (si su tema tiene una y está habilitada).
  - **Efecto de cambiar este ajuste:** El contenido que introduzca aquí se mostrará en la columna derecha, de forma similar a la columna izquierda.
  - **Valor recomendado:** Dejar vacío si no es necesario.
  - **Escenario / ejemplo de comerciante:** Una lista de "Más vendidos", un bloque de contacto de atención al cliente, un feed de Pinterest o una sección de "Productos vistos recientemente".
- **HTML para el pie de página (displayFooter)** (`htmlbox_footercol`)

  - **Qué hace este ajuste:** Este contenido aparece en la sección del pie de página en la parte inferior de cada página.
  - **Efecto de cambiar este ajuste:** El contenido que introduzca aquí será visible en la parte inferior de su sitio web.
  - **Valor recomendado:** Dejar vacío si no es necesario.
  - **Escenario / ejemplo de comerciante:** Logotipos de métodos de pago, sellos de confianza, una breve descripción de "Sobre nosotros", enlaces a redes sociales o un aviso de derechos de autor personalizado.
- **HTML para la página de inicio (displayHome)** (`htmlbox_homecol`)

  - **Qué hace este ajuste:** Este contenido se muestra específicamente en la página de inicio de su tienda.
  - **Efecto de cambiar este ajuste:** El contenido que introduzca aquí será una parte central del diseño de su página de inicio.
  - **Valor recomendado:** Dejar vacío si no es necesario.
  - **Escenario / ejemplo de comerciante:** Una cuadrícula de categorías destacadas, una sección de "Por qué comprar con nosotros", testimonios de clientes o un gran botón de llamada a la acción.
- **HTML para el cuerpo (displayBody)** (`htmlbox_body`)

  - **Qué hace este ajuste:** Este contenido se inyecta en la etiqueta `<body>` de su HTML, normalmente al final, antes de la etiqueta de cierre `</body>`. A menudo se utiliza para scripts globales o elementos que deben estar disponibles en todo el sitio pero que no están visualmente vinculados a una sección específica.
  - **Efecto de cambiar este ajuste:** El contenido estará presente en cada página de su tienda, pero su ubicación visual podría depender del CSS de su tema. Es excelente para códigos de seguimiento o pop-ups.
  - **Valor recomendado:** Dejar vacío si no es necesario.
  - **Escenario / ejemplo de comerciante:** Código de seguimiento de Google Analytics, Píxel de Facebook, un banner global de consentimiento de cookies (si no lo gestiona otro módulo) o un script de widget de chat.

#### Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | ¿Habilitar SSL (https) para este módulo? | SÍ | Asegura que el contenido se cargue de forma segura, evitando advertencias de contenido mixto. |
| Configuración del módulo | ¿Deshabilitar el editor TinyMCE? | NO | Controla el editor de texto enriquecido para la entrada de contenido. Habilitar para código sin formato. |
| Configuración del módulo | ¿Mostrar solo para clientes registrados? | NO | Restringe la visibilidad del contenido a los usuarios registrados. |
| Configuración del módulo | ¿Mostrar solo para clientes NO registrados? | NO | Restringe la visibilidad del contenido a los usuarios invitados. |
| Configuración del módulo | HTML para la cabecera | Vacío | Contenido personalizado en el área de la cabecera (por ejemplo, anuncios, banners superiores). |
| Configuración del módulo | HTML para la columna superior | Vacío | Contenido personalizado debajo de la cabecera, a menudo de ancho completo (por ejemplo, promociones principales). |
| Configuración del módulo | HTML para la columna izquierda | Vacío | Contenido personalizado en la barra lateral izquierda (por ejemplo, feeds sociales, boletín). |
| Configuración del módulo | HTML para la columna derecha | Vacío | Contenido personalizado en la barra lateral derecha (por ejemplo, más vendidos, atención al cliente). |
| Configuración del módulo | HTML para el pie de página | Vacío | Contenido personalizado en el pie de página (por ejemplo, logotipos de pago, sellos de confianza). |
| Configuración del módulo | HTML para la página de inicio | Vacío | Contenido específicamente en la página de inicio (por ejemplo, productos destacados). |
| Configuración del módulo | HTML para el cuerpo | Vacío | Contenido/scripts globales inyectados en el `<body>` (por ejemplo, análisis, widgets de chat). |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P: Mi HTML personalizado no aparece o se ve roto.**
R:

1. **Verifique el Hook:** Asegúrese de haber introducido el contenido en el campo de la caja HTML correcto para la ubicación deseada (por ejemplo, `HTML para la página de inicio` para la página de inicio).
2. **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** en su Back Office de PrestaShop y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). PrestaShop a menudo almacena contenido en caché, y es posible que la nueva configuración del módulo no aparezca inmediatamente.
3. **Inspeccionar HTML:** Si se siente cómodo, utilice las herramientas de desarrollo de su navegador (F12) para inspeccionar el área donde debería estar el contenido. Busque errores en la consola o vea si su HTML está presente pero con un estilo incorrecto.
4. **Interferencia de TinyMCE:** Si está pegando código complejo (especialmente JavaScript o iframes), intente habilitar "¿Deshabilitar el editor TinyMCE?" para asegurarse de que el editor no esté eliminando o alterando su código.

**P: El contenido aparece, pero no se ve bien en el móvil.**
R: El módulo en sí es responsivo, pero el *contenido que añade* también debe ser responsivo.

1. **Utilice HTML/CSS responsivo:** Si está escribiendo HTML personalizado, asegúrese de utilizar principios de diseño responsivo (por ejemplo, `max-width: 100%` para imágenes, media queries CSS).
2. **Widgets de terceros:** Si está incrustando un widget (como Facebook o Twitter), verifique si el proveedor del widget ofrece códigos de incrustación o configuraciones responsivas.
3. **Contenido simple:** Para contenido móvil crítico, manténgalo simple: texto plano, imágenes pequeñas y llamadas a la acción claras.

**P: He añadido JavaScript, pero no se está ejecutando.**
R:

1. **Ubicación:** El JavaScript añadido al campo `HTML para el cuerpo` es generalmente el lugar más seguro para los scripts globales, ya que se carga al final de la página.
2. **Errores de sintaxis:** Verifique su código JavaScript en busca de errores de sintaxis. Un solo error puede impedir que se ejecute todo el script.
3. **Conflictos de jQuery:** Si su script depende de jQuery, asegúrese de que se carga correctamente y de que no hay conflictos con la versión de jQuery de PrestaShop. Es posible que deba envolver su código en `(function($){ /* su código */ })(jQuery);` o usar `jQuery.noConflict();`.
4. **Scripts externos:** Si está enlazando a un archivo `.js` externo, asegúrese de que la URL sea correcta y accesible.

**P: ¿Cómo traduzco el contenido de mis cajas HTML a diferentes idiomas?**
R: La versión actual del módulo no ofrece campos multilingües incorporados para cada caja HTML. Para lograr contenido multilingüe, tiene dos opciones principales:

1. **Detección manual de idioma (Avanzado):** Puede incrustar lógica condicional dentro del contenido de su caja HTML utilizando variables Smarty (si su tema permite el procesamiento de Smarty en hooks) o JavaScript para detectar el idioma actual y mostrar contenido diferente. Esta es una solución más avanzada.
   *Ejemplo (Smarty):*

   ```
   {if $language.iso\_code == 'en'} <p>Welcome to our English store!</p>{elseif $language.iso\_code == 'fr'} <p>Bienvenue dans notre boutique française !</p>{/if}
   ```
2. **Módulos separados (Solución alternativa):** Para contenido crítico, podría considerar instalar instancias separadas del módulo "Caja HTML" (si lo permite el desarrollador del módulo o duplicando el módulo) y asignar cada una a un idioma específico, luego gestionar su visualización a través de las posiciones de los módulos de PrestaShop. Esta es una solución alternativa más compleja.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters que trabajan con el módulo Caja HTML.

### 4.1 Descripción general de la arquitectura

El módulo `Caja HTML` es un módulo PrestaShop sencillo diseñado principalmente para inyectar contenido HTML/JS/CSS personalizado en varios hooks del front-office. Sigue una estructura de módulo PrestaShop clásica, aprovechando la clase `Module` para la instalación, desinstalación y configuración, y utilizando los métodos `hook` para renderizar contenido en el front office. La configuración se gestiona a través del método `getContent()`, que renderiza un formulario de configuración estándar de PrestaShop. El módulo almacena su contenido directamente en la tabla `ps_configuration`.

### 4.2 Controladores (`controllers/`)

Este módulo **no** contiene ningún controlador de administración de Front-Office o Back-Office personalizado. Toda la funcionalidad, incluida la configuración y la renderización del front-office, se maneja directamente dentro del archivo principal del módulo `htmlbox.php`.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo **no** define ninguna clase personalizada o instancias de `ObjectModel`. Todos los datos se almacenan como valores de configuración.

### 4.4 Activos de JavaScript (`views/js/`)

- **`htmlbox/tinymce16.inc.js`**
  - **Alcance:** Back-office (específicamente la página de configuración del módulo).
  - **Propósito:** Este archivo es responsable de inicializar y configurar el editor de texto enriquecido TinyMCE dentro del formulario de configuración del módulo. Transforma los elementos `<textarea>` estándar en un editor WYSIWYG fácil de usar, permitiendo a los comerciantes formatear texto, insertar imágenes y gestionar contenido HTML sin codificación directa. Probablemente incluye configuraciones personalizadas para integrar TinyMCE con el gestor de archivos de PrestaShop para la carga de imágenes.
  - **Notas para desarrolladores:** Si `htmlbox_disabletiny` está habilitado, este script no se cargará o su funcionalidad será omitida. Los desarrolladores que deseen personalizar la experiencia de TinyMCE (por ejemplo, añadir botones personalizados, cambiar el diseño de la barra de herramientas) tendrían que modificar este archivo o anular su carga/configuración.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo **no** incluye ningún archivo CSS personalizado. Cualquier estilo para el contenido HTML inyectado debe proporcionarse dentro del propio contenido HTML (estilos en línea o etiquetas `<style>`) o por el tema activo de PrestaShop.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **`views/templates/hook/html.tpl`**
  - **Alcance:** Front-office.
  - **Renderizado de Hooks:** Este es el archivo de plantilla principal utilizado por el módulo para renderizar el contenido HTML personalizado en todos los hooks registrados del front-office.
  - **Contenido:** Probablemente contiene una estructura simple para generar la variable `$html_content`, que se pasa desde los métodos hook del módulo.
  - **Notas para desarrolladores:** Esta plantilla es mínima. El contenido real se carga dinámicamente de la tabla `ps_configuration` en función del hook. Los desarrolladores pueden anular esta plantilla en su tema (por ejemplo, `themes/yourtheme/modules/htmlbox/html.tpl`) para envolver el contenido en `div`s personalizados, añadir clases específicas o aplicar lógica condicional, aunque la mayoría de las personalizaciones se realizarán directamente en el propio contenido de la caja HTML.

### 4.7 Esquema de la base de datos y mapa de Hooks

- **Tablas de la base de datos**:
  El módulo no crea ninguna tabla de base de datos personalizada. Toda la configuración y el contenido se almacenan en la tabla estándar `ps_configuration` de PrestaShop utilizando las siguientes claves:

  - `mypresta_updates`
  - `update_`
  - `updatev_`
  - `htmlbox_header`
  - `htmlbox_top`
  - `htmlbox_leftcol`
  - `htmlbox_rightcol`
  - `htmlbox_footercol`
  - `htmlbox_homecol`
  - `htmlbox_body`
  - `htmlbox_ssl`
  - `htmlbox_origtiny`
  - `htmlbox_disabletiny`
  - `htmlbox_home`
  - `htmlbox_hook`
  - `htmlbox_logged`
  - `htmlbox_unlogged`
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Principalmente para añadir metaetiquetas, enlaces CSS o JavaScript que necesitan cargarse temprano. |
| `displayTop` | Sección superior de la página, normalmente encima del contenido principal. | Contenido general para la parte superior de la página, a menudo dependiente del tema. |
| `displayNav1` | Barra de navegación, a menudo la barra superior con enlaces rápidos. | Contenido para la primera barra de navegación. |
| `displayNav2` | Barra de navegación secundaria, a menudo debajo de `displayNav1`. | Contenido para la segunda barra de navegación. |
| `displayTopColumn` | Área de ancho completo debajo de la cabecera, encima del contenido principal. | Área de contenido prominente, a menudo utilizada para banners o deslizadores. |
| `displayLeftColumn` | Barra lateral izquierda en las páginas donde está habilitada. | Contenido para la barra lateral izquierda (por ejemplo, filtros, categorías, bloques personalizados). |
| `displayRightColumn` | Barra lateral derecha en las páginas donde está habilitada. | Contenido para la barra lateral derecha (por ejemplo, anuncios, widgets sociales). |
| `displayHome` | Área de contenido principal de la página de inicio. | Contenido específicamente para la página de inicio. |
| `displayFooter` | Sección inferior de cada página. | Contenido para el pie de página (por ejemplo, derechos de autor, logotipos de pago, enlaces). |
| `displayBody` | Al final de la etiqueta `<body>`. | Ideal para JavaScript global (por ejemplo, análisis, widgets de chat) o elementos que deben cargarse al final. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). MyPresta.eu proporciona soporte dedicado para todos sus módulos.
