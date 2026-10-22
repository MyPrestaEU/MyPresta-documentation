---
title: "HTML Box Pro - manual del vendedor"
sidebar:
  label: "HTML Box Pro - manual del vendedor"
description: "Configuración de las cajas HTML, las posiciones de hook y las reglas de visibilidad para una tienda que ya tiene el módulo."
---
> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo HTML Box Pro en MyPresta.eu](https://mypresta.eu/modules/front-office-features/html-box-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/html-box-pro/)
>
> ---



El nombre técnico del módulo es `htmlboxpro`, versión 4.0.5. En este idioma la lista de módulos muestra **HTML Box Pro**.

## 1. Dónde están las pantallas

Módulos, después Gestor de módulos, después el módulo **HTML Box Pro**, después Configurar. La página es la configuración del módulo (`configure=htmlboxpro`).

La barra bajo el título tiene dos botones: **Configuración** y **Cajas**. **Configuración** escribe `hbp_lasttab` = 1. **Cajas** escribe `hbp_lasttab` = 2. Si falta la clave, abrir la página escribe 1, así que la primera vista es **Configuración**.

En la misma barra, **Soporte** abre `https://mypresta.eu/contact.html` en una pestaña nueva. **Actualizaciones** abre la página del módulo en MyPresta en una pestaña nueva. La comprobación de versión es el panel al final de **Configuración**, no ese botón.

No hay importación ni bloque en la ficha de producto. Una caja aparece en la tienda solo cuando su hook está activado, el bloque está activo y pasa los filtros de más abajo.

Si `firsttime_hbp` no es 1, la página muestra un aviso con `https://www.youtube.com/watch?v=uxzhSr5TrF4`. Cerrarlo envía `firsttime_hbp` = 1 y el aviso no vuelve.

## 2. Qué escribe la instalación

La instalación ejecuta la instalación padre, crea las tablas, escribe `hbp_notinyjs` = 1 y registra `actionAdminControllerSetMedia` y cada hook de la lista de más abajo.

No enciende esos hooks. Un hook imprime cajas solo cuando la clave `hbp_` más el nombre del hook vale 1. Hasta que se guarda la casilla en **Cajas**, la clave no existe y el hook no devuelve nada.

Abrir la configuración siempre comprueba las columnas y añade las que falten en `hbp_block`. Las filas existentes se quedan.

## 3. Configuración

![Pantalla en inglés. Settings es Configuración. Global module settings es Configuración global del módulo. Updates notifications es Notificaciones de actualizaciones.](https://mypresta.eu/docs/images/docs/htmlboxpro-settings.webp)

El título es **Configuración global del módulo**. El botón es **Guardar**. Cada interruptor es **Activado** (1) o **Desactivado** (0).

| Etiqueta | Clave | Tras instalar |
| --- | --- | --- |
| Usar el editor de texto enriquecido interno del módulo | `hbp_tiny` | falta la clave; el formulario muestra **Desactivado** |
| Evitar eliminar URL de imágenes | `hbp_forceurls` | falta la clave; el formulario muestra **Desactivado** |
| No cargar (duplicar) cajas con las consultas ajax de la página del producto | `hbp_noajax` | falta la clave; el formulario muestra **Desactivado** |
| No cargar las bibliotecas de tinyMCE | `hbp_notinyjs` | 1, o sea **Activado** |

**Guardar** envía los nombres de los cuatro interruptores. El módulo escribe cada valor enviado. `hbp_tiny` = 1 carga en esta página `views/js/tinymce16.inc.js`. El mismo interruptor junto con `hbp_forceurls` = 1 carga en su lugar `views/js/tinymce16-force-urls.inc.js`. `hbp_tiny` = 0 carga el archivo de la tienda `js/admin/tinymce.inc.js` y llama a `tinySetup()`. `hbp_notinyjs` = 1 omite `js/tiny_mce/tinymce.min.js`. La página sigue incluyendo `js/tiny_mce/tiny_mce.js`, `views/js/script.js` y `views/css/styles.css`.

`hbp_noajax` = 1 hace que `generateHookContents` no devuelva nada cuando la petición tiene `ajax` = 1 y `action` = refresh. El resto de peticiones sigue imprimiendo las cajas.

Bajo los interruptores la página añade el panel de actualización de `checkforupdates`. La lista **Notificaciones de actualizaciones** tiene `-- select --`, **Activar** (1) y **Desactivar** (0). **Comprobar ahora** es el botón `submit_settings_updates_now`. **Guardar** de ese panel es `submit_settings_updates` y escribe solo `mypresta_updates`.

El constructor pregunta al servidor remoto cuando `mypresta_updates` no es 0, o cuando falta la clave (`Configuration::get` es false), y `update_htmlboxpro` tiene más de 259200 segundos. La petición sale si `allow_url_fopen` está activo. El valor de licencia de este paquete es `nlc`. Hay un aviso cuando la versión devuelta es mayor que 4.0.5 y la petición no es ajax. **Desactivar** (0) entra igual en la rama con tiempo; la condición del aviso es la de esa rama.

## 4. Cajas

![Pantalla en inglés. Boxes es Cajas. Default positions es Posiciones predeterminadas. Search hooks no está en translations/es.php, la pantalla muestra esa fuente en inglés.](https://mypresta.eu/docs/images/docs/htmlboxpro-boxes.webp)

**Cajas** son dos columnas. A la izquierda, **Posiciones predeterminadas**. Encima de las filas hay un campo de búsqueda. El marcador **Search hooks** no está en `translations/es.php`, la pantalla muestra esa fuente en inglés. **Posiciones personalizadas** es el panel bajo esa lista, en la misma columna izquierda. La columna derecha son los bloques del hook elegido o el estado vacío. La columna principal empieza con el título **No box selected** y la frase **Seleccione bloques de la lista disponible en el lado izquierdo. O cree un nuevo bloque.** **No box selected** y **No boxes in this position yet** (hook desplegado sin bloques) no están en `translations/es.php`, la pantalla muestra esa fuente en inglés.

Cada hook predeterminado es una fila: casilla, nombre del hook y el botón de caja nueva. El nombre enlaza a `https://mypresta.eu/prestashop/hook/` más el nombre en minúsculas. La casilla envía `togglehook`. Marcada escribe `hbp_{hook}` = 1 y llama otra vez a `registerHook`. Desmarcada no envía `status`, así que la clave pasa a 0. Apagar el hook no lo desregistra. El texto de éxito es **Visibilidad del hook cambiada correctamente**.

La fila del bloque muestra el nombre interno, o **sin nombre de bloque interno** si el nombre está vacío. Los botones son **Editar este bloque**, **Duplicar este bloque** y **Eliminar este bloque**. El éxito del interruptor de actividad es **Visibilidad del bloque cambiada correctamente**. Arrastrar una fila envía `action=updateSlidesPosition` y `elements{hook}[]` y escribe `hbp_block.position`. La pestaña carga jQuery UI sortable. Un hook vacío muestra **no hay bloques definidos**. En multitienda la fila puede mostrar **para esta tienda**.

**Duplicar este bloque** copia el bloque y antepone `[duplicar] ` al nombre. El texto de éxito es **Bloque duplicado correctamente**. **Eliminar este bloque** borra la fila por el modelo de objeto. El texto de éxito es **Bloque eliminado correctamente**. El interruptor de la lista ejecuta `smart_clean` en el cuerpo de cada idioma, guarda el bloque y pone `active` con SQL.

## 5. Crear y editar un bloque

![Pantalla en inglés. Create new block es Crear nuevo bloque. Contents es Contenidos. Smarty templates manager es Administrador de plantillas Smarty. Placement no tiene traducción.](https://mypresta.eu/docs/images/docs/htmlboxpro-block-form.webp)

Añadir una caja abre **Crear nuevo bloque**. Editar abre **Editar bloque existente**. El botón es **Guardar**. Alta envía `submitAddNewHbox`. Edición envía `submitEditHbox`. El texto de alta es **Bloque añadido correctamente**. El texto de guardado es **Bloque guardado correctamente**.

El cuerpo de cada idioma de la tienda va a `hbp_block_lang.body`. Antes de guardar el módulo ejecuta `addslashes(smart_clean(...))`. `smart_clean` reduce un carácter de espacio repetido a uno y recorta los extremos. El último reemplazo de `prepare()` reescribe `\'`, `\\` y `\"`. Las líneas anteriores de `prepare()` parten de la cadena original y no cambian el valor devuelto. La función no quita etiquetas HTML. La misma limpieza se repite cuando el interruptor de la lista cambia la actividad.

Las etiquetas de los campos están en `translations/es.php`. El título de productos es **Productos**. **Placement**, **Pages**, **Cart**, **Customers** y **Schedule** no tienen entrada en ese archivo, la pantalla muestra esa fuente en inglés.

| Sección | Qué hacen los campos |
| --- | --- |
| Contenido | **Contenidos** (`hbp_body`, un valor por idioma) y **Nombre** (`hbp_name`, 150 caracteres). El interruptor del editor en `views/js/script.js` llama a `tinyMCE.execCommand('mceToggleEditor')` para el campo de ese idioma. Bajo el editor está **Administrador de plantillas Smarty**. El botón abre el gestor de `lib/smartyTemplatesManager/`. |
| Placement | Tienda, posición (`hbp_hook`), **Active** (`hbp_active`, 0 en la tabla hasta que el guardado pone 1), solo páginas SSL (`hbp_bssl`), **Active on mobile devices**, **Active on tablet devices**, **Active on PC devices**. Un valor de dispositivo ausente se guarda como 1. Las etiquetas en español están en `translations/es.php`. |
| Pages | Inicio, ofertas, confirmación de pedido, categoría, categoría y subcategorías, categorías excluidas, categoría CMS, página CMS, página de fabricante, URL exacta y palabras de búsqueda. Los id van separados por comas. El buscador junto a un id es la herramienta de búsqueda del módulo (`ajax=1` y `searchType`). |
| Products | Incluir o excluir id de productos, todas las fichas, precio específico, sin stock, disponible para comprar, no disponible, en stock, valor mínimo y máximo, categoría del producto, fabricante, proveedor y valor de característica. |
| Cart | La caja solo si el carrito contiene, o no contiene, los id de categoría o de producto indicados. |
| Customers | **All users** (0), **Logged only** (1), **Unlogged only** (2) en `hbp_logged`. Los textos en español de esas tres opciones están en `translations/es.php`. **Show for all groups** y las casillas de grupo van a `hbp_cgroup` como lista separada por comas. **Hide for (users' groups)** es `hbp_hcgroup`. La geolocalización y el país de la dirección de entrega están en esta sección. |
| Schedule | Moneda, fecha desde / hasta, días de la semana y hora desde / hasta. |

Los días de la semana llaman a la traducción con el dominio `forms` (`Sunday` a `Saturday`). Los archivos `translations/*.php` guardan esas palabras en el dominio `htmlboxpro`, no en `forms`. La pantalla muestra la fuente en inglés: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday.

El texto de geolocalización apunta a `https://mypresta.eu/prestashop-17/geolite2-city-geolocation-download.html` y al directorio `/app/Resources/geoip/`. El mismo texto dice que la geolocalización no funciona en localhost. Los países elegidos van a `selected_geoip`, separados por punto y coma. Los países de entrega van a `delivery_address_selected`, separados por punto y coma. Es un interruptor distinto de la geolocalización.

## 6. Cuándo la tienda oculta un bloque

`generateHookContents` carga bloques con `active` = 1 para el idioma y el hook actuales, ordenados por `position`. Si la multitienda está activa, `shop` tiene que ser el id de la tienda actual o 0. La plantilla `html.tpl` oculta el cuerpo cuando falla alguna regla de abajo. Un interruptor en **Desactivado** no aplica esa regla.

| Interruptor activo | El cuerpo se oculta cuando |
| --- | --- |
| Solo inicio | el controlador no es `index` |
| Rango de fechas | hoy es anterior a la fecha desde o posterior a la fecha hasta (`Y-m-d`) |
| Palabras de búsqueda | la búsqueda no es una de las palabras separadas por comas |
| Solo páginas SSL | `$_SERVER['HTTPS']` no es `on` |
| Solo conectados | el cliente no está conectado |
| Solo no conectados | el cliente está conectado |
| Solo fichas de producto elegidas | el id de producto no está en la lista. Un primer elemento vacío deja el bloque si hay id de producto |
| Sin stock | el stock que usa la plantilla es mayor que 0 |
| En stock | ese stock no es mayor que 0 |
| No se puede comprar / se puede comprar | el valor `oos` no coincide con la regla deny o allow de `html.tpl` |
| Precio específico / sin precio específico | `hook_params.product` no tiene un precio específico que coincida |
| Categorías elegidas | el controlador no es el de categoría o el id no está elegido |
| Categorías y subcategorías | la categoría no está elegida y no es hija según `htmlboxpro::checkIfChildren` |
| Categoría CMS, página CMS, página de fabricante | el id actual no está en la lista o el controlador es otra página |
| URL elegida | `htmlboxpro::currentPageURL()` no está en la lista guardada. La comparación quita `rand=` |
| Producto en categoría | las categorías del producto no cortan la lista |
| Característica | el producto no tiene el valor de característica elegido |
| Confirmación de pedido | el controlador no es `orderconfirmation` |
| Fabricante o proveedor del producto | el fabricante o el proveedor no está elegido |
| Carrito, categoría o producto, contiene o no contiene | el carrito no coincide con la lista. El PHP de `get_blocks` quita el bloque antes de la plantilla en esos cuatro filtros |
| Ocultar para el grupo | el grupo del cliente coincide con `hbp_hcgroup`. Los grupos 1 y 2 se comparan con el grupo por defecto. Otro grupo oculta el bloque si está entre los grupos del cliente |
| Dispositivo | `Context::getDevice()` es 1 y PC está apagado; 2 y la tableta está apagada; 4 y el móvil está apagado |
| Valor mínimo / máximo | el precio convertido queda fuera del importe o el hook no tiene producto |
| Días de la semana | `hbp_daytype_on` es 1 y el `%w` de hoy no está en la lista |
| Moneda | `hbp_currency_on` es 1 y el id de moneda no es `hbp_currency` |
| Dirección de entrega | el país de entrega no está en `delivery_address_selected` |
| Geolocalización | `hbp_geoip` es 1 y el país resuelto no está en `selected_geoip` |
| Productos excluidos, todas las fichas, categorías excluidas | el producto o la categoría actual está excluido |

El filtro de hora corre en PHP, antes de la plantilla. Si `hbp_tim` es 1, `timfrom` y `timto` se comparan con `date("H:i:s")` después de quitar los dos puntos. `timto` pasa por `ltrim` con la máscara de caracteres `0`, así que se quitan los ceros de la izquierda de ese límite. Un bloque fuera de la ventana sale de la lista.

## 7. Marcas en el cuerpo de la caja

El reemplazo corre cuando la petición tiene `controller` y no es `AdminModules`. Una marca que no se llena pasa a cadena vacía al final. La excepción es `{current_url}`.

| Marca | Se llena cuando |
| --- | --- |
| `{currency_iso}` | hay una moneda; el valor es el código ISO |
| `{id_lang}` | siempre en esa rama; el valor es el código ISO del idioma, no el id numérico |
| `{id_customer}`, `{email_customer}`, `{customer_firstname}`, `{customer_lastname}` | el cliente está conectado |
| `{id_product}`, `{id_product_attribute}`, `{product_name}`, `{product_ean13}`, `{product_isbn}`, `{manufacturer_name}` | el controlador es `product` o el hook recibe `product` |
| `{product_price_tax_incl}`, `{product_price_tax_excl}` | ficha de producto; importe con el helper de precio del módulo |
| `{product_price_tax_incl_no_currency}`, `{product_price_tax_excl_no_currency}` | los mismos importes sin el signo de moneda |
| `{id_category}`, `{name_category}`, `{path_array_category}` | la petición trae un id de categoría |
| `{cart_products_id}`, `{cart_total}`, `{cart_total_with_currency}` | hay un carrito |
| `{order_id}`, `{order_customer_email}`, `{order_currency_iso_code}`, `{order_total_paid}`, `{order_total_paid_tax_excl}`, `{order_total_paid_tax_incl}`, `{order_total_products_tax_included}`, `{order_total_products_tax_excluded}`, `{order_products_id}`, `{order_products_id_google}`, `{order_delivery_date}`, `{order_delivery_country}` | la rama de confirmación de pedido tiene un id de pedido |
| `{current_url}` | cada petición, después de la rama de arriba. Esquema, host y URI |
| `{HOOK:HookName}` | `Hook::exec` de ese nombre, salvo que el nombre sea el hook que está pintando esta caja; entonces la marca queda vacía |
| `{HOOK:HookName:moduleName}` | `Hook::exec` limitado al id de ese módulo |
| `{smartyTemplate:name}` | la plantilla de `loadSmartyTemplateFromManager` |

`{shop_name}` recibe el nombre de la tienda y el pase de limpieza sustituye después `{shop_name}` por una cadena vacía. La marca no queda como nombre de la tienda. `{id_product_attribute}` está vacío cuando el id de atributo es 0.

## 8. Posiciones personalizadas

![Pantalla en inglés. Custom positions es Posiciones personalizadas. Add support of new hook es Añadir soporte para nuevo hook. Hook name es Nombre del hook. Add new hook es Añadir nuevo hook. regenerate now! es ¡regenerar ahora!](https://mypresta.eu/docs/images/docs/htmlboxpro-custom-hooks.webp)

**Posiciones personalizadas** lista filas de `hbp_customhook`. El título sobre el campo es **Añadir soporte para nuevo hook**. **Añadir nuevo hook** lee **Nombre del hook**. El nombre guardado conserva solo letras y dígitos (`preg_replace("/[^\da-z]/i", '')`). Si la tienda no tiene un hook con ese nombre, el módulo crea una fila `Hook` con `live_edit` 1, `position` 1, el título igual al nombre y la descripción `Custom hook created with usage of HTML BOX PRO module`. Inserta `hbp_customhook` si falta la fila, reescribe `htmlboxpro.php` y registra el hook.

Si el hook ya existe y el método `hook{Name}` ya está en `htmlboxpro.php`, la página muestra **El hook ya existe en la base de datos de la tienda** y no añade otra fila. Si el hook existe y falta el método, el módulo reescribe el archivo y registra el hook igual.

**¡regenerar ahora!** envía `hbp_rh_submit`. El aviso del botón es **use esta opción para reconstruir el archivo del módulo si los hooks personalizados no funcionan**. El título de al lado es **Regenerar hooks**. La reescritura cambia el tramo de `htmlboxpro.php` entre `//~~explode~~//` por un método por hook: `hook{Name}` devuelve `generateHookContents("{Name}", $params)`. El archivo tiene que poder escribirse. Texto de error: **El archivo principal del módulo no tiene permisos de escritura. Compruebe los permisos (CHMOD) del archivo /modules/htmlboxpro/htmlboxpro.php**. Texto de éxito: **Archivo principal del módulo reconstruido correctamente. El módulo debería admitir ahora hooks personalizados.**

**Remove hook** pregunta **Remove this custom hook?** Esas dos cadenas no están en `translations/es.php`, la pantalla muestra esa fuente en inglés. La acción borra la fila `hbp_customhook` y, si existe el id del hook en la tienda, borra ese `Hook`, y después reescribe el archivo.

El enlace **¿Cómo usar hooks personalizados?** abre `https://mypresta.eu/en/art/news/html-content-box-custom-hooks.html`. En el formulario, un bloque en un hook propio muestra **Este bloque usa un hook personalizado** y dos fragmentos:

`{hook::exec('HookName') nofilter}`

`{hook h='HookName' product=$product}`

El segundo fragmento es el descrito para una lista de productos.

## 9. Hooks registrados en la instalación

`actionAdminControllerSetMedia` añade el autocompletado de jQuery solo cuando `configure` es `htmlboxpro`. No imprime una caja.

Estos hooks llaman a `generateHookContents` con el nombre del hook. La salida sigue dependiendo de `hbp_{hook}` = 1 y de un bloque activo:

`displayHeader`, `displayBanner`, `displayNav1`, `displayNav2`, `displayNavFullWidth`, `displayTop`, `displayHome`, `displayFooterBefore`, `displayFooter`, `displayFooterAfter`, `displayMyAccountBlock`, `displayBeforeBodyClosingTag`, `displayLeftColumn`, `displayLeftColumnProduct`, `displayRightColumn`, `displayRightColumnProduct`, `displayOrderConfirmation`, `displayCustomerAccount`, `displayCustomerAccountForm`, `displayProductAdditionalInfo`, `displayReassurance`, `displayFooterProduct`, `displayAfterProductThumbs`, `displayProductListReviews`, `actionProductOutOfStock`, `displayShoppingCart`, `displayCartExtraProductActions`, `displayShoppingCartFooter`, `displayExpressCheckout`, `displayCustomerLoginFormAfter`, `displayBeforeCarrier`, `displayAfterCarrier`, `displayPaymentTop`, `displayPaymentByBinaries`.

`displayHeader` no adjunta un CSS ni un JS en la tienda. Imprime las cajas de ese hook. La tienda no recibe una hoja de estilo propia del módulo. El HTML, el CSS y el JavaScript son el cuerpo que guardó el vendedor.

`registerHook` usa el método padre cuando `hook{Name}` ya existe. Si no, inserta la fila `Hook` cuando hace falta e inserta `hook_module`.

## 10. Tablas y archivos

La instalación crea tres tablas si faltan, motor InnoDB, juego de caracteres `utf8_general_ci`. Delante del nombre va el prefijo de la tienda.

| Tabla | Columnas de la sentencia CREATE |
| --- | --- |
| `hbp_block` | `id` (auto increment, clave primaria), `position` por defecto 1, `hook` varchar(50), `active` por defecto 0, `logged` por defecto 0, `name` varchar(150), índice `indek1` |
| `hbp_customhook` | `id`, `hook` varchar(70) |
| `hbp_block_lang` | `id`, `id_lang`, `body` text. La sentencia CREATE no tiene clave primaria |

El modelo `models/hbox.php` mapea `hbp_block`, y `body` es multilingüe. La siguiente apertura de la configuración añade las columnas de los filtros: `bssl`, `shop` (por defecto 1), las banderas de página y de producto, las columnas de texto de los id elegidos, `datefrom`, `dateto`, `timfrom`, `timto`, `cgroup` (pasada a varchar 250), `hcgroup`, `onmobile`, `ontablet`, `onpc` (por defecto 1), campos de precio, `daytype`, `currency`, `geoip` y las columnas de carrito y de entrega. `inconsistency()` ensancha `hook` a varchar(255).

Otros archivos: `views/templates/hook/html.tpl` es el cuerpo de la tienda, `views/templates/admin/_configure/helpers/form/form.tpl` sustituye el formulario helper de este módulo, `lib/searchTool/` es la búsqueda de id, `lib/smartyTemplatesManager/` sirve `{smartyTemplate:name}`, `lib/prestashop9compatibility.php` es el helper de precio. `key.php` es opcional y no está en este paquete. La licencia de actualización dentro de `checkforupdates` es el literal `nlc`.

Claves de configuración que no son columnas: `hbp_notinyjs`, `hbp_tiny`, `hbp_forceurls`, `hbp_noajax`, `hbp_lasttab`, `firsttime_hbp`, `hbp_{hookname}`, `mypresta_updates`, `update_htmlboxpro`, `updatev_htmlboxpro`.

## 11. Desactivar, activar, desinstalar

La clase no tiene `disable()` ni `enable()`. Desactivar usa el padre de PrestaShop: el módulo sigue instalado, las tablas y la configuración se quedan, los hooks no se ejecutan. Activar usa la activación padre.

La clase no tiene `uninstall()`. Desinstalar usa el método padre: el módulo se da de baja y se quitan los registros de hook que PrestaShop guardó para él. El método padre no borra `hbp_block`, `hbp_block_lang` ni `hbp_customhook`. No borra las claves de configuración de la lista. No borra las filas `Hook` creadas con **Añadir nuevo hook** y no restaura `htmlboxpro.php` después de **¡regenerar ahora!** ni después de añadir un hook propio. Una instalación posterior usa `CREATE TABLE IF NOT EXISTS`, así que las filas que queden en esas tablas siguen ahí.

## 12. Zona vacía bajo las pestañas

El código acepta `selecttab` = 3 y puede guardar `hbp_lasttab` = 3. La barra no tiene un tercer botón y el render del formulario no tiene página para 3. Con ese valor la zona bajo la barra está vacía. **Configuración** o **Cajas** vuelven a escribir 1 o 2.

## 13. Soporte

Página del módulo: [HTML Box Pro](https://mypresta.eu/modules/front-office-features/html-box-pro.html).
