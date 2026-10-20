---
title: "Mass assign / move products to categories - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Mass assign / move products to categories PrestaShop module by MyPresta.eu."
sidebar:
  label: "Mass assign / move products to categories - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Mass assign / move products to categories Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/mass-assign-move-products-to-categories.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/mass-assign-move-products-to-categories/)
>
> ---


# Mass assign / move products to categories

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 9.x, 8.x, 1.7.x, 1.6.x, 1.5.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are required beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The “Mass assign / move products to categories” module provides a wizard-like interface to guide you through the process of bulk product category management.

### 2.1 Module Configuration Page (Back Office > Modules > Module Manager > Configure “Mass assign / move products to categories”)

Upon clicking “Configure,” you will be taken to the module’s main configuration page, which acts as a step-by-step wizard.

#### Step 1: Select Products to Manage

This section allows you to define which products you want to modify.

- **What this setting does:** This is the first crucial step where you identify the group of products that will be affected by the mass action.
- **Effect of changing this setting:** The products you select here will be the only ones processed in the subsequent steps.
- **Recommended value:** Use the search bar to find products by name. You can add multiple products to the list.
- **Merchant scenario / example:**
  - *Scenario 1: Specific products:* You want to move “Product A,” “Product B,” and “Product C” to a new category. You would search for each product and add them to the list.
  - *Scenario 2: Products from an existing category:* You want to move all products currently in your “Old Collection” category to a new “Archived Items” category. You would first select all products from “Old Collection” here.

#### Step 2: Select Categories to Assign/Move Products To

This section lets you choose the target categories for your selected products.

- **What this setting does:** Here, you specify the categories where the products from Step 1 will be assigned or moved.
- **Effect of changing this setting:** The selected products will be linked to these categories.
- **Recommended value:** Use the category tree to select one or more target categories.
- **Merchant scenario / example:**
  - *Scenario 1: Assign to a new category:* You’ve selected 5 products in Step 1. Now you select “New Arrivals” and “Best Sellers” here. The 5 products will be assigned to both “New Arrivals” and “Best Sellers.”
  - *Scenario 2: Move to a single category:* You’ve selected 10 products. You select “Seasonal Sale” here. Depending on your choice in Step 3, these products will either be added to “Seasonal Sale” or moved exclusively to it.

#### Step 3: What to do with selected products?

This is the most critical step, determining the nature of the bulk action.

- **What this setting does:** This radio button selection dictates whether products are *assigned* (added to new categories while keeping existing ones) or *moved* (removed from existing categories and placed only in the new ones).
- **Effect of changing this setting:**
  - **Assign products to selected categories:**
    - *When selected:* The products chosen in Step 1 will be *added* to the categories selected in Step 2. They will retain all their current category associations. This is useful for cross-listing products or adding them to promotional categories without disrupting their primary placement.
    - *Merchant scenario:* You have a product in “Electronics” and “Gadgets.” You want to add it to “Holiday Deals” without removing it from “Electronics” or “Gadgets.” You would select “Assign.”
  - **Move products to selected categories (remove from current categories):**
    - *When selected:* The products chosen in Step 1 will be *removed* from all categories they are currently assigned to, and then *only* assigned to the categories selected in Step 2. This is a complete re-categorization.
    - *Merchant scenario:* You have a product in “Old Collection” and “Discontinued Items.” You want it to *only* appear in “Archived Products.” You would select “Move.”
- **Recommended value:** This depends entirely on your specific goal. Carefully consider if you want to *add* categories or *replace* them.
- **Merchant scenario / example:**
  - *Assign:* You’re running a “Black Friday” sale. You select all sale products and “Assign” them to the “Black Friday Deals” category. They still appear in their original categories (e.g., “T-Shirts,” “Laptops”), but now also under “Black Friday Deals.”
  - *Move:* You’ve decided to restructure your “Women’s Apparel” section. You select all products from “Dresses” and “Skirts” and “Move” them to a new “Women’s Bottoms & Dresses” category. They will no longer appear in the old “Dresses” or “Skirts” categories.

#### “Execute” Button

- **What this setting does:** This button initiates the bulk operation based on your selections in the previous steps.
- **Effect of changing this setting:** Once clicked, the module will process all selected products according to your chosen action (assign or move) and target categories. A confirmation or success message will typically appear.
- **Recommended value:** Click this only when you are absolutely sure of your selections.
- **Merchant scenario / example:** After carefully reviewing your product and category selections and confirming your desired action (assign or move), click “Execute” to apply the changes to your store’s product catalog.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Main Config | **Step 1: Select Products** | N/A (user input) | Defines the specific products to be affected by the bulk action. |
| Main Config | **Step 2: Select Categories** | N/A (user input) | Defines the target categories where products will be assigned or moved. |
| Main Config | **Step 3: What to do?** | N/A (user choice) | **Assign:** Adds products to new categories, keeping existing ones. **Move:** Removes from all current categories, assigns only to new ones. |
| Main Config | **Execute Button** | N/A (user action) | Triggers the bulk category assignment/move operation. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I clicked “Execute,” but nothing happened, or I don’t see the changes.**
A:

1. **Clear Cache:** After any significant change in PrestaShop, especially category or product assignments, you should always clear your store’s cache. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions).
2. **Check Product Status:** Ensure the products you are trying to assign/move are active and visible.
3. **Check Category Status:** Ensure the target categories are active and visible.
4. **Re-run the Module:** Go back to the module, re-select your products and categories, and try again.

**Q: My products disappeared from their original categories after using the module!**
A: This likely means you selected “Move products to selected categories (remove from current categories)” in Step 3. This option is designed to *replace* existing category assignments with the new ones. If this was unintentional, you will need to manually re-assign products to their original categories or use the module again with the “Assign products” option to add them back. Always double-check Step 3 before executing!

**Q: Can I undo a mass assignment/move?**
A: The module does not have an “undo” button. This is why it’s crucial to **always back up your database before performing any mass actions** on your store. If you made a mistake, restoring a backup is the safest way to revert. Otherwise, you’ll need to manually correct the category assignments or use the module again to re-assign products as needed.

**Q: The product search isn’t finding my products.**
A:

1. **Check Spelling:** Ensure you are typing the product name correctly.
2. **Product Status:** Make sure the product is active in your catalog.
3. **Clear Browser Cache:** Sometimes browser cache can interfere with AJAX search functions. Try clearing your browser’s cache or using an incognito window.

**Q: Does this module affect the default category of a product?**
A: The module primarily manages the *associated* categories. While moving a product might implicitly change its default category if the old default is removed and only one new category is assigned, it’s best practice to manually verify and set the default category on the product edit page if you have specific SEO or navigation requirements for the default category.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a technical overview for developers and webmasters looking to understand, debug, or extend the “Mass assign / move products to categories” module.

### 4.1 Architecture Overview

The module `masspc` (Mass Product Categories) is a standard PrestaShop module primarily operating within the Back Office. It leverages AJAX for product search and category selection, providing a wizard-like user experience. The core logic for product and category manipulation is handled within the main module class, which extends `Module`. It does not introduce custom `ObjectModel` classes or dedicated Admin Controllers beyond its main configuration page.

### 4.2 Controllers (`controllers/`)

This module does not utilize dedicated Front-Office or Back-Office Admin Controllers in the `controllers/` directory. All logic is handled directly within the main module file `masspc.php` (or `ajax_products_list.php` as per the dossier, which is an unusual naming convention for the main module file but implies it handles the core logic and AJAX requests).

### 4.3 Core Classes & Models (`classes/`)

This module does not introduce any custom classes or models in a `classes/` directory. All core logic is encapsulated within the main module file. Product and category data manipulation relies on PrestaShop’s native `Product` and `Category` `ObjectModel` classes and their associated methods (e.g., `Product::updateCategories()`).

### 4.4 JavaScript Assets (`views/js/`)

- **`masspc/lib/searchTool/views/js/autocomplete.js`**
  - **Scope:** Back-office (used within the module’s configuration page).
  - **Description:** This script likely provides the core functionality for an AJAX-based autocomplete search feature, specifically for finding products by name. It listens for user input in a search field, sends AJAX requests to the module’s backend (likely `ajax_products_list.php` itself or a method within it), and displays suggestions. It handles the selection of products and adding them to the list for processing.
- **`masspc/views/js/jquery.autocomplete.js`**
  - **Scope:** Back-office (used within the module’s configuration page).
  - **Description:** This appears to be a jQuery plugin or a custom script that implements or enhances the autocomplete functionality. It might be a dependency for `autocomplete.js` or an alternative/older implementation. It would handle the visual rendering of the autocomplete suggestions and the interaction when a user selects an item.

### 4.5 CSS Stylesheets (`views/css/`)

- **`masspc/lib/searchTool/views/css/autocomplete.css`**
  - **Scope:** Back-office (styles the module’s configuration page).
  - **Description:** This stylesheet provides the visual styling for the autocomplete search input, the suggestion dropdown, and potentially the list of selected products within the module’s configuration interface. Developers can override these styles in their custom admin theme or by adding more specific CSS rules.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`masspc/lib/searchTool/views/scripts.tpl`**
  - **Scope:** Back-office (included in the module’s configuration page).
  - **Description:** This template likely includes JavaScript code or links to JS files (`autocomplete.js`, `jquery.autocomplete.js`) and potentially CSS files (`autocomplete.css`) required for the product search and selection interface. It’s typically used to inject assets into the `<head>` or `<body>` of the admin page.
- **`masspc/views/templates/admin/cselection.tpl`**
  - **Scope:** Back-office (admin configuration page).
  - **Description:** This template renders the “Step 2: Select Categories to Assign/Move Products To” section of the module. It displays the category tree structure, allowing the administrator to select target categories. It likely uses a recursive structure to display parent and child categories.
- **`masspc/views/templates/admin/target_products.tpl`**
  - **Scope:** Back-office (admin configuration page).
  - **Description:** This template renders the “Step 1: Select Products to Manage” section. It includes the product search input field (where `autocomplete.js` operates) and displays the list of products that have been selected for the bulk action.
- **`masspc/views/templates/admin/wtd.tpl`**
  - **Scope:** Back-office (admin configuration page).
  - **Description:** This template renders the “Step 3: What to do with selected products?” section. It contains the radio buttons for “Assign products to selected categories” and “Move products to selected categories,” along with their descriptions.
- **`masspc/views/templates/hook/form.tpl`**
  - **Scope:** Back-office (admin configuration page).
  - **Description:** This is likely the main wrapper template for the module’s configuration form, which includes the other `admin/` templates (`target_products.tpl`, `cselection.tpl`, `wtd.tpl`) to build the complete wizard interface. It would contain the overall form structure and the “Execute” button.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  - This module does not create any custom database tables. It interacts directly with PrestaShop’s core tables:
    - `ps_product_category`: For managing product-to-category associations.
    - `ps_product_shop`: For product-specific shop data, including default category.
    - `ps_category`: For retrieving category names and structure.
    - `ps_product`: For retrieving product names and details for the search.
- **Registered Hooks Table**:
  - The module’s primary functionality is accessed via its configuration page, not through front-office hooks.
  - It likely uses the `displayBackOfficeHeader` hook to inject its CSS and JavaScript assets into the Back Office header.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayBackOfficeHeader` | Renders in the `<head>` of Back Office pages. | Injects module-specific CSS and JavaScript files for the configuration page. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Mass assign / move products to categories” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
