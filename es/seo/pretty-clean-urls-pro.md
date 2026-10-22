---
title: "URLs amigables y limpias - manual del vendedor"
description: "Instrucciones de configuración y resolución de problemas para quien ya tiene este módulo."
sidebar:
  label: "URLs amigables y limpias - manual del vendedor"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Pretty / Clean URLs PRO en MyPresta.eu](https://mypresta.eu/modules/seo/pretty-clean-urls-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/seo/pretty-clean-urls-pro/)
>
> ---


Nombre técnico `purls`, versión 3.0.0, nombre en el panel: URLs amigables y limpias.

## Dónde están las pantallas

Entre en **Módulos > Gestor de módulos** y configure **URLs amigables y limpias**. La página es el formulario **Configuración**, debajo el panel **Posibles colisiones** y debajo el panel **Actualizaciones de MyPresta**. El módulo no añade una entrada de menú propia, una pantalla de importación ni un bloque en la ficha del producto.

Las etiquetas salen de `translations/es.php`. La frase «on documentation page of this module» no está en los archivos de traducción, así que la pantalla muestra el texto fuente en inglés.

## Qué escribe el hecho de abrir la configuración

`install()` no escribe estos valores. Al abrir la configuración, `getContent()` escribe una ruta cuando el valor actual falta o está vacío:

| Clave | Valor escrito |
| --- | --- |
| `PURLS_ROUTE_cms_rule` | `info/{rewrite}.html` |
| `PURLS_ROUTE_cms_category_rule` | `info/{rewrite}` |
| `PURLS_ROUTE_supplier_rule` | `supplier/{rewrite}/` |
| `PURLS_ROUTE_manufacturer_rule` | `manufacturer/{rewrite}/` |
| `PS_ROUTE_category_rule` | `{parent_categories:/}{rewrite}/` |
| `PS_ROUTE_product_rule` | `{category:/}{rewrite}.html` |

`PS_ROUTE_product_rule` y `PS_ROUTE_category_rule` son claves de PrestaShop. Si están vacías, abrir esta página las sustituye por los valores de la tabla. Con más de un idioma, las cuatro claves `PURLS_ROUTE_*` se guardan por idioma. Con un idioma, como un solo texto.

## Configuración

![La pantalla está en inglés. En este manual: Configuración.](https://mypresta.eu/docs/images/docs/purls-configure-settings.webp)

![Pantalla en inglés, después de guardar. ID de producto: ID of product + ID of attribute. Hash desactivado. Categorías, fabricantes, proveedores y CMS activados. 301 activado. En este manual: Configuración.](https://mypresta.eu/docs/images/docs/purls-configure-enabled.webp)

La leyenda es **Configuración**. La descripción es **Selecciona de qué tipo de URLs quieres eliminar el ID**. El botón es **Guardar** (`submitCategoryFeatured`).

`install()` no crea estas claves. Hasta el primer guardado, `Configuration::get` devuelve false. La eliminación solo corre con los valores de abajo, así que una clave ausente deja el ID en la URL. En el formulario, false coincide con la opción `0` (**No eliminar números de ID** / **Desactivado**).

| Etiqueta | Clave | Valores |
| --- | --- | --- |
| ID de Producto | `purls_products` | `0` No eliminar números de ID. `1` ID de producto + ID de atributo. `2` Solo ID de atributo. `3` Solo ID de producto. |
| Hashcode con atributos | `purls_product_hash` | `1` Activado, `0` Desactivado. |
| Categorías | `purls_categories` | `1` Activado quita el ID de los enlaces de categoría. `0` Desactivado. |
| Fabricantes | `purls_manufacturers` | `1` Activado quita el ID de los enlaces de fabricante. `0` Desactivado. |
| Proveedores | `purls_suppliers` | `1` Activado quita el ID de los enlaces de proveedor. `0` Desactivado. |
| CMS | `purls_cms` | `1` Activado quita el ID de los enlaces CMS. `0` Desactivado. |
| Redirección 301 desde URLs antiguas | `purls_301` | Radio. `1` Activado, `0` Desactivado. Texto: Activar la redirección automática de URLs antiguas (con ID) a URLs nuevas (sin ID). |

La ayuda de **ID de Producto** pide editar el esquema de productos:

- **ID de producto + ID de atributo**: quitar `{id}` y `{id_product_attribute}`.
- **Solo ID de atributo**: quitar `{id_product_attribute}`.
- **Solo ID de producto**: quitar `{id}` y usar `{id_product_attribute:-}` como id de atributo.

La misma ayuda abre `https://mypresta.eu/documentation/pretty-clean-urls/configuration-and-module-usage/schema-of-urls-settings.html`. El texto del enlace es la fuente inglesa «on documentation page of this module».

**Hashcode con atributos**: Activado corta la URL del producto en `#`. Desactivado, y solo si ID de Producto es `1` o `2`, conserva un hash como `#/size-s/color-white`. El texto de ayuda dice que la opción actúa cuando el id de atributo de producto se quita de la URL. En el código, `Link::getProductLink()` conserva el hash solo si `purls_product_hash` es `0` y `purls_products` es `1` o `2`. Con el valor `3`, el mismo método corta siempre la URL en `#`. El valor `0` de ID de Producto llama al método padre de PrestaShop.

| Etiqueta | Clave | Campo de idioma | Palabras del formulario |
| --- | --- | --- | --- |
| Regla de producto | `PS_ROUTE_product_rule` | No | `{rewrite}`, `{category}`, `{categories}`, `{id}`, `{-:id_product_attribute}` |
| Regla de categoría | `PS_ROUTE_category_rule` | No | `{id}`, `{rewrite}`, `{parent_categories}` |
| Regla de proveedor | `PURLS_ROUTE_supplier_rule` | Sí | `{id}`, `{rewrite}` |
| Regla de marca | `PURLS_ROUTE_manufacturer_rule` | Sí | `{id}`, `{rewrite}` |
| Regla de página CMS | `PURLS_ROUTE_cms_rule` | Sí | `{categories:/}`, `{id}`, `{rewrite}` |
| Regla de página de categoría CMS | `PURLS_ROUTE_cms_category_rule` | Sí | `{id}`, `{rewrite}` |

En regla de producto y de categoría aparece: este campo también se configura en la sección de esquema de URLs, en Parámetros de la tienda > Tráfico y SEO.

En proveedor, marca, página CMS y categoría CMS, con el interruptor a `0`, aparece **Para editar este campo, necesitas activar la opción de eliminar el ID de este tipo de URL**. El campo sigue siendo editable. El dispatcher y `Link` usan la ruta del módulo solo con el interruptor a `1`.

### Esquemas de los campos de ruta

Son los patrones de la página de esquemas. En **Regla de producto** va una fila del grupo que corresponde a **ID de producto**. `{category}` es el rewrite de la categoría por defecto. `{categories}` son los rewrite de las categorías padre unidos con `/` (`Link::getProductLink()`). `{rewrite}` es `link_rewrite`. `{id}` es el id del producto. `{id_product_attribute:-}` es el id de la combinación, con `-` delante cuando ese id está presente. Un campo de producto vacío se rellena con `{category:/}{rewrite}.html` también si el ID de producto es `2` o `3`, así que en esas dos opciones hay que escribir en el campo una fila de su grupo.

| Campo | ID de producto | Esquema |
| --- | --- | --- |
| Regla de producto | `1` | `{rewrite}.html` |
| Regla de producto | `1` | `{category:/}{rewrite}.html` |
| Regla de producto | `1` | `{categories}{rewrite}.html` |
| Regla de producto | `1` | `{categories}{rewrite}` |
| Regla de producto | `2` | `{id}-{rewrite}.html` |
| Regla de producto | `2` | `{category:/}{id}-{rewrite}.html` |
| Regla de producto | `2` | `{categories}{id}-{rewrite}.html` |
| Regla de producto | `2` | `{categories}{id}-{rewrite}` |
| Regla de producto | `3` | `{id_product_attribute:-}{rewrite}.html` |
| Regla de producto | `3` | `{category:/}{id_product_attribute:-}{rewrite}.html` |
| Regla de producto | `3` | `{categories}{id_product_attribute:-}{rewrite}.html` |
| Regla de producto | `3` | `{categories}{id_product_attribute:-}{rewrite}` |

| Campo | Esquema |
| --- | --- |
| Regla de categoría | `{parent_categories:/}{rewrite}/` |
| Regla de categoría | `{rewrite}/` |
| Regla de proveedor | `supplier/{rewrite}/` |
| Regla de proveedor | `any-text/{rewrite}/` |
| Regla de marca | `manufacturer/{rewrite}/` |
| Regla de marca | `any-text/{rewrite}/` |
| Regla de página CMS | `info/{rewrite}.html` |
| Regla de página de categoría CMS | `info/{rewrite}` |

Un campo de categoría vacío se rellena con `{parent_categories:/}{rewrite}/`. La otra fila de categoría es la alternativa. `{parent_categories}` son los rewrite de las categorías padre unidos con `/`, sin los id 1, 2 y la propia categoría. Un campo de proveedor vacío se rellena con `supplier/{rewrite}/`, un campo de marca vacío con `manufacturer/{rewrite}/`. `any-text` no es una palabra de la ruta. Es un prefijo fijo que se escribe en lugar de esas palabras, por ejemplo `marca/{rewrite}/`. La página de esquemas no da alternativa para las dos reglas CMS. Los campos CMS vacíos se rellenan con `info/{rewrite}.html` e `info/{rewrite}`.

`parent::loadRoutes()` lee `PS_ROUTE_` más el id de la ruta. Si ese valor no está vacío, esa cadena es la regla compilada, así que un esquema de producto o de categoría guardado sustituye la regla que asignó `loadRoutes()`. Este módulo no escribe `PS_ROUTE_supplier_rule_{id_lang}`, `PS_ROUTE_manufacturer_rule_{id_lang}`, `PS_ROUTE_cms_rule_{id_lang}` ni `PS_ROUTE_cms_category_rule_{id_lang}`. Esas rutas de idioma siguen siendo los valores `PURLS_ROUTE_*`. Las rutas base `supplier_rule` y `manufacturer_rule` siguen siendo `supplier/{rewrite}/` y `manufacturer/{rewrite}/`.

## Qué hace Guardar

**Guardar** hace esto, en este orden:

1. Borra los nombres de configuración `PURLS_ROUTE_cms_category_rule`, `PURLS_ROUTE_cms_rule`, `PURLS_ROUTE_supplier_rule` y `PURLS_ROUTE_manufacturer_rule`. Los valores de esos cuatro claves, en todos los idiomas, desaparecen antes de escribir los nuevos.
2. Vuelve a escribir esas cuatro claves desde los campos enviados. Con varios idiomas, los campos se llaman `PURLS_ROUTE_..._{id_lang}`. Con un idioma, el campo usa el id del idioma de contexto. Un campo vacío se guarda como cadena vacía.
3. Escribe `purls_product_hash`, `PS_ROUTE_category_rule`, `PS_ROUTE_product_rule`, `purls_products`, `purls_categories`, `purls_manufacturers`, `purls_suppliers`, `purls_cms` y `purls_301`.

Guardar sustituye el esquema de producto y de categoría de PrestaShop. El formulario no escribe `PS_ROUTE_supplier_rule`, `PS_ROUTE_manufacturer_rule`, `PS_ROUTE_cms_rule` ni `PS_ROUTE_cms_category_rule`. El texto de confirmación es **Tus ajustes han sido actualizados.**

## Avisos del formulario

El aviso sale cuando el interruptor correspondiente está apagado (`0` o ausente) y `strpos` de la palabra en la ruta de PrestaShop es `== false`. En PHP esa comparación también es verdadera cuando la palabra está en la posición 0, así que un esquema que empieza por `{id}` muestra el aviso igualmente.

La comprobación lee claves de PrestaShop, no los campos `PURLS_ROUTE_*`:

- ID de Producto es `0` y `PS_ROUTE_product_rule` no tiene `{id}`: «La URL de reescritura de tu producto no contiene la variable {id}. Es necesaria cuando no quieres eliminar el ID de la URL de las páginas de producto».
- ID de Producto es `0` y falta `{-:id_product_attribute}`: «La URL de reescritura de tu producto no contiene la variable {-:id_product_attribute}. Es necesaria cuando no quieres eliminar el ID del atributo del producto de la URL de las páginas de producto».
- Categorías es `0` y `PS_ROUTE_category_rule` no tiene `{id}`: «La URL de reescritura de tu categoría no contiene la variable {id}. Es necesaria cuando no quieres eliminar el ID de la URL de las páginas de categoría».
- Fabricantes es `0` y `PS_ROUTE_manufacturer_rule` no tiene `{id}`: «La URL de reescritura de tu fabricante no contiene la variable {id}. Es necesaria cuando no quieres eliminar el ID de la URL de las páginas de fabricante».
- Proveedores es `0` y `PS_ROUTE_supplier_rule` no tiene `{id}`: «La URL de reescritura de tu proveedor no contiene la variable {id}. Es necesaria cuando no quieres eliminar el ID de la URL de las páginas de proveedor».
- CMS es `0` y `PS_ROUTE_cms_category_rule` no tiene `{id}`: «La URL de reescritura de tu categoría de CMS no contiene la variable {id}. Es necesaria cuando no quieres eliminar el ID de la URL de las páginas de proveedor».
- CMS es `0` y `PS_ROUTE_cms_rule` no tiene `{id}`: «La URL de reescritura de tu CMS no contiene la variable {id}. Es necesaria cuando no quieres eliminar el ID de la URL de las páginas de proveedor».

Los dos últimos textos hablan de páginas de proveedor. Así está en `translations/es.php`.

## Posibles colisiones

![La pantalla está en inglés. En este manual: Posibles colisiones.](https://mypresta.eu/docs/images/docs/purls-collisions.webp)

El panel **Posibles colisiones** es `views/purls.tpl`, debajo del formulario. Lista `link_rewrite` duplicados por idioma activo de la tienda actual.

El texto **Añade esta URL a tu tabla de trabajos cron para corregir automáticamente las colisiones** imprime un enlace de la tienda al controlador `cron` del módulo, con `key` igual a `Tools::hash('purls')`. Este paquete no contiene `controllers/front/cron.php`. El método `cronJob()` llama a la misma rutina para productos y categorías en cada idioma activo, y ningún archivo de este paquete llama a `cronJob()`.

**URLs de Productos**. Columnas: **ID**, **Nombre**, **Reescritura de Enlace**, **Ocurrencia**, **Acción**. Por idioma, el menú **Corregir todas las colisiones** tiene **Corregir todo de una vez** y **Corregir parcialmente**. **Mostrar productos** recarga la página con `product_rewrite` e `id_lang`. Si la lista está vacía: **No se encontraron colisiones**.

**URLs de Categorías** usa las mismas columnas. El botón es **Hacer únicos los campos de reescritura**. **Mostrar categorías** añade `category_rewrite`. `getAllCategoryCollisionsRewrite()` recibe un argumento `id_lang` y ejecuta el SQL con el id de idioma del contexto, no con ese argumento.

**Corregir todo de una vez**, **Hacer únicos los campos de reescritura** y **Corregir parcialmente** llaman a `makeUnique()`. En cada rewrite duplicado, la primera fila conserva `link_rewrite`. Cada fila siguiente se guarda con ese rewrite más `-1`, `-2`, y así, en el idioma del botón. `save()` se ejecuta para cada fila del grupo, incluida la primera. Eso cambia `product_lang.link_rewrite` o `category_lang.link_rewrite`. La desinstalación no devuelve el rewrite anterior.

**Corregir parcialmente** envía una petición AJAX por fila de producto (`AjaxCollisions`, `id_lang`, `id_product`) y oculta la fila tras la respuesta.

La consulta de productos agrupa `link_rewrite` en `product_lang` de la tienda y el idioma actuales y se queda con grupos de recuento 2 o más. No filtra por categoría. Las categorías hacen lo mismo sobre `category_lang`.

## Rutas, redirecciones y el hash del producto

El emparejamiento propio de `Dispatcher::getController()` corre cuando PrestaShop usa URLs amigables (`use_routes`), el controlador aún no está elegido y la petición no es del back office. La sobreescritura copia las rutas originales y las vuelve a registrar con el sufijo `_original`.

Estas pantallas de la tienda son posteriores al guardado de Configuración. El idioma de la tienda es inglés. Las rutas no llevan id numérico.

![Tienda en inglés. Ruta: men/hummingbird-printed-t-shirt.html#/color-white/size-s. Seleccionados Size S y Color White.](https://mypresta.eu/docs/images/docs/purls-front-product.webp)

![Tienda en inglés. Ruta: clothes/men/. Título: Men.](https://mypresta.eu/docs/images/docs/purls-front-category.webp)

![Tienda en inglés. Ruta: manufacturer/studio-design/. Título: List of products by brand Studio Design.](https://mypresta.eu/docs/images/docs/purls-front-manufacturer.webp)

![Tienda en inglés. Ruta: info/delivery.html. Título: Delivery.](https://mypresta.eu/docs/images/docs/purls-front-cms.webp)

Con el interruptor a `1`, `Dispatcher::loadRoutes()` asigna estas `default_routes` y luego llama a `parent::loadRoutes()`:

| Interruptor | Id de ruta | Regla asignada |
| --- | --- | --- |
| `purls_products` = `1` | `product_rule` | `{category:/}{rewrite}.html` |
| `purls_products` = `2` | `product_rule` | `{category:/}{id}-{rewrite}.html` |
| `purls_products` = `3` | `product_rule` | `{category:/}{id_product_attribute:-}{rewrite}.html` |
| `purls_categories` = `1` | `category_rule` | `{parent_categories:/}{rewrite}/` |
| `purls_suppliers` = `1` | `supplier_rule` y `supplier_rule_{id_lang}` | base `supplier/{rewrite}/`, regla de idioma desde `PURLS_ROUTE_supplier_rule` |
| `purls_manufacturers` = `1` | `manufacturer_rule` y `manufacturer_rule_{id_lang}` | base `manufacturer/{rewrite}/`, regla de idioma desde `PURLS_ROUTE_manufacturer_rule` |
| `purls_cms` = `1` | `cms_rule`, `cms_category_rule` y las mismas con `_{id_lang}` | base `info/{rewrite}.html` e `info/{rewrite}` |

Los demás esquemas de estos campos están en Configuración, en **Esquemas de los campos de ruta**. Un esquema de producto o de categoría guardado sustituye la regla de esta tabla.

`Link` construye la dirección solo con el interruptor encendido. Si no, llama al método padre de PrestaShop.

- Productos (`purls_products` `1`, `2` o `3`): `getProductLink()` usa `product_rule`. Los parámetros que no son palabras de esa ruta se omiten. Los `extraParams` que no son palabras de la ruta se conservan.
- Categorías (`purls_categories` = `1`): `getCategoryLink()` usa `category_rule`. Si la ruta tiene la palabra `parent_categories`, la ruta se arma con las categorías padre, sin los id 1, 2 y la propia categoría.
- Proveedores, fabricantes, páginas CMS y categorías CMS usan `supplier_rule_{id_lang}`, `manufacturer_rule_{id_lang}`, `cms_rule_{id_lang}` y `cms_category_rule_{id_lang}`.

Búsqueda cuando el id no está en la URL:

- Productos en modos `1` y `3`: el último segmento, sin `.html`, se compara con `product_lang.link_rewrite`. Si hay un segmento de categoría, también se compara el `link_rewrite` de la categoría por defecto. Si no hay resultado, una segunda consulta usa solo `link_rewrite`. El resultado va a `$_GET['id_product']`.
- Categorías: la ruta se compara con `category_lang.link_rewrite`, con los segmentos padre si hay más de una parte.
- Páginas CMS: `cms_lang.link_rewrite`, sin `.html`.
- Categorías CMS: `cms_category_lang.link_rewrite`.
- Fabricantes y proveedores: `Tools::str2url()` del **nombre**, no de la columna `link_rewrite`. El primer segmento `supplier` lo rechaza la comprobación de fabricante. Si varios nombres dan el mismo slug, queda la última fila del bucle.

`purls_301` = `1` envía `HTTP/1.1 301 Moved Permanently` solo en estos casos:

- La ruta de proveedor trae `id_supplier` y la eliminación de proveedores está activa: redirección a `getSupplierLink()`.
- La ruta de fabricante trae `id_manufacturer` y la eliminación de fabricantes está activa: redirección a `getManufacturerLink()`.
- La ruta CMS trae `id_cms`: redirección a `getCmsLink()`. Trae `id_cms_category`: redirección a `getCmsCategoryLink()`. La eliminación CMS tiene que estar activa.
- Modo de producto `1`: la ruta trae `id_product` e `isProductLink()` devolvió false: redirección a `getProductLink()`. Los modos `2` y `3` no llaman a esa redirección.
- La eliminación de categorías está activa, la ruta trae `id_category` e `isCategoryLink()` devolvió false: redirección a `getCategoryLink()`.

El modo de producto `3`, si el emparejamiento trae `id_product_attribute` no vacío, llama a `isProductLinkAttribute()`. Ese método escribe `$_GET['id_product']` y `$_GET['id_product_attriubte']` (la clave está escrita así en el archivo). No escribe `id_product_attribute`.

En la ficha de producto, `displayHeader` añade `views/js/purls.js` solo si el controlador es `product`, la petición no es AJAX, hay id de producto, `purls_product_hash` es `0`, `purls_products` es `1` o `2` y el producto tiene combinaciones. El separador es `PS_ATTRIBUTE_ANCHOR_SEPARATOR`, o `-` si ese valor falta o está vacío. El script lee el hash, marca el `select` o el `radio` `group[groupId]` y emite `prestashop.updateProduct` si un control cambió.

`CartController::displayAjaxProductRefresh()` reconstruye la URL del producto y añade `idpa` con el id de combinación. `ProductController::init()` copia `idpa` a `id_product_attribute` cuando `id_product_attribute` no está. `getIdProductAttributeByRequest()` lee primero `idpa`.

Si `pm_advancedsearch4` está instalado, `hookModuleRoutes()` añade tres rutas con `/filter-{id}/s-{id_search}/{as4_sq}` a las reglas de categoría, proveedor y fabricante. Si no está instalado, el hook no devuelve nada.

## Hooks

`install()` registra solo estos hooks:

| Hook | Método | Qué hace |
| --- | --- | --- |
| `displayHeader` | `hookdisplayHeader` | En la ficha de producto, con las condiciones de arriba, añade `views/js/purls.js` y el mapa `purls_attributes`. |
| `ModuleRoutes` | `hookModuleRoutes` | Devuelve rutas de Advanced Search 4 si ese módulo está instalado. |
| `actionAdminControllerSetMedia` | `hookactionAdminControllerSetMedia` | Método vacío. |

## Clases y archivos sustituidos

PrestaShop copia estos archivos a `override/` de la tienda durante la instalación:

| Archivo | Clase | Qué cambia |
| --- | --- | --- |
| `override/classes/Dispatcher.php` | `Dispatcher` extiende `DispatcherCore` | `loadRoutes()`, `getController()` y `isProductLink`, `isProductLinkAttribute`, `isCategoryLink`, `isCmsLink`, `isCmsCategoryLink`, `isManufacturerLink`, `isSupplierLink`. |
| `override/classes/Link.php` | `Link` extiende `LinkCore` | `getProductLink`, `getCategoryLink`, `getSupplierLink`, `getManufacturerLink`, `getCMSLink`, `getCMSCategoryLink`, `getPaginationLink`, `getAnchor`. Omite parámetros que no son palabras de la ruta compilada. |
| `override/controllers/front/ProductController.php` | `ProductController` | Lee `idpa` en `init()`, `getIdProductAttributeByRequest()` y `getIdProductAttribute()`. |
| `override/controllers/front/CartController.php` | `CartController` | `displayAjaxProductRefresh()` añade `idpa`. |
| `override/controllers/front/CmsController.php` | `CmsController` | Con `purls_cms` a `1`, resuelve `id_cms` / `id_cms_category` desde `link_rewrite`. También lee rutas antiguas `content/{id}-{rewrite}` y `content/category/{id}-{rewrite}`. |
| `override/controllers/front/listing/CategoryController.php` | `CategoryController` | Con `purls_categories` a `1`, resuelve `id_category` desde `category_rewrite` y la ruta. |
| `override/controllers/front/listing/ManufacturerController.php` | `ManufacturerController` | Con `purls_manufacturers` a `1`, resuelve `id_manufacturer` con `Tools::str2url(name)`. |
| `override/controllers/front/listing/SupplierController.php` | `SupplierController` | Con `purls_suppliers` a `1`, resuelve `id_supplier` con `Tools::str2url(name)`. |
| `override/controllers/admin/AdminProductsController.php` | `AdminProductsController` | Solo `getPreviewUrl()`. Construye el enlace del producto en el idioma por defecto de la tienda, id de combinación `0` y `force_routes` igual a `PS_REWRITING_SETTINGS`. Un producto inactivo recibe `adtoken`, `ad` e `id_employee`. |

No hay panel en el formulario del producto. No hay archivo CSS. La configuración es `views/purls.tpl` más el helper de formulario de PrestaShop. El script de la tienda es `views/js/purls.js`. `purls.tpl` incluye además la función `FixProductsCollisions`.

`Link::psversion()` y `ProductController::psversion()` parten `_PS_VERSION_`. `getCategoryLink()` usa una rama de meta title cuando la versión menor es 6 o 7, o la mayor es 8 o superior, y otra rama en el resto. Los comentarios de `Dispatcher.php` y `ProductController.php` nombran PrestaShop 9 y, en un método privado, PrestaShop 1.7.

El módulo no crea ninguna tabla SQL. Lee y escribe `configuration`, y lee `product_lang`, `category_lang`, `cms_lang`, `cms_category_lang`, `manufacturer`, `supplier` y las tablas de atributos al armar el hash. La reparación de colisiones escribe `link_rewrite` mediante `Product::save()` y `Category::save()`.

En el back office, el constructor crea `override/controllers/front/listing` con modo `0777` si existe `override/controllers/front/` y no existe `listing`.

## Actualizaciones de MyPresta

![La pantalla está en inglés. En este manual: Actualizaciones de MyPresta.](https://mypresta.eu/docs/images/docs/purls-updates.webp)

El panel **Actualizaciones de MyPresta** está entre el formulario de configuración y el panel de colisiones.

| Etiqueta | Control |
| --- | --- |
| Comprobar actualizaciones | Botón **Comprobar ahora** (`submit_settings_updates_now`). Muestra **¡Nueva versión disponible!** o **¡El módulo está actualizado!** |
| Notificaciones de actualizaciones | Lista `mypresta_updates`: **-- seleccionar --** (`-`), **Activar** (`1`), **Desactivar** (`0`). |
| Página del módulo | Enlace a la página del producto. La dirección está en la sección de soporte. |
| Guardar | `submit_settings_updates` escribe solo `mypresta_updates`. |

En cada petición del back office el constructor llama a `checkforupdates()`. Si `update_purls` falta o tiene más de 259200 segundos, `purlsUpdate::verify()` pide `http://dev.mypresta.eu/update/get.php` si hay `allow_url_fopen` y `file_get_contents`. Guarda el tiempo Unix en `update_purls` y el cuerpo de la respuesta en `updatev_purls`. El valor de licencia de este paquete es `nlc` (`$this->mkey`), salvo que un `key.php` junto al módulo lo cambie. Este paquete no trae `key.php`.

Si `mypresta_updates` no es `0` ni false, la versión remota guardada es mayor que 3.0.0 y la petición no es AJAX, el back office muestra **Nueva versión disponible, consulta http://MyPresta.eu para más información** y **Más detalles en el changelog**. El valor `0` ejecuta igual la petición temporizada y no añade ese aviso. Una clave ausente es false, y false equivale a `0`, así que no añade el aviso.

## Instalación, desactivar, activar, desinstalar

`install()` llama a `parent::install()` y registra `displayHeader`, `ModuleRoutes` y `actionAdminControllerSetMedia`. Si algo de eso falla, la instalación devuelve false. No inserta configuración y no crea una tabla.

El archivo no define `enable()` ni `disable()`. Desactivar el módulo en el panel no ejecuta un método de este archivo. Las clases de override siguen en `override/` de la tienda, porque este módulo no tiene un `disable()` que las quite. Los tres hooks no se ejecutan mientras el módulo está desactivado.

`uninstall()` devuelve solo `parent::uninstall()`. Eso quita el módulo, da de baja los hooks y borra las copias de override que instaló PrestaShop. No borra la configuración. No restaura `PS_ROUTE_product_rule` ni `PS_ROUTE_category_rule`. No restaura los `link_rewrite` cambiados por los botones de colisiones. Quedan: `purls_products`, `purls_product_hash`, `purls_categories`, `purls_manufacturers`, `purls_suppliers`, `purls_cms`, `purls_301`, las cuatro claves `PURLS_ROUTE_*`, `mypresta_updates`, `update_purls`, `updatev_purls` y las dos claves `PS_ROUTE_*` escritas por el formulario.

## Cuando una página no resuelve

- El ID sigue en la URL: ID de Producto es `0` o la clave no se guardó, o el esquema de producto/categoría todavía contiene `{id}`. El emparejamiento propio de `getController()` solo corre con las URLs amigables (`use_routes`) activas.
- Una URL limpia cae en el controlador de no encontrado: dos productos o categorías comparten `link_rewrite`. El panel de colisiones lista esas filas. Los botones de corrección cambian `link_rewrite` en la base.
- Una URL antigua con id no redirige: `purls_301` no es `1`, o el tipo de página es el modo de producto `2` o `3` (esas ramas no llaman a `Tools::redirect`).
- La URL de fabricante o proveedor abre el registro equivocado, o ninguno: el emparejamiento usa `Tools::str2url()` del nombre.
- El módulo está desactivado y las URLs siguen pasando por este código: los overrides siguen en `override/` hasta la desinstalación.
- Tras desinstalar, los esquemas de producto y categoría son los últimos valores guardados por este formulario.

## Soporte

Página del producto: [https://mypresta.eu/modules/seo/pretty-clean-urls-pro.html](https://mypresta.eu/modules/seo/pretty-clean-urls-pro.html). El campo **Página del módulo** del panel de actualizaciones abre esta dirección. La ayuda de la configuración abre también `https://mypresta.eu/documentation/pretty-clean-urls/configuration-and-module-usage/schema-of-urls-settings.html`.
