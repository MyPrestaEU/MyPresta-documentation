---
title: "Características de la combinación - manual del comerciante"
description: "Manual de configuración y resolución de problemas para quien ya tiene el módulo instalado."
sidebar:
  label: "Características de la combinación - manual del comerciante"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Product combination features en MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-combination-features.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/product-combination-features/)
>
> ---


Nombre técnico: `combfeat`. Versión **1.4.0**. En el back-office el módulo se llama **Características de la combinación**.

## 1. Requisitos y compatibilidad

- **PrestaShop:** de 1.7.0.0 a 9.x (`ps_versions_compliancy` hasta 9.99.99).
- **PHP:** la versión que exija esa versión de PrestaShop.
- **Ficha de producto:** el tema debe exponer la combinación elegida en el atributo `data-product` de `#product-details` (estándar de PrestaShop) y disparar el evento `updatedProduct` al cambiar los atributos. Classic y los temas basados en él lo hacen.
- **PrestaShop 8 y 9, pestaña Módulos del producto:** el archivo `src/PrestaShopBundle/Resources/views/Admin/Sell/Catalog/Product/Blocks/modules-content.html.twig` debe poder escribirse en la instalación o en la primera apertura de la configuración. Véase la sección 3.
- **Navegación por facetas (opcional):** `ps_facetedsearch` instalado, permiso para crear una vista SQL y escritura en `modules/ps_facetedsearch/src/Adapter/MySQL.php`.
- **Comprobación de actualizaciones (opcional):** `allow_url_fopen` para que el módulo llame a `https://dev.mypresta.eu`.

## 2. Dónde trabajar en el back-office

| Lugar | Ruta | Para qué |
| --- | --- | --- |
| Configuración del módulo | **Módulos > Gestor de módulos**, buscar **Características de la combinación**, **Configurar** | Interruptores, selectores CSS, modo de título, navegación por facetas, importación CSV, actualizaciones |
| Contenido de la combinación | **Catálogo > Productos**, editar el producto, pestaña **Módulos**, bloque **Contenido de la combinación** | Características, descripción y títulos de cada combinación |
| Catálogo de características | **Catálogo > Atributos y características** (el nombre depende de la versión de PrestaShop) | Crear características y valores antes de asignarlos en el producto. La importación CSV puede crear los que falten |
| Plantilla de navegación por facetas | Configuración del módulo Navegación por facetas | Añadir la característica a la plantilla de filtros. Este módulo no lo hace solo |

El módulo no tiene una entrada de menú propia ni un controlador de tienda o de back-office.

## 3. Archivos que el módulo modifica

### 3.1 Pestaña Módulos del producto en PrestaShop 8 y 9

En la instalación, y cada vez que se abre la página de configuración, el módulo edita:

`src/PrestaShopBundle/Resources/views/Admin/Sell/Catalog/Product/Blocks/modules-content.html.twig`

Sustituye `{{ module.content|raw_purified }}` por `{{ module.content|raw }}`. La primera vez copia el archivo original a `modules-content.html.twig.raw.bak` junto a él.

PrestaShop 8 y 9 depuran el HTML que los módulos imprimen en la ficha de producto. Sin este cambio el editor **Contenido de la combinación** queda vacío o sus campos no se envían al guardar el producto. En PrestaShop 1.7 ese archivo Twig no existe. El módulo omite el cambio.

Si el archivo no se puede leer o escribir, el módulo no muestra un error. Revise los permisos si la pestaña Módulos sigue vacía.

### 3.2 Adaptador de la navegación por facetas

Con **Filter combination features in Faceted Search** activado (valor por defecto), el módulo crea la vista SQL `{prefix}combfeat_feature_product` y apunta `modules/ps_facetedsearch/src/Adapter/MySQL.php` a esa vista. La vista es la lista de características del producto más las características activas de las combinaciones.

Desactivar la opción, desactivar el módulo o desinstalarlo vuelve a escribir el código original del adaptador. La desinstalación también elimina la vista cuando el adaptador ya no la menciona.

La página de configuración muestra un aviso si la vista no se puede crear, si el archivo del adaptador no existe, no se puede leer, no se puede escribir, o no coincide con el código esperado de Faceted Search. Los mensajes (en inglés en el módulo):

- Could not create the Faceted Search feature view. Combination features will not appear in category filters.
- Faceted Search is installed, but its database adapter was not found. Combination features will not appear in category filters.
- Faceted Search adapter could not be read. Combination features will not appear in category filters.
- This Faceted Search version does not use the expected feature table. Combination features will not appear in category filters.
- Faceted Search adapter is not writable. Make modules/ps_facetedsearch/src/Adapter/MySQL.php writable so combination features can be filtered.
- Faceted Search adapter could not be updated. Combination features will not appear in category filters.

## 4. Configuración del módulo

Abra **Configurar**. En la página hay dos formularios y, debajo, el panel **Actualizaciones de MyPresta**. **Guardar** en el formulario de ajustes envía `submitCombfeatSettings`. **Import** envía `submitCombfeatImport`.

### 4.1 Activar características para combinaciones

Clave: `combfeat_p_feat`. Por defecto: **Activado**.

Si está activado, cada combinación de la pestaña **Módulos** del producto tiene una pestaña **Características**. Ahí se asignan valores que ya existen.

Si está desactivado, esa pestaña se oculta. El script de la tienda es aparte: características y descripciones las actualiza el mismo script, descrito en la sección 6.

**Guardar un producto con este interruptor apagado borra las características de combinación de ese producto.** El formulario ya no contiene los campos de características. Un guardado vacía las filas de características del módulo para el producto y vuelve a escribir solo lo que envió el formulario. Las descripciones y los títulos se conservan. Vuelva a activar la opción antes de editar el producto si esas características deben quedarse.

### 4.2 Clase CSS de la ficha técnica

Clave: `combfeat_ds`. Por defecto: `.data-sheet`.

Un selector jQuery. El módulo sustituye el **HTML interno** del elemento encontrado por pares:

```html
<dt class="name">Característica</dt><dd class="value">Valor</dd>
```

Apúntelo al `<dl>` que ya contiene esas filas. En el tema Classic es `dl.data-sheet`, así que el valor por defecto es el adecuado. Un bloque mayor, como `.product-features` o `#product-details`, queda sustituido por completo por los pares `<dt>` / `<dd>`.

Si el selector no encuentra nada y la combinación elegida tiene características, el módulo sustituye todo el contenido de `#product-details` por una sección nueva de ficha técnica. Desaparecen la referencia, la marca y el resto de lo que había en `#product-details`. Ajuste el selector para que ese recurso no se use.

### 4.3 Flujo de trabajo

Clave: `combfeat_workflow`. Por defecto: **Reemplazar las características existentes del producto** (valor `0`).

| Opción | Valor | Ficha técnica al elegir una combinación |
| --- | --- | --- |
| **Reemplazar las características existentes del producto** | `0` | Las características de la combinación sustituyen la ficha técnica. Si la combinación no tiene, se vuelven a escribir las del producto. |
| **Añadir a la lista existente de características del producto** | `1` | Las características del producto quedan primero. Las de la combinación se añaden detrás. Si la combinación no tiene, solo se ven las del producto. |

El mismo valor en el producto y en la combinación aparece dos veces en el modo **Añadir**. El módulo no quita duplicados.

Se permiten varios valores de una misma característica. Cada valor es una fila. El orden sigue la posición de la característica en el catálogo.

**El flujo de trabajo solo cambia la ficha técnica.** La descripción se sustituye siempre, en los dos modos. Véase la sección 6.4.

El script de la tienda depende de este ajuste: `views/js/combfeat.js` para Reemplazar, `views/js/combfeat-append.js` para Añadir.

### 4.4 Filter combination features in Faceted Search

Clave: `combfeat_faceted`. Por defecto: **Enabled**.

La etiqueta en pantalla está en inglés: **Filter combination features in Faceted Search**. Ese texto aún no está en los archivos de traducción del módulo. El texto de ayuda también está en inglés: los valores que solo existen en combinaciones aparecen en `ps_facetedsearch`, y un producto se cuenta si el valor está en el producto o en cualquier combinación. Hay que añadir la característica a la plantilla de Faceted Search. La lista de características del producto no cambia.

Con `ps_facetedsearch` instalado y el interruptor activado:

- En los filtros de categoría pueden aparecer valores que solo existen en combinaciones.
- Un producto se cuenta si el valor está en el producto **o en cualquiera de sus combinaciones**. El filtro no depende de la combinación que el visitante elija después. Un producto cuenta una vez, aunque varias combinaciones lleven el valor.
- La característica se añade igualmente a la plantilla de navegación por facetas. El módulo no edita plantillas.
- La lista de características de la ficha de producto en el catálogo se queda como está.

Después de guardar características de combinación, o después de una importación CSV, el módulo vacía la caché de bloques de la navegación por facetas (`layered_filter_block`) para que los filtros se reconstruyan.

### 4.5 Activar descripciones para combinaciones

Clave: `combfeat_p_desc`. Por defecto: **Activado**.

En el texto fuente inglés la etiqueta es **Turn on descriptionsfor combinations** (no hay espacio antes de «for»). La traducción española es **Activar descripciones para combinaciones**.

Si está activado, cada combinación tiene una pestaña **Descripción** con un campo de texto enriquecido por idioma de la tienda.

Si está desactivado, esa pestaña se oculta y guardar el producto no cambia las descripciones ya guardadas. Si las características siguen activadas, el script de la tienda sigue ejecutándose y aplica una descripción guardada antes. Vacíe los campos, guarde y solo entonces apague el interruptor si la tienda debe dejar de usarlas.

### 4.6 Descripción de la clase CSS / ID del objeto

Clave: `combfeat_description`. Por defecto: `#description`.

Selector jQuery del bloque cuyo HTML sustituye la descripción de la combinación. En el tema Classic `#description` es la pestaña de la descripción larga, así que el valor por defecto apunta a ese bloque.

Si el selector no encuentra nada, la descripción de la página no se toca.

El texto que se usa cuando una combinación no tiene descripción es la **descripción larga** del producto (`description`), en el idioma actual. No es la descripción corta ni la meta descripción. Si este selector apunta al bloque de la descripción corta, una combinación sin texto propio llena ese bloque con la descripción larga.

### 4.7 Activar meta título para combinaciones

Clave: `combfeat_p_title`. Por defecto: **Activado**.

Si está activado, la ficha de producto carga `views/js/combfeat-title.js`. Elegir una combinación actualiza `document.title` y, si existe, `<meta property="og:title">`.

El título del HTML que envía el servidor sigue siendo el meta título del producto. El visitante ve el título de la combinación después de que se ejecuta JavaScript. Un rastreador que no ejecuta JavaScript conserva el título del producto.

Si está desactivado, la pestaña **Meta título** se oculta, el script no se carga y guardar el producto no cambia los títulos guardados.

### 4.8 Modo de título predeterminado

Clave: `combfeat_title_default`. Por defecto: **Añadir nombre de atributo y valor (separados por comas)** (valor `1`).

Solo se usa cuando esa combinación no tiene **Título completo** ni **Añadir al título** en el idioma actual.

El título de partida es el título del navegador guardado en la primera carga de la página. Los cambios posteriores no lo vuelven a guardar, así que los fragmentos añadidos no se acumulan.

| Opción | Valor | Resultado |
| --- | --- | --- |
| **No cambiar el título de forma predeterminada** | `0` | Se queda el título de documento original. |
| **Añadir nombre de atributo y valor (separados por comas)** | `1` | Título original, luego el separador, luego grupos y valores, por ejemplo `Color: Rojo, Talla: M`. |
| **Añadir solo valores de atributos (separados por comas)** | `2` | Título original, luego el separador, luego solo los valores, por ejemplo `Rojo, M`. |

Los nombres de grupo y los valores salen del idioma actual de la tienda.

### 4.9 Separador de título

Clave: `combfeat_title_separator`. Por defecto: ` - ` (espacio, guion, espacio).

Se inserta entre el título de documento original y la parte añadida. La parte añadida es el texto del modo predeterminado o **Añadir al título** de la combinación. El separador se usa tal como está guardado, espacios incluidos.

**Título completo** no usa el separador. Sustituye él solo el título del documento.

Si el título original está vacío, se usa solo la parte añadida.

### 4.10 Referencia rápida de ajustes

| Ajuste | Clave | Por defecto |
| --- | --- | --- |
| Activar características para combinaciones | `combfeat_p_feat` | Activado (`1`) |
| Clase CSS de la ficha técnica | `combfeat_ds` | `.data-sheet` |
| Flujo de trabajo | `combfeat_workflow` | Reemplazar (`0`) |
| Filter combination features in Faceted Search | `combfeat_faceted` | Activado (`1`) |
| Activar descripciones para combinaciones | `combfeat_p_desc` | Activado (`1`) |
| Descripción de la clase CSS / ID del objeto | `combfeat_description` | `#description` |
| Activar meta título para combinaciones | `combfeat_p_title` | Activado (`1`) |
| Modo de título predeterminado | `combfeat_title_default` | Nombre de atributo y valor (`1`) |
| Separador de título | `combfeat_title_separator` | ` - ` |

## 5. Importación de características de combinación

Segundo formulario de la página de configuración. Estas etiquetas son, por ahora, los textos fuente en inglés en todos los idiomas (aún no están en los archivos de traducción).

La importación asigna valores de características a combinaciones. No importa descripciones ni títulos, y no escribe filas en la lista de características del producto (`feature_product`). Una característica o un valor que no exista se crea en el catálogo.

### 5.1 Import mode

| Modo | Qué hace |
| --- | --- |
| **Append to combination features** (por defecto) | Conserva las asignaciones ya guardadas. Una fila que ya está en esa combinación se omite. |
| **Replace features of listed combinations** | Para cada combinación que aparece en el archivo, borra las características de esa combinación en el módulo y después escribe las filas del archivo. Las combinaciones que no están en el archivo se quedan. Las descripciones y los títulos no se borran. |

### 5.2 Reglas del archivo

- UTF-8, extensión `.csv` o `.txt`. Se acepta un BOM inicial. Tamaño máximo **8 MB**.
- El separador se detecta en la línea de cabecera: punto y coma, coma o tabulador. Si no aparece ninguno, se usa el punto y coma.
- La cabecera debe identificar la combinación con `id_product_attribute` o `combination_reference`.
- La cabecera debe identificar la característica con `feature` y `value`, o con `id_feature_value`.
- Las filas vacías se omiten. Se listan como máximo 30 errores de fila; el resto se cuenta.

Nombres de columna aceptados (espacios y guiones pasan a ser guiones bajos; no importa mayúsculas o minúsculas):

| Columna | También se acepta |
| --- | --- |
| `id_product` | `product_id` |
| `id_product_attribute` | `id_combination`, `combination_id` |
| `product_reference` | — |
| `combination_reference` | `combination_ref`, `attribute_reference` |
| `feature` | `feature_name`, `id_feature` |
| `value` | `feature_value` |
| `id_feature_value` | `feature_value_id` |

`id_product` y `product_reference` son opcionales. Si los rellena, deben pertenecer a esa combinación. Una discrepancia rechaza la fila.

Búsqueda de la combinación:

- `id_product_attribute` se usa cuando es mayor que cero. Si el ID y `combination_reference` están rellenos, la referencia debe coincidir con esa fila.
- Si no, se usa la referencia de la combinación. Si varias combinaciones la comparten, añada `id_product` o `id_product_attribute`. Mensaje: Combination reference matches more than one combination.

Búsqueda del valor:

- `id_feature_value` mayor que cero carga ese valor. Las celdas de nombre y valor se ignoran.
- Si no, `feature` y `value` son obligatorios. Una celda de característica formada solo por dígitos es un ID de característica.
- Los nombres se buscan de forma exacta y después sin distinguir mayúsculas. Si coincide más de una característica o valor, la fila se rechaza. No se adivina nada.
- Una característica que no existe se crea. Su nombre se copia a cada idioma de la tienda. Longitud máxima 128.
- Un valor que no existe se crea como valor normal (no personalizado), con el mismo texto en cada idioma. Longitud máxima 255. Edite después **Catálogo > Atributos y características** si los idiomas necesitan textos distintos.

**Download sample file** envía `import/combfeat-features-sample.csv`:

```csv
id_product;id_product_attribute;product_reference;combination_reference;feature;value;id_feature_value
12;45;DEMO-1;DEMO-1-RED;Material;Cotton;
12;46;DEMO-1;DEMO-1-BLUE;Material;Wool;
;;DEMO-2;DEMO-2-XL;Composition;100% cotton;
10;25;;;;;83
```

Las filas del ejemplo significan:

1. Combinación 45 del producto 12; las referencias deben coincidir; característica Material / Cotton (se crea si falta).
2. Combinación 46 del producto 12, Material / Wool.
3. La combinación cuya referencia es `DEMO-2-XL` en el producto cuya referencia es `DEMO-2`, característica Composition / 100% cotton. Sin ID numéricos.
4. Combinación 25 del producto 10, valor de característica existente 83. Nombre y valor vacíos.

Tras una importación correcta se vacía la caché de bloques de la navegación por facetas. La confirmación indica cuántas asignaciones se guardaron, cuántas ya estaban y qué filas fallaron.

## 6. Contenido de la combinación en el producto

**Catálogo > Productos**, editar el producto, pestaña **Módulos**. Título del bloque: **Contenido de la combinación**. Subtítulo: **Características, descripciones y meta títulos por combinación**.

Cree primero las combinaciones (pestaña **Combinaciones** del producto). Si el producto no tiene, el bloque lo indica y no hay nada que editar.

### 6.1 La lista

- **Expandir todo** / **Contraer todo**.
- **Filtrar combinaciones…** coincide con el nombre de la combinación, el ID de combinación y la referencia de combinación.
- Cada fila muestra la imagen de la combinación (o un sustituto), los nombres de atributo, **Combination ID**, **Reference** cuando la combinación tiene referencia, y distintivos. Los distintivos **Características**, **Descripción** y **Título** se encienden cuando esa parte está rellena. El de características indica el número de valores. Combination ID y Reference son los textos fuente en inglés.
- La primera combinación está abierta. **Configurar** abre una fila, **Cerrar** la pliega.
- Dentro de la fila, las pestañas de los interruptores activos: **Características**, **Descripción**, **Meta título**.

Si los tres interruptores están apagados, el bloque muestra: Todas las opciones de combinación están desactivadas. Active las características, descripciones o títulos en la configuración del módulo.

### 6.2 Características

Texto de ayuda: Busque y adjunte los valores de características utilizados para esta combinación en la página del producto.

Escriba al menos **2 caracteres** del nombre de la característica o del valor, en el idioma actual del empleado. Aparecen hasta 20 coincidencias, con la etiqueta `Característica: valor`. Elegir una añade una ficha. La búsqueda solo encuentra valores que ya existen. Créelos en el catálogo o con la importación CSV.

El mismo valor no se puede añadir dos veces. Sí se pueden añadir varios valores de la misma característica. **×** quita una ficha. La retirada se guarda con el producto.

### 6.3 Descripción

Un campo de texto enriquecido por idioma. La lista de idiomas se muestra cuando la tienda tiene más de un idioma. Un HTML vacío significa que no hay descripción: en la tienda vuelve la descripción larga del producto y, al guardar, se borra la fila de ese idioma.

### 6.4 Meta título

Los dos campos son por idioma, 512 caracteres cada uno. Un campo vacío omite esa sustitución.

| Campo | Efecto en la tienda |
| --- | --- |
| **Título completo (sobrescribe todo el título)** | Sustituye todo el título del documento. El separador y el modo predeterminado no se usan. Si los dos campos están rellenos, gana este. |
| **Añadir al título (fragmento añadido al final)** | Título de documento original, luego el separador, luego este fragmento. Se usa cuando el título completo está vacío. |

Si los dos están vacíos, se aplica el modo de título predeterminado de la sección 4.8.

### 6.5 Guardado

Los cambios se guardan con el producto. Use el botón **Guardar** del producto (incluido guardar y previsualizar, según la versión de PrestaShop). El bloque no tiene un botón de guardado propio.

Al guardar, el módulo:

1. Borra cada fila de características de combinación de este producto e inserta las fichas presentes en el formulario.
2. Guarda o borra la descripción de cada idioma.
3. Guarda la fila de título de cada idioma, o la borra cuando los dos campos de título están vacíos.
4. Vacía la caché de bloques de la navegación por facetas si esa opción está activada.

El formulario envía un campo oculto `combfeat_submitted`. Si ese campo falta, el módulo no toca los datos. En PrestaShop 8 y 9 esto depende del cambio Twig de la sección 3.1.

Borrar una combinación en PrestaShop no borra sus filas en este módulo. Las filas dejan de usarse porque la combinación ya no existe. Las características desaparecen al guardar el producto (el formulario solo envía las combinaciones actuales). Las filas de descripción y título de una combinación borrada permanecen hasta que las quite de la base de datos.

## 7. Tienda

Los scripts solo se añaden en la ficha de producto, solo si la petición no es una recarga ajax de todo el controlador, solo si el producto tiene combinaciones y solo si al menos uno de los tres interruptores está activado.

| Interruptor | Script |
| --- | --- |
| Características o descripciones, flujo = Reemplazar | `views/js/combfeat.js` |
| Características o descripciones, flujo = Añadir | `views/js/combfeat-append.js` |
| Meta título | `views/js/combfeat-title.js` |

Cambiar de combinación no hace otra petición. Los datos de todas las combinaciones se imprimen en la página para el **idioma actual**. El script lee la combinación elegida del atributo `data-product` de `#product-details` (`id_product_attribute`) y se vuelve a ejecutar con el evento `updatedProduct`.

`displayProductAdditionalInfo` también imprime un elemento oculto `#product-details-combfeat` con la combinación resuelta para la primera vista (grupos de atributos de la URL, `id_product_attribute` de la petición o la combinación por defecto). Las combinaciones no disponibles siguen el ajuste de stock de PrestaShop y **Mostrar los atributos no disponibles**. El elemento oculto solo se usa cuando `#product-details` no existe. Un tema que conserve `#product-details` debe poner `data-product` en ese elemento. Así está en la plantilla estándar de producto.

El módulo no carga una hoja de estilos en la tienda. Los nuevos `<dt class="name">` y `<dd class="value">` usan las reglas de ficha técnica del tema.

### 7.1 Características y descripciones comparten un script

`combfeat.js` y `combfeat-append.js` actualizan la ficha técnica **y** la descripción en cuanto se cargan. No vuelven a leer los dos interruptores.

- Características activadas y descripciones desactivadas: una descripción guardada antes se sigue aplicando hasta que la vacíe y guarde.
- Descripciones activadas y características desactivadas: las características que sigan guardadas se siguen aplicando. Guardar el producto con el interruptor de características apagado borra esas características guardadas. Véase la sección 4.1.

El script del título es independiente y solo se ejecuta si el interruptor del título está activado.

### 7.2 Ficha técnica

Reemplazar y Añadir están descritos en la sección 4.3. En cada ejecución el módulo reconstruye las filas. El marcado extra que el tema tenía dentro de la ficha técnica (enlaces, clases adicionales en un valor) no se conserva.

### 7.3 Descripción

Si la combinación tiene una descripción en el idioma actual, ese HTML sustituye el contenido del selector de descripción. Si no, lo sustituye la descripción larga del producto. El modo Añadir no añade texto de descripción.

### 7.4 Título

Prioridad para la combinación elegida, en el idioma actual:

1. **Título completo**, cuando no está vacío.
2. Si no, **Añadir al título**, unido con el separador de la sección 4.9.
3. Si no, el modo de título predeterminado de la sección 4.8.

`og:title` recibe el mismo texto cuando existe esa metaetiqueta.

## 8. Navegación por facetas

Con la opción activada, los filtros de categoría leen una vista que une:

- `feature_product` — características asignadas al producto;
- `combfeat` — características activas asignadas a combinaciones, unidas a `feature_value` para obtener el ID de la característica.

Reconstruya el índice de la navegación por facetas o vacíe la caché de PrestaShop si un filtro se queda desactualizado después de resolver el aviso de la página de configuración. Guardar características de combinación e importar un CSV ya vacían `layered_filter_block`.

La ficha de producto en la tienda sigue mostrando las características de producto de PrestaShop hasta que se ejecuta el script de este módulo. El filtro y la ficha técnica son dos fuentes distintas.

## 9. Actualizaciones de MyPresta

El panel bajo los formularios:

| Control | Comportamiento |
| --- | --- |
| **Comprobar ahora** | Contacta con MyPresta y muestra **¡Nueva versión disponible!** o **¡El módulo está actualizado!** |
| **Notificaciones de actualizaciones** | **Activar** muestra un aviso en el back-office cuando hay una versión más reciente: **¡Nueva versión disponible! Consulte http://MyPresta.eu para obtener más información**, con el enlace **Más detalles en el registro de cambios**. **Desactivar** oculta ese aviso. |
| **Página del módulo** | Abre la página del complemento: [Product combination features](https://mypresta.eu/modules/front-office-features/product-combination-features.html) |

Mientras un empleado está en el back-office, el módulo contacta con el servidor de actualizaciones como máximo una vez cada 3 días. La comprobación necesita `allow_url_fopen`. Si no está disponible, se mantiene la versión instalada y no se informa de una más reciente.

## 10. Resolución de problemas

**El bloque de la pestaña Módulos está vacío en PrestaShop 8 o 9.**  
Compruebe que `modules-content.html.twig` contiene `{{ module.content|raw }}` y que la tienda pudo escribir ese archivo. Vuelva a abrir la configuración del módulo para que se reintente el cambio. Después vacíe la caché de Symfony (**Parámetros avanzados > Rendimiento**).

**La ficha técnica no cambia.**  
El producto necesita combinaciones, el interruptor de características debe estar activado o las características ya deben estar guardadas, y la combinación necesita al menos un valor (en el modo Reemplazar, una combinación sin valores restaura las características del producto, y puede parecer que no ha pasado nada). Compruebe el selector en la consola del navegador: `document.querySelectorAll('.data-sheet')` con su selector real. El tema debe actualizar `data-product` en `#product-details` y disparar `updatedProduct`.

**Todo el bloque product-details fue sustituido por una lista corta de características.**  
El selector de la ficha técnica no encontró nada. Póngalo en el `<dl>` real, normalmente `.data-sheet`.

**La descripción no cambia, o la descripción corta fue sustituida por la larga.**  
El selector por defecto `#description` es la descripción larga en Classic. El texto de reserva es siempre la descripción larga. En **Descripción de la clase CSS / ID del objeto** apunte al elemento que debe cambiar.

**Apagué las descripciones y el texto antiguo sigue viéndose.**  
Vacíe los campos, guarde el producto y después apague el interruptor. O apague también las características para que ninguno de esos scripts se cargue. Apagar las características y guardar borra las características de combinación guardadas.

**Apagué las características y desaparecieron al guardar el producto.**  
Así funciona el guardado cuando los campos de características no están en el formulario. Vuelva a activar el interruptor antes de editar si los datos siguen haciendo falta. Vuelva a importar el CSV si tiene el archivo.

**El título de la pestaña del navegador no cambia.**  
Active el interruptor del título. Un título completo vacío y un campo Añadir al título vacío juntos significan que se usa el modo predeterminado. **No cambiar el título de forma predeterminada** deja el título como estaba. El cambio es en el navegador: abra la página, cambie de combinación y lea el título de la pestaña. El código HTML sigue teniendo el meta título del producto.

**Falta una característica en el filtro de categoría.**  
Active **Filter combination features in Faceted Search**, añada la característica a la plantilla de navegación por facetas y lea el aviso de la configuración del módulo. El archivo del adaptador debe poder escribirse. El valor debe estar guardado en el producto o en una combinación.

**Errores de filas CSV.**

| Mensaje | Causa |
| --- | --- |
| The CSV must contain id_product_attribute or combination_reference | La cabecera no identifica una combinación |
| The CSV must contain feature and value, or id_feature_value | La cabecera no identifica un valor de característica |
| Combination was not found | El ID o la referencia no existe |
| Product ID does not match this combination | `id_product` está relleno y apunta a otro producto |
| Product reference does not match this combination | `product_reference` no coincide |
| Combination reference does not match this combination ID | El ID y la referencia están rellenos y se contradicen |
| Combination reference matches more than one combination | Añada `id_product` o `id_product_attribute` |
| Feature name or value matches more than one | Dos fichas del catálogo comparten esa etiqueta. Use `id_feature_value` |
| Feature and value are required when id_feature_value is empty | La celda del nombre o del valor está vacía |
| The CSV file is larger than 8 MB | Divida el archivo |

**Varios idiomas.**  
Las descripciones y los dos campos de título se guardan por idioma. Los valores de característica usan la traducción de PrestaShop de la característica en el idioma del visitante. La asignación en sí no es por idioma.

## 11. Referencia técnica

### 11.1 Hooks

| Hook | Cuándo | Qué hace |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Back-office, controladores `AdminProducts` y `AdminModules` | Carga `views/css/combfeat.css`, `views/js/acplt.js`, `views/js/admin-combfeat.js` y el autocompletado de jQuery. También asegura la configuración y la integración con Faceted Search |
| `displayAdminProductsExtra` | Edición del producto, pestaña Módulos | Muestra `views/templates/admin/combfeat.tpl` |
| `actionProductUpdate` | Guardado del producto | Escribe características, descripciones y títulos cuando está presente `combfeat_submitted` |
| `displayHeader` | Ficha de producto, sin ajax | Imprime los datos de combinación del idioma actual y añade los scripts de la tienda |
| `displayProductAdditionalInfo` | Ficha de producto | Muestra el archivo oculto `views/templates/hook/product-details.tpl` |

Registrados en la instalación: `actionProductUpdate`, `displayProductAdditionalInfo`, `displayAdminProductsExtra`, `actionAdminControllerSetMedia`, `displayHeader`.

La página de configuración también responde a la búsqueda de características. Una petición con `ajax=1` y `q` devuelve coincidencias JSON y termina. El editor de producto llama a esa URL a través de `AdminModules` con `configure=combfeat`.

### 11.2 Base de datos

El prefijo es el de la tienda. La desinstalación **no** elimina estas tablas, así que el contenido de las combinaciones sobrevive a la desinstalación y sigue ahí después de una instalación posterior (`CREATE TABLE IF NOT EXISTS`).

`combfeat` — una fila por valor de característica en una combinación:

| Columna | Papel |
| --- | --- |
| `id_combfeat` | Clave primaria |
| `id_product` | Producto |
| `id_product_attribute` | Combinación |
| `id_feature_value` | Valor de característica del catálogo |
| `active` | `1` cuando la fila se usa. La tienda y la vista de Faceted Search leen las filas activas |

`combfeat_details` — descripción, una fila por combinación e idioma:

| Columna | Papel |
| --- | --- |
| `id_combfeat` | Clave primaria |
| `id_product`, `id_product_attribute`, `id_lang` | Destino |
| `details` | HTML |
| `active` | Guardado como `1` |

`combfeat_title` — títulos, una fila por combinación e idioma:

| Columna | Papel |
| --- | --- |
| `id_combfeat` | Clave primaria |
| `id_product`, `id_product_attribute`, `id_lang` | Destino |
| `title_full` | Hasta 512 caracteres. Sustituye el título del documento |
| `title_append` | Hasta 512 caracteres. Se añade después del título original |
| `active` | Guardado como `1` |

`{prefix}combfeat_feature_product` — vista SQL, no una tabla de contenido que se edite. Unión de `feature_product` y de las filas activas de `combfeat`. El valor de configuración `COMBFEAT_FEATURE_VIEW` guarda la versión de la vista (`1`).

Otras claves de configuración: `update_combfeat` y `updatev_combfeat` (comprobación de actualizaciones), `mypresta_updates` (interruptor de notificaciones).

### 11.3 Clases PHP

| Archivo | Clase | Papel |
| --- | --- | --- |
| `combfeat.php` | `combfeat` | Clase del módulo: instalación, configuración, hooks, datos del editor de producto, datos de la tienda |
| `combfeat.php` | `combfeatUpdate` | Comparación de versión y petición al servidor de actualizaciones |
| `classes/CombfeatImporter.php` | `CombfeatImporter` | Análisis del CSV, resolución de combinación y característica, descarga del ejemplo |
| `classes/CombfeatFacetedSearch.php` | `CombfeatFacetedSearch` | Vista, parche del adaptador, restauración, vaciado de la caché de filtros |
| `models/cfeat.php` | `cfeat` | Filas de `combfeat`. `getAllByProductId`, `getFeaturesStaticByIdProduct`, `assign`, `insertDatas`, borrados |
| `models/cfeatdesc.php` | `cfeatdesc` | Filas de `combfeat_details` |
| `models/cfeattitle.php` | `cfeattitle` | Filas de `combfeat_title`. `saveTitleRow` borra la fila cuando los dos títulos están vacíos |

No hay directorio `controllers/`.

### 11.4 Recursos y plantillas

| Archivo | Dónde | Papel |
| --- | --- | --- |
| `views/js/acplt.js` | Back-office | Autocompletado de la búsqueda de características |
| `views/js/admin-combfeat.js` | Back-office | Acordeón, filtro, pestañas, banderas de idioma, fichas, refresco de TinyMCE, copia del contenido del editor antes de guardar el producto |
| `views/css/combfeat.css` | Solo back-office | Maquetación de **Contenido de la combinación** |
| `views/js/combfeat.js` | Tienda, modo Reemplazar | Reconstruye la ficha técnica y la descripción |
| `views/js/combfeat-append.js` | Tienda, modo Añadir | Igual, con las características del producto delante de las de la combinación |
| `views/js/combfeat-title.js` | Tienda | `document.title` y `og:title` |
| `views/templates/admin/combfeat.tpl` | Pestaña Módulos del producto | El editor |
| `views/templates/hook/product-details.tpl` | Ficha de producto | `#product-details-combfeat` oculto, con `data-product` |
| `import/combfeat-features-sample.csv` | Descarga desde la configuración | Ejemplo de importación |

### 11.5 Instalación y desinstalación

La instalación crea las tres tablas, escribe la configuración por defecto, registra los cinco hooks, aplica el cambio Twig y aplica la integración con Faceted Search.

`disable` restaura el adaptador de la navegación por facetas. `enable` escribe las claves de configuración que falten y vuelve a aplicar la integración cuando el interruptor de Faceted Search está activado.

La desinstalación restaura el adaptador, elimina la vista cuando ya no se referencia y desinstala el módulo. Las filas de combinación de las tres tablas permanecen en la base de datos.

## 12. Soporte

Registro de cambios y actualizaciones: [Product combination features en MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-combination-features.html).

Pedidos y soporte: [cuenta de cliente de MyPresta.eu](https://mypresta.eu/my-account/orders/). Correo: support@mypresta.eu.