---
title: "HTML Box Pro - Manual para el Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo HTML Box Pro para PrestaShop de MyPresta.eu."
sidebar:
  label: "HTML Box Pro - Manual para el Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo HTML Box Pro en MyPresta.eu](https://mypresta.eu/modules/front-office-features/html-box-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/html-box-pro/)
>
> ---


# HTML Box Pro

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser requeridas por PrestaShop y son suficientes para este módulo.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > HTML Box Pro)

Esta es la pantalla principal donde gestiona todas sus Cajas HTML. El módulo presenta una lista de las cajas existentes y opciones para agregar nuevas o modificar la configuración global.

#### Sección de Configuración Global

En la parte superior de la página de configuración, encontrará algunas configuraciones globales que afectan el funcionamiento del módulo.

- **Usar módulo interno**

  - **Qué hace esta configuración:** Esta es una configuración heredada que generalmente se refiere al mecanismo de actualización interno del módulo.
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado ("Sí"):* El módulo podría usar sus propios métodos internos para verificar actualizaciones.
    - *Cuando está deshabilitado ("No"):* El módulo dependerá de los mecanismos de actualización estándar de PrestaShop o de las actualizaciones manuales.
  - **Valor recomendado:** "Sí" (a menos que experimente problemas, entonces intente "No").
  - **Escenario / ejemplo del comerciante:** Generalmente, déjelo activado. Si encuentra problemas con las actualizaciones o notificaciones del módulo, su webmaster podría sugerir alternar esta opción.
- **Evitar eliminar URLs de imágenes**

  - **Qué hace esta configuración:** Cuando utiliza el editor TinyMCE incorporado (el editor de texto enriquecido) para agregar imágenes, a veces puede eliminar automáticamente la ruta URL completa, especialmente si copia y pega contenido. Esta configuración evita ese comportamiento.
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado ("Sí"):* Las URLs de las imágenes que inserte en el contenido de la caja HTML se conservarán exactamente como las introdujo, evitando enlaces de imágenes rotos.
    - *Cuando está deshabilitado ("No"):* El editor podría modificar o eliminar partes de las URLs de las imágenes, lo que podría provocar que las imágenes no se muestren correctamente.
  - **Valor recomendado:** "Sí"
  - **Escenario / ejemplo del comerciante:** Si está agregando imágenes de fuentes externas (por ejemplo, un CDN u otro sitio web) o incluso imágenes internas con rutas absolutas, habilitar esto asegura que sus imágenes siempre se muestren.
- **No cargar librerías tinyMCE**

  - **Qué hace esta configuración:** TinyMCE es el editor de texto enriquecido que le permite formatear texto fácilmente, agregar imágenes y crear tablas sin escribir código HTML directamente. Esta configuración controla si el módulo carga su propia versión del editor TinyMCE.
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado ("Sí"):* El módulo NO cargará su editor TinyMCE. Esto puede ser útil si su tema u otro módulo ya carga TinyMCE, evitando conflictos o cargas duplicadas. Sin embargo, perderá el editor visual para sus cajas HTML y necesitará escribir HTML puro.
    - *Cuando está deshabilitado ("No"):* El módulo cargará su editor TinyMCE, proporcionándole una interfaz fácil de usar para crear y editar el contenido de su caja HTML.
  - **Valor recomendado:** "No" (a menos que sea un desarrollador y prefiera escribir HTML puro, o si experimenta conflictos con otras instancias de TinyMCE).
  - **Escenario / ejemplo del comerciante:** Si desea utilizar el editor visual para agregar fácilmente texto, negrita, cursiva, imágenes y enlaces sin conocer HTML, mantenga esta opción en "No". Si ve un comportamiento extraño con el editor o errores en la consola, un desarrollador podría sugerir activarla para solucionar problemas.

#### Sección de Gestión de Cajas HTML

Debajo de la configuración global, encontrará una tabla que lista todas sus cajas HTML creadas. Desde aquí, puede agregar nuevas cajas, editar las existentes o eliminarlas.

- **Agregar nueva Caja HTML** (Botón)

  - **Qué hace esto:** Al hacer clic en este botón, se le dirigirá a un nuevo formulario donde podrá definir una nueva caja HTML.
  - **Efecto:** Abre el formulario "Agregar nueva Caja HTML".
- **Editar** (Icono junto a cada caja)

  - **Qué hace esto:** Le permite modificar la configuración y el contenido de una caja HTML existente.
  - **Efecto:** Abre el formulario "Editar Caja HTML", precargado con la configuración actual de la caja.
- **Eliminar** (Icono junto a cada caja)

  - **Qué hace esto:** Elimina permanentemente una caja HTML de su tienda.
  - **Efecto:** La caja HTML ya no aparecerá en su front office. Esta acción es irreversible.
  - **Valor recomendado:** Solo elimine las cajas que ya no necesite.

#### Formulario Agregar/Editar Caja HTML

Cuando haga clic en "Agregar nueva Caja HTML" o "Editar" una existente, verá un formulario con los siguientes campos:

- **Nombre**

  - **Qué hace esta configuración:** Este es un nombre interno para su caja HTML, visible solo en el Back Office. Le ayuda a identificar diferentes cajas.
  - **Efecto de cambiar esta configuración:** Cambia la etiqueta de esta caja en su lista de configuración del módulo. No tiene efecto en el front office.
  - **Valor recomendado:** Un nombre descriptivo (por ejemplo, "Banner de página de inicio - Rebajas de verano", "Insignias de confianza de página de producto", "Información de contacto del pie de página").
  - **Escenario / ejemplo del comerciante:** Nombrar sus cajas claramente le ayuda a encontrarlas y gestionarlas rápidamente, especialmente a medida que su tienda crece y agrega más contenido personalizado.
- **Tienda** (Solo visible en entornos multi-tienda)

  - **Qué hace esta configuración:** Si administra varias tiendas desde una única instalación de PrestaShop, esto le permite especificar en qué tienda(s) debe aparecer esta caja HTML.
  - **Efecto de cambiar esta configuración:** La caja HTML solo se mostrará en las tiendas seleccionadas.
  - **Valor recomendado:** Seleccione las tiendas específicas donde el contenido sea relevante.
  - **Escenario / ejemplo del comerciante:** Podría tener un banner promocional diferente para su tienda francesa que para su tienda alemana.
- **Posición**

  - **Qué hace esta configuración:** Esta es la configuración más crucial, que determina *dónde* aparecerá la caja HTML en su tienda. Es una lista desplegable de todos los hooks disponibles de PrestaShop.
  - **Efecto de cambiar esta configuración:** El contenido de su caja HTML se renderizará en la ubicación del hook seleccionado.
  - **Valor recomendado:** Elija el hook que mejor se adapte al propósito del contenido (por ejemplo, `displayHeader` para un banner superior, `displayLeftColumn` para un bloque de barra lateral).
  - **Escenario / ejemplo del comerciante:** Si desea agregar un mensaje de "Envío gratuito" encima de las descripciones de sus productos, seleccionaría `displayProductAdditionalInfo`.
- **Activo**

  - **Qué hace esta configuración:** Controla si la caja HTML está actualmente visible en su tienda.
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado ("Sí"):* La caja HTML se mostrará en su front office.
    - *Cuando está deshabilitado ("No"):* La caja HTML se ocultará, pero su contenido y configuración se guardarán, lo que le permitirá reactivarla más tarde.
  - **Valor recomendado:** "Sí" para contenido activo, "No" para contenido que desea ocultar temporalmente o preparar para uso futuro.
  - **Escenario / ejemplo del comerciante:** Puede preparar una caja de promoción navideña con antelación, mantenerla en "No" y luego cambiarla a "Sí" cuando llegue el momento, sin tener que recrearla.
- **Solo en páginas seguras (SSL)**

  - **Qué hace esta configuración:** Restringe la visualización de la caja HTML a las páginas que se cargan a través de HTTPS (conexión segura).
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado ("Sí"):* La caja solo aparecerá en páginas con `https://` en la URL.
    - *Cuando está deshabilitado ("No"):* La caja aparecerá tanto en páginas seguras (HTTPS) como no seguras (HTTP) (si su tienda aún usa HTTP, lo cual no se recomienda).
  - **Valor recomendado:** "Sí" si el contenido contiene información sensible o si desea asegurarse de que solo se cargue en páginas seguras. Generalmente, todas las tiendas modernas deberían ser completamente HTTPS, por lo que esto podría no ser estrictamente necesario, pero agrega una capa adicional de control.
  - **Escenario / ejemplo del comerciante:** Si su caja HTML contiene una insignia de pago o un sello de seguridad, es posible que desee asegurarse de que solo aparezca en páginas seguras para reforzar la confianza.
- **Solo en la página de inicio**

  - **Qué hace esta configuración:** Restringe la visualización de la caja HTML únicamente a la página de inicio de su tienda.
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado ("Sí"):* La caja solo aparecerá cuando los clientes visiten su página de inicio principal.
    - *Cuando está deshabilitado ("No"):* La caja aparecerá en todas las páginas donde su "Posición" (hook) seleccionada esté disponible.
  - **Valor recomendado:** "No" a menos que el contenido esté diseñado específicamente para la página de inicio.
  - **Escenario / ejemplo del comerciante:** Un gran banner promocional para una venta en todo el sitio se establecería típicamente en "Sí" para esta opción si solo lo desea en la página de inicio, o en "No" si desea que aparezca en la cabecera de cada página.
- **Contenido** (Este es el editor de contenido principal)

  - **Qué hace esta configuración:** Aquí es donde introduce el código HTML, JavaScript o CSS real que se mostrará. Utiliza el editor de texto enriquecido TinyMCE (si no está deshabilitado globalmente) para facilitar la creación de contenido.
  - **Efecto de cambiar esta configuración:** El contenido que introduzca aquí se renderizará en su front office en el hook seleccionado.
  - **Valor recomendado:** Introduzca el contenido deseado. Puede usar:
    - Texto plano
    - HTML (por ejemplo, `<p>Hola Mundo!</p>`, etiquetas `<img>`, enlaces `<a>`)
    - CSS (envuelto en etiquetas `<style>`, por ejemplo, `<style>.mi-clase { color: rojo; }</style>`)
    - JavaScript (envuelto en etiquetas `<script>`, por ejemplo, `<script>alert('¡Bienvenido!');</script>`)
  - **Escenario / ejemplo del comerciante:**
    - *HTML:* Agregar una imagen de banner personalizada: `<img src="https://sutienda.com/img/cms/banner.jpg" alt="Rebajas de Verano" style="width:100%;">`
    - *JavaScript:* Incrustar un código de seguimiento de Google Analytics: `<script> (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){ (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o), m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m) })(window,document,'script','//www.google-analytics.com/analytics.js','ga'); ga('create', 'UA-XXXXX-Y', 'auto'); ga('send', 'pageview'); </script>`
    - *CSS:* Cambiar el color de un elemento específico: `<style> #header .logo { border: 2px solid blue; } </style>`

#### 2.1.1 Tabla de referencia rápida de configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de configuración principal | Usar módulo interno | Sí | Controla el mecanismo de actualización interno. |
| Página de configuración principal | Evitar eliminar URLs de imágenes | Sí | Asegura que las URLs de las imágenes se conserven en el editor. |
| Página de configuración principal | No cargar librerías tinyMCE | No | Habilita el editor visual para facilitar la creación de contenido. |
| Formulario Agregar/Editar | Nombre | Nombre Descriptivo | Etiqueta interna para la caja HTML. |
| Formulario Agregar/Editar | Tienda | Todas las Tiendas | Selecciona qué tiendas muestran el contenido (multi-tienda). |
| Formulario Agregar/Editar | Posición | (Elegir Hook) | Determina dónde aparece el contenido en el front office. |
| Formulario Agregar/Editar | Activo | Sí | Alterna la visibilidad de la caja HTML en el front office. |
| Formulario Agregar/Editar | Solo en páginas seguras (SSL) | No (o Sí si es crítico) | Restringe la visualización a páginas HTTPS. |
| Formulario Agregar/Editar | Solo en la página de inicio | No | Restringe la visualización solo a la página de inicio. |
| Formulario Agregar/Editar | Contenido | (Su HTML/JS/CSS) | El contenido real a mostrar. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P1: Mi caja HTML no aparece en el front office. ¿Qué debo verificar?**
R1:

- **¿Está activa?** Vaya a la configuración del módulo y asegúrese de que el interruptor "Activo" de su caja esté en "Sí".
- **¿Posición (Hook) correcta?** Verifique que haya seleccionado la "Posición" (hook) correcta donde espera que aparezca el contenido. Algunos hooks son específicos de ciertas páginas (por ejemplo, `displayProductAdditionalInfo` solo en páginas de productos).
- **¿Solo en la página de inicio?** Si configuró "Solo en la página de inicio" en "Sí", solo aparecerá en su página de inicio principal.
- **¿Solo SSL?** Si "Solo en páginas seguras (SSL)" está en "Sí", asegúrese de que está viendo una página HTTPS.
- **Caché:** Borre la caché de PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché) y la caché de su navegador.
- **Errores de contenido:** Si su contenido HTML/JS/CSS tiene errores, podría impedir que la caja se renderice. Intente con un simple texto "Hola Mundo" para probar.

**P2: El editor TinyMCE (editor visual) no funciona o se ve extraño.**
R2:

- **Configuración "No cargar librerías tinyMCE":** Asegúrese de que esté configurada en "No" en la configuración global del módulo si desea utilizar el editor visual.
- **Conflictos de tema:** A veces, los temas personalizados u otros módulos pueden interferir con TinyMCE. Intente deshabilitar temporalmente otros módulos para ver si el problema se resuelve.
- **Problemas del navegador:** Intente con un navegador diferente o borre la caché y las cookies de su navegador.

**P3: Mis imágenes o enlaces están rotos después de guardar el contenido de la caja HTML.**
R3:

- **Configuración "Evitar eliminar URLs de imágenes":** Asegúrese de que esté configurada en "Sí" en la configuración global del módulo.
- **Rutas absolutas vs. relativas:** Siempre use URLs absolutas (que comiencen con `http://` o `https://`) para imágenes y enlaces, especialmente si son externos o si desea que funcionen de manera consistente en todo su sitio.
- **Verifique el HTML:** Inspeccione el código HTML generado en el editor (generalmente un botón de "Código fuente") para asegurarse de que sus atributos `src` y `href` sean correctos.

**P4: ¿Cómo traduzco el contenido de mis cajas HTML a diferentes idiomas?**
R4:

- HTML Box Pro admite contenido multi-idioma. Cuando esté editando una caja HTML, verá pestañas de idioma (por ejemplo, Inglés, Francés, Español) junto al campo "Contenido".
- Haga clic en cada pestaña de idioma e introduzca el contenido traducido para ese idioma específico. El módulo mostrará automáticamente la versión de idioma correcta a sus clientes según el idioma de tienda seleccionado.

**P5: El contenido se ve bien en el escritorio pero está distorsionado en el móvil.**
R5:

- **Diseño responsivo:** Asegúrese de que el contenido HTML que está agregando esté diseñado para ser responsivo. Utilice propiedades CSS como `max-width: 100%; height: auto;` para imágenes, y considere usar consultas de medios CSS dentro de sus etiquetas `<style>` para diseños más complejos.
- **Responsividad del tema:** Si bien el módulo en sí es responsivo, si su HTML personalizado no lo es, podría romper el diseño. Pruebe a fondo en diferentes dispositivos.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo HTML Box Pro sigue una arquitectura estándar de módulo de PrestaShop, aprovechando principalmente la clase `Module` para su funcionalidad principal y `getContent()` para su configuración de Back Office. Registra hooks dinámicamente y renderiza contenido basándose en la configuración almacenada. El módulo utiliza una biblioteca `SmartyTemplatesManager` personalizada para gestionar sus formularios y plantillas de Back Office, proporcionando una interfaz de usuario consistente para agregar y editar cajas HTML. El contenido se almacena en la tabla `ps_configuration`, con cada caja HTML representada por una clave de configuración única.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores dedicados de front-office o back-office en los directorios `controllers/front` o `controllers/admin`. Toda la lógica del Back Office se maneja dentro del método `getContent()` del archivo `htmlboxpro.php`, que renderiza formularios y procesa envíos. La renderización del contenido del front-office se maneja directamente a través de la ejecución de hooks dentro del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

El módulo no define clases `ObjectModel` personalizadas ni otras clases principales en un directorio `classes/`. Toda la gestión de datos y la lógica de negocio están encapsuladas dentro del archivo principal del módulo `htmlboxpro.php`. Las configuraciones de las cajas HTML se almacenan directamente en la tabla `ps_configuration`, con claves como `hbp_name_X`, `hbp_content_X_Y`, `hbp_hook_X`, etc., donde `X` es el ID de la caja e `Y` es el ID del idioma.

### 4.4 Activos JavaScript (`views/js/`)

- `htmlboxpro/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`
  - **Alcance:** Back-office.
  - **Responsabilidad:** Proporciona funcionalidad JavaScript para la biblioteca `SmartyTemplatesManager`, que se utiliza para renderizar y gestionar los formularios de configuración del módulo (por ejemplo, agregar/editar cajas HTML). Esto incluye elementos de formulario dinámicos, interacciones AJAX para guardar/cargar datos de plantillas y, potencialmente, gestión de pestañas.
- `htmlboxpro/views/js/script.js`
  - **Alcance:** Back-office.
  - **Responsabilidad:** Contiene JavaScript específico del módulo para la página de configuración del Back Office. Esto podría incluir oyentes de eventos para envíos de formularios, actualizaciones dinámicas de la lista de cajas HTML u otras mejoras de la interfaz de usuario específicas de HTML Box Pro.
- `htmlboxpro/views/js/tinymce16-force-urls.inc.js`
  - **Alcance:** Back-office.
  - **Responsabilidad:** Este script se carga cuando la opción "Evitar eliminar URLs de imágenes" está habilitada. Contiene la configuración y los plugins de TinyMCE diseñados específicamente para evitar que el editor elimine o modifique URLs absolutas, particularmente para imágenes. Asegura que los atributos `src` permanezcan intactos.
- `htmlboxpro/views/js/tinymce16.inc.js`
  - **Alcance:** Back-office.
  - **Responsabilidad:** Este script contiene la inicialización y configuración del editor TinyMCE para el módulo. Define la barra de herramientas del editor, los plugins y el comportamiento general al editar el contenido de la caja HTML. Se carga cuando la opción "No cargar librerías tinyMCE" está deshabilitada.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `htmlboxpro/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`
  - **Alcance:** Estilo del formulario de administración del Back-office.
  - **Responsabilidad:** Proporciona estilo para los componentes de la interfaz de usuario de la biblioteca `SmartyTemplatesManager`, asegurando una apariencia consistente para los formularios de configuración del módulo dentro del Back Office de PrestaShop.
- `htmlboxpro/views/css/styles.css`
  - **Alcance:** Estilo del formulario de administración del Back-office.
  - **Responsabilidad:** Contiene reglas CSS específicas del módulo para la página de configuración de HTML Box Pro, como el estilo para la lista de cajas HTML, botones u otros elementos personalizados dentro de la interfaz de administración del módulo.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

El módulo utiliza en gran medida las plantillas Smarty para su interfaz de Back Office.

- **Plantillas de hook (`htmlboxpro/`)**:
  - `htmlboxpro/html.tpl`: Esta es la plantilla principal del front-office. Es responsable de renderizar el contenido real de la caja HTML (`{$htmlboxpro_content}`) dentro del hook seleccionado en el front office.
- **Plantillas de administración (`views/templates/admin/`)**:
  - `htmlboxpro/views/templates/admin/_configure/helpers/form/form.tpl`: Esta plantilla es probablemente una anulación o una plantilla específica utilizada por el formulario de configuración del módulo, posiblemente personalizando cómo el `HelperForm` estándar de PrestaShop renderiza sus campos, especialmente para el editor TinyMCE.
- **Plantillas de administración (`views/templates/`)**:
  - `htmlboxpro/views/custom_hook_info.tpl`: Probablemente muestra información o instrucciones relacionadas con hooks personalizados.
  - `htmlboxpro/views/form-add-new.tpl`: Plantilla para el formulario "Agregar nueva Caja HTML".
  - `htmlboxpro/views/form-edit.tpl`: Plantilla para el formulario "Editar Caja HTML".
  - `htmlboxpro/views/messages.tpl`: Se utiliza para mostrar mensajes de éxito, error o informativos en el Back Office.
  - `htmlboxpro/views/scripts.tpl`: Probablemente incluye activos JavaScript y CSS para la página de configuración del Back Office.
- **Plantillas de la biblioteca SmartyTemplatesManager (`htmlboxpro/lib/smartyTemplatesManager/tpl/`, `htmlboxpro/lib/smartyTemplatesManager/views/`)**:
  - `htmlboxpro/lib/smartyTemplatesManager/tpl/example.tpl`: Una plantilla de ejemplo, probablemente para fines de desarrollo o demostración dentro de la biblioteca.
  - `htmlboxpro/lib/smartyTemplatesManager/views/buttonManager.tpl`: Renderiza botones o enlaces de acción dentro de la interfaz de `SmartyTemplatesManager`.
  - `htmlboxpro/lib/smartyTemplatesManager/views/createTemplateForm.tpl`: Se utiliza para crear nuevas plantillas/elementos dentro del contexto de `SmartyTemplatesManager`.
  - `htmlboxpro/lib/smartyTemplatesManager/views/editTemplateForm.tpl`: Se utiliza para editar plantillas/elementos existentes dentro del contexto de `SmartyTemplatesManager`.
  - `htmlboxpro/lib/smartyTemplatesManager/views/mainForm.tpl`: El envoltorio o estructura principal para los formularios gestionados por `SmartyTemplatesManager`.
  - `htmlboxpro/lib/smartyTemplatesManager/views/selectInput.tpl`: Una plantilla genérica para renderizar una entrada de selección desplegable.
  - `htmlboxpro/lib/searchTool/views/scripts.tpl`: Probablemente incluye activos JavaScript y CSS para un componente de herramienta de búsqueda dentro del Back Office.

### 4.7 Esquema de la base de datos y mapa de Hooks

- **Tablas de la base de datos**:

  - El módulo no crea tablas SQL personalizadas. Toda la configuración de las cajas HTML se almacena en la tabla estándar `ps_configuration` de PrestaShop.
  - Las claves de configuración siguen un patrón como:
    - `HBP_NAME_{ID}`: Nombre de la caja HTML.
    - `HBP_CONTENT_{ID}_{LANG_ID}`: El contenido HTML/JS/CSS real para una caja y un idioma específicos.
    - `HBP_HOOK_{ID}`: El nombre del hook donde se muestra la caja.
    - `HBP_ACTIVE_{ID}`: Booleano (0/1) que indica si la caja está activa.
    - `HBP_SSL_{ID}`: Booleano (0/1) que indica si solo está en páginas SSL.
    - `HBP_HOMEPAGE_{ID}`: Booleano (0/1) que indica si solo está en la página de inicio.
    - `HBP_SHOP_{ID}`: Lista de IDs de tienda separadas por comas (para multi-tienda).
    - `HBP_LAST_ID`: Almacena el último ID utilizado para una caja HTML para generar IDs únicos.
    - `HBP_NOTINYJS`: Configuración global para "No cargar librerías tinyMCE".
    - `HBP_FORCEURLS`: Configuración global para "Evitar eliminar URLs de imágenes".
    - Otras claves como `MYPRESTA_UPDATES`, `UPDATE_HTMLBOXPRO`, `UPDATEV_HTMLBOXPRO` para la gestión de actualizaciones.
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayAfterCarrier` | Después de la selección del transportista en el proceso de pago. | Mostrar contenido relacionado con las opciones de envío o los pasos finales. |
| `displayFooterBefore` | Antes del contenido principal del pie de página. | Agregar contenido encima del pie de página estándar. |
| `displayLeftColumn` | En la barra lateral izquierda de las páginas aplicables. | Mostrar bloques de la barra lateral (por ejemplo, categorías, filtros, información personalizada). |
| `displayCustomerAccountForm` | Dentro del formulario de creación/edición de la cuenta del cliente. | Agregar campos o información personalizada relacionada con las cuentas de los clientes. |
| `displayRightColumnProduct` | En la barra lateral derecha de las páginas de productos. | Mostrar contenido de la barra lateral específico del producto (por ejemplo, productos relacionados, insignias de confianza). |
| `displayBanner` | En la parte superior de la página, típicamente para un banner de todo el sitio. | Mostrar banners promocionales o anuncios. |
| `actionAdminControllerSetMedia` | Cuando un controlador de administración establece sus medios (CSS/JS). | Inyectar CSS/JS personalizado en el Back Office (utilizado por el módulo para sus propios activos de administración). |
| `displayOrderConfirmation` | En la página de confirmación del pedido después de una compra exitosa. | Mostrar mensajes de agradecimiento, información de seguimiento o ventas adicionales. |
| `displayHeader` | En la sección `<head>` de cada página. | Ideal para inyectar metaetiquetas, scripts de seguimiento o CSS/JS global. |
| `displayCartExtraProductActions` | Dentro del resumen del carrito, cerca de las acciones del producto. | Agregar contenido relacionado con los artículos del carrito (por ejemplo, ventas adicionales, ventas cruzadas, información de envío). |
| `displayFooter` | En la sección principal del pie de página de la tienda. | Agregar contenido general del pie de página, enlaces o información de derechos de autor. |
| `displayPaymentByBinaries` | Durante el proceso de selección de pago. | Mostrar información relacionada con el pago o sellos de confianza. |
| `displayCustomerLoginFormAfter` | Después del formulario de inicio de sesión del cliente. | Agregar contenido debajo del formulario de inicio de sesión (por ejemplo, enlaces de "olvidó su contraseña", avisos de registro). |
| `displayReassurance` | Dentro del bloque de tranquilidad del producto (a menudo debajo de la imagen del producto). | Mostrar elementos de confianza como envío gratuito, pago seguro, devoluciones fáciles. |
| `displayProductAdditionalInfo` | Debajo de la descripción del producto o del bloque de información principal. | Agregar detalles adicionales del producto, guías de tallas o contenido personalizado. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, inicie sesión en su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está listo para ayudarle con cualquier problema o pregunta relacionada con el módulo HTML Box Pro.
