---
title: "Split combinations into separate products - Merchant Manual & Configuration Guide"
description: ""
sidebar:
  label: "Split combinations into separate products - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Split combinations into separate products Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/split-combinations-into-separate-products.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/split-combinations-into-separate-products/)
>
> ---


# Split combinations into separate products

## 1. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 1.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the module, accessed by clicking “Configure” after installation.

#### General Settings

- **Enable Module:**

  - **What this setting does:** This is the master switch to activate or deactivate the module’s functionality.
  - **Effect of changing this setting:**
    - *When enabled:* The module’s features, including the ability to split products and its display logic, become active.
    - *When disabled:* The module’s functionality is completely turned off. No combinations will be split, and any existing split products will revert to their original state or be managed as regular products depending on the module’s internal logic.
  - **Recommended value:** YES (once you are ready to use the module).
  - **Merchant scenario / example:** You’re setting up the module for the first time and want to test it. You enable it to see its effects. If you need to temporarily disable it for maintenance, you can switch it off.
- **Split Mode:**

  - **What this setting does:** Determines how the module handles product combinations. You can choose between creating actual new products for each combination or just changing how they are displayed on listing pages.
  - **Effect of changing this setting:**
    - *When set to “Create separate products for each combination”:* The module will physically create new product entries in your database for each combination. Each new product will have its own ID, URL, stock, price, etc. This is the most powerful option for SEO and granular control.
    - *When set to “Show one tile per combination on category, brand, supplier, search and best-seller lists (virtual split)”:* The module will *not* create new products. Instead, it will modify how existing products with combinations are displayed on listing pages, making it *appear* as if each combination is a separate product. The actual product catalog remains unchanged. This is less impactful for SEO but can improve browsing experience.
  - **Recommended value:** “Create separate products for each combination” for maximum SEO and control, or “Show one tile per combination…” for a simpler display enhancement.
  - **Merchant scenario / example:** You want each color and size of your T-shirt to have its own product page and rank in Google. You choose “Create separate products.” If you just want to make your category pages look cleaner by showing each variation without creating new products, you choose “Show one tile per combination.”
- **Only split active products:**

  - **What this setting does:** Controls whether the module should process only products that are currently enabled in your store, or all products regardless of their active status.
  - **Effect of changing this setting:**
    - *When enabled:* Only products that are currently set to “active” in your PrestaShop catalog will have their combinations split. Inactive products will be ignored.
    - *When disabled:* The module will attempt to split combinations for all products, including those that are currently inactive.
  - **Recommended value:** YES (to avoid creating unnecessary products for items you’re not selling).
  - **Merchant scenario / example:** You have many old, inactive products in your catalog. You only want to split combinations for your current, active inventory to keep your store organized. You enable this setting.
- **Source Product Action After Split:**

  - **What this setting does:** Defines what happens to the original product (the one with combinations) after its combinations have been split into new, individual products.
  - **Effect of changing this setting:**
    - *When set to “Disable source product”:* The original product will be marked as inactive in your catalog. It will no longer be visible in the front office.
    - *When set to “Keep source product active”:* The original product will remain active and visible in your store. You might need to manually adjust its display or content to avoid confusion with the new split products.
    - *When set to “Delete source product”:* The original product will be permanently removed from your catalog. Use with extreme caution!
  - **Recommended value:** “Disable source product” or “Keep source product active” (depending on your strategy). “Delete source product” is generally not recommended unless you are absolutely sure.
  - **Merchant scenario / example:** You’ve split a “T-shirt” product into “T-shirt - Red - S”, “T-shirt - Blue - M”, etc. You want customers to only see the individual variations, so you choose “Disable source product” for the original “T-shirt.”
- **Copy Product Images:**

  - **What this setting does:** Determines whether the images associated with the original product and its combinations should be copied to the newly created split products.
  - **Effect of changing this setting:**
    - *When enabled:* The images from the original product and its specific combination will be duplicated and assigned to the new split product. This ensures each new product has relevant visuals.
    - *When disabled:* New split products will be created without any images. You would then need to manually upload images for each new product, which is very time-consuming.
  - **Recommended value:** YES.
  - **Merchant scenario / example:** You have a “Red T-shirt” combination with a specific image. When you split it into “T-shirt - Red - Small,” you want that red t-shirt image to automatically be assigned to the new product.
- **Minimum Combinations to Split:**

  - **What this setting does:** Sets a threshold for the number of combinations a product must have before the module considers splitting it. Products with fewer combinations than this value will be ignored.
  - **Effect of changing this setting:**
    - *When set to a value (e.g., 2):* Only products that have 2 or more combinations will be processed. Products with only 1 combination (or no combinations) will be skipped.
    - *When set to 0 or 1:* All products with at least one combination will be considered for splitting.
  - **Recommended value:** 2 (to avoid splitting simple products that might not benefit from it).
  - **Merchant scenario / example:** You have some products with only one combination (e.g., a “One Size” T-shirt). You don’t want to split these, but you do want to split products with multiple colors and sizes. You set this to 2.

#### Name Builder Settings

These settings control how the names of the new split products are generated.

- **Name Builder Template:**

  - **What this setting does:** Allows you to define a custom template for generating the names of the new split products. You can use placeholders for product name, attribute group names, and attribute names.
  - **Effect of changing this setting:** The module will use this template to construct the `name` field for each new product.
  - **Recommended value:** `[product_name] - [attribute_group_name]: [attribute_name]` (or similar, depending on your brand style).
  - **Merchant scenario / example:** Your original product is “Fancy Dress.” It has combinations like “Color: Red” and “Size: Small.” If your template is `[product_name] - [attribute_name]`, the new product name would be “Fancy Dress - Red.”
- **URL Builder Template:**

  - **What this setting does:** Similar to the Name Builder, this allows you to define a custom template for generating the friendly URLs (slugs) of the new split products.
  - **Effect of changing this setting:** The module will use this template to construct the `link_rewrite` field for each new product.
  - **Recommended value:** `[product_name]-[attribute_name]` (or similar, ensuring it’s SEO-friendly and unique).
  - **Merchant scenario / example:** Using the “Fancy Dress” example, if your URL template is `[product_name]-[attribute_name]`, the new URL might be `/fancy-dress-red`.
- **Separator for Multiple Attributes:**

  - **What this setting does:** Specifies the character or string used to separate multiple attribute names when they are combined in the product name or URL.
  - **Effect of changing this setting:** This character will be inserted between attribute names if a product has combinations from multiple attribute groups (e.g., Color and Size).
  - **Recommended value:** `-` (hyphen) for URLs, `,`  (comma space) for names.
  - **Merchant scenario / example:** If a product is “T-shirt - Red - Small,” the hyphen is the separator. You can change it to a slash `/` if you prefer.

#### Advanced Settings

- **Redirect Old URLs:**

  - **What this setting does:** If enabled, the module will create 301 redirects from the original product’s URL (and potentially combination-specific URLs) to the new split product’s URL. This is crucial for SEO.
  - **Effect of changing this setting:**
    - *When enabled:* Search engines and users accessing old URLs will be automatically redirected to the correct new product page, preserving SEO value and preventing broken links.
    - *When disabled:* Old URLs will lead to 404 “Page Not Found” errors, harming your SEO and user experience.
  - **Recommended value:** YES.
  - **Merchant scenario / example:** You’ve split “T-shirt” into “T-shirt - Red - Small.” If a customer or search engine tries to access the old “T-shirt” page, they will be automatically sent to the most relevant new split product page.
- **Clear Cache After Split:**

  - **What this setting does:** Automatically clears PrestaShop’s cache after a splitting operation is performed.
  - **Effect of changing this setting:**
    - *When enabled:* Ensures that changes made by the module (new products, redirects) are immediately visible on the front office without manual cache clearing.
    - *When disabled:* You might need to manually clear the cache (Advanced Parameters > Performance) for the changes to appear.
  - **Recommended value:** YES.
  - **Merchant scenario / example:** You’ve just split a large number of products. Enabling this ensures your customers see the new product listings right away without you having to manually clear the cache.

### 1.2 Dedicated Admin Screens & Controller Views

#### AdminMySplitProductsController (Back Office > Modules > Split combinations into separate products > Manage Splits)

This screen provides the interface for initiating, managing, and rolling back product splitting operations.

- **Screen Name & Menu Location:** “Manage Splits” (accessible from the main module configuration page or potentially a new menu item under “Catalog” or “Modules”).
- **Available Actions & Settings:**
  - **Product Search & Selection:** A search bar and autocomplete feature to find specific products you want to split.
  - **“Split Product” Button:** Initiates the splitting process for the selected product.
  - **“Rollback” Button:** Allows you to undo a previous split operation for a specific product, restoring the original product and removing the split ones.
  - **History Table:** A list of all products that have been split, showing:
    - Original Product Name
    - Date of Split
    - Number of Combinations Split
    - Status (e.g., “Completed,” “Rolled Back”)
    - Action buttons (e.g., “Rollback,” “View Split Products”)
- **Effect of changes:**
  - **Splitting a product:** Creates new product entries in your catalog based on the selected product’s combinations and the module’s configuration settings (names, URLs, images, etc.). The original product’s status might change (e.g., disabled).
  - **Rolling back a split:** Deletes the products created during the split and restores the original product to its state before the split (e.g., re-enables it, restores its combinations). This is a powerful undo feature.
- **Recommended workflow for daily store management:**
  1. Use the search bar to find the product you wish to split.
  2. Review the proposed names and URLs (if a preview is available).
  3. Click “Split Product.”
  4. Monitor the history table for the status.
  5. If you make a mistake or change your mind, use the “Rollback” feature from the history table.

#### index.php (mysplitproducts/controllers/admin/index.php)

This file likely serves as a placeholder or a base for the module’s admin controllers, ensuring PrestaShop’s security best practices by preventing direct directory listing. It doesn’t represent a distinct user-facing screen but is part of the module’s internal structure.

### 1.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration Page** | Enable Module | YES | Master switch for module functionality. |
|  | Split Mode | “Create separate products” | How combinations are handled (new products vs. virtual display). |
|  | Only split active products | YES | Process only active products. |
|  | Source Product Action After Split | “Disable source product” | What happens to the original product. |
|  | Copy Product Images | YES | Duplicate images to new split products. |
|  | Minimum Combinations to Split | 2 | Threshold for product splitting. |
|  | Name Builder Template | `[product_name] - [attribute_group_name]: [attribute_name]` | Defines new product names. |
|  | URL Builder Template | `[product_name]-[attribute_name]` | Defines new product friendly URLs. |
|  | Separator for Multiple Attributes | `-` (for URL), `,`  (for name) | Character to separate multiple attributes. |
|  | Redirect Old URLs | YES | Creates 301 redirects for SEO. |
|  | Clear Cache After Split | YES | Automatically clears PrestaShop cache. |
| **Manage Splits (AdminMySplitProductsController)** | Product Search & Split | N/A | Find and initiate splitting for products. |
|  | Rollback Split | N/A | Undo a previous split operation. |
|  | History Table | N/A | View and manage past split operations. |

## 2. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: After splitting products, I don’t see the new products in my categories or search results.**

- **A:** The most common reason is caching.
  - **Solution:** Go to **Advanced Parameters > Performance** in your PrestaShop Back Office. Click “Clear cache” (or “Clear Smarty cache” and “Clear cache” for all caches). If the module setting “Clear Cache After Split” is enabled, this should happen automatically, but sometimes a manual clear is needed. Also, ensure the new products are set to “active” and associated with categories.

**Q2: My old product URLs are now showing “Page Not Found” (404 errors).**

- **A:** This usually means the redirection feature is not active or not working correctly.
  - **Solution:** Go to the module’s configuration page and ensure “Redirect Old URLs” is set to YES. If it’s already enabled, clear your PrestaShop cache (Advanced Parameters > Performance). If the issue persists, check your server’s `.htaccess` file for any conflicting rewrite rules, or contact support.

**Q3: The names or URLs of my new split products look strange or are not what I expected.**

- **A:** This is controlled by the “Name Builder Template” and “URL Builder Template” settings.
  - **Solution:** Go to the module’s configuration page and review these templates. Make sure you are using the correct placeholders (`[product_name]`, `[attribute_name]`, `[attribute_group_name]`) and that the separators are appropriate. You can test different templates on a single product first. Remember to clear the cache after making changes to templates.

**Q4: Some products with combinations were not split, even though I initiated the process.**

- **A:** Check the “Minimum Combinations to Split” setting in the module’s configuration.
  - **Solution:** If a product has fewer combinations than this threshold, it will be skipped. Adjust this setting if you want to split products with fewer variations. Also, ensure “Only split active products” is not preventing inactive products from being processed if that’s your intention.

**Q5: What happens to customer carts if I split a product they’ve already added?**

- **A:** The module is designed to handle this gracefully. Existing open carts that contain a combination of a product that has been split will typically be updated to reflect the new, distinct product ID. This means the customer’s cart will still contain the correct item, now linked to its new, individual product entry. However, it’s always best to perform splits during low-traffic periods or test thoroughly.

## 3. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 3.1 Architecture Overview

The “Split combinations into separate products” module (`mysplitproducts`) is built following PrestaShop’s MVC (Model-View-Controller) pattern. It heavily leverages `ObjectModel` for data persistence, custom `AdminController` for its Back Office interface, and a set of dedicated service classes to encapsulate the complex logic of product splitting, naming, and redirection. The module extends PrestaShop’s core functionality by dynamically creating and managing product entities, handling URL rewrites, and integrating with the module manager. It relies on a robust internal logging system and a finder pattern for efficient data retrieval.

### 3.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None explicitly defined in the provided inventory. Front-office display logic for virtual splits or redirects is likely handled through hooks within the main `mysplitproducts.php` file or via overrides.
- **Back-Office Admin Controllers**:

  - `controllers/admin/AdminMySplitProductsController.php`
    - **Class Name & Parent Class:** `AdminMySplitProductsController` extends `ModuleAdminController`.
    - **Tab Name and Managed Entity:** This controller manages the core functionality of splitting and rolling back products. It presents a grid/management view for products that have been processed and allows administrators to initiate new splits or revert existing ones. It interacts with `MspSplitEngine`, `MspLogger`, and `MspRedirector` classes.
    - **Responsibility:** Handles the display of the “Manage Splits” interface, processes AJAX requests for product search, initiates the product splitting process, and manages rollback operations. It’s the central hub for the module’s administrative tasks.
  - `controllers/admin/index.php`
    - **Class Name & Parent Class:** N/A (not a class file).
    - **Responsibility:** This is a standard empty `index.php` file placed in subdirectories to prevent directory listing, enhancing security. It does not contain any functional logic for the module.

### 3.3 Core Classes & Models (`classes/`)

- `classes/index.php`
  - **Responsibility:** Standard empty `index.php` for security, preventing directory listing.
- `classes/MspAliasStore.php`
  - **What database table it interacts with:** Likely `ps_mysplitproducts_alias` (custom table) or `ps_configuration` for storing aliases/redirects.
  - **Whether it extends ObjectModel:** Unlikely to directly extend `ObjectModel` but manages data related to aliases.
  - **Key public methods and business logic encapsulated:** Manages the mapping between original product/combination IDs and their newly created split product IDs. Crucial for redirection and rollback functionality.
- `classes/MspCatalog.php`
  - **What database table it interacts with:** `ps_product`, `ps_product_lang`, `ps_product_shop`, `ps_category_product`, `ps_image`, `ps_image_shop`, `ps_stock_available`, etc. (core PrestaShop product tables).
  - **Whether it extends ObjectModel:** No, likely a service class.
  - **Key public methods and business logic encapsulated:** Provides methods for querying and manipulating core PrestaShop product data. Used by `MspSplitEngine` to retrieve product details, combinations, and update product statuses.
- `classes/MspCombinationSearchProvider.php`
  - **What database table it interacts with:** `ps_product`, `ps_product_lang`, `ps_product_attribute`, `ps_attribute`, `ps_attribute_lang`, `ps_attribute_group`, `ps_attribute_group_lang`.
  - **Whether it extends ObjectModel:** No, likely a service class.
  - **Key public methods and business logic encapsulated:** Provides functionality to search for products and their combinations, often used for the autocomplete feature in the admin controller.
- `classes/MspFinder.php`
  - **What database table it interacts with:** Various PrestaShop tables, depending on the search context.
  - **Whether it extends ObjectModel:** No, likely a utility/service class.
  - **Key public methods and business logic encapsulated:** A general-purpose data retrieval class, abstracting common database queries for products, attributes, and other entities needed by the module.
- `classes/MspLogger.php`
  - **What database table it interacts with:** Likely `ps_mysplitproducts_log` (custom table).
  - **Whether it extends ObjectModel:** Yes, or manages a custom table directly.
  - **Key public methods and business logic encapsulated:** Records all splitting and rollback operations, including timestamps, affected products, and status. Essential for the history table in `AdminMySplitProductsController` and for debugging.
- `classes/MspNameBuilder.php`
  - **What database table it interacts with:** N/A (pure logic).
  - **Whether it extends ObjectModel:** No, a utility class.
  - **Key public methods and business logic encapsulated:** Implements the logic for generating new product names and friendly URLs based on the configured templates (`MSP_NAME_BUILDER_TEMPLATE`, `MSP_URL_BUILDER_TEMPLATE`) and attribute data.
- `classes/MspProductCloner.php`
  - **What database table it interacts with:** `ps_product`, `ps_product_lang`, `ps_product_shop`, `ps_category_product`, `ps_image`, `ps_image_shop`, `ps_stock_available`, etc.
  - **Whether it extends ObjectModel:** No, a service class.
  - **Key public methods and business logic encapsulated:** The core class responsible for duplicating a product and its associated data (images, stock, categories, features, etc.) to create a new, distinct product for a specific combination. It handles the complex process of copying data across multiple PrestaShop tables.
- `classes/MspRedirector.php`
  - **What database table it interacts with:** `ps_mysplitproducts_redirect` (custom table) or `ps_url_rewrite` (core PrestaShop).
  - **Whether it extends ObjectModel:** No, a service class.
  - **Key public methods and business logic encapsulated:** Manages the creation and removal of 301 redirects from original product/combination URLs to the new split product URLs. Integrates with PrestaShop’s URL rewrite system or implements its own redirection logic.
- `classes/MspSplitEngine.php`
  - **What database table it interacts with:** Orchestrates interactions with `MspCatalog`, `MspProductCloner`, `MspNameBuilder`, `MspRedirector`, `MspLogger`.
  - **Whether it extends ObjectModel:** No, the main orchestrator service class.
  - **Key public methods and business logic encapsulated:** The central class that coordinates the entire splitting process. It takes a product ID, retrieves its combinations, uses `MspNameBuilder` to generate new details, `MspProductCloner` to create new products, `MspRedirector` for URLs, and `MspLogger` to record the operation. Also handles the rollback logic.

### 3.4 JavaScript Assets (`views/js/`)

- `lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Back-office.
  - **What event listeners it binds:** Input events on search fields.
  - **What DOM manipulation, modal popups, animation, or external third-party SDK calls it executes:** Provides an autocomplete functionality for product search fields in the admin interface, likely using AJAX calls to `AdminMySplitProductsController` to fetch product suggestions.
- `views/js/admin.js`
  - **Scope:** Back-office.
  - **What event listeners it binds:** Click events on buttons (e.g., “Split Product,” “Rollback”), form submissions.
  - **What DOM manipulation, modal popups, animation, or external third-party SDK calls it executes:** Handles the interactive elements of the `AdminMySplitProductsController` dashboard, including initiating split/rollback actions, updating the history table, and displaying loading indicators or success/error messages.
- `views/js/configure.js`
  - **Scope:** Back-office.
  - **What event listeners it binds:** Change events on configuration fields, form submissions.
  - **What DOM manipulation, modal popups, animation, or external third-party SDK calls it executes:** Manages the main module configuration form. May include logic for showing/hiding fields based on other selections (e.g., split mode), form validation, and AJAX saving of configuration settings.
- `views/js/listing.js`
  - **Scope:** Front-office (for virtual split mode).
  - **What event listeners it binds:** Potentially `prestashop.on` events for product list updates, DOM ready.
  - **What DOM manipulation, modal popups, animation, or external third-party SDK calls it executes:** If the “virtual split” mode is active, this script would dynamically modify product listings on category, search, and other pages to display individual combination tiles. This might involve cloning existing product elements, updating their content (name, image, price), and re-rendering parts of the product grid.

### 3.5 CSS Stylesheets (`views/css/`)

- `lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Back-office admin form styling.
  - **Main UI components and containers it styles:** Styles for the autocomplete dropdown, search input fields, and suggestion lists within the admin panel.
  - **Key CSS class selectors developers can override in their theme:** `.autocomplete-suggestions`, `.autocomplete-suggestion`, `.autocomplete-selected`.
- `views/css/admin.css`
  - **Scope:** Back-office admin form styling.
  - **Main UI components and containers it styles:** General styling for the module’s configuration pages and the “Manage Splits” dashboard, including tables, buttons, form elements, and status indicators.
  - **Key CSS class selectors developers can override in their theme:** `.mysplitproducts-config`, `.mysplitproducts-dashboard`, `.mysplitproducts-table`, `.mysplitproducts-status-success`, `.mysplitproducts-status-error`.

### 3.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**: None explicitly listed, but the module might use hooks for front-office display in virtual split mode (e.g., `displayProductList`, `displayProductExtraContent`) which would be handled by the main `mysplitproducts.php` file.
- **Admin templates (`views/templates/admin/`)**:
  - `views/templates/admin/configure_shell.tpl`
    - **Purpose:** This template likely serves as the main wrapper or shell for the module’s configuration page, including the general settings and possibly tabs or sections for other settings. It provides the overall layout for `getContent()`.
  - `views/templates/admin/dashboard.tpl`
    - **Purpose:** This template renders the “Manage Splits” dashboard, including the product search input, the “Split Product” button, and the history table of split operations. It’s the view for `AdminMySplitProductsController`.
- **Front-office templates (`views/templates/front/`)**: None explicitly listed. Front-office rendering for virtual splits would likely involve modifying existing theme templates via hooks or overrides, or dynamically injecting content via JavaScript (`listing.js`).

### 3.7 Database Schema & Hooks Map

- **Database Tables**:

  - `ps_mysplitproducts_log`: Stores a history of all split and rollback operations, including `id_product_original`, `id_product_split`, `action` (split/rollback), `date_add`, `status`.
  - `ps_mysplitproducts_redirect`: Stores 301 redirect mappings from old URLs to new split product URLs, including `old_url`, `new_url`, `id_product_original`, `id_product_split`.
  - `ps_mysplitproducts_alias`: Stores mappings between original product/combination IDs and the new split product IDs, crucial for internal lookups and rollbacks.
  - Configuration records stored in `ps_configuration`:
    - `MSP_MODE`: (int) 0 for virtual, 1 for real split.
    - `MSP_ACTIVE_ONLY`: (bool) Only split active products.
    - `MSP_SOURCE_ACTION`: (int) Action for source product (disable, keep active, delete).
    - `MSP_IMAGE_COPY`: (bool) Copy images to new products.
    - `MSP_MIN_COMBINATIONS`: (int) Minimum combinations for splitting.
    - `MSP_NAME_BUILDER_TEMPLATE`: (string) Template for new product names.
    - `MSP_URL_BUILDER_TEMPLATE`: (string) Template for new product URLs.
    - `MSP_SEPARATOR_MULTIPLE_ATTRIBUTES`: (string) Separator for multiple attributes.
    - `MSP_REDIRECT_OLD_URLS`: (bool) Enable 301 redirects.
    - `MSP_CLEAR_CACHE_AFTER_SPLIT`: (bool) Clear cache automatically.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Potentially injects CSS/JS for front-office virtual split, or meta tags for SEO. |
| `displayBackOfficeHeader` | In the `<head>` section of every Back Office page. | Injects CSS/JS for module’s admin pages (`admin.css`, `admin.js`, `autocomplete.css`, `autocomplete.js`). |
| `actionProductUpdate` | After a product is updated. | Potentially triggers re-evaluation for splitting or updates related to split products. |
| `actionProductDelete` | After a product is deleted. | Handles cleanup of split products or redirects if the original product is deleted. |
| `actionProductSave` | Before or after a product is saved. | Intercepts product saves to manage split products or related data. |
| `actionObjectProductAddAfter` | After a new product is added. | Potentially triggers splitting for newly added products if configured. |
| `actionObjectProductUpdateAfter` | After a product is updated. | Updates related split products or redirects. |
| `actionObjectProductDeleteAfter` | After a product is deleted. | Cleans up associated split products and redirects. |
| `displayProductList` | When a product list is rendered (category, search, etc.). | **Crucial for virtual split mode.** Modifies the product list to display individual combination tiles. |
| `displayProductExtraContent` | On the product page, below the main content. | Could be used to display links to other combinations or a message about split products. |
| `displayAdminProductsExtra` | On the product edit page in the Back Office. | Adds a custom tab or section to the product edit page for managing splits related to that specific product. |
| `actionAdminProductsListingResultsModifier` | Modifies the results of the product listing in the Back Office. | Adjusts the product list to show/hide original products or highlight split products. |
| `actionFrontControllerSetMedia` | Before a front controller renders its template. | Registers front-office JavaScript (`listing.js`) and CSS for virtual split mode. |
| `moduleRoutes` | During URL routing initialization. | Registers custom routes for split products or redirects. |

## 4. Official Support & Updates

For the latest module updates, bug fixes, and comprehensive support, please refer to your customer account at MyPresta.eu.

- **Module Updates:** Log in to your account at [MyPresta.eu Order History & Downloads](https://mypresta.eu/my-account/orders/) to download the most recent version of “Split combinations into separate products.”
- **Technical Support:** If you encounter any issues or have questions that are not covered in this guide, please open a support ticket through your MyPresta.eu customer account. Our team of experts is ready to assist you.
