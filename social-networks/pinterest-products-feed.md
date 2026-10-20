---
title: "Pinterest products feed - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Pinterest products feed PrestaShop module by MyPresta.eu."
sidebar:
  label: "Pinterest products feed - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Pinterest products feed Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/pinterest-products-feed.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/pinterest-products-feed/)
>
> ---


# Pinterest products feed

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and ensure smooth operation of modules. Your hosting environment should also allow for sufficient memory and execution time for generating large product feeds, especially if you have many products.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The “Pinterest products feed” module has a main configuration screen and a dedicated administration screen for managing your product feeds.

### 2.1 Module Configuration Page (Back Office > Modules > Module Manager > Configure Pinterest products feed)

This is the main setup screen where you define the core parameters for your Pinterest product feed.

#### General Settings Tab

This tab contains the fundamental settings for generating your product feed.

- **Enable Pinterest Feed:**

  - **What this setting does:** This is the master switch to activate or deactivate the module’s functionality.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The module will generate the product feed and make it accessible via a URL.
    - *When disabled (NO):* The module will not generate or update the feed, and the feed URL will become inactive.
  - **Recommended value:** YES (once you’ve configured other settings).
  - **Merchant scenario / example:** You’re ready to start selling on Pinterest, so you enable this after setting up your product filters.
- **Feed File Type:**

  - **What this setting does:** Determines the format of the product feed file. Pinterest supports both CSV (Comma Separated Values) and XML (Extensible Markup Language).
  - **Effect of changing this setting:**
    - *When set to CSV:* The feed will be a plain text file with product data separated by commas.
    - *When set to XML:* The feed will be a structured file using XML tags.
  - **Recommended value:** XML (generally more robust for complex data, but both work with Pinterest).
  - **Merchant scenario / example:** Pinterest often recommends XML for richer data, so you might choose XML for better compatibility and future-proofing.
- **Default Language for Feed:**

  - **What this setting does:** Selects the language in which product names, descriptions, and other textual data will be exported in the feed.
  - **Effect of changing this setting:**
    - *When set to English:* All product text will be in English.
    - *When set to French:* All product text will be in French.
  - **Recommended value:** The primary language of your target audience on Pinterest.
  - **Merchant scenario / example:** If you’re targeting customers in France, you’d select French. If you’re targeting a global English-speaking audience, you’d select English.
- **Default Currency for Feed:**

  - **What this setting does:** Selects the currency in which product prices will be exported in the feed.
  - **Effect of changing this setting:**
    - *When set to USD:* All prices will be in US Dollars.
    - *When set to EUR:* All prices will be in Euros.
  - **Recommended value:** The primary currency of your target market on Pinterest.
  - **Merchant scenario / example:** If your main market uses Euros, set this to EUR to ensure correct pricing display on Pinterest.
- **Default Country for Feed:**

  - **What this setting does:** Selects the country associated with your products in the feed. This can influence shipping and tax calculations on Pinterest’s side.
  - **Effect of changing this setting:**
    - *When set to United States:* Products are associated with the US market.
    - *When set to France:* Products are associated with the French market.
  - **Recommended value:** Your primary country of operation or target market.
  - **Merchant scenario / example:** If your business is based in Germany and primarily sells to German customers, you would select Germany.
- **Default Carrier for Feed:**

  - **What this setting does:** Specifies the default shipping carrier to be associated with products in the feed. This can be used by Pinterest to estimate shipping costs.
  - **Effect of changing this setting:**
    - *When set to “My Carrier”:* Pinterest might use this carrier’s general shipping rules (if available) for display.
  - **Recommended value:** Your most commonly used or default shipping carrier.
  - **Merchant scenario / example:** If you mostly ship with FedEx, you’d select FedEx here.
- **Include Product Combinations (Variations):**

  - **What this setting does:** Determines whether individual product variations (like different sizes or colors of a shirt) are included as separate items in the feed.
  - **Effect of changing this setting:**
    - *When enabled (YES):* Each combination (e.g., “Red T-shirt - Small”, “Red T-shirt - Medium”) will be a distinct entry in the feed.
    - *When disabled (NO):* Only the main product will be included, without individual variations.
  - **Recommended value:** YES (if you want customers to see and click on specific variations on Pinterest).
  - **Merchant scenario / example:** You sell t-shirts in various sizes and colors. Enabling this ensures each unique size/color combination gets its own pin on Pinterest, allowing customers to find exactly what they’re looking for.
- **Export Products with Specific Attribute (e.g., Size):**

  - **What this setting does:** Allows you to specify a particular attribute (like “Size” or “Color”) that should be included in the product feed, often used for rich product data.
  - **Effect of changing this setting:**
    - *When selected (e.g., “Size”):* The size attribute of your products will be explicitly included in the feed data.
    - *When not selected:* This specific attribute will not be explicitly exported.
  - **Recommended value:** Select an attribute that is crucial for product differentiation, like “Size” or “Color”.
  - **Merchant scenario / example:** If you sell clothing, selecting “Size” ensures Pinterest can display size information directly on the pin, improving the shopping experience.
- **Export Products with Specific Feature (e.g., Material):**

  - **What this setting does:** Similar to attributes, this allows you to include a specific product feature (like “Material” or “Brand”) in the feed.
  - **Effect of changing this setting:**
    - *When selected (e.g., “Material”):* The material feature of your products will be explicitly included in the feed data.
    - *When not selected:* This specific feature will not be explicitly exported.
  - **Recommended value:** Select a feature that adds valuable information for shoppers, like “Material”, “Brand”, or “Style”.
  - **Merchant scenario / example:** If you sell furniture, selecting “Material” (e.g., “Oak”, “Pine”) helps customers filter and find products based on their preferences.
- **Export Products with Specific Custom Label (e.g., Best Seller):**

  - **What this setting does:** Allows you to include a custom label (if you’ve defined them in PrestaShop) in the feed. These can be used for specific marketing campaigns on Pinterest.
  - **Effect of changing this setting:**
    - *When selected (e.g., “Best Seller”):* Products with this custom label will have it included in their feed data.
    - *When not selected:* Custom labels will not be exported.
  - **Recommended value:** Use if you have specific labels for marketing or categorization on Pinterest.
  - **Merchant scenario / example:** You’ve marked certain products as “Best Sellers” in PrestaShop. Exporting this label allows you to create Pinterest ad campaigns specifically targeting these high-performing products.
- **Exclude Products by Category:**

  - **What this setting does:** Provides a tree-like selector to choose entire categories of products that you do NOT want to include in your Pinterest feed.
  - **Effect of changing this setting:**
    - *When categories are selected:* All products within those categories (and their subcategories) will be excluded from the generated feed.
    - *When no categories are selected:* All products from all categories will be considered for export (unless excluded by other settings).
  - **Recommended value:** Exclude categories that are not suitable for Pinterest (e.g., services, digital downloads, or products you don’t want to advertise).
  - **Merchant scenario / example:** You sell both physical products and digital gift cards. You’d exclude the “Digital Gift Cards” category from the feed as Pinterest is primarily for physical products.
- **Exclude Specific Products:**

  - **What this setting does:** Allows you to search for and select individual products that you want to explicitly exclude from the Pinterest feed.
  - **Effect of changing this setting:**
    - *When products are selected:* Those specific products will not appear in the generated feed.
    - *When no products are selected:* All products (not excluded by category) will be considered for export.
  - **Recommended value:** Exclude specific products that are out of stock indefinitely, discontinued, or for any other reason you don’t want them on Pinterest.
  - **Merchant scenario / example:** A particular product is temporarily unavailable due to a supplier issue, so you exclude it until it’s back in stock.
- **Generate Feed URL:**

  - **What this setting does:** Displays the unique URL where your Pinterest product feed can be accessed. This is the URL you will provide to Pinterest.
  - **Effect of changing this setting:** This is a display-only field. The URL changes if you change your shop’s domain or SSL settings.
  - **Recommended value:** Copy this URL and paste it into your Pinterest Business account settings when setting up your product catalog.
  - **Merchant scenario / example:** After configuring all settings, you copy this URL and go to your Pinterest Business account to set up your product catalog, pasting this URL into the “Data Source” field.
- **Generate Feed (Button):**

  - **What this setting does:** Manually triggers the generation of the product feed file.
  - **Effect of changing this setting:** Clicking this button will immediately create or update the feed file based on your current settings. This can take some time for large catalogs.
  - **Recommended value:** Click this after making any changes to your feed settings or when you want to force an immediate update.
  - **Merchant scenario / example:** You’ve just added 50 new products and want them to appear on Pinterest as soon as possible, so you click “Generate Feed”.

#### Cron Job Settings Tab

This tab provides information for automating the feed generation process.

- **Cron Job URL:**

  - **What this setting does:** Displays a special URL that, when visited, automatically triggers the feed generation process without you having to click the “Generate Feed” button in the back office.
  - **Effect of changing this setting:** This is a display-only field.
  - **Recommended value:** Copy this URL and set it up as a “cron job” on your web hosting server.
  - **Merchant scenario / example:** You want your Pinterest feed to update every night at 3 AM. You copy this URL and configure a cron job on your server to visit this URL daily at 3 AM.
- **How to set up a Cron Job:**

  - **What this setting does:** Provides instructions on how to set up an automated task (cron job) on your web server to regularly update your product feed.
  - **Effect of changing this setting:** This is an informational section.
  - **Recommended value:** Follow these instructions or provide them to your webmaster/hosting support to ensure your feed is always fresh.
  - **Merchant scenario / example:** You’re not sure how to set up a cron job. This section gives you the exact steps or the information to pass to your hosting provider.

### 2.2 Dedicated Admin Screens & Controller Views

#### Pinterest Feeds Dashboard (Back Office > Sell > Pinterest Feeds)

This dedicated section of your PrestaShop back office provides an overview and management interface for your Pinterest product feeds. You can find it under the “Sell” menu in PrestaShop 1.7/8/9.

- **Screen Name & Menu Location:** Pinterest Feeds (under “Sell” in the main menu).
- **Available Actions & Settings:**
  - **Feed Listing Table:** This table displays all generated feeds (if the module supports multiple feeds, otherwise it will show the main one). It typically includes:
    - **Feed Name/ID:** A unique identifier for the feed.
    - **Language:** The language of the products in the feed.
    - **Currency:** The currency of the prices in the feed.
    - **Last Generated:** The date and time the feed was last updated.
    - **Feed URL:** The direct link to the generated feed file.
    - **Actions:** Buttons to view, download, or regenerate the feed.
  - **Add New Feed / Edit Feed:** While the module primarily focuses on a single main feed, this interface might allow for future expansion or specific feed configurations. For now, it largely reflects the settings from the main configuration page.
  - **Grid / Management View:** This screen provides a clear overview of your feed’s status and quick access to its URL and regeneration options.
- **Effect of changes:**
  - *Regenerating a feed:* Updates the feed file with the latest product data from your store, reflecting any changes in product information, prices, or stock levels.
  - *Viewing the feed URL:* Allows you to quickly copy the URL needed for Pinterest.
- **Recommended workflow for daily store management:**
  1. Periodically check this dashboard to ensure your feed is being generated regularly (if you’ve set up a cron job) and that the “Last Generated” timestamp is recent.
  2. If you make significant product changes (e.g., mass price updates, new product launches), you might manually regenerate the feed from this screen or the module configuration to ensure Pinterest gets the latest data quickly.
  3. Copy the Feed URL from here when initially setting up your Pinterest Business account.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration Page** | Enable Pinterest Feed | YES | Activates/deactivates feed generation. |
|  | Feed File Type | XML | Sets the output format for the feed (CSV or XML). |
|  | Default Language for Feed | Your Primary Language | Language for product names/descriptions. |
|  | Default Currency for Feed | Your Primary Currency | Currency for product prices. |
|  | Default Country for Feed | Your Primary Country | Country association for products. |
|  | Default Carrier for Feed | Your Default Carrier | Shipping carrier for Pinterest estimates. |
|  | Include Product Combinations | YES | Exports individual product variations. |
|  | Export Products with Specific Attribute | Select relevant attribute (e.g., Size) | Includes specific product attributes in the feed. |
|  | Export Products with Specific Feature | Select relevant feature (e.g., Material) | Includes specific product features in the feed. |
|  | Export Products with Specific Custom Label | Select relevant label (e.g., Best Seller) | Includes custom labels for marketing. |
|  | Exclude Products by Category | Select categories to exclude | Prevents products from chosen categories from appearing in the feed. |
|  | Exclude Specific Products | Select individual products to exclude | Prevents specific products from appearing in the feed. |
|  | Generate Feed URL | (Display Only) | The URL to provide to Pinterest for fetching your feed. |
|  | Generate Feed (Button) | Click after changes | Manually triggers immediate feed generation. |
| **Cron Job Settings Tab** | Cron Job URL | (Display Only) | URL for automated feed generation via server cron. |
|  | How to set up a Cron Job | Follow instructions | Guide for setting up automated feed updates. |
| **Pinterest Feeds Dashboard** | Feed Listing Table | (View) | Overview of generated feeds, status, and URLs. |
|  | Regenerate Feed (Action) | Click as needed | Updates the feed with the latest store data. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My products aren’t appearing on Pinterest after I’ve set up the feed. What should I do?**
A1: First, ensure the “Enable Pinterest Feed” setting in the module configuration is set to YES. Then, manually click the “Generate Feed” button to create the initial feed file. Next, double-check that you’ve correctly copied and pasted the “Generate Feed URL” into your Pinterest Business account’s product catalog settings. Pinterest can take some time (up to 24-48 hours) to process a new feed. Also, check your Pinterest Business account for any error messages related to the feed.

**Q2: The prices or stock levels on Pinterest are outdated. How can I fix this?**
A2: This usually means your feed isn’t updating regularly. Ensure you have set up the cron job on your hosting server using the “Cron Job URL” provided in the module. If the cron job is set up, verify it’s running correctly (your hosting provider can assist with this). You can also manually regenerate the feed by clicking the “Generate Feed” button in the module’s configuration to force an immediate update.

**Q3: Some of my products are missing from the Pinterest feed.**
A3: Go to the module’s configuration page and check the “Exclude Products by Category” and “Exclude Specific Products” settings. You might have inadvertently excluded categories or individual products. Also, ensure the products have valid images, prices, and are set to “active” and “available for order” in your PrestaShop store, as the module typically only exports active, purchasable products.

**Q4: The feed generation process takes a very long time or times out.**
A4: If you have a very large catalog (thousands of products), generating the feed can be resource-intensive.
\* **Solution 1:** Increase PHP `memory_limit` and `max_execution_time` settings in your server’s `php.ini` file. Your hosting provider can help with this.
\* **Solution 2:** Ensure your cron job is set to run during off-peak hours to minimize impact on store performance.
\* **Solution 3:** Consider excluding less important categories or products if the feed size is consistently an issue.

**Q5: My custom theme styles are not applied to the module’s admin interface.**
A5: The module’s admin interface uses its own CSS (`admin-app.css`, `admin-theme.css`). These are separate from your front-office theme. If you want to customize the look of the module’s back-office pages, you would need to override these specific CSS files or add custom CSS to your PrestaShop back office. This is typically a task for a web developer.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the “Pinterest products feed” module for developers and webmasters.

### 4.1 Architecture Overview

The `pinterestfeed` module follows a standard PrestaShop MVC (Model-View-Controller) pattern, with dedicated front controllers for feed generation and cron execution, and admin controllers for configuration and management. It leverages `ObjectModel` for potential data persistence (though primarily focuses on dynamic feed generation) and utilizes Smarty templates for rendering both back-office configuration and informational views. The core logic for generating the feed according to Pinterest’s specifications is encapsulated in dedicated helper classes.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

These controllers handle public-facing requests, primarily for the feed itself and cron job execution.

- `controllers/front/cron.php`
  - **Class name & parent class:** `PinterestFeedCronModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** This controller is designed to be called by a server-side cron job. When accessed, it triggers the `PinterestFeedGenerator` class to regenerate the product feed based on the module’s current configuration. It typically returns a simple success/failure message or logs the process. It does not render a visual page.
- `controllers/front/feed.php`
  - **Class name & parent class:** `PinterestFeedFeedModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** This controller serves the actual product feed file. When accessed via the “Generate Feed URL”, it reads the pre-generated feed file (or generates it if it doesn’t exist/is outdated, depending on implementation) and outputs its content (CSV or XML) with appropriate HTTP headers (`Content-Type`).

#### Back-Office Admin Controllers

These controllers manage the module’s configuration and provide administrative interfaces.

- `controllers/admin/AdminExportProductsFeedPinterest.php`
  - **Class name & parent class:** `AdminExportProductsFeedPinterestController` extending `ModuleAdminController`.
  - **Tab name and managed entity:** This controller is responsible for the “Pinterest Feeds” dashboard found under the “Sell” menu. It manages the display and actions related to the generated product feeds. It doesn’t directly manage a specific `ObjectModel` entity but rather orchestrates the generation and display of feed-related data.
  - **Key Configuration Keys leveraged:** `PS_LANG_DEFAULT`, `PS_CARRIER_DEFAULT`, `PS_COUNTRY_DEFAULT`, `PS_CURRENCY_DEFAULT` (for default values in forms), `pm_pinterestfeed_products`, `pm_export_size_attribute` (for module-specific settings). It also uses `pf_tree` for category selection and `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` for language selection in forms.
- `controllers/admin/index.php`
  - **Class name & parent class:** This file likely serves as a placeholder or a simple redirect/entry point for the admin section, rather than a full-fledged controller. In PrestaShop, `index.php` files in subdirectories often prevent direct directory listing. Its primary role is to ensure security by preventing direct access to the directory contents.

### 4.3 Core Classes & Models (`classes/`)

- `classes/index.php`
  - **Purpose:** Standard PrestaShop security file to prevent direct directory listing.
- `classes/PinterestFeedGenerator.php`
  - **Responsibility:** This is the core logic class for constructing the product feed.
  - **Database interaction:** Interacts with various PrestaShop core tables (e.g., `ps_product`, `ps_product_lang`, `ps_image`, `ps_category`, `ps_attribute`, `ps_feature`, `ps_stock_available`) to fetch product data.
  - **ObjectModel extension:** Does not extend `ObjectModel` directly, as its purpose is data aggregation and formatting rather than single-entity persistence.
  - **Key public methods:** Contains methods for fetching products, handling combinations, applying filters (categories, specific products), formatting data according to Pinterest’s specifications, and writing the output to the chosen file type (CSV/XML).
- `classes/PinterestFeedSpec.php`
  - **Responsibility:** This class likely defines the required and optional fields for the Pinterest product feed specification. It acts as a mapping or validation layer to ensure the generated feed adheres to Pinterest’s guidelines.
  - **Database interaction:** None directly.
  - **ObjectModel extension:** Does not extend `ObjectModel`.
  - **Key public methods:** May contain methods to retrieve the list of required/optional fields, their data types, and any specific formatting rules.

### 4.4 JavaScript Assets (`views/js/`)

- `lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Back-office.
  - **Purpose:** Provides autocomplete functionality, likely for searching and selecting products or categories in the admin configuration forms (e.g., for “Exclude Specific Products”).
  - **Event listeners:** Binds to input field `keyup` or `input` events to trigger AJAX searches.
  - **DOM manipulation:** Displays search results in a dropdown list, allows selection, and updates hidden input fields.
- `views/js/admin-app.js`
  - **Scope:** Back-office.
  - **Purpose:** Main JavaScript for the module’s back-office configuration and dashboard. Handles form submissions, dynamic updates, and potentially AJAX calls for feed generation status.
  - **Event listeners:** Binds to form `submit` events, button `click` events (e.g., “Generate Feed”), and potentially `change` events on select boxes.
  - **DOM manipulation:** Manages the display of configuration tabs, updates status messages, and interacts with the autocomplete component.

### 4.5 CSS Stylesheets (`views/css/`)

- `lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Back-office admin form styling.
  - **Purpose:** Styles the autocomplete search input and its dropdown results, ensuring a consistent look and feel within the PrestaShop back office.
  - **Key CSS class selectors:** `.autocomplete-container`, `.autocomplete-results`, `.autocomplete-item`.
- `views/admin-theme.css`
  - **Scope:** Back-office admin form styling.
  - **Purpose:** Provides general styling for the module’s back-office configuration pages, ensuring it integrates well with the PrestaShop admin theme.
  - **Key CSS class selectors:** `.panel`, `.form-group`, `.control-label`, `.help-block`.
- `views/css/admin-app.css`
  - **Scope:** Back-office admin form styling.
  - **Purpose:** Specific styling for the module’s custom elements and layout within the admin interface, such as tab navigation, custom buttons, or unique informational blocks.
  - **Key CSS class selectors:** `.pinterestfeed-tabs`, `.pinterestfeed-panel`, `.pinterestfeed-alert`.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**: The module description does not explicitly list hook templates, suggesting its front-office presence is primarily via the feed URL, not direct display. If any, they would be for informational blocks.
- **Admin templates (`views/templates/admin/`)**:
  - `views/templates/admin/dashboard.tpl`: Likely the main template for the “Pinterest Feeds” dashboard, displaying the list of feeds, their status, and actions.
  - `views/templates/admin/feeds.tpl`: Could be a partial template used within `dashboard.tpl` to render the table of feeds.
  - `views/templates/admin/form-chrome.tpl`: A generic wrapper template for admin forms, providing the standard PrestaShop panel and form structure.
  - `views/templates/admin/layout.tpl`: The main layout template for the module’s admin section, defining the overall structure including header, tabs, and content area.
- **Configuration & Utility templates (`views/`)**:
  - `views/categories-fancybox.tpl`: Template for a Fancybox modal used for category selection (e.g., for exclusion).
  - `views/custom-labels.tpl`: Template for displaying or managing custom labels.
  - `views/exclude-products.tpl`: Template for the product exclusion search and selection interface.
  - `views/google_lang_links.tpl`: Potentially for displaying language-specific links or information, though its direct use in a Pinterest feed module might be for informational purposes.
  - `views/returnAlert.tpl`: A generic template for displaying success or error alerts in the back office.
  - `views/script-fancybox.tpl`: Contains JavaScript for initializing and managing Fancybox modals.
  - `views/script.tpl`: General JavaScript snippets or initialization scripts for the module’s admin pages.
  - `lib/searchTool/views/scripts.tpl`: Contains JavaScript for the autocomplete search tool.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  - The module does not appear to create its own custom SQL tables based on the provided inventory.
  - It relies heavily on existing PrestaShop core tables: `ps_product`, `ps_product_lang`, `ps_image`, `ps_category`, `ps_category_product`, `ps_attribute_group`, `ps_attribute`, `ps_feature`, `ps_feature_product`, `ps_stock_available`, `ps_configuration` (for module settings like `PINTERESTFEED_ENABLED`, `PINTERESTFEED_FILE_TYPE`, etc.).
- **Registered Hooks Table**:
  The module’s primary function is feed generation, which is typically triggered by direct controller access (feed URL, cron URL) or admin actions. While the module description mentions “Front-Office Hooks: Header, Columns, Product, or Footer”, the provided file inventory and feature description suggest these are not actively used for visual display by *this specific module*. Instead, the module likely registers hooks for internal processes or potential future extensions.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | On every page load in the front office. | Potentially for adding custom JS/CSS if the module had a front-office component, or for internal tracking. (Unlikely to be used for visual output by this module). |
| `displayRightColumn` | In the right column of the front office. | (Unlikely to be used for visual output by this module). |
| `displayLeftColumn` | In the left column of the front office. | (Unlikely to be used for visual output by this module). |
| `displayFooter` | In the footer of every page in the front office. | (Unlikely to be used for visual output by this module). |
| `displayProductExtraContent` | On the product page, below the main content. | (Unlikely to be used for visual output by this module). |
| `actionProductUpdate` | After a product is updated in the back office. | Potentially to mark the feed as needing regeneration or to trigger a partial update. |
| `actionProductAdd` | After a new product is added. | Similar to `actionProductUpdate`. |
| `actionProductDelete` | After a product is deleted. | Similar to `actionProductUpdate`. |
| `actionUpdateQuantity` | After product stock quantity changes. | Potentially to trigger feed regeneration if stock changes are critical for the feed. |
| `actionModuleInstall` | During module installation. | To create configuration entries and potentially initial feed file. |
| `actionModuleUninstall` | During module uninstallation. | To clean up configuration entries and generated files. |
| `displayAdminProductsExtra` | On the product edit page in the back office. | Could be used to add a specific tab or field related to Pinterest feed settings for individual products. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for your “Pinterest products feed” module, please refer to your customer account at MyPresta.eu. Our team is dedicated to ensuring your module functions perfectly and helps you achieve your e-commerce goals.

- **MyPresta.eu Order History & Downloads:** <https://mypresta.eu/my-account/orders/>
- **MyPresta.eu Support Contact:** <https://mypresta.eu/contact>
