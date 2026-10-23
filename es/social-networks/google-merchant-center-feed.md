---
title: "Google Merchant Center Feed - manual del vendedor"
sidebar:
  label: "Google Merchant Center Feed - manual del vendedor"
description: "Configuración del archivo de catálogo, de los archivos guardados y de la dirección del catálogo en una tienda que ya tiene el módulo."
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Google merchant center feed en MyPresta.eu](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/google-merchant-center-feed/)
>
> ---


El nombre técnico del módulo es `gmfeed`, versión 2.4.3. En la lista de módulos se muestra **Google Merchant Center Feed**. Ese nombre está escrito en el archivo del módulo y no sale de `translations/es.php`.

## 1. Dónde están las pantallas

Hay dos pantallas.

Módulos, después Gestor de módulos, después **Google Merchant Center Feed**, después Configurar. Esa página tiene un campo, **Mostrar árbol de categorías**.

Catálogo, después **Google Merchant Feed**. Es el controlador `AdminExportProductsFeedGoogle`. El título es **Feeds de Google Merchant Center**. Las pestañas son **Panel de control**, **Feeds**, **Actualizaciones** y **Create / Edit feed**. La última queda desactivada hasta abrir **Crear nuevo feed** o un feed existente. **Create / Edit feed** no tiene entrada en `translations/es.php`, la pantalla muestra el texto inglés de origen.

No hay pantalla de importación ni bloque en la ficha del producto. El escaparate no dibuja un recuadro. El efecto público es la dirección de catálogo de un feed guardado.

## 2. Qué escribe la instalación

La instalación ejecuta la instalación padre, registra `actionAdminControllerSetMedia`, crea una pestaña bajo Catálogo y crea las tablas del punto 8.

La clase de la pestaña es `AdminExportProductsFeedGoogle`. La etiqueta pasada en la instalación es **Google Merchant Feed**. La misma etiqueta se escribe para cada idioma de la tienda que exista en ese momento.

`actionAdminControllerSetMedia` carga los plugins fancybox y autocomplete solo cuando el controlador es `AdminExportProductsFeedGoogle`.

La clase no tiene `enable()` ni `disable()`.

## 3. Ajustes del módulo

![Ajustes del módulo](https://mypresta.eu/docs/images/docs/gmfeed-settings.webp)

La pantalla está en inglés. En este manual esa vista se llama **Ajustes del módulo**.

La leyenda es **Ajustes del módulo**. El botón es **Save**. El único campo es **Mostrar árbol de categorías** (`pf_tree`). **No** es 0. **Sí** es 1. Si falta la clave, `(int)Configuration::get('pf_tree')` vale 0 y el selector muestra **No**. **Save** no tiene entrada para esta plantilla en `translations/es.php`, el botón muestra el texto inglés de origen.

**Save** envía `submitgmfeedSettings` y escribe `pf_tree`. El texto posterior es **Ajustes guardados correctamente**.

**Sí** hace que la lista de emparejamiento de categorías del formulario muestre las categorías padre. La descripción enlaza `https://i.imgur.com/enzXRaJ.png`. La misma descripción enlaza **Catálogo > Google Merchant Feed**.

Esta página no genera el archivo de catálogo.

## 4. Página del catálogo

![Panel de control](https://mypresta.eu/docs/images/docs/gmfeed-dashboard.webp)

La pantalla está en inglés. En este manual esa pestaña se llama **Panel de control**.

![Feeds](https://mypresta.eu/docs/images/docs/gmfeed-feeds.webp)

La pantalla está en inglés. En este manual esa pestaña se llama **Feeds**.

Abra **Catálogo > Google Merchant Feed**.

**Panel de control** muestra las cifras de `gms` y `gms_log`. Si ninguna dirección se ha llamado, la página muestra el texto inglés **No cron or URL generations yet. Save a feed, then call its catalog URL from a scheduler.**

**Feeds** lista las filas de `gms`, el `id_gms` más alto primero. **Crear nuevo feed** abre el formulario. Duplicar copia la cadena de consulta guardada, quita `export_id_gms`, `id_gms` y `gmfeed_write_key` y añade ` (copy)` al nombre. Un nombre vacío parte de **Untitled feed**. El texto posterior es el inglés **Feed duplicated. Review the copy and save if you need a different filename or URL.** Quitar borra esa fila de `gms`. El texto es **Feed removed.** El archivo guardado en disco no se borra con esa acción.

![Actualizaciones](https://mypresta.eu/docs/images/docs/gmfeed-updates.webp)

La pantalla está en inglés. En este manual esa pestaña se llama **Actualizaciones**.

**Actualizaciones** es el formulario de `lib/updateChecker.php`. **Check now** envía `submit_settings_updates_now`. **Save** envía `submit_settings_updates` y escribe `mypresta_updates`. El constructor pregunta al servidor remoto cuando `mypresta_updates` no es 0 y `update_gmfeed` tiene más de 172800 segundos. El valor de licencia enviado si falta `mkey` es `nokey`. Aparece un aviso cuando `updatev_gmfeed` es mayor que 2.4.3 y la petición no es ajax.

## 5. Formulario del feed

![Crear nuevo feed](https://mypresta.eu/docs/images/docs/gmfeed-form.webp)

La pantalla está en inglés. En este manual esa vista se llama **Crear nuevo feed**. El recorte muestra la parte alta del formulario. El resto de los campos sigue debajo.

**Create feed** y **Edit feed** usan el mismo formulario. El nombre del feed es obligatorio. **Active** **Yes** / **No** se guarda en `gms.active`. Un feed nuevo está activo. **Shop** guarda `gms.id_shop`. El resto de campos se guarda en `gms.conf` como cadena de consulta.

Una clave ausente en un formulario nuevo toma el valor de la tabla. Al editar, una clave ausente toma ese mismo valor y no lee la configuración compartida `gm_`.

| Clave | Valor por defecto de un formulario nuevo | Qué hace el código con ella |
|---|---|---|
| `export_file_format` | `csv` | `csv` o `xml`. Cualquier otra extensión la devuelve `sanitizeExportExtension` a `csv`. |
| `export_type` | `product` | `sanitizeExportType` conserva solo `products` y `combinations`. El `product` guardado se trata como `products`. |
| `export_save_file` | `0` | `0` envía el catálogo en la respuesta. `1` escribe un archivo en `/modules/gmfeed/`. |
| `export_filename` | vacío | Solo se usa al guardar en archivo. Vacío pasa a ser el tipo de exportación. Se quitan los caracteres que no sean letras, dígitos, `_` o `-`. |
| `export_identification` | `id_product` | Id de producto escrito como id del catálogo. |
| `export_delimiter` | barra vertical | Separador de las columnas CSV. |
| `export_enclosure` | `0` | Valor de cierre pasado al escritor CSV. |
| `export_language` | `PS_LANG_DEFAULT` | Idioma de nombres y descripciones. |
| `export_currency` | `PS_CURRENCY_DEFAULT` | Moneda de los precios. |
| `export_tax` | `price_tin` | Qué columna de precio se rellena. |
| `export_specific` | `1` | Si la moneda por defecto de la tienda difiere de la del contexto, un valor distinto de cero hace que el paso de precio use precios específicos. |
| `export_category` | `all` | Categorías incluidas en el catálogo. |
| `export_manufacturers` | `all` | Fabricantes incluidos. |
| `export_manufacturers_default` | `Default` | Texto de marca cuando el producto no tiene fabricante. |
| `export_suppliers` | `all` | Proveedores incluidos. |
| `export_gtin` | `upc` | Qué código de producto se escribe como GTIN. |
| `export_img` | `1` | Tipo de imagen pasado a `getImageLink`. La lista muestra los nombres de los tipos de imagen. |
| `export_what_pictures` | `0` | `0` es el texto inglés **Export cover only** y quita la columna de imágenes adicionales. `1` es **Export all pictures**. |
| `export_active` | false | Se pasa a `Product::getProducts` como indicador de solo activos. `0` es **Export all products.** `1` es **Export only active products**. |
| `export_instock` | false | `1` omite una fila cuando la cantidad es 0 o menor. `0` es **Export all products.** `1` es **Export only in-stock products**. |
| `export_igid` | `0` | `0` quita `item_group_id`. |
| `export_gender` | `0` | `0` quita la columna de género. |
| `export_age_group` | `0` | `0` quita la columna de grupo de edad. |
| `export_size` | `0` | `0` quita la columna de talla. |
| `export_color` | `0` | `0` quita la columna de color. |
| `export_shipping_info` | `0` | `0` es **Do not include**. `1` es **Include (shipping price calculated for each item separately)**. `2` es **Set shipping price manually**. |
| `export_product_weight` | `0` | El peso sigue apagado hasta que se cambia este valor. |
| `export_product_type` | `0` | El tipo de producto sigue apagado hasta que se cambia este valor. |
| `export_removehtml` | `0` | Un valor distinto de `0` quita el HTML de la descripción. |
| `export_nophoto_exclude` | `0` | `1` descarta un producto sin foto. |
| `export_adult` | `0` | Adult sigue apagado hasta que se cambia este valor. |
| `export_storecode` | `0` | `0` quita la columna de código de tienda. |
| `export_country_prices` | `PS_COUNTRY_DEFAULT` | País usado para el precio. |
| `export_group_prices` | `PS_UNIDENTIFIED_GROUP` | Grupo de clientes usado para el precio. |
| `remember_settings` | true | Si el valor enviado es `1`, el mismo guardado escribe también `gm_{clave}` en Configuration. Se omiten la clave de escritura, la tienda, el id del feed y la marca de activo. |
| `feed_active` | activo en un feed nuevo | `gms.active`. `0` hace que la dirección devuelva HTTP 503 y el texto `Feed is disabled`. |

**Save to file** describe el directorio `modules/gmfeed/` e indica que escribir el archivo desde la dirección exige la clave mostrada en este formulario. La clave es `gmfeed_write_key`, un HMAC de `gmfeed.write.` más el id de tienda, con `_COOKIE_KEY_`. Un empleado conectado escribe el archivo sin esa clave. Cualquier otra persona recibe `Access denied`.

El texto tras guardar es el inglés **Feed saved. Its catalog URL is ready to use.**

## 6. Dirección del catálogo y archivo

La dirección del catálogo es el controlador frontal `feed` más `?feed=` y el id de `gms`. `gms::getFeedUrl` añade `gmfeed_write_key` cuando construye el enlace para el back office.

Abrir esa dirección carga la cadena guardada y sustituye los valores `export_` y `gmfeed_` de la petición, salvo la clave de escritura y `debug_feed`. Un feed ausente, o un `conf` de 20 caracteres o menos, termina con `feed does not exists`. Un feed cuyo `id_shop` está definido y no es la tienda actual termina con `Feed is not available in this store`.

`debug_feed` imprime los parámetros guardados y no escribe el archivo.

El nombre de archivo es el `export_filename` saneado más `.csv`, `.xml` o `.txt`. La ruta tiene que quedar dentro de `/modules/gmfeed/`. `.htaccess` de ese directorio niega la ejecución directa de archivos PHP. `index.php` sigue permitido. El catálogo lo sirve el controlador frontal, no la apertura de los archivos PHP.

Cada ejecución inserta `gms_log`: hora, duración, número de ítems, estado, si se guardó un archivo, nombre de archivo, formato y origen `url`.

## 7. Categorías de Google

El formulario lista los archivos de taxonomía de `/modules/gmfeed/google/`. Un idioma de la tienda figura como presente cuando existe `google/{language_code}.txt`. Este paquete contiene `google/en-us.txt`. La primera línea de ese archivo es `# Google_Product_Taxonomy_Version: 2015-02-19`.

Emparejar una categoría de la tienda escribe `pixelgoogle`: `id_google`, `id_category`, `id_lang`, `value`. **Mostrar árbol de categorías** solo cambia cómo se dibuja esa lista.

## 8. Tablas

La instalación crea tres tablas cuando faltan. El prefijo de la tienda va delante de cada nombre.

| Tabla | Qué escribe la sentencia CREATE |
|---|---|
| `pixelgoogle` | `id_pixelgoogle` auto increment, clave primaria, `id_google`, `id_category`, `id_lang`, `value` varchar 254. Juego de caracteres `utf8`. |
| `gms` | `id_gms` auto increment, `name`, `id_shop` por defecto 0, `conf` text, `active` por defecto 1. Claves `idtoskey` e `id_shop`. La sentencia CREATE no tiene clave primaria. |
| `gms_log` | `id_gms_log` auto increment, clave primaria, `id_gms`, `date_add`, `duration_ms`, `items`, `status` por defecto `ok`, `save_file`, `file_name`, `format`, `source` por defecto `url`. |

Abrir la página del catálogo ejecuta `gms::ensureSchema()`. Eso añade `gms.active` y `gms.id_shop` si faltan, crea `gms_log` si falta la tabla y rellena `id_shop` 0 con `PS_SHOP_DEFAULT`.

Configuración compartida que no es una columna: `pf_tree`, `gm_{campo}` cuando el formulario lo escribe fuera de un feed, `mypresta_updates`, `update_gmfeed`, `updatev_gmfeed`.

Archivos de la página del catálogo: `views/css/admin-app.css`, `views/js/admin-app.js`, fancybox, autocomplete. La configuración del módulo carga fancybox. El script de búsqueda de id sale de `lib/searchTool/`.

## 9. Desinstalación

`uninstall()` borra la pestaña de Catálogo `AdminExportProductsFeedGoogle` y después ejecuta la desinstalación padre. La padre quita el módulo y el registro del hook.

El método no borra `pixelgoogle`, `gms` ni `gms_log`. No borra `pf_tree`, `mypresta_updates`, `update_gmfeed`, `updatev_gmfeed` ni las claves `gm_`. No borra los archivos escritos en `/modules/gmfeed/`. Una instalación posterior usa `CREATE TABLE IF NOT EXISTS`, así que las filas que quedan en las tablas permanecen.

## 10. Soporte

Página del módulo: [Google Merchant Center Feed](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html).
