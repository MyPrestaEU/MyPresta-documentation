---
title: "Microsoft Merchant Center Product Feed - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Microsoft Merchant Center Product Feed PrestaShop module by MyPresta.eu."
sidebar:
  label: "Microsoft Merchant Center Product Feed - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Microsoft Merchant Center Product Feed Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/microsoft-merchant-center-product-feed.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/microsoft-merchant-center-product-feed/)
>
> ---


# Microsoft Merchant Center Product Feed

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL). Your server must be able to execute cron jobs for automated feed generation.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” will take you to the main configuration page for the module. This is where you’ll set up the general behavior and access the feed management tools.

#### General Settings

This section typically covers global settings that affect how the module operates and generates feeds.

- **What this setting does:** These are the core settings that define how your product data is prepared for Microsoft Merchant Center. You’ll typically find options for selecting the language, currency, and country for your feed, as well as general export preferences.
- **Effect of changing this setting:**
  - *Language:* Determines which language version of your product names, descriptions, and categories will be included in the feed. Crucial for targeting specific international markets.
  - *Currency:* Sets the currency for all prices in the feed. Must match the currency configured in your Microsoft Merchant Center account for the target country.
  - *Country:* Specifies the target country for the feed. This influences tax rules, shipping settings, and other country-specific requirements in Microsoft Merchant Center.
  - *Other export options:* May include settings for handling product variants, excluding certain categories, or defining how specific attributes (like size or color) are exported.
- **Recommended value:**
  - *Language, Currency, Country:* Select the primary language, currency, and country you are targeting with your Microsoft Shopping Ads. If you advertise in multiple countries/languages, you will likely create separate feeds for each.
  - *Other options:* Follow the module’s recommendations or adjust based on your specific product catalog and advertising strategy.
- **Merchant scenario / example:** If you sell in France and your store’s default language is French, you would select French for the language, EUR for the currency, and France for the country. If you also sell in Germany, you would create a separate feed configured for German language, EUR currency, and Germany as the country.

#### Feed Management & Generation

This section provides access to create, manage, and generate your product feeds.

- **What this setting does:** This is the heart of the module, allowing you to define and generate the actual product feed files. You’ll typically find options to create new feeds, view existing ones, and trigger the generation process.
- **Effect of changing this setting:**
  - *Creating a new feed:* Initiates the process of setting up a new product feed with its own specific settings (language, currency, categories, etc.).
  - *Generating a feed:* Processes your PrestaShop product data and creates the CSV, XML, or TSV file that you will upload to Microsoft Merchant Center. This file contains all the product attributes in the format required by Microsoft.
  - *Cron URL:* Provides a special web address that, when visited, automatically triggers the feed generation. This is essential for setting up automated daily or hourly updates of your product feed without manual intervention.
- **Recommended value:**
  - Create at least one feed for your primary target market.
  - Set up a cron job using the provided URL to ensure your product feed is regularly updated (e.g., daily) with the latest product information (stock levels, prices, new products).
- **Merchant scenario / example:** You’ve just launched a new product line. By having a daily cron job, your Microsoft Shopping Ads will automatically reflect these new products and their current stock levels the next day, without you having to manually re-upload the feed.

### 2.2 Dedicated Admin Screens & Controller Views

#### AdminExportProductsFeedMicrosoftController (Back Office > Microsoft Merchant Center > Export Products Feed)

This is the primary dedicated screen for managing the details of your product feeds. You’ll access this through a new menu item added by the module, likely under “Catalog” or a new “Microsoft Merchant Center” section.

- **Screen Name & Menu Location:** **Back Office > Microsoft Merchant Center > Export Products Feed** (or similar, depending on module version and PrestaShop menu structure).
- **Available Actions & Settings:** This screen is where you define the specific content and mapping for each of your product feeds. You’ll typically see a list of existing feeds, with options to “Add New Feed” or “Edit” an existing one. When adding/editing, you’ll configure:
  - **Feed Name:** A descriptive name for your feed (e.g., “France - French Feed”, “USA - English Feed”).
  - **Target Country:** The country for which this feed is intended (e.g., France, United States). This impacts currency, language, and tax rules.
  - **Content Language:** The language of the product data in this feed (e.g., French, English).
  - **Currency:** The currency used for prices in this feed (e.g., EUR, USD).
  - **File Format:** Choose between CSV, XML, or TSV, as required by Microsoft Merchant Center.
  - **Category Mapping:** This is a crucial section where you map your PrestaShop categories to Microsoft’s product taxonomy. This helps Microsoft understand what your products are and show them in relevant searches.
  - **Product Filtering:** Options to include/exclude specific products or entire categories from the feed.
  - **Attribute Mapping:** Map PrestaShop product attributes (like size, color, material) to Microsoft’s required attributes (e.g., `size`, `color`, `material`).
  - **Custom Labels:** Define up to 5 custom labels (`custom_label_0` to `custom_label_4`) to segment your products for bidding strategies in Microsoft Ads.
  - **Availability & Condition:** Settings to define how product availability (in stock, out of stock, preorder) and condition (new, used, refurbished) are exported.
  - **GTIN (Global Trade Item Number):** Settings for exporting EAN/UPC codes as GTINs.
  - **Brand:** How product brands are exported.
  - **Description:** Options for exporting product descriptions, often with plain-text conversion.
  - **Image Links:** How product images are linked.
  - **Price & Sale Price:** How regular and sale prices are exported, including tax considerations.
  - **Cron URL:** The unique URL for this specific feed that you’ll use for automated updates.
- **Effect of changes:**
  - Changes here directly impact the content and structure of the generated product feed file. Incorrect settings can lead to product disapprovals in Microsoft Merchant Center.
  - Proper category mapping ensures your products appear in relevant shopping categories on Bing.
  - Accurate price and availability data prevents customer frustration and ad disapprovals.
- **Recommended workflow for daily store management:**
  1. **Initial Setup:** Create a feed for each target country/language combination you advertise in. Carefully map your categories to Microsoft’s taxonomy.
  2. **Review Attributes:** Ensure all critical attributes (GTIN, brand, price, availability, image links) are correctly mapped and exported.
  3. **Set up Cron Jobs:** Implement the provided Cron URLs on your hosting server to automate daily (or more frequent) feed generation. This is critical for keeping your product data fresh.
  4. **Monitor Microsoft Merchant Center:** Regularly check your Microsoft Merchant Center account for any product disapprovals or warnings, and adjust module settings as needed.
  5. **Product Updates:** When adding new products or making significant changes to existing ones, ensure your cron job is running, or manually regenerate the feed if immediate update is required.

#### index.php (mmcfeed/controllers/admin/index.php)

This controller likely serves as a dashboard or a general management view for the module within the PrestaShop Back Office.

- **Screen Name & Menu Location:** Likely part of the main “Microsoft Merchant Center” menu section, possibly the default landing page.
- **Available Actions & Settings:** This screen probably displays an overview of your configured feeds, their last generation date, status, and quick links to edit or generate them. It might also show general module status or important alerts.
- **Effect of changes:** This view provides a quick glance at your feed setup. Actions here (like clicking “Generate Feed”) will trigger the feed generation process.
- **Recommended workflow for daily store management:** Use this screen as a quick dashboard to monitor the health of your product feeds. If you need to manually trigger a feed update, this is where you’d do it.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration Page** | Target Language | Your primary store language | Determines language for product names, descriptions, etc. |
|  | Target Currency | Your primary store currency | Sets currency for all prices in the feed. |
|  | Target Country | Your primary target market | Influences tax, shipping, and country-specific rules. |
|  | Cron URL | Provided by module | Automates feed generation at scheduled intervals. |
| **AdminExportProductsFeedMicrosoftController** | Feed Name | Descriptive (e.g., “France - FR”) | Identifies the specific feed. |
|  | File Format | CSV, XML, or TSV | Choose based on Microsoft Merchant Center requirements. |
|  | Category Mapping | Map PrestaShop to Microsoft Taxonomy | Ensures products appear in correct shopping categories. |
|  | Product Filtering | Based on your strategy | Include/exclude specific products or categories. |
|  | Attribute Mapping | Map PrestaShop to Microsoft attributes | Provides detailed product information for ads. |
|  | Custom Labels (0-4) | As needed for ad campaigns | Segment products for bidding strategies. |
|  | GTIN Export | Enabled if available | Exports EAN/UPC for product identification. |
|  | Availability Date | Enabled if applicable | Exports product availability date for pre-orders. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My products are not appearing in Microsoft Shopping Ads. What should I check?**
A:

1. **Feed Upload Status:** First, check your Microsoft Merchant Center account to ensure your feed has been successfully uploaded and processed without major errors.
2. **Product Disapprovals:** Look for any product disapprovals in the “Diagnostics” section of Microsoft Merchant Center. These will tell you exactly why products aren’t showing. Common reasons include missing GTINs, incorrect image links, or policy violations.
3. **Module Configuration:** Verify that your module settings (language, currency, country, category mapping) are correct and match your Microsoft Merchant Center account settings.
4. **Feed Generation:** Ensure the feed is being generated correctly by the module. Try manually generating it and checking the output file.
5. **Ad Campaigns:** Confirm that your Microsoft Ads campaigns are active, properly targeted, and linked to the correct product feed.

**Q: My product prices or stock levels are outdated in Microsoft Shopping Ads.**
A: This usually means your product feed isn’t being updated frequently enough.

1. **Cron Job:** Ensure your cron job is correctly set up on your hosting server and running at the desired frequency (e.g., daily). The module provides a unique URL for this.
2. **Manual Generation:** If you’ve made urgent changes, you can manually regenerate the feed from the module’s configuration page and re-upload it to Microsoft Merchant Center (if not using scheduled fetches).

**Q: Some of my products are missing from the feed.**
A:

1. **Category Exclusion:** Check if the categories containing these products have been accidentally excluded in the module’s settings.
2. **Product Status:** Ensure the products are active, visible, and in stock in your PrestaShop store. Products marked as “disabled” or “out of stock” (depending on your settings) might be excluded.
3. **Specific Filters:** Review any specific product filters you might have applied in the module configuration.

**Q: How do I map my PrestaShop categories to Microsoft’s product taxonomy?**
A: In the module’s feed configuration screen, there will be a section for “Category Mapping.” You’ll typically see a list of your PrestaShop categories. For each, you’ll need to select the most appropriate category from Microsoft’s predefined taxonomy list. This is a crucial step for ad relevance. Take your time to get this right.

**Q: My custom theme is causing display issues with the module’s admin interface.**
A: While the module’s front-office impact is zero, its back-office interface might sometimes conflict with heavily customized admin themes.

1. **Clear Cache:** First, try clearing your PrestaShop Smarty cache (Advanced Parameters > Performance > Clear cache).
2. **Default Theme:** Temporarily switch your back-office theme to the default PrestaShop theme to see if the issue persists. If it resolves, the conflict is with your custom admin theme.
3. **Contact Support:** If the issue continues, gather screenshots and details and contact MyPresta.eu support for assistance.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The `Microsoft Merchant Center Product Feed` module (`mmcfeed`) follows a standard PrestaShop module architecture, primarily leveraging Admin Controllers for back-office management and Front Controllers for generating the product feed via cron jobs. It does not introduce new `ObjectModel` classes but rather queries existing PrestaShop product data and formats it according to Microsoft Merchant Center specifications. The module relies heavily on configuration values stored in `ps_configuration` and utilizes Smarty templates for rendering both admin interfaces and potentially parts of the feed generation logic (though typically feeds are generated programmatically).

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `mmcfeed/controllers/front/feed.php`
  - **Class name & parent class:** `MmcfeedFeedModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** This controller is the primary endpoint for generating the product feed. It is designed to be called via a unique URL (the “cron URL”) for automated feed generation. It handles the logic of querying product data, applying filtering and mapping rules defined in the back office, and outputting the product feed in the specified format (CSV, XML, TSV). It typically does not render a visual page but outputs raw data.
- `mmcfeed/controllers/front/index.php`
  - **Class name & parent class:** `MmcfeedIndexModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** This is a placeholder or fallback front controller. In many modules, `index.php` in a controller directory serves as a default or a simple entry point. It might redirect or simply return an empty response if no specific action is defined. Its direct functional role in feed generation is likely minimal compared to `feed.php`.

#### Back-Office Admin Controllers

- `mmcfeed/controllers/admin/AdminExportProductsFeedMicrosoft.php`
  - **Tab name and managed entity:** Manages the configuration and generation of individual Microsoft Merchant Center product feeds. It creates a new menu item in the PrestaShop back office.
  - **Responsibility:** This controller handles the CRUD operations for product feed configurations. It displays the list of configured feeds, allows adding new feeds, editing existing ones, and triggering their generation. It processes form submissions for defining feed-specific settings such as target country, language, currency, file format, category mapping, product filtering, and attribute mapping (e.g., `gtin`, `identifier_exists`, `title`, `availability`, `brand`, `link`, `image_link`, `description`, `product_type`, `condition`, `price`, `sale_price`, `tax rate`, `custom_label_0`, `google_product_category`). It interacts with `ps_configuration` for storing these settings and orchestrates the data retrieval and formatting for the feed generation process.
- `mmcfeed/controllers/admin/index.php`
  - **Tab name and managed entity:** Likely a dashboard or overview page for the module in the PrestaShop back office.
  - **Responsibility:** This controller probably serves as the main entry point for the module’s admin interface, providing a summary of configured feeds, their status, and quick actions. It might render a dashboard-like template (`dashboard.tpl`) to give an overview of the module’s activity.

### 4.3 Core Classes & Models (`classes/`)

The provided information indicates no custom classes or models within the `classes/` directory. This suggests the module primarily operates by directly querying PrestaShop’s core `Product`, `Category`, `Language`, `Currency`, etc., `ObjectModel` classes and `ps_configuration` for its settings. The logic for data processing and feed generation is likely encapsulated within the main `mmcfeed.php` module file and the admin/front controllers.

### 4.4 JavaScript Assets (`views/js/`)

- `mmcfeed/lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Back-office.
  - **Responsibility:** Provides autocomplete functionality, likely for searching products, categories, or attributes within the module’s configuration forms. This enhances the user experience when mapping categories or filtering products. It binds to input fields and performs AJAX requests to fetch suggestions.
- `mmcfeed/views/js/admin-app.js`
  - **Scope:** Back-office.
  - **Responsibility:** This is the main JavaScript file for the module’s back-office interface. It handles various interactive elements, form validations, dynamic content loading (e.g., Fancybox modals for category selection), and AJAX calls related to saving configurations or triggering feed generation. It likely binds event listeners to buttons, selects, and input fields within the `AdminExportProductsFeedMicrosoft` controller’s forms.

### 4.5 CSS Stylesheets (`views/css/`)

- `mmcfeed/lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Back-office admin form styling.
  - **Responsibility:** Styles the autocomplete dropdowns and input fields used by the `autocomplete.js` script, ensuring a consistent and user-friendly appearance within the PrestaShop back office.
- `mmcfeed/views/admin-theme.css`
  - **Scope:** Back-office admin form styling.
  - **Responsibility:** Provides general styling adjustments and overrides for the module’s back-office pages to integrate seamlessly with the PrestaShop admin theme. It might define styles for layout, buttons, tables, and form elements specific to the module.
- `mmcfeed/views/css/admin-app.css`
  - **Scope:** Back-office admin form styling.
  - **Responsibility:** Contains specific styles for the module’s custom UI components and layouts within the admin panel, such as category mapping interfaces, product exclusion lists, or dashboard elements. It works in conjunction with `admin-theme.css` to provide the module’s visual identity in the back office.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**: None explicitly listed, indicating the module does not render content directly into standard front-office hooks.
- **Admin templates (`views/templates/admin/`)**:
  - `mmcfeed/views/templates/admin/dashboard.tpl`: Likely the main dashboard template rendered by `controllers/admin/index.php`, providing an overview of the module and its configured feeds.
  - `mmcfeed/views/templates/admin/feeds.tpl`: Probably renders the list of product feeds managed by `AdminExportProductsFeedMicrosoftController`, showing their status, last generation date, and actions.
  - `mmcfeed/views/templates/admin/form-chrome.tpl`: A generic template for wrapping forms in the PrestaShop admin interface, providing consistent styling and structure (e.g., header, footer, save buttons).
  - `mmcfeed/views/templates/admin/layout.tpl`: A base layout template for the module’s admin pages, defining the overall structure, including headers, menus, and content areas.
- **Other templates (`views/`)**:
  - `mmcfeed/lib/searchTool/views/scripts.tpl`: Contains JavaScript code or script inclusions related to the search tool/autocomplete functionality.
  - `mmcfeed/views/categories-fancybox.tpl`: Renders the content for a Fancybox modal used for category selection or mapping, likely providing a tree-like structure for easy navigation.
  - `mmcfeed/views/category_taxonomy.tpl`: A partial template used within `categories-fancybox.tpl` or the main feed configuration form to display and manage the mapping of PrestaShop categories to Microsoft’s taxonomy.
  - `mmcfeed/views/exclude-products.tpl`: Renders the interface for selecting and managing products to be excluded from the feed.
  - `mmcfeed/views/google_lang_links.tpl`: This template name is curious for a Microsoft module. It might be a leftover from a Google Merchant Center module or a generic component for handling language-specific links, potentially for the feed URLs themselves.
  - `mmcfeed/views/returnAlert.tpl`: A generic template for displaying success or error messages to the user in the back office.
  - `mmcfeed/views/script-fancybox.tpl`: Contains JavaScript code or script inclusions specifically for the Fancybox library, used for modal popups.
  - `mmcfeed/views/script.tpl`: A general script inclusion template, potentially for module-wide JavaScript variables or initializations.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create custom SQL tables based on the provided information.
  - All module configurations are stored in the `ps_configuration` table, using keys prefixed with `mmc_` (e.g., `mmc_pf_tree`, `mmc_mmcfeed_products`, `mmc_export_size_attribute`, `mmc_export_exclude_categories`, `mmc_export_availability_date`).
  - It interacts with standard PrestaShop tables such as `ps_product`, `ps_product_lang`, `ps_category`, `ps_category_lang`, `ps_image`, `ps_stock_available`, `ps_attribute_group`, `ps_attribute`, `ps_feature`, `ps_feature_value`, `ps_manufacturer`, `ps_tax_rule`, etc., to retrieve product data.
- **Registered Hooks Table**:
  The module primarily uses back-office hooks for its administration interface and potentially `action` hooks for internal logic. Front-office hooks are not used for rendering content but the module’s front controller `feed.php` acts as a direct endpoint for external services (like cron jobs).

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of front-office pages. | *Not used for rendering content.* If registered, likely for internal JS/CSS loading, but the module’s primary function is feed generation, not front-office display. |
| `displayRightColumn` | In the right column of front-office pages. | *Not used for rendering content.* |
| `displayLeftColumn` | In the left column of front-office pages. | *Not used for rendering content.* |
| `displayFooter` | In the footer of front-office pages. | *Not used for rendering content.* |
| `displayAdminProductsExtra` | On the product edit page in the back office. | *Potentially used* to add a tab or section for product-specific feed exclusions or overrides. |
| `actionAdminControllerSetMedia` | When an admin controller is initialized and before its media (JS/CSS) are loaded. | Used to register module-specific JavaScript (`admin-app.js`, `autocomplete.js`) and CSS (`admin-app.css`, `admin-theme.css`, `autocomplete.css`) for the back-office interface. |
| `actionModuleInstall` | During module installation. | To create configuration entries in `ps_configuration` and potentially register admin tabs. |
| `actionModuleUninstall` | During module uninstallation. | To clean up configuration entries and remove admin tabs. |
| `actionValidateOrder` | After an order has been successfully validated. | *Unlikely for this module.* If present, it would be for tracking conversions or updating feed data based on sales, but not a core function for a feed generator. |
| `actionProductUpdate` | After a product has been updated. | *Potentially used* to trigger a flag for feed regeneration or to update internal caches if the module maintains any. |
| `actionProductAdd` | After a new product has been added. | *Potentially used* to trigger a flag for feed regeneration or to update internal caches. |
| `displayAdminNavBarBefore` | Before the main navigation bar in the back office. | *Potentially used* to add a quick link or notification related to the module. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). MyPresta.eu provides dedicated support for all purchased modules, ensuring your store remains up-to-date and functional.
