---
title: "Search and replace text in product fields - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Search and replace text in product fields PrestaShop module by MyPresta.eu."
sidebar:
  label: "Search and replace text in product fields"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Search and replace text in product fields Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/search-and-replace-text-in-product-fields.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/search-and-replace-text-in-product-fields/)
>
> ---


# Search and replace text in product fields

## 1. Requirements & Compatibility
-   **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
-   **PHP Compatibility**: PHP 7.1 - 8.5
-   **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are required beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The "Search and replace text in product fields" module does not have a traditional configuration page with settings like switches or input fields. Instead, it integrates directly into the PrestaShop product list, providing a new action to perform search and replace operations.

### 2.1 Accessing the Search and Replace Tool

The module's functionality is accessed directly from your PrestaShop product list:

1.  **Navigate to the Product List:**
    -   In your PrestaShop Back Office, go to **Catalog > Products**.
2.  **Select Products:**
    -   You can either select one or more specific products by checking the boxes next to them, or you can choose to apply the search and replace to *all* products currently displayed in the list (e.g., if you've filtered the list).
3.  **Access the Bulk Actions Menu:**
    -   After selecting products, a "Bulk actions" dropdown menu will appear (usually at the top or bottom of the product list).
4.  **Select "Search and replace text in product fields":**
    -   Click on the "Bulk actions" dropdown and select the option labeled **"Search and replace text in product fields"**.

### 2.2 The Search and Replace Interface

Once you select the "Search and replace text in product fields" action, a modal window or dedicated interface will appear. This is where you define your search and replace operation.

**Available Fields for Search and Replace:**
The module allows you to target various text fields associated with your products. These typically include:
-   **Product Name:** The main title of your product.
-   **Short Description:** The brief summary often displayed near the product image.
-   **Description:** The full, detailed product description.
-   **Meta Title:** The title displayed in browser tabs and search engine results.
-   **Meta Description:** The short summary displayed under the title in search engine results.
-   **Friendly URL:** The SEO-friendly part of the product's web address.
-   **Tags:** Keywords associated with the product.
-   **Features:** Values of custom product features (e.g., "Color: Red" - you could replace "Red" with "Crimson").
-   **Attribute Values:** Values for product attributes (e.g., "Size: S" - you could replace "S" with "Small").
-   **Customization Fields:** Text fields that customers can fill out for product customization.

**Key Settings within the Interface:**

-   **Search for:**
    -   **What this setting does:** This is the exact text phrase you want to find within the selected product fields.
    -   **Effect of changing this setting:** The module will look for this precise string of characters. It is case-sensitive by default unless a "Case-insensitive" option is provided (check the interface for this).
    -   **Recommended value:** Enter the exact text you wish to find.
    -   **Merchant scenario / example:** If you want to change "old brand name" to "new brand name", you would enter "old brand name" here.

-   **Replace with:**
    -   **What this setting does:** This is the new text phrase that will replace every instance of the "Search for" text found.
    -   **Effect of changing this setting:** All occurrences of the "Search for" text will be updated to this new text. If left empty, the "Search for" text will be deleted.
    -   **Recommended value:** Enter the new text you want to use.
    -   **Merchant scenario / example:** Following the example above, you would enter "new brand name" here.

-   **Select fields to search in:**
    -   **What this setting does:** This is a list of checkboxes or a multi-select dropdown where you choose which specific product text fields (e.g., "Description", "Short Description", "Meta Title") the module should process.
    -   **Effect of changing this setting:** Only the selected fields will be scanned and modified. Unselected fields will remain untouched.
    -   **Recommended value:** Select only the fields relevant to your current task to avoid unintended changes.
    -   **Merchant scenario / example:** If you only want to update the main product description, check only "Description". If you're updating a brand name everywhere, you might check "Product Name", "Short Description", "Description", "Meta Title", and "Meta Description".

-   **Apply to selected products / Apply to all filtered products:**
    -   **What this setting does:** This confirms whether the operation applies only to the products you manually checked in the list, or to all products currently visible in the product list (which might be a filtered subset).
    -   **Effect of changing this setting:** Determines the scope of the operation. Be very careful with "all filtered products" to ensure your filters are correctly applied.
    -   **Recommended value:** Always double-check your product selection before proceeding.
    -   **Merchant scenario / example:** If you filtered the product list to show only products from a specific category, and then choose "Apply to all filtered products", the changes will only affect products in that category.

-   **Case-sensitive / Case-insensitive (if available):**
    -   **What this setting does:** Determines if the search should distinguish between uppercase and lowercase letters.
    -   **Effect of changing this setting:**
        -   *Case-sensitive:* "Apple" will not match "apple".
        -   *Case-insensitive:* "Apple" will match "apple", "APPLE", "Apple", etc.
    -   **Recommended value:** Use case-insensitive for broad replacements (e.g., fixing a common typo that might appear in different cases). Use case-sensitive for precise replacements where casing matters.
    -   **Merchant scenario / example:** If you want to replace "ProductX" with "Product Y", but some descriptions might have "productX", using case-insensitive will catch both.

-   **Preview / Dry Run (if available):**
    -   **What this setting does:** Some advanced search and replace tools offer a "preview" or "dry run" mode that shows you what changes *would* be made without actually saving them.
    -   **Effect of changing this setting:** Allows you to review the impact of your operation before committing, preventing accidental data loss.
    -   **Recommended value:** Always use a preview if available, especially for large-scale operations.
    -   **Merchant scenario / example:** Before replacing "old" with "new" across 1000 products, a preview would show you exactly which products and fields would be affected.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Product List (Bulk Actions) | Search for | User-defined | The exact text string to find. Case-sensitive unless specified. |
| Product List (Bulk Actions) | Replace with | User-defined | The text string to replace the 'Search for' text with. Empty deletes the text. |
| Product List (Bulk Actions) | Select fields to search in | User-defined | Checkboxes to select which product fields (description, name, meta, etc.) to modify. |
| Product List (Bulk Actions) | Apply to selected products / all filtered products | User-defined | Defines the scope of the operation: only checked products or all currently filtered products. |
| Product List (Bulk Actions) | Case-sensitive / Case-insensitive | (Check module interface) | Determines if the search distinguishes between uppercase and lowercase letters. |
| Product List (Bulk Actions) | Preview / Dry Run | (If available, always use) | Shows potential changes before applying them, preventing errors. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I ran the search and replace, but I don't see the changes on my website.**
A: PrestaShop uses caching to speed up your store. After making changes in the back office, you often need to clear the cache for them to appear on the front office.
    -   Go to **Advanced Parameters > Performance**.
    -   Click "Clear cache" in the top right corner.
    -   If you use a third-party caching module or CDN, clear their caches as well.

**Q: The module doesn't appear in the "Bulk actions" menu on the product list.**
A:
    1.  **Check Installation:** Ensure the module is correctly installed and enabled in **Modules > Module Manager**.
    2.  **Permissions:** Verify that your user account has the necessary permissions to manage modules and products.
    3.  **Module Conflicts:** Rarely, another module that heavily modifies the product list or bulk actions might conflict. Try temporarily disabling other recently installed modules to see if the issue resolves.

**Q: I accidentally replaced the wrong text or made a mistake. How can I undo it?**
A: Unfortunately, the module performs a direct database update, and there is no built-in "undo" button. This is why backups are crucial.
    -   **Restore from Backup:** The safest way to revert is to restore your database from a backup taken *before* you ran the operation.
    -   **Run a Reverse Operation:** If you only changed a simple phrase, you might be able to run another search and replace operation to revert it (e.g., search for "new text" and replace with "old text"). This is risky and only works for simple, direct replacements.

**Q: Can I use this module for multi-language stores?**
A: Yes, the module operates on product fields, which are often multi-language aware in PrestaShop. When you select fields like "Description" or "Product Name", the module will typically apply the search and replace to all active languages for those fields. The interface should allow you to specify which languages to target if that option is available.

**Q: The search and replace operation is very slow or times out for a large number of products.**
A:
    1.  **Server Resources:** Large operations on thousands of products can be resource-intensive. Ensure your server has adequate PHP memory limits and execution time. You might need to increase `memory_limit` and `max_execution_time` in your `php.ini` (consult your hosting provider or webmaster).
    2.  **Process in Batches:** If possible, filter your product list and run the operation on smaller batches of products (e.g., by category, brand, or ID range) instead of trying to process your entire catalog at once.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a technical overview for developers and webmasters looking to understand, debug, or extend the "Search and replace text in product fields" module.

### 4.1 Architecture Overview
The `snrp` module is a straightforward PrestaShop module primarily focused on extending the Back Office product list functionality. It leverages PrestaShop's hook system to inject a new bulk action into the `AdminProducts` controller. The core logic resides within the main module file, handling the display of the search/replace form and the execution of the database updates. It does not use custom `ObjectModel` classes or dedicated admin controllers but rather extends existing PrestaShop admin views.

### 4.2 Controllers (`controllers/`)
This module does not introduce any custom Front-Office or Back-Office controllers. Its functionality is integrated into the existing `AdminProducts` controller via hooks.

### 4.3 Core Classes & Models (`classes/`)
This module does not define any custom classes in a `classes/` directory. All core logic is contained within the main module file `snrp/index.php`. The module directly interacts with PrestaShop's `Product` and `ProductLang` `ObjectModel`s, and potentially `FeatureValue`, `AttributeGroup`, and `Tag` data, by performing SQL updates based on the user's input.

### 4.4 JavaScript Assets (`views/js/`)

-   **`snrp/views/js/snrp.js`**
    *   **Scope:** Back-office (specifically, the `AdminProducts` list page).
    *   **Responsibility:** This script is responsible for the client-side behavior of the search and replace tool.
        *   It likely binds an event listener to the "Search and replace text in product fields" option within the "Bulk actions" dropdown.
        *   When selected, it triggers the display of the modal window or form where the user inputs the search term, replacement term, and selects target fields.
        *   It handles the AJAX request to the module's `getContent()` method (or a dedicated AJAX endpoint if one were implemented within `index.php`) to submit the search and replace parameters.
        *   It manages the UI feedback during and after the operation (e.g., loading spinners, success/error messages).
        *   It might include validation logic for the input fields before submission.

### 4.5 CSS Stylesheets (`views/css/`)

-   **`snrp/views/css/snrp.css`**
    *   **Scope:** Back-office (specifically, the `AdminProducts` list page).
    *   **Responsibility:** This stylesheet provides the visual styling for the search and replace interface.
        *   It defines the appearance of the modal window (size, positioning, background overlay).
        *   It styles the input fields, buttons, checkboxes, and any other UI elements within the search and replace form.
        *   It ensures the interface integrates visually with the PrestaShop Back Office theme.
    *   **Key CSS class selectors developers can override:** Developers can inspect the generated HTML of the modal to identify specific class names (e.g., `.snrp-modal`, `.snrp-form-group`, `.snrp-button`) to customize its appearance in their custom admin themes or via `override/css/admin.css`.

### 4.6 Smarty Template Structure (`views/templates/`)
The module description indicates no `.tpl` files in `views/templates/`. This suggests that the module's configuration form and the search/replace modal interface are likely rendered directly within the `getContent()` method of `snrp/index.php` using raw HTML and PHP, or by dynamically generating the form elements via JavaScript.

If a modal is used, it's possible the HTML structure is injected directly into the DOM by `snrp.js` or rendered as part of the `getContent()` response.

### 4.7 Database Schema & Hooks Map

-   **Database Tables**:
    *   This module does not create any custom database tables.
    *   It directly modifies existing PrestaShop tables, primarily:
        *   `ps_product_lang`: For product names, short descriptions, descriptions, meta titles, meta descriptions, and friendly URLs (language-specific fields).
        *   `ps_tag`: For product tags.
        *   Potentially `ps_feature_product` and `ps_product_attribute_lang` if feature values and attribute values are targeted.
    *   Configuration settings (if any were present) would typically be stored in `ps_configuration`.

-   **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| :-------- | :--------------- | :---------------- |
| `displayBackOfficeHeader` | Renders in the `<head>` section of the Back Office. | Used to include `snrp.js` and `snrp.css` on relevant admin pages (e.g., `AdminProducts`). |
| `displayAdminProductsExtra` | Renders additional content on the `AdminProducts` list page. | This hook is likely used to inject the HTML structure for the "Search and replace text in product fields" option into the "Bulk actions" dropdown or to add a button that triggers the modal. |
| `actionProductUpdate` / `actionObjectProductUpdateAfter` | Executed after a product is updated. | While not explicitly stated, the module might hook into these to perform additional actions or logging after a successful search and replace operation, though direct SQL updates are more probable for performance. |
| `actionAdminProductsListingResultsModifier` | Modifies the results of the product listing. | Less likely for this module, but could be used to add a column or modify data displayed before the search/replace action is triggered. |

The core functionality of performing the search and replace logic will be handled within the module's `getContent()` method (or a dedicated AJAX method within `index.php`) when the form is submitted, processing the selected product IDs and fields.

## 5. Official Support & Updates
For the latest updates, bug fixes, and official support for the "Search and replace text in product fields" module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module's functionality and compatibility.
