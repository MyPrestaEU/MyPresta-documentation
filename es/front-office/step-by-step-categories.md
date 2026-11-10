---
title: Step by Step - documentación y manual de usuario
sidebar:
  label: Step by Step - documentación y manual de usuario
description: Guía de configuración y de resolución de problemas para tiendas que ya tienen el filtro de categorías Step by Step.
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Step by step - categories en MyPresta.eu](https://mypresta.eu/modules/front-office-features/step-by-step-categories.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/step-by-step-categories/)
>
> ---


## 1. Requisitos

El módulo funciona en PrestaShop. No necesita otro módulo ni una cuenta externa.

- PrestaShop desde 1.6.0.0, incluidos PrestaShop 8 y 9.
- PHP en la versión que pide esa versión de PrestaShop. La comprobación de actualizaciones usa cURL si PHP lo tiene. Si no, abre la dirección con una petición normal. No instale una extensión PHP extra para las listas.
- No hace falta ningún otro módulo.
- En multitienda un bloque puede pertenecer a una tienda o a todas.

## 2. Instalación

1. En el back office abra **Módulos** y después **Gestor de módulos**.
2. Suba el archivo zip y pulse **Instalar**.
3. Abra **Configurar** en **Step By Step - categories tree**. La página tiene **Blocks**, **Settings** y **Updates**. **Blocks** es la lista de conjuntos de listas. La primera visita crea la página oculta de esa lista. No aparece como entrada propia en el menú izquierdo.
4. La instalación no vacía la caché en un paso aparte. Si la tienda sigue mostrando el diseño anterior después de una actualización, vacíe la caché en **Parámetros avanzados**, **Rendimiento**.

La desinstalación quita esa página oculta. Los bloques, los títulos, las etiquetas y los dos interruptores globales se quedan en la base de datos. Si vuelve a instalarlo, los mismos bloques siguen ahí. Abra **Configurar** una vez para volver a registrar la página de la lista.

Aparte del interruptor normal del **Gestor de módulos** no hay una acción propia de activación. Si desactiva el módulo, las listas desaparecen de la tienda y los bloques guardados se quedan.

## 3. Configuración y uso en el back office

Cree un bloque, fije la profundidad del árbol de categorías y elija el sitio en la tienda. El cliente elige una categoría. La lista siguiente carga sus hijas. **ok** abre la categoría elegida, o un producto si la lista de productos está activa.

Las capturas de este capítulo son del back office en inglés. Los textos de la pantalla siguen en inglés.

### 3.1 Página de configuración del módulo

Abra **Módulos**, **Gestor de módulos**, **Step By Step - categories tree**, **Configurar**.

![Ajustes](https://mypresta.eu/docs/images/docs/stepbystep-configure-settings.webp)

Arriba están **Blocks**, **Settings** y **Updates**. **Blocks** sale de esta página y abre la lista de bloques. **Settings** es la pestaña inicial. Debajo de la barra dice que estas opciones valen para cada bloque y que los bloques se editan en **Blocks**.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Reset search fields** | No | Yes vacía las listas después de una búsqueda. No guarda las categorías que el visitante eligió. El navegador guarda esa elección 30 minutos. |
| **Include Select2 library** | No | Yes carga el script y la hoja de estilo extra para **Search inside dropdown** de un bloque. No deja listas normales. |

Pulse **Save**. La página muestra **Settings saved.**

![Actualizaciones](https://mypresta.eu/docs/images/docs/stepbystep-configure-updates.webp)

**Updates** es el formulario **MyPresta updates**.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Manual check** | botón **Check now** | Pregunta a MyPresta si existe una versión más nueva. **New version available!** lleva al registro de cambios. **Module is up to date!** significa que esta instalación coincide con la versión publicada. El botón no sube un zip. |
| **Automatic notifications** | Enabled | Enabled repite esa comprobación más o menos cada 3 días mientras trabaja en el back office. Disabled la omite. |
| **Product page** | enlace a la página del módulo | Abre la página de Step by Step en mypresta.eu. |

**Save** muestra **Update settings saved.** Suba un zip nuevo desde el **Gestor de módulos** cuando aparezca una versión más nueva.

### 3.2 Lista de bloques

Abra **Blocks**. Debajo de la barra dice que cada bloque es un conjunto de listas.

![Lista de bloques](https://mypresta.eu/docs/images/docs/stepbystep-blocks-list.webp)

| Campo | Al inicio | Qué hace |
|---|---|---|
| **ID** | se asigna al guardar | Número del bloque. Sirve para distinguir filas. |
| **Title** | Block y el número, hasta que escriba un título | Encabezado en el idioma del back office. |
| **Depth** | 3 en un bloque nuevo | Cuántas listas dibuja el bloque. |
| **Root category** | categoría Home de la tienda en un bloque nuevo | Padre de la primera lista, como número y nombre. |
| **Hook** | Top en un bloque nuevo | Sitio del bloque en la tienda. |
| **Active** | Yes | El icono activa o desactiva el bloque. Off oculta las listas y deja la fila. |
| **Position** | siguiente posición libre | Arrastre la fila para cambiar el orden de los bloques del mismo hook. |

Las acciones de fila son **Edit** y **Delete**. **Bulk actions** tiene **Enable selection**, **Disable selection** y **Delete selected**. La confirmación pregunta **Delete selected blocks?**

**Add new** abre un formulario vacío. Un bloque nuevo está activo, profundidad 3, raíz la categoría Home, orden por ID ascendente, contador de productos apagado, botón después de la última lista, productos apagados, envío automático apagado, búsqueda en la lista apagada, etiqueta dentro de la lista, hook Top y la tienda actual. Guárdelo. El formulario se vuelve a abrir para que rellene las etiquetas. Las etiquetas aparecen en el formulario cuando el bloque ya existe.

La lista muestra los bloques de la tienda en la que está y los bloques con **All shops**.

### 3.3 Formulario del bloque

Abra una fila con **Edit**, o use **Add new** y luego la pantalla de edición que sigue al primer guardado.

![Formulario del bloque, parte superior](https://mypresta.eu/docs/images/docs/stepbystep-block-form.webp)

![Formulario del bloque, etiquetas y posición](https://mypresta.eu/docs/images/docs/stepbystep-block-form-bottom.webp)

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Block title** | vacío | Encabezado encima de las listas. Un campo por idioma de la tienda. |
| **Depth** | 3 | Cuántas listas dibuja el bloque. Guarde el bloque y ábralo otra vez para rellenar una etiqueta por nivel. El formulario muestra como máximo 30 campos de etiqueta. |
| **Root category** | categoría Home | La primera lista muestra las hijas de esta categoría. |
| **Sort method** | By ID | By ID, By name o By position. Position es el orden de la categoría en el catálogo. |
| **Sort direction** | Ascending | Ascending o Descending. |
| **Products counter** | No | Yes escribe el número de productos entre paréntesis detrás del nombre de la categoría. |
| **Submit button** | After last select box | After each select box muestra **ok** en el nivel en el que está el cliente. After last select box muestra un **ok** para todo el conjunto. |
| **Include products** | No | Yes muestra una lista de productos de la última categoría elegida. |
| **Auto submit** | No | Yes envía el formulario en cuanto se elige la última categoría disponible. La tienda abre esa categoría. Vale cuando **Include products** está apagado. Si la categoría elegida no tiene hijas, la tienda también la abre. |
| **Search inside dropdown** | No | Yes activa la búsqueda dentro de las listas. En **Settings**, **Include Select2 library** también tiene que estar encendido. |
| **Exclude categories** | vacío | IDs de categoría que no deben salir en las listas. Sepárelos con comas, por ejemplo 1,2,3,4,5,6. La búsqueda junto al campo encuentra una categoría y añade su ID. |
| **Show on category pages** | vacío | Vacío muestra el bloque en cada página donde está su hook. IDs de categoría, separados por comas, lo muestran solo en esas páginas de categoría. |
| **Label position** | Inside select box | Inside select box pone la etiqueta como primera opción. Outside select box la imprime encima del campo. |
| **Label 1**, **Label 2** y siguientes | vacío | Un campo por nivel y por idioma. Aparecen después de guardar el bloque. Cambie **Depth** y guarde si necesita más o menos. |
| **Module position** | Top | Top, displaySearch, TopColumn, Left column, Right column, Home o displaySbs. |
| **Position top settings** | Blocks | Blocks apila las listas. Wide horizontal bar las pone en una fila. La barra ancha vale en Top y displaySearch. Los demás sitios siguen apilados. En la barra ancha, **ok** queda detrás de la última lista y baja a la línea siguiente si no cabe. |
| **Shop** | la tienda que está editando | Una tienda o **All shops**. **All shops** deja el bloque en cada tienda. |
| **Active** | Yes | No oculta el bloque en la tienda. |

Pulse **Save**. PrestaShop muestra su confirmación habitual. Borrar un bloque borra también el título, la elección de la barra ancha y las etiquetas de nivel.

Para mostrar un bloque en un archivo del tema que no tiene un hook ya colocado, use el hook displaySbs y ponga **Module position** en displaySbs. Los demás sitios se enganchan en **Diseño**, **Posiciones**, si el tema no los imprime solo.

## 4. Tienda

El cliente ve el título del bloque y las listas.

1. La primera lista muestra las hijas de la categoría raíz. Las listas siguientes quedan inactivas hasta que el nivel anterior tiene una categoría.
2. El cliente elige una categoría. Un indicador cubre el bloque. La lista siguiente se llena con las hijas. El indicador desaparece cuando la lista está lista, y también si la petición falla.
3. Las IDs excluidas no salen en esas listas.
4. Con **Submit button** en after each select box, **ok** está en el nivel actual. Con after last select box hay un **ok** para el conjunto.
5. **ok** abre la categoría elegida.
6. Con **Include products**, el último nivel añade una lista de productos. La primera opción es **- Select Product -**. **ok** usa entonces el producto elegido.
7. Con **Auto submit** encendido e **Include products** apagado, la última categoría se abre sin **ok**. La misma redirección vale si la categoría elegida no tiene hijas.
8. Con **Reset search fields** apagado, una visita posterior puede mostrar las mismas categorías. El navegador las guarda 30 minutos. Con la opción encendida, las listas empiezan vacías.
9. Si **Search inside dropdown** e **Include Select2 library** están encendidos, el cliente puede escribir dentro de la lista.

En la columna izquierda y en la derecha los niveles van uno bajo otro, con el título en mayúsculas como en Classic. En la barra ancha los niveles van en una fila. En una pantalla estrecha la barra ancha se apila. Los colores, el borde y el botón **ok** salen del tema, también Hummingbird y Classic en PrestaShop 9.

Un bloque con **Show on category pages** relleno no aparece en otras páginas. Un bloque inactivo no aparece. Un bloque de otra tienda tampoco.

## 5. Problemas

**El bloque no aparece en la tienda.** Abra el bloque y revise **Active**, **Module position** y **Shop**. **Show on category pages** vacío lo muestra en cada página de ese hook. Una lista rellena lo muestra solo en esas páginas de categoría. En **Diseño**, **Posiciones**, compruebe que el hook está en las páginas previstas. Para un sitio propio, la plantilla tiene que llamar a displaySbs y el bloque tiene que usar esa posición.

**La lista siguiente no se llena, o el indicador se queda.** Vacíe la caché de la tienda para que tome la hoja de estilo y el script actuales. El indicador debe desaparecer cuando termina la petición, también si la respuesta no se puede aplicar. Si la tienda sigue mostrando el cargador gif anterior, el CSS anterior está en caché.

**La búsqueda dentro de la lista no hace nada.** Encienda **Include Select2 library** en **Settings** y **Search inside dropdown** en el bloque. Guarde los dos. Vacíe la caché.

**A un bloque nuevo le faltan las etiquetas.** Guarde el bloque una vez. Ábralo otra vez. **Label 1** y el resto aparecen cuando el bloque existe, y solo hasta el **Depth** guardado.

**Falta una categoría que debería estar en la lista.** Quite su ID de **Exclude categories**. Compruebe que es hija del padre elegido y que está activa en el catálogo.

**La barra ancha sigue apilando los campos.** **Wide horizontal bar** vale en Top y displaySearch. Izquierda, derecha, inicio, TopColumn y displaySbs siguen apilados. En el teléfono la barra ancha se apila a propósito.

**Después de una actualización falta la página Blocks.** Abra **Configurar** una vez. Esa visita registra la página. No desinstale el módulo si quiere seguir usando las filas que ya tiene. La desinstalación quita la página y deja las filas.

**La pantalla de configuración antigua no tiene icono de papelera.** Esa es una versión anterior. Suba el zip actual de la cuenta de cliente. En la versión actual se borra un bloque en la lista **Blocks**, con **Delete** en la fila o con **Delete selected**.

## 6. Para desarrolladores

### 6.1 Resumen

Nombre técnico `stepbystep`, clase `Stepbystep`, versión 1.9.0, autor MyPresta.eu, pestaña `front_office_features`. El nombre en el back office es **Step By Step - categories tree**.

`AdminStepbystepBlocksController` escribe filas en `sbs_block` y el título, las etiquetas y la bandera de la barra ancha en `Configuration`. Los hooks de la tienda leen las filas activas de la tienda actual o con `id_shop = 0`. `controllers/front/tree.php` entrega el script que rellena la lista siguiente.

### 6.2 Archivos

| Archivo | Función |
|---|---|
| `stepbystep.php` | Instalación, hooks, formulario de ajustes, HTML de las listas, script de la tienda. |
| `controllers/admin/AdminStepbystepBlocksController.php` | Lista de bloques y formulario del bloque. |
| `models/SbsBlock.php` | Modelo de objeto de `sbs_block`. |
| `controllers/front/tree.php` | Controlador de la tienda que entrega el script del nivel siguiente. |
| `views/templates/hook/front.tpl` | Marcado de la tienda para cada hook. |
| `views/templates/hook/header.tpl` | Imprime el script en línea. |
| `views/templates/admin/configure.tpl` | Barra Blocks, Settings, Updates. |
| `css/sbs-front.css` | Diseño de la tienda, variables del tema, indicador. |
| `js/advajax.js` | Petición de las listas. |
| `lib/updatesChecker.php` | Comprobación de actualizaciones. Clase `stepbystepUpdate`. |
| `lib/searchTool/searchTool.php` | Búsqueda del ID de categoría en el formulario del bloque. Clase `searchToolstepbystep`. |
| `lib/prestashop9compatibility.php` | Clase `stepbystepPrestashopNewCompatibility`. |
| `views/css/admin.css` | Barra del back office. |

`tree.php` en la raíz del módulo es la copia anterior del controlador de la tienda. El enlace de la tienda usa `controllers/front/tree.php`. `views/templates/hook/block.tpl`, `blockSbs.tpl`, `top.tpl` y `displaySearch.tpl` no se renderizan. `css/sbs-block.css` y `css/sbs-top.css` no se cargan.

### 6.3 Controladores

`AdminStepbystepBlocksController` extiende `ModuleAdminController`. `class_name` es `AdminStepbystepBlocks`. `id_parent` es `-1`, así que la página está oculta en el menú. El identificador de la lista es `id`. Arrastrar la posición llama a `ajaxProcessUpdatePositions`. El filtro de la lista es `id_shop` de la tienda del contexto o `0`.

`stepbysteptreeModuleFrontController` es el controlador de tienda `tree`. `initContent` pone `ajax` y no llama a `parent::initContent`. Lee `sbs_block`, `sbs_pid`, `sbs_lvl` y, al confirmar, `sbs_blockid` y `sbs_cidlink`. El cuerpo de la respuesta es JavaScript. Un bloque que no existe cierra la respuesta.

### 6.4 Hooks

Hooks registrados: `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayTop`, `displaySearch`, `displayHome`, `displaySbs`, `displayBackOfficeHeader`. Desde PrestaShop 1.6 también `displaytopColumn`.

| Hook | Valor de posición del bloque | Diseño |
|---|---|---|
| `displayTop` | 1 | arriba, barra ancha si `sbs_top_type{id}` es 1 |
| `displayLeftColumn` | 2 | apilado |
| `displayRightColumn` | 3 | apilado |
| `displayHome` | 4 | apilado |
| `displaytopColumn` | 5 | apilado |
| `displaySearch` | 6 | arriba, barra ancha si `sbs_top_type{id}` es 1 |
| `displaySbs` | 7 | apilado |

`displayHeader` carga `js/advajax.js` y `css/sbs-front.css`. Si `SBS_SELECT2` es 1, carga también Select2. No hay una anulación de `enable()` ni de `disable()`.

### 6.5 Overrides

El módulo no sustituye ninguna clase ni ningún controlador de PrestaShop.

### 6.6 Base de datos

| Tabla | Contenido |
|---|---|
| `ps_sbs_block` | `id`, `depth`, `root`, `orderby`, `orderway`, `counter`, `each_submit`, `lbl_position`, `block_position`, `position`, `active`, `products`, `last_submit`, `search_inside`, `exclude`, `id_shop`, `on_cat_only`, `id_categories`. |

El prefijo es el de la tienda. La desinstalación no borra la tabla. `inconsistency()` añade una columna que falte de esta lista cuando se abre la configuración del módulo o la lista de bloques. `on_cat_only` se queda y no está en el formulario. La tienda usa `id_categories`.

### 6.7 Claves de configuración y traducciones

| Clave | Si falta |
|---|---|
| `SBS_RESET` | Cuenta como 0. La elección se queda 30 minutos en cookies `sbs_selectbox_{block}_{level}`. |
| `SBS_SELECT2` | Cuenta como 0. Select2 no se carga. |
| `sbs_title{id}` | Título del bloque, multilingüe. |
| `{id}sbs_lbl_{n}` | Etiqueta del nivel `n`, multilingüe, de 1 a la profundidad, máximo 30. |
| `sbs_top_type{id}` | 0 apilado, 1 barra ancha. |

La instalación también escribe `sbs_depth`, `sbs_counter`, `sbs_each_submit`, `sbs_position`, `sbs_lbl_position` y `sbs_root`. El formulario del bloque no lee esas claves. Los bloques nuevos usan los valores de `prepareObjectDefaults()`.

Las traducciones están en `translations/{iso}.php`. Los textos del controlador de bloques tienen el origen `AdminStepbystepBlocksController`. El texto del botón es el texto del módulo `ok`. El marcador de producto es `- Select Product -`.

### 6.8 Ampliación

Sustituya `views/templates/hook/front.tpl` en el tema como `themes/{theme}/modules/stepbystep/views/templates/hook/front.tpl`. Sustituya `css/sbs-front.css` por el mismo camino si el tema debe cambiar el diseño. El sitio del botón en la barra ancha es el orden flex de esa hoja: el `.sbs__actions` visible queda detrás de las listas y baja de línea con ellas.

## 7. Ayuda

Página del módulo: [Step by Step categories](https://mypresta.eu/modules/front-office-features/step-by-step-categories.html).

Para escribir sobre este módulo, entre en la cuenta de cliente de [mypresta.eu](https://mypresta.eu), abra el formulario de contacto y elija **Support for paid modules**. Ese asunto indica que hace falta iniciar sesión. Después de entrar, elija este módulo en el historial de compras.
