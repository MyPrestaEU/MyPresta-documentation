---
title: "Manufacturer (brand) on products list in back office - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Manufacturer (brand) on products list in back office PrestaShop module by MyPresta.eu."
sidebar:
  label: "Manufacturer (brand) on products list in back office - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Manufacturer (brand) on products list in back office Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/manufacturer-brand-on-products-list-in-back-office.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/manufacturer-brand-on-products-list-in-back-office/)
>
> ---


# Manufacturer (brand) on products list in back office

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.0.0 - 1.7.7.x, 1.7.8.x, 8.x (standard list), 8.x (experimental product list), 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” will take you to the module’s main settings page. This page primarily handles update notifications and general module maintenance.

- **What this setting does:** This section typically manages how the module checks for updates and displays notifications.
- **Effect of changing this setting:**
  - *When enabled:* The module will periodically check MyPresta.eu for new versions and inform you if an update is available. This helps you keep your module current with the latest features and bug fixes.
  - *When disabled:* The module will not check for updates automatically, and you will not receive notifications about new versions. You would need to manually check your MyPresta.eu account for updates.
- **Recommended value:** **Enabled (Yes)**. Keeping this enabled ensures you’re always aware of available updates, which is crucial for security and compatibility with future PrestaShop versions.
- **Merchant scenario / example:** You want to be notified when a new version of the module is released that supports the latest PrestaShop 8.x features. Enabling this setting ensures you get that notification directly in your back office.

### 2.2 Dedicated Admin Screens & Controller Views

This module does not introduce new, separate menu items or dedicated admin screens for managing its core functionality. Instead, its changes are integrated directly into the existing **Catalog > Products** page.

**Screen Name & Menu Location:**

- **Catalog > Products** (The standard PrestaShop product listing page)

**Available Actions & Settings:**
Upon navigating to **Catalog > Products**, you will immediately notice the changes introduced by the module:

- **New Column: Manufacturer/Brand:** A new column will appear in your product list displaying the name of the manufacturer associated with each product.
- **Manufacturer Logo (Optional):** Depending on the module’s internal logic, it might also display the manufacturer’s logo next to the name, if available and configured.
- **Filter by Manufacturer:** Above the product list, you will find a new filter option, typically a dropdown menu, allowing you to select a specific manufacturer. Once selected, the product list will instantly update to show only products from that brand.

**Effect of changes:**

- **Adding the Manufacturer Column:** Provides an immediate visual cue for each product’s brand, eliminating the need to open product pages individually to check this information.
- **Filtering by Manufacturer:** Dramatically speeds up tasks where you need to work with products from a specific brand. For example, if a manufacturer announces a price increase, you can quickly filter all their products and update prices. Or if you need to check stock levels for a particular brand’s items.

**Recommended workflow for daily store management:**

1. **Quick Brand Identification:** When browsing your product list, use the new “Manufacturer” column to quickly identify brands.
2. **Targeted Management:** If you need to perform an action on all products from a specific brand (e.g., update descriptions, adjust prices, check inventory), use the new “Filter by Manufacturer” dropdown at the top of the product list. Select the desired brand, and your list will be instantly refined.
3. **Bulk Actions:** Combine the manufacturer filter with PrestaShop’s standard bulk actions (e.g., selecting multiple products and applying a change) for highly efficient brand-specific management.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Update notifications | Enabled | Notifies you of new module versions for security and features. |
| Catalog > Products List | Manufacturer Column | N/A (Always On) | Displays product brand directly in the product list for quick identification. |
| Catalog > Products List | Filter by Manufacturer | N/A (Always On) | Allows filtering the product list by a specific brand, streamlining brand-specific management tasks. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve installed the module, but I don’t see the manufacturer column or filter on my product list.**
A:

1. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes PrestaShop needs a cache refresh to display new elements.
2. **Module Enabled:** Double-check that the module is indeed enabled in **Modules > Module Manager**.
3. **PrestaShop Version Compatibility:** Ensure you downloaded the correct module version for your specific PrestaShop installation. If you’re on PrestaShop 8.x, make sure you didn’t accidentally install a 1.7.x version, for example.
4. **Theme Overrides:** While the module is designed without overrides, a heavily customized theme or another module might conflict. If the issue persists, try disabling other modules one by one to identify a conflict.

**Q: The manufacturer name appears, but the logo doesn’t.**
A: The module primarily focuses on displaying the manufacturer name. If it supports logos, ensure that:

1. **Manufacturer Logo Uploaded:** You have actually uploaded a logo for that manufacturer in **Catalog > Manufacturers** in your PrestaShop back office.
2. **Module Setting:** There might be an internal setting (though not exposed in the basic configuration for this module) that controls logo display. If not, it means the module is designed to show only the name.

**Q: Can I change the position of the manufacturer column in the product list?**
A: This module integrates directly into PrestaShop’s product grid system. The exact position of the column is determined by PrestaShop’s core product list configuration. While this module adds the column, it typically doesn’t offer options to drag and drop column positions. You might need a more advanced grid customization module or custom development to reorder columns.

**Q: Does this module slow down my back office?**
A: No, the module is designed to be lightweight and efficient. It leverages PrestaShop’s native hook system to add the manufacturer data without heavy processing. You should not experience any noticeable slowdowns.

**Q: Will this module work with the new experimental product page in PrestaShop 8.x?**
A: Yes, the module description explicitly states compatibility with “8.x-experimental product list,” meaning it’s designed to work with both the standard and the newer, experimental product listing interfaces in PrestaShop 8.x.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The `Manufacturer (brand) on products list in back office` module (internal name `dpmypresta`) is designed to enhance the PrestaShop Back Office product listing page by adding manufacturer information. It adheres to a non-override approach, relying heavily on PrestaShop’s hook system, particularly the `actionProductGrid*` hooks introduced in PrestaShop 1.7.x for modifying the product catalog grid. This makes it robust against PrestaShop core updates. The module primarily injects new columns and filtering capabilities into the existing product grid data and rendering process.

### 4.2 Controllers (`controllers/`)

This module does not use front-office controllers. It includes two admin controller files, but `AdminDpMyPrestaController.php` appears to be a placeholder or a remnant, and `index.php` is a standard empty file to prevent directory listing. The module’s core logic for configuration is handled within `dpmypresta.php`’s `getContent()` method, and the product grid modifications are handled via hooks.

- **Front-Office Controllers**: None. All functionality is back-office specific.
- **Back-Office Admin Controllers**:
  - `controllers/admin/AdminDpMyPrestaController.php`
    - Class name: `AdminDpMyPrestaController` (extends `ModuleAdminController`)
    - Responsibility: This controller is present but appears to be a placeholder. Its `__construct` method sets up basic module context. It does not define any specific actions or render any unique views beyond what might be inherited from `ModuleAdminController`. It’s not directly linked to the core functionality of adding manufacturer data to the product list, which is hook-driven.
  - `controllers/admin/index.php`
    - Standard empty `index.php` file for security to prevent directory listing.

### 4.3 Core Classes & Models (`classes/`)

The module does not define any custom classes or `ObjectModel`s in the `classes/` directory. Its operations are directly integrated into PrestaShop’s existing data structures and grid mechanisms via hooks.

### 4.4 JavaScript Assets (`views/js/`)

The module does not include any custom JavaScript files. All interactions and display logic for the manufacturer column and filter are handled by PrestaShop’s native grid components and the module’s PHP logic.

### 4.5 CSS Stylesheets (`views/css/`)

The module does not include any custom CSS files. The styling for the added manufacturer column and filter is inherited from the PrestaShop back office theme.

### 4.6 Smarty Template Structure (`views/templates/`)

The module leverages the new Twig templating system used in PrestaShop 1.7+ for back-office grids.

- **Admin templates (`views/templates/admin/`)**:
  - `views/PrestaShop/Admin/Product/CatalogPage/Lists/list.html.twig`
    - This Twig template likely extends or modifies the core PrestaShop product list template. It’s responsible for rendering the overall product catalog page, including the grid. The module injects the manufacturer column and filter into this structure.
  - `views/PrestaShop/Admin/Product/CatalogPage/Lists/products_table.html.twig`
    - This Twig template specifically renders the table of products within the catalog page. The module modifies this template to add the manufacturer data to each product row.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: The module does not create any custom database tables. It relies on existing PrestaShop tables, primarily `ps_product`, `ps_manufacturer`, and `ps_configuration` for its settings.

  - Configuration values (`mypresta_updates`, `update_`, `updatev_`) are stored in the `ps_configuration` table.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionProductGridDataModifier` | After product data is fetched for the grid. | Modifies the raw data array for each product, injecting manufacturer ID and name. |
| `actionAdminProductsListingFieldsModifier` | Before the product grid fields are defined. | Adds the ‘Manufacturer’ column definition to the product grid. |
| `actionProductGridDefinitionModifier` | Modifies the definition of the product grid itself. | Potentially adds the manufacturer filter to the grid’s filter collection. |
| `actionAdminProductsListingResultsModifier` | After the product listing results are prepared. | Further modifies the results, ensuring manufacturer data is correctly formatted for display. |
| `actionProductGridQueryBuilderModifier` | Modifies the Doctrine Query Builder for the product grid. | Joins the `ps_manufacturer` table to the product query and adds conditions for filtering by manufacturer. |
| `displayBackOfficeHeader` | Renders content in the `<head>` section of the Back Office. | Used for loading module-specific assets (though none are present in this module) or for update checks. |
| `displayAdminProductsExtra` | Renders extra content on the product page (not directly used for list modification). | Not directly related to the core functionality of this module, but a common hook for admin product page extensions. |

## 5. Official Support & Updates

For official updates, technical support, and further assistance with the “Manufacturer (brand) on products list in back office” module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is ready to help you with any questions or issues you may encounter.
