---
title: "Google Merchant Center Feed - merchant manual"
sidebar:
  label: "Google Merchant Center Feed - merchant manual"
description: "Configuration of the catalog feed, saved files and the catalog URL for a shop that already has the module."
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Google merchant center feed Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/google-merchant-center-feed/)
>
> ---


The module technical name is `gmfeed`, version 2.4.3. In this language the module list shows **Google Merchant Center Feed**. That name is written in the module file and is not taken from `translations/en.php`.

## 1. Where the screens are

There are two screens.

Modules, then Module Manager, then **Google Merchant Center Feed**, then Configure. That page has one field, **Show categories tree**.

Catalog, then **Google Merchant Feed**. That page is the controller `AdminExportProductsFeedGoogle`. Its heading is **Google Merchant Center feeds**. The tabs are **Dashboard**, **Feeds**, **Updates**, and **Create / Edit feed**. **Create / Edit feed** stays disabled until you open **Create new feed** or an existing feed.

There is no import screen and no block on the product edit page. The storefront does not draw a box. The public effect is the catalog URL of a saved feed.

## 2. What install writes

Install runs the parent install, registers `actionAdminControllerSetMedia`, creates a tab under Catalog, and creates the tables below.

The tab class is `AdminExportProductsFeedGoogle`. The label passed at install is **Google Merchant Feed**. The same label is written for every shop language that exists at install time.

`actionAdminControllerSetMedia` loads the fancybox and autocomplete plugins only when the controller is `AdminExportProductsFeedGoogle`.

The class has no `enable()` and no `disable()`.

## 3. Module settings

![Module settings](https://mypresta.eu/docs/images/docs/gmfeed-settings.webp)

The legend is **Module settings**. The button is **Save**. The only field is **Show categories tree** (`pf_tree`). **No** is 0. **Yes** is 1. When the key is missing, `(int)Configuration::get('pf_tree')` is 0, so the select matches **No**.

**Save** posts `submitgmfeedSettings` and writes `pf_tree`. The success text is **Settings saved properly**.

**Yes** makes the category pairing list on the feed form show parent categories. The description links to `https://i.imgur.com/enzXRaJ.png`. The same description links to **Catalog > Google Merchant Feed**.

This page does not build the catalog file.

## 4. Catalog page

![Dashboard](https://mypresta.eu/docs/images/docs/gmfeed-dashboard.webp)

![Feeds](https://mypresta.eu/docs/images/docs/gmfeed-feeds.webp)

Open **Catalog > Google Merchant Feed**.

**Dashboard** shows **Saved feeds**, **Cron runs today**, **Runs last 7 days** and **Saved files**. The numbers come from `gms` and `gms_log`. When no URL has been called, the page shows **No cron or URL generations yet. Save a feed, then call its catalog URL from a scheduler.**

**Feeds** lists rows from `gms`, newest `id_gms` first. **Create new feed** opens the form. Duplicate copies the saved query string, drops `export_id_gms`, `id_gms` and `gmfeed_write_key`, and appends ` (copy)` to the name. If the name is empty, the copy starts from **Untitled feed**. The success text is **Feed duplicated. Review the copy and save if you need a different filename or URL.** Remove deletes that `gms` row. The success text is **Feed removed.** The saved file on disk is not deleted by that action.

![Updates](https://mypresta.eu/docs/images/docs/gmfeed-updates.webp)

**Updates** is the update form from `lib/updateChecker.php`. **Check now** posts `submit_settings_updates_now`. **Save** posts `submit_settings_updates` and writes `mypresta_updates`. The constructor asks the remote server when `mypresta_updates` is not 0 and `update_gmfeed` is older than 172800 seconds. The license value sent when `mkey` is missing is `nokey`. A warning is shown when `updatev_gmfeed` is higher than 2.4.3 and the request is not ajax.

## 5. Feed form

![Create feed](https://mypresta.eu/docs/images/docs/gmfeed-form.webp)

The shot shows the top of the form. The rest of the fields continue below it.

**Create feed** and **Edit feed** use the same form. The feed name is required. **Active** **Yes** / **No** is stored on `gms.active`. A new feed is active. **Shop** stores `gms.id_shop`. The other fields are stored in `gms.conf` as a query string.

A missing key on a new form uses the default below. While you edit a feed, a missing key uses that same default and does not read the shared `gm_` configuration.

| Key | Default on a new form | What the code does with it |
|---|---|---|
| `export_file_format` | `csv` | `csv` or `xml`. Any other extension is forced back to `csv` by `sanitizeExportExtension`. |
| `export_type` | `product` | `sanitizeExportType` keeps only `products` and `combinations`. The stored default `product` is therefore treated as `products`. |
| `export_save_file` | `0` | `0` streams the catalog in the response. `1` writes a file under `/modules/gmfeed/`. |
| `export_filename` | empty | Used only when save-to-file is on. Empty becomes the export type. Characters other than letters, digits, `_` and `-` are removed. |
| `export_identification` | `id_product` | Product id written as the catalog id. |
| `export_delimiter` | vertical bar | Separator between CSV columns. |
| `export_enclosure` | `0` | Enclosure value passed to the CSV writer. |
| `export_language` | `PS_LANG_DEFAULT` | Language of names and descriptions. |
| `export_currency` | `PS_CURRENCY_DEFAULT` | Currency of prices. |
| `export_tax` | `price_tin` | Which price column is filled. |
| `export_specific` | `1` | When the shop default currency differs from the context currency, a non-zero value makes the price step use specific prices. |
| `export_category` | `all` | Categories included in the catalog. |
| `export_manufacturers` | `all` | Manufacturers included. |
| `export_manufacturers_default` | `Default` | Brand text when the product has none. |
| `export_suppliers` | `all` | Suppliers included. |
| `export_gtin` | `upc` | Which product code is written as GTIN. |
| `export_img` | `1` | Image type passed to `getImageLink`. The select lists image type names. |
| `export_what_pictures` | `0` | `0` removes the additional image column. |
| `export_active` | false | Passed to `Product::getProducts` as the active-only flag. `0` is **Export all products.** `1` is **Export only active products**. |
| `export_instock` | false | `1` skips a row when quantity is 0 or less. `0` is **Export all products.** `1` is **Export only in-stock products**. |
| `export_igid` | `0` | `0` removes `item_group_id`. |
| `export_gender` | `0` | `0` removes the gender column. |
| `export_age_group` | `0` | `0` removes the age group column. |
| `export_size` | `0` | `0` removes the size column. |
| `export_color` | `0` | `0` removes the color column. |
| `export_shipping_info` | `0` | `0` is **Do not include**. |
| `export_product_weight` | `0` | Weight stays off until this is set. |
| `export_product_type` | `0` | Product type stays off until this is set. |
| `export_removehtml` | `0` | A value other than `0` strips HTML from the description. |
| `export_nophoto_exclude` | `0` | `1` drops a product that has no photo. |
| `export_adult` | `0` | Adult stays off until this is set. |
| `export_storecode` | `0` | `0` removes the store code column. |
| `export_country_prices` | `PS_COUNTRY_DEFAULT` | Country used for the price. |
| `export_group_prices` | `PS_UNIDENTIFIED_GROUP` | Customer group used for the price. |
| `remember_settings` | true | When the posted value is `1`, the same save also writes `gm_{key}` into Configuration. The write key, shop, feed id and active flag are skipped. |
| `feed_active` | on for a new feed | `gms.active`. `0` makes the URL return HTTP 503 and the text `Feed is disabled`. |

**Save to file** describes the directory `modules/gmfeed/` and states that writing the file from the URL requires the secret key shown on this form. The key is `gmfeed_write_key`, an HMAC of `gmfeed.write.` plus the shop id, using `_COOKIE_KEY_`. A logged-in employee can write the file without that key. Anyone else gets `Access denied`.

The success text after save is **Feed saved. Its catalog URL is ready to use.**

## 6. Catalog URL and file

The catalog URL is the module front controller `feed`, plus `?feed=` and the `gms` id. `gms::getFeedUrl` also appends `gmfeed_write_key` when it builds the link for the back office.

Opening that URL loads the saved query string and replaces `export_` and `gmfeed_` values from the request, except the write key and `debug_feed`. A missing feed, or a `conf` shorter than or equal to 20 characters, stops with `feed does not exists`. A feed whose `id_shop` is set and is not the current shop stops with `Feed is not available in this store`.

`debug_feed` prints the stored parameters and does not write the file.

The file name is the sanitized `export_filename` plus `.csv`, `.xml` or `.txt`. The path must stay inside `/modules/gmfeed/`. `.htaccess` in that directory denies direct execution of PHP files. `index.php` stays allowed. The catalog itself is served by the front controller, not by opening the PHP files.

Each run inserts `gms_log`: time, duration, item count, status, whether a file was saved, file name, format, and source `url`.

## 7. Google categories

The feed form lists taxonomy files from `/modules/gmfeed/google/`. A shop language is marked present when `google/{language_code}.txt` exists. This package contains `google/en-us.txt`. The first line of that file is `# Google_Product_Taxonomy_Version: 2015-02-19`.

Pairing a shop category writes `pixelgoogle`: `id_google`, `id_category`, `id_lang`, `value`. **Show categories tree** only changes how that list is drawn.

## 8. Tables

Install creates three tables when they are missing. The shop prefix is in front of each name.

| Table | What the CREATE statement writes |
|---|---|---|
| `pixelgoogle` | `id_pixelgoogle` auto increment, primary key, `id_google`, `id_category`, `id_lang`, `value` varchar 254. Charset `utf8`. |
| `gms` | `id_gms` auto increment, `name`, `id_shop` default 0, `conf` text, `active` default 1. Keys `idtoskey` and `id_shop`. The CREATE statement has no primary key. |
| `gms_log` | `id_gms_log` auto increment, primary key, `id_gms`, `date_add`, `duration_ms`, `items`, `status` default `ok`, `save_file`, `file_name`, `format`, `source` default `url`. |

Opening the catalog page runs `gms::ensureSchema()`. That adds `gms.active` and `gms.id_shop` when they are missing, creates `gms_log` when the table is missing, and fills `id_shop` 0 with `PS_SHOP_DEFAULT`.

Shared configuration that is not a column: `pf_tree`, `gm_{field}` when the form writes it outside a feed, `mypresta_updates`, `update_gmfeed`, `updatev_gmfeed`.

Assets on the catalog page: `views/css/admin-app.css`, `views/js/admin-app.js`, fancybox, autocomplete. The module configure page loads fancybox. The ID search script comes from `lib/searchTool/`.

## 9. Uninstall

`uninstall()` deletes the Catalog tab `AdminExportProductsFeedGoogle` and then runs the parent uninstall. The parent removes the module and the hook registration.

The method does not drop `pixelgoogle`, `gms` or `gms_log`. It does not delete `pf_tree`, `mypresta_updates`, `update_gmfeed`, `updatev_gmfeed` or `gm_` keys. It does not delete files written under `/modules/gmfeed/`. A later install uses `CREATE TABLE IF NOT EXISTS`, so rows left in the tables remain.

## 10. Support

Module page: [Google Merchant Center Feed](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html).
