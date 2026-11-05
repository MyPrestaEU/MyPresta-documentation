---
title: "Combinations Tab Pro - documentation and user manual"
description: "Configure the combinations matrix, day-to-day product-page settings, and fix common storefront problems if you already own Combinations Tab Pro."
sidebar:
  label: "Combinations Tab Pro - documentation and user manual"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Product page combinations table Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-combinations-table.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/product-page-combinations-table/)
>
> ---


Screenshots in this manual are from an English back office. Use the same tab and field names below even if your employee language differs.

## 1. Requirements

Combinations Tab Pro shows a combinations list or 2D matrix on the product page so customers can filter, sort, set quantities, and add variants to the cart.

- PrestaShop: 1.7, 8, and 9
- PHP: a version supported by your PrestaShop shop
- PHP extensions the module uses: JSON
- Other modules: none required. Optional **Product combination features** unlocks combination description and combination features columns when that module is installed in the shop
- Outside the shop: nothing. Update checks contact MyPresta when notifications are enabled
- Large catalogs: many combinations per product slow the page if you leave every column and both list and grid extras on; use filters, pagination, or a preset that matches your catalog

## 2. Installation

1. Upload the module ZIP in **Modules** → **Module Manager**, then install and enable **Combinations Tab Pro**.
2. Open configuration from the module list with **Configure**. There is no separate back-office menu entry for daily orders; all settings live on that configuration page.
3. Installation does not clear PrestaShop cache by itself. Clear Smarty / theme cache in **Advanced Parameters** → **Performance** if the table does not appear after install.

**After uninstall:** the module is removed from Module Manager. Database tables for wishlist, back-in-stock alerts, and per-entity override profiles are dropped. Configuration values stay in the shop database, so a later reinstall can pick up previous switches until you change them again. Theme overrides of module templates (if you added any) are not removed by uninstall.

## 3. Configuration and back-office work

Open **Modules** → **Module Manager** → **Combinations Tab Pro** → **Configure**. The page uses top tabs: **Overview**, **Display**, **Cart**, **B2B**, **Visibility**, **Exclusions**, **Integrations**, **Overrides**, **Updates**. Product search on **Visibility**, **Exclusions**, and **Overrides** runs in the background (AJAX); there is no separate Orders menu for this module.

### 3.1 Full process

1. Merchant configures placement, view mode, columns or grid cells, cart rules, optional B2B tools, visibility, exclusions, integrations, and overrides.
2. Customer opens a product that has combinations and that passes visibility rules.
3. The storefront shows a list (one row per combination) or a 2D grid (matrix when the product has two attribute groups and view mode allows it), in the product footer or under a **Product variants** tab.
4. Customer may use attribute filters, sort list headers, set quantities, and add one or many lines to the cart (including bulk add).
5. Optional tools: wishlist heart, back-in-stock notify, CSV quantity paste, export sheet, fill last order.
6. Checkout continues as a normal PrestaShop order. The module does not use quote-style statuses; success is a visible table, filled quantities, and a cart that contains the selected combinations.

### 3.2 Overview & presets

![Overview and presets — English back office](https://mypresta.eu/docs/images/docs/combinationstab-overview.webp)

**Overview & presets** is the starting tab. Ready-made setups turn many switches on or off at once. Use **Preview** to see the planned values, then **Apply**. Confirmation: *Preset applied. Review Display & Columns and Cart & prices if you want to fine-tune.* Then open **Display** and **Cart** to adjust details.

Main presets by name:

| Preset | Tag | What it prepares |
|---|---|---|
| **Fashion** | B2C | Photos, filters, color swatches, wishlist, mobile cards for clothing with many sizes and colors |
| **B2B Wholesale** | B2B | SKU-first matrix, bulk add to cart, CSV import, export, volume discounts |
| **Minimal** | Simple | Combination name, price, and add to cart only |
| **Replace buy block** | UX | Hides the default PrestaShop buy block so customers order from the table |
| **2D size × color** | Grid | Forces 2D grid with rich cell content when products have Color + Size |
| **Detailed list** | List | Full list with images, SKU, EAN, stock, sort, pagination |
| **Electronics** | B2C | Reference, EAN, unit price, availability dates for appliances and gadgets |
| **Beauty & cosmetics** | B2C | Color box + text, photos, wishlist and back-in-stock for shades and kits |
| **Catalog only** | Display | Combinations without ordering; prices can stay for logged-in customers |
| **Logged-in pricing** | B2B | Prices and add to cart only for logged-in customers |
| **Mobile first** | UX | List with mobile cards, plus/minus qty, sticky bulk add |
| **Restock & alerts** | Conversion | Out-of-stock rows with dates and back-in-stock alerts |
| **Luxury / lookbook** | B2C | Large photos, zoom, hidden exact stock, savings highlights |
| **Food & packaging** | Retail | Unit price, weight, min qty, volume discounts |
| **Quick order sheet** | B2B | Grid + bulk add + CSV/export/reorder without images |

### 3.3 Display — Placement

![Display settings — English back office](https://mypresta.eu/docs/images/docs/combinationstab-display.webp)

Sub-tab **Placement**. Page-level placement and chrome around the table (list and 2D grid). Save shows *Display settings saved.*

| Field | At the start | What it does |
|---|---|---|
| **Position on the product page** | Product footer (below product content) | Chooses where customers see the combinations table. Use **Product footer** below the product, or **Product tabs section** for a tab named like **Product variants**. Pick the place that fits your theme — the wrong choice can hide the table or put it too far down. |
| **Tab style (legacy themes)** | Classic tabs (PS 1.5 style) | Only matters if you use the Product tabs position on older themes. Leave the default unless your theme still uses PrestaShop 1.5-style tabs. Changes how the tab title is injected; modern 1.7/8/9 themes usually ignore this. Options: Classic tabs (PS 1.5 style) or Accordion bars (PS 1.6 style). |
| **Custom HTML above the table** | Empty | Free content (shipping note, size guide link, and similar) above the matrix. Optional per language. Visible above both list and 2D grid. |
| **Hide default PrestaShop buy block** | No | Hides the classic attribute dropdowns and add to cart on the product page. Set **Yes** when the table should be the only way to buy. Cleaner page; make sure the table itself allows add to cart. |
| **Hide default buy block only when table has combinations** | No | Keeps the normal buy block on simple products; hides it when the matrix is shown. **Yes** is usually safest so simple products still work normally. |
| **Also hide default buy block based on product restrictions** | No | Advanced pairing with Visibility rules. Leave **No** unless you use complex show/hide product lists. Can hide the native buy block on selected products even without the table. |

### 3.4 Display — View mode

| Field | At the start | What it does |
|---|---|---|
| **View mode** | List (classic table — one row per combination) | Chooses list table or 2D matrix. **List** = always rows; **2D grid** = force matrix when possible; **Auto** = matrix for 2 attribute groups, list otherwise. Fashion/B2B shops with Color+Size suit Grid/Auto; products with one attribute stay as list. |
| **Click combination to open that variant** | Off | Clicking a row/cell opens the product URL for that combination. Set **Yes** if you want browsing variants from the table. Useful with photos; disable if clicks should only change quantity. |

### 3.5 Display — Filters

These rules apply to both the list table and the 2D grid.

| Field | At the start | What it does |
|---|---|---|
| **Attribute filters above the table / grid** | Off | Shows clickable chips (for example Red, XL) to filter rows/columns. Set **Yes** for products with many combinations. Customers narrow both the list and the matrix without scrolling forever. |
| **Hide out-of-stock combinations** | Off | Removes out-of-stock combinations from the list and the 2D grid. Set **Yes** to sell only available variants. Shorter table/matrix; customers cannot see missing sizes. |
| **Hide combinations with price = 0** | Off | Hides free/zero-price variants from list and grid. Set **Yes** if zero means “not for sale”. Matrices can look incomplete if some cells are intentionally 0. |
| **Show only combinations that have a picture** | Off | Hides combinations without images in list and grid. Set **Yes** for lookbooks; **No** if every SKU must be orderable. Incomplete catalogs look nicer but some variants disappear. |
| **Multistore: disabled attribute values** | Hide the whole combination | When an attribute value is disabled for the current shop. Multistore only — choose hide combination, show as “-”, or ignore. Applies before list and grid are built; single-shop stores can leave the default. |

### 3.6 Display — Stock format

How stock quantities are displayed in list and grid when stock is shown. Column/cell visibility is under List columns or Grid cells.

| Field | At the start | What it does |
|---|---|---|
| **Show negative stock as zero** | Off | Displays 0 instead of negative numbers. Set **Yes** if your stock can go below zero. Cleaner stock numbers in list and grid. |
| **Hide exact stock above a threshold** | Off | Shows for example “20+” instead of the real number. Set **Yes** and set the threshold field. Hides large warehouse numbers from competitors in list and grid. |
| **Stock threshold (show as X+)** | Empty | When hide exact stock is **Yes**, quantities above this show as “N+”. Example: 20 makes stock 45 appear as “20+”. |

### 3.7 Display — Grid axes, images, cells

A 2D grid is a size×color style matrix. It works when the product has exactly two attribute groups and View mode is **Grid** or **Auto**. Wrong axis pairing (same group twice) breaks the grid and falls back to list.

**Grid axes**

| Field | At the start | What it does |
|---|---|---|
| **Grid rows = attribute group** | -- automatic -- | Which attribute becomes the left side of the matrix (for example Color). Pick a group or leave Automatic (first attribute group by position). Wrong pair breaks the grid and falls back to list. |
| **Grid columns = attribute group** | -- automatic -- | Which attribute becomes the top of the matrix (for example Size). Pick a different group than rows, or Automatic. Each cell is one combination where customers type quantity. |

**Grid images** (2D grid only)

| Field | At the start | What it does |
|---|---|---|
| **Show image in cells** | Off | Thumbnail inside each matrix cell. Set **Yes** for fashion color×size matrices. Denser cells; uses combination image or cover fallback below. |
| **Use product cover when combination has no image** | Yes | Shows the main product photo as fallback in grid cells. Set **Yes** to never show a blank image in the matrix. Only affects 2D grid, not the list. |
| **Grid thumbnail image type** | Empty (shop image types) | PrestaShop image size used inside grid cells. Pick a small type (for example cart / small_default). Only the 2D grid; list uses List images → Thumbnail type. |

**Grid cells** — drag **Cell block order** (top→bottom), then Save. Only enabled blocks appear. Wishlist/BIS still need **Integrations**; add to cart needs the master switch under **Cart**.

| Field | At the start | What it does |
|---|---|---|
| **Cell block order** | Default block order | Order of blocks inside each matrix cell. Drag, then Save. Only enabled blocks below appear. Image on/off and size are under Grid images. |
| **Grid: show reference (SKU)** | Off | SKU under the cell content. Set **Yes** for B2B so buyers identify SKUs without opening the product. |
| **Grid: show price** | Off | Price in the cell (tax/discount rules follow Cart settings). Set **Yes** for almost every shop so customers compare variants by price in the matrix. |
| **Grid: show unit price** | Off | Unit price in the cell. Set **Yes** if you use unit pricing. Compact line under the main price. |
| **Grid: show stock quantity** | Off | Available stock number in the cell. Set **Yes** for transparency; reveals inventory per size/color. |
| **Grid: show availability** | Off | In stock / Out of stock label in the cell. Set **Yes** when stock numbers are hidden. Clear status without the exact qty. |
| **Grid: show minimal quantity** | Off | Min order qty in the cell. Set **Yes** for B2B packs; reduces wrong cart quantities. |
| **Grid: show savings badge** | Off | % saved vs the most expensive combination. Set **Yes** for conversion; highlights cheaper sizes/colors. |
| **Grid: quantity input** | Off | Qty field in each cell (works with bulk Add to cart). Set **Yes** for matrix ordering so customers fill quantities per size. |
| **Grid: Add to cart button (when bulk ATC is off)** | Off | Per-cell add button when Bulk add to cart is disabled. Set **Yes** for one-click adds without bulk. Ignored while bulk ATC is on. |
| **Grid: wishlist heart** | Off | Heart button in the cell. Enable Wishlist under Integrations first. Customers save a size/color from the matrix. |
| **Grid: back-in-stock alert** | Off | Notify button on out-of-stock cells. Enable Back in stock under Integrations first. Captures demand for missing sizes. |

### 3.8 Display — List layout, images, columns

These settings affect only the classic list (one row per combination), not 2D grid cells.

**List layout & sorting**

| Field | At the start | What it does |
|---|---|---|
| **Column order (list only)** | Default column order | Sets the left-to-right order of columns in the list view. Drag items, then Save. Customers see columns in this order (only enabled columns appear). |
| **Mobile card layout (list)** | Yes | On phones, turns wide table rows into stacked cards. Set **Yes** for better mobile UX. Each combination looks like a small card; desktop stays a normal table. |
| **Hide table header (list)** | Off | Removes the top row with column names. Usually leave **No**. Cleaner look but harder to understand columns. |
| **Paginate long tables (list)** | Off | Splits many combinations into pages. Set **Yes** if a product has dozens of variants. Faster page feel; set Rows per page below. |
| **Rows per page** | 10 when pagination is used without a custom value | How many combinations per page when pagination is on. Example: 10 or 20. Smaller number = shorter pages, more clicking. |
| **Allow sorting by column headers** | Yes | Clickable headers to sort the list. Set **Yes** for long lists. Customers sort by price, reference, and similar (list view only). |
| **Default sort by price** | Off | Initial sort uses price. Optional. Cheapest/expensive first depending on direction. |
| **Default sort by attribute** | Off | Initial sort by a chosen attribute group. Set attribute ID and direction below. Example: sizes S→XL. |
| **Attribute sort uses** | Attribute value position | Sort by attribute position (catalog order) or by name A→Z. Position is usually best for sizes. Changes default row order when attribute sort is enabled. |
| **Attribute group ID to sort by** | Empty | Numeric ID of the attribute group used for default sort. In Catalog → Attributes, open the group and read the ID from the URL. Wrong ID = unexpected order. |
| **Sort direction** | Ascending | Ascending or descending default order. Ascending for S→XL; Descending for price high→low when sorting by price. Controls the first rows customers see. |

**List images**

| Field | At the start | What it does |
|---|---|---|
| **Show image column** | Yes | Adds a thumbnail for each combination. Set **Yes** when variants have different photos so customers recognize variants faster. |
| **Show image column only if at least one combination has a photo** | Off | Hides the empty image column when no combination has a picture. Set **Yes** to avoid a useless empty column. Table stays clean on products without combination images. |
| **Use product cover when combination has no image** | Off | Shows the main product photo as fallback in the list. Set **Yes** to never show a blank image cell. Only affects list view, not the 2D grid. |
| **Click image to zoom** | Off | Opens a larger image in a lightbox. Set **Yes** for visual products; set zoom size below. Customers inspect details without leaving the page. |
| **Thumbnail image type** | Empty (shop image types) | PrestaShop image size used in the list column. Pick a small type (for example cart / small_default). Only the list; grid uses Grid images → Thumbnail type. |
| **Zoom image type** | Empty (shop image types) | Image size opened in the lightbox when zoom is enabled. Pick a large type (for example large_default). Sharper zoom preview in list view. |

**List columns** — visibility for the classic list. Combination description / features need the optional Combination features module; otherwise those controls stay locked with a shop link.

| Field | At the start | What it does |
|---|---|---|
| **How attributes are shown** | All attributes in one column | One combined “Combination name” column vs separate columns per attribute (Color, Size…). Separated columns are easier to scan and sort. List view layout changes immediately. |
| **Include attribute label in the name** | Off | Shows “Color: Red, Size: L” instead of “Red, L”. Set **Yes** for clarity; only applies to the single-column method. Longer but clearer names. |
| **Color attribute display** | Text only | How color values look (swatch, text, or both). Color box for fashion; Text if colors are named specially. Only affects attributes of type “color”. |
| **Show combination / attribute columns** | Yes | Master switch for attribute name columns. Almost always **Yes**. **No** hides how variants differ — only for very special layouts. |
| **Show combination description** | Off (locked without Combination features) | Shows the custom description assigned to the combination by Combination features. Set **Yes** when variants have unique copy. Extra list column; empty cells show “-”. |
| **Show combination features** | Off (locked without Combination features) | Shows feature values assigned to the combination by Combination features. Set **Yes** when variants have their own data sheet. Extra list column with feature name + values. |
| **Show reference (SKU)** | Yes | Shows the combination reference. Set **Yes** for B2B / wholesale so buyers order by SKU faster. |
| **Show EAN** | No | Shows barcode EAN-13. Set **Yes** if staff/customers scan codes. Extra column; turn off for B2C fashion if unused. |
| **Show MPN** | No | Manufacturer part number column. Set **Yes** when you fill MPN in catalog. Empty cells show “-” if MPN is blank. |
| **Show weight** | Off | Product weight + combination impact. Set **Yes** for shipping-sensitive goods so customers estimate shipping. |
| **Show stock quantity** | Yes | Available stock per combination. Set **Yes** for transparency; pair with Stock format for “10+”. Builds trust; reveals inventory. |
| **Show total product stock in header** | No | Adds the sum of stock next to the Quantity header. Optional quick overview of total availability. |
| **Show availability text** | Yes | “In stock” / “Out of stock” (or your shop labels). Set **Yes** for clarity so customers see status without reading the number. |
| **Show availability date when out of stock** | Yes | Prints the combination available date under out-of-stock status. Set **Yes** if you fill available dates. Sets expectations for restock. |
| **Show minimal quantity** | Off | Shows the minimum order qty of the combination. Set **Yes** for B2B packs; reduces add-to-cart errors. |
| **Show price** | Yes | Price column per combination (list only). Set **Yes** for almost every shop. Customers compare variants by price. Grid uses Grid cells → show price. |
| **Show unit price** | Off | Unit price column (list only). Set **Yes** if you use unit pricing. Empty/odd values if unity is not set on the product. |
| **Show savings column** | No | How much cheaper a combination is vs the most expensive one (list only). Set **Yes** for upsell psychology. Extra column with % and amount saved. Grid uses Grid cells → savings badge. |
| **Show volume (quantity) discounts column** | Off | Lists quantity discount tiers per combination (list only). Set **Yes** for wholesale. Wider table; great for B2B. |
| **Hide volume discount rows that do not apply** | Off | Cleans empty discount lists in the list column. Set **Yes** to reduce noise so only meaningful tiers remain. |

### 3.9 Cart — Prices

![Cart settings — English back office](https://mypresta.eu/docs/images/docs/combinationstab-cart.webp)

Sub-tab **Prices**. Global price display rules for list and 2D grid. Save shows *Cart & price settings saved.*

| Field | At the start | What it does |
|---|---|---|
| **Show prices only to logged-in customers** | No | Guests see a login prompt instead of prices. Set **Yes** for B2B hidden pricing. Guests must log in to see amounts in list and grid. |
| **Tax display** | Tax included | Tax included, excluded, or follow the customer group setting. Match your shop price policy. Wrong choice confuses B2B vs B2C buyers. |
| **Show “tax incl./excl.” label next to price** | Off | Small text after the price. Set **Yes** for legal clarity in the EU. Slightly busier cells. |
| **Show discount % badge on reduced prices** | Off | Shows -X% when a specific price reduction exists. Set **Yes** to highlight deals. Draws attention to discounted combinations in list and grid. |
| **Highlight the cheapest combination** | Yes | Marks the lowest-price row/cell. Set **Yes** to guide impulse buys. Green highlight on the best price in list and grid. |

### 3.10 Cart — Add to cart

| Field | At the start | What it does |
|---|---|---|
| **Show add to cart controls** | Yes | Quantity field and/or button per combination. Set **Yes** to sell from the table. **No** = display-only matrix. |
| **Add to cart only for logged-in customers** | Off | Guests cannot add from the table. Set **Yes** for B2B. Guests see a message instead of buttons. |
| **Show quantity input** | Yes | Editable qty box. **Yes** always recommended. **No** hides qty (harder to buy multiple units). |
| **Qty box also in the table header (fill all rows)** | Off | One header qty copies to all rows. Optional convenience. Speeds bulk filling; use carefully. |
| **Plus / minus buttons** | No | +/- steppers next to qty. Set **Yes** for touch devices. Easier quantity changes. |
| **Block qty higher than stock** | Off | Prevents ordering more than available (when out-of-stock orders are not allowed). Set **Yes** to avoid oversell. + button stops at stock. |
| **AJAX add to cart** | Yes | Adds without full page reload. Set **Yes** on modern themes. Smoother UX; disable only if a theme conflicts. |
| **Bulk add to cart (one button for many rows)** | Off | Customer fills several qty fields, then one **Add to cart** sends all. Set **Yes** for B2B/fashion. Default per-row buttons can be hidden; sticky bar appears on mobile. |
| **Show live total price of selected quantities** | Off | Calculates sum of selected lines (respects quantity discounts when possible). Set **Yes** with bulk add. Customers see cart value before clicking Add. |
| **Tip: how many units until next quantity discount** | Yes | Under the bulk bar, tells the customer “add X more to unlock the next discount”. Set **Yes** if you use quantity discounts. Encourages larger carts. |
| **Use Font Awesome cart icon** | Off | FA icon instead of Material icon. Set **Yes** only if your theme loads Font Awesome. Missing FA = broken icon. |

### 3.11 B2B Tools and Groups

![B2B tools — English back office](https://mypresta.eu/docs/images/docs/combinationstab-b2b.webp)

**Tools** — wholesale helpers. Global switches are defaults; use **Groups** to allow or deny per PrestaShop customer group. Save shows *B2B settings saved.*

| Field | At the start | What it does |
|---|---|---|
| **CSV quantity import on product page** | No | Buyers paste lines like SKU;5 (or EAN;qty) to fill quantities. Set **Yes** for wholesale; then allow it per group if needed. Huge time saver for re-orders. |
| **Export order sheet (CSV / XLSX / PDF)** | No | Downloads the combinations with typed quantities. Set **Yes** for buyers who send sheets to accounting. Buttons appear next to bulk add. |
| **Fill last order button** | No | Restores quantities from the last bulk add / export for this product. Set **Yes** for repeat wholesale orders. One click refills the matrix. |

**Groups** — for each customer group set **Show table**, **Add to cart**, **CSV import**, **Export**, **Reorder** (Yes/No). Defaults when no custom rule exists: show table Yes, add to cart Yes, CSV/export/reorder follow the global Tools switches (off after install). If **Show table** is No for the visitor’s group, the matrix does not appear. If **Add to cart** is No, the visitor cannot add from the table even when the global Cart switches are on.

### 3.12 Visibility

![Visibility — English back office](https://mypresta.eu/docs/images/docs/combinationstab-visibility.webp)

Control on which products customers see the combinations table. Search products with the on-screen product picker (AJAX search). Confirmation: *Successfully updated*.

| Field | At the start | What it does |
|---|---|---|
| **Visibility rule** | Show on all products | Decides if the table appears on every product, only selected ones, or everywhere except selected ones. Pick a rule, then tick categories / add products in the selector below. “All products” is simplest; use Include/Exclude when only some catalog items need the matrix. |
| **Selected categories & products** | None | The list of categories and products used by the rule above. Tick categories and/or search products and click Add. Only used when the rule is Include or Exclude — ignored for “all products”. |
| **Hide table when product has too few attribute groups** | Off | Hides the table on products that have only a few attribute groups (for example only Color, no Size). Set **Yes** and set the number below. Example: threshold 1 hides products with 1 or fewer attribute groups — useful if you only want the matrix for Color+Size products. |
| **Hide when attribute groups ≤** | Empty | Threshold for the switch above. Enter 1 to hide single-attribute products; enter 0 effectively never hides by this rule. Compared to the number of attribute groups on the product. |

### 3.13 Exclusions

Permanently hide chosen combinations from the table (all products). Search a product, pick combinations with **Select**, then **Save**. Confirmation: *Settings saved*. Those variants stay in PrestaShop but never appear in the matrix — useful for obsolete sizes or internal SKUs. Product and combination search uses the same AJAX product search as Visibility.

| Field | At the start | What it does |
|---|---|---|
| **Search for product** | Empty | Find the product whose combinations you want to exclude. |
| **Combination** | None selected | Mark combinations to hide from the storefront matrix, then Save. |

### 3.14 Integrations

![Integrations — English back office](https://mypresta.eu/docs/images/docs/combinationstab-integrations.webp)

Save shows *Integrations saved.* The form notes Advanced Stock Management when it is detected; without ASM, leave the warehouse switch Off.

| Field | At the start | What it does |
|---|---|---|
| **Combination wishlist** | No | Heart button saves a variant to a light wishlist (account or cookie). Set **Yes** if customers bookmark sizes. Link appears in My Account; not a full wishlist suite. |
| **Back-in-stock email alerts** | No | Out-of-stock rows get a notify button; when stock returns, the module emails the customer. Set **Yes** and make sure your shop can send emails. Recovers demand on missing sizes. |
| **Warehouse stock column** | No | Lists quantities per warehouse when Advanced Stock is enabled. Set **Yes** only with ASM. Without ASM the column stays empty — keep Off. |

### 3.15 Overrides

![Overrides — English back office](https://mypresta.eu/docs/images/docs/combinationstab-overrides.webp)

Profiles cascade **Product → deepest Category → Manufacturer → Global**. Only overridden fields change the lower layer. Filter the list with **All / Products / Categories / Manufacturers**. Create with **Product override**, **Category override**, or **Manufacturer override**.

On the edit screen: search and select an entity, enable only the fields you want to override, leave unticked fields to inherit. Use **Copy all from global** to seed values, then **Save override**. Success: *Override profile saved.* Delete asks *Delete this override profile?* Success: *Override profile deleted.*

Typical reasons to use overrides: one brand always needs grid mode; one category hides prices for guests; one product needs extra SKU columns without changing the whole shop.

### 3.16 Updates

**Check now** asks MyPresta whether a newer build exists. Messages: *New version available!* or *Module is up to date!*

| Field | At the start | What it does |
|---|---|---|
| **Check updates** | — | Runs an immediate check and shows whether a new version exists. |
| **Updates notifications** | Select / as previously saved | Turn this option on if you want to check MyPresta.eu for module updates automatically. This option will display notification about new versions of this addon. |
| **Module page** | Link on screen | Direct link to the official addon page where you can read about changes in the module (changelog). Use Support (chapter 7) for help requests. |

## 4. Front office

- **Placement:** product footer below product content, or a **Product variants** tab in the product tabs area, depending on Display → Placement.
- **List vs 2D grid:** list is one row per combination. Grid is a matrix when the product has exactly two attribute groups and View mode is Grid or Auto; otherwise the storefront falls back to list.
- **Filters:** attribute chips above the table/grid when enabled.
- **Sorting / pagination / mobile cards:** list only, when those Display options are on.
- **Add to cart:** per-row controls and/or bulk **Add to cart** with optional live total and “units until next discount” tip.
- **Toolbar:** when enabled — **Fill last order**, **Export** (CSV / XLSX / PDF), **Import quantities** textarea with lines like `REF001;5`, then **Apply**.
- **Wishlist:** heart on rows/cells when Integrations + column/cell switches allow it. Logged-in customers get **My combination wishlist** on the customer account page.
- **Back in stock:** notify control on out-of-stock lines; email when stock returns (shop mail must work).
- **Guest prices:** with “prices only for logged-in”, guests see a login prompt instead of amounts; with “ATC only for logged-in”, guests cannot add from the table.

No separate storefront screenshot is required here; theme layout decides the exact chrome around the module block.

## 5. Common problems

### 5.1 Table not visible on the product page

Check module enabled, product has combinations, **Visibility** rule includes the product, customer group **Show table** is Yes, and position matches your theme (footer vs tabs). Clear cache. Confirm Exclusions did not hide every combination.

### 5.2 Wrong position or empty tab

Change **Position on the product page**. On modern themes, ignore Tab style. If you use tabs, open the product and look for **Product variants**.

### 5.3 Expected 2D grid but see a list

Grid needs exactly two attribute groups and View mode Grid or Auto. One attribute, or three or more, forces list. Same attribute group for both axes also falls back to list — set different row and column groups.

### 5.4 Default buy block missing or still visible

Review **Hide default PrestaShop buy block** and **Hide default buy block only when table has combinations**. If the native block is hidden but the table has no add to cart, customers cannot buy — turn Cart → **Show add to cart controls** on.

### 5.5 Bulk add does nothing or reloads badly

Turn **AJAX add to cart** on for modern themes. Confirm **Bulk add to cart** is Yes and quantities are filled. Group rule **Add to cart** must be Yes for that customer group.

### 5.6 Group rules block add to cart or hide the table

Under **B2B** → **Groups**, set **Show table** and **Add to cart** to Yes for the visitor’s group (Guest, Customer, or your wholesale group).

### 5.7 Prices hidden for guests

Expected when **Show prices only to logged-in customers** is Yes. Turn it Off for public prices, or ask guests to log in.

### 5.8 Wishlist or back-in-stock missing

Enable them under **Integrations**, then enable the matching list column or grid cell switches. For BIS, confirm PrestaShop can send mail and that stock updates when you restock.

### 5.9 Combination description / features columns locked

Install and enable the optional **Product combination features** module. Until then those columns stay locked in Display and Overrides.

### 5.10 CSV / export / fill last order missing

Enable the tools under **B2B** → **Tools**, and set Yes for that customer group under **Groups**.

## 6. Developer guide

### 6.1 Overview

- Technical name: `combinationstab`
- Version: 3.0.5
- Display name: Combinations Tab Pro
- Author: mypresta.eu
- Module tab: `smart_shopping`
- Main class: `Combinationstab`
- BO UI: `CtpAdminBo` (`lib/CtpAdminBo.php`)
- Settings resolution: `CtpSettingsResolver` (Product → Category → Manufacturer → Global)
- Optional: `CtpCombfeat` — file may be absent; `class_exists('CtpCombfeat')` gates combination description/features. Without the class, those options stay locked.

Flow: Configuration / entity settings → FO hooks render list or grid templates → front controllers handle AJAX cart helpers, wishlist, BIS, CSV, export, reorder, price calculator.

### 6.2 Important files

| Path | Role |
|---|---|
| `combinationstab.php` | Module class, install/uninstall, hooks, visibility/exclusions forms |
| `lib/CtpAdminBo.php` | Configure page tabs and HelperForm fields |
| `lib/CtpColumnRegistry.php` | List columns, presets, order JSON |
| `lib/CtpGridRegistry.php` | Grid cell blocks and order JSON |
| `lib/CtpGrid2d.php` | 2D matrix build / `shouldUseGrid` |
| `lib/CtpCombinationsData.php` | Combination rows for FO |
| `lib/CtpGroupRules.php` | Per-group show/atc/csv/export/reorder |
| `lib/CtpWishlist.php` / `CtpBackInStock.php` / `CtpExport.php` / `CtpReorder.php` | Feature helpers |
| `lib/CtpSettingsResolver.php` | Override table and cascade |
| `views/templates/admin/tabs.tpl` | BO tab chrome |
| `views/templates/hook/productfooter.tpl` / `productfooter_grid.tpl` | FO list / grid |
| `views/templates/hook/_toolbar.tpl` | Bulk / export / CSV toolbar |
| `controllers/front/*.php` | Front endpoints |
| `controllers/admin/AdminCombinationstabSearchController.php` | AJAX product search for BO pickers |

### 6.3 Controllers

**Admin:** `AdminCombinationstabSearchController` — AJAX product/combination search used by Visibility, Exclusions, Overrides. Not a menu page for merchants.

**Front:**

| Controller | Purpose |
|---|---|
| `Wishlist` | Toggle / list wishlist (JSON + account page) |
| `BackInStock` | Subscribe for OOS alerts (JSON) |
| `CsvImport` | Apply pasted SKU/EAN quantities (JSON) |
| `Export` | Download CSV/XLSX/PDF sheet |
| `Reorder` | Save / restore last quantities (JSON) |
| `PriceCalculator` | Live selected total / volume tip (JSON body, no curl) |

### 6.4 Hooks (registered on install)

`displayHeader`, `displayProductFooter`, `displayFooterProduct`, `displayProductTab`, `displayProductExtraContent`, `displayProductTabContent`, `CombinationsTable`, `ActionAdminControllerSetMedia`, `displayCustomerAccount`, `actionUpdateQuantity`.

No custom `enable()` / `disable()` beyond PrestaShop defaults. Uninstall drops feature tables then `parent::uninstall()`.

### 6.5 Overrides

The module ships no class/controller overrides under `override/`. Theme template overrides of module `.tpl` files are optional and merchant-side.

### 6.6 Database

Uninstall drops these tables; Configuration keys are kept.

| Table | Content |
|---|---|
| `ctp_wishlist` | `id_ctp_wishlist`, customer/guest, product, combination, shop, `date_add` |
| `ctp_backinstock` | Email subscriptions, product/combination, shop, lang, `notified`, dates |
| `ctp_entity_settings` | `entity_type`, `id_entity`, JSON `settings`, `date_upd` |

### 6.7 Configuration keys and defaults (install)

Selected defaults written on install: `ctp_position` = `productFooter`, `ctp_where` = `1`, `ctp_view_mode` = `list`, `ctp_image`/`ctp_price`/`ctp_reference`/`ctp_cname`/`ctp_atc`/`ctp_atcq`/`ctp_ajax`/`ctp_sort`/`ctp_quantity`/`ctp_availability`/`ctp_availability_d` = `1`, `ctp_ean`/`ctp_mpn` = `0`, `ctp_wishlist`/`ctp_bis`/`ctp_export`/`ctp_csv_import`/`ctp_reorder` = `0`, `ctp_group_rules` = `{}`, `ctp_column_order` = JSON from `CtpColumnRegistry::defaultKeys()`, plus related tax/hide/grid keys as in `install()`. Column/cell order also uses JSON (`ctp_column_order`, `ctp_grid_cell_order`). Translations: `translations/{iso}.php`. Field `desc` texts live mainly in `CtpAdminBo`.

### 6.8 Extending

Override FO templates from the theme under `modules/combinationstab/...` without editing the module package. Theme must still call the registered product hooks for output. Optional Combination features integration requires `lib/CtpCombfeat.php` present and `CtpCombfeat::isAvailable()` true.

## 7. Support

Product page: https://mypresta.eu/modules/front-office-features/product-page-combinations-table.html

To get help: log in to your customer account on mypresta.eu, open Contact, and choose **Support for paid modules**. The form requires login for paid modules; after login, pick this module from your purchase history.
