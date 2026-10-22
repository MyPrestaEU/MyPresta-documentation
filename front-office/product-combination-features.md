---
title: "Product combination features - Merchant manual"
description: "Configuration and troubleshooting manual for staff who already have the module installed."
sidebar:
  label: "Product combination features - Merchant manual"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Product combination features Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-combination-features.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/product-combination-features/)
>
> ---


Technical name: `combfeat`. Version **1.4.0**. In the back office the module is listed as **Combination's features**.

## 1. Requirements and compatibility

- **PrestaShop:** 1.7.0.0 through 9.x (`ps_versions_compliancy` max 9.99.99).
- **PHP:** the version required by that PrestaShop release.
- **Product page:** the theme must expose the selected combination on `#product-details` in the `data-product` attribute (standard PrestaShop) and fire the `updatedProduct` event when attributes change. Classic and themes built on it do this.
- **PrestaShop 8 and 9, product Modules tab:** the file `src/PrestaShopBundle/Resources/views/Admin/Sell/Catalog/Product/Blocks/modules-content.html.twig` must be writable the first time the module is installed or its configuration page is opened. See [Files the module changes](#3-files-the-module-changes).
- **Faceted Search (optional):** `ps_facetedsearch` installed, permission to create a SQL view, and write access to `modules/ps_facetedsearch/src/Adapter/MySQL.php`.
- **Update check (optional):** `allow_url_fopen` so the module can call `https://dev.mypresta.eu`.

## 2. Where to work in the back office

| Place | Path | What you do there |
| --- | --- | --- |
| Module configuration | **Modules > Module Manager**, search for **Combination's features**, **Configure** | Switches, CSS selectors, title mode, Faceted Search, CSV import, update check |
| Combination content | **Catalog > Products**, edit a product, **Modules** tab, block **Combination content** | Features, description and titles of each combination |
| Feature catalog | **Catalog > Attributes & Features** (wording depends on the PrestaShop version) | Create features and values before attaching them on the product page. The CSV import can create missing ones |
| Faceted Search template | Faceted Search module configuration | Add the feature to the filter template. This module does not add it for you |

The module has no menu entry of its own and no front-office or back-office controller.

## 3. Files the module changes

### 3.1 Product Modules tab on PrestaShop 8 and 9

On install, and again every time the configuration page opens, the module edits:

`src/PrestaShopBundle/Resources/views/Admin/Sell/Catalog/Product/Blocks/modules-content.html.twig`

It replaces `{{ module.content|raw_purified }}` with `{{ module.content|raw }}`. The first time, it copies the original file to `modules-content.html.twig.raw.bak` next to it.

PrestaShop 8 and 9 otherwise purify HTML printed by modules on the product page. Without this change the **Combination content** editor is empty or its fields are not submitted with the product. On PrestaShop 1.7 that Twig file does not exist; the module skips the change.

If the file cannot be read or written, the module does not show an error. Check the file permissions when the Modules tab stays empty.

### 3.2 Faceted Search adapter

When **Filter combination features in Faceted Search** is enabled (the default), the module creates the SQL view `{prefix}combfeat_feature_product` and points `modules/ps_facetedsearch/src/Adapter/MySQL.php` at that view. The view is the product feature list plus active combination features.

Disabling the option, disabling the module, or uninstalling it writes the original adapter source back. Uninstall also drops the view when the adapter no longer refers to it.

The configuration page shows a warning when the view cannot be created, the adapter file is missing, unreadable, not writable, or does not match the expected Faceted Search source. The exact messages are:

- Could not create the Faceted Search feature view. Combination features will not appear in category filters.
- Faceted Search is installed, but its database adapter was not found. Combination features will not appear in category filters.
- Faceted Search adapter could not be read. Combination features will not appear in category filters.
- This Faceted Search version does not use the expected feature table. Combination features will not appear in category filters.
- Faceted Search adapter is not writable. Make modules/ps_facetedsearch/src/Adapter/MySQL.php writable so combination features can be filtered.
- Faceted Search adapter could not be updated. Combination features will not appear in category filters.

## 4. Module configuration

Open **Configure**. Two forms are on the page, then the **MyPresta updates** panel. **Save** on the settings form stores `submitCombfeatSettings`. **Import** stores `submitCombfeatImport`.

### 4.1 Turn on features for combinations

Configuration key: `combfeat_p_feat`. Default: **Enabled**.

When enabled, each combination on the product **Modules** tab has a **Features** tab. You attach existing feature values there.

When disabled, that tab is hidden. The storefront script is a separate matter: features and descriptions are updated by the same script, described in [Storefront](#6-storefront).

**Saving a product while this switch is off deletes the combination features of that product.** The product form no longer contains the feature fields, and a save clears the module’s feature rows for the product, then writes back only what the form sent. Descriptions and titles are kept. Turn the switch back on before you edit the product if those features should stay.

### 4.2 Data sheet css class

Configuration key: `combfeat_ds`. Default: `.data-sheet`.

A jQuery selector. The module replaces the **inner HTML** of the matched element with pairs:

```html
<dt class="name">Feature</dt><dd class="value">Value</dd>
```

Point it at the `<dl>` that already holds the feature rows. In the Classic theme that element is `dl.data-sheet`, so the default is correct. Pointing it at a larger block, such as `.product-features` or `#product-details`, replaces everything inside that block with the `<dt>` / `<dd>` pairs.

If the selector matches nothing and the selected combination has features, the module replaces the entire contents of `#product-details` with a new data-sheet section. That removes reference, brand and any other content that lived in `#product-details`. Set the selector so this fallback is not used.

### 4.3 Workflow

Configuration key: `combfeat_workflow`. Default: **Replace existing product features** (value `0`).

| Option | Value | Data sheet when a combination is selected |
| --- | --- | --- |
| **Replace existing product features** | `0` | Combination features replace the data sheet. If that combination has no features, the product’s own features are written back. |
| **Append to existing list of product features** | `1` | Product features stay first. Combination features are added after them. If the combination has none, only the product features are shown. |

The same feature value on the product and on the combination is listed twice in **Append** mode. The module does not remove duplicates.

Several values of one feature are allowed. Each value is its own row. Rows follow the feature position from the catalog.

**Workflow changes the data sheet only.** The description is always replaced, in both modes. See [Description](#64-description).

The storefront script is chosen from this setting: `views/js/combfeat.js` for Replace, `views/js/combfeat-append.js` for Append.

### 4.4 Filter combination features in Faceted Search

Configuration key: `combfeat_faceted`. Default: **Enabled**.

When `ps_facetedsearch` is installed and this switch is on:

- Feature values that exist only on combinations can appear in category filters.
- A product is counted when the value is on the product **or on any of its combinations**. The filter does not depend on which combination the visitor later selects. One product counts once, even if several combinations carry the value.
- You still add the feature to the Faceted Search template. The module does not edit templates.
- The product feature list on the product page in the catalog is left as it is.

After you save combination features, or after a CSV import, the module empties the Faceted Search block cache (`layered_filter_block`) so the filters rebuild.

Details and the file change are in [Files the module changes](#32-faceted-search-adapter) and [Faceted Search](#7-faceted-search).

### 4.5 Turn on descriptions for combinations

Configuration key: `combfeat_p_desc`. Default: **Enabled**.

The English back-office label is **Turn on descriptionsfor combinations** (there is no space before “for”). Other languages use the corrected translation, for example “Włącz opisy dla kombinacji”.

When enabled, each combination has a **Description** tab with a rich-text field per shop language.

When disabled, that tab is hidden and a product save does not change stored descriptions. If features are still enabled, the storefront script still runs and will apply a description that was saved earlier. Clear the description fields, save, and only then turn the switch off if the storefront should stop using them.

### 4.6 Description of css class / object ID

Configuration key: `combfeat_description`. Default: `#description`.

A jQuery selector for the block whose HTML is replaced by the combination description. In the Classic theme `#description` is the long-description tab, so the default matches that block.

If the selector matches nothing, the description on the page is left untouched.

The text used when a combination has no description is the product’s **long description** (`description`), in the current language. It is not the short description and not the meta description. If you point this selector at the short-description block, a combination without its own text will fill that block with the long description.

### 4.7 Turn on meta title for combinations

Configuration key: `combfeat_p_title`. Default: **Enabled**.

When enabled, the product page loads `views/js/combfeat-title.js`. Choosing a combination updates `document.title` and, when present, `<meta property="og:title">`.

The title in the HTML sent by the server stays the product meta title. Visitors see the combination title after JavaScript runs. A crawler that does not run JavaScript keeps the product title.

When disabled, the **Meta title** tab is hidden, the script is not loaded, and a product save does not change stored titles.

### 4.8 Default title mode

Configuration key: `combfeat_title_default`. Default: **Add attribute name and value (comma separated)** (value `1`).

Used only when that combination has no **Full title** and no **Append to title** in the current language.

The original title is the browser title captured on the first load of the page. Later changes do not capture it again, so appended parts do not stack.

| Option | Value | Result |
| --- | --- | --- |
| **Do not change title by default** | `0` | The original document title stays. |
| **Add attribute name and value (comma separated)** | `1` | Original title, then the separator, then groups and values such as `Color: Red, Size: M`. |
| **Add attribute values only (comma separated)** | `2` | Original title, then the separator, then values only, such as `Red, M`. |

Group names and values come from the current shop language.

### 4.9 Title separator

Configuration key: `combfeat_title_separator`. Default: ` - ` (space, hyphen, space).

Inserted between the original document title and the added part. The added part is either the default-mode text or the combination’s **Append to title**. The separator is used as stored, including spaces.

**Full title** does not use the separator. It replaces the document title on its own.

If the original title is empty, the added part is used alone.

### 4.10 Settings quick reference

| Setting | Key | Default |
| --- | --- | --- |
| Turn on features for combinations | `combfeat_p_feat` | Enabled (`1`) |
| Data sheet css class | `combfeat_ds` | `.data-sheet` |
| Workflow | `combfeat_workflow` | Replace (`0`) |
| Filter combination features in Faceted Search | `combfeat_faceted` | Enabled (`1`) |
| Turn on descriptions for combinations | `combfeat_p_desc` | Enabled (`1`) |
| Description of css class / object ID | `combfeat_description` | `#description` |
| Turn on meta title for combinations | `combfeat_p_title` | Enabled (`1`) |
| Default title mode | `combfeat_title_default` | Attribute name and value (`1`) |
| Title separator | `combfeat_title_separator` | ` - ` |

## 5. Import combination features

The second form on the configuration page. These labels are currently the English source strings in every language (they are not in the module translation files yet).

Import assigns feature values to combinations. It does not import descriptions or titles, and it does not write rows into the product feature list (`feature_product`). A missing feature or a missing value is created in the catalog.

### 5.1 Import mode

| Mode | What it does |
| --- | --- |
| **Append to combination features** (default) | Keeps assignments already stored. A row that is already on that combination is skipped. |
| **Replace features of listed combinations** | For each combination that appears in the file, deletes that combination’s module features, then writes the file rows. Combinations absent from the file are left as they are. Descriptions and titles are not deleted. |

### 5.2 File rules

- UTF-8 `.csv` or `.txt`. A leading BOM is accepted. Maximum size **8 MB**.
- The separator is detected from the header line: semicolon, comma, or tab. If none of those appear, the semicolon is used.
- The header must identify the combination with `id_product_attribute` or `combination_reference`.
- The header must identify the feature with `feature` and `value`, or with `id_feature_value`.
- Empty rows are skipped. At most 30 row errors are listed; the rest are counted.

Accepted header names (spaces and hyphens become underscores, letter case is ignored):

| Column | Also accepted |
| --- | --- |
| `id_product` | `product_id` |
| `id_product_attribute` | `id_combination`, `combination_id` |
| `product_reference` | — |
| `combination_reference` | `combination_ref`, `attribute_reference` |
| `feature` | `feature_name`, `id_feature` |
| `value` | `feature_value` |
| `id_feature_value` | `feature_value_id` |

`id_product` and `product_reference` are optional. When you fill them in, they must belong to that combination. A mismatch rejects the row.

Finding the combination:

- `id_product_attribute` is used when it is greater than zero. `combination_reference` must match that row when both are filled in.
- Otherwise the combination reference is used. If several combinations share it, add `id_product` or `id_product_attribute`. The message is: Combination reference matches more than one combination.

Finding the feature value:

- `id_feature_value` greater than zero loads that value. The feature name and value cells are ignored.
- Otherwise `feature` and `value` are required. A feature cell that contains only digits is a feature ID.
- Names are matched exactly, then without regard to case. If more than one feature or value matches, the row is rejected. Nothing is guessed.
- A feature that does not exist is created. Its name is copied to every shop language. Maximum length 128.
- A value that does not exist is created as a normal (not custom) value, with the same text in every language. Maximum length 255. Edit **Catalog > Attributes & Features** afterwards if languages need different texts.

**Download sample file** sends `import/combfeat-features-sample.csv`:

```csv
id_product;id_product_attribute;product_reference;combination_reference;feature;value;id_feature_value
12;45;DEMO-1;DEMO-1-RED;Material;Cotton;
12;46;DEMO-1;DEMO-1-BLUE;Material;Wool;
;;DEMO-2;DEMO-2-XL;Composition;100% cotton;
10;25;;;;;83
```

Row by row, that sample means:

1. Combination 45 of product 12, references must match, feature Material / Cotton (created if missing).
2. Combination 46 of product 12, Material / Wool.
3. The combination whose reference is `DEMO-2-XL` on the product whose reference is `DEMO-2`, feature Composition / 100% cotton. No numeric IDs.
4. Combination 25 of product 10, existing feature value 83. Feature name and value are empty.

After a successful import the Faceted Search block cache is cleared. The confirmation reports how many assignments were saved, how many were already present, and which rows failed.

## 6. Combination content on the product

**Catalog > Products**, edit the product, open the **Modules** tab. The block title is **Combination content**. The subtitle is **Features, descriptions and meta titles per combination**.

Create the combinations first (the **Combinations** tab of the product). If the product has none, the block says so and there is nothing to edit.

### 6.1 The list

- **Expand all** / **Collapse all**.
- **Filter combinations…** matches the combination name, the combination ID and the combination reference.
- Each row shows the combination image (or a placeholder), the attribute names, **Combination ID**, **Reference** when the combination has one, and badges. The badges **Features**, **Description** and **Title** light up when that part is filled. The feature badge includes the number of values. These two ID/reference labels are the English source strings.
- The first combination is open. **Configure** opens a row, **Close** collapses it.
- Inside the row, the tabs that correspond to enabled switches: **Features**, **Description**, **Meta title**.

If all three switches are off, the block shows: All combination options are disabled. Enable features, descriptions or titles in the module configuration.

### 6.2 Features

Help text: Search and attach feature values used for this combination on the product page.

Type at least **2 characters** of the feature name or the value, in the employee’s current language. Up to 20 matches appear, labelled `Feature: value`. Pick one to add a token. The search only finds values that already exist. Create them in the catalog, or create them with the CSV import.

The same value cannot be added twice. Several values of the same feature can. **×** removes a token. The removal is stored when you save the product.

### 6.3 Description

One rich-text field per language. The language dropdown is shown when the shop has more than one language. Empty HTML is treated as no description: on the storefront the long product description is shown again, and on save the stored row for that language is deleted.

### 6.4 Meta title

Both fields are per language, 512 characters each. Leave a field empty to skip that override.

| Field | Storefront effect |
| --- | --- |
| **Full title (overwrite entire title)** | Replaces the whole document title. The separator and the default mode are not used. If both fields are filled, this one wins. |
| **Append to title (fragment added at the end)** | Original document title, then the separator, then this fragment. Used when Full title is empty. |

When both are empty, [Default title mode](#48-default-title-mode) is used.

### 6.5 Saving

Changes are stored with the product. Use the product **Save** button (including save and preview / save and stay, depending on the PrestaShop version). There is no separate save button in the block.

On save the module:

1. Deletes every combination-feature row of this product and inserts the tokens present in the form.
2. For each language, saves or deletes the description.
3. For each language, saves the title row, or deletes it when both title fields are empty.
4. Clears the Faceted Search block cache when the Faceted Search option is on.

The form sends a hidden `combfeat_submitted` field. If that field is missing, the module does not touch the data. On PrestaShop 8 and 9 this depends on the Twig change in [section 3.1](#31-product-modules-tab-on-prestashop-8-and-9).

Deleting a combination in PrestaShop does not delete its rows in this module. The rows are unused because the combination no longer exists. They are removed for features when you save the product (the form only sends current combinations). Description and title rows of a deleted combination remain until you remove them from the database.

## 7. Storefront

Scripts are added only on the product page, only when the request is not an ajax refresh of the whole controller, only when the product has combinations, and only when at least one of the three switches is on.

| Switch | Script |
| --- | --- |
| Features or descriptions, Workflow = Replace | `views/js/combfeat.js` |
| Features or descriptions, Workflow = Append | `views/js/combfeat-append.js` |
| Meta title | `views/js/combfeat-title.js` |

There is no extra request when the customer changes a combination. The data for every combination is printed into the page for the **current language**. The script reads the selected combination from `#product-details` attribute `data-product` (`id_product_attribute`) and runs again on the `updatedProduct` event.

`displayProductAdditionalInfo` also prints a hidden `#product-details-combfeat` element with the combination resolved for the first view (attribute groups from the URL, `id_product_attribute` from the request, or the default combination). Unavailable combinations follow PrestaShop’s stock setting and **Display unavailable attributes**. The hidden element is used only when `#product-details` itself is missing. Themes that keep `#product-details` must put `data-product` on that element. That is the standard product template.

The module does not load a front-office stylesheet. The new `<dt class="name">` and `<dd class="value">` use the theme rules for the data sheet.

### 7.1 Features and descriptions share one script

`combfeat.js` and `combfeat-append.js` update the data sheet **and** the description whenever they are loaded. They do not read the two switches again.

- Features enabled and descriptions disabled: a description saved earlier is still applied, until you clear it and save.
- Descriptions enabled and features disabled: features still stored are still applied. Saving the product while the feature switch is off deletes those stored features. See [Turn on features](#41-turn-on-features-for-combinations).

The title script is separate and runs only when the title switch is on.

### 7.2 Data sheet

Replace and Append are described under [Workflow](#43-workflow). On each run the module rebuilds the rows. Extra markup the theme had inside the data sheet (links, extra classes on a value) is not kept.

### 7.3 Description

If the combination has a description in the current language, that HTML replaces the contents of the description selector. Otherwise the product long description replaces it. Append mode does not append description text.

### 7.4 Title

Priority for the selected combination, in the current language:

1. **Full title**, when it is not empty.
2. Otherwise **Append to title**, joined with the [separator](#49-title-separator).
3. Otherwise the [default title mode](#48-default-title-mode).

`og:title` receives the same text when that meta tag exists.

## 8. Faceted Search

With the option enabled, category filters read a view that unions:

- `feature_product` — features assigned to the product;
- `combfeat` — active features assigned to combinations, joined to `feature_value` to obtain the feature ID.

Rebuild the Faceted Search index or clear the PrestaShop cache if a filter stays stale after the warning on the configuration page has been resolved. Saving combination features and importing a CSV already truncates `layered_filter_block`.

The product page in the shop still shows product features from PrestaShop until this module’s script runs. The filter and the data sheet are two different sources.

## 9. MyPresta updates

The panel under the forms:

| Control | Behaviour |
| --- | --- |
| **Check now** | Contacts MyPresta and shows **New version available!** or **Module is up to date!** |
| **Updates notifications** | **Enable** shows a back-office warning when a newer version is published, with a link to the changelog. **Disable** hides that warning. |
| **Module page** | Opens the add-on page: [Product combination features](https://mypresta.eu/modules/front-office-features/product-combination-features.html) |

While an employee is in the back office the module contacts the update server at most once every 3 days. The check needs `allow_url_fopen`. If that is unavailable, the installed version is kept and no newer version is reported.

## 10. Troubleshooting

**The Modules tab block is empty on PrestaShop 8 or 9.**  
Confirm that `modules-content.html.twig` contains `{{ module.content|raw }}` and that the shop could write that file. Re-open the module configuration page so the module tries the change again. Clear the Symfony cache afterwards (**Advanced Parameters > Performance**).

**The data sheet does not change.**  
The product needs combinations, the feature switch needs to be on or features must already be stored, and the combination needs at least one value (in Replace mode a combination with no values restores the product features, which can look like “nothing happened”). Confirm the selector in the browser console: `document.querySelectorAll('.data-sheet')` using your real selector. The theme must update `data-product` on `#product-details` and fire `updatedProduct`.

**The whole product-details block was replaced by a short feature list.**  
The data-sheet selector matched nothing. Set it to the real `<dl>`, usually `.data-sheet`.

**The description does not change, or the short description was replaced by the long one.**  
The default selector `#description` is the long description in Classic. The fallback text is always the long description. Point **Description of css class / object ID** at the element that should change.

**I turned descriptions off and the old text is still showing.**  
Clear the fields, save the product, then turn the switch off. Or turn features off as well so neither script loads. Remember that turning features off and saving deletes stored combination features.

**I turned features off and the combination features disappeared after I saved the product.**  
That is how save works when the feature fields are not in the form. Turn the switch on again before editing if you still need the data. Re-import from CSV if you have a file.

**The browser tab title does not change.**  
Turn the title switch on. An empty Full title and an empty Append field together mean the default mode is used; mode **Do not change title by default** leaves the title as it was. The change is client-side: view the page, change the combination, and read the tab title. The HTML source still has the product meta title.

**A feature is missing in the category filter.**  
Enable **Filter combination features in Faceted Search**, add the feature to the Faceted Search template, and read any warning on the module configuration page. The adapter file must be writable. The value must be stored on the product or on a combination.

**CSV row errors.**

| Message | Cause |
| --- | --- |
| The CSV must contain id_product_attribute or combination_reference | Header does not identify a combination |
| The CSV must contain feature and value, or id_feature_value | Header does not identify a feature value |
| Combination was not found | ID or reference does not exist |
| Product ID does not match this combination | `id_product` is filled in and points at another product |
| Product reference does not match this combination | `product_reference` does not match |
| Combination reference does not match this combination ID | Both ID and reference are filled in and disagree |
| Combination reference matches more than one combination | Add `id_product` or `id_product_attribute` |
| Feature name or value matches more than one | Two catalog entries share that label. Use `id_feature_value` |
| Feature and value are required when id_feature_value is empty | Name or value cell is blank |
| The CSV file is larger than 8 MB | Split the file |

**Multilanguage.**  
Descriptions and both title fields are stored per language. Feature values use the PrestaShop feature translation for the visitor’s language. The assignment itself is not per language.

## 11. Technical reference

### 11.1 Hooks

| Hook | When | What it does |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Back office, controllers `AdminProducts` and `AdminModules` | Loads `views/css/combfeat.css`, `views/js/acplt.js`, `views/js/admin-combfeat.js`, and jQuery autocomplete. Also ensures configuration and the Faceted Search integration |
| `displayAdminProductsExtra` | Product edit, Modules tab | Renders `views/templates/admin/combfeat.tpl` |
| `actionProductUpdate` | Product save | Writes features, descriptions and titles when `combfeat_submitted` is present |
| `displayHeader` | Product page, non-ajax | Prints combination data for the current language and adds the front-office scripts |
| `displayProductAdditionalInfo` | Product page | Renders the hidden `views/templates/hook/product-details.tpl` |

Registered on install: `actionProductUpdate`, `displayProductAdditionalInfo`, `displayAdminProductsExtra`, `actionAdminControllerSetMedia`, `displayHeader`.

The configuration page also answers the feature search. A request with `ajax=1` and `q` returns JSON matches and stops. The product editor calls that URL through `AdminModules` with `configure=combfeat`.

### 11.2 Database

Prefix is the shop prefix. Uninstall does **not** drop these tables, so combination content survives uninstall and is still there after a later install (`CREATE TABLE IF NOT EXISTS`).

`combfeat` — one row per feature value on a combination:

| Column | Role |
| --- | --- |
| `id_combfeat` | Primary key |
| `id_product` | Product |
| `id_product_attribute` | Combination |
| `id_feature_value` | Catalog feature value |
| `active` | `1` when used. The storefront and the Faceted Search view read active rows |

`combfeat_details` — description, one row per combination and language:

| Column | Role |
| --- | --- |
| `id_combfeat` | Primary key |
| `id_product`, `id_product_attribute`, `id_lang` | Target |
| `details` | HTML |
| `active` | Stored as `1` |

`combfeat_title` — titles, one row per combination and language:

| Column | Role |
| --- | --- |
| `id_combfeat` | Primary key |
| `id_product`, `id_product_attribute`, `id_lang` | Target |
| `title_full` | Up to 512 characters. Replaces the document title |
| `title_append` | Up to 512 characters. Added after the original title |
| `active` | Stored as `1` |

`{prefix}combfeat_feature_product` — SQL view, not a table of content you edit. Union of `feature_product` and active `combfeat` rows. Configuration value `COMBFEAT_FEATURE_VIEW` stores the view version (`1`).

Other configuration keys: `update_combfeat` and `updatev_combfeat` (update check), `mypresta_updates` (notification switch).

### 11.3 PHP classes

| File | Class | Role |
| --- | --- | --- |
| `combfeat.php` | `combfeat` | Module class: install, configuration, hooks, product editor data, storefront payload |
| `combfeat.php` | `combfeatUpdate` | Version compare and the update-server request |
| `classes/CombfeatImporter.php` | `CombfeatImporter` | CSV parse, combination and feature resolution, sample download |
| `classes/CombfeatFacetedSearch.php` | `CombfeatFacetedSearch` | View, adapter patch, restore, filter-cache clear |
| `models/cfeat.php` | `cfeat` | `combfeat` rows. `getAllByProductId`, `getFeaturesStaticByIdProduct`, `assign`, `insertDatas`, deletes |
| `models/cfeatdesc.php` | `cfeatdesc` | `combfeat_details` rows |
| `models/cfeattitle.php` | `cfeattitle` | `combfeat_title` rows. `saveTitleRow` deletes the row when both titles are empty |

There is no `controllers/` directory.

### 11.4 Assets and templates

| File | Where | Role |
| --- | --- | --- |
| `views/js/acplt.js` | Back office | Autocomplete used by the feature search |
| `views/js/admin-combfeat.js` | Back office | Accordion, filter, tabs, language flags, tokens, TinyMCE refresh, copy of editor content before product save |
| `views/css/combfeat.css` | Back office only | Layout of **Combination content** |
| `views/js/combfeat.js` | Storefront, Replace | Rebuilds the data sheet and the description |
| `views/js/combfeat-append.js` | Storefront, Append | Same, with product features kept in front of combination features |
| `views/js/combfeat-title.js` | Storefront | `document.title` and `og:title` |
| `views/templates/admin/combfeat.tpl` | Product Modules tab | The editor |
| `views/templates/hook/product-details.tpl` | Product page | Hidden `#product-details-combfeat` with `data-product` |
| `import/combfeat-features-sample.csv` | Download from configuration | Sample import |

### 11.5 Install and uninstall

Install creates the three tables, writes the default configuration, registers the five hooks, applies the Twig change, and applies the Faceted Search integration.

`disable` restores the Faceted Search adapter. `enable` writes missing configuration keys and applies the integration again when the Faceted Search switch is on.

Uninstall restores the adapter, drops the view when it is no longer referenced, and uninstalls the module. Combination rows in the three tables stay in the database.

## 12. Support

Changelog and updates: [Product combination features on MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-combination-features.html).

Orders and support: [MyPresta.eu customer account](https://mypresta.eu/my-account/orders/). Email: support@mypresta.eu.
