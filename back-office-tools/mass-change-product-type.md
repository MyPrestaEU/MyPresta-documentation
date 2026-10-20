---
title: "Mass change product type - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Mass change product type PrestaShop module by MyPresta.eu."
sidebar:
  label: "Mass change product type - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Mass change product type Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/mass-change-product-type.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/mass-change-product-type/)
>
> ---


# Mass change product type

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient and are usually enabled by default on most hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The “Mass change product type” module provides a single, intuitive configuration screen within your PrestaShop Back Office. This screen guides you through selecting products and then applying the desired product type change.

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

To access the module’s configuration, navigate to **Modules > Module Manager**, search for “Mass change product type”, and click **“Configure”**.

The configuration page is divided into two main sections: **1. Select products** and **2. What to do with selected products**.

#### Section 1: Select products

This section allows you to define which products will be affected by the mass change. You can select products based on various criteria.

##### 1.1 Select products by category

- **What this setting does:** Allows you to select all products belonging to one or more specific categories.
- **Effect of changing this setting:**
  - *When categories are selected:* Only products within the chosen categories will be considered for the type change.
  - *When no categories are selected:* This criterion will not be used to filter products.
- **Recommended value:** Select the categories relevant to your mass change operation.
- **Merchant scenario / example:** You want to convert all products in your “Digital Downloads” category from standard products to virtual products. You would select the “Digital Downloads” category here.

##### 1.2 Select products by brand

- **What this setting does:** Allows you to select all products associated with one or more specific brands (manufacturers).
- **Effect of changing this setting:**
  - *When brands are selected:* Only products from the chosen brands will be considered for the type change.
  - *When no brands are selected:* This criterion will not be used to filter products.
- **Recommended value:** Select the brands relevant to your mass change operation.
- **Merchant scenario / example:** You’ve decided to sell all products from “Brand X” as bundles. You would select “Brand X” here.

##### 1.3 Select products by feature

- **What this setting does:** Allows you to select products that have a specific feature and, optionally, a specific value for that feature.
- **Effect of changing this setting:**
  - *When a feature (and optionally value) is selected:* Only products matching this feature criterion will be considered.
  - *When no feature is selected:* This criterion will not be used to filter products.
- **Recommended value:** Choose the feature and value that precisely identifies the products you want to modify.
- **Merchant scenario / example:** You want to change all products with the feature “Material” set to “Digital” to virtual products. You would select “Material” and then “Digital” here.

##### 1.4 Select products by attribute

- **What this setting does:** Allows you to select products that have a specific attribute and, optionally, a specific value for that attribute. This is useful for products with combinations.
- **Effect of changing this setting:**
  - *When an attribute (and optionally value) is selected:* Only products matching this attribute criterion will be considered.
  - *When no attribute is selected:* This criterion will not be used to filter products.
- **Recommended value:** Choose the attribute and value that precisely identifies the products you want to modify.
- **Merchant scenario / example:** You want to convert all products that have the attribute “Size” set to “Downloadable” to virtual products. You would select “Size” and then “Downloadable” here.

##### 1.5 Select products by search phrase

- **What this setting does:** Allows you to select products whose names contain a specific phrase. This uses a search tool to find products.
- **Effect of changing this setting:**
  - *When a search phrase is entered:* Products whose names match the phrase will be added to the selection.
  - *When no search phrase is entered:* This criterion will not be used to filter products.
- **Recommended value:** Enter a clear and concise phrase to identify your target products.
- **Merchant scenario / example:** You want to change all products with “eBook” in their name to virtual products. You would type “eBook” into the search box.

##### 1.6 Selected Products List

- **What this setting does:** After applying any of the above filters, this area will display a list of products that match your criteria. You can manually remove products from this list if you don’t want them to be affected.
- **Effect of changing this setting:**
  - *Removing a product:* That specific product will be excluded from the mass type change.
  - *Leaving products in the list:* They will be included in the mass type change.
- **Recommended value:** Always review this list carefully to ensure only the intended products are selected.
- **Merchant scenario / example:** You searched for “eBook” but one physical book titled “eBook Reader Manual” appeared. You would remove this specific product from the list.

#### Section 2: What to do with selected products

Once you have selected your target products, this section allows you to choose the new product type you want to apply.

##### 2.1 Change product type to:

- **What this setting does:** This dropdown menu allows you to select the new product type for all the products identified in Section 1.
- **Options:**
  - **Standard product:** A regular physical product.
  - **Pack of products:** A bundle of other products.
  - **Product with combinations:** A product with variations (e.g., size, color).
  - **Virtual product:** A non-physical product (e.g., service, download).
- **Effect of changing this setting:**
  - *Selecting an option:* All selected products will be converted to this new type.
- **Recommended value:** Choose the product type that accurately reflects the new nature of your selected products.
- **Merchant scenario / example:** You’ve selected all “eBook” products. You would choose “Virtual product” here.

##### 2.2 Apply Changes Button

- **What this setting does:** This button executes the mass change operation.
- **Effect of changing this setting:**
  - *Clicking the button:* The module will process all products in the “Selected Products List” and change their product type to the one chosen in “Change product type to:”. A confirmation message will usually appear.
- **Recommended value:** Click this only after you are absolutely certain about your product selection and the desired new type.
- **Merchant scenario / example:** After reviewing your selected eBooks and confirming “Virtual product” as the new type, you click “Apply Changes” to convert them all.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | **Select products by category** | Select relevant categories | Filters products by their assigned categories. |
| Module Configuration | **Select products by brand** | Select relevant brands | Filters products by their manufacturer/brand. |
| Module Configuration | **Select products by feature** | Select feature & value | Filters products by specific features and their values. |
| Module Configuration | **Select products by attribute** | Select attribute & value | Filters products by specific attributes and their values (for combinations). |
| Module Configuration | **Select products by search phrase** | Enter search term | Filters products by keywords in their name. |
| Module Configuration | **Selected Products List** | Review carefully | Displays selected products; allows manual removal before processing. |
| Module Configuration | **Change product type to:** | Choose desired type | Sets the new product type (Standard, Pack, Combinations, Virtual) for all selected products. |
| Module Configuration | **Apply Changes Button** | Click to execute | Initiates the mass product type change for all selected products. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I changed product types, but I don’t see the changes on my store’s front office.**
A: After making changes in the Back Office, always clear your PrestaShop cache. Go to **Advanced Parameters > Performance** and click “Clear cache” in the top right corner. Your browser’s cache might also need clearing (Ctrl+F5 or Cmd+R).

**Q: Some products were not changed, even though they were in my selection.**
A:

1. **Check the “Selected Products List” again:** Did you accidentally remove them from the list before applying changes?
2. **Verify criteria:** Double-check your selection criteria (category, brand, feature, attribute, search phrase). Are the products truly matching all selected filters?
3. **Product status:** Ensure the products are active and not disabled.
4. **Errors:** Check if any error messages appeared during the “Apply Changes” process.

**Q: Can I revert the changes made by this module?**
A: This module performs direct database updates. There is no “undo” button within the module itself. This is why a **database backup before use is crucial**. If you need to revert, you would typically restore your database from a backup taken *before* you used the module. Alternatively, you would need to use the module again to change the product types back to their original state, or manually edit them.

**Q: Will this module affect my product’s SEO or URLs?**
A: Changing a product’s type itself does not directly alter its SEO-friendly URL. However, if changing the type leads to other modifications (e.g., removing combinations, changing product structure), it’s always a good idea to check your product pages and potentially regenerate URLs (SEO & URLs section in PrestaShop) if you notice any issues, though this is rare for just a type change.

**Q: The module is not showing any products when I use the search phrase.**
A:

1. **Check for typos:** Ensure your search phrase is spelled correctly.
2. **Case sensitivity:** Product names might be case-sensitive depending on your database configuration, try different casing.
3. **Language:** Ensure you are searching in the correct language if your store is multi-lingual.
4. **Module conflict:** Temporarily disable other search-related modules to check for conflicts.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a technical overview for developers and webmasters maintaining or extending a PrestaShop store using the “Mass change product type” module.

### 4.1 Architecture Overview

The “Mass change product type” module (`massptype`) is a standard PrestaShop module primarily operating within the Back Office. It leverages PrestaShop’s `Module` class and utilizes AJAX for product filtering and the mass update process. The core logic resides in the main module file, handling configuration, product selection, and the bulk update of product types. It integrates a custom search tool for product selection.

### 4.2 Controllers (`controllers/`)

This module does not use dedicated front-office or back-office controllers in the `controllers/admin` or `controllers/front` directories. All logic is handled within the main module file `massptype.php` and its `getContent()` method, which acts as the primary configuration entry point. AJAX requests are dispatched through the main module’s `ajax_products_list.php` file.

### 4.3 Core Classes & Models (`classes/`)

The module does not define custom `ObjectModel` classes. It directly interacts with PrestaShop’s core `Product` and `Product::updateProductFlags()` methods to modify product types.

### 4.4 JavaScript Assets (`views/js/`)

- `massptype/lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Back-office (used within the module’s configuration page).
  - **Purpose:** Provides the core logic for the product search autocomplete functionality. It likely handles sending AJAX requests to the module’s `ajax_products_list.php` endpoint to fetch product suggestions based on user input.
- `massptype/views/js/jquery.autocomplete.js`
  - **Scope:** Back-office (used within the module’s configuration page).
  - **Purpose:** This appears to be a jQuery plugin for autocomplete functionality, likely a dependency or a custom implementation used by the search tool. It handles the UI aspect of displaying suggestions and user interaction.

### 4.5 CSS Stylesheets (`views/css/`)

- `massptype/lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Back-office (styles elements within the module’s configuration page).
  - **Purpose:** Styles the autocomplete dropdown, input fields, and potentially the selected product list within the module’s search tool interface. Developers can override these styles in their custom Back Office theme or by adding more specific CSS rules.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `massptype/views/templates/hook/form.tpl`
    - **Hook:** Not directly hooked in the traditional sense, but rendered by `getContent()` of the main module file.
    - **Purpose:** This is the main template for the module’s configuration form in the Back Office. It contains the HTML structure for selecting products by various criteria and choosing the new product type.
- **Admin templates (`views/templates/admin/`)**:
  - `massptype/views/templates/admin/target_products.tpl`
    - **Purpose:** This template is likely used to render the list of selected products after the filtering criteria have been applied. It dynamically updates via AJAX to show which products will be affected.
  - `massptype/views/templates/admin/wtd.tpl` (What To Do)
    - **Purpose:** This template likely renders the section where the user selects the new product type (Standard, Pack, Combinations, Virtual) and the “Apply Changes” button.
- **Other templates**:
  - `massptype/lib/searchTool/views/scripts.tpl`
    - **Purpose:** This template likely includes JavaScript code or initializes the JavaScript autocomplete functionality for the product search tool. It might be included within `form.tpl`.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: The module does not create custom database tables. It modifies existing PrestaShop core tables, specifically `ps_product` (and potentially `ps_product_shop`) by updating the `cache_is_pack`, `cache_has_attachments`, `is_virtual`, and `cache_default_attribute` fields, which determine the product type. Configuration settings are stored in `ps_configuration` using standard keys (e.g., `_PS_MASS_PTYPE_...`).
- **Registered Hooks Table**:
  The module does not register any traditional front-office or back-office display hooks. Its functionality is entirely contained within its `getContent()` method and AJAX calls.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionModuleInstall` | During module installation | Sets up initial configuration. |
| `actionModuleUninstall` | During module uninstallation | Cleans up configuration. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Mass change product type” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality.
