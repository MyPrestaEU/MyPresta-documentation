---
title: "Product page combinations table - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Product page combinations table PrestaShop module by MyPresta.eu."
sidebar:
  label: "Product page combinations table - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Product page combinations table Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-combinations-table.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/product-page-combinations-table/)
>
> ---


# Product page combinations table

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen where you control how the combinations table appears and behaves on your product pages.

#### General Settings

- **Activate filters feature**

  - **What this setting does:** Enables or disables a filtering system above the combinations table, allowing customers to quickly narrow down options based on specific attribute values (e.g., “Show only Red shirts”).
  - **Effect of changing this setting:**
    - *When enabled:* A filter bar will appear above the table, making it easier for customers to find specific combinations in large lists.
    - *When disabled:* No filter bar will be shown, and all combinations will be displayed without filtering options.
  - **Recommended value:** YES (if you have many combinations per product, or if customers often search for specific attributes).
  - **Merchant scenario / example:** A clothing store with dozens of sizes and colors for a single t-shirt. Filters help customers quickly find “Large Blue” shirts.
- **Highlight best price**

  - **What this setting does:** Visually emphasizes the combination with the lowest price in the table, drawing customer attention to the most affordable option.
  - **Effect of changing this setting:**
    - *When enabled:* The row corresponding to the cheapest combination will be highlighted (e.g., with a different background color).
    - *When disabled:* No special highlighting for the lowest price.
  - **Recommended value:** YES (can encourage purchases by highlighting value).
  - **Merchant scenario / example:** A product with various bundles or configurations where one combination offers a significantly better deal.
- **Display savings column**

  - **What this setting does:** Adds an extra column to the table that shows the amount or percentage a customer saves when purchasing a specific combination, especially useful with quantity discounts or special pricing.
  - **Effect of changing this setting:**
    - *When enabled:* A “Savings” column will appear, displaying the discount for each combination if applicable.
    - *When disabled:* This column will not be shown.
  - **Recommended value:** YES (if you frequently offer discounts or have quantity-based pricing).
  - **Merchant scenario / example:** Selling a product with a base price, but certain combinations (e.g., a “bundle” combination) have a reduced price, and you want to show the saving.
- **Quantity discount threshold tip**

  - **What this setting does:** Displays a small tooltip or message indicating the quantity required to unlock a specific discount, encouraging customers to buy more.
  - **Effect of changing this setting:**
    - *When enabled:* When a customer hovers over or interacts with a quantity input, a tip might appear showing “Buy 5 for 10% off!”.
    - *When disabled:* No such tips will be displayed.
  - **Recommended value:** YES (if you use PrestaShop’s quantity discounts feature).
  - **Merchant scenario / example:** A store selling office supplies where buying 10 pens gets a 5% discount, and this tip reminds the customer.
- **Mobile card layout**

  - **What this setting does:** Determines how the combinations table is displayed on mobile devices. Instead of a wide table, it can switch to a more user-friendly “card” layout.
  - **Effect of changing this setting:**
    - *When enabled:* On smartphones, each combination will be presented as a separate, vertically stacked card, making it easier to read and interact with.
    - *When disabled:* The module will attempt to display the full table, which might require horizontal scrolling on mobile, potentially hindering usability.
  - **Recommended value:** YES (crucial for mobile responsiveness and a good user experience).
  - **Merchant scenario / example:** A customer browsing your store on their phone. The card layout ensures they can easily see and select combinations without zooming or excessive scrolling.
- **Column order**

  - **What this setting does:** Allows you to customize the sequence of columns (e.g., Image, Reference, Price, Quantity) in the combinations table.
  - **Effect of changing this setting:**
    - *When changed:* The columns will re-arrange themselves in the front-office table according to your specified order.
  - **Recommended value:** Arrange columns in an intuitive order that makes sense for your products (e.g., Image, Attributes, Price, Quantity, Add to Cart).
  - **Merchant scenario / example:** For a fashion store, you might want “Image” first, then “Color,” then “Size,” then “Price.” For electronics, “Reference” might be more important.
- **Click and switch combination**

  - **What this setting does:** Controls whether clicking on a combination row in the table automatically updates the main product image, price, and other details on the product page to reflect that specific combination.
  - **Effect of changing this setting:**
    - *When enabled:* Clicking a row will dynamically update the main product display, giving the customer a visual confirmation of their selection.
    - *When disabled:* The main product display will not change when a row is clicked; only the quantity input and Add to Cart button for that row are active.
  - **Recommended value:** YES (improves user experience by providing visual feedback).
  - **Merchant scenario / example:** A customer clicks on a “Red, Large” combination, and the main product image immediately switches to the red version of the product.

#### Image Settings

- **Display image**

  - **What this setting does:** Determines if a thumbnail image for each combination should be shown in the table.
  - **Effect of changing this setting:**
    - *When enabled:* An image column will appear, showing the specific image associated with each combination (if available).
    - *When disabled:* No image column will be displayed.
  - **Recommended value:** YES (visuals are powerful for product selection).
  - **Merchant scenario / example:** A clothing store where each color variation has a distinct image.
- **Display image column if there is at least one combination with picture**

  - **What this setting does:** Controls the visibility of the image column based on whether any combination actually has a specific image assigned to it.
  - **Effect of changing this setting:**
    - *When enabled:* If even one combination has an image, the image column will appear for all combinations (showing the default product image for those without specific combination images).
    - *When disabled:* The image column will only appear if *all* combinations have specific images, or it might not appear at all if you also use “Use default product image” carefully.
  - **Recommended value:** YES (prevents an empty image column if only a few combinations have images).
  - **Merchant scenario / example:** You have 20 combinations, but only 5 have unique images. This ensures the image column still shows up, using the main product image for the other 15.
- **Use default product image**

  - **What this setting does:** If a specific combination does not have its own image, this setting determines if the main product image should be used as a fallback.
  - **Effect of changing this setting:**
    - *When enabled:* Combinations without specific images will display the main product image.
    - *When disabled:* Combinations without specific images will show a placeholder or no image.
  - **Recommended value:** YES (ensures all combinations have a visual representation).
  - **Merchant scenario / example:** A product with many size variations but only one image per color. This ensures all sizes of a specific color show the correct color image.
- **Enable fancybox zoom**

  - **What this setting does:** Allows customers to click on combination images in the table to view a larger, zoomed version in a pop-up (Fancybox).
  - **Effect of changing this setting:**
    - *When enabled:* Clicking a combination image will open it in a Fancybox pop-up.
    - *When disabled:* Images will not be clickable for zoom.
  - **Recommended value:** YES (improves image viewing experience).
  - **Merchant scenario / example:** A customer wants to see the texture or detail of a specific color variation more closely.
- **Image type to display**

  - **What this setting does:** Selects the size/type of image (e.g., `small_default`, `medium_default`) to be displayed as thumbnails in the combinations table.
  - **Effect of changing this setting:**
    - *When changed:* The size of the images in the table will update to the selected image type.
  - **Recommended value:** `small_default` or `medium_default` (choose one that fits well within your table layout without being too large or too small).
  - **Merchant scenario / example:** You want the images in the table to be slightly larger than the tiny `small_default` but not as big as `large_default`.
- **Image type used to enlarge thumbnail**

  - **What this setting does:** Selects the size/type of image to be used when the Fancybox zoom feature is activated.
  - **Effect of changing this setting:**
    - *When changed:* The image displayed in the Fancybox pop-up will be of the selected size.
  - **Recommended value:** `large_default` or `thickbox_default` (choose the largest, highest quality image type for zooming).
  - **Merchant scenario / example:** A customer zooms in on an image and expects to see a high-resolution version.

#### Attributes Display Settings

- **Attributes display method**

  - **What this setting does:** Controls how the attribute names (e.g., “Size”, “Color”) are displayed in the table header.
  - **Effect of changing this setting:**
    - *Options (e.g., “Full name”, “Short name”, “ID”):* Changes how the attribute headers appear.
  - **Recommended value:** “Full name” (most descriptive for customers).
  - **Merchant scenario / example:** You want “Size” to appear as “Size” not “S” or “ID: 1”.
- **Attribute associations with shop (multistore)**

  - **What this setting does:** In a multistore environment, this allows you to specify which attribute groups are relevant for which shops, preventing irrelevant attributes from appearing.
  - **Effect of changing this setting:**
    - *When configured:* Only attributes associated with the current shop context will be displayed in the table.
  - **Recommended value:** Configure carefully if you run a multistore with different product catalogs.
  - **Merchant scenario / example:** Shop A sells clothes (Size, Color), Shop B sells electronics (Storage, RAM). This prevents “Storage” from appearing in Shop A’s combination table.
- **Include label to attribute name**

  - **What this setting does:** Adds the attribute group name as a prefix to the attribute value (e.g., “Size: S”, “Color: Red”).
  - **Effect of changing this setting:**
    - *When enabled:* Attribute values will be more descriptive.
    - *When disabled:* Only the attribute value will be shown (e.g., “S”, “Red”).
  - **Recommended value:** YES (improves clarity, especially if attribute values are not self-explanatory).
  - **Merchant scenario / example:** A product has an attribute value “Standard”. Is it a standard size, standard color, or standard finish? “Finish: Standard” clarifies it.
- **Color attribute**

  - **What this setting does:** Allows you to specify which attribute group represents “color” in your store. This is important for the module to correctly display color swatches or color-specific logic.
  - **Effect of changing this setting:**
    - *When selected:* The module will treat values from this attribute group as colors, potentially displaying them as color swatches instead of text.
  - **Recommended value:** Select your primary “Color” attribute group.
  - **Merchant scenario / example:** You have an attribute group named “Color” with values like “Red”, “Blue”, “Green”. Selecting this group ensures these are displayed as actual color swatches.

#### Display Options

- **Hide table header**

  - **What this setting does:** Removes the header row from the combinations table (e.g., “Image | Size | Color | Price | Quantity”).
  - **Effect of changing this setting:**
    - *When enabled:* The table will start directly with the combination rows, without column titles.
    - *When disabled:* The header row will be visible.
  - **Recommended value:** NO (headers are usually important for clarity, unless your table is very simple and self-explanatory).
  - **Merchant scenario / example:** For a very simple product with only one attribute (e.g., “Pack Size”), you might hide the header if the column content is obvious.
- **Hide out of stock combinations**

  - **What this setting does:** Prevents combinations that are currently out of stock from being displayed in the table.
  - **Effect of changing this setting:**
    - *When enabled:* Only in-stock combinations will be visible, reducing clutter and preventing customer frustration.
    - *When disabled:* Out-of-stock combinations will still be shown, often with a “Sold Out” label or disabled Add to Cart button.
  - **Recommended value:** YES (generally better for user experience, unless you want to show all options for pre-orders or back-in-stock notifications).
  - **Merchant scenario / example:** A popular shoe model has sold out of size 10. Hiding it prevents customers from trying to select it.
- **Hide combinations with price = 0**

  - **What this setting does:** Excludes combinations that have a price of zero from being displayed in the table.
  - **Effect of changing this setting:**
    - *When enabled:* Combinations with a zero price will not appear.
    - *When disabled:* Zero-priced combinations will be listed.
  - **Recommended value:** YES (unless you intentionally offer free combinations, which is rare).
  - **Merchant scenario / example:** Sometimes, due to misconfiguration, a combination might end up with a zero price. Hiding these prevents confusion.
- **Show only combinations with pictures**

  - **What this setting does:** Filters the table to only display combinations that have a specific image assigned to them.
  - **Effect of changing this setting:**
    - *When enabled:* Only combinations with unique images will be listed.
    - *When disabled:* All combinations will be shown, regardless of whether they have a specific image.
  - **Recommended value:** NO (usually better to show all combinations, using default images if necessary, unless visual differentiation is paramount).
  - **Merchant scenario / example:** If you only want to showcase combinations that have distinct visual differences, and you haven’t uploaded images for all of them.
- **Display price**

  - **What this setting does:** Controls whether the price for each combination is shown in the table.
  - **Effect of changing this setting:**
    - *When enabled:* A “Price” column will be visible.
    - *When disabled:* The price column will be hidden.
  - **Recommended value:** YES (price is a critical factor for customers).
  - **Merchant scenario / example:** A customer wants to compare prices across different sizes or materials of a product.
- **Display unit price**

  - **What this setting does:** Shows the unit price (e.g., price per kg, per liter) for each combination, if applicable.
  - **Effect of changing this setting:**
    - *When enabled:* An additional “Unit Price” column will appear.
    - *When disabled:* This column will not be shown.
  - **Recommended value:** YES (if your products are sold by weight/volume and unit pricing is relevant).
  - **Merchant scenario / example:** Selling coffee beans in different bag sizes, and customers want to compare the price per 100g.
- **Display price only for logged customers**

  - **What this setting does:** Hides combination prices from visitors who are not logged into their customer accounts.
  - **Effect of changing this setting:**
    - *When enabled:* Guests will not see prices; they might see a message prompting them to log in.
    - *When disabled:* Prices are visible to everyone.
  - **Recommended value:** NO (unless you run a B2B store or have specific pricing strategies requiring login).
  - **Merchant scenario / example:** A wholesale store where pricing is negotiated or specific to registered business accounts.
- **Show tax label**

  - **What this setting does:** Displays a label indicating whether the prices shown are inclusive or exclusive of tax (e.g., “Tax incl.”, “Tax excl.”).
  - **Effect of changing this setting:**
    - *When enabled:* The tax status will be clearly indicated next to prices.
    - *When disabled:* No tax label will be shown.
  - **Recommended value:** YES (improves transparency and complies with legal requirements in many regions).
  - **Merchant scenario / example:** Customers in Europe expect to see “Tax incl.” prices, while B2B customers might prefer “Tax excl.”

#### Other Configuration Keys (Advanced/Internal)

These settings are typically managed by the module internally or are less frequently adjusted by merchants.

- `mypresta_updates`, `update_`, `updatev_`: Internal keys for module updates and version tracking.
- `ctp_position`: Controls the hook position where the table is displayed.
- `ctp_lasttab`: Related to displaying the table in a product tab.
- `ctp_reference`, `ctp_ean`, `ctp_mpn`: Control display of Reference, EAN13/JAN, and MPN columns.
- `ctp_cname`: Controls display of combination name.
- `ctp_atc`, `ctp_atcq`: Control “Add to Cart” button and quantity input.
- `ctp_ajax`: Determines if AJAX is used for adding to cart.
- `ctp_sort`: Sorting options for combinations within the table.
- `ctp_quantity`, `ctp_quantity_sum`: Display of stock quantity and sum of quantities.
- `ctp_availability`, `ctp_availability_d`: Display of availability status and date.
- `ctp_imagetype`, `ctp_imagetype_zoom`, `ctp_grid_imagetype`, `ctp_grid_defimg`: Image type settings (covered above).
- `ctp_attributes_method`: Attribute display method (covered above).
- `ctp_prices_tax`: Tax display settings (covered above).
- `ctp_color_method`: How color attributes are displayed (e.g., swatches).
- `ctp_hide_default`, `ctp_hide_r`: Hide default combination, hide combinations with zero price (covered above).
- `ctp_where`, `ctp_tabtype`: Placement of the table (hook, tab type).
- `ctp_quantity_pm`: Plus/minus buttons for quantity input.
- `ctp_view_mode`: Overall table view mode (table, grid, etc.).
- `ctp_grid_row_attr`, `ctp_grid_col_attr`: Settings for grid layout (which attributes form rows/columns).

### 2.2 Dedicated Admin Screens & Controller Views

#### AdminCombinationstabSearchController (Back Office > Modules > Product page combinations table > Search)

This controller provides a dedicated interface within the PrestaShop back office, likely for managing or searching combinations, potentially across multiple products, or for advanced configuration related to combination display.

- **Screen Name & Menu Location:** You will typically find a new menu item under **Modules > Product page combinations table** (or similar, depending on PrestaShop version) labeled “Search” or “Combinations Search”.
- **Available Actions & Settings:** This screen likely presents a grid or management view of product combinations. It might allow you to:
  - Search for specific combinations by attributes, reference, EAN, or product name.
  - View details of combinations, such as stock, price, and associated product.
  - Potentially perform bulk actions like updating stock or price for multiple combinations (though this is often handled by PrestaShop’s core product page).
  - This screen is primarily for *managing* and *viewing* combination data in a structured way, separate from the main product edit page.
- **Effect of changes:** Any changes made here (if editing is enabled) would directly update the combination data in your PrestaShop database, affecting prices, stock, and availability on the front office.
- **Recommended workflow for daily store management:** Use this screen to quickly audit combination data, find specific combinations, or verify stock levels without navigating to individual product pages. It’s a powerful tool for stores with a large catalog of products and combinations.

#### index.php (combinationstab/controllers/admin/index.php)

This file typically serves as a placeholder or a redirector for the main admin controller of the module. It might simply load the `AdminCombinationstabSearchController` or present a basic landing page for the module’s admin section. It usually doesn’t have direct configurable settings but acts as an entry point.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Activate filters feature | YES | Enables attribute filters for combinations table. |
|  | Highlight best price | YES | Visually highlights the lowest-priced combination. |
|  | Display savings column | YES | Shows discount amount/percentage in a dedicated column. |
|  | Quantity discount threshold tip | YES | Displays tips for quantity-based discounts. |
|  | Mobile card layout | YES | Optimizes table display for mobile devices. |
|  | Column order | Customizable | Defines the sequence of columns in the table. |
|  | Click and switch combination | YES | Updates main product image/details on row click. |
|  | Display image | YES | Shows combination images in the table. |
|  | Display image column if there is at least one combination with picture | YES | Ensures image column appears if any combination has an image. |
|  | Use default product image | YES | Fallback to main product image if combination has no specific image. |
|  | Enable fancybox zoom | YES | Allows zooming of combination images. |
|  | Image type to display | `medium_default` | Sets thumbnail size in the table. |
|  | Image type used to enlarge thumbnail | `large_default` | Sets zoom image size. |
|  | Attributes display method | Full name | How attribute headers are labeled (e.g., “Size”). |
|  | Attribute associations with shop (multistore) | Configure as needed | Filters attributes by shop in multistore. |
|  | Include label to attribute name | YES | Adds attribute group name to value (e.g., “Size: S”). |
|  | Color attribute | Select your Color attribute | Identifies the color attribute for special display. |
|  | Hide table header | NO | Keeps column titles visible for clarity. |
|  | Hide out of stock combinations | YES | Removes unavailable combinations from the table. |
|  | Hide combinations with price = 0 | YES | Removes zero-priced combinations. |
|  | Show only combinations with pictures | NO | Displays all combinations, using default images if needed. |
|  | Display price | YES | Shows the price for each combination. |
|  | Display unit price | YES (if applicable) | Shows price per unit (e.g., per kg). |
|  | Display price only for logged customers | NO | Makes prices visible to all visitors. |
|  | Show tax label | YES | Indicates if prices are tax inclusive/exclusive. |
| **AdminCombinationstabSearchController** | Grid / Management View | N/A | Search, view, and potentially manage combinations across products. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The combinations table isn’t showing up on my product page.**
A1:

- **Check Module Position:** Go to **Design > Positions** (or **Modules > Positions** in older PrestaShop versions) in your Back Office. Search for the module “Product page combinations table”. Ensure it’s hooked into a relevant display hook like `displayProductFooter`, `displayProductExtraContent`, or `displayProductTabContent`. If it’s not, click “Transplant a module” and add it to the desired hook.
- **Module Configuration:** Double-check the module’s configuration page to ensure it’s enabled and not hidden by other settings (e.g., “Hide combinations with price = 0” might hide all if all are zero).
- **Product Has Combinations:** Make sure the product you are viewing actually has combinations defined in its product settings.
- **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache”. Sometimes, old cached content prevents new module displays.

**Q2: My combination images aren’t appearing or are the wrong size.**
A2:

- **Image Settings:** Review the “Image type to display” and “Image type used to enlarge thumbnail” settings in the module’s configuration. Ensure you’ve selected appropriate image types that exist in your PrestaShop theme.
- **Combination Images Uploaded:** Verify that you have actually uploaded specific images for your product combinations in the product’s “Combinations” tab in the Back Office. If not, the module will fall back to the main product image (if “Use default product image” is enabled).
- **Regenerate Thumbnails:** If you changed image types or uploaded new images, go to **Design > Image Settings** (or **Preferences > Images**) and click “Regenerate thumbnails” for the relevant image types (e.g., `medium_default`, `large_default`).

**Q3: The table looks strange or misaligned on my custom theme.**
A3:

- **CSS Conflicts:** Custom themes sometimes have conflicting CSS styles. This module tries to be compatible, but minor adjustments might be needed.
- **Contact Support:** If you’re comfortable with CSS, you can inspect the elements using your browser’s developer tools and try to override conflicting styles. Otherwise, contact MyPresta.eu support with details of your theme and a screenshot; they can often provide a quick fix.
- **Module Updates:** Ensure you are running the latest version of the module, as compatibility improvements are often included in updates.

**Q4: Prices are not showing correctly or are hidden.**
A4:

- **Display Price Settings:** Check “Display price” and “Display price only for logged customers” in the module configuration. If the latter is enabled, ensure you are logged in as a customer to see prices.
- **PrestaShop Core Pricing:** Verify that the prices for your combinations are correctly set in the product’s “Combinations” tab.
- **Tax Settings:** Check “Show tax label” and your general PrestaShop tax settings (**International > Taxes**) to ensure prices are calculated and displayed as expected (tax incl./excl.).

**Q5: How do I change the order of attributes in the table?**
A5:

- The module’s “Column order” setting allows you to re-arrange the columns. For the order of attributes themselves (e.g., “Size” before “Color”), this is typically managed in PrestaShop’s core: **Catalog > Attributes & Features > Attributes** and **Attribute Groups**. The order you set there usually influences how they appear in the module’s table.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Product page combinations table” module (`combinationstab`) follows a standard PrestaShop module architecture, heavily leveraging hooks for front-office display and custom admin controllers for advanced configuration and data management. It integrates deeply with PrestaShop’s core product and combination data, dynamically rendering HTML tables or grids using Smarty templates. AJAX is used for features like “Add to Cart” and combination switching for a seamless user experience. The module does not introduce custom `ObjectModel` classes but works directly with existing `Product` and `Combination` objects.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

These controllers handle specific AJAX requests or dedicated front-office functionalities.

- `controllers/front/BackInStock.php`
  - **Class name & parent class:** `CombinationstabBackInStockModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** Likely handles AJAX requests related to “back in stock” notifications for specific combinations. This could involve submitting a form to register for notifications when an out-of-stock combination becomes available.
- `controllers/front/CsvImport.php`
  - **Class name & parent class:** `CombinationstabCsvImportModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** Suggests functionality for importing combination data via CSV from the front-office, possibly for specific user groups or B2B scenarios. This would involve parsing CSV files and updating product combinations.
- `controllers/front/Export.php`
  - **Class name & parent class:** `CombinationstabExportModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** Provides functionality to export combination data, potentially for specific products or filtered sets, likely in CSV or similar format. Useful for B2B or data analysis.
- `controllers/front/index.php`
  - **Class name & parent class:** `CombinationstabIndexModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** Often a placeholder or a default dispatcher. It might handle general AJAX requests related to the combinations table that don’t fit into more specific controllers, or simply redirect.
- `controllers/front/PriceCalculator.php`
  - **Class name & parent class:** `CombinationstabPriceCalculatorModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** Handles AJAX requests to dynamically calculate and return prices for combinations, especially relevant for quantity discounts or complex pricing rules, ensuring real-time price updates without page reloads.
- `controllers/front/Reorder.php`
  - **Class name & parent class:** `CombinationstabReorderModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** Likely facilitates reordering previously purchased combinations, potentially from a customer’s account page or a dedicated “reorder” list.
- `controllers/front/Wishlist.php`
  - **Class name & parent class:** `CombinationstabWishlistModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** Manages AJAX interactions with a wishlist feature integrated into the combinations table, allowing customers to add specific combinations to their wishlist.

#### Back-Office Admin Controllers

These controllers provide the administrative interface for the module.

- `controllers/admin/AdminCombinationstabSearchController.php`
  - **Tab name and managed entity:** “Combinations Search” (or similar, accessible via module’s menu). Manages `Product` combinations.
  - **Responsibility:** Implements a search and management interface for product combinations. This controller likely uses a `HelperList` or `HelperForm` to display a filterable and sortable grid of combinations, allowing administrators to quickly find and potentially edit combination data (e.g., stock, price, reference) without navigating to individual product pages. It might also handle bulk actions.
- `controllers/admin/index.php`
  - **Tab name and managed entity:** N/A (entry point).
  - **Responsibility:** A common pattern for admin controller directories. This file typically serves as a default entry point or a redirector to the main `AdminCombinationstabSearchController`. It doesn’t usually contain direct logic but ensures the admin menu item points to a valid controller.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes in the `classes/` directory. This suggests the module primarily extends existing PrestaShop core functionalities and objects (`Product`, `Combination`, `Attribute`, `AttributeGroup`) rather than introducing new data models. All business logic is likely encapsulated within the main `combinationstab.php` file and its controllers.

### 4.4 JavaScript Assets (`views/js/`)

The module uses a variety of JavaScript files to provide dynamic front-office and back-office functionality.

- `combinationstab/js/admin.js`
  - **Scope:** Back-office.
  - **Details:** Handles JavaScript logic for the module’s administration pages, including form interactions, AJAX calls for configuration updates, and potentially dynamic elements within the `AdminCombinationstabSearchController` interface.
- `combinationstab/js/atc.js`
  - **Scope:** Front-office.
  - **Details:** Manages the “Add to Cart” functionality for the combinations table. It binds click events to “Add to Cart” buttons, handles quantity inputs, and sends AJAX requests to PrestaShop’s cart controller to add selected combinations (potentially multiple at once) without page reload.
- `combinationstab/js/combinationstab-switch.js`
  - **Scope:** Front-office.
  - **Details:** Implements the “Click and switch combination” feature. It listens for clicks on combination rows in the table and dynamically updates the main product image, price, and other product details on the page to reflect the selected combination.
- `combinationstab/js/combinationstab.js`
  - **Scope:** Front-office.
  - **Details:** The main front-office JavaScript file for the combinations table. It initializes the table, handles general interactions, potentially manages the display of stock, availability, and price updates based on user input or selections.
- `combinationstab/js/ctp-extras.js`
  - **Scope:** Front-office.
  - **Details:** Contains additional, non-core JavaScript functionalities for the combinations table, such as tooltip displays, minor UI enhancements, or specific interactions not covered by the main scripts.
- `combinationstab/js/ctp-filters.js`
  - **Scope:** Front-office.
  - **Details:** Implements the filtering logic for the combinations table. It listens to changes in filter dropdowns or input fields, dynamically hides/shows table rows based on selected attribute values, and updates the visible combinations.
- `combinationstab/js/ctp-mobile.js`
  - **Scope:** Front-office.
  - **Details:** Handles the responsive behavior of the combinations table, specifically implementing the “Mobile card layout” feature. It detects screen size and transforms the table into a card-based layout for better mobile usability.
- `combinationstab/js/ctp-wishlist-toast.js`
  - **Scope:** Front-office.
  - **Details:** Provides visual feedback (e.g., a toast notification) when a combination is added to a wishlist, enhancing the user experience.
- `combinationstab/lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Back-office (likely).
  - **Details:** Provides autocomplete functionality, probably for product or combination search fields within the module’s admin interfaces (e.g., `AdminCombinationstabSearchController`).
- `combinationstab/views/js/wishlist.js`
  - **Scope:** Front-office.
  - **Details:** Dedicated JavaScript for the wishlist integration, handling AJAX calls to add/remove items from the wishlist directly from the combinations table.

### 4.5 CSS Stylesheets (`views/css/`)

The module includes several CSS files for both front-office styling and back-office administration.

- `combinationstab/css/admin.css`
  - **Scope:** Back-office admin form styling.
  - **Details:** Styles the module’s configuration page and any custom admin interfaces (like `AdminCombinationstabSearchController`), ensuring a consistent look within the PrestaShop back office.
- `combinationstab/css/combinationstab.css`
  - **Scope:** Front-office customer styling.
  - **Details:** Contains the core styling for the combinations table, including table layout, cell padding, text alignment, and basic responsiveness.
- `combinationstab/css.css`
  - **Scope:** Front-office customer styling.
  - **Details:** Potentially an older or supplementary stylesheet for the front-office, or specific overrides.
- `combinationstab/lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Back-office (likely).
  - **Details:** Styles for the autocomplete search fields used in the admin panel.
- `combinationstab/views/css/ctp-admin.css`
  - **Scope:** Back-office admin form styling.
  - **Details:** Additional or specific admin styling, potentially for newer features or overrides to `admin.css`.
- `combinationstab/views/css/wishlist.css`
  - **Scope:** Front-office customer styling.
  - **Details:** Styles for the wishlist button and any associated elements within the combinations table.

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses Smarty templates for rendering all its front-office and back-office views.

#### Hook templates (`views/templates/hook/`)

These templates are designed to be rendered when specific PrestaShop hooks are executed.

- `views/templates/hook/columns/cells.tpl`
  - **Hook:** Likely rendered within the main combinations table template.
  - **Output:** Defines the structure and content of individual data cells within the table rows (e.g., displaying attribute values, price, quantity input).
- `views/templates/hook/columns/headers.tpl`
  - **Hook:** Likely rendered within the main combinations table template.
  - **Output:** Defines the header cells for the combinations table, displaying column titles like “Image”, “Size”, “Price”.
- `views/templates/hook/columns/_wishlist_btn.tpl`
  - **Hook:** Integrated into combination rows.
  - **Output:** Renders the “Add to Wishlist” button or icon for each combination in the table.
- `views/templates/hook/customer_account.tpl`
  - **Hook:** `displayCustomerAccount`
  - **Output:** Adds a link or block to the customer’s account page, potentially for accessing reorder lists, exported data, or wishlist management.
- `views/templates/hook/grid/_axis_label.tpl`
  - **Hook:** Used internally when `ctp_view_mode` is set to a grid layout.
  - **Output:** Renders labels for the axes (rows/columns) of a grid-style combination display.
- `views/templates/hook/grid/_cell.tpl`
  - **Hook:** Used internally when `ctp_view_mode` is set to a grid layout.
  - **Output:** Renders individual cells within a grid-style combination display, containing combination details.
- `views/templates/hook/productfooter.tpl`
  - **Hook:** `displayProductFooter`
  - **Output:** The primary template for rendering the combinations table when placed below the main product content. This is often the default or most common placement.
- `views/templates/hook/productfooter_grid.tpl`
  - **Hook:** `displayProductFooter` (conditional on view mode).
  - **Output:** An alternative template for `displayProductFooter` specifically for rendering the combinations in a grid layout instead of a traditional table.
- `views/templates/hook/quickViewScripts.tpl`
  - **Hook:** Potentially `displayHeader` or `actionFrontControllerSetMedia` (for quick view modals).
  - **Output:** Includes necessary JavaScript or initializes module functionality specifically for product quick view modals, ensuring the combinations table works within these pop-ups.
- `views/templates/hook/tab.tpl`
  - **Hook:** `displayProductTabContent` (or similar for product tabs).
  - **Output:** Renders the combinations table within a dedicated product tab on the product page.
- `views/templates/hook/volume_discounts.tpl`
  - **Hook:** Integrated into combination rows or as a tooltip.
  - **Output:** Displays information about quantity discounts for specific combinations.
- `views/templates/hook/_filters.tpl`
  - **Hook:** Rendered above the combinations table.
  - **Output:** Renders the attribute filtering interface for the combinations table.
- `views/templates/hook/_toolbar.tpl`
  - **Hook:** Rendered above the combinations table.
  - **Output:** Renders a toolbar, potentially containing filters, search, or other interactive elements for the combinations table.

#### Admin templates (`views/templates/admin/`)

These templates are used for the module’s back-office configuration and management screens.

- `views/templates/admin/b2b.tpl`
  - **Output:** Template for B2B-specific settings or features within the admin panel.
- `views/templates/admin/b2b_groups.tpl`
  - **Output:** Template for managing B2B customer groups or their specific pricing/visibility settings.
- `views/templates/admin/column_editor.tpl`
  - **Output:** Provides an interface for administrators to customize the order and visibility of columns in the front-office combinations table.
- `views/templates/admin/getCombinations.tpl`
  - **Output:** Used by `AdminCombinationstabSearchController` to display a list or grid of combinations.
- `views/templates/admin/getProducts.tpl`
  - **Output:** Used by `AdminCombinationstabSearchController` or other admin tools to display a list of products.
- `views/templates/admin/grid_block_editor.tpl`
  - **Output:** Interface for configuring the grid-style display of combinations, potentially defining which attributes form rows and columns.
- `views/templates/admin/menu.tpl`
  - **Output:** Renders the module’s sub-menu items within the PrestaShop back office.
- `views/templates/admin/overrides_entity.tpl`
  - **Output:** Template for managing entity-specific overrides (e.g., product-specific settings for the table).
- `views/templates/admin/overrides_fields.tpl`
  - **Output:** Template for managing field-specific overrides.
- `views/templates/admin/overrides_list.tpl`
  - **Output:** Template for listing and managing various overrides configured for the module.
- `views/templates/admin/presets.tpl`
  - **Output:** Interface for saving and loading configuration presets for the combinations table.
- `views/templates/admin/selectedProducts.tpl`
  - **Output:** Displays a list of products that have been selected for specific module configurations or overrides.
- `views/templates/admin/subtabs.tpl`
  - **Output:** Renders sub-navigation tabs within the module’s configuration interface.
- `views/templates/admin/tabs.tpl`
  - **Output:** Renders main navigation tabs for the module’s configuration.
- `views/templates/admin/tabstype.tpl`
  - **Output:** Configuration options related to how the combinations table is displayed within product tabs.

#### Front-office templates (`views/templates/front/`)

- `views/templates/front/wishlist.tpl`
  - **Output:** Renders the front-office wishlist interface, potentially a dedicated page or a modal, showing items added to the wishlist via the combinations table.

#### Other templates

- `combinationstab/lib/searchTool/views/scripts.tpl`
  - **Output:** Includes JavaScript snippets or initializes scripts for the search tool functionality.

### 4.7 Database Schema & Hooks Map

#### Database Tables

The module dossier indicates no custom SQL files. This implies the module primarily uses PrestaShop’s `ps_configuration` table to store its settings and relies on existing core tables like `ps_product_attribute`, `ps_product_attribute_combination`, `ps_product_attribute_shop`, `ps_stock_available`, etc., for combination data.

- **`ps_configuration`**: Stores all module settings (e.g., `CTP_POSITION`, `CTP_IMAGE`, `CTP_PRICE_LOGGED`, `CTP_MOBILE_CARD_LAYOUT`).

#### Registered Hooks Table

The module registers itself to various PrestaShop hooks to inject its content and functionality.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `ActionAdminControllerSetMedia` | When an admin controller is initialized and media (JS/CSS) is set. | Injects module-specific JS/CSS into the Back Office. |
| `displayRightColumn` | Renders content in the right column of the front office. | Displays the combinations table in the right column (less common for tables). |
| `displayProductFooter` | Renders content below the main product information on the product page. | Primary hook for displaying the combinations table below the product. |
| `displayHeader` | Renders content in the `<head>` section of the front office. | Injects module-specific JS/CSS, meta tags, or other head elements for front-office functionality. |
| `displayProductExtraContent` | Renders additional content blocks on the product page. | Provides flexibility to place the combinations table in a custom content block. |
| `displayRightColumnProduct` | Renders content in the right column specifically on the product page. | Similar to `displayRightColumn` but targeted to product pages. |
| `displayCustomerAccount` | Renders content on the customer’s account page. | Adds links or information related to reordering, wishlists, or exports. |
| `actionUpdateQuantity` | After a product’s quantity (stock) is updated. | Potentially triggers updates to the combinations table display (e.g., “out of stock” status). |
| `displayProductListFunctionalButtons` | Renders buttons in product listings (e.g., category pages). | Might add quick-view or comparison buttons related to combinations. |
| `displayExtraLeft` | Renders content in an extra left column (if theme supports). | Another placement option for the combinations table. |
| `CombinationsTable` | **Custom Hook** | A custom hook defined by the module itself, allowing other modules or themes to integrate with or override its table output. |
| `displayLeftColumnProduct` | Renders content in the left column specifically on the product page. | Similar to `displayRightColumnProduct` but for the left column. |
| `displayProductTabContent` | Renders content within a product tab. | Displays the combinations table in a dedicated product tab. |
| `displayCombinationsTable` | **Custom Hook** | Another custom hook, likely for the main rendering of the combinations table, offering an alternative to `displayProductFooter`. |
| `displayProductActions` | Renders content near the “Add to Cart” button on the product page. | Could be used for a compact combination selector or quick add buttons. |

## 5. Official Support & Updates

For the latest module updates, technical support, and any questions regarding the “Product page combinations table” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is ready to assist you.
