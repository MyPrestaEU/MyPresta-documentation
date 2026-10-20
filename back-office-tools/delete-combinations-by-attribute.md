---
title: "Delete combinations by attribute - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Delete combinations by attribute PrestaShop module by MyPresta.eu."
sidebar:
  label: "Delete combinations by attribute - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Delete combinations by attribute Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/delete-combinations-by-attribute.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/delete-combinations-by-attribute/)
>
> ---


# Delete combinations by attribute

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special hosting requirements beyond a standard PrestaShop setup.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main and only configuration screen for the “Delete combinations by attribute” module. You will find all the tools here to select and delete combinations.

#### **Top Section: Module Updates & Information**

This section typically displays information about module updates and versions from MyPresta.eu.

- **What this setting does:** Provides information about available updates for the module, ensuring you are running the latest version for bug fixes and new features.
- **Effect of changing this setting:** These are informational fields and do not have direct settings you can change. They simply display data.
- **Recommended value:** Keep your module updated to the latest version.
- **Merchant scenario / example:** You see a notification that a new version `1.3.1` is available. You would then download it from MyPresta.eu and update the module.

#### **Main Configuration Options**

1. **Attribute value**

   - **What this setting does:** This is the primary filter. It allows you to select a specific attribute value (e.g., “Red”, “Small”, “Cotton”) that you want to target for deletion. The module will look for all product combinations that include this selected attribute value.
   - **Effect of changing this setting:**
     - *When a value is selected:* The module will identify all combinations across your store that use this specific attribute value.
     - *When no value is selected:* You cannot proceed with the deletion process as the module doesn’t know which combinations to target.
   - **Recommended value:** Select the exact attribute value you wish to remove combinations for.
   - **Merchant scenario / example:** You have discontinued all “Orange” colored products. You would select “Orange” from this dropdown to target all combinations with “Orange” as one of their attributes.
2. **Quantity**

   - **What this setting does:** This allows you to filter combinations based on their current stock quantity. You can choose to delete combinations only if their quantity is below, equal to, or above a specified number.
   - **Effect of changing this setting:**
     - *When “What to do” is set to “less than” and “Quantity” is 5:* Only combinations with a stock quantity of 4 or less will be considered for deletion.
     - *When “What to do” is set to “equal to” and “Quantity” is 0:* Only combinations with exactly 0 stock will be considered.
   - **Recommended value:** Often used with “equal to” and “0” to clean up out-of-stock combinations.
   - **Merchant scenario / example:** You want to remove all combinations of “Orange” products that are currently out of stock. You would select “Orange” in “Attribute value”, then set “What to do” to “equal to” and “Quantity” to “0”.
3. **What to do (with Quantity)**

   - **What this setting does:** This dropdown works in conjunction with the “Quantity” field to define the condition for stock filtering. Options typically include “less than”, “equal to”, “greater than”.
   - **Effect of changing this setting:** It modifies the comparison logic for the “Quantity” filter.
   - **Recommended value:** “equal to” is common for targeting out-of-stock items.
   - **Merchant scenario / example:** To remove combinations that have very low stock, you might choose “less than” and set “Quantity” to “3”.
4. **List of reference codes**

   - **What this setting does:** This field allows you to specify a list of product reference codes (SKUs) to include or exclude from the deletion process. This is useful if you only want to affect a subset of products.
   - **Effect of changing this setting:**
     - *When “Code field” is “Reference” and “What to do” is “include”:* Only combinations belonging to products with these specific reference codes will be affected.
     - *When “Code field” is “Reference” and “What to do” is “exclude”:* Combinations belonging to products with these specific reference codes will be skipped.
   - **Recommended value:** Use this to narrow down the scope of deletion to specific products. Enter one code per line.
   - **Merchant scenario / example:** You only want to remove “Orange” combinations from products with reference codes `PROD-A`, `PROD-B`, and `PROD-C`. You would enter these codes, select “Reference” for “Code field”, and “include” for “What to do”.
5. **Code field**

   - **What this setting does:** Defines which product identifier field the “List of codes” refers to. Options are typically “Reference” (SKU) or “EAN13” (Barcode).
   - **Effect of changing this setting:** Changes how the module interprets the codes entered in “List of codes”.
   - **Recommended value:** “Reference” for internal SKUs, “EAN13” for barcodes.
   - **Merchant scenario / example:** If your list contains EAN13 barcodes, select “EAN13” here.
6. **List of codes (What to do)**

   - **What this setting does:** Determines whether the “List of reference codes” (or EAN codes) should be *included* in the deletion process (only delete from these products) or *excluded* (delete from all products EXCEPT these).
   - **Effect of changing this setting:** Controls the scope of products affected by the deletion.
   - **Recommended value:** “include” for targeted deletions, “exclude” for broad deletions with exceptions.
   - **Merchant scenario / example:** You want to delete “Orange” combinations from all products *except* your best-selling `BESTSELLER-01`. You would enter `BESTSELLER-01` in the “List of codes” and select “exclude” here.
7. **Product**

   - **What this setting does:** This allows you to select a specific product by its name. If selected, the deletion will *only* apply to combinations of this single product, overriding any other product-level filters.
   - **Effect of changing this setting:**
     - *When a product is selected:* The module will only process combinations belonging to this specific product.
     - *When left empty:* The module will apply the deletion criteria across all products in your store (subject to other filters like “List of reference codes”).
   - **Recommended value:** Use this for highly targeted deletions on a single product.
   - **Merchant scenario / example:** You only want to remove “Orange” combinations from your “Summer Dress” product. You would select “Summer Dress” here.

#### **Action Button**

- **“Delete selected combinations” button**
  - **What this button does:** This is the action button that, when clicked, executes the deletion process based on all the criteria you have set above.
  - **Effect of clicking this button:** **This action is irreversible!** All product combinations matching your selected “Attribute value”, “Quantity” filters, and “Product” or “Reference/EAN” filters will be permanently deleted from your database. This includes their associated stock, images, and specific prices.
  - **Recommended value:** **ALWAYS perform a full database backup before clicking this button.** Double-check all your settings carefully.
  - **Merchant scenario / example:** After carefully selecting “Color: Orange”, setting “Quantity: equal to 0”, and confirming your backup, you click this button to remove all out-of-stock orange combinations.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | **Attribute value** | *Select specific value* | Primary filter: Deletes combinations containing this attribute value. |
| Module Configuration | **Quantity** | *0 or desired number* | Filters combinations based on their stock quantity. |
| Module Configuration | **What to do (with Quantity)** | *equal to* | Defines the comparison logic for the “Quantity” filter (less than, equal to, greater than). |
| Module Configuration | **List of reference codes** | *Empty or specific codes* | List of product reference (SKU) or EAN codes to include/exclude. One per line. |
| Module Configuration | **Code field** | *Reference* | Specifies if “List of codes” refers to “Reference” or “EAN13”. |
| Module Configuration | **List of codes (What to do)** | *include* | Determines if the listed codes are included in or excluded from the deletion. |
| Module Configuration | **Product** | *Empty or specific product name* | Targets deletion to a single product, overriding other product filters. |
| Module Configuration | **Delete selected combinations** | **Click with caution!** | Executes the irreversible deletion of combinations based on all criteria. **Backup first!** |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I clicked “Delete” but nothing happened, or not all combinations were deleted.**
A:

- **Check your filters:** Re-verify all your settings: “Attribute value”, “Quantity” conditions, “List of codes” (include/exclude), and “Product” selection. Even a small mismatch can prevent combinations from being targeted.
- **Clear Cache:** Sometimes PrestaShop’s cache can cause display issues. Go to **Advanced Parameters > Performance** and click “Clear cache”.
- **Module Conflicts:** Another module might be interfering. Try disabling other modules one by one (especially those related to product management or combinations) to see if the issue resolves.

**Q: I accidentally deleted combinations I didn’t mean to. Can I get them back?**
A: **No, not directly through the module.** This is why a backup is critical. If you have a recent database backup, you can restore your store to the state it was in before the deletion. If you don’t have a backup, you will have to manually recreate the combinations.

**Q: The attribute value I want to delete isn’t showing up in the dropdown.**
A:

- **Check if it exists:** Ensure the attribute value actually exists in your PrestaShop catalog and is assigned to at least one product. Go to **Catalog > Attributes & Features** to verify.
- **Language:** Make sure you are viewing the Back Office in the correct language if the attribute value name is language-dependent.

**Q: Can I delete combinations based on features instead of attributes?**
A: No, this module is specifically designed to work with **attributes and attribute values**. Features are a different concept in PrestaShop and are not supported by this module for deletion.

**Q: Will deleting combinations also delete the associated images or specific prices?**
A: Yes, when a combination is deleted, all data directly linked to that specific combination (like its unique image, specific price rules for that combination, and its stock quantity) will also be removed. The main product image and general product specific prices will remain.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The `delcombs` module is a straightforward PrestaShop module primarily focused on Back Office functionality. It adheres to the PrestaShop module structure, utilizing the `Module` class for installation, uninstallation, and configuration. Its core logic resides within the `getContent()` method of the main module file, where it handles form submission, data validation, and the execution of database operations to delete product combinations. It does not introduce custom front-office controllers or complex ObjectModels, relying instead on direct database queries and PrestaShop’s core `Product` and `Combination` classes for data manipulation.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. All functionality is confined to the Back Office.
- **Back-Office Admin Controllers**: None. The module’s configuration and processing logic are handled within the `getContent()` method of the main module class, which is rendered as part of the standard module configuration page.

### 4.3 Core Classes & Models (`classes/`)

The module does not define any custom classes in the `classes/` directory. It directly interacts with PrestaShop’s core `Product` and `Combination` classes and performs direct database queries for efficiency in mass deletion operations.

### 4.4 JavaScript Assets (`views/js/`)

- `delcombs/views/js/delcombs-admin.js`
  - **Scope:** Back-office (module configuration page).
  - **Purpose:** This script likely handles dynamic behavior on the module’s configuration form. This could include:
    - AJAX calls for searching products or attributes (e.g., for the “Product” selection field).
    - Conditional display of form fields based on user selections (e.g., showing/hiding quantity filters).
    - Input validation before form submission.
    - Confirmation dialogs before executing the deletion action.
    - Interactions with the `searchTool` (likely a custom search component for products/attributes).

### 4.5 CSS Stylesheets (`views/css/`)

- `delcombs/views/css/delcombs-admin.css`
  - **Scope:** Back-office (module configuration page).
  - **Purpose:** Provides styling for the module’s configuration form elements, ensuring a consistent and user-friendly interface within the PrestaShop Back Office.
  - **Key CSS class selectors:** Likely targets specific IDs or classes within the module’s `getContent()` output, such as form groups, input fields, and potentially the `searchTool` component. Developers can override these styles in their custom admin themes or by adding higher-specificity CSS.

### 4.6 Smarty Template Structure (`views/templates/`)

- `delcombs/lib/searchTool/views/scripts.tpl`
  - **Scope:** Back-office.
  - **Purpose:** This template likely contains JavaScript code or Smarty variables needed by a generic search tool component used within the module. It might initialize search fields, define AJAX endpoints for search queries, or set up client-side data handling for search results. It’s probably included by the main configuration template.
- `delcombs/views/templates/admin/tabs.tpl`
  - **Scope:** Back-office (module configuration page).
  - **Purpose:** This is the main Smarty template rendered by the `getContent()` method of the `delcombs` module. It structures the entire configuration form, including:
    - The various input fields (dropdowns for attributes, text areas for codes, quantity inputs).
    - The “Delete selected combinations” button.
    - Any informational messages or warnings.
    - It likely includes `scripts.tpl` for the search functionality.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any custom database tables.
  - It operates directly on PrestaShop’s core tables, primarily:
    - `ps_product_attribute` (main combinations table)
    - `ps_product_attribute_combination` (links combinations to attribute values)
    - `ps_product_attribute_shop` (shop-specific combination data)
    - `ps_stock_available` (stock for combinations)
    - `ps_specific_price` (specific prices for combinations)
    - `ps_image` (images linked to combinations)
    - `ps_product` (for filtering by product ID, reference, EAN)
    - `ps_attribute_lang`, `ps_attribute_group_lang` (for displaying attribute names in the dropdowns)
  - Configuration settings are stored in `ps_configuration` with keys like `delcombs_attribute`, `delcombs_product`, `delcombs_qty_wtd`, `delcombs_qty`, `delcombs_ref_codes`, `delcombs_ref_type`, `delcombs_ean_codes`, `delcombs_ean_type`, `delcombs_ean_field`, `delcombs_product_mode`.
- **Registered Hooks Table**:
  The module does not register any front-office or back-office display hooks. Its functionality is entirely self-contained within its configuration page.
  It might use action hooks internally (e.g., `actionProductUpdate` or `actionAttributeCombinationSave`) to clear cache or react to changes, but these are not explicitly listed as registered hooks for external module interaction.
  The module’s core logic is triggered by the form submission within its `getContent()` method, not by a standard PrestaShop hook.

## 5. Official Support & Updates

For official updates, technical support, and to download the latest versions of the “Delete combinations by attribute” module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
