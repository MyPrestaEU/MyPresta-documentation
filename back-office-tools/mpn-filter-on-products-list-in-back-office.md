---
title: "MPN filter on products list in back office - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the MPN filter on products list in back office PrestaShop module by MyPresta.eu."
sidebar:
  label: "MPN filter on products list in back office - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy MPN filter on products list in back office Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/mpn-filter-on-products-list-in-back-office.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/mpn-filter-on-products-list-in-back-office/)
>
> ---


# MPN filter on products list in back office

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient and usually enabled by default on most hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This module is designed to be plug-and-play. It does not have a dedicated configuration screen with settings to adjust. Upon installation, the module automatically integrates the MPN column and filtering capabilities into your product list.

You will see a standard “Configuration” button after installation, but clicking it will typically show a simple message indicating that the module is active and requires no further configuration.

**How to use the module after installation:**

1. Navigate to **Catalog > Products** in your PrestaShop back office.
2. You will now see a new column labeled “MPN” in your product list.
3. You can click on the “MPN” column header to sort your products by MPN in ascending or descending order.
4. Above the product list, in the filter section, you will find a new input field under the “MPN” column. You can type an MPN (or part of an MPN) into this field and press Enter or click the “Filter” button to filter your product list by that MPN.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | (No configurable settings) | N/A | The module works automatically upon installation, adding MPN column and filter to Catalog > Products. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve installed the module, but I don’t see the MPN column in my product list.**
A: First, ensure you are looking at the “Catalog > Products” page in your PrestaShop back office. If it’s still not visible, try clearing your PrestaShop cache:
1. Go to **Advanced Parameters > Performance**.
2. Click “Clear cache” in the top right corner.
3. Also, clear your browser’s cache.
4. If the issue persists, ensure the module is enabled in the Module Manager.

**Q: Can I use this module to add MPN to the front office for customers?**
A: No, this module is strictly for back-office administration. It does not modify the front office or display MPNs to customers. You would need a separate module or custom development for front-office MPN display.

**Q: Does this module create new database fields for MPN?**
A: No, PrestaShop already has an `mpn` field in the `ps_product` table. This module simply makes that existing field visible and filterable in the back office product list. It does not add new database tables or fields.

**Q: The filter isn’t working, or the column isn’t sorting correctly.**
A: This could be a caching issue or a conflict with another module that modifies the product list.
1. Clear PrestaShop cache (as described above).
2. If you have other modules that heavily customize the “Catalog > Products” page, try temporarily disabling them one by one to identify a conflict.
3. Ensure your PrestaShop version is fully compatible with the module version you downloaded.

**Q: How do I enter or edit the MPN for a product?**
A: You edit the MPN directly on the product’s edit page:
1. Go to **Catalog > Products**.
2. Click “Edit” next to the product you want to modify.
3. Navigate to the “Quantities” tab (or “Basic settings” in older versions).
4. You will find the “MPN (Manufacturer Part Number)” field there. Enter or update the value and save the product. The new MPN will then appear in the product list.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “MPN filter on products list in back office” module is a lightweight PrestaShop module primarily designed to extend the existing Back Office product listing functionality. It achieves this by overriding specific Twig templates responsible for rendering the product catalog page in PrestaShop 1.7.x, 8.x, and 9.x. It does not introduce new controllers, models, or complex JavaScript/CSS assets. Its core function is to inject the MPN column and its associated filter into the standard product list view.

### 4.2 Controllers (`controllers/`)

This module does not introduce any custom front-office or back-office controllers. All its functionality is achieved through template overrides and PrestaShop’s core module mechanisms.

### 4.3 Core Classes & Models (`classes/`)

This module does not introduce any custom PHP classes or `ObjectModel` definitions. It leverages the existing `Product` `ObjectModel` and its `mpn` field.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include any custom JavaScript files. The filtering and sorting functionality for the new MPN column is handled by PrestaShop’s existing DataTables.js implementation for the product list, which automatically adapts to new columns.

### 4.5 CSS Stylesheets (`views/css/`)

This module does not include any custom CSS files. The styling of the new MPN column and filter field will inherit directly from your PrestaShop back office theme.

### 4.6 Smarty Template Structure (`views/templates/`)

The module’s primary mechanism is to override core PrestaShop Back Office Twig templates to inject the MPN column.

- **`mpnmypresta/views/PrestaShop/Admin/Product/CatalogPage/Lists/list.html.twig`**:
  - **Purpose**: This template is a direct override of the core PrestaShop product list template (`admin-dev/themes/new-theme/template/catalog/products/list.html.twig` or similar path depending on PS version).
  - **Functionality**: It modifies the structure of the product list to include the MPN column header and the corresponding filter input field. It ensures that the MPN field is recognized as a sortable and filterable column within the DataTables configuration.
- **`mpnmypresta/views/PrestaShop/Admin/Product/CatalogPage/Lists/products_table.html.twig`**:
  - **Purpose**: This template is a direct override of the core PrestaShop product table template (`admin-dev/themes/new-theme/template/catalog/products/products_table.html.twig` or similar path).
  - **Functionality**: It modifies the table rows to display the actual MPN value for each product in the newly added column. It accesses the `product.mpn` property from the product data passed to the template.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: This module does not create any new database tables. It relies on the existing `mpn` column within the `ps_product` table (or `ps_product_shop` for shop-specific MPNs, though typically it’s on `ps_product`).
- **Registered Hooks Table**: This module does not explicitly register any new hooks. Its functionality is achieved through template overrides. While it doesn’t use `displayHeader`, `displayRightColumn`, `actionValidateOrder` etc., in its `install()` method, it likely registers itself for template overrides, which is an implicit form of hooking into the rendering process.

## 5. Official Support & Updates

For official updates, technical support, and any inquiries regarding the “MPN filter on products list in back office” module, please refer to your MyPresta.eu customer account. Our support team is available to assist you with any issues or questions you may have.

- **MyPresta.eu Order History & Downloads**: <https://mypresta.eu/my-account/orders/>
- **MyPresta.eu Support Contact**: <https://mypresta.eu/contact>
