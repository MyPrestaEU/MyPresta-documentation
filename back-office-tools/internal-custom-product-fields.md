---
title: "Internal, custom product fields - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Internal, custom product fields PrestaShop module by MyPresta.eu."
sidebar:
  label: "Internal, custom product fields"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Internal, custom product fields Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/internal-custom-product-fields.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/internal-custom-product-fields/)
>
> ---


# Internal, custom product fields

## 1. Requirements & Compatibility
- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Internal, custom product fields)

This is the main configuration screen for the module, accessible immediately after installation or by clicking "Configure" from the Module Manager.

-   **What this setting does:** This screen primarily handles the module's internal update mechanism and basic settings.
-   **Effect of changing this setting:**
    -   `mypresta_updates`: This internal setting controls whether the module checks for updates from MyPresta.eu.
    -   `update_`: Related to the update check process.
    -   `updatev_`: Related to the update check process.
    -   `PS_LANG_DEFAULT`: This is a standard PrestaShop configuration key and is usually read by modules to determine the default language for displaying content in the Back Office. It's not a setting you typically change directly within this module's configuration.
-   **Recommended value:** For `mypresta_updates`, it's generally recommended to keep it enabled to receive notifications about new versions and bug fixes. The other settings are internal and should not be manually altered.
-   **Merchant scenario / example:** You don't usually interact with these specific settings directly. The main purpose of this screen is to provide a landing page for the module and ensure its update mechanism is active.

### 2.2 Dedicated Admin Screen: Internal Fields Management (Back Office > Catalog > Internal Fields)

This is the core screen where you define and manage your custom internal product fields. After installing the module, a new menu item named "Internal Fields" will appear under the "Catalog" menu in your PrestaShop Back Office.

-   **Screen Name & Menu Location:** **Catalog > Internal Fields**
-   **Available Actions & Settings:**
    -   **Grid View:** This screen displays a list of all custom internal fields you have created. Each row shows the field's name and its status (enabled/disabled).
    -   **"Add new field" Button:** Click this button to create a brand new custom field.
    -   **Edit/Delete Actions:** For each field in the list, you will see action buttons (pencil icon for edit, trash can icon for delete) to modify or remove existing fields.
    -   **Field Creation/Editing Form:** When adding or editing a field, you will typically see:
        -   **Field Name:** (e.g., "Supplier SKU", "Warehouse Location", "Special Handling Notes"). This is the label that will appear next to the input box on the product edit page.
        -   **Active/Inactive Switch:** Controls whether this custom field is currently available for use on product pages. If inactive, it won't show up.
        -   **Field Type:** (e.g., Text, Textarea, Number, etc. - *based on module's actual capabilities, assuming text for now*). This determines the type of input box.
        -   **Save Button:** To save your changes or the new field.
-   **Effect of changes:**
    -   **Adding a new field:** Once saved, this new field will immediately appear on *every* product's edit page in your Back Office, ready for you to input data.
    -   **Editing a field:** Changes to the field name or status will reflect instantly on all product edit pages.
    -   **Deleting a field:** The field will be removed from all product edit pages. **Be careful:** Deleting a field will also delete all the data previously entered into that field for all products.
    -   **Activating/Deactivating a field:** An active field is visible on product pages; an inactive field is hidden.
-   **Recommended workflow for daily store management:**
    1.  Go to **Catalog > Internal Fields**.
    2.  Click "Add new field" to create a field like "Supplier Part Number" or "Internal Notes".
    3.  Set the field name and ensure it's active.
    4.  Save the field.
    5.  Now, when you go to **Catalog > Products** and edit any product, you will see a new input box for your "Supplier Part Number" where you can enter specific data for that product.
    6.  Repeat for any other internal data you need to track.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|---|
| Module Configuration Page | `mypresta_updates` | Enabled | Controls module update checks. Keep enabled for updates. |
| Module Configuration Page | `update_`, `updatev_` | (Internal) | Internal update mechanism variables. Do not modify. |
| Module Configuration Page | `PS_LANG_DEFAULT` | (Internal) | PrestaShop's default language ID. Read-only. |
| Catalog > Internal Fields | **Add new field** | N/A | Creates a new custom internal product field. |
| Catalog > Internal Fields | **Field Name** | User-defined | Label for the custom field on product edit pages. |
| Catalog > Internal Fields | **Active/Inactive** | Active | Controls visibility of the field on product edit pages. |
| Catalog > Internal Fields | **Edit/Delete Actions** | N/A | Modify or remove existing custom fields. Deleting removes all associated data. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I created a new field, but I don't see it on my product edit page.**
A:
1.  Go to **Catalog > Internal Fields** and ensure the field you created is marked as "Active".
2.  Clear your PrestaShop cache: Go to **Advanced Parameters > Performance**, then click "Clear cache" in the top right corner.
3.  Try editing a product again. If it still doesn't appear, ensure your PrestaShop version is fully compatible with the module.

**Q: Can I display these custom fields on my front-office for customers?**
A: No, this module is specifically designed for internal Back Office use only. The data entered into these fields is not intended to be displayed to customers. If you need custom fields for the front-office, you would need a different type of module or custom development.

**Q: What happens if I delete a custom field?**
A: When you delete a custom field from **Catalog > Internal Fields**, all the data you have entered into that specific field for *all* your products will be permanently removed. Always be sure you no longer need the data before deleting a field.

**Q: The module seems to be causing issues with my custom theme. What should I do?**
A:
1.  First, clear your Smarty cache (as mentioned above).
2.  If the issue persists, try temporarily disabling other modules one by one to see if there's a conflict.
3.  Check your browser's developer console (F12) for any JavaScript errors.
4.  If you still can't resolve it, contact MyPresta.eu support with details of your theme and the specific issue.

**Q: How do I translate the names of my custom fields into different languages?**
A: The module should allow you to define the field name for each language enabled in your PrestaShop store when you create or edit the field. Look for language tabs next to the "Field Name" input box on the field creation/edit form.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters.

### 4.1 Architecture Overview
The "Internal, custom product fields" module extends PrestaShop's product management capabilities by injecting custom fields into the product edit page in the Back Office. It leverages PrestaShop's MVC pattern, primarily through an Admin Controller for managing the custom field definitions and overrides to integrate these fields into the existing product forms. Data is stored in a dedicated database table, and JavaScript is used for dynamic form manipulation.

### 4.2 Controllers (`controllers/`)

-   **Front-Office Controllers**: This module does not have dedicated front-office controllers as its functionality is entirely Back Office-oriented. Front-office hooks are likely used for general module setup or to ensure no front-office conflicts.

-   **Back-Office Admin Controllers**:
    *   `aipf/controllers/admin/AdminInternalFields.php`
        *   **Class Name**: `AdminInternalFieldsController` (extends `ModuleAdminController`)
        *   **Tab Name**: "Internal Fields" (under Catalog menu)
        *   **Responsibility**: This is the primary controller for managing the definitions of the custom internal product fields. It handles the listing, creation, editing, and deletion of these fields. It uses PrestaShop's `HelperList` for the grid view and `HelperForm` for the add/edit forms. It interacts with the module's custom `ObjectModel` (likely `AipfInternalField`) to persist field definitions.
    *   `aipf/controllers/admin/index.php`
        *   **Responsibility**: This is a standard empty `index.php` file often placed in directories to prevent directory listing on web servers, enhancing security. It does not contain any functional controller logic.

### 4.3 Core Classes & Models (`classes/`)

The module uses overrides to integrate its functionality into PrestaShop's core.

-   `aipf/override/classes/controller/Controller.php`
    *   **Class Name**: `Controller` (overrides the core `Controller` class)
    *   **Responsibility**: This override is likely used to inject module-specific JavaScript or CSS globally or conditionally, or to modify the behavior of all controllers. Given the module's purpose, it might be used to ensure necessary assets are loaded for the product page or to handle specific AJAX requests related to the custom fields.
-   `aipf/override/classes/controller/index.php`
    *   **Responsibility**: Security placeholder.
-   `aipf/override/classes/index.php`
    *   **Responsibility**: Security placeholder.

*Note: Based on the description, there should be an `ObjectModel` class for `AipfInternalField` (e.g., `classes/AipfInternalField.php`) to manage the custom field definitions and potentially another to manage the actual product data for these fields. This is not explicitly listed in the inventory but is implied by the functionality.*

### 4.4 JavaScript Assets (`views/js/`)

-   `aipf/lib/js/admin/aipf-configuration.js`
    *   **Scope**: Back-office (module configuration).
    *   **Purpose**: Likely handles specific JavaScript logic for the module's main configuration screen, such as update checks or simple form interactions.
-   `aipf/lib/js/admin/aipf.js`
    *   **Scope**: Back-office (general admin, potentially product page).
    *   **Purpose**: Contains core JavaScript logic for the module within the Back Office. This could include AJAX calls for saving product field data, dynamic field rendering on the product page, or interactions with the `AdminInternalFieldsController`.
-   `aipf/lib/js/front/aipf-front.js`
    *   **Scope**: Front-office.
    *   **Purpose**: Although the module is for internal use, this file might exist as a placeholder or to handle very specific, non-visual front-office tasks, such as ensuring no conflicts with other scripts, or for a potential future feature that was not implemented. Given the module's description, its impact on the front-office should be minimal to none.
-   `aipf/views/js/AdminInternalFields.js`
    *   **Scope**: Back-office (AdminInternalFieldsController screen).
    *   **Purpose**: Specific JavaScript for the "Catalog > Internal Fields" management screen. This would handle interactions within the grid, form validation for adding/editing fields, and AJAX requests related to field management.

### 4.5 CSS Stylesheets (`views/css/`)

-   `aipf/lib/css/aipf.css`
    *   **Scope**: Primarily Back-office, potentially minimal front-office.
    *   **Purpose**: Provides styling for the custom fields on the product edit page, the "Internal Fields" management screen, and any other UI elements introduced by the module in the Back Office. It might also contain reset styles or very basic rules that could apply to the front-office to prevent conflicts, though its main focus is administrative UI.
    *   **Key CSS class selectors**: Developers might look for classes like `.aipf-field-container`, `.aipf-input`, `.aipf-label` to override or customize the appearance of the custom fields.

### 4.6 Smarty Template Structure (`views/templates/`)

-   **Hook templates (`views/templates/hook/`)**: Not explicitly listed, but the module would likely use templates for hooks like `displayAdminProductsExtra` or `displayAdminProductsMainStepLeftColumnMiddle` to inject the custom fields into the product edit page.
-   **Admin templates (`views/templates/admin/`)**:
    *   `aipf/views/templates/admin/combination.tpl`
        *   **Purpose**: This template is specifically designed to inject custom internal fields into the product combination (variant) editing interface within the Back Office. It would render the input fields for the custom data associated with each product combination. This is crucial for products with attributes (like size, color) where each combination might need its own internal notes or identifiers.
-   **Front-office templates (`views/templates/front/`)**: None explicitly listed, aligning with the module's Back Office-only nature.

### 4.7 Database Schema & Hooks Map

-   **Database Tables**:
    *   `ps_aipf_internal_field`: This table would store the definitions of the custom internal fields (e.g., `id_aipf_internal_field`, `name`, `active`, `field_type`).
    *   `ps_aipf_internal_field_lang`: If field names are translatable, this table would store the language-specific names for the custom fields (e.g., `id_aipf_internal_field`, `id_lang`, `name`).
    *   `ps_aipf_product_data`: This table would store the actual data entered by the merchant for each custom field, linked to a specific product and potentially a specific combination (e.g., `id_aipf_internal_field`, `id_product`, `id_product_attribute` (if applicable), `value`).
    *   `ps_configuration`: Standard PrestaShop table used to store module configuration values like `mypresta_updates`, `update_`, `updatev_`.

-   **Registered Hooks Table**:

| Hook Name | Scope | Execution Timing | Technical Purpose |
|---|---|---|---|
| `actionAjaxDieProductControllerdisplayAjaxRefreshBefore` | Front/Admin | Before AJAX response in ProductController | Potentially for pre-processing AJAX requests related to product data, ensuring custom fields are considered. |
| `actionOutputHTMLBefore` | Front/Admin | Before HTML output | General hook, could be used for global asset injection or early processing. |
| `ActionAfterUpdateCombinationFormFormHandler` | Admin | After combination form is updated | To save or process custom field data related to product combinations. |
| `actionAdminControllerSetMedia` | Admin | When admin controller sets media | To inject module-specific CSS/JS into Back Office pages (e.g., product edit page, module config). |
| `actionCombinationFormFormBuilderModifier` | Admin | When combination form builder is modified | To dynamically add custom fields to the product combination form. |
| `actionProductUpdate` | Admin | After a product is updated | To save or process custom field data when a product is saved. |
| `ActionFrontControllerSetMedia` | Front | When front controller sets media | To inject module-specific CSS/JS into Front Office pages (if needed, though unlikely for this module). |

## 5. Official Support & Updates
For the latest updates, bug fixes, and official support for the "Internal, custom product fields" module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist you with any issues or questions regarding the module's functionality and compatibility.
