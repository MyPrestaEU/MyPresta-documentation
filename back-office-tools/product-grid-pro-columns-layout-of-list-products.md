---
title: "Product Grid Pro - columns & layout of list products - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Product Grid Pro - columns & layout of list products PrestaShop module by MyPresta.eu."
sidebar:
  label: "Product Grid Pro - columns & layout of list products"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Product Grid Pro - columns & layout of list products Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/product-grid-pro-columns-layout-of-list-products.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/product-grid-pro-columns-layout-of-list-products/)
>
> ---


# Product Grid Pro - columns & layout of list products

## 1. Requirements & Compatibility
- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special hosting requirements beyond a standard PrestaShop setup.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

This module primarily works by overriding the default PrestaShop product list controller. Its configuration is mainly managed directly within the "Catalog > Products" section itself, with a simple "reset" option available in the module's main configuration.

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

To access this, navigate to **Modules > Module Manager**, search for "Product Grid Pro", and click "Configure".

This screen offers a single, crucial option:

-   **Reset module configuration**
    -   **What this setting does:** This button allows you to revert all changes made by the module back to its default settings. This means any custom column order, visibility, or added columns you've configured in the "Catalog > Products" list will be reset to the module's initial state.
    -   **Effect of changing this setting:**
        -   *When clicked:* The module will clear its stored preferences for your product grid layout. This is useful if you've made many changes and want to start fresh, or if you encounter an unexpected display issue and want to rule out configuration problems.
    -   **Recommended value:** Only click this if you explicitly want to reset your product grid customization.
    -   **Merchant scenario / example:** You've been experimenting with different column layouts for months, and now your product list feels cluttered or disorganized. Clicking "Reset module configuration" will bring it back to a clean, default state, allowing you to reconfigure it from scratch.

### 2.2 Dedicated Admin Screens & Controller Views

The core functionality of "Product Grid Pro" is experienced directly within the **Catalog > Products** section of your PrestaShop Back Office. This module enhances the standard product list, adding new columns and allowing you to customize its layout.

-   **Screen Name & Menu Location:** **Catalog > Products**
-   **Available Actions & Settings:**
    -   **New Columns:** The module introduces several new, highly useful columns to your product list. These include:
        -   **EAN13:** European Article Number (barcode).
        -   **Supplier reference:** Your internal reference for the product from your supplier.
        -   **Manufacturer:** The brand or manufacturer of the product.
        -   **Combinations:** Indicates if the product has variations (sizes, colors, etc.).
        -   **Units sold:** The total number of units of this product sold.
        -   **Last sold:** The date when the last unit of this product was sold.
        -   **Weight:** The product's weight.
        -   **Wholesale:** The wholesale price of the product.
        -   **Created:** The date the product was added to your catalog.
        -   **Condition:** The product's condition (New, Used, Refurbished).
        -   **On sale:** Indicates if the product is currently on sale.
        -   **Available for order:** Whether customers can currently purchase the product.
        -   **Show price:** Whether the product's price is displayed on the front office.
        -   **Online only:** Indicates if the product is only available online (not in physical stores).
        -   **Visibility:** Where the product is visible (Catalog, Search, Both, None).
        -   **Virtual:** Indicates if the product is a virtual product (e.g., download, service).
        -   **Pack:** Indicates if the product is a pack of products.
        -   **Indexed:** Whether the product is indexed for search.
        -   **Customizable:** Whether the product has customization fields.
        -   **Supplier:** The specific supplier associated with the product.
    -   **Column Visibility:** You can choose which of these new and existing columns are visible in your product list. This helps declutter the view and focus on what's important.
    -   **Column Order (Drag & Drop):** You can easily reorder the columns by dragging and dropping them into your preferred sequence. This allows you to arrange the most critical information to the left for quick access.
    -   **Filtering & Sorting:** Each of the new columns supports filtering and sorting, just like the default PrestaShop columns. This means you can, for example, sort products by "Units sold" to see your bestsellers, or filter by "Manufacturer" to manage products from a specific brand.
-   **Effect of changes:**
    -   **Adding/Removing Columns:** Directly changes the information displayed in your "Catalog > Products" list. Removing a column hides that data; adding one makes it visible.
    -   **Reordering Columns:** Changes the visual layout of the product list, allowing you to prioritize information.
    -   **Filtering/Sorting:** Helps you quickly locate and analyze specific groups of products based on the criteria you set.
-   **Recommended workflow for daily store management:**
    1.  **Identify your key metrics:** What product information do you check most often? (e.g., stock, price, units sold, supplier reference).
    2.  **Enable essential columns:** Go to **Catalog > Products**, find the column customization options (often a gear icon or a "Columns" button), and enable only the columns you truly need.
    3.  **Arrange for efficiency:** Drag and drop your most important columns to the left side of the grid so they are immediately visible without horizontal scrolling.
    4.  **Use filters:** When managing stock, use the "Units sold" filter to identify slow-moving items, or filter by "Last sold" to find products that haven't sold recently.
    5.  **Regularly review:** Periodically review your column setup to ensure it still meets your operational needs.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|---|
| Module Configuration Page | Reset module configuration | N/A (button) | Reverts all custom product grid settings (column visibility, order) to module defaults. Use to start fresh or troubleshoot. |
| Catalog > Products Grid | EAN13 column | Disabled | Displays the EAN13 barcode for each product. Useful for inventory and scanning. |
| Catalog > Products Grid | Supplier reference column | Disabled | Shows the supplier's internal reference for the product. Essential for supplier management. |
| Catalog > Products Grid | Manufacturer column | Disabled | Displays the product's manufacturer/brand. Useful for brand-specific management. |
| Catalog > Products Grid | Combinations column | Disabled | Indicates if a product has combinations. Quick check for complex products. |
| Catalog > Products Grid | Units sold column | Disabled | Shows the total units sold for each product. Great for identifying bestsellers. |
| Catalog > Products Grid | Last sold column | Disabled | Displays the date of the last sale for a product. Helps identify slow-moving stock. |
| Catalog > Products Grid | Weight column | Disabled | Shows the product's weight. Important for shipping calculations. |
| Catalog > Products Grid | Wholesale column | Disabled | Displays the wholesale price. Useful for margin calculations and B2B stores. |
| Catalog > Products Grid | Created column | Disabled | Shows the date the product was added. Helps track catalog growth. |
| Catalog > Products Grid | Condition column | Disabled | Displays the product's condition (New, Used, Refurbished). Relevant for certain product types. |
| Catalog > Products Grid | On sale column | Disabled | Indicates if the product is currently on sale. Quick overview of promotions. |
| Catalog > Products Grid | Available for order column | Disabled | Shows if the product can be ordered. Essential for stock management. |
| Catalog > Products Grid | Show price column | Disabled | Indicates if the price is visible on the front office. |
| Catalog > Products Grid | Online only column | Disabled | Shows if the product is exclusive to online sales. |
| Catalog > Products Grid | Visibility column | Disabled | Displays where the product is visible (catalog, search, both, none). |
| Catalog > Products Grid | Virtual column | Disabled | Indicates if the product is virtual (downloadable, service). |
| Catalog > Products Grid | Pack column | Disabled | Shows if the product is a pack of other products. |
| Catalog > Products Grid | Indexed column | Disabled | Indicates if the product is indexed for search. |
| Catalog > Products Grid | Customizable column | Disabled | Shows if the product has customization options. |
| Catalog > Products Grid | Supplier column | Disabled | Displays the product's main supplier. |
| Catalog > Products Grid | Column Order (Drag & Drop) | N/A (user-defined) | Customize the visual sequence of columns for optimal workflow. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I've enabled new columns, but they don't appear on the product list.**
A1: After enabling columns, ensure you save your changes (if there's a save button in the column customization interface). Sometimes, clearing your browser cache or PrestaShop's Smarty cache can help. Go to **Advanced Parameters > Performance**, and click "Clear cache" in the top right.

**Q2: The drag-and-drop reordering isn't working, or the layout looks strange.**
A2: This could be a JavaScript conflict with another module or your theme.
    1.  Try clearing your browser cache and PrestaShop's Smarty cache (**Advanced Parameters > Performance > Clear cache**).
    2.  If the issue persists, try clicking the "Reset module configuration" button on the module's configuration page (**Modules > Module Manager > Product Grid Pro > Configure**). This will revert the layout to default and might resolve the conflict.
    3.  If still problematic, temporarily disable other modules that also modify the product list or admin interface to identify a conflict.

**Q3: Can I add even more custom fields to the product grid?**
A3: This module provides a predefined set of commonly requested fields. It does not offer a generic way to add *any* custom field you might have created (e.g., with another custom fields module). If you need a very specific custom field, it would require further custom development.

**Q4: Will this module slow down my Back Office?**
A4: The module is designed to be efficient. While adding many columns means more data is loaded, the impact on performance is generally minimal and outweighed by the efficiency gains. If you notice significant slowdowns, consider disabling less critical columns to reduce the data loaded.

**Q5: The module is installed, but I don't see any new options in Catalog > Products.**
A5: Ensure the module is correctly installed and enabled. Sometimes, after installation, you might need to refresh your browser or even log out and back into the Back Office for the changes to take effect. Also, check for any error messages during installation. If you're on PrestaShop 1.6, the interface for column customization might be slightly different than 1.7/8/9.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters working with the "Product Grid Pro" module.

### 4.1 Architecture Overview

The "Product Grid Pro" module primarily functions by overriding the core `AdminProductsController` in PrestaShop. This is a common and powerful technique in PrestaShop module development, allowing modules to extend or modify the behavior of core functionalities without directly altering core files. The module injects additional columns, filters, and sorting capabilities into the product list table by manipulating the `$this->fields_list` array within the overridden controller. It also uses a dedicated JavaScript file to handle the drag-and-drop reordering of columns and potentially other dynamic UI enhancements. Configuration is stored in `ps_configuration`.

### 4.2 Controllers (`controllers/`)

This module does not introduce new front-office controllers. Its primary interaction is with the Back Office `AdminProductsController`.

-   **Front-Office Controllers**: None.
-   **Back-Office Admin Controllers**:
    *   `myproductgridpro/override/controllers/admin/AdminProductsController.php`
        *   **Class name & parent class**: `AdminProductsController` (overrides the core `AdminProductsController`).
        *   **Responsibility**: This is the core of the module's functionality. It extends the default product list functionality.
            *   It modifies the `$this->fields_list` array to add new column definitions (EAN13, Supplier reference, Manufacturer, Units sold, Last sold, Weight, Wholesale, Created, Condition, On sale, Available for order, Show price, Online only, Visibility, Virtual, Pack, Indexed, Customizable, Supplier).
            *   It ensures these new fields are sortable and filterable.
            *   It handles the logic for retrieving the data for these new columns from the database.
            *   It integrates the JavaScript for column reordering and visibility management.
    *   `myproductgridpro/override/controllers/admin/index.php`
        *   **Class name & parent class**: This file is likely a placeholder or a simple redirector within the override structure and does not contain a full controller class definition for a specific entity. Its presence in the `override/controllers/admin/` directory suggests it might be part of the override mechanism itself, potentially ensuring the `AdminProductsController.php` override is correctly loaded or handling general admin context. In most cases, the actual logic resides in `AdminProductsController.php`.

### 4.3 Core Classes & Models (`classes/`)

This module does not define custom `ObjectModel` classes. It directly interacts with existing PrestaShop `Product` and `Configuration` objects.

### 4.4 JavaScript Assets (`views/js/`)

-   `myproductgridpro/views/js/product_grid_admin.js`
    *   **Scope**: Back-office (specifically the `Catalog > Products` page).
    *   **Responsibility**:
        *   Handles the dynamic manipulation of the product list table in the PrestaShop Back Office.
        *   Implements drag-and-drop functionality for reordering columns, allowing administrators to customize the layout.
        *   Manages the visibility of columns (showing/hiding them based on user preferences).
        *   Likely stores and retrieves user preferences for column order and visibility using AJAX calls or local storage/cookies, which are then used by the overridden `AdminProductsController` to render the grid.
        *   May include event listeners for UI elements that control column selection (e.g., a gear icon or dropdown menu to toggle columns).

### 4.5 CSS Stylesheets (`views/css/`)

-   `myproductgridpro/views/css/product_grid_admin.css`
    *   **Scope**: Back-office (specifically the `Catalog > Products` page).
    *   **Responsibility**:
        *   Provides styling for the enhanced product grid, ensuring new columns and UI elements (like drag handles or column toggles) are displayed correctly and integrate seamlessly with the PrestaShop Back Office theme.
        *   May include styles for drag-and-drop indicators, hidden column states, or specific widths for new columns.
        *   Key CSS class selectors developers can override in their theme: Look for classes prefixed with `product-grid-pro` or similar, or specific table header/cell classes that might be targeted for custom styling.

### 4.6 Smarty Template Structure (`views/templates/`)

The module does not appear to use custom `.tpl` files based on the provided inventory. This suggests that the modifications to the product grid are primarily achieved through PHP (in the overridden controller) and JavaScript, which dynamically manipulates the existing HTML structure generated by PrestaShop's core templates for the `AdminProductsController`. The module likely injects its JS and CSS via hooks like `displayBackOfficeHeader`.

### 4.7 Database Schema & Hooks Map

-   **Database Tables**:
    *   The module primarily stores its configuration settings (e.g., preferred column order, visibility) within the `ps_configuration` table. Configuration keys would typically be prefixed with `MYPRODUCTGRIDPRO_` or similar.
    *   It does not create new custom database tables.
-   **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
|---|---|---|
| `displayBackOfficeHeader` | Executed in the `<head>` section of the Back Office. | Used to include the module's `product_grid_admin.js` and `product_grid_admin.css` assets, ensuring they are loaded on the `AdminProductsController` page. |
| `actionAdminProductsControllerSave` (or similar `actionAdminController` hooks) | Executed when an admin controller saves data. | While not explicitly listed, the module might use such hooks to save the custom column preferences (order, visibility) to `ps_configuration` when an admin user modifies them. |
| `actionAdminProductsListingFieldsModifier` (PrestaShop 1.7+) | Executed before the product list fields are rendered. | This hook is crucial for modules that modify the `AdminProductsController`'s `$this->fields_list`. It allows the module to add, remove, or modify column definitions dynamically. |
| `actionAdminProductsListingResultsModifier` (PrestaShop 1.7+) | Executed after the product data is fetched but before rendering. | Allows the module to modify the actual data rows for the new columns (e.g., calculating "Units sold" or "Last sold" if not directly available from the main product query). |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the "Product Grid Pro - columns & layout of list products" module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist you with any technical issues or questions regarding the module's functionality.
