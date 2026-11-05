---
title: "Google Merchant Center Feed - merchant manual"
sidebar:
  label: "Google Merchant Center Feed - merchant manual"
description: "How to configure the product file for Google Merchant Center and what to do when that file fails."
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Google merchant center feed Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/google-merchant-center-feed/)
>
> ---


## 1. Requirements

The module runs on PrestaShop 1.6, 1.7, 8 and 9, and on PHP 5.6 through 8.5.

The server needs cURL and JSON. It does not need another module.

With tens of thousands of products, opening the file address takes longer and needs more memory.

You create the Google Merchant Center account yourself.

## 2. Installation

1. Upload the module in **Modules**, **Module Manager**, and enable it.
2. After installation, **Catalog** has an entry **Google Merchant Feed**.
3. The module does not clear the cache during installation.

Uninstall removes only the Catalog entry. The file list, category pairs, files saved on the server and the category-tree setting stay. They come back when you install the module again.

## 3. Configuration

### 3.1 Module configuration page

Open **Modules**, **Module Manager**, **Google Merchant Center Feed**, **Configure**. The heading is **Module settings**. There is one field.

![Module settings](https://mypresta.eu/docs/images/docs/gmfeed-settings.webp)

| Field | At the start | What it does |
|---|---|---|
| **Show categories tree** | **No** | **Yes** shows parent categories while you match Google categories. It does not choose which products go into the file. |

Click **Save**. You will see **Settings saved properly**.

### 3.2 Dashboard

Open **Catalog**, **Google Merchant Feed**. The heading is **Google Merchant Center feeds**. The tab is **Dashboard**.

![Dashboard](https://mypresta.eu/docs/images/docs/gmfeed-dashboard.webp)

The dashboard shows how many files you have saved, how many times someone opened an address today, how many times in the last 7 days, and how many files are on the server. The chart and the recent-runs list stay empty until someone opens an address. At the bottom is the list of files set to save on the server.

### 3.3 File list

The tab is **Feeds**.

![Feeds](https://mypresta.eu/docs/images/docs/gmfeed-feeds.webp)

When the list is empty you see **You have no feeds yet** and **Create your first feed**.

When files exist, a row shows status, name, shop, last run and the address. **Create new feed** sits above the list.

- The switch turns a file on or off. The address stays.
- A live file has one address. Google reads that address, and the list is built on every open.
- Saving on the server has two addresses. The generate address builds the list and writes the file. Paste the file address into Google, not the generate address. If the file is not there yet, open the generate address first.
- **Edit** opens the form. A copy adds a copy mark to the name. **Delete** asks you to confirm and removes the row. The file on disk stays.

### 3.4 Updates

The tab is **Updates**.

![Updates](https://mypresta.eu/docs/images/docs/gmfeed-updates.webp)

- **MyPresta Updates**
- **Check Now** asks once whether a newer version exists.
- Automatic notifications: **Enabled** or **Disabled**. **Enabled** checks about every three days and can show a notice in the back office.
- **Product Page** opens the module page.
- **Save** stores these settings.

### 3.5 Feed form

Click **Create new feed** or **Edit**. The tab is **Create / Edit feed**. At the bottom are **Save feed** and **Save & download**.

The picture shows the top of the form.

![Create feed](https://mypresta.eu/docs/images/docs/gmfeed-form.webp)

An empty name becomes **Untitled feed** when you save.

| Field | At the start | What it does |
|---|---|---|
| **Feed name** | empty, required | The name on the list. |
| **Active** | **Yes** | **No** keeps the address. Opening it says the file is off. |
| **Shop** | the current shop | The field appears only when the shop has several stores. The address works in the selected store. |

### 3.6 Catalog options

| Field | At the start | What it does |
|---|---|---|
| **Remember settings** | **Yes** | The next new file starts from the same choices. The file you just saved keeps its own. |

### 3.7 What to export

This is where you choose the file Google will read, and whether that read builds the list on the spot or writes a file on the server.

![What to export](https://mypresta.eu/docs/images/docs/gmfeed-form-export.webp)

Leave **CSV** unless Google must receive XML. **Products** is one row per product. The other choice is one row per variant. Only then does **Combination title** appear: the product name, the name plus the variant value, or the name plus "label: value". With products only, that field stays hidden.

**Save to file** on **No** means the address builds the list on every open and writes nothing to disk. Set **Yes** when you want a file on the server. The note under the field says the write works for the address from this page, and that address must contain the key. The address copied from the list already has it. An address without the key shows **Access denied** and writes nothing. Logged in to the back office, you can generate the file without pasting the key.

In **File name**, keep letters, digits, a hyphen and an underscore. Other characters are removed. An empty name is filled from the export type. **How to identify product?** is the ID column Google uses to tell items apart. Leave the product id unless each variant must be its own item.

| Field | At the start | What it does |
|---|---|---|
| Type of file | **CSV** | **CSV** or **XML**. |
| What you want to export | **Products** | **Products**: one row per product. The other choice: one row per variant. |
| **Save to file** | **No** | **No**: the address shows the list at once. **Yes**: the list is also written on the server. Writing needs the key from this page in the address. Without the key you see **Access denied**. Logged in to the back office, you write the file without pasting the key. |
| **File name** | empty | Letters, digits, a hyphen and an underscore stay. An empty name is filled from the export type. |
| How to identify the product | product id | Product id, variant id, or both. That is the ID column in the file. |

### 3.8 Size, gender, color and age

Google asks for these columns on apparel and similar products. They start off, so they are not in the file. Turn a group on only when the shop actually stores that value.

![Size, gender, color and age](https://mypresta.eu/docs/images/docs/gmfeed-form-attributes.webp)

For size you see the shop's attributes. Hold Ctrl and click to select more than one. When the product has none of them, the file gets the default value. Gender, color and age work the same way. The source, feature and attribute fields appear after you set that group to **Yes**. Gender values are male, female and unisex. Age values are newborn, infant, toddler, kids and adult. Use those words when Google must recognize them.

| Group | Fields |
|---|---|
| Size | export or not, size attribute, default value |
| Gender | export or not, source, feature, attribute, default: male, female, unisex |
| Color | export or not, source, attribute, feature, default value |
| Age | export or not, source, feature, attribute, default: newborn, infant, toddler, kids, adult |

### 3.9 File settings

This is the content of a row: identifiers, shipping, descriptions, names, stock, pictures and prices. Leave the starting values when Google should get an ordinary catalog. Change a field when Merchant Center is missing that column or rejects the value.

![Identifiers and shipping](https://mypresta.eu/docs/images/docs/gmfeed-form-feed-a.webp)

**Include item_group_id** ties variants of one product into one group. Turn it on when you export variants. **Unique product identifier** says where the GTIN comes from. It starts on UPC. Pick EAN-13, the reference, MPN or ISBN when that is where you keep the barcode. The last choice leaves the field empty and tells Google there is no identifier. **Include identifier_exists field** adds a column that says so. Leave **Include adult field** on "do not include" unless you sell adult products.

**Include shipping price** adds nothing at the start. You can calculate shipping per item or type one amount. When you calculate it, pick a zone from the shop's zones. Calculating per item uses more server resources than one amount. **Include product's additional shipping cost** adds the extra shipping fee from the product page. **Manual shipping value** is the amount when shipping is manual. It starts at 0. **Include weight** adds the weight.

![Shipping, descriptions and name](https://mypresta.eu/docs/images/docs/gmfeed-form-feed-b.webp)

**Product type** writes your category path as product_type. **Product type - include category ID** adds the category number so two categories with the same name stay distinct. **Short description** uses the short description or the long one. **Remove html from descriptions** on **Yes** strips the tags. **Product name** is the product name or the meta title.

![Name format, language and stock](https://mypresta.eu/docs/images/docs/gmfeed-form-feed-c.webp)

Leave **Format name** unchanged. Google does not accept a name in all capitals. If the shop names are written that way, pick lowercase, the first letter, or each word. **Remove selected characters from product name** cuts the characters you type. The form's example is x, = and a comma. Leave it empty when you cut nothing. Do not type only a space. **Language** is the language of names and descriptions. **Delimiter** separates CSV columns. It starts as a vertical bar, which Google allows. Turn **Wrap strings in double quotes** on when the program you open the file in requires quotes.

**Information about stock** reports the real stock at the start. The other choices force one status on every product. **Availability date** fills the date for backorder products that have none of their own. **Include quantity info** adds the quantity column.

![Pictures and prices](https://mypresta.eu/docs/images/docs/gmfeed-form-feed-d.webp)

**Default manufacturer value** is the brand text when the product has no manufacturer. It starts as Default. **Image size for product pictures** is the picture size in the address. The list comes from the shop. **Use default product picture if combination will not have associated photo** uses the product picture when the variant has none. **How many pictures you want to export?** starts on the cover only. **Currency** and **Export prices for selected country** start as the shop currency and the shop country. The picture shows the currency and country of the test shop, not a fixed module value. **Include specific prices** on **Yes** uses specific prices when the file currency is not the currency you are looking at the shop in. **Export prices for selected group** starts on the visitor group. **Export also unit price** adds a unit price. **Price tax included or excluded** starts with tax included.

| Field | At the start | What it does |
|---|---|---|
| Item group id | **No** | Column that ties variants of one product together. |
| Unique product identifier | UPC | UPC, EAN-13, reference, MPN, ISBN, or empty. Empty says the identifier does not exist. |
| identifier_exists field | **No** | Column for whether an identifier exists. |
| adult field | do not include | Leave it out, include as true, or include as false. |
| Shipping price | do not include | Calculated per item, or typed by hand. |
| Product additional shipping cost | **No** | Adds the extra shipping fee from the product page. |
| Manual shipping amount | 0 | The amount when shipping is manual. |
| Zone used to calculate shipping | the first zone | The zone the shipping price is taken from. |
| Weight | **No** | Weight column. |
| Product type | **No** | Your own category path in the file. |
| Add the category id to the type | **No** | The category number next to the name. |
| Short description | short description | Short description or long description. |
| Remove HTML from descriptions | **No** | **Yes** strips the tags. |
| Product name | product name | Or the meta title. |
| Combination title | the product name only | The name, the name plus the variant value, or the name plus "label: value". |
| Name format | unchanged | First letter, each word, or all lowercase. |
| Characters to cut from the name | empty | The characters you type disappear from the name. |
| Language | shop language | Names and descriptions in the file. |
| Delimiter | vertical bar | The character between CSV columns. |
| Quotes around text | **No** | **Yes** wraps fields in quotes. |
| Stock information | the real stock | All in stock, all out of stock, all backorder, or backorder treated as in stock. |
| Availability date | empty | The date for backorder products that have no date of their own. |
| Quantity | **No** | **Yes** adds the quantity. |
| Brand when there is none | Default | The brand text when the product has no manufacturer. |
| Picture size | sizes from the shop | Which picture size to put in the address. |
| Product picture when the variant has none | **No** | For variants without their own picture. |
| How many pictures | cover only | Or all pictures. |
| Currency | shop currency | Prices in the file. |
| Tax in the price | tax included | Tax included or tax excluded. |
| Specific prices | **Yes** | When the file currency is not the currency you are looking at the shop in. |
| Price group | visitor group | Prices for that customer group. |
| Unit price | **No** | An extra unit-price column. |
| Price country | shop country | The country used for tax and discounts. |

### 3.10 Selected products

Leave **All** when every manufacturer, supplier and category should be in the file. Pick one entry when Google should receive only that slice. This narrows the file. It does not replace the exclusions in the next section.

![Manufacturer, supplier and category](https://mypresta.eu/docs/images/docs/gmfeed-form-products.webp)

| Field | At the start | What it does |
|---|---|---|
| Manufacturer | **All** | One manufacturer, or all of them. |
| Supplier | **All** | One supplier, or all of them. |
| Category | **All** | One category, or all of them. |

### 3.11 Exclusions

This removes products that passed the filter in section 3.10. At the start almost nothing is excluded: products without a picture stay, disabled products stay, and products with no stock stay.

![Exclusions](https://mypresta.eu/docs/images/docs/gmfeed-form-exclude.webp)

**Exclude categories**: type the start of a category name and pick it from the suggestions. Products in that category drop out. **Exclude products without pictures** on **Yes** drops products with no picture. **Products's availability** set to active only skips products that are disabled in the shop. **Products's stock** set to in-stock only skips a quantity of zero or less. Turn **Exclude products with specific reference** on, then type the start of the reference. Variants whose reference starts the same way drop out too. **Exclude products worth less than defined value** drops products cheaper than the amount. The currency beside the field is the shop currency. **Exclude products** is a search. Type the start of a name, pick a product, or click **Add all search results**.

| Field | At the start | What it does |
|---|---|---|
| Categories to skip | empty | Type a name. Products in that category drop out. |
| Products without a picture | **No** | **Yes** skips products with no picture. |
| Availability | all products | Or only products that are enabled in the shop. |
| Stock | all products | Or only products that are in stock. |
| Skip by reference | off | Turns on a filter on the start of the reference. It also applies to variants. |
| Start of the reference | empty | Text that makes a reference drop out. |
| Skip cheaper than | off | A price threshold in the shop currency. |
| Threshold amount | empty | Products under this amount drop out. |
| Named products | empty | A search box for products to skip. |

### 3.12 Limit

Leave 0 when the whole catalog should go into one file. Beside the field you see how many products the shop has, and a note that the module will export them in one file. On a weak host, set a limit and a part number. The form's example is 3000 products and a limit of 1000, which makes three files, parts 1, 2 and 3. Each part is its own saved file, with its own address.

![Limit and store code](https://mypresta.eu/docs/images/docs/gmfeed-form-limit.webp)

| Field | At the start | What it does |
|---|---|---|
| Product limit | 0 | 0 or empty means no limit. The number of products in the shop is shown beside the field. |
| Part of the file | 0 | The part number when you split one catalog into several files. With 3000 products and a limit of 1000 you make parts 1, 2 and 3. |

### 3.13 Local store code

| Field | At the start | What it does |
|---|---|---|
| Include the store code | **No** | A column for the local store code. |
| Store code | empty | The same code as in Google Business. Letter case matters. |

### 3.14 Google categories

At the bottom there is one row per shop language. **Pair categories** opens the matching of a shop category to a Google category. **Synchronize** fetches the Google category list for that language. When the list file is missing, the button for that language is red and tells you to synchronize first. In the picture, en-us already has the file and fr does not.

![Google categories](https://mypresta.eu/docs/images/docs/gmfeed-form-categories.webp)

**Show categories tree** from section 3.1 only changes how the matching list is drawn: parent categories become visible. It does not choose products for the file. The list shipped with the module is in English, for the United States, from February 2015. You get another language with **Synchronize**, or when that list file is already in the module.

**Save & download** and **Save feed** are at the bottom again.

**Show categories tree** from section 3.1 only changes how this list is drawn. It does not change which products go into the file.

## 4. Store front

Customers see nothing on the shop. There is no block on the product page, in the cart or in the footer. There is no shop screenshot.

There is an address that Google or a browser opens. Copy it from the list. Do not build it yourself.

A live open returns CSV or XML. When saving on the server, the generate address writes the file, and the address you give Google is the file address.

Adding your own parameters changes nothing. The module uses the settings saved on that file.

Saving the form does not send products to Google. The list is built when the address is opened.

| What you see when you open it | What to do |
|---|---|
| feed does not exists | The number is wrong, or the file was removed. Copy the address from the list. |
| Feed is disabled | Turn **Active** on. |
| Feed is not available in this store | The file belongs to another shop. |
| Access denied | Saving on the server is on, and the address has no key. Copy the address from the list. |
| Invalid export path | Shorten the file name. |
| Unable to save export file | Check disk space and write permission on the module folder. |

## 5. Problems

**Google still shows yesterday's products.** The module does not send anything to Google. Open the address and check the list. Then fetch the file by hand in Merchant Center.

**The file has almost no products.** Check whether you kept only enabled products, only products in stock, one manufacturer, one supplier, one category, exclusions, a limit or a part number.

**The category tree is on, and the file still has the same products.** The tree only shows parent categories while you match them.

**I uninstalled the module and the list disappeared.** Install it again. The data stays. Only the Catalog entry went away.

**A large catalog stops halfway.** Set a limit and a part number. Make several files.

## 6. For the developer

### 6.1 Overview

`gmfeed` 2.4.3. The class `gmfeed` extends `Module`. The name in the module list is the fixed string `Google Merchant Center Feed`. Author MyPresta.eu. Tab `administration`.

The form saves a `gms` row. The `conf` field is a query string. The front address reads that row, builds CSV or XML and ends the response. Saving to a file writes it under `/modules/gmfeed/`.

### 6.2 Files

- `gmfeed.php`: install, uninstall, the configuration page, the write token, and sanitizing of the name, the extension and the type.
- `controllers/admin/AdminExportProductsFeedGoogle.php`: dashboard, list, form, save.
- `controllers/front/feed.php`: generation. `initContent()` calls `generateFeed()` and `die()`.
- `model/gms.php`: the file row and the address. Class `gms`.
- `model/google.php`: category pairs. Class `pixelgoogle`.
- `lib/updateChecker.php`: class `gmfeedUpdate`.
- `lib/searchTool/searchTool.php`: category and product suggestions.
- `views/templates/admin/`: `layout.tpl`, `dashboard.tpl`, `feeds.tpl`, `form-chrome.tpl`.
- `google/en-us.txt`: the taxonomy. First line `# Google_Product_Taxonomy_Version: 2015-02-19`.
- `.htaccess` in the module folder blocks PHP execution.

### 6.3 Controllers

Admin: `AdminExportProductsFeedGoogle`, parent `AdminCatalog`. Views in `gmfeed_view`: `dashboard`, `feeds`, `form`, `updates`.

Front: `gmfeedfeedModuleFrontController`. Address `module/gmfeed/feed?feed=` plus the number.

The write key is HMAC-SHA256 of `gmfeed.write.` plus the shop id, secret `_COOKIE_KEY_`. A logged-in employee writes without the key. Incoming `export_` and `gmfeed_` parameters are dropped and replaced with the saved ones. The key and `debug_feed` stay.

A disabled file returns HTTP 503 and `Feed is disabled`. An empty or too short `conf` ends with `feed does not exists`. A different `id_shop` ends with `Feed is not available in this store`.

### 6.4 Hooks

There is one hook: `actionAdminControllerSetMedia`. It loads fancybox and autocomplete only on `AdminExportProductsFeedGoogle`. The module does not expose its own hooks. There is no `enable()` and no `disable()`.

### 6.5 Overrides

This module does not override PrestaShop classes or controllers.

### 6.6 Database

| Table | Contents |
|---|---|
| `pixelgoogle` | A category pair: `id_google`, `id_category`, `id_lang`, `value`. |
| `gms` | A file: `name`, `id_shop`, `conf`, `active`. `CREATE` does not set a primary key. |
| `gms_log` | One opening of the address: time, count, status, file save, name, format, source. |

`ensureSchema` on the catalog page adds `active` and `id_shop`, creates `gms_log` when it is missing, and fills `id_shop` 0 with the default shop. Uninstall does not drop the tables.

### 6.7 Keys and translations

`pf_tree`: a missing key means off. The rest of the form lives in `gms.conf`. **Remember settings** posted as 1 also copies fields to `gm_{field}`, skipping the write key, the short link, active, the shop and the file id. While a file is open, a missing field uses the form default, not the `gm_` copy. An older `notepad_products` key is copied to `gmfeed_products` when the new key is missing.

Updates: `mypresta_updates`, `update_gmfeed` (172800 seconds between checks), `updatev_gmfeed`. A missing `mkey` is sent as `nokey`.

A new language is a file `translations/{iso}.php`. Strings from `$this->l()` start from the English source. The name in the module list does not go through `$this->l()`. In `translations/de.php` the configuration-page strings are Czech.

The stored export type `product` is treated as `products` when the file is built. Allowed file extensions are `csv`, `xml` and `txt`. The form shows CSV and XML.

### 6.8 Extending

The theme has nothing to override on the shop page, because the front does not render a template. A different column layout means changing the module code. You add a taxonomy in another language as `google/{code}.txt`.

## 7. Support

Module page: [Google Merchant Center Feed](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html).

To write about this module, log in to your customer account on [mypresta.eu](https://mypresta.eu/), open [Contact](https://mypresta.eu/contact.html) and choose the subject **Support for paid modules**. The form says login is required. After you log in, pick this module from your purchase history.
