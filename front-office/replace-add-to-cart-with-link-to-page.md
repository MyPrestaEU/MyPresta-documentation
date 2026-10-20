---
title: "Replace add to cart with link to page - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Replace add to cart with link to page PrestaShop module by MyPresta.eu."
sidebar:
  label: "Replace add to cart with link to page - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Replace add to cart with link to page Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/replace-add-to-cart-with-link-to-page.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/replace-add-to-cart-with-link-to-page/)
>
> ---


# Replace add to cart with link to page

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main screen where you control the global behavior of the module.

- **Enabled**

  - **What this setting does:** This is the master switch to turn the module’s functionality on or off across your entire store.
  - **Effect of changing this setting:**
    - *When enabled:* The module will start replacing “Add to Cart” buttons with custom links based on your product-specific settings and other global configurations.
    - *When disabled:* The module will be inactive, and all “Add to Cart” buttons will revert to their default PrestaShop behavior.
  - **Recommended value:** YES (to activate the module).
  - **Merchant scenario / example:** If you’re testing the module or temporarily want to disable its functionality without uninstalling it, you can set this to NO. For active use, it should be YES.
- **Button text**

  - **What this setting does:** Defines the text that will appear on the custom button, replacing “Add to Cart.” This text can be translated into different languages.
  - **Effect of changing this setting:** The text on the button will change to your specified value.
  - **Recommended value:** Something descriptive like “Learn More,” “Request Quote,” “View Details,” or “Visit Partner Site.”
  - **Merchant scenario / example:** If you’re linking to an external site for more information, you might set this to “Learn More.” If you’re directing customers to a quote form, “Request Quote” would be appropriate.
- **Hide quantity field**

  - **What this setting does:** Controls whether the quantity input field (where customers select how many items to add) is visible on product pages when the module is active.
  - **Effect of changing this setting:**
    - *When enabled:* The quantity selector will be hidden, as it’s not relevant when the button redirects instead of adding to cart.
    - *When disabled:* The quantity selector will remain visible, which might be confusing if the button doesn’t add to cart.
  - **Recommended value:** YES.
  - **Merchant scenario / example:** Since the button no longer adds to cart, there’s usually no need for a quantity field. Hiding it simplifies the interface and avoids confusion.
- **Add to cart button on product page CSS class**

  - **What this setting does:** Allows you to specify a custom CSS class for the replacement button on the product page. This is useful for styling the button to match your theme or to make it stand out.
  - **Effect of changing this setting:** The button will inherit the styles defined by this CSS class in your theme’s stylesheet.
  - **Recommended value:** Leave empty if your theme’s default button styling is acceptable, or use a class like `btn btn-primary` or `my-custom-button` if you have specific styles.
  - **Merchant scenario / example:** If your theme uses `btn-success` for primary action buttons, you could enter `btn-success` here to make your custom button green and prominent.
- **Quantity CSS Class**

  - **What this setting does:** Allows you to specify a CSS class for the quantity input field on the product page. This is primarily for advanced styling or if you need to target the quantity field with custom CSS.
  - **Effect of changing this setting:** The quantity input field will receive this CSS class.
  - **Recommended value:** Leave empty unless you have a specific styling need.
  - **Merchant scenario / example:** A developer might use this to apply specific width or padding to the quantity field if it’s not hidden.
- **Apply module to list of products**

  - **What this setting does:** Determines whether the module’s functionality (replacing “Add to Cart” with a custom link) also applies to product buttons displayed in lists (e.g., category pages, search results, featured products on homepage).
  - **Effect of changing this setting:**
    - *When enabled:* “Add to Cart” buttons in product lists will also be replaced by the custom link.
    - *When disabled:* Only the product page’s “Add to Cart” button will be affected; product list buttons will retain their default behavior.
  - **Recommended value:** YES, for consistency across your store, especially if the custom link is a critical part of your sales funnel.
  - **Merchant scenario / example:** If all products requiring this custom link are services that need a quote, you’d want this enabled so customers don’t try to “add to cart” from a category page.
- **CSS class of element with product**

  - **What this setting does:** This is a technical setting to help the module identify the main container for a product in a list view. It’s crucial for the module to correctly find and modify the “Add to Cart” button within each product item.
  - **Effect of changing this setting:** If incorrect, the module might fail to apply its changes to product list items.
  - **Recommended value:** This is highly theme-dependent. Common values include `product-miniature`, `product-container`, `product-item`. You might need to inspect your theme’s HTML to find the correct class.
  - **Merchant scenario / example:** If your theme uses `<div class="product-card">` for each product in a list, you would enter `product-card` here.
- **CSS class of** (This likely refers to the “Add to Cart” button itself within a product list item)

  - **What this setting does:** Specifies the CSS class of the “Add to Cart” button within product list items. This helps the module target the correct button for replacement.
  - **Effect of changing this setting:** If incorrect, the module might not replace the “Add to Cart” button in product lists.
  - **Recommended value:** This is highly theme-dependent. Common values include `add-to-cart`, `product-add-to-cart`, `btn-primary`. Inspect your theme’s HTML.
  - **Merchant scenario / example:** If your theme’s “Add to Cart” button in lists has the class `btn-add-to-cart`, you’d enter that here.
- **CSS class of Quantity input on list of products**

  - **What this setting does:** Similar to the product page setting, this allows you to specify the CSS class for the quantity input field when products are displayed in a list. This is used to hide it if `Hide quantity field` is enabled.
  - **Effect of changing this setting:** If incorrect, the quantity field might remain visible in product lists even if you’ve chosen to hide it.
  - **Recommended value:** Leave empty unless you have a specific styling need or if the quantity field is not being hidden correctly. Inspect your theme’s HTML.
  - **Merchant scenario / example:** If your theme uses `product-quantity-input` for the quantity field in lists, you would enter that here.
- **Hide tooltip over button**

  - **What this setting does:** Controls whether the default PrestaShop tooltip (often showing “Add to cart” or similar) appears when hovering over the custom button.
  - **Effect of changing this setting:**
    - *When enabled:* The tooltip will be hidden, preventing potentially confusing messages.
    - *When disabled:* The default tooltip might still appear, which could conflict with the custom button’s purpose.
  - **Recommended value:** YES.
  - **Merchant scenario / example:** If your custom button says “Request Quote,” you don’t want a tooltip popping up saying “Add to cart.” Hiding it ensures a clear message.
- **Add rel=“nofollow”**

  - **What this setting does:** Adds the `rel="nofollow"` attribute to the custom link. This tells search engines not to follow the link and not to pass any “link juice” to the destination.
  - **Effect of changing this setting:**
    - *When enabled:* The link will have `rel="nofollow"`, which is useful for external links you don’t want to endorse or for internal links that aren’t critical for SEO (e.g., login pages).
    - *When disabled:* The link will be a standard followed link.
  - **Recommended value:** YES for external links, especially affiliate links or links to sites you don’t fully control. NO for internal links within your own site that you want search engines to crawl.
  - **Merchant scenario / example:** If you’re linking to an affiliate partner’s website, enabling `nofollow` is a best practice to avoid potential SEO penalties and to clearly indicate it’s a sponsored or external link.
- **Open links in new window (tab)**

  - **What this setting does:** Determines whether the custom link opens in the same browser tab or a new one.
  - **Effect of changing this setting:**
    - *When enabled:* The link will open in a new browser tab, keeping your store page open in the original tab.
    - *When disabled:* The link will open in the same tab, navigating the customer away from your store.
  - **Recommended value:** YES for external links, to keep customers on your site. NO for internal links where you want the customer to navigate within your store.
  - **Merchant scenario / example:** If you’re directing customers to an external partner site, opening in a new tab is generally better so they can easily return to your product page.
- **Module visibility for selected products**

  - **What this setting does:** This is a crucial setting that defines *which* products will have their “Add to Cart” button replaced. It works in conjunction with the product-specific settings you’ll find on each product’s edit page.
  - **Effect of changing this setting:**
    - *Enabled:* The module will only apply to products where you have explicitly defined a custom URL in their product settings.
    - *Disabled:* The module will not apply to any products, regardless of their individual settings.
  - **Recommended value:** Enabled. This allows you to selectively apply the custom link feature to specific products.
  - **Merchant scenario / example:** You only want to replace the “Add to Cart” button for your custom-made furniture, not for standard accessories. You would enable this setting, then go to each furniture product and set its custom URL.

#### Product-Specific Settings (Back Office > Catalog > Products > Edit Product > Modules Tab)

Once the module is installed and enabled, you will find new settings when editing individual products.

- **Product URL Field**
  - **What this setting does:** This is where you enter the specific URL that the “Add to Cart” button for *this particular product* will redirect to.
  - **Effect of changing this setting:** When a customer clicks the custom button on this product’s page (or in a list, if enabled), they will be taken to this URL.
  - **Recommended value:** A full, valid URL (e.g., `https://example.com/request-a-quote` or `/contact-us`).
  - **Merchant scenario / example:** For a “Custom Design Service” product, you might enter `https://yourstore.com/contact-us?subject=Custom%20Design%20Inquiry` here.

### 2.2 Dedicated Admin Screens & Controller Views

#### AdminAtcurlSearchController (Back Office > Modules > Replace add to cart with link to page > Configure > “Selected Products” Tab)

This screen provides a centralized way to manage and view which products have custom URLs configured.

- **Screen Name & Menu Location:** You access this screen by navigating to **Modules > Module Manager**, finding “Replace add to cart with link to page,” clicking “Configure,” and then selecting the “Selected Products” tab (or similar, depending on module version).
- **Available Actions & Settings:** This screen typically displays a grid or list of products that currently have a custom URL defined.
  - **Columns:** You’ll usually see columns like Product ID, Product Name, and the Custom URL.
  - **Search/Filter:** There might be search or filter options to quickly find specific products.
  - **Edit/Delete:** You might have direct links to edit the product (which takes you to the standard product edit page) or remove the custom URL for a product directly from this list.
- **Effect of changes:**
  - Modifying a URL here (if direct editing is available) or via the product edit page will immediately change where the button redirects for that product.
  - Removing a product from this list (or clearing its custom URL on the product edit page) will revert its “Add to Cart” button to the default PrestaShop behavior.
- **Recommended workflow for daily store management:** Use this screen to quickly audit which products are using the custom link feature. If you need to update many product links, this view helps you keep track. For adding new links, it’s usually more efficient to go directly to the product’s edit page.

#### index.php (atcurl/controllers/admin/index.php)

This file is a placeholder and typically does not represent a user-facing admin screen. In PrestaShop, `index.php` files within controller directories are often used to prevent direct directory listing or to include other files. It’s not a configuration screen for merchants.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration Page** | Enabled | YES | Master switch to activate/deactivate module functionality. |
|  | Button text | “Learn More” (example) | Text displayed on the custom button. |
|  | Hide quantity field | YES | Hides the quantity selector on product pages. |
|  | Add to cart button on product page CSS class | (Empty / Theme-dependent) | Custom CSS class for the button on product pages. |
|  | Quantity CSS Class | (Empty) | Custom CSS class for the quantity input on product pages. |
|  | Apply module to list of products | YES | Extends module functionality to product listing pages. |
|  | CSS class of element with product | `product-miniature` (example) | Helps module identify product containers in lists. |
|  | CSS class of (Add to Cart button in list) | `add-to-cart` (example) | Helps module identify “Add to Cart” buttons in lists. |
|  | CSS class of Quantity input on list of products | (Empty) | Custom CSS class for quantity input in product lists. |
|  | Hide tooltip over button | YES | Prevents default “Add to cart” tooltip on custom button. |
|  | Add rel=“nofollow” | YES (for external) / NO (for internal) | Adds `nofollow` attribute to the custom link. |
|  | Open links in new window (tab) | YES (for external) / NO (for internal) | Opens custom link in a new browser tab. |
|  | Module visibility for selected products | Enabled | Activates product-specific URL configuration. |
| **Product Edit Page (Modules Tab)** | Product URL Field | (Custom URL) | Defines the specific redirection URL for *this* product. |
| **AdminAtcurlSearchController** | Grid of Products with Custom URLs | N/A | Centralized view to manage products with custom links. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My “Add to Cart” button isn’t changing, even after configuring a URL.**
A1:

- **Check Module Status:** First, ensure the “Enabled” switch on the module’s main configuration page is set to YES.
- **Check Product Visibility:** Make sure “Module visibility for selected products” is set to “Enabled” on the module’s configuration page.
- **Check Product URL:** Verify that you have entered a valid URL in the “Product URL Field” for the specific product you’re testing (on the product’s edit page under the “Modules” tab).
- **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes PrestaShop caches old content.
- **Theme Compatibility:** Your theme might use non-standard CSS classes for its “Add to Cart” button or product containers. Check the “CSS class of element with product” and “CSS class of” settings on the module configuration page. You might need to use your browser’s developer tools (F12) to inspect the HTML and find the correct classes.

**Q2: The quantity field is still visible, even though I selected to hide it.**
A2:

- **Check “Hide quantity field”:** Ensure this setting is enabled on the module’s configuration page.
- **Check “CSS class of Quantity input”:** If your theme uses a non-standard class for the quantity input, the module might not be able to find and hide it. Use your browser’s developer tools to inspect the quantity input field and enter its CSS class into the “Quantity CSS Class” setting (for product page) and “CSS class of Quantity input on list of products” (for product lists).
- **Clear Cache:** Always clear your PrestaShop cache after making configuration changes.

**Q3: The module works on product pages but not on category/listing pages.**
A3:

- **Check “Apply module to list of products”:** Ensure this setting is enabled on the module’s configuration page.
- **Check CSS Classes for Lists:** The module needs to know how your theme structures product lists. Verify the “CSS class of element with product” and “CSS class of” (for the button) settings are correct for your theme. These are often different from the product page classes. Use browser developer tools to inspect elements on a category page.
- **Clear Cache:** Clear your PrestaShop cache.

**Q4: My custom button doesn’t look right (wrong color, size, etc.).**
A4:

- **CSS Class for Styling:** Use the “Add to cart button on product page CSS class” setting. Enter a CSS class that already exists in your theme and provides the desired styling (e.g., `btn btn-primary`, `btn-success`).
- **Custom CSS:** If you need unique styling, you’ll need to add custom CSS to your theme. You can target the button using the class you set in the module’s configuration, or by inspecting its HTML. For example:

  ```
  .my-custom-button-class { background-color: #ff6600; color: white; border-radius: 5px; padding: 10px 20px;}
  ```

  Add this CSS to your theme’s custom CSS file or via a custom CSS module.
- **Clear Cache:** Clear your PrestaShop cache.

**Q5: How do I translate the button text into other languages?**
A5:

- Go to **International > Translations** in your PrestaShop Back Office.
- Select “Installed modules translations,” choose your theme, and then select the language you want to translate.
- Find the “Replace add to cart with link to page” module. You will see the “Button text” field there, allowing you to enter translations for each language.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Replace add to cart with link to page” module (`atcurl`) is a standard PrestaShop module following an MVC-like pattern. It primarily extends existing PrestaShop functionality through hooks to modify the front-office display of product pages and product lists. Configuration is handled via the main module’s `getContent()` method and stored in `ps_configuration`. Product-specific URLs are stored as `Product::specific_fields` or potentially in a custom table, with an Admin Controller (`AdminAtcurlSearchController`) providing a management interface. JavaScript is heavily used to dynamically replace buttons and hide elements on the front-office.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: This module does not contain any dedicated front-office controllers. All front-office modifications are handled via hooks and JavaScript.
- **Back-Office Admin Controllers**:

  - `atcurl/controllers/admin/AdminAtcurlSearchController.php`
    - **Class name & parent class:** `AdminAtcurlSearchController` extends `ModuleAdminController`.
    - **Tab name and managed entity:** This controller is likely responsible for displaying a grid or list of products that have a custom URL configured by the module. It provides a centralized view for managing these product associations, potentially allowing for quick edits or removals of the custom URL. It does not manage a dedicated `ObjectModel` but rather interacts with product data and the module’s configuration.
  - `atcurl/controllers/admin/index.php`
    - This is a standard PrestaShop placeholder file, typically containing `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../../../"); exit;` to prevent direct directory listing and redirect to the main admin panel. It does not provide any functional controller logic.

### 4.3 Core Classes & Models (`classes/`)

The module does not appear to define any custom classes or `ObjectModel`s in the `classes/` directory. Product-specific URLs are likely stored as `Product::specific_fields` or directly within the `ps_configuration` table, keyed by product ID, or potentially a custom field added to the product entity.

### 4.4 JavaScript Assets (`views/js/`)

- `atcurl/lib/js/admin/atcurl177.js`
  - **Scope:** Back-office (Admin).
  - **Responsibility:** Likely handles logic specific to the module’s configuration page or the `AdminAtcurlSearchController` for PrestaShop 1.7.7+ versions. This could include AJAX calls for saving settings, dynamic updates to the UI, or interactions with the product search/selection tool.
- `atcurl/lib/js/front/atcurl-list-177.js`
  - **Scope:** Front-office.
  - **Responsibility:** Specifically targets product listing pages (category, search, homepage blocks). It listens for DOM changes (e.g., when products are loaded via AJAX) and dynamically replaces “Add to Cart” buttons with the custom link, hides quantity fields, and applies custom CSS classes as configured. It’s tailored for PrestaShop 1.7.7+ themes.
- `atcurl/lib/js/front/atcurl177.js`
  - **Scope:** Front-office.
  - **Responsibility:** Primarily targets the single product page. It identifies the “Add to Cart” button, replaces it with the custom link, hides the quantity input, and applies `nofollow` or `target="_blank"` attributes based on module settings. It also handles hiding tooltips. Tailored for PrestaShop 1.7.7+ themes.
- `atcurl/lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Back-office (Admin).
  - **Responsibility:** Provides autocomplete functionality, likely for selecting products in the module’s configuration or in the `AdminAtcurlSearchController` grid. This helps administrators quickly find and associate products with custom URLs.

### 4.5 CSS Stylesheets (`views/css/`)

- `atcurl/lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Back-office (Admin).
  - **Responsibility:** Styles the autocomplete dropdown and related UI elements used in the admin search tool, ensuring it integrates visually with the PrestaShop Back Office theme.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - `atcurl/views/hook/displayProductAdditionalInfo.tpl`
    - **Hook:** `displayProductAdditionalInfo`
    - **Purpose:** This template is likely rendered on the product page, providing the container or the actual custom button HTML that replaces the standard “Add to Cart” button. It would contain the logic to display the custom button text and link.
  - `atcurl/views/hook/displayProductListReviews.tpl`
    - **Hook:** `displayProductListReviews` (This hook name is unusual for button replacement and might be a typo or an indirect way to inject JS/CSS for product lists. It’s more common to use `displayProductListFunctionalButtons` or `displayProductActions` for button modifications in lists).
    - **Purpose:** If used, this template would inject JavaScript or a hidden element into product list items, which the `atcurl-list-177.js` script then uses to perform the button replacement. It’s less likely to contain the button HTML directly.
- **Admin templates (`views/templates/admin/`)**:

  - `atcurl/lib/searchTool/views/scripts.tpl`
    - **Purpose:** This template is likely included in the Back Office to load the necessary JavaScript (`autocomplete.js`) and potentially CSS (`autocomplete.css`) for the product search/selection tool used in the module’s configuration or `AdminAtcurlSearchController`.
  - `atcurl/views/tpl/selectedProducts.tpl`
    - **Purpose:** This template is used by the `AdminAtcurlSearchController` to render the grid or list of products that have custom URLs configured. It defines the table structure and how each product’s information (ID, name, URL) is displayed.
- **Front-office templates (`views/templates/front/`)**: None explicitly listed, as front-office changes are primarily handled by JS and hook templates.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not appear to create custom SQL tables.
  - **`ps_configuration`**: Stores global module settings (e.g., `ATC_URL_BUTTON_FRONT`, `ATC_URL_BUTTON_TEXT`, `ATC_URL_BLANK`, `ATC_URL_NOFOLLOW`, `ATC_HIDE_TOOLTIP`, `ATC_URL_PL`, `ATC_URL_visibility_rule`, `ATC_URL_BUTTON_QTY_HIDE`, `ATC_URL_visibility_products`, `ATC_URL_visibility_cat`).
  - **`ps_product_shop` / `ps_product_lang`**: Product-specific URLs are likely stored as an additional field associated with the product, potentially using PrestaShop’s `specific_fields` mechanism or by directly updating product properties. The module’s `install()` method would add this field.
- **Registered Hooks Table**:

| Hook Name | Scope | Execution Timing | Technical Purpose |
| --- | --- | --- | --- |
| `displayProductAdditionalInfo` | Front-Office | On product page, usually below the product description or price block. | Injects the custom button HTML or a placeholder for JS to target. |
| `ActionAdminControllerSetMedia` | Back-Office | When an admin controller loads its media (JS/CSS). | Loads admin-specific JavaScript (`atcurl177.js`, `autocomplete.js`) and CSS (`autocomplete.css`) for module configuration and product management. |
| `actionProductUpdate` | Back-Office | After a product is updated/saved in the Back Office. | Allows the module to save the custom URL associated with the product. |
| `displayHeader` | Front-Office | In the `<head>` section of every front-office page. | Injects front-office JavaScript (`atcurl177.js`, `atcurl-list-177.js`) and potentially inline CSS or configuration variables for the JS scripts. |
| `displayProductListReviews` | Front-Office | Within product list items, often near the product name or rating. | (As noted above, this hook is unusual for button replacement. It’s likely used to inject JS for list item processing, or it might be a legacy hook. Developers should verify its actual use in the module code.) |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the “Replace add to cart with link to page” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our team is dedicated to ensuring the module functions optimally with your PrestaShop store.
