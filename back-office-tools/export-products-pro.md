---
title: "Export Products Pro - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Export Products Pro PrestaShop module by MyPresta.eu."
sidebar:
  label: "Export Products Pro - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Export Products Pro Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/export-products-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/export-products-pro/)
>
> ---


# Export Products Pro

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for general PrestaShop operation, but this module has no specific exotic requirements beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Export Products Pro)

This is the main configuration screen where you define the general behavior and settings for your product exports.

#### General Settings

- **Export format**:

  - **What this setting does:** Determines the file format for your exported data.
  - **Effect of changing this setting:**
    - *When set to CSV:* The module will generate a Comma Separated Values file, which is widely compatible with spreadsheet software like Excel, Google Sheets, or LibreOffice Calc. This is the most common and versatile format.
    - *When set to XML:* The module will generate an Extensible Markup Language file, often used for more structured data exchange between systems or for specific product feeds (e.g., Google Shopping).
  - **Recommended value:** CSV for general use and spreadsheet analysis. XML if you have a specific system that requires it.
  - **Merchant scenario / example:** If you want to open the data in Excel to analyze prices, choose CSV. If you’re creating a feed for a third-party application that specifies XML, choose XML.
- **Delimiter**:

  - **What this setting does:** This character separates the different columns (fields) in your CSV file.
  - **Effect of changing this setting:**
    - *When set to comma (,):* Each piece of data in a row will be separated by a comma. This is standard for many systems.
    - *When set to semicolon (;):* Each piece of data will be separated by a semicolon. This is common in some European regions or when commas might appear within your product data (e.g., in descriptions), causing parsing issues.
  - **Recommended value:** Comma (`,`) for most cases. If your spreadsheet software struggles to open the CSV correctly, try semicolon (`;`).
  - **Merchant scenario / example:** If you open your CSV in Excel and all data appears in one column, try changing the delimiter to semicolon and re-exporting.
- **Export only active products**:

  - **What this setting does:** Controls whether only products currently visible and purchasable on your store are included in the export.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* Only products with their “Status” set to “Online” or “Active” in your PrestaShop back office will be exported. This is useful for current inventory.
    - *When disabled (No):* All products, including those marked as inactive or disabled, will be exported. This is useful for a complete catalog backup or auditing.
  - **Recommended value:** Yes, for most operational exports.
  - **Merchant scenario / example:** If you’re generating a product feed for Google Shopping, you only want active products, so enable this. If you’re doing a full data backup, disable it.
- **Export only in stock products**:

  - **What this setting does:** Filters the export to include only products that currently have a quantity greater than zero.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* Only products that are currently in stock will be exported.
    - *When disabled (No):* Products regardless of their stock level (in stock or out of stock) will be exported.
  - **Recommended value:** Yes, if you’re creating a feed for sales or current availability.
  - **Merchant scenario / example:** If you’re sending a list of available products to a dropshipper, enable this. If you need to see all products, including those you need to reorder, disable it.
- **Export product images**:

  - **What this setting does:** Determines if the URLs of your product images are included in the export.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* The CSV/XML file will contain columns with the URLs to your product images.
    - *When disabled (No):* Image URLs will be omitted, resulting in a smaller file size if images are not needed.
  - **Recommended value:** Yes, if you need images for marketplaces or external catalogs.
  - **Merchant scenario / example:** If you’re updating a product catalog on another platform that requires image URLs, enable this.
- **Export product short description**:

  - **What this setting does:** Includes the short description (summary) of your products in the export.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* The short description for each product will be included as a column.
    - *When disabled (No):* The short description will be omitted.
  - **Recommended value:** Yes, as short descriptions are often used for product listings and search results.
  - **Merchant scenario / example:** If you’re creating a product feed for a comparison site that displays short descriptions, enable this.
- **Export product description**:

  - **What this setting does:** Includes the full, detailed description of your products in the export.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* The full product description will be included as a column.
    - *When disabled (No):* The full description will be omitted.
  - **Recommended value:** Yes, for a complete data export.
  - **Merchant scenario / example:** If you’re migrating your store to a new platform and need all product content, enable this.
- **Remember settings**:

  - **What this setting does:** If enabled, the module will save your last-used export settings (filters, selected fields) for your next export.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* The module will pre-fill the export form with your previous choices, saving time for repetitive exports.
    - *When disabled (No):* The export form will always reset to default settings each time you visit it.
  - **Recommended value:** Yes, if you frequently perform similar exports.
  - **Merchant scenario / example:** If you regularly export a list of active, in-stock products with specific fields, enabling this will make your workflow faster.

#### Filter Options

- **Export products from category**:

  - **What this setting does:** Allows you to select specific product categories to include in your export.
  - **Effect of changing this setting:**
    - *When specific categories are selected:* Only products belonging to those categories will be exported.
    - *When no categories are selected (or all are selected):* All products, regardless of category, will be considered for export (subject to other filters).
  - **Recommended value:** Select specific categories if you need a targeted export; otherwise, leave unselected for a full catalog.
  - **Merchant scenario / example:** If you only want to export products from your “Electronics” category, select it here.
- **Export only parent categories**:

  - **What this setting does:** If you’ve selected categories, this option further refines whether products from subcategories are also included.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* Only products directly assigned to the selected parent categories will be exported. Products in their subcategories will be excluded.
    - *When disabled (No):* Products from the selected parent categories AND all their subcategories will be exported.
  - **Recommended value:** No, for most cases, as you usually want products from subcategories too. Enable only if you have a specific reason to exclude subcategory products.
  - **Merchant scenario / example:** If you have “Clothing” as a parent category and “T-Shirts” as a subcategory, enabling this would export products directly in “Clothing” but not those in “T-Shirts”.
- **Export products from manufacturer**:

  - **What this setting does:** Allows you to filter products by their assigned manufacturer.
  - **Effect of changing this setting:**
    - *When specific manufacturers are selected:* Only products from those manufacturers will be exported.
    - *When no manufacturers are selected (or all are selected):* Products from all manufacturers will be considered.
  - **Recommended value:** Select specific manufacturers for targeted exports.
  - **Merchant scenario / example:** If you need to send a product list to a specific brand for review, select their manufacturer here.
- **Export products from supplier**:

  - **What this setting does:** Allows you to filter products by their assigned supplier.
  - **Effect of changing this setting:**
    - *When specific suppliers are selected:* Only products from those suppliers will be exported.
    - *When no suppliers are selected (or all are selected):* Products from all suppliers will be considered.
  - **Recommended value:** Select specific suppliers for targeted exports.
  - **Merchant scenario / example:** If you need to provide a list of products you stock from a particular supplier, select them here.

### 2.2 Dedicated Admin Screen: Export Products Pro Dashboard (Back Office > Catalog > Export Products Pro)

This is the primary interface for initiating and managing your product exports.

- **Screen Name & Menu Location:** **Catalog > Export Products Pro**
- **Available Actions & Settings:**
  - **Export Button:** This is the main action button. Clicking it will start the export process based on the settings you’ve configured on this page.
  - **Field Selection:** Below the general settings, you will find a comprehensive list of all available product and combination fields. You can individually check or uncheck which fields you want to include in your export.
    - **Product Fields:** Includes standard product details like ID, name, reference, EAN13, UPC, price, quantity, weight, descriptions, etc.
    - **Combination Fields:** If your products have combinations (e.g., size, color), you’ll see fields specific to combinations like “Combination ID”, “Attribute (Name:Type:Position)”, “Value (Value:Position)”, “Impact on price”, “Impact on weight”, “Default (0 = No, 1 = Yes)”, “Combination availability date”.
  - **Effect of changes:**
    - **Selecting/Deselecting fields:** Only the checked fields will appear as columns in your exported CSV/XML file. This allows you to create highly customized exports, including only the data you need and omitting unnecessary information.
  - **Recommended workflow for daily store management:**
    1. Navigate to **Catalog > Export Products Pro**.
    2. Review the “General Settings” and “Filter Options” at the top of the page. Adjust them based on whether you need active products, in-stock products, specific categories, manufacturers, or suppliers.
    3. Carefully select the “Product Fields” and “Combination Fields” you wish to include in your export. If you’re unsure, it’s often safer to select more fields initially and then remove unwanted columns in your spreadsheet software.
    4. Click the “Export” button. The module will generate and prompt you to download the CSV or XML file.
    5. Open the downloaded file in your preferred spreadsheet software (e.g., Excel, Google Sheets) to verify the data and format.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Export format | CSV | Determines output file type (CSV or XML). |
|  | Delimiter | Comma (`,`) | Character separating fields in CSV. Change if parsing issues occur. |
|  | Export only active products | Yes | Includes only active products. |
|  | Export only in stock products | Yes | Includes only products with quantity > 0. |
|  | Export product images | Yes | Includes image URLs in export. |
|  | Export product short description | Yes | Includes product short description. |
|  | Export product description | Yes | Includes full product description. |
|  | Remember settings | Yes | Saves your last export choices for convenience. |
|  | Export products from category | (None selected) | Filters export by selected categories. |
|  | Export only parent categories | No | If categories selected, includes/excludes subcategory products. |
|  | Export products from manufacturer | (None selected) | Filters export by selected manufacturers. |
|  | Export products from supplier | (None selected) | Filters export by selected suppliers. |
| **Export Products Pro Dashboard** | **Field Selection** | Varies by need | Choose specific product/combination attributes to include as columns in the export file. |
|  | Export Button | N/A | Initiates the product export based on all configured settings. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My exported CSV file looks garbled or all data is in one column when I open it in Excel.**
**A1:** This is usually a delimiter issue or character encoding problem.

- **Solution 1 (Delimiter):** Go back to the module configuration, change the “Delimiter” setting from comma (`,`) to semicolon (`;`), and re-export. Try opening the new file.
- **Solution 2 (Encoding):** When opening the CSV in Excel, use the “Data > From Text/CSV” option. In the import wizard, ensure you select the correct “File Origin” or “Encoding” (usually `UTF-8`) and specify the correct delimiter.

**Q2: Some products are missing from my export, but I know they exist in my store.**
**A2:** Check your filter settings in the module configuration:

- **Solution:** Ensure “Export only active products” and “Export only in stock products” are set correctly for your needs. If you’ve selected specific categories, manufacturers, or suppliers, double-check that the missing products fall within those filters. If you want everything, ensure no filters are selected.

**Q3: The export process takes a very long time or times out for large catalogs.**
**A3:** Exporting thousands of products can be resource-intensive.

- **Solution 1:** Try exporting smaller batches by using the “Export products from category,” “manufacturer,” or “supplier” filters.
- **Solution 2:** If you have access to your server settings, you might need to temporarily increase PHP’s `memory_limit` and `max_execution_time` in your `php.ini` file. Contact your hosting provider for assistance with this.
- **Solution 3:** Deselect unnecessary fields to reduce the amount of data processed.

**Q4: How do I translate the column headers in the exported file?**
**A4:** The column headers in the exported file are generally based on the internal field names or default PrestaShop labels, and are not directly translatable through the module’s interface.

- **Solution:** The easiest way is to open the exported CSV file in a spreadsheet program (like Excel or Google Sheets) and manually rename the column headers to your desired language or terminology. Save the file with the new headers.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the Export Products Pro module, intended for developers, webmasters, and technical agencies.

### 4.1 Architecture Overview

The `Export Products Pro` module follows the standard PrestaShop MVC pattern, primarily focusing on back-office functionality. It leverages Admin Controllers for its user interface and custom classes for data handling and feed generation. The module’s core logic resides in its main `exportproducts.php` file and the `AdminExportProductsController` which manages the export process and configuration. It uses `ObjectModel` for its custom data if any, though in this case, it primarily interacts with core PrestaShop product data.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `controllers/front/feed.php`
  - **Class name & parent class:** `ExportProductsFeedModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** This controller is likely responsible for generating a product feed (e.g., XML or CSV) that can be accessed directly via a URL. It would handle the logic for querying products based on specific parameters and outputting them in the chosen format. This could be used for automated feed generation for external services.
- `controllers/front/index.php`
  - **Class name & parent class:** `ExportProductsIndexModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** This controller might serve as a default entry point or a fallback for front-office requests related to the module. Given the module’s primary function, it might redirect or display a simple message, or it could be a placeholder for future front-office features.

#### Back-Office Admin Controllers

- `controllers/admin/AdminExportProducts.php`
  - **Tab name and managed entity:** This controller manages the main “Export Products Pro” dashboard in the PrestaShop Back Office, accessible via **Catalog > Export Products Pro**. It does not manage a single `ObjectModel` entity in the traditional sense but rather orchestrates the product export process.
  - **Responsibility:**
    - Displays the configuration form for export settings (filters, format, delimiter, etc.).
    - Handles the POST request when the “Export” button is clicked.
    - Processes the selected product and combination fields.
    - Queries the PrestaShop database for product and combination data based on the applied filters.
    - Generates the CSV or XML file content.
    - Initiates the file download to the user’s browser.
    - Manages the `ep_remember_settings` functionality to persist user choices.
- `controllers/admin/index.php`
  - **Responsibility:** This is typically an empty file or a file containing a simple `die('No direct script access');` statement, serving as a security measure to prevent direct access to the `controllers/admin` directory. It does not contain active controller logic.

### 4.3 Core Classes & Models (`classes/`)

- `classes/ExportProductsFeed.php`
  - **What database table it interacts with:** This class likely interacts with various core PrestaShop tables such as `ps_product`, `ps_product_lang`, `ps_product_shop`, `ps_category_product`, `ps_manufacturer`, `ps_supplier`, `ps_image`, `ps_product_attribute`, `ps_product_attribute_combination`, `ps_attribute`, `ps_attribute_lang`, `ps_attribute_group`, `ps_attribute_group_lang`, etc.
  - **Whether it extends `ObjectModel` and definition of `$definition` fields:** It is unlikely to extend `ObjectModel` directly, as its primary role is to *query* and *process* existing product data rather than manage a new database entity. It would contain methods for fetching product data, filtering it, and formatting it for export.
  - **Key public methods and business logic encapsulated:**
    - Methods for retrieving product data with various joins (categories, manufacturers, suppliers, images, descriptions).
    - Methods for handling product combinations and their specific attributes.
    - Logic for applying filters (active, in-stock, category, manufacturer, supplier).
    - Methods for formatting data into CSV or XML structures.
    - Potentially methods for handling large datasets to prevent memory exhaustion.
- `classes/index.php`
  - **Responsibility:** Similar to `controllers/admin/index.php`, this is a security file to prevent direct directory listing or execution of files within the `classes/` directory.

### 4.4 JavaScript Assets (`views/js/`)

The provided module inventory indicates no custom JavaScript files (`[]`). This suggests that the module’s front-end (Back Office configuration) relies entirely on PrestaShop’s native JavaScript libraries (e.g., jQuery, PrestaShop’s core JS) for form handling, or its interface is simple enough not to require complex client-side interactions beyond standard form submissions.

### 4.5 CSS Stylesheets (`views/css/`)

The provided module inventory indicates no custom CSS files (`[]`). This implies that the module’s Back Office interface uses PrestaShop’s default back-office styling, ensuring a consistent look and feel without introducing custom styles.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`exportproducts/script.tpl`**
  - **Scope:** Likely a generic template used for embedding small JavaScript snippets or configuration variables directly into the HTML, possibly hooked into `displayHeader` or `displayBackOfficeHeader` if it needs to run on specific pages. Given no JS files, this might contain inline JS for form validation or dynamic behavior.
- **`exportproducts/views/templates/admin/dashboard.tpl`**
  - **Scope:** Admin template.
  - **Purpose:** This is the main template for the `AdminExportProductsController`. It renders the entire export configuration form, including general settings, filter options, and the extensive list of product and combination fields that the merchant can select for export. It also contains the “Export” button.
- **`exportproducts/views/templates/admin/form_header.tpl`**
  - **Scope:** Admin template.
  - **Purpose:** This template likely renders a common header section for the admin configuration forms, potentially including the module’s title, description, and perhaps some introductory text or links. It’s designed to be included at the top of other admin templates (like `dashboard.tpl`) for consistency.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not appear to create its own custom database tables.
  - It stores its configuration settings (e.g., `ep_export_format`, `ep_export_active`, `ep_remember_settings`, `ep_export_categories_onlycats`, etc.) in the standard PrestaShop `ps_configuration` table. These keys are prefixed with `ep_` for “Export Products”.
  - It primarily reads data from core PrestaShop tables: `ps_product`, `ps_product_lang`, `ps_product_shop`, `ps_category_product`, `ps_manufacturer`, `ps_supplier`, `ps_image`, `ps_product_attribute`, `ps_product_attribute_combination`, `ps_attribute`, `ps_attribute_lang`, `ps_attribute_group`, `ps_attribute_group_lang`, etc.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayModuleRoutes` | During route generation for modules. | Allows the module to register custom friendly URLs for its front-office controllers (e.g., `/feed` for `feed.php`). |
| `moduleRoutes` | During route generation for modules. | Similar to `displayModuleRoutes`, used for defining custom URL patterns and associating them with module controllers. |
| `displayBackOfficeHeader` | Renders content in the `<head>` section of the Back Office. | Potentially used to include `script.tpl` for inline JS or CSS, or to add specific meta tags or JS variables needed by the admin interface. |
| `actionAdminControllerSetMedia` | Before an Admin Controller renders its page. | Used to register CSS and JavaScript files for the Back Office, ensuring they are loaded only when needed. (Though no JS/CSS files are listed, this hook would be the standard place if they were present). |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the **Export Products Pro** module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to ensuring the smooth operation and continued enhancement of our modules.
