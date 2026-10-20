---
title: "Product list attributes (combinations) - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Product list attributes (combinations) PrestaShop module by MyPresta.eu."
sidebar:
  label: "Product list attributes (combinations)"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Product list attributes (combinations) Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-list-attributes-combinations.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/product-list-attributes-combinations/)
>
> ---


# Product list attributes (combinations)

## 1. Requirements & Compatibility

-   **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
-   **PHP Compatibility**: PHP 5.6 - 8.5
-   **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required, which are typically available on most modern web hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)
After installation, clicking "Configure" will take you to the main settings page for the "Product list attributes (combinations)" module. This is where you control how combinations are displayed on your product lists.

#### General Settings

-   **Display combinations on product list:**
    -   **What this setting does:** This is the master switch for the module. It controls whether product combinations are shown on product listing pages at all.
    -   **Effect of changing this setting:**
        -   *When enabled (YES):* The module will inject the combination selection interface into your product list templates, allowing customers to choose variants directly.
        -   *When disabled (NO):* The module will be inactive on the front office, and product lists will behave as standard PrestaShop, requiring customers to visit the product page to select combinations.
    -   **Recommended value:** YES (to utilize the module's core functionality).
    -   **Merchant scenario / example:** If you want to offer a faster shopping experience, enable this. If you prefer customers to always land on the product page for more details, disable it.

-   **Display "Add to cart" button:**
    -   **What this setting does:** Determines if an "Add to cart" button is shown alongside the combination selectors on the product list.
    -   **Effect of changing this setting:**
        -   *When enabled (YES):* An "Add to cart" button will appear next to the combination options. Once a customer selects a combination, they can click this button to add it to their cart.
        -   *When disabled (NO):* The combination selectors will still be visible, but customers will need to click the product image or name to go to the product page to add it to the cart. This might be useful if you want to show options but still encourage product page visits.
    -   **Recommended value:** YES (for maximum convenience and conversion).
    -   **Merchant scenario / example:** For a quick-buy experience, enable this. If your products require extensive reading or customization before purchase, you might disable it to guide customers to the product page.

-   **Display quantity input:**
    -   **What this setting does:** Controls whether a quantity input field is displayed next to the "Add to cart" button on the product list.
    -   **Effect of changing this setting:**
        -   *When enabled (YES):* Customers can specify the quantity of a chosen combination they wish to add to their cart directly from the product list.
        -   *When disabled (NO):* The "Add to cart" button will add a single unit of the selected combination. Customers would then need to adjust quantities in the cart or on the product page.
    -   **Recommended value:** YES (for most stores, as it offers more flexibility).
    -   **Merchant scenario / example:** If customers often buy multiple units of the same item (e.g., socks, stationery), enable this. If your products are typically bought one at a time, you might disable it for a cleaner look.

-   **Display product reference:**
    -   **What this setting does:** Shows or hides the product's reference number (SKU) next to the combination options.
    -   **Effect of changing this setting:**
        -   *When enabled (YES):* The product reference will be visible, which can be helpful for customers tracking specific items or for B2B clients.
        -   *When disabled (NO):* The reference will not be displayed, leading to a cleaner, less cluttered interface.
    -   **Recommended value:** NO (unless your target audience specifically benefits from seeing references).
    -   **Merchant scenario / example:** For B2B stores or technical products where customers often order by SKU, enable this. For general retail, it's usually not necessary.

-   **Display product EAN13/JAN:**
    -   **What this setting does:** Shows or hides the product's EAN13 or JAN barcode number.
    -   **Effect of changing this setting:**
        -   *When enabled (YES):* The EAN13/JAN will be visible, which can be useful for customers who need to cross-reference products using these identifiers.
        -   *When disabled (NO):* The EAN13/JAN will not be displayed.
    -   **Recommended value:** NO (similar to reference, only enable if there's a specific customer need).
    -   **Merchant scenario / example:** Rarely needed for front-office display, but could be useful for specific niches or B2B.

-   **Display product UPC:**
    -   **What this setting does:** Shows or hides the product's UPC barcode number.
    -   **Effect of changing this setting:**
        -   *When enabled (YES):* The UPC will be visible.
        -   *When disabled (NO):* The UPC will not be displayed.
    -   **Recommended value:** NO (similar to EAN13/JAN).
    -   **Merchant scenario / example:** Similar to EAN13/JAN, typically not a front-office requirement for most retail.

-   **Display product weight:**
    -   **What this setting does:** Shows or hides the product's weight next to the combination options.
    -   **Effect of changing this setting:**
        -   *When enabled (YES):* The product weight will be visible, which can be important for customers concerned about shipping costs or handling.
        -   *When disabled (NO):* The weight will not be displayed.
    -   **Recommended value:** NO (unless weight is a critical factor for your products).
    -   **Merchant scenario / example:** For products where weight is a significant purchasing factor (e.g., bulk goods, heavy machinery parts), enable this.

-   **Display product price:**
    -   **What this setting does:** Controls whether the price of the selected combination is dynamically updated and displayed on the product list.
    -   **Effect of changing this setting:**
        -   *When enabled (YES):* As a customer selects different combinations, the price displayed will update to reflect the specific combination's price (including any attribute price impacts).
        -   *When disabled (NO):* The price shown on the product list will remain the base product price, and customers might need to infer combination pricing or go to the product page.
    -   **Recommended value:** YES (crucial for transparency and informed purchasing).
    -   **Merchant scenario / example:** Always enable this for clear pricing. If disabled, customers might be confused by price changes at checkout.

-   **Display product availability:**
    -   **What this setting does:** Shows or hides the stock availability status for the selected combination (e.g., "In stock," "Out of stock," "Last items!").
    -   **Effect of changing this setting:**
        -   *When enabled (YES):* Customers will see the stock status, helping them make purchasing decisions and preventing frustration from trying to order out-of-stock items.
        -   *When disabled (NO):* Stock status will not be shown, potentially leading to customers attempting to add out-of-stock items to their cart.
    -   **Recommended value:** YES (highly recommended for managing customer expectations).
    -   **Merchant scenario / example:** Essential for any store to prevent orders for unavailable items. Always enable.

-   **Display product description:**
    -   **What this setting does:** Shows or hides a short description of the product below the combinations.
    -   **Effect of changing this setting:**
        -   *When enabled (YES):* A brief product description will appear, offering more context without requiring a click to the product page.
        -   *When disabled (NO):* The description will not be shown, keeping the product list concise.
    -   **Recommended value:** NO (product lists are usually for quick browsing; detailed descriptions belong on the product page).
    -   **Merchant scenario / example:** If you have very short, impactful descriptions that aid quick decisions, you might enable this. Otherwise, keep it off to avoid clutter.

-   **Display product short description:**
    -   **What this setting does:** Similar to "Display product description," but specifically for the short description field.
    -   **Effect of changing this setting:**
        -   *When enabled (YES):* The product's short description will be visible.
        -   *When disabled (NO):* The short description will not be displayed.
    -   **Recommended value:** NO (for the same reasons as the full description).
    -   **Merchant scenario / example:** Use sparingly, only if your short descriptions are extremely concise and crucial for list-view purchasing.

-   **Display product images:**
    -   **What this setting does:** Determines if the product image updates dynamically when a customer selects a different combination (e.g., selecting a "blue" shirt shows the blue shirt image).
    -   **Effect of changing this setting:**
        -   *When enabled (YES):* The main product image on the list will change to reflect the image associated with the selected combination. This provides a rich visual feedback.
        -   *When disabled (NO):* The product image will remain static, showing the default product image regardless of the selected combination.
    -   **Recommended value:** YES (highly recommended for visual confirmation and a better user experience).
    -   **Merchant scenario / example:** Crucial for clothing, electronics, or any product where visual representation of the variant is important.

-   **Display product attributes as:**
    -   **What this setting does:** This is a crucial setting that defines how the combination options (e.g., size, color) are presented to the customer.
    -   **Effect of changing this setting:**
        -   *Dropdown list:* Attributes will appear as standard HTML dropdown `<select>` elements. This is compact and suitable for many options.
        -   *Radio buttons:* Attributes will appear as radio buttons. Good for a small number of distinct options.
        -   *Color picker:* If your attributes are defined as "color" type in PrestaShop, this will display them as clickable color swatches.
    -   **Recommended value:**
        -   *Color picker* for color attributes.
        -   *Dropdown list* for attributes with many options (e.g., sizes S-XXL).
        -   *Radio buttons* for attributes with few, distinct options (e.g., "Yes/No," "With/Without").
    -   **Merchant scenario / example:** For a clothing store, you'd likely use "Color picker" for colors and "Dropdown list" for sizes. For a simple product with two options like "Gift Wrapped: Yes/No," radio buttons might be best.

-   **Display product attributes for:**
    -   **What this setting does:** Allows you to specify which product attributes should have their combinations displayed on the product list. You can select specific attribute groups (e.g., "Size," "Color," "Material").
    -   **Effect of changing this setting:**
        -   *Selected attribute groups:* Only combinations involving the chosen attribute groups will be displayed. For example, if you select "Color" and "Size," customers will see options for colors and sizes.
        -   *No selection:* If nothing is selected, the module might default to displaying all attributes or none, depending on the module's internal logic. It's best to explicitly select.
    -   **Recommended value:** Select all relevant attribute groups that define your product combinations.
    -   **Merchant scenario / example:** If you sell T-shirts in different colors and sizes, select "Color" and "Size." If you also have a "Material" attribute but don't want to show it on the list, leave it unselected.

-   **Hook to display module:**
    -   **What this setting does:** Determines where on your product listing pages the combination selectors will be injected.
    -   **Effect of changing this setting:**
        -   *displayProductListFunctionalButtons:* This hook is typically located near the "Add to cart" button or other functional elements on product list items.
        -   *displayProductListReviews:* Often near review stars or review counts.
        -   *displayProductListPrice:* Usually near the product price.
        -   *displayProductListExtraContent:* A general hook for extra content, often at the bottom of the product card.
        -   *displayProductListFooter:* At the very bottom of the product card.
    -   **Recommended value:** `displayProductListFunctionalButtons` or `displayProductListExtraContent` are common choices, but this depends heavily on your theme's layout. You may need to experiment to find the best visual placement.
    -   **Merchant scenario / example:** If your theme has a clean area below the product name and price, `displayProductListFunctionalButtons` might fit well. If you want the options to appear more prominently, `displayProductListExtraContent` might be better.

-   **Exclude products from module:**
    -   **What this setting does:** Allows you to specify individual products by their ID that should *not* display combinations on the product list, even if the module is generally enabled.
    -   **Effect of changing this setting:**
        -   *Entering product IDs (comma-separated):* The specified products will revert to standard PrestaShop behavior on product lists, requiring a click to the product page for combination selection.
        -   *Leaving empty:* All products with combinations will display them on the list.
    -   **Recommended value:** Leave empty unless you have specific products that require a full product page visit.
    -   **Merchant scenario / example:** You might have a few complex products with many attributes, or products that require a detailed configurator, where you prefer customers to land on the product page first.

-   **Exclude categories from module:**
    -   **What this setting does:** Allows you to specify categories by their ID that should *not* display combinations on their product lists.
    -   **Effect of changing this setting:**
        -   *Entering category IDs (comma-separated):* Products within these categories will not show combinations on their respective listing pages.
        -   *Leaving empty:* All categories will display product combinations.
    -   **Recommended value:** Leave empty unless you have specific categories where this feature is not desired.
    -   **Merchant scenario / example:** If you have a "Clearance" category where all products are single-variant and you want to keep the display very minimal, you might exclude it.

#### 2.1.1 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|---|
| Module Configuration | Display combinations on product list | YES | Master switch to enable/disable combination display on product lists. |
| Module Configuration | Display "Add to cart" button | YES | Shows an "Add to cart" button next to combinations for direct purchase. |
| Module Configuration | Display quantity input | YES | Allows customers to select quantity directly on product list. |
| Module Configuration | Display product reference | NO | Shows/hides product SKU. |
| Module Configuration | Display product EAN13/JAN | NO | Shows/hides product EAN13/JAN. |
| Module Configuration | Display product UPC | NO | Shows/hides product UPC. |
| Module Configuration | Display product weight | NO | Shows/hides product weight. |
| Module Configuration | Display product price | YES | Dynamically updates price based on selected combination. |
| Module Configuration | Display product availability | YES | Shows stock status for selected combination. |
| Module Configuration | Display product description | NO | Shows/hides full product description. |
| Module Configuration | Display product short description | NO | Shows/hides short product description. |
| Module Configuration | Display product images | YES | Dynamically updates product image based on selected combination. |
| Module Configuration | Display product attributes as | Dropdown, Radio, Color picker | Defines visual presentation of attribute options. |
| Module Configuration | Display product attributes for | Select relevant groups | Specifies which attribute groups to display. |
| Module Configuration | Hook to display module | `displayProductListFunctionalButtons` | Determines visual placement of the module on product cards. |
| Module Configuration | Exclude products from module | Leave empty | Comma-separated product IDs to exclude from the feature. |
| Module Configuration | Exclude categories from module | Leave empty | Comma-separated category IDs to exclude from the feature. |

### 2.2 Dedicated Admin Screens & Controller Views

This module uses custom admin controllers for internal management, but these are not typically accessed directly by the merchant for daily configuration. They are primarily for internal module operations or advanced debugging.

#### 2.2.1 AdminPlaSearchController (Back Office > Modules > Product list attributes (combinations) > Search Configuration)
-   **Screen Name & Menu Location:** This controller is likely used for internal search configuration or data management related to how combinations are indexed or retrieved. It might not have a direct, visible menu item for the merchant, or it could be an internal tab within the module's main configuration.
-   **Available Actions & Settings:** This screen would typically present a grid or list view of data (e.g., indexed products, attribute mappings) and might offer actions like "Rebuild Index," "Clear Cache," or "Edit Search Settings."
-   **Effect of changes:** Changes here would impact the performance or accuracy of combination display, especially in large catalogs. Incorrect settings could lead to combinations not appearing or loading slowly.
-   **Recommended workflow for daily store management:** Merchants generally do not need to interact with this screen unless advised by support or for advanced troubleshooting. The module's main configuration page handles all user-facing settings.

#### 2.2.2 index.php (pla/controllers/admin/index.php)
-   **Screen Name & Menu Location:** This `index.php` file within the `admin` controller directory is a common PrestaShop practice to prevent directory listing. It typically doesn't represent a user-facing screen but rather ensures security and proper routing for other admin controllers within the module.
-   **Available Actions & Settings:** No direct merchant-facing actions or settings.
-   **Effect of changes:** No direct effect on store display or data, as it's a structural file.
-   **Recommended workflow for daily store management:** No interaction required.

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: Combinations are not showing up on my product list. What should I do?**
A:
1.  **Check Module Status:** Go to **Modules > Module Manager**, find "Product list attributes (combinations)", and ensure it's installed and enabled.
2.  **Check Module Configuration:** Go to the module's configuration page. Ensure "Display combinations on product list" is set to YES.
3.  **Check Attribute Groups:** Make sure you have selected the correct "Display product attributes for" groups (e.g., "Size," "Color").
4.  **Check Exclusions:** Verify that the product or category you're testing is not listed in "Exclude products from module" or "Exclude categories from module."
5.  **Clear Cache:** Go to **Advanced Parameters > Performance** and click "Clear cache" (or "Clear Smarty cache" in older versions). Sometimes, old cached files prevent new module content from appearing.
6.  **Theme Compatibility:** Your theme might be heavily customized and not use the standard PrestaShop hooks. Try changing the "Hook to display module" setting to a different hook (e.g., `displayProductListExtraContent`) and clear cache. If issues persist, contact your webmaster or MyPresta.eu support.

**Q: The "Add to cart" button or quantity input isn't showing.**
A:
1.  **Check Module Configuration:** Ensure "Display 'Add to cart' button" and "Display quantity input" are both set to YES in the module's configuration.
2.  **Clear Cache:** Always clear your PrestaShop cache after making configuration changes.

**Q: The product image doesn't change when I select a different combination.**
A:
1.  **Check Module Configuration:** Ensure "Display product images" is set to YES.
2.  **Product Images:** Verify that your product combinations actually have associated images. In your product's back office page, go to the "Combinations" tab and ensure each combination has images linked to it.
3.  **Clear Cache:** Clear your PrestaShop cache.

**Q: The styling (colors, alignment) of the combinations looks off on my store.**
A:
This is usually a CSS conflict with your theme.
1.  **Clear Cache:** Sometimes, clearing cache helps.
2.  **Theme Customization:** Your theme might have specific styling rules that override or conflict with the module's default CSS. This requires a webmaster or developer to inspect the CSS and make adjustments in your theme's stylesheet. The module provides its own CSS files, but themes can always override them.

**Q: Does this module work with multi-language stores?**
A: Yes, the module is designed to be compatible with PrestaShop's multi-language features. Attribute names and values will display in the selected front-office language, provided they are correctly translated in your PrestaShop back office (Catalog > Attributes & Features).

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview of the "Product list attributes (combinations)" module for developers and webmasters.

### 4.1 Architecture Overview
The module follows a standard PrestaShop MVC (Model-View-Controller) pattern, primarily extending `Module` for its core functionality and `ModuleFrontController` for AJAX interactions. It leverages PrestaShop's hook system to inject its content into product listing templates. The module's main logic resides in `index.php` (the main module file), which handles installation, uninstallation, and the `getContent()` method for back-office configuration. Front-office display is managed through Smarty templates rendered via hooks, with dynamic interactions powered by JavaScript and AJAX.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers
-   `controllers/front/ajax.php`
    *   **Class name & parent class:** `PlaAjaxModuleFrontController` extends `ModuleFrontController`.
    *   **Responsibility:** This controller handles all AJAX requests from the front office. When a customer interacts with the combination selectors (e.g., changes a size or color), this controller is responsible for receiving the request, processing it (e.g., fetching updated prices, stock, images for the selected combination), and returning a JSON response to update the front-end dynamically without a full page reload. It's crucial for the interactive experience of the module.
-   `controllers/front/index.php`
    *   **Class name & parent class:** `PlaIndexModuleFrontController` extends `ModuleFrontController`.
    *   **Responsibility:** This is a placeholder front controller, often used to prevent directory listing or as a fallback for module-specific routes. In this module's context, it might not have direct, active routing but serves as a standard PrestaShop practice. The primary front-office interaction is via `ajax.php`.

#### Back-Office Admin Controllers
-   `controllers/admin/AdminPlaSearchController.php`
    *   **Class name & parent class:** `AdminPlaSearchController` extends `ModuleAdminController`.
    *   **Tab name and managed entity:** This controller likely manages internal search or indexing mechanisms for product combinations. It might not have a direct menu entry but could be accessed internally by the module for tasks like rebuilding a search index for combinations. It would typically manage a virtual entity related to search data rather than a direct `ObjectModel`.
-   `controllers/admin/index.php`
    *   **Class name & parent class:** Not a direct controller class, but a standard `index.php` file.
    *   **Tab name and managed entity:** This file is a security measure to prevent directory listing of the `admin` folder. It does not represent a functional admin screen itself.

### 4.3 Core Classes & Models (`classes/`)
The module dossier indicates no custom classes or models in the `classes/` directory. This suggests that the module primarily operates by extending existing PrestaShop core functionalities (like `Product`, `Combination`) and uses direct database queries or PrestaShop's `Db` class for data interaction, rather than defining its own `ObjectModel` entities. All core logic is likely encapsulated within the main module file (`pla/index.php`) and its controllers.

### 4.4 JavaScript Assets (`views/js/`)
-   `pla/lib/searchTool/views/js/autocomplete.js`
    *   **Scope:** Potentially both Front-office (for live search functionality if integrated) and Back-office (for admin search fields). Given the module's focus, it's more likely for back-office search configuration related to `AdminPlaSearchController`.
    *   **Details:** Handles autocomplete functionality, likely for searching products or attributes within the module's admin configuration or a custom search feature. It would bind to input fields, listen for `keyup` events, and make AJAX calls to fetch suggestions.
-   `pla/views/templates/js/pla.js`
    *   **Scope:** Front-office.
    *   **Details:** This is the main JavaScript file for the front-office functionality.
        *   **Event Listeners:** Binds `change` events to combination selectors (dropdowns, radio buttons, color pickers) on product list items.
        *   **DOM Manipulation:** Updates product prices, stock status, product images, and "Add to cart" button states based on selected combinations.
        *   **AJAX Calls:** Makes AJAX requests to `controllers/front/ajax.php` to retrieve updated combination data (price, stock, image URL, etc.) when a selection changes.
        *   **Module Initialization:** Likely contains code to initialize the combination selectors on page load and re-initialize them after AJAX updates (e.g., infinite scroll, category filtering).

### 4.5 CSS Stylesheets (`views/css/`)
-   `pla/css.css`
    *   **Scope:** Likely Front-office.
    *   **Details:** General styling for the combination display elements on product lists. Contains base styles for dropdowns, radio buttons, quantity inputs, and "Add to cart" buttons as rendered by the module.
-   `pla/lib/searchTool/views/css/autocomplete.css`
    *   **Scope:** Potentially both Front-office and Back-office.
    *   **Details:** Styles for the autocomplete suggestions list and input fields, likely used in conjunction with `autocomplete.js`.
-   `pla/views/templates/css/pla-classic.css`
    *   **Scope:** Front-office.
    *   **Details:** Specific styling tailored for older PrestaShop themes (e.g., Classic theme or similar structures). Might contain more explicit overrides or fallback styles.
-   `pla/views/templates/css/pla.css`
    *   **Scope:** Front-office.
    *   **Details:** Primary styling for the module's front-office elements, potentially for newer PrestaShop versions or a more generic approach. Contains styles for the combination wrappers, attribute options, and dynamic elements.
    *   **Key CSS class selectors:** Developers can expect classes like `.pla-combinations-wrapper`, `.pla-attribute-group`, `.pla-attribute-option`, `.pla-add-to-cart-btn`, `.pla-quantity-input`, `.pla-price-display`, `.pla-availability-status` to be present and can override them in their theme's `custom.css` or `theme.css`.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)
-   `pla/views/templates/hook/pla.tpl`
    *   **Hook:** Primarily intended for hooks like `displayProductListFunctionalButtons`, `displayProductListExtraContent`, etc.
    *   **Output:** This is the main template responsible for rendering the combination selectors, "Add to cart" button, quantity input, price, and availability on each product item in the product list. It iterates through available attribute groups and values, generating the appropriate HTML (dropdowns, radio buttons, color swatches) based on module configuration.

#### Admin templates (`views/templates/admin/`)
-   `pla/views/templates/admin/admin.tpl`
    *   **Purpose:** This template is used for the module's main configuration page in the PrestaShop back office (accessed via `getContent()` in `pla/index.php`). It contains the forms for all the settings described in Section 4.1.
-   `pla/views/templates/admin/selectedCa.tpl`
    *   **Purpose:** Likely a partial template used within an admin form or grid to display selected categories (e.g., for the "Exclude categories from module" setting). It would render a list of selected categories, possibly with options to remove them.
-   `pla/views/templates/admin/selectedProducts.tpl`
    *   **Purpose:** Similar to `selectedCa.tpl`, but for selected products (e.g., for the "Exclude products from module" setting). It would display a list of selected products.

#### JavaScript templates (`views/templates/js/`)
-   `pla/views/templates/js/pla_admin.tpl`
    *   **Scope:** Back-office.
    *   **Output:** This template likely contains JavaScript code specifically for the admin panel. It might include scripts for handling dynamic form elements, AJAX calls within the admin, or initializing components on the module's configuration page.

### 4.7 Database Schema & Hooks Map

#### Database Tables
The module dossier indicates no custom SQL files. This implies that the module primarily stores its configuration settings in PrestaShop's `ps_configuration` table.
-   **`ps_configuration`**: Stores module settings (e.g., `PLA_DISPLAY_COMBINATIONS`, `PLA_DISPLAY_ADD_TO_CART`, `PLA_EXCLUDE_PRODUCTS`, `PLA_HOOK_NAME`, etc.). These keys are typically prefixed with `PLA_` or `MYPRESTA_PLA_`.

#### Registered Hooks Table
The module registers and utilizes several PrestaShop hooks to integrate its functionality.

| Hook Name | Execution Timing | Technical Purpose |
|---|---|---|
| `displayHeader` | In the `<head>` section of every front-office page. | To include necessary CSS and JavaScript files for the module's front-office functionality. |
| `displayProductListFunctionalButtons` | Within each product item on product listing pages, typically near action buttons. | A common hook for injecting the combination selectors and "Add to cart" button. |
| `displayProductListReviews` | Within each product item on product listing pages, often near review elements. | Alternative hook for displaying combination options. |
| `displayProductListPrice` | Within each product item on product listing pages, near the product price. | Alternative hook for displaying combination options. |
| `displayProductListExtraContent` | A general-purpose hook within each product item for additional content. | Flexible hook for injecting the combination selectors, often at the bottom of the product card. |
| `displayProductListFooter` | At the very bottom of each product item on product listing pages. | Another alternative hook for displaying combination options. |
| `actionFrontControllerSetMedia` | Before a front controller renders its content, allowing modules to add assets. | To conditionally load specific JS/CSS assets only when needed by the module on relevant pages. |
| `actionProductUpdate` | After a product is updated in the back office. | Potentially used to clear module-specific caches or re-index product combination data if the module has an internal indexing mechanism. |
| `actionAttributeGroupUpdate` / `actionAttributeUpdate` | After attribute groups or attributes are updated. | Similar to `actionProductUpdate`, for cache clearing or re-indexing. |

## 5. Official Support & Updates
For the latest module updates, bug fixes, and official support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our team is dedicated to providing assistance and ensuring the smooth operation of your module.
