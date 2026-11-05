---
title: "Microsoft Merchant Center Product Feed - documentation and user manual"
description: "A user manual for people who already have the module and need to configure Microsoft Merchant Center feeds or fix feed generation and catalog problems."
sidebar:
  label: "Microsoft Merchant Center Product Feed - documentation and user manual"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Microsoft Merchant Center Product Feed Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/microsoft-merchant-center-product-feed.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/microsoft-merchant-center-product-feed/)
>
> ---


## 1. Requirements

Before installing the module, make sure the shop and hosting meet these requirements:

- PrestaShop 1.7, 8, or 9.
- PHP 7.1 through 8.5.
- PHP extensions: cURL, JSON, hash, and SimpleXML when you generate XML feeds.
- An active Microsoft Merchant Center account in which you can create a catalog and provide its feed address.
- No other PrestaShop module is required.

A large catalog needs enough PHP execution time and memory to collect products, calculate prices and shipping, and build the output. If one full feed exceeds your hosting limits, use **Limit number of products in feed** together with **Part of feed** to divide it into smaller feeds.

## 2. Installation

1. Open **Modules → Module Manager**.
2. Click **Upload a module** and upload the module ZIP file.
3. Install **Microsoft Merchant Center Feed**.
4. Open **Catalog → Microsoft Merchant Feed**. This is the workspace for creating feeds, copying catalog addresses, monitoring runs, and pairing categories.
5. If category names are repeated in different branches of your catalog, open **Modules → Module Manager**, find the module, click **Configure**, and enable **Show categories tree**.

Installation does not clear the PrestaShop cache.

To remove the module, uninstall it in **Module Manager**. Uninstallation removes **Microsoft Merchant Feed** from the **Catalog** menu, but it keeps saved feeds, generation history, category pairings, remembered form settings, generated catalog files, and downloaded taxonomy data. Reinstalling the module can therefore reuse the retained data.

## 3. Configuration and back-office workflow

Use this process to publish a catalog:

1. Open **Catalog → Microsoft Merchant Feed** and select **Create new feed**.
2. Enter a **Feed name**, leave **Active** set to **Yes**, select the output and product options, pair **Microsoft Categories**, and click **Save feed**.
3. Choose one publication method:
   - For a live feed, leave **Save to file** set to **No**. Copy the **Live catalog URL**. Microsoft requests this address and the module regenerates the feed on every request.
   - For a static file, set **Save to file** to **Yes**. Call the secret **Generate / cron URL** manually or from a scheduler. After the first successful generation, copy the **Catalog file URL**. Give Microsoft Merchant Center the catalog file address, never the generate address.
4. Create or open the relevant catalog in Microsoft Merchant Center and paste the copied live or catalog file address into its feed source.
5. Return to **Dashboard** to confirm that runs are recorded and that a saved file is ready when file mode is used.
6. Open the feed's **Microsoft Categories** section, synchronize the taxonomy for the feed language, and use **Pair categories** to connect shop categories with Microsoft shopping categories.
7. To pause publication without changing the address, turn the feed off in **Feeds**. Turning **Active** off stops generation; turning it on resumes the same feed at the same address.

Screenshots in this manual come from an English back office.

### 3.1 Module settings

Open **Modules → Module Manager**, find **Microsoft Merchant Center Feed**, and click **Configure**.

![Module settings with Show categories tree](https://mypresta.eu/docs/images/docs/mmcfeed-module-settings.webp)

| Field | On start | What it does |
|---|---|---|
| **Show categories tree** | No | The feed workspace is under **Catalog → Microsoft Merchant Feed**. There you can pair shop categories with Microsoft Shopping categories. Set this field to **Yes** to show each category's parent path in the pairing window. Parent paths make categories with identical names easier to distinguish. Click **Save**; the page confirms **Settings saved properly**. |

### 3.2 Feeds list

Open **Catalog → Microsoft Merchant Feed**, then select **Feeds**.

![Feeds list](https://mypresta.eu/docs/images/docs/mmcfeed-feeds.webp)

If no feed exists, the page shows **You have no feeds yet** and **Create your first feed**. Otherwise, use these columns:

| Column | What it shows |
|---|---|
| **Status** | **On** or **Off**. Use the switch to pause or resume the feed without deleting it or changing its address. |
| **Feed** | Feed name plus badges for file format, product or variant export, language, and **Live** or **File** mode. |
| **Shop** | The shop to which the feed belongs. In multistore, a feed outside the current shop is marked **Not available in this store**. |
| **Last run** | Number of generated items and the last run time. Before the first call it shows **Never** and **No cron call yet**. |
| **Catalog URL** | In live mode, the **Live catalog** address. In file mode, the secret **Generate / cron** address and the public **Catalog file** address. Copy the address with the adjacent copy button. |
| **Actions** | The commands available for the feed. |

Use the actions as follows:

- **Edit** opens all saved options.
- **Duplicate** creates a copy and opens it for review. Change its name, filename, shop, filters, or other settings before saving when the copy must be independent.
- **Generate** calls the generator in file mode.
- **Open file** opens the saved file in file mode.
- **Open** generates and opens a live feed.
- **Delete** permanently removes the feed record after confirmation.

After an operation, the page can show:

- **Feed saved. Its catalog URL is ready to use.**
- **Feed removed.**
- **Feed duplicated. Review the copy and save if you need a different filename or URL.**

### 3.3 Dashboard

Select **Dashboard** to monitor feed activity.

![Dashboard](https://mypresta.eu/docs/images/docs/mmcfeed-dashboard.webp)

The summary shows **Saved feeds**, successful **Cron runs today**, products generated today, **Runs last 7 days**, average generation duration, and the number of **Saved files** that are ready. **Catalog generation activity** charts the last 14 days. **Recent runs** lists the latest feed, time, item count, duration, format, and whether a file was written.

The **Generated files** table lists each file-mode feed with its shop, filename, size, state, and last update. **Waiting for first cron** means the feed is saved but the generate address has not yet produced its file. **On disk** means the file is available at its catalog file address.

### 3.4 Updates tab

Select **Updates** to check the installed module against MyPresta updates.

![Updates tab](https://mypresta.eu/docs/images/docs/mmcfeed-updates.webp)

| Field | On start | What it does |
|---|---|---|
| **Manual Check** | No result until checked | Click **Check Now** after installation or when you expect a new release. The module contacts the update service once, compares versions, and immediately reports **Module is up to date!** or **New version available!** |
| **Automatic Notifications** | Current shared MyPresta update preference | Set **Enabled** to check in the back office about every three days and show employees a warning when a newer version exists. Set **Disabled** if you manage checks manually. Click **Save** to apply the choice. |
| **Product Page** | Link available | Open the official module page to reach its module information and support resources. No setting is required. |

### 3.5 Create / Edit feed

Select **Create new feed**, or click **Edit** beside an existing feed. Fields appear in the following on-screen order. Options described as shop-dependent come from the languages, currencies, countries, groups, image types, features, attributes, categories, manufacturers, suppliers, zones, and shops configured in PrestaShop.

Click **Save feed** to save and return to the list. Click **Save & download** to save the settings and immediately download a newly generated CSV or XML file. When editing, the page also shows the relevant **Live catalog URL**, or the **Generate / cron URL** and **Catalog file URL**.

![Create or edit feed: name, status, format, type, and file mode](https://mypresta.eu/docs/images/docs/mmcfeed-form-top.webp)

**Feed identity and output**

| Field | On start | What it does |
|---|---|---|
| **Feed name** | Blank | Enter a required, recognizable name used on the feeds list. If an empty submission reaches saving, it is stored as **Untitled feed**. |
| **Active** | Yes | Leave enabled to allow generation. Set to **No** to pause the feed while retaining its address and settings. |
| **Shop** | Current shop; shown in multistore only | Assign the feed to one shop. Its catalog address works only for that shop. |
| **Remember settings** | Yes | Save the form choices as starting values for the next new feed. Set to **No** when this feed's choices must not become the remembered defaults. |
| **Type of file module will generate** | CSV | Choose **CSV** for a text feed or **XML** for an Atom shopping feed. For TSV, choose **CSV** and set **Delimiter** to `Tab`; TSV is CSV output with a tab separator. |
| **What you want to export?** | Products | Choose **Products** for one row per product or **All products variants** to export combinations separately. |
| **Save to file** | No | **No** makes the feed live and returns it whenever its catalog address is called. **Yes** makes the generate address write a static file; schedule that secret address, then submit the separate catalog file address to Microsoft. |
| **File name** | Blank | When **Save to file** is enabled, enter the base name of the static feed file. If blank, the module uses the export type. Use letters, numbers, hyphens, or underscores for a predictable name. |
| **How to identify product?** | `id_product` | Choose `id_product`, `id_combination`, or `id_product-id_attribute`. This value becomes the unique item ID in the feed. Use a combination-aware choice when variants are exported separately. |

**Size, gender, color, and age group**

![Size, gender, color, and age fields](https://mypresta.eu/docs/images/docs/mmcfeed-form-attributes.webp)

| Field | On start | What it does |
|---|---|---|
| **Export size** | No | Set to **Yes** to include the `size` field. |
| **Size attribute** | None | Select the product attribute group that contains size. Hold Ctrl while clicking to select multiple groups. Products without a selected size value use **Default size value**. |
| **Default size value** | Blank | Enter the fallback size used when a product has no value in the selected size attribute group. |
| **Export gender** | No | Set to **Yes** to include the `gender` field. |
| **Export gender value from** | No source selected | Choose **Attribute** or **Feature** as the source of gender data. Complete the matching source field below. |
| **Gender feature** | No feature selected | When the source is **Feature**, select the product feature that stores gender. |
| **Gender attribute** | No attribute selected | When the source is **Attribute**, select the product attribute group that stores gender. |
| **Default gender value** | Blank | Choose **Male**, **Female**, or **Unisex** as the fallback when a product does not provide a gender value through the selected source. |
| **Export color** | No | Set to **Yes** to include the `color` field. |
| **Export color value from** | No source selected | Choose **Attribute** or **Feature** as the source of color data. |
| **Color attribute** | No attribute selected | When the source is **Attribute**, select the product attribute group that stores color. |
| **Color feature** | No feature selected | When the source is **Feature**, select the product feature that stores color. |
| **Default color value** | Blank | Enter the fallback when the selected color source is empty. Use English color names because Microsoft accepts English names for this field. |
| **Export age_group** | No | Set to **Yes** to include the `age_group` field. |
| **Export age group value from** | No source selected | Choose **Attribute** or **Feature** as the source of age-group data. |
| **age group feature** | No feature selected | When the source is **Feature**, select the product feature that stores age group. |
| **age group attribute** | No attribute selected | When the source is **Attribute**, select the product attribute group that stores age group. |
| **Default age group value** | No fallback selected | Choose the fallback used when a product has no source value: **adult**, **kids**, **toddler**, **infant**, or the on-screen **newbord** value. Match Microsoft's accepted age-group values when preparing production data. |

**Feed fields, shipping, text, stock, images, and prices**

![Feed settings including identifiers, shipping, descriptions, language, and delimiter](https://mypresta.eu/docs/images/docs/mmcfeed-form-feed-settings.webp)

| Field | On start | What it does |
|---|---|---|
| **Include item_group_id** | No | Set to **Yes** to group variants that differ by details such as size, color, pattern, age group, or gender. This lets Microsoft treat them as variants of one product rather than unrelated offers. |
| **Unique product identifier** | Product UPC barcode | Choose the product field used for GTIN or identifier data: **Product UPC barcode**, **Product ean13 / JAN barcode**, **Product reference number**, **Product MPN code**, **Product ISBN code**, or **Make this field empty, identifier_exists field will have value false then**. Supply manufacturer-assigned identifiers whenever available; they improve product matching and listing quality. |
| **Include identifier_exists field** | No | Set to **Yes** to add `identifier_exists`. It tells Microsoft whether an item has a unique product identifier. |
| **Include adult field** | Do not include | Choose **Include as true** for age-restricted adult products, **Include as false** to send an explicit false value, or **- do not include -** to omit the field. The form also displays an unrelated fourth label, **Lowercase all letters, example: product name**; do not use it for this field. |
| **Include shipping price** | Do not include | Choose **Do not include**, **Include (shipping price calculated for each item separately)**, or **Set shipping price manually**. Automatic calculation is product-specific; manual mode applies one entered amount. |
| **Include product's additional shipping cost** | No | Set to **Yes** to add each product's own additional shipping fee to the exported delivery price. |
| **Manual shipping value** | 0 | When manual shipping is selected, enter the shipping amount applied to each item. |
| **Automatic shipping price zone select** | Initial shop zone | When automatic shipping is selected, choose the destination zone used for calculation. Per-item calculation consumes more hosting resources than a flat manual value. |
| **Include weight** | No | Set to **Yes** to include product shipping weight with the shop's weight unit. |
| **Product type** | No | Set to **Yes** to include the shop's own category structure as `product_type`. |
| **Product type - include category ID** | No | When **Product type** is enabled, set this to **Yes** to append the category ID and distinguish categories that share a name. |
| **Short description** | Short description | Choose whether the feed's description value comes from **Short description** or **Long description**. |
| **Remove html from descriptions** | Yes | Microsoft requires plain text. HTML tags and disruptive line breaks are removed from feed descriptions even if **No** is selected, so keep this set to **Yes** as an accurate reminder of the resulting output. |
| **Product name** | Product name | Choose **Product name** or **Meta title** as the feed title source. |
| **Format name** | Do not format name | Leave unchanged, capitalize only the first letter, capitalize each word, or lowercase all letters. Use formatting when catalog titles contain all-capital text that Microsoft does not accept. |
| **Remove selected characters from product name** | Blank | Enter each character to remove from titles, for example `x=,` removes `x`, `=`, and `,`. Leave the field truly empty, without a space, to remove nothing. |
| **Language** | Shop default language | Choose the language used for product titles, descriptions, and other translated catalog data. |
| **Delimiter** | `|` | Set the separator for CSV output. Enter `Tab` for TSV, which is recommended by Microsoft Merchant Center. Pipe and comma can also be used for CSV. This setting does not change XML. |
| **Wrap strings in double quotes** | Yes | Keep enabled so text containing separators or special characters does not break CSV rows. |
| **Information about stock** | Include real stock information | Use actual availability, or force all exported products to **in-stock**, **out-of-stock**, or **backorder**. The final option reports products with enabled backorders as in stock instead of backorder. |
| **Availability date** | Blank | Enter a fallback date for backorder products that have no individual availability date. Microsoft requires this date for backorder offers. |
| **Include quantity info** | No | Set to **Yes** to include an inventory column containing the product or combination quantity. |
| **Default manufacturer value** | `Default` | Enter the brand fallback used when a product has no associated manufacturer. |
| **Image size for product pictures** | Store-dependent initial image type | Choose the PrestaShop image type used to build product image addresses. |
| **Use default product picture if combination will not have associated photo** | No | Set to **Yes** to use the main product image when an exported combination has no assigned image. |
| **How many pictures you want to export?** | Export cover only | Choose **Export cover only** or **Export all pictures**. All pictures adds additional image links. |
| **Currency** | Shop default currency | Choose the currency used for exported prices. Match the catalog's target market in Microsoft Merchant Center. |
| **Price tax included or excluded** | Price Tax Included | Choose whether regular and sale prices include or exclude tax. |
| **Include specific prices** | Yes | Keep enabled when PrestaShop specific prices define prices for currencies or other contexts that must be reflected in the feed. |
| **Export prices for selected group** | Shop's unidentified customer group | Select the customer group whose price context the module uses. |
| **Export also unit price** | No | Set to **Yes** to include unit pricing measure information in variant feeds where it is available. |
| **Export prices for selected country** | Shop default country | Choose the country context for tax and country-dependent discounts used in price calculation. |

**Product selection, exclusions, limits, local inventory, and category pairing**

![Filters, limits, store code, and Microsoft Categories](https://mypresta.eu/docs/images/docs/mmcfeed-form-filters.webp)

| Field | On start | What it does |
|---|---|---|
| **Product Manufacturer** | All | Export all manufacturers or only products from the selected manufacturer. |
| **Product Supplier** | All | Export all suppliers or only products from the selected supplier. |
| **Product Category** | All | Export all categories or limit the feed to the selected category. |
| **Exclude categories** | Blank | Search for categories and add them to the exclusion list. Products assigned to a selected excluded category are omitted. |
| **Exclude products without pictures** | No | Set to **Yes** to omit products that do not have a usable image. |
| **Products's availability** | Export all products | Choose **Export only active products** to omit disabled catalog products. |
| **Products's stock** | Export all products | Choose **Export only in-stock products** to omit products without stock. |
| **Exclude products with specific reference** | No | Set to **Yes** to enable reference-prefix filtering. |
| **Exclude product where reference starts with:** | Blank | Enter the prefix to omit. It applies to products and combinations whose references start with that text. |
| **Exclude products worth less than defined value** | No | Set to **Yes** to omit products below a minimum value measured in the shop's default currency. |
| **Value of products (worth less) to exclude** | Blank | Enter the minimum value used by the preceding filter. Products priced below it are omitted. |
| **Exclude products** | Empty list | Start typing a product name and select it to add that product to the exclusion list. Use **Add all search results** to exclude every result of the current search; remove an item with its remove button. |
| **Limit number of products in feed** | 0 | Enter the maximum number of products in this feed. Leave blank or enter `0` for no limit. Use a limit when a large catalog exceeds available execution time or memory. |
| **Part of feed** | 0 | Enter `0` when the feed is not split. For split feeds, create separate feeds with the same limit and consecutive parts. For 3,000 products and a limit of 1,000, use parts 1, 2, and 3. |
| **Include store code to feed** | No | Set to **Yes** for a local inventory feed that must identify a physical store. Use the same identifier configured in your Microsoft business account. |
| **Store code** | Blank | Enter the exact, case-sensitive alphanumeric store identifier used by Microsoft. |
| **Microsoft Categories** | Taxonomy not guaranteed to be synchronized | For each language, check the file state. Click **Synchronize**, or choose a source under **Synchronize specific** when the normal source does not cover that language. Then click **Pair categories**, search for the appropriate Microsoft category beside each shop category, and save the pairing. The repeat icon applies one category value to all fields; the delete icon removes a pairing. |

## 4. Storefront and feed addresses

The module adds no block, button, product-page content, customer form, account page, or other storefront interface. Customers do not interact with it.

External services use the catalog address copied from **Feeds**:

- **Live catalog URL** regenerates and returns the catalog on every request. Nothing is saved as a static file.
- **Generate / cron URL** contains the secret needed to write a static file. Call it from a scheduler or use **Generate**. Do not give it to Microsoft Merchant Center.
- **Catalog file URL** points to the static file produced by the generate address. Use this address as the Microsoft Merchant Center feed source when **Save to file** is enabled.

Opening an unavailable address can show:

| What you see | What to do |
|---|---|
| **Feed is disabled** | Open **Feeds** and turn the feed status to **On**, or edit it and set **Active** to **Yes**. |
| **feed does not exists** | Copy the current address again from **Feeds**. The saved feed was deleted, the address is incomplete, or the saved configuration is invalid. |
| **Feed is not available in this store** | Switch to the shop assigned to the feed, edit the feed's **Shop**, and copy the address generated for that shop. |
| **Access denied** | In file mode, use the complete **Generate / cron URL** copied from the feed page. Do not remove or edit its secret part. |

## 5. Problems and solutions

### 5.1 The feed reports that it is disabled

**Symptom:** Opening the address shows **Feed is disabled**.

**Cause:** The status switch is off or **Active** is set to **No**.

**Action:** Open **Catalog → Microsoft Merchant Feed → Feeds** and switch the feed to **On**. Its existing address remains valid.

### 5.2 The feed does not exist

**Symptom:** Opening the address shows **feed does not exists**.

**Cause:** The address points to a deleted feed, is incomplete, or the saved feed has no usable configuration.

**Action:** Open **Feeds** and copy the address again. If the feed is absent, create and save it again.

### 5.3 The feed belongs to another shop

**Symptom:** The list says **Not available in this store**, or the address shows **Feed is not available in this store**.

**Cause:** The feed is assigned to a different shop in multistore.

**Action:** Switch the back office to the assigned shop, or edit **Shop**, save, and copy the resulting address.

### 5.4 A file-mode generation says access is denied

**Symptom:** Calling a file generator shows **Access denied**, and no file is updated.

**Cause:** The address is missing the secret write authorization included by the module.

**Action:** Copy **Generate / cron URL** again from **Feeds** or the edit page and use it unchanged in the scheduler. Keep this address private.

### 5.5 Microsoft receives the generator response instead of a stable file

**Symptom:** Scheduled retrieval in Microsoft fails or unexpectedly starts generation on every request even though **Save to file** is enabled.

**Cause:** The **Generate / cron URL** was pasted into Microsoft Merchant Center.

**Action:** Use the generate address only in your scheduler. Run it once, confirm **On disk** on **Dashboard**, and paste **Catalog file URL** into Microsoft Merchant Center.

### 5.6 The feed is empty or products are missing

**Symptom:** Generation succeeds but returns no items or fewer items than expected.

**Cause:** Manufacturer, supplier, category, excluded category, excluded product, image, active status, stock, reference-prefix, minimum-value, limit, or part settings remove the products.

**Action:** Edit the feed and review all fields under product selection and exclusions. Temporarily choose **All**, disable exclusion switches, clear exclusion lists, and set the limit and part to `0`. Save and generate again, then reintroduce filters one at a time.

### 5.7 Microsoft categories are missing

**Symptom:** The feed has no useful Microsoft category values or **Pair categories** cannot search the taxonomy.

**Cause:** The taxonomy for the selected language is not synchronized, or shop categories are not paired.

**Action:** Edit the feed, scroll to **Microsoft Categories**, and click **Synchronize** for the language. If that source is unavailable, choose a source under **Synchronize specific**. When the file is reported as available, click **Pair categories** and complete the mappings.

### 5.8 A large catalog times out or exhausts memory

**Symptom:** Generation stops, takes too long, or the saved file is not updated.

**Cause:** The hosting account cannot process the whole catalog, price context, images, and automatic shipping calculations in one run.

**Action:** Enter a practical **Limit number of products in feed** and create separate feeds with consecutive **Part of feed** values. Prefer a manual flat shipping amount over per-item automatic shipping when appropriate, and schedule parts separately.

### 5.9 Microsoft reports data-quality issues

**Symptom:** Microsoft Merchant Center warns about identifiers, descriptions, prices, availability, images, variants, age groups, gender, colors, or shipping.

**Cause:** The selected source fields are empty, use an unsupported value, or do not match the Microsoft catalog market.

**Action:** Open the affected feed and match **Language**, **Currency**, country and tax context to the Microsoft catalog. Supply valid GTIN data, brand fallback, plain-text descriptions, current availability, suitable images, and category pairs. For apparel, verify **size**, **gender**, **color**, **age_group**, and **item_group_id**. Regenerate the feed and review diagnostics again in Microsoft Merchant Center.

## 6. Developer reference

### 6.1 Module overview

| Item | Value |
|---|---|
| Technical name | `mmcfeed` |
| Version | `1.1.0` |
| Display name | `Microsoft Merchant Center Feed` |
| Author | `MyPresta.eu` |
| Module tab | `administration` |
| Back-office tab | `AdminExportProductsFeedMicrosoft`, installed under `AdminCatalog` |
| Front endpoint | `controllers/front/feed.php` |

`mmcfeed` extends `Module`. Feed definitions are stored by the `mmc` ObjectModel as a name, shop, active flag, and serialized query-string configuration. Both immediate back-office downloads and front-controller calls build CSV or XML from PrestaShop product data. File mode writes a sanitized filename in the module directory; live mode streams the response.

### 6.2 Important files and classes

| File | Responsibility |
|---|---|
| `mmcfeed.php` | Module metadata, install and uninstall, global configuration form, sanitization helpers, safe file paths, and HMAC write-token validation. |
| `controllers/admin/AdminExportProductsFeedMicrosoft.php` | Dashboard, feeds list, create/edit form, duplication, deletion, category synchronization and pairing, immediate exports, and form-default persistence. |
| `controllers/front/feed.php` | Loads a saved feed, validates active state and shop ownership, applies stored options, streams live output, or writes a static file. |
| `model/mmc.php` | `mmc` ObjectModel, schema migration, feed URL construction, list enrichment, run logging, dashboard statistics, and generated-file metadata. |
| `model/categorymap.php` | Defines the `pixelgoogle` ObjectModel used for category mappings. |
| `model/google.php` | Duplicates the same `pixelgoogle` class definition and methods as `model/categorymap.php`; loading both definitions in one request would cause a class redeclaration. |
| `lib/updateChecker.php` | `mmcfeedUpdate`, update checks, shared notification preference, and the Updates form. |
| `lib/searchTool/searchTool.php` | Product and category autocomplete used by exclusion fields. |
| `views/templates/admin/layout.tpl` | Application header, navigation tabs, notices, and shared assets. |
| `views/templates/admin/feeds.tpl` | Feed cards, URLs, states, and row actions. |
| `views/templates/admin/dashboard.tpl` | KPIs, activity chart, recent runs, and generated files. |
| `views/templates/admin/form-chrome.tpl` | Form header and live/file URL presentation. |
| `views/category_taxonomy.tpl` | Taxonomy status, synchronization, and pairing entry points. |
| `views/categories-fancybox.tpl` | Category mapping dialog and optional parent paths. |
| `views/exclude-products.tpl` | Product exclusion autocomplete and selected-product list. |
| `views/js/admin-app.js` and `views/css/admin-app.css` | Back-office application interactions and styling. |

### 6.3 Controllers and request flow

`AdminExportProductsFeedMicrosoftController` extends `ModuleAdminController`. Its application views are selected by `mmcfeed_view`: `dashboard`, `feeds`, `updates`, or `form`. It handles:

- `saveonly` for saving a feed and returning to the list.
- `submitExport` for saving and immediately downloading output.
- `updatemmc` with `id_mmc` for editing.
- `duplicatemmc` and `deletemmc` for row actions.
- AJAX `toggleFeedActive`.
- AJAX taxonomy synchronization, category mapping, autocomplete, association saving, and association deletion.

`mmcfeedfeedModuleFrontController` extends `ModuleFrontController`. It accepts the saved feed ID, loads only stored feed parameters, rejects a missing or disabled feed and a feed owned by another shop, and invokes generation. In file mode it also requires `mmcfeed_write_key`. Debug and incoming export parameters are stripped or ignored so callers cannot override stored feed settings.

The module has placeholder `index.php` files but no second functional front controller.

### 6.4 Hooks and lifecycle

The only registered hook is `actionAdminControllerSetMedia`. For `AdminExportProductsFeedMicrosoft`, it enables the jQuery Fancybox and autocomplete plugins. The hook method contains no front-office output.

The module does not define custom `enable()` or `disable()` methods. It has no module-provided hooks.

`install()` calls the parent installer, registers the hook, creates the admin tab, creates the tables, and runs schema completion. It does not clear cache. `uninstall()` deletes the admin tab and calls `parent::uninstall()`; it does not drop module tables, delete configuration values, remove generated feeds, or remove taxonomy files.

### 6.5 Overrides

The module installs no PrestaShop class or controller overrides.

### 6.6 Database

The actual table prefix is the shop's configured database prefix.

| Table | Contents |
|---|---|
| `pixelgoogle` | Category mapping records: primary key `id_pixelgoogle`, legacy `id_google`, PrestaShop `id_category`, `id_lang`, and mapped taxonomy `value`. |
| `mmc` | Saved feeds: primary key `id_mmc`, `name`, owner `id_shop`, serialized `conf`, and `active`. Schema checks add `active` and `id_shop` to older installations and assign legacy feeds to the default shop. |
| `mmc_log` | Generation history: feed ID, timestamp, duration, item count, status, file-mode flag, filename, format, and source. Entries older than 90 days are removed when a run is logged. |

Uninstallation keeps all three tables. It also keeps their feed records, mappings, and run history.

### 6.7 Configuration keys and defaults

Global and updater keys are:

| Key | Default or behavior |
|---|---|
| `mmc_pf_tree` | Missing value behaves as `0`; controls parent paths in category mapping. |
| `mypresta_updates` | Shared MyPresta update preference; a missing value behaves as disabled in the periodic check. |
| `update_mmcfeed` | Timestamp of the latest update check; written during checks. |
| `updatev_mmcfeed` | Latest version returned by the update service. |

When **Remember settings** is enabled, form defaults are stored with the `mmc_` prefix. The keys and code fallbacks are:

| Keys | Fallbacks |
|---|---|
| `mmc_export_igid`, `mmc_export_active`, `mmc_export_instock`, `mmc_export_product_type`, `mmc_export_product_type_id`, `mmc_export_product_weight`, `mmc_export_shipping_info`, `mmc_export_unit_price`, `mmc_export_save_file`, `mmc_export_nophoto_exclude`, `mmc_export_adult`, `mmc_export_color`, `mmc_export_gender`, `mmc_export_age_group`, `mmc_export_size`, `mmc_export_storecode`, `mmc_export_mainpicture`, `mmc_export_inventory`, `mmc_export_ie` | `0` or false. |
| `mmc_export_additional_sc`, `mmc_export_exworthless` | False. |
| `mmc_remember_settings`, `mmc_export_specific`, `mmc_export_enclosure`, `mmc_export_removehtml` | `1` or true. |
| `mmc_export_file_format` | `csv`. |
| `mmc_export_type` | Legacy fallback `product`, normalized to `products` for generation. |
| `mmc_export_identification` | `id_product`. |
| `mmc_export_gtin` | `upc`. |
| `mmc_export_product_name` | `name`. |
| `mmc_export_product_name_format`, `mmc_export_instock_info`, `mmc_export_what_pictures` | `0`. |
| `mmc_export_short_description_what` | `short`. |
| `mmc_export_delimiter` | `|`. |
| `mmc_export_tax` | `price_tin`. |
| `mmc_export_manufacturers_default` | `Default`. |
| `mmc_export_language`, `mmc_export_currency`, `mmc_export_country_prices`, `mmc_export_group_prices` | Corresponding shop defaults. |
| `mmc_export_category`, `mmc_export_manufacturers`, `mmc_export_suppliers` | Legacy fallback `all`; the visible selector uses its **All** option. |
| `mmc_export_shipping_info_price`, `mmc_limit_limit`, `mmc_limit_page` | `0`. |
| `mmc_export_shipping_id_zone` | `1`. |
| `mmc_export_filename`, `mmc_export_remove_char_product_name`, `mmc_export_exclude`, `mmc_export_exclude_categories`, `mmc_export_color_type`, `mmc_export_color_default`, `mmc_export_gender_default`, `mmc_export_size_default`, `mmc_export_availability_date`, `mmc_export_exreference`, `mmc_export_exreference_value`, `mmc_export_sc`, `mmc_export_exworthless_value` | Empty string. |
| `mmc_export_color_attribute`, `mmc_export_color_feature`, `mmc_export_gender_type`, `mmc_export_gender_feature`, `mmc_export_gender_attribute`, `mmc_export_age_group_type`, `mmc_export_age_group_feature`, `mmc_export_age_group_attribute`, `mmc_export_age_group_default` | `0`. |
| `mmc_export_size_attribute` | Comma-separated IDs; empty by default. |
| `mmc_mmcfeed_products` | Comma-separated excluded product IDs; empty by default. |

The form also reads `delete_images` through the remembered-setting loop as `mmc_delete_images`, although it has no visible field in this version. Uninstallation does not delete any of these keys.

### 6.8 Generated files, taxonomy, security, and extensions

Static feeds are written as `modules/mmcfeed/{sanitized-name}.{csv|xml|txt}`. Feed names are reduced to letters, digits, hyphens, and underscores, and safe-path checks prevent escaping the module directory. Taxonomy files are stored under `modules/mmcfeed/google/{language-code}.txt`. Neither group is removed on uninstall.

The file-write token is `hash_hmac('sha256', 'mmcfeed.write.' . $idShop, _COOKIE_KEY_)`. A back-office employee may write directly; an external file-generation call must present the token, and comparison uses `hash_equals`. The feed controller discards untrusted incoming `export_*`, `mmcfeed_*`, `mmc_*`, `pf_*`, limit, debug, and exclusion parameters before applying the saved feed configuration.

CSV uses `fputcsv`, a normalized delimiter, and double-quote enclosure. Feed text has HTML entities decoded, whitespace normalized, line breaks and tabs removed, and HTML stripped. XML uses `SimpleXMLElement`. Update checks use cURL when available and fall back to URL-aware file access.

Translations use `translations/{iso}.php`. Most strings pass through module translation calls; some option labels such as **All**, **Price Tax Included**, and **Price Tax Excluded** are literal English. Field descriptions live directly in the admin controller's HelperForm arrays; updater descriptions live in `lib/updateChecker.php`.

There is no storefront template to override in a theme. Back-office Smarty templates can be changed only by modifying or extending the module. For safer customization, extend feed generation through a maintained module fork or a separate integration instead of editing PrestaShop core files; no formal extension hook is exposed.

## 7. Help

Product page: [Microsoft Merchant Center Product Feed](https://mypresta.eu/modules/advertising-and-marketing/microsoft-merchant-center-feed.html)

For support, log in to your customer account at mypresta.eu, open the contact page, and select **Support for paid modules**. Login is required for this topic; after signing in, select the module from your purchase history and describe the feed, shop, and exact message you see.
