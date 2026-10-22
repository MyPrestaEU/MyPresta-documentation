---
title: "Pretty Clean URLs - merchant manual"
description: "Configuration and troubleshooting instructions for merchants who already have this module."
sidebar:
  label: "Pretty Clean URLs - merchant manual"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Pretty / Clean URLs PRO Module on MyPresta.eu](https://mypresta.eu/modules/seo/pretty-clean-urls-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/seo/pretty-clean-urls-pro/)
>
> ---


Technical name `purls`, version 3.0.0, name in the back office: Pretty Clean URLs.

## Where the screens are

Open **Modules > Module Manager** and configure **Pretty Clean URLs**. The page is one settings form, then the panel **Possible collisions**, then the panel **MyPresta updates**. The module does not add a menu entry of its own, an import screen, or a block on the product edit page.

Labels below are the English source from `translations/en.php`. The sentence "on documentation page of this module" is not in the translation files, so the screen shows that English source.

## What opening the configuration page writes

`install()` does not write these values. The first time the configuration page is opened, `getContent()` writes a route when the current value is missing or an empty string:

| Key | Value written |
| --- | --- |
| `PURLS_ROUTE_cms_rule` | `info/{rewrite}.html` |
| `PURLS_ROUTE_cms_category_rule` | `info/{rewrite}` |
| `PURLS_ROUTE_supplier_rule` | `supplier/{rewrite}/` |
| `PURLS_ROUTE_manufacturer_rule` | `manufacturer/{rewrite}/` |
| `PS_ROUTE_category_rule` | `{parent_categories:/}{rewrite}/` |
| `PS_ROUTE_product_rule` | `{category:/}{rewrite}.html` |

`PS_ROUTE_product_rule` and `PS_ROUTE_category_rule` are PrestaShop keys. If they are empty, opening this page replaces them with the values above. With more than one language, the four `PURLS_ROUTE_*` keys are stored per language. With one language, they are stored as a single string.

## Settings

![Settings](https://mypresta.eu/docs/images/docs/purls-configure-settings.webp)

![Settings after save. Product ID is ID of product + ID of attribute. Hashcode with attributes is Disabled. Categories, Manufacturers, Suppliers and CMS are Enabled. 301 redirection from old urls is Enabled. The route fields stay {category:/}{rewrite}.html, {parent_categories:/}{rewrite}/, supplier/{rewrite}/, manufacturer/{rewrite}/, info/{rewrite}.html and info/{rewrite}.](https://mypresta.eu/docs/images/docs/purls-configure-enabled.webp)

The form legend is **Settings**. The description is **Select from what kind of URLs you want to remove ID**. The submit button is **Save** (`submitCategoryFeatured`).

`install()` does not create these keys. Until the first save, `Configuration::get` returns false. Removal runs only for the values listed below, so a missing key leaves IDs in place. On the form, false matches option `0` (**Do not remove ID numbers** / **Disabled**).

| Label | Key | Values |
| --- | --- | --- |
| Product ID | `purls_products` | `0` Do not remove ID numbers. `1` ID of product + ID of attribute. `2` ID of attribute only. `3` ID of product only. |
| Hashcode with attributes | `purls_product_hash` | `1` Enabled, `0` Disabled. |
| Categories | `purls_categories` | `1` Enabled removes the ID from category links. `0` Disabled. |
| Manufacturers | `purls_manufacturers` | `1` Enabled removes the ID from manufacturer links. `0` Disabled. |
| Suppliers | `purls_suppliers` | `1` Enabled removes the ID from supplier links. `0` Disabled. |
| CMS | `purls_cms` | `1` Enabled removes the ID from CMS links. `0` Disabled. |
| 301 redirection from old urls | `purls_301` | Radio. `1` Enabled, `0` Disabled. Text: Turn on auto-redirection from old urls (with ID) to new urls (without ID). |

**Product ID** help tells you to edit the product schema:

- **ID of product + id of attribute**: remove `{id}` and `{id_product_attribute}` from "Route to products".
- **ID of attribute only**: remove `{id_product_attribute}` from "Route to products".
- **ID of product only**: remove `{id}` from "Route to products" and use `{id_product_attribute:-}` for the attribute id.

The same help links to `https://mypresta.eu/documentation/pretty-clean-urls/configuration-and-module-usage/schema-of-urls-settings.html`. The link text is the English source "on documentation page of this module".

**Hashcode with attributes**: Enabled cuts the product URL at `#`, so the attribute hash is not in the address. Disabled, and only when Product ID is `1` or `2`, keeps a hash such as `#/size-s/color-white`. The help text says the option works when the product attribute id is removed from the URL. In code, `Link::getProductLink()` keeps the hash only when `purls_product_hash` is `0` and `purls_products` is `1` or `2`. For value `3` the same method always cuts the URL at `#`. Value `0` of Product ID does not use this method; it calls the PrestaShop parent.

| Label | Key | Language field | Keywords shown on the form |
| --- | --- | --- | --- |
| Product rule | `PS_ROUTE_product_rule` | No | `{rewrite}`, `{category}`, `{categories}`, `{id}`, `{-:id_product_attribute}` |
| Category rule | `PS_ROUTE_category_rule` | No | `{id}`, `{rewrite}`, `{parent_categories}` |
| Supplier rule | `PURLS_ROUTE_supplier_rule` | Yes | `{id}`, `{rewrite}` |
| Brand rule | `PURLS_ROUTE_manufacturer_rule` | Yes | `{id}`, `{rewrite}` |
| Cms page rule | `PURLS_ROUTE_cms_rule` | Yes | `{categories:/}`, `{id}`, `{rewrite}` |
| Cms category page rule | `PURLS_ROUTE_cms_category_rule` | Yes | `{id}`, `{rewrite}` |

Product rule and Category rule show: This field is also configurable under "schema of urls" section in: Shop parameters > Traffic & SEO.

Supplier rule, Brand rule, Cms page rule, and Cms category page rule show this text when the matching switch is `0`: **To edit this field you need to activate option to remove id from this type of url**. The input stays editable. The dispatcher and `Link` use the module route only when the switch is `1`.

### Schemas for the route fields

These are the patterns from the schema page. Use a row from the group that matches **Product ID**. `{category}` is the default category rewrite. `{categories}` is the parent category rewrites joined by `/` (`Link::getProductLink()`). `{rewrite}` is `link_rewrite`. `{id}` is the product id. `{id_product_attribute:-}` is the combination id, with `-` in front when that id is present. An empty product field is filled with `{category:/}{rewrite}.html` even when Product ID is `2` or `3`, so for those two options type one of their rows into **Product rule**.

| Field | Product ID | Schema |
| --- | --- | --- |
| Product rule | `1` | `{rewrite}.html` |
| Product rule | `1` | `{category:/}{rewrite}.html` |
| Product rule | `1` | `{categories}{rewrite}.html` |
| Product rule | `1` | `{categories}{rewrite}` |
| Product rule | `2` | `{id}-{rewrite}.html` |
| Product rule | `2` | `{category:/}{id}-{rewrite}.html` |
| Product rule | `2` | `{categories}{id}-{rewrite}.html` |
| Product rule | `2` | `{categories}{id}-{rewrite}` |
| Product rule | `3` | `{id_product_attribute:-}{rewrite}.html` |
| Product rule | `3` | `{category:/}{id_product_attribute:-}{rewrite}.html` |
| Product rule | `3` | `{categories}{id_product_attribute:-}{rewrite}.html` |
| Product rule | `3` | `{categories}{id_product_attribute:-}{rewrite}` |

| Field | Schema |
| --- | --- |
| Category rule | `{parent_categories:/}{rewrite}/` |
| Category rule | `{rewrite}/` |
| Supplier rule | `supplier/{rewrite}/` |
| Supplier rule | `any-text/{rewrite}/` |
| Brand rule | `manufacturer/{rewrite}/` |
| Brand rule | `any-text/{rewrite}/` |
| Cms page rule | `info/{rewrite}.html` |
| Cms category page rule | `info/{rewrite}` |

An empty category field is filled with `{parent_categories:/}{rewrite}/`. The other category row is the alternative. `{parent_categories}` is the parent rewrites joined by `/`, skipping ids 1, 2, and the category itself. An empty supplier field is filled with `supplier/{rewrite}/`, an empty brand field with `manufacturer/{rewrite}/`. `any-text` is not a keyword. It is a fixed prefix you type instead of those words, for example `brand/{rewrite}/`. The schema page lists no alternative for the two CMS rules. Empty CMS fields are filled with `info/{rewrite}.html` and `info/{rewrite}`.

`parent::loadRoutes()` reads `PS_ROUTE_` plus the route id. When that value is not empty, that string is the compiled rule, so a saved product or category schema replaces the rule `loadRoutes()` assigned. This module does not write `PS_ROUTE_supplier_rule_{id_lang}`, `PS_ROUTE_manufacturer_rule_{id_lang}`, `PS_ROUTE_cms_rule_{id_lang}`, or `PS_ROUTE_cms_category_rule_{id_lang}`. Those language routes stay the `PURLS_ROUTE_*` values. The base routes `supplier_rule` and `manufacturer_rule` stay `supplier/{rewrite}/` and `manufacturer/{rewrite}/`.

## What Save does

**Save** does all of the following, in this order:

1. Deletes the configuration names `PURLS_ROUTE_cms_category_rule`, `PURLS_ROUTE_cms_rule`, `PURLS_ROUTE_supplier_rule`, and `PURLS_ROUTE_manufacturer_rule`. Every language value of those four keys is removed before the new values are written.
2. Writes those four keys again from the posted fields. With more than one language, the field names are `PURLS_ROUTE_..._{id_lang}`. With one language, the field uses the current context language id. An empty field is stored as an empty string.
3. Writes `purls_product_hash`, `PS_ROUTE_category_rule`, `PS_ROUTE_product_rule`, `purls_products`, `purls_categories`, `purls_manufacturers`, `purls_suppliers`, `purls_cms`, and `purls_301` from the posted values.

Saving replaces the PrestaShop product and category schemas. The form does not write `PS_ROUTE_supplier_rule`, `PS_ROUTE_manufacturer_rule`, `PS_ROUTE_cms_rule`, or `PS_ROUTE_cms_category_rule`. The success text is **Your settings have been updated.**

## Alerts on the settings form

These alerts are added when the matching removal switch is off (`0` or missing) and `strpos` of the keyword in the PrestaShop route is `== false`. In PHP that comparison is also true when the keyword is at position 0, so a schema that starts with `{id}` still raises the alert.

The check reads PrestaShop keys, not the `PURLS_ROUTE_*` fields:

- Product ID is `0`, and `PS_ROUTE_product_rule` has no `{id}`: "Your product rewrite url does not contain {id} variable. It is required when you do not want to remove ID from URL of product pages".
- Product ID is `0`, and `PS_ROUTE_product_rule` has no `{-:id_product_attribute}`: "Your product rewrite url does not contain {-:id_product_attribute} variable. It is required when you do not want to remove ID of product attribute from URL of product pages".
- Categories is `0`, and `PS_ROUTE_category_rule` has no `{id}`: "Your category rewrite url does not contain {id} variable. It is required when you do not want to remove ID from URL of category pages".
- Manufacturers is `0`, and `PS_ROUTE_manufacturer_rule` has no `{id}`: "Your manufacturer rewrite url does not contain {id} variable. It is required when you do not want to remove ID from URL of manufacturer pages".
- Suppliers is `0`, and `PS_ROUTE_supplier_rule` has no `{id}`: "Your supplier rewrite url does not contain {id} variable. It is required when you do not want to remove ID from URL of supplier pages".
- CMS is `0`, and `PS_ROUTE_cms_category_rule` has no `{id}`: "Your cms category rewrite url does not contain {id} variable. It is required when you do not want to remove ID from URL of supplier pages".
- CMS is `0`, and `PS_ROUTE_cms_rule` has no `{id}`: "Your cms rewrite url does not contain {id} variable. It is required when you do not want to remove ID from URL of supplier pages".

The last two English strings say "supplier pages". That is the text in the source.

## Possible collisions

![Possible collisions](https://mypresta.eu/docs/images/docs/purls-collisions.webp)

The panel **Possible collisions** is `views/purls.tpl`, rendered under the settings form. It lists duplicate `link_rewrite` values per active language for the current shop.

The info text **Add this url to your cron job table to automatically fix collisions** prints a front-office module link to controller `cron` with parameter `key` set to `Tools::hash('purls')`. This package does not contain `controllers/front/cron.php`. The class method `cronJob()` calls the same unique-rewrite routine for products and categories in every active language, and nothing in this package calls `cronJob()`.

**Product URLs** columns: **ID**, **Name**, **Link Rewrite**, **Occurance**, **Action**. For each language the menu **Fix all collisions** has **Fix all at once** and **Fix partially**. **Show products** reloads the page with `product_rewrite` and `id_lang` and lists the other products that share that rewrite. **No Collisions found** is shown when the list for that language is empty.

**Category URLs** has the same columns. The button is **Make rewrite fields unique**. **Show categories** adds `category_rewrite` to the request. The category query `getAllCategoryCollisionsRewrite()` receives an `id_lang` argument and then runs the SQL with the context language id, not with that argument.

**Fix all at once**, **Make rewrite fields unique**, and **Fix partially** call `makeUnique()`. For each duplicated rewrite, the first row keeps `link_rewrite`. Each following row is saved with that rewrite plus `-1`, `-2`, and so on, in the language of the button. `save()` runs for every row in the group, including the first. This changes `product_lang.link_rewrite` or `category_lang.link_rewrite`. Uninstall does not put the old rewrite back.

**Fix partially** sends one AJAX request per product row (`AjaxCollisions`, `id_lang`, `id_product`) and hides the row after the response. Each request runs `makeUnique('products', ...)` for that product's rewrite.

The product query groups by `link_rewrite` in `product_lang` for the current shop and language and keeps groups with count of at least 2. It does not filter by category. The category query does the same on `category_lang`.

## Routes, redirects, and the product hash

Custom matching in `Dispatcher::getController()` runs when PrestaShop friendly URLs are in use (`use_routes`), the controller is not already chosen, and the request is not in the back office. The override copies the original routes and also registers them again with the suffix `_original`.

These shop screens were taken after the save above. The shop language is English. The paths have no numeric id.

![Product path men/hummingbird-printed-t-shirt.html#/color-white/size-s. Size S and Color White are selected.](https://mypresta.eu/docs/images/docs/purls-front-product.webp)

![Category path clothes/men/. The page title is Men.](https://mypresta.eu/docs/images/docs/purls-front-category.webp)

![Brand path manufacturer/studio-design/. The heading is List of products by brand Studio Design.](https://mypresta.eu/docs/images/docs/purls-front-manufacturer.webp)

![CMS path info/delivery.html. The heading is Delivery.](https://mypresta.eu/docs/images/docs/purls-front-cms.webp)

When a switch is `1`, `Dispatcher::loadRoutes()` assigns these `default_routes` and then calls `parent::loadRoutes()`:

| Switch | Route id | Rule assigned in the override |
| --- | --- | --- |
| `purls_products` = `1` | `product_rule` | `{category:/}{rewrite}.html` |
| `purls_products` = `2` | `product_rule` | `{category:/}{id}-{rewrite}.html` |
| `purls_products` = `3` | `product_rule` | `{category:/}{id_product_attribute:-}{rewrite}.html` |
| `purls_categories` = `1` | `category_rule` | `{parent_categories:/}{rewrite}/` |
| `purls_suppliers` = `1` | `supplier_rule` and `supplier_rule_{id_lang}` | base `supplier/{rewrite}/`, language rule from `PURLS_ROUTE_supplier_rule` |
| `purls_manufacturers` = `1` | `manufacturer_rule` and `manufacturer_rule_{id_lang}` | base `manufacturer/{rewrite}/`, language rule from `PURLS_ROUTE_manufacturer_rule` |
| `purls_cms` = `1` | `cms_rule`, `cms_category_rule`, and the same with `_{id_lang}` | base `info/{rewrite}.html` and `info/{rewrite}`, language rules from `PURLS_ROUTE_cms_rule` and `PURLS_ROUTE_cms_category_rule` |

The other schemas for these fields are under Settings, in **Schemas for the route fields**. A saved product or category schema replaces the rule in this table.

`Link` builds the address only when the matching switch is on. Otherwise it calls the PrestaShop parent.

- Products (`purls_products` `1`, `2`, or `3`): `getProductLink()` uses route `product_rule`. Parameters that are not keywords of that route are omitted, so an id that is not in the schema is not added as a query parameter. `extraParams` that are not keywords are kept.
- Categories (`purls_categories` = `1`): `getCategoryLink()` uses `category_rule`. If the route has the keyword `parent_categories`, the path is built from parent categories, skipping ids 1, 2, and the category itself.
- Suppliers, manufacturers, CMS pages, and CMS categories use `supplier_rule_{id_lang}`, `manufacturer_rule_{id_lang}`, `cms_rule_{id_lang}`, and `cms_category_rule_{id_lang}`.

Lookup when the id is not in the URL:

- Products in modes `1` and `3`: the last path segment, without `.html`, is matched to `product_lang.link_rewrite`. If the path has a category segment, the default category `link_rewrite` is matched as well. If that finds nothing, a second query uses `link_rewrite` only. The result is written to `$_GET['id_product']`.
- Categories: the path is matched to `category_lang.link_rewrite`, with the parent segments when the path has more than one part. If that finds nothing, a second query uses `link_rewrite` in the current shop.
- CMS pages: `cms_lang.link_rewrite`, with `.html` removed.
- CMS categories: `cms_category_lang.link_rewrite`.
- Manufacturers and suppliers: `Tools::str2url()` of the **name**, not the `link_rewrite` column. The first path segment `supplier` is rejected by the manufacturer check. If several names produce the same slug, the last row in the loop wins.

`purls_301` = `1` sends `HTTP/1.1 301 Moved Permanently` in these cases only:

- Supplier route contains `id_supplier`, and suppliers removal is on: redirect to `getSupplierLink()`.
- Manufacturer route contains `id_manufacturer`, and manufacturers removal is on: redirect to `getManufacturerLink()`.
- CMS route contains `id_cms`: redirect to `getCmsLink()`. Contains `id_cms_category`: redirect to `getCmsCategoryLink()`. CMS removal must be on.
- Product mode `1`: the matched route contains `id_product` and `isProductLink()` returned false: redirect to `getProductLink()`. Modes `2` and `3` do not call that redirect.
- Categories removal is on, the matched route contains `id_category`, and `isCategoryLink()` returned false: redirect to `getCategoryLink()`.

Product mode `3`, when the match contains a non-empty `id_product_attribute`, calls `isProductLinkAttribute()`. That method sets `$_GET['id_product']` and `$_GET['id_product_attriubte']` (the key is spelled that way in the file). It does not set `id_product_attribute`.

On the product page, `displayHeader` adds `views/js/purls.js` only when the controller is `product`, the request is not AJAX, a product id is present, `purls_product_hash` is `0`, `purls_products` is `1` or `2`, and the product has combinations. The script receives `purls_attributes`: keys are `group-value` segments joined by `/`, values are `groupId|attributeId-group-value`. The separator is `PS_ATTRIBUTE_ANCHOR_SEPARATOR`, or `-` when that value is missing or empty. The script reads the hash, sets `select` or `radio` `group[groupId]`, and emits `prestashop.updateProduct` when a control changed.

`CartController::displayAjaxProductRefresh()` rebuilds the product URL and appends `idpa` with the combination id. `ProductController::init()` copies `idpa` into `id_product_attribute` when `id_product_attribute` is absent. `getIdProductAttributeByRequest()` reads `idpa` first.

If `pm_advancedsearch4` is installed, `hookModuleRoutes()` adds three routes that append `/filter-{id}/s-{id_search}/{as4_sq}` to the category, supplier, and manufacturer rules. If that module is not installed, the hook returns nothing.

## Hooks

`install()` registers these hooks and no others:

| Hook | Method | What it does |
| --- | --- | --- |
| `displayHeader` | `hookdisplayHeader` | On the product page, under the conditions above, adds `views/js/purls.js` and the `purls_attributes` map. |
| `ModuleRoutes` | `hookModuleRoutes` | Returns Advanced Search 4 routes when that module is installed. |
| `actionAdminControllerSetMedia` | `hookactionAdminControllerSetMedia` | Empty method. |

## Classes and replaced files

PrestaShop copies these files into the shop `override/` directory during install:

| File | Class | What the override changes |
| --- | --- | --- |
| `override/classes/Dispatcher.php` | `Dispatcher` extends `DispatcherCore` | `loadRoutes()`, `getController()`, and the lookup methods `isProductLink`, `isProductLinkAttribute`, `isCategoryLink`, `isCmsLink`, `isCmsCategoryLink`, `isManufacturerLink`, `isSupplierLink`. |
| `override/classes/Link.php` | `Link` extends `LinkCore` | `getProductLink`, `getCategoryLink`, `getSupplierLink`, `getManufacturerLink`, `getCMSLink`, `getCMSCategoryLink`, `getPaginationLink`, `getAnchor`. Drops route parameters that are not keywords of the compiled route. |
| `override/controllers/front/ProductController.php` | `ProductController` | Reads `idpa` in `init()`, `getIdProductAttributeByRequest()`, and `getIdProductAttribute()`. |
| `override/controllers/front/CartController.php` | `CartController` | `displayAjaxProductRefresh()` appends `idpa`. |
| `override/controllers/front/CmsController.php` | `CmsController` | When `purls_cms` is `1`, resolves `id_cms` / `id_cms_category` from `link_rewrite`. Also reads old `content/{id}-{rewrite}` and `content/category/{id}-{rewrite}` paths. |
| `override/controllers/front/listing/CategoryController.php` | `CategoryController` | When `purls_categories` is `1`, resolves `id_category` from `category_rewrite` and the path. |
| `override/controllers/front/listing/ManufacturerController.php` | `ManufacturerController` | When `purls_manufacturers` is `1`, resolves `id_manufacturer` from `Tools::str2url(name)`. |
| `override/controllers/front/listing/SupplierController.php` | `SupplierController` | When `purls_suppliers` is `1`, resolves `id_supplier` from `Tools::str2url(name)`. |
| `override/controllers/admin/AdminProductsController.php` | `AdminProductsController` | `getPreviewUrl()` only. Builds the product link in the shop default language, with combination id `0`, and `force_routes` equal to `PS_REWRITING_SETTINGS`. An inactive product gets query parameters `adtoken`, `ad`, and `id_employee`. |

There is no panel on the product form. There is no CSS file. The configuration markup is `views/purls.tpl` plus the PrestaShop helper form. The front script is `views/js/purls.js`. `purls.tpl` also contains the inline function `FixProductsCollisions`.

`Link::psversion()` and `ProductController::psversion()` split `_PS_VERSION_`. `getCategoryLink()` uses one meta title branch when the minor version is 6 or 7, or the major version is 8 or higher, and another branch otherwise. Comments in `Dispatcher.php` and `ProductController.php` name PrestaShop 9 and, for one private method, PrestaShop 1.7.

The module creates no SQL table. It reads and writes `configuration`, and it reads `product_lang`, `category_lang`, `cms_lang`, `cms_category_lang`, `manufacturer`, `supplier`, and the attribute tables while building the hash. Collision repair writes `link_rewrite` through `Product::save()` and `Category::save()`.

In the back office the constructor creates `override/controllers/front/listing` with mode `0777` when `override/controllers/front/` exists and `listing` does not.

## MyPresta updates

![MyPresta updates](https://mypresta.eu/docs/images/docs/purls-updates.webp)

The panel **MyPresta updates** sits between the settings form and the collisions panel.

| Label | Control |
| --- | --- |
| Check updates | Button **Check now** (`submit_settings_updates_now`). Prints **New version available!** or **Module is up to date!** |
| Updates notifications | Select `mypresta_updates`: **-- select --** (`-`), **Enable** (`1`), **Disable** (`0`). |
| Module page | Link on the product page. The address is in the support section. |
| Save | `submit_settings_updates` writes `mypresta_updates` only. |

On every back-office request the constructor calls `checkforupdates()`. When `update_purls` is missing or older than 259200 seconds, `purlsUpdate::verify()` requests `http://dev.mypresta.eu/update/get.php` if `allow_url_fopen` and `file_get_contents` are available. It stores the Unix time in `update_purls` and the response body in `updatev_purls`. The license value sent from this package is `nlc` (`$this->mkey`), unless a `key.php` file beside the module overrides it. This package does not contain `key.php`.

When `mypresta_updates` is not `0` and not false, and the stored remote version is higher than 3.0.0, and the request is not AJAX, the back office gets the warning **New version available, check http://MyPresta.eu for more informations** plus **More details in changelog**. Value `0` still runs the timed request and does not add that warning. A missing key is false, and false equals `0`, so a missing key takes the branch that does not add the warning.

## Install, disable, enable, uninstall

`install()` calls `parent::install()` and registers `displayHeader`, `ModuleRoutes`, and `actionAdminControllerSetMedia`. If any of those fail, install returns false. It does not insert configuration values and it does not create a table.

The file does not define `enable()` or `disable()`. Disabling the module in the back office does not run a method from this file. The override classes stay in the shop `override/` directory, because this module has no `disable()` that removes them. The three hooks are not executed while the module is disabled.

`uninstall()` returns `parent::uninstall()` only. That removes the module, unregisters its hooks, and removes the override copies PrestaShop installed. It does not delete configuration. It does not restore `PS_ROUTE_product_rule` or `PS_ROUTE_category_rule`. It does not restore `link_rewrite` values changed by the collision buttons. Keys left in place: `purls_products`, `purls_product_hash`, `purls_categories`, `purls_manufacturers`, `purls_suppliers`, `purls_cms`, `purls_301`, the four `PURLS_ROUTE_*` keys, `mypresta_updates`, `update_purls`, `updatev_purls`, and the two `PS_ROUTE_*` keys the form wrote.

## When a page does not resolve

- IDs are still present: Product ID is `0` or the key was never saved, or the product/category schema still contains `{id}`. Custom `getController()` matching runs only when friendly URLs (`use_routes`) are on.
- A clean URL returns the not-found controller: two products or categories share `link_rewrite`. The collisions panel lists those rows. The fix buttons change `link_rewrite` in the database.
- An old URL with an id is not redirected: `purls_301` is not `1`, or the page type is product mode `2` or `3` (those branches do not call `Tools::redirect`).
- Manufacturer or supplier URL opens the wrong record, or none: the match uses `Tools::str2url()` of the name.
- The module is disabled and URLs still go through this code: the overrides are still in `override/` until uninstall.
- After uninstall the product and category schemas are the values last saved by this form.

## Support

Product page: [https://mypresta.eu/modules/seo/pretty-clean-urls-pro.html](https://mypresta.eu/modules/seo/pretty-clean-urls-pro.html). The updates panel field **Module page** opens this address. The settings help also opens `https://mypresta.eu/documentation/pretty-clean-urls/configuration-and-module-usage/schema-of-urls-settings.html`.
