---
title: "Assign carrier to products in bulk - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Assign carrier to products in bulk PrestaShop module by MyPresta.eu."
sidebar:
  label: "Assign carrier to products in bulk - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Assign carrier to products in bulk Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/assign-carrier-to-products-in-bulk.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/assign-carrier-to-products-in-bulk/)
>
> ---


# Assign carrier to products in bulk

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No unusual server configurations are required.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Assign carrier to products in bulk)

This is the main interface where you will define your bulk carrier assignment tasks. The page is designed to be intuitive, guiding you through the process of selecting carriers and then specifying which products should be affected.

**Main Configuration Options:**

1. **Select Carriers:**

   - **What this setting does:** This section displays a list of all active shipping carriers configured in your PrestaShop store (found under **Shipping > Carriers**). You can select one or more carriers that you wish to assign to your products.
   - **Effect of changing this setting:**
     - *When one or more carriers are selected:* The chosen carriers will be assigned to the products you specify in the next steps. This means these carriers will become available shipping options for those products during checkout.
     - *When no carriers are selected:* The module will not perform any assignment. You must select at least one carrier to proceed.
   - **Recommended value:** Select all carriers that should be available for the target products.
   - **Merchant scenario / example:** If you want to make “UPS Ground” and “FedEx Express” available for a new line of electronics, you would select both from this list.
2. **Select Products to Assign Carriers To:**

   - **What this setting does:** This crucial section allows you to define the scope of products that will receive the selected carrier assignments. You have three powerful options:
     - **By Categories:** Assign carriers to all products within specific categories.
     - **By Manufacturers:** Assign carriers to all products from specific manufacturers.
     - **By Specific Products:** Assign carriers to individual products you select.
   - **Effect of changing this setting:**
     - *When “By Categories” is selected:* A list of your store’s categories will appear. Selecting categories here means all products belonging to these categories will have the chosen carriers assigned.
     - *When “By Manufacturers” is selected:* A list of your store’s manufacturers will appear. Selecting manufacturers here means all products associated with these manufacturers will have the chosen carriers assigned.
     - *When “By Specific Products” is selected:* An input field with an autocomplete feature will appear. You can type product names, and the system will suggest products. You can add multiple specific products to the list.
   - **Recommended value:** Choose the method that best groups your target products. For broad changes, categories or manufacturers are efficient. For precise adjustments, specific products are best.
   - **Merchant scenario / example:**
     - *Categories:* You launch a new “Fragile Items” category. You’d select this category and assign a specialized “Fragile Goods Carrier” to all products within it.
     - *Manufacturers:* A new brand of clothing arrives. You select the manufacturer and assign your standard “Apparel Carrier” to all their products.
     - *Specific Products:* You have three unique, oversized products that require a “Freight Carrier.” You’d search for and add these three products individually.
3. **Action Buttons:**

   - **“Assign Carriers” Button:**
     - **What this button does:** Initiates the bulk assignment process. After clicking, the module will process your selections and update the carrier associations for all specified products.
     - **Effect of clicking this button:** The selected carriers will be linked to the chosen products. A success or error message will typically be displayed.
     - **Recommended action:** Click this only after carefully reviewing your carrier and product selections.
     - **Merchant scenario / example:** After setting up your carriers and product groups, clicking this button executes the changes across your store.
   - **“Clear All Assignments” Button (or similar):**
     - **What this button does:** This option (if present) would typically remove *all* carrier assignments for the selected products, or potentially for all products in the store, depending on the module’s exact implementation.
     - **Effect of clicking this button:** Products would revert to having no specific carriers assigned, or only default carriers, potentially impacting shipping availability.
     - **Recommended action:** Use with extreme caution and only if you fully understand the implications. This is a powerful action that can disrupt your shipping options.
     - **Merchant scenario / example:** You’re completely overhauling your shipping strategy and need to reset all product-carrier links before reassigning them.

### 2.2 Dedicated Admin Screens & Controller Views

#### 2.2.1 AdminMassCarrierCronController (Back Office > Advanced Parameters > Mass Carrier Cron)

This screen provides management for cron jobs related to the module, allowing you to schedule and automate carrier assignment tasks.

- **Screen Name & Menu Location:** You’ll typically find a new menu item under **Advanced Parameters** (or a similar section, depending on PrestaShop version) named something like “Mass Carrier Cron” or “Carrier Assignment Scheduler.”
- **Available Actions & Settings:** This screen will likely display a grid (list) of scheduled tasks. For each task, you might see:
  - **Task ID:** Unique identifier.
  - **Description:** A brief explanation of what the task does (e.g., “Assign UPS to Category X”).
  - **Frequency:** How often the task runs (e.g., daily, weekly, once).
  - **Last Run:** Timestamp of the last execution.
  - **Status:** Whether the task is active, pending, or completed.
  - **Actions:** Buttons to “Add New Task,” “Edit,” “Delete,” or “Run Now.”
- **Effect of changes:**
  - *Adding a new task:* Allows you to define a new bulk carrier assignment operation to run automatically at a specified interval. This is useful for recurring updates (e.g., new product imports).
  - *Editing a task:* Modifies the parameters (carriers, products, frequency) of an existing scheduled assignment.
  - *Deleting a task:* Removes a scheduled assignment, preventing it from running in the future.
  - *Running a task now:* Executes a scheduled task immediately, outside of its regular schedule.
- **Recommended workflow for daily store management:**
  - Use this screen to automate routine carrier assignments, especially if you regularly import new products into specific categories or from certain manufacturers that always use the same carriers.
  - For one-off, immediate assignments, use the main module configuration page (4.1).
  - Regularly check the “Last Run” and “Status” to ensure your automated tasks are executing correctly.

#### 2.2.2 index.php (masscarrier/controllers/admin/index.php)

This file typically serves as a placeholder or a redirect within the module’s admin controllers directory and does not usually represent a distinct, configurable screen for the merchant. In PrestaShop module development, `index.php` files within subdirectories often prevent directory listing or handle basic routing, rather than providing a user interface. Therefore, there are no specific merchant-facing settings or actions associated with this file.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration Page** | Select Carriers | Select all relevant | Choose which carriers will be assigned to products. |
|  | Select Products: By Categories | Select relevant categories | Assign carriers to all products within chosen categories. |
|  | Select Products: By Manufacturers | Select relevant manufacturers | Assign carriers to all products from chosen manufacturers. |
|  | Select Products: By Specific Products | Search & add products | Assign carriers to individually selected products. |
|  | Assign Carriers Button | Click after selection | Executes the bulk carrier assignment. |
|  | Clear All Assignments Button | Use with caution | Removes carrier assignments for selected products (if present). |
| **AdminMassCarrierCronController** | Add/Edit/Delete Task | Based on automation needs | Schedule and manage automated bulk carrier assignments. |
|  | Run Now Action | As needed for immediate execution | Manually trigger a scheduled task. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I assigned carriers, but they’re not showing up for customers at checkout.**
A:

1. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). PrestaShop often caches carrier availability.
2. **Carrier Configuration:** Double-check that the carriers themselves are active, have valid shipping zones, and are configured to handle the product’s weight/price range. Go to **Shipping > Carriers** and edit the carrier to review its settings.
3. **Product Dimensions/Weight:** Ensure the product’s dimensions and weight are correctly entered and fall within the carrier’s defined ranges.
4. **Module Execution:** Re-run the assignment process in the module, ensuring you’ve selected the correct carriers and product groups.

**Q: The module seems to be stuck or takes a very long time to process.**
A:

1. **Server Resources:** If you have a very large catalog (tens of thousands of products) and are assigning to “all products,” the process can be resource-intensive. Ensure your hosting has sufficient PHP memory and execution time limits.
2. **Cron Job:** For extremely large operations, consider using the “AdminMassCarrierCronController” to schedule the task as a background cron job, which is more robust for long-running processes.
3. **Break Down Tasks:** Instead of assigning to *all* products at once, try breaking it down by major categories or manufacturers.

**Q: Can I remove a carrier from products in bulk using this module?**
A: The primary function of this module is to *assign* carriers. While it doesn’t have a direct “remove carrier from selected products” feature, you can effectively achieve this by:

1. **Re-assigning:** If you want to replace Carrier A with Carrier B for a group of products, simply select Carrier B and the product group, then run the assignment. This will add Carrier B. You would then need to manually remove Carrier A from those products if you want it completely gone, or use a separate tool if available.
2. **Manual Removal:** For specific products, you can still go to the product edit page (**Catalog > Products > Edit Product > Shipping tab**) and uncheck the carrier manually.

**Q: My custom theme isn’t displaying the module’s elements correctly (if any were visible).**
A: This module has no front-office visual elements, so theme compatibility issues are unlikely from a display perspective. If you encounter issues with the *back-office* configuration screens:

1. **PrestaShop Version:** Ensure you downloaded the correct module version for your PrestaShop installation.
2. **Browser Cache:** Clear your browser’s cache.
3. **Theme Overrides:** If your back-office theme is heavily customized, it might interfere. Try temporarily switching to the default PrestaShop back-office theme to see if the issue persists.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Assign carrier to products in bulk” module (`masscarrier`) follows a standard PrestaShop MVC (Model-View-Controller) pattern, primarily focusing on administrative tasks. It leverages PrestaShop’s `Module` class for its core functionality and extends `AdminController` for its dedicated back-office management screens. The module directly interacts with PrestaShop’s core product and carrier data, modifying the `ps_product_carrier` table to establish associations. It also includes a front controller for cron job execution, allowing for scheduled bulk operations.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `controllers/front/cronjob.php`
    - **Class name & parent class**: `MassCarrierCronjobModuleFrontController` extends `ModuleFrontController`.
    - **Responsibility**: This controller is designed to be called externally, typically by a server-side cron job. It executes the scheduled carrier assignment tasks defined in the back-office. It does not render any visual output to the browser but performs background processing. It handles the logic for retrieving pending tasks from the `masscarriercron` table and applying the carrier changes to products.
- **Back-Office Admin Controllers**:

  - `controllers/admin/AdminMassCarrierCron.php`
    - **Tab name and managed entity**: This controller manages the `masscarriercron` entity, which represents scheduled bulk carrier assignment tasks. It creates a new tab in the PrestaShop back office (likely under “Advanced Parameters” or a custom “Mass Carrier” menu).
    - **Responsibility**: Provides a standard PrestaShop `AdminController` interface for listing, adding, editing, and deleting scheduled cron tasks. It handles form submission for creating/updating tasks, validating input, and interacting with the `masscarriercron` database table.
  - `controllers/admin/index.php`
    - **Responsibility**: This is a standard empty `index.php` file often placed in PrestaShop module directories to prevent directory listing when accessed directly via a web browser. It does not contain any functional logic or manage any entity.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes in the `classes/` directory. This implies that the core logic for carrier assignment and cron job management is likely handled directly within the main `masscarrier.php` file and the respective controllers, possibly using PrestaShop’s `Product` and `Carrier` `ObjectModel`s directly.

### 4.4 JavaScript Assets (`views/js/`)

- `masscarrier/lib/searchTool/views/js/autocomplete.js`
  - **Scope**: Back-office.
  - **Responsibility**: This script likely provides the autocomplete functionality for selecting specific products on the module’s main configuration page. It listens for user input in a designated product search field, sends AJAX requests to a back-office controller (or the main module `getContent()` method) to fetch product suggestions, and displays them in a dropdown list. It handles selection events to add chosen products to a list for bulk assignment.

### 4.5 CSS Stylesheets (`views/css/`)

- `masscarrier/lib/searchTool/views/css/autocomplete.css`
  - **Scope**: Back-office admin form styling.
  - **Responsibility**: Provides styling for the autocomplete search input and its suggestion list, ensuring it integrates visually with the PrestaShop back-office theme. It defines styles for the input field, the dropdown container, and individual suggestion items. Developers can override these classes in their custom back-office themes if needed.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - No specific hook templates are listed, suggesting the module’s primary configuration is handled via `getContent()` and dedicated admin controllers.
- **Admin templates (`views/templates/admin/`)**:

  - `masscarrier/lib/searchTool/views/scripts.tpl`
    - **Purpose**: This template likely includes the necessary JavaScript for the autocomplete search tool (e.g., `autocomplete.js`) and potentially inline JavaScript configurations or CSS links. It’s probably included in the main module configuration form or an admin controller form.
  - `masscarrier/masscarrier.tpl`
    - **Purpose**: This is the main configuration template for the module, rendered by the `getContent()` method of `masscarrier.php`. It contains the HTML structure for selecting carriers, choosing product groups (categories, manufacturers, specific products), and the “Assign Carriers” button. It likely includes the `scripts.tpl` for the autocomplete functionality.
  - `masscarrier/views/button-subcategories.tpl`
    - **Purpose**: This template likely renders a button or a section related to managing subcategories, possibly for expanding/collapsing category trees in the product selection interface, or for specific actions related to subcategory selection.
- **Front-office templates (`views/templates/front/`)**:

  - No front-office templates are listed, consistent with the module’s back-office administrative nature.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - `ps_masscarriercron`: This custom table stores the details of scheduled bulk carrier assignment tasks. It would typically contain fields such as:
    - `id_masscarriercron`: Primary key.
    - `carriers`: A serialized array or comma-separated string of carrier IDs.
    - `product_selection_type`: (e.g., ‘category’, ‘manufacturer’, ‘product’).
    - `product_selection_ids`: A serialized array or comma-separated string of category/manufacturer/product IDs.
    - `frequency`: (e.g., ‘daily’, ‘weekly’, ‘once’).
    - `last_run`: DATETIME of the last execution.
    - `active`: BOOLEAN indicating if the task is enabled.
  - The module primarily interacts with PrestaShop’s core tables:
    - `ps_product_carrier`: This is the crucial table that stores the many-to-many relationship between products and carriers. The module inserts/updates records in this table.
    - `ps_product`: To retrieve product information.
    - `ps_category_product`: To link products to categories.
    - `ps_product_supplier` / `ps_manufacturer`: To link products to manufacturers.
    - `ps_carrier`: To retrieve carrier information.
- **Registered Hooks Table**:
  The module description mentions “Front-Office Hooks: Header, Columns, Product, or Footer” but based on the code inventory and module purpose, it’s highly unlikely to register any front-office hooks for visual output. These might be generic placeholders or refer to internal hooks used for module initialization or data processing.

  The module would primarily use internal PrestaShop hooks for its functionality:

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `actionModuleInstall` | During module installation | Creates `ps_masscarriercron` table, registers admin tabs. |
  | `actionModuleUninstall` | During module uninstallation | Drops `ps_masscarriercron` table, unregisters admin tabs. |
  | `actionAdminControllerSetMedia` | When an admin controller is loaded | Injects JS/CSS assets for back-office forms (e.g., autocomplete.js, autocomplete.css). |
  | `displayBackOfficeHeader` | Renders in the back-office header | May include global back-office JS/CSS or configuration. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Assign carrier to products in bulk” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). MyPresta.eu provides direct support and ensures you have access to the most compatible and feature-rich versions of the module for your PrestaShop store.
