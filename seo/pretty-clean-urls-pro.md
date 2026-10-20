---
title: "Pretty / Clean URLs PRO - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Pretty / Clean URLs PRO PrestaShop module by MyPresta.eu."
sidebar:
  label: "Pretty / Clean URLs PRO - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Pretty / Clean URLs PRO Module on MyPresta.eu](https://mypresta.eu/modules/seo/pretty-clean-urls-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/seo/pretty-clean-urls-pro/)
>
> ---


# Pretty / Clean URLs PRO

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.0.0 - 1.7.4.x, 1.7.5.0 - 1.7.7.x, 1.7.8.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL). Your server must also have `mod_rewrite` enabled for Apache or equivalent URL rewriting functionality for Nginx, which is standard for most PrestaShop installations.
- **PrestaShop Friendly URLs**: PrestaShop's native "Friendly URL" option (found under **Shop Parameters > SEO & URLs**) *must be enabled* for this module to function correctly. This module enhances PrestaShop's native functionality, it does not replace it.

## 2. Complete Configuration Walkthrough

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” will take you to the main configuration page for “Pretty / Clean URLs PRO”. This is where you control the core behavior of the module.

**General Settings**

-   **Enable Pretty URLs:**
    -   **What this setting does:** This is the master switch for the module. It controls whether the module actively generates and uses clean URLs throughout your store.
    -   **Effect of changing this setting:**
        -   *When enabled:* The module will start generating and redirecting to clean URLs for all supported page types (products, categories, CMS, etc.).
        -   *When disabled:* The module will be inactive, and PrestaShop will revert to its default URL structure (which may include IDs).
    -   **Recommended value:** **YES** (This is the primary function of the module).
    -   **Merchant scenario / example:** You’ve just installed the module and want to activate its SEO benefits. You would enable this setting. If you need to temporarily troubleshoot or revert to default PrestaShop behavior, you might disable it.
-   **Remove IDs from URLs:**
    -   **What this setting does:** This option specifically controls whether the numerical ID (e.g., `123` in `yourstore.com/123-my-product`) is removed from the URLs.
    -   **Effect of changing this setting:**
        -   *When enabled:* URLs will be shorter and cleaner, like `yourstore.com/my-product`. This is generally better for SEO and aesthetics.
        -   *When disabled:* URLs will still be “pretty” but will retain the ID, e.g., `yourstore.com/123-my-product`. This might be useful if you have external systems that rely on the ID being present in the URL, though it’s less common.
    -   **Recommended value:** **YES** (For maximum SEO benefit and clean aesthetics).
    -   **Merchant scenario / example:** You want the absolute cleanest URLs possible for better search engine indexing and user readability. You would enable this.
-   **Automatic 301 Redirection:**
    -   **What this setting does:** This critical setting tells the module to automatically create 301 permanent redirects from old, ID-based URLs to the new, clean URLs.
    -   **Effect of changing this setting:**
        -   *When enabled:* Any visitor or search engine bot trying to access an old URL (e.g., one that was indexed before the module was active) will be seamlessly redirected to the new, clean URL. This prevents 404 errors and preserves your SEO link equity.
        -   *When disabled:* Old URLs will lead to 404 “Page Not Found” errors, which is bad for user experience and can severely harm your SEO.
    -   **Recommended value:** **YES** (Absolutely essential for maintaining SEO and user experience during and after the transition to clean URLs).
    -   **Merchant scenario / example:** You’ve just activated the module on an existing store with many indexed pages. Enabling this ensures that all your old links continue to work and pass their SEO value to the new links.
-   **Force Trailing Slash:**
    -   **What this setting does:** Determines whether a trailing slash (`/`) is always added to the end of your URLs (e.g., `yourstore.com/category/` vs. `yourstore.com/category`).
    -   **Effect of changing this setting:**
        -   *When enabled:* All generated URLs will end with a slash. This can help with URL consistency and some SEO tools prefer it.
        -   *When disabled:* URLs will not necessarily end with a slash, depending on PrestaShop’s default behavior for that page type.
    -   **Recommended value:** **YES** (For consistency and to avoid potential duplicate content issues if search engines treat `url` and `url/` as different pages).
    -   **Merchant scenario / example:** You want to ensure all your category and CMS page URLs consistently end with a slash for better SEO management and to prevent potential duplicate content issues.
-   **Remove .html Extension:**
    -   **What this setting does:** This option controls whether the `.html` extension is removed from product and CMS page URLs.
    -   **Effect of changing this setting:**
        -   *When enabled:* URLs will be even shorter, e.g., `yourstore.com/my-product` instead of `yourstore.com/my-product.html`. This is generally preferred for modern web design and SEO.
        -   *When disabled:* Product and CMS page URLs will retain the `.html` extension.
    -   **Recommended value:** **YES** (For the cleanest, most modern URL structure).
    -   **Merchant scenario / example:** You want your product pages to look like `yourstore.com/my-product` instead of `yourstore.com/my-product.html` for a sleeker appearance and better SEO.

**Save Button:**

-   Always click the “Save” button after making any changes to apply them to your store.

### 2.2 Dedicated Admin Screens & Controller Views

This module primarily works by overriding core PrestaShop classes and controllers to modify URL generation and routing. While it doesn’t introduce a new, dedicated menu item in the Back Office for managing a list of “Pretty URLs,” it integrates directly with existing PrestaShop functionalities.

**AdminProductsController Integration (Back Office > Catalog > Products)**

-   **Screen Name & Menu Location:** **Catalog > Products**
-   **Available Actions & Settings:**
    -   When you edit or create a product, the module influences how the “Friendly URL” field behaves. Instead of requiring you to manually remove IDs or ensure a clean structure, the module’s logic will automatically generate and suggest a clean, ID-free URL based on your product name and the module’s settings.
    -   The module ensures that when you save a product, its URL is generated according to your “Pretty / Clean URLs PRO” settings (e.g., no ID, no `.html` extension if configured).
-   **Effect of changes:**
    -   When you save a product, the URL generated and used by PrestaShop will reflect the clean URL structure defined in the module’s configuration.
    -   If you change a product’s name, the module will help ensure the friendly URL is updated cleanly.
-   **Recommended workflow for daily store management:**
    -   Continue managing your products as usual under **Catalog > Products**. The module works in the background to ensure the URLs are optimized.
    -   When creating or editing products, ensure your product names are descriptive, as these are used to generate the friendly URLs.
    -   You can still manually adjust the “Friendly URL” field for a product if you need a specific URL, but the module’s logic will guide the initial generation.

**Other Admin Controllers (Implicit Integration)**

The module also implicitly affects other areas where URLs are generated, such as:

-   **Catalog > Categories**: When creating or editing categories.
-   **Catalog > Manufacturers**: When creating or editing manufacturers.
-   **Catalog > Suppliers**: When creating or editing suppliers.
-   **Design > Pages (CMS)**: When creating or editing CMS pages.

In all these cases, the module ensures that the friendly URLs generated by PrestaShop adhere to the “Pretty / Clean URLs PRO” settings, removing IDs and extensions as configured.

### 2.3 PrestaShop SEO & URLs Settings Integration

The "Pretty / Clean URLs PRO" module from version 2.8.3 and higher has its own dedicated section for defining URL schemas, making it unnecessary to manually configure these settings under PrestaShop's native **Shop Parameters > SEO & URLs** section. However, it's crucial to understand the interaction.

:::caution Important Note
While the module manages the URL schema, PrestaShop's native **Friendly URL** option under **Shop Parameters > SEO & URLs** *must be enabled* for the module to function. The module enhances this core PrestaShop functionality.
:::

**Schema of URLs (Managed by Module)**

Historically, PrestaShop users would define the URL patterns (routes) for products, categories, CMS pages, etc., in the **Shop Parameters > SEO & URLs** section. The "Pretty / Clean URLs PRO" module now takes over this responsibility, allowing you to configure these directly from its own configuration page.

The module ensures that the routes are set to remove `{id}` from URLs, which is essential for truly clean URLs. If, for any reason, you find that the routes in **Shop Parameters > SEO & URLs** still contain `{id}` after installing and configuring the module, it might indicate an issue with module overrides (see Section 6 for troubleshooting).

For reference, here are the recommended route structures that the module aims to implement:

| Route Type          | Default PrestaShop Value (Example) | Module's Desired Value (Clean) |
| :------------------ | :--------------------------------- | :----------------------------- |
| Route to product    | `{category:/}{id}-{rewrite}{-:ean13}.html` | `{category:/}{rewrite}.html` (or `{rewrite}.html`) |
| Route to category   | `{id}-{rewrite}`                   | `{parent_categories:/}{rewrite}/` (or `{rewrite}/`) |
| Route to supplier   | `{id}__{rewrite}`                  | `supplier/{rewrite}/`          |
| Route to manufacturer | `{id}_{rewrite}`                   | `manufacturer/{rewrite}/`      |
| Route to CMS page   | `content/{id}-{rewrite}`           | `info/{rewrite}.html`          |
| Route to CMS category page | `content/category/{id}-{rewrite}` | `info/{rewrite}`               |

:::tip Multistore Environment
If you are running a PrestaShop Multistore, remember to verify and, if necessary, adjust the URL schema settings for each individual shop. You can select the shop you want to configure from the shop-context menu in your Back Office.
:::

### 2.4 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Config | Enable Pretty URLs | YES | Activates/deactivates the module’s core functionality. |
| Module Config | Remove IDs from URLs | YES | Removes numerical IDs from URLs (e.g., `123-product` becomes `product`). |
| Module Config | Automatic 301 Redirection | YES | Redirects old ID-based URLs to new clean URLs, preserving SEO. |
| Module Config | Force Trailing Slash | YES | Ensures all URLs end with a `/` for consistency and SEO. |
| Module Config | Remove .html Extension | YES | Removes `.html` from product/CMS page URLs for cleaner links. |
| Catalog > Products (Edit) | Friendly URL field | Auto-generated | Module influences the automatic generation of clean URLs for products. |
| Catalog > Categories (Edit) | Friendly URL field | Auto-generated | Module influences the automatic generation of clean URLs for categories. |
| Design > Pages (Edit) | Friendly URL field | Auto-generated | Module influences the automatic generation of clean URLs for CMS pages. |
| Shop Parameters > SEO & URLs | Friendly URL | YES | **CRITICAL:** Must be enabled for the module to work. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: After installing, my URLs still look the same, or I’m getting 404 errors.**

-   **A:** First, ensure “Enable Pretty URLs” is set to YES in the module’s configuration.
-   Second, go to **Advanced Parameters > Performance** in your PrestaShop Back Office and click “Clear cache” (or “Clear Smarty cache” in older versions).
-   Third, ensure that PrestaShop’s native “Friendly URL” option is enabled under **Shop Parameters > SEO & URLs**. This module enhances PrestaShop’s native friendly URL functionality, it doesn’t replace it entirely.
-   Finally, check your server’s `.htaccess` file (if using Apache) or Nginx configuration. The module relies on server-side URL rewriting (mod\_rewrite for Apache) to function correctly. If you’re unsure, contact your hosting provider.

**Q2: My custom theme has some strange display issues after enabling the module.**

-   **A:** This module primarily affects URL generation and redirection, not visual display. It’s unlikely to directly cause theme display issues. However, if you’ve cleared the cache, your theme’s CSS or JS might need to be reloaded. Try clearing your browser cache. If the issue persists, it might be a conflict with another module or a custom theme modification. Temporarily disable “Pretty / Clean URLs PRO” to see if the issue resolves. If it does, contact MyPresta.eu support.

**Q3: Will this module work with my existing custom URLs or redirects?**

-   **A:** The module focuses on generating clean URLs for core PrestaShop entities (products, categories, CMS, etc.). If you have manually created custom redirects or specific friendly URLs outside of PrestaShop’s standard system, the module’s automatic 301 redirection will prioritize its own generated clean URLs. It’s generally best to let the module manage all core entity URLs for consistency. If you have very specific custom redirects, you might need to test how they interact.

**Q4: I changed a product name, but the URL didn’t update automatically.**

-   **A:** When you change a product’s name, PrestaShop usually suggests a new friendly URL. You need to explicitly save the product for the changes to take effect and for the module to process the new URL. If the friendly URL field doesn’t update automatically, you might need to manually click “Generate URL” next to the friendly URL field on the product edit page, then save the product. The module will then ensure this new URL is clean and handles redirection from the old one.

**Q5: Does this module affect my multi-language URLs?**

-   **A:** No, it enhances them! The module works with PrestaShop’s multi-language capabilities. It will generate clean URLs for each language, respecting the language code in the URL (e.g., `/en/my-product` and `/fr/mon-produit`). Ensure your product, category, and CMS page names are translated for each language to get the best friendly URLs.

**Q6: I see an error message "keyword {id} is required for route (...)" when trying to save URL schemas.**

-   **A:** This error typically occurs if the module's overrides (a core part of its functionality) are not correctly installed or are disabled in your PrestaShop store. The module relies on these overrides to modify PrestaShop's default URL routing behavior, allowing it to remove the `{id}` from routes.
    -   **Solution:**
        1.  **Check Overrides:** Ensure that PrestaShop's override system is enabled. You can usually find this setting under **Advanced Parameters > Performance**. Look for an option related to "Disable non PrestaShop modules" or "Disable overrides" and ensure it is set to "No".
        2.  **Reinstall Module:** Sometimes, reinstalling the module can resolve override issues. Uninstall the module, clear your PrestaShop cache, and then reinstall it.
        3.  **Manual Override Check:** Verify that the module's override files are present in your `override/classes/` and `override/controllers/` directories (e.g., `override/classes/Dispatcher.php`, `override/controllers/front/ProductController.php`). If they are missing, it indicates an installation problem.
    -   If the problem persists, please contact MyPresta.eu support.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Pretty / Clean URLs PRO” module operates by overriding core PrestaShop classes, specifically `Dispatcher` and `Link`, to modify how URLs are generated and parsed. It intercepts the default URL routing and generation logic to remove IDs and extensions based on its configuration settings. The module leverages PrestaShop’s override system (`/override/`) to inject its custom logic without directly modifying core files, ensuring upgrade compatibility. It also includes an admin controller override for `AdminProductsController` to ensure the friendly URL generation in the back office aligns with the module’s settings.

### 4.2 Controllers (`controllers/`)

The module primarily uses front-office controller overrides to modify URL generation and routing.

-   **Front-Office Controllers**:

    -   `purls/override/controllers/front/CartController.php`
        -   **Class name & parent class**: `CartController` (overrides `CartControllerCore`)
        -   **Responsibility**: Modifies URL generation for cart-related links to ensure they are clean and ID-free where applicable.
    -   `purls/override/controllers/front/CmsController.php`
        -   **Class name & parent class**: `CmsController` (overrides `CmsControllerCore`)
        -   **Responsibility**: Modifies URL generation for CMS pages, removing IDs and `.html` extensions as configured.
    -   `purls/override/controllers/front/listing/CategoryController.php`
        -   **Class name & parent class**: `CategoryController` (overrides `CategoryControllerCore`)
        -   **Responsibility**: Modifies URL generation for category pages, removing IDs and ensuring clean URLs.
    -   `purls/override/controllers/front/listing/index.php`
        -   **Class name & parent class**: Not a direct controller, likely an empty file or placeholder. PrestaShop’s autoloader might pick up other files in this directory.
        -   **Responsibility**: No direct responsibility; serves as a directory marker.
    -   `purls/override/controllers/front/listing/ManufacturerController.php`
        -   **Class name & parent class**: `ManufacturerController` (overrides `ManufacturerControllerCore`)
        -   **Responsibility**: Modifies URL generation for manufacturer pages, removing IDs and ensuring clean URLs.
    -   `purls/override/controllers/front/listing/SupplierController.php`
        -   **Class name & parent class**: `SupplierController` (overrides `SupplierControllerCore`)
        -   **Responsibility**: Modifies URL generation for supplier pages, removing IDs and ensuring clean URLs.
    -   `purls/override/controllers/front/ProductController.php`
        -   **Class name & parent class**: `ProductController` (overrides `ProductControllerCore`)
        -   **Responsibility**: Modifies URL generation for product pages, removing IDs and `.html` extensions as configured.
-   **Back-Office Admin Controllers**:

    -   `purls/override/controllers/admin/AdminProductsController.php`
        -   **Class name & parent class**: `AdminProductsController` (overrides `AdminProductsControllerCore`)
        -   **Responsibility**: Integrates with the product management interface to ensure that when friendly URLs are generated or updated in the back office, they adhere to the module’s settings (e.g., removing IDs). It likely modifies the `generateFriendlyUrl` method or similar logic.

### 4.3 Core Classes & Models (`classes/`)

The module’s core logic resides in its class overrides, which are fundamental to how PrestaShop handles URLs.

-   `purls/override/classes/Dispatcher.php`
    -   **Class name & parent class**: `Dispatcher` (overrides `DispatcherCore`)
    -   **Database interaction**: None directly, but interacts with `ps_configuration` for module settings.
    -   **Key public methods and business logic**: This class is responsible for routing incoming requests to the correct controller and for generating URLs. The override likely modifies methods like `getFriendlyUrl` or `createUrl` to remove IDs and extensions, and to handle the 301 redirection logic for old URLs. It’s the central point for URL parsing and generation.
-   `purls/override/classes/Link.php`
    -   **Class name & parent class**: `Link` (overrides `LinkCore`)
    -   **Database interaction**: None directly, but interacts with `ps_configuration` for module settings.
    -   **Key public methods and business logic**: The `Link` class is used throughout PrestaShop to construct URLs for various entities (products, categories, CMS, etc.). The override in this module modifies methods like `getProductLink`, `getCategoryLink`, `getCMSLink`, etc., to generate URLs that are clean, ID-free, and without `.html` extensions as per the module’s configuration. It works in conjunction with the `Dispatcher` override to ensure consistent URL generation.

### 4.4 JavaScript Assets (`views/js/`)

-   `purls/views/js/purls.js`
    -   **Scope**: Back-office (likely on product/category/CMS edit pages).
    -   **Details**: This script likely contains client-side logic to enhance the friendly URL generation process within the PrestaShop Back Office. It might:
        -   Listen for changes in product/category/CMS names and automatically update the “Friendly URL” field based on the module’s settings.
        -   Provide real-time feedback or validation for the generated URLs.
        -   Potentially interact with AJAX calls to the server to get suggested friendly URLs.
        -   Ensure that the “Generate URL” button (if present) triggers the module’s logic.

### 4.5 CSS Stylesheets (`views/css/`)

No custom CSS files were found in the module archive, indicating that the module does not introduce new visual elements requiring specific styling. It relies on PrestaShop’s default Back Office styling for its configuration page.

### 4.6 Smarty Template Structure (`views/templates/`)

-   **Admin templates (`views/templates/admin/`)**:
    -   `purls/views/purls.tpl`
        -   **Scope**: Back-office, module configuration page.
        -   **Details**: This template renders the main configuration form for the “Pretty / Clean URLs PRO” module. It contains the HTML structure for all the settings described in Section 4.1, including switches for enabling/disabling features, and the “Save” button. It uses standard PrestaShop form helpers and styling.

### 4.7 Database Schema & Hooks Map

-   **Database Tables**:

    -   The module does not create any custom SQL tables.
    -   It stores its configuration settings in the standard PrestaShop `ps_configuration` table. The configuration keys would typically follow a pattern like `PURLS_ENABLE`, `PURLS_REMOVE_IDS`, `PURLS_301_REDIRECT`, etc.
-   **Registered Hooks Table**:
    The module primarily operates through class overrides rather than direct hook registration for its core functionality. However, it might implicitly interact with hooks that trigger URL generation or redirection.

| Hook Name | Execution Timing | Technical Purpose |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | On every page load in the front office, within the `<head>` section. | While not directly registering a visual element, the module’s `Dispatcher` and `Link` overrides are active during page rendering, influencing any URLs generated within the header (e.g., canonical URLs, language switchers). |
| `actionDispatcherBefore` | Before the dispatcher processes the request. | The `Dispatcher` override is active at this stage, allowing the module to intercept and modify the URL parsing and routing logic before PrestaShop determines which controller to load. This is crucial for handling 301 redirects from old URLs. |
| `actionDispatcherAfter` | After the dispatcher has processed the request. | The `Dispatcher` override can also be active here, potentially for post-processing or logging related to URL handling. |
| `actionProductUpdate` / `actionProductAdd` | After a product is updated or added in the Back Office. | The `AdminProductsController` override ensures that when a product is saved, its friendly URL is generated according to the module’s settings. This is an implicit interaction rather than a direct hook registration by the module itself. |
| `actionCategoryUpdate` / `actionCategoryAdd` | After a category is updated or added in the Back Office. | Similar to products, the module ensures clean URLs for categories. |
| `actionCmsUpdate` / `actionCmsAdd` | After a CMS page is updated or added in the Back Office. | Similar to products, the module ensures clean URLs for CMS pages. |

## 5. Official Support & Resources

For official updates, technical support, and any inquiries regarding the “Pretty / Clean URLs PRO” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist you with any issues or questions you may have.
