---
title: "Zalando Fashion Connector Importer (FCI) - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Zalando Fashion Connector Importer (FCI) PrestaShop module by MyPresta.eu."
sidebar:
  label: "Zalando Fashion Connector Importer (FCI) - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Zalando Fashion Connector Importer (FCI) Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/zalando-fashion-connector-importer-fci.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/zalando-fashion-connector-importer-fci/)
>
> ---


# Zalando Fashion Connector Importer (FCI)

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for most PrestaShop modules and are usually available on any modern hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Zalando Fashion Connector Importer (FCI))

This is the main configuration screen where you set up the basic parameters for your Zalando feed.

- **What this setting does:** This section allows you to define the core information that will be included in your Zalando product feed.
- **Effect of changing this setting:** The values you set here will directly influence the data that Zalando receives about your products, affecting how they are displayed and managed on their platform.

| Setting / Option | What this setting does | Effect of changing this setting | Recommended value | Merchant scenario / example |
| --- | --- | --- | --- | --- |
| **Store** | Specifies the name of your store as it should appear on Zalando. This helps Zalando identify your specific retail outlet. | *When set:* Your specified store name will be included in the product feed. *When left empty:* Zalando might use a default identifier or reject the feed if a store name is mandatory. | Your actual store name (e.g., “My Boutique Fashion”) | If you have multiple physical stores or brands, this helps Zalando differentiate your inventory. |
| **EAN (European Article Number)** | Determines whether the EAN (barcode) of your products should be included in the feed. EANs are crucial for product identification. | *When enabled:* EANs will be part of the feed, allowing Zalando to accurately match your products. *When disabled:* Products might not be correctly identified or could be rejected by Zalando if EAN is a mandatory field. | YES | Essential for most product listings, especially in fashion, to ensure unique identification. |
| **Price** | Controls whether the product’s selling price is included in the feed. | *When enabled:* The current selling price from your PrestaShop store will be sent to Zalando. *When disabled:* Zalando will not receive price updates, potentially leading to outdated pricing on their platform. | YES | Crucial for ensuring customers see the correct price on Zalando. |
| **Retail Price** | Determines if the original retail price (often the “strike-through” price for discounts) is included. | *When enabled:* The original price will be sent, allowing Zalando to display savings or promotions. *When disabled:* Only the current selling price will be sent, potentially hiding discount information. | YES (if you use retail prices for promotions) | If you run sales, including the retail price helps highlight the discount to customers on Zalando. |
| **Quantity** | Specifies whether the current stock quantity of your products is included in the feed. | *When enabled:* Your product stock levels will be updated on Zalando, preventing overselling. *When disabled:* Zalando will not receive stock updates, leading to potential discrepancies and customer dissatisfaction if an item is out of stock. | YES | Absolutely critical to avoid selling products you no longer have available. |
| **Product Name** | Controls whether the product’s name is included in the feed. | *When enabled:* The product name from your PrestaShop store will be sent to Zalando. *When disabled:* Products might be listed without names or rejected if this is a mandatory field. | YES | Essential for customers to identify and search for your products on Zalando. |
| **Client ID (zf\_client)** | Your unique client identifier provided by Zalando for API access. | *When correctly entered:* Allows the module to authenticate with Zalando’s systems. *When incorrect or empty:* The feed generation and updates will fail. | The ID provided by Zalando | You must obtain this from your Zalando Connected Retail account manager. |
| **API Key (zf\_api)** | Your unique API key provided by Zalando for secure communication. | *When correctly entered:* Enables secure data transfer between your store and Zalando. *When incorrect or empty:* The feed generation and updates will fail due to authentication issues. | The key provided by Zalando | This is a security credential; keep it confidential and obtain it from Zalando. |

### 2.2 Dedicated Admin Screens & Controller Views

#### 2.2.1 Product Export Configuration (Back Office > Zalando FCI > Export Products)

This screen, accessible via the PrestaShop back office menu, is where you define the detailed parameters for generating your product feed for Zalando. It allows for fine-tuning what data is included and how it’s formatted.

- **Screen Name & Menu Location:** **Zalando FCI > Export Products** (This will appear as a new menu item in your PrestaShop Back Office navigation).
- **Available Actions & Settings:** This screen presents a form with numerous options to customize your product export. You’ll find fields for selecting stores, currencies, product attributes, and filtering options.
- **Effect of changes:** Changes here directly impact the content and structure of the generated product feed file. Incorrect settings can lead to Zalando rejecting your feed or displaying incorrect product information.
- **Recommended workflow for daily store management:**
  1. Initially, configure all settings carefully according to Zalando’s specifications and your store’s needs.
  2. Generate a test feed and validate it with Zalando (if possible) to ensure all data is correct.
  3. Once configured, you’ll primarily use this screen to generate the feed manually when needed, or you’ll set up a cron job (a scheduled task) to automate the feed generation based on these settings.

| Setting / Option | What this setting does | Effect of changing this setting | Recommended value | Merchant scenario / example |
| --- | --- | --- | --- | --- |
| **Remember Settings (zf\_remember\_settings)** | If enabled, the module will remember your last chosen export settings for convenience. | *When enabled:* Your selections on this page will persist for future exports. *When disabled:* Settings will revert to defaults each time you visit the page. | YES | Saves time if you frequently generate feeds with the same parameters. |
| **Export File Format (zf\_export\_file\_format)** | Selects the output format for the product feed file (e.g., CSV, XML). | *When set:* The generated file will be in the chosen format. *When incorrect:* Zalando might not be able to process the file. | Check Zalando’s requirements (usually CSV or XML) | Zalando will specify the required format for their import system. |
| **Export Type (zf\_export\_type)** | Defines what kind of products to export (e.g., all products, only active, only specific categories). | *When set:* Only products matching the criteria will be included. *When incorrect:* You might export too many or too few products. | All active products, or as per Zalando’s onboarding | If you only want to list a subset of your catalog on Zalando. |
| **Store (zf\_export\_store)** | Allows you to select which PrestaShop store (in a multi-store setup) to export products from. | *When selected:* Products from that specific store will be exported. *When incorrect:* Products from the wrong store might be included. | Your primary store, or the relevant store for Zalando | For merchants running multiple distinct stores from one PrestaShop installation. |
| **Delimiter (zf\_export\_delimiter)** | Specifies the character used to separate data fields in the export file (e.g., comma, semicolon). | *When set:* The chosen delimiter will be used. *When incorrect:* The file will be unreadable by Zalando. | Check Zalando’s requirements (often comma or semicolon) | Crucial for CSV files to ensure data is parsed correctly. |
| **Currency (zf\_export\_currency)** | Selects the currency for product prices in the export file. | *When selected:* Prices will be converted to or displayed in this currency. *When incorrect:* Zalando might display wrong prices or reject the feed. | The currency required by Zalando (e.g., EUR) | If your store operates in multiple currencies, ensure you export in the one Zalando expects. |
| **Product Name Format (zf\_export\_product\_name\_format)** | Defines how product names are formatted (e.g., include manufacturer, attributes). | *When set:* Product names will follow this format. *When incorrect:* Names might be unclear or not meet Zalando’s guidelines. | As per Zalando’s recommendations for clarity | To ensure product names are informative and consistent on Zalando. |
| **Include Tax (zf\_export\_tax)** | Determines if product prices in the feed should include tax. | *When enabled:* Prices will be tax-inclusive. *When disabled:* Prices will be tax-exclusive. | Check Zalando’s requirements for price display | Important for tax compliance and correct price display on Zalando. |
| **Export Country Prices (zf\_export\_country\_prices)** | If enabled, prices specific to different countries will be included (if configured in PrestaShop). | *When enabled:* Country-specific pricing will be exported. *When disabled:* Only default prices will be exported. | YES (if you have country-specific pricing) | For international sellers with varied pricing strategies per region. |
| **Default Country (PS\_COUNTRY\_DEFAULT)** | The default country for your PrestaShop store, used as a fallback for some settings. | *When set:* Provides a base country for pricing and tax calculations. | Your store’s primary country | Ensures consistent default behavior for international settings. |
| **Export Active Products Only (zf\_export\_active)** | If enabled, only products currently marked as “active” in PrestaShop will be exported. | *When enabled:* Only available products are sent. *When disabled:* Inactive products might be included, leading to errors on Zalando. | YES | Prevents listing products you don’t want to sell or are no longer available. |
| **Export Manufacturers (zf\_export\_manufacturers)** | If enabled, manufacturer information will be included in the feed. | *When enabled:* Manufacturer data is sent. *When disabled:* Manufacturer data is omitted. | YES | Useful for customers to filter by brand on Zalando. |
| **Export Suppliers (zf\_export\_suppliers)** | If enabled, supplier information will be included in the feed. | *When enabled:* Supplier data is sent. *When disabled:* Supplier data is omitted. | NO (unless required by Zalando) | Less common for customer-facing feeds, more for internal tracking. |
| **Export Category (zf\_export\_category)** | If enabled, product category information will be included. | *When enabled:* Category data is sent. *When disabled:* Category data is omitted. | YES | Helps Zalando categorize your products correctly and aids customer navigation. |
| **Export In-Stock Products Only (zf\_export\_instock)** | If enabled, only products with available stock will be exported. | *When enabled:* Only products you can fulfill are sent. *When disabled:* Out-of-stock products might be included, leading to overselling issues. | YES | Crucial for preventing customer disappointment due to unavailable items. |
| **Exclude Price Max (zf\_export\_exclude\_price\_max)** | If enabled, products above a certain price threshold will be excluded from the feed. | *When enabled:* Products exceeding the max price will not be exported. *When disabled:* All products, regardless of price, are exported. | NO (unless you have specific high-value items to exclude) | Useful if Zalando has price limits or if you only want to sell certain price ranges on their platform. |
| **Exclude Price Max Value (zf\_export\_exclude\_price\_max\_v)** | The maximum price value for the “Exclude Price Max” setting. | *When set:* Defines the upper price limit for exported products. | Leave empty if not excluding by max price | If you only want to sell items under €500 on Zalando, set this to 500. |

#### 2.2.2 Admin Index Screen (Back Office > Zalando FCI > Index)

This screen likely serves as a landing page or a simple management view for the module, potentially displaying information or providing quick links.

- **Screen Name & Menu Location:** **Zalando FCI > Index** (This will appear as a new menu item in your PrestaShop Back Office navigation, often the first item under the module’s main menu).
- **Available Actions & Settings:** This screen typically displays a grid or a simple informational panel. It might show the last export date, a link to generate the feed, or general module status. It’s usually not a screen for detailed configuration but rather for overview or quick actions.
- **Effect of changes:** There are usually no direct “settings” to change on this screen. Its purpose is more informational or navigational.
- **Recommended workflow for daily store management:** Use this as a quick entry point to the module, to check the status of your last export, or to navigate to the “Export Products” screen for detailed configuration and feed generation.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Store | Your Store Name | Identifies your store on Zalando. |
| **Module Configuration** | EAN | YES | Essential for product identification. |
| **Module Configuration** | Price | YES | Ensures correct pricing on Zalando. |
| **Module Configuration** | Retail Price | YES (if used) | Displays original price for promotions. |
| **Module Configuration** | Quantity | YES | Critical for accurate stock levels, prevents overselling. |
| **Module Configuration** | Product Name | YES | Essential for product identification and search. |
| **Module Configuration** | Client ID (zf\_client) | Provided by Zalando | Authenticates with Zalando API. |
| **Module Configuration** | API Key (zf\_api) | Provided by Zalando | Secures communication with Zalando API. |
| **Export Products** | Remember Settings | YES | Saves time by preserving export choices. |
| **Export Products** | Export File Format | Check Zalando’s requirements | Defines the output file type. |
| **Export Products** | Export Type | All active products | Controls which products are included. |
| **Export Products** | Store | Your primary store | Selects products from a specific store (multi-store). |
| **Export Products** | Delimiter | Check Zalando’s requirements | Separates fields in CSV files. |
| **Export Products** | Currency | Required by Zalando (e.g., EUR) | Sets the currency for exported prices. |
| **Export Products** | Product Name Format | As per Zalando’s recommendations | Formats product names for clarity. |
| **Export Products** | Include Tax | Check Zalando’s requirements | Determines if prices are tax-inclusive. |
| **Export Products** | Export Country Prices | YES (if applicable) | Includes country-specific pricing. |
| **Export Products** | Default Country | Your store’s primary country | Fallback for country-related settings. |
| **Export Products** | Export Active Products Only | YES | Prevents listing inactive products. |
| **Export Products** | Export Manufacturers | YES | Includes brand information. |
| **Export Products** | Export Suppliers | NO (unless required) | Includes supplier information. |
| **Export Products** | Export Category | YES | Helps Zalando categorize products. |
| **Export Products** | Export In-Stock Products Only | YES | Prevents listing out-of-stock items. |
| **Export Products** | Exclude Price Max | NO (unless needed) | Excludes products above a set price. |
| **Export Products** | Exclude Price Max Value | Leave empty if not excluding | Sets the maximum price for exclusion. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My products aren’t appearing on Zalando, or the feed is being rejected. What should I check first?**
A1:

- **Check Module Configuration:** Go to **Modules > Module Manager > Zalando Fashion Connector Importer (FCI) > Configure**. Ensure your “Client ID” and “API Key” are correctly entered as provided by Zalando.
- **Check Export Settings:** Navigate to **Zalando FCI > Export Products**. Verify that the “Export File Format” and “Delimiter” match Zalando’s exact requirements. Also, ensure “Export Active Products Only” and “Export In-Stock Products Only” are enabled if you only want to send available items.
- **Validate Product Data:** Ensure your products in PrestaShop have valid EANs, names, prices, and stock quantities. Missing or invalid data is a common reason for rejections.
- **Clear Cache:** Sometimes, old data can persist. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions).

**Q2: The prices or stock levels on Zalando are not updating correctly.**
A2:

- **Check Export Frequency:** How often are you generating the feed? If you’re doing it manually, you need to do it regularly. If you’ve set up a cron job, ensure it’s running at the desired frequency (e.g., hourly).
- **Module Configuration:** Double-check that “Price” and “Quantity” are enabled on the main module configuration screen.
- **Zalando’s Processing Time:** Remember that even after you generate and send the feed, Zalando’s systems need time to process and update the data. This can sometimes take a few minutes to several hours depending on their load.

**Q3: I have a custom theme, and the module’s admin interface looks a bit off.**
A3:

- The module’s admin interface uses standard PrestaShop styling, but minor visual inconsistencies can occur with highly customized back-office themes. This usually doesn’t affect functionality.
- If it’s a significant issue, contact MyPresta.eu support. For minor tweaks, a web developer can often adjust the `zalandofci/views/admin-theme.css` file or add custom CSS to your PrestaShop back office.

**Q4: How do I set up a cron job to automate the feed generation?**
A4:

- The exact steps depend on your hosting provider. You’ll typically find a “Cron Jobs” or “Scheduled Tasks” section in your hosting control panel (e.g., cPanel, Plesk).
- You’ll need the URL that triggers the feed generation. This URL is usually provided on the module’s “Export Products” configuration page after you save your settings, or it can be constructed using the front controller path (e.g., `yourstore.com/module/zalandofci/feed`).
- Set the cron job to execute this URL at your desired interval (e.g., `wget -q -O /dev/null "http://yourstore.com/module/zalandofci/feed"`). If you’re unsure, consult your hosting provider’s documentation or support.

**Q5: The module is installed, but I don’t see “Zalando FCI” in my Back Office menu.**
A5:

- **Clear PrestaShop Cache:** Go to **Advanced Parameters > Performance** and clear the cache. Sometimes the menu doesn’t refresh immediately after module installation.
- **Check Module Status:** Go to **Modules > Module Manager** and search for “Zalando Fashion Connector Importer (FCI)”. Ensure it is listed as “Installed” and “Enabled”.
- **Permissions:** In rare cases, employee permissions might restrict menu visibility. Check **Administration > Permissions** for your employee profile.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The Zalando Fashion Connector Importer (FCI) module follows a standard PrestaShop module architecture, leveraging MVC principles where applicable. It primarily focuses on data export, utilizing a combination of front and admin controllers. The core logic resides in the main module file and admin controllers for configuration and feed generation. It does not appear to use custom `ObjectModel` classes, instead directly querying the PrestaShop database for product data. The module’s primary function is to generate a data feed, which is typically consumed by an external system (Zalando) via a scheduled task (cron job) hitting a front controller.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

These controllers are accessible from the front-office URL and are typically used for generating the product feed, often triggered by a cron job.

- `controllers/front/feed.php`
  - **Class name & parent class**: `ZalandofciFeedModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility**: This is the primary endpoint for generating the product feed. It responds to requests (typically from cron jobs) and dynamically generates the product data based on the module’s configuration. It likely fetches product information (EAN, price, quantity, name) and formats it into the specified output (e.g., CSV, XML) for Zalando. This controller does not render a visual page but outputs raw data.
- `controllers/front/index.php`
  - **Class name & parent class**: `ZalandofciIndexModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility**: This controller likely serves as a fallback or a simple entry point, potentially redirecting or displaying a minimal message. In many modules, an `index.php` front controller is present to prevent directory listing or provide a default action if no specific action is requested.

#### Back-Office Admin Controllers

These controllers manage the module’s configuration and product export settings within the PrestaShop Back Office.

- `controllers/admin/AdminExportProductsFci.php`
  - **Tab name and managed entity**: “Export Products” under the “Zalando FCI” menu. This controller manages the detailed product export configuration.
  - **Responsibility**: This controller handles the display and submission of the product export form. It retrieves configuration settings (e.g., `zf_export_file_format`, `zf_export_type`, `zf_export_currency`, `zf_export_tax`, `zf_export_active`, etc.) from `ps_configuration`, processes user input, and triggers the actual product data retrieval and formatting logic for the feed generation. It likely uses `AdminController` methods for form rendering (`renderForm`) and saving (`postProcess`).
- `controllers/admin/index.php`
  - **Tab name and managed entity**: “Index” under the “Zalando FCI” menu.
  - **Responsibility**: Similar to its front-office counterpart, this admin controller likely serves as a landing page or a simple overview. It might display general module information, quick links to other admin pages, or a status message. It’s not typically involved in complex data management but rather in navigation and informational display.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes or models in the `classes/` directory. This suggests that the module directly interacts with PrestaShop’s core `Product` and `ProductSupplier` (or similar) `ObjectModel` classes and the `Configuration` class for settings. Data retrieval is likely handled directly within the controllers or the main module file using `Db::getInstance()->executeS()` or `DbQuery` objects.

### 4.4 JavaScript Assets (`views/js/`)

The module dossier indicates no custom JavaScript files. This implies that the module’s configuration and functionality are primarily server-side driven, with minimal or no dynamic front-end interactions in the Back Office or Front Office that require custom JS.

### 4.5 CSS Stylesheets (`views/css/`)

- `zalandofci/views/admin-theme.css`
  - **Scope**: Back-office admin form styling.
  - **Main UI components and containers it styles**: This stylesheet is responsible for the visual presentation of the module’s configuration forms and potentially any custom grids or informational panels within the PrestaShop Back Office. It ensures that the module’s interface integrates visually with the PrestaShop admin theme.
  - **Key CSS class selectors developers can override**: Developers can inspect the module’s admin pages to identify specific classes (e.g., `.zalandofci-form`, `.zalandofci-panel`, `.zalandofci-alert`) and override them in their custom admin theme or by adding CSS via a `displayBackOfficeHeader` hook.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - The module dossier does not explicitly list templates within a `hook/` subdirectory, but it registers hooks like `displayHeader`, `displayRightColumn`, `displayProduct`, `displayFooter`. If any visual output were intended for these hooks, templates would typically reside here. Given the module’s purpose (backend data feed), it’s likely these hooks are used for technical purposes (e.g., adding JS/CSS, or not used for visual output at all).
- **Admin templates (`views/templates/admin/`)**:
  - `zalandofci/views/how-it-works.tpl`
    - **Purpose**: This template likely provides informational content within the Back Office, possibly on the main configuration page or the “Index” screen, explaining how the module functions or providing setup instructions.
  - `zalandofci/views/returnAlert.tpl`
    - **Purpose**: This template is probably used to display success or error messages (alerts) within the Back Office after an action (e.g., saving configuration, generating a feed).
  - `zalandofci/views/script.tpl`
    - **Purpose**: This template might contain inline JavaScript code or be used to include external JS files conditionally within the Back Office. It could be used for dynamic form behavior or to trigger specific actions.
- **Front-office templates (`views/templates/front/`)**:
  - The module dossier does not list any specific front-office templates, reinforcing the idea that the module does not have a direct visual presence on the customer-facing side of the store.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not appear to create custom SQL tables during installation (`install()` method).
  - All module-specific configuration settings (e.g., `zf_client`, `zf_api`, `zf_export_file_format`, `zf_remember_settings`, etc.) are stored in PrestaShop’s standard `ps_configuration` table. These keys are prefixed with `zf_` or `PS_` (for core PrestaShop settings used by the module).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Renders in the `<head>` section of all front-office pages. | Potentially used to include module-specific CSS or JS, though no custom JS/CSS is listed for the front office. Could also be used for meta tags or other non-visual elements. |
| `displayRightColumn` | Renders in the right column of pages that have one. | Unlikely to be used for visual output given the module’s purpose. Could be a legacy hook or used for very specific, non-visual data injection. |
| `displayProduct` | Renders on the product page. | Unlikely to be used for visual output. Could be used to add hidden data attributes to product elements for external scripts, though no custom JS is listed. |
| `displayFooter` | Renders in the footer section of all front-office pages. | Similar to `displayHeader`, could be used for including JS/CSS or other non-visual elements at the end of the page load. |
| `actionAdminControllerSetMedia` | Executed when an admin controller is setting its media (JS/CSS). | Used by `AdminExportProductsFci` to load `zalandofci/views/admin-theme.css` for its configuration forms. |

## 5. Official Support & Updates

For official updates, technical support, and to download the latest versions of the Zalando Fashion Connector Importer (FCI) module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist you with any issues or questions regarding the module’s functionality and integration.
