---
title: "GPSR Free - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the GPSR Free PrestaShop module by MyPresta.eu."
sidebar:
  label: "GPSR Free"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy GPSR Free Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/gpsr-free.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/gpsr-free/)
>
> ---


# GPSR Free

## 1. Requirements & Compatibility
-   **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
-   **PHP Compatibility**: PHP 7.1 - 8.5
-   **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required, which are typically available on most PrestaShop-compatible hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > GPSR Free)

This is the main configuration screen for the GPSR Free module, accessible immediately after installation or by clicking "Configure" from the Module Manager.

-   **What this setting does:** This switch controls whether the GPSR information block is displayed on your product pages in the front office.
-   **Effect of changing this setting:**
    -   *When enabled (Yes):* The GPSR information block, containing manufacturer, responsible person, and warning details, will appear on product pages where you have mapped the relevant information.
    -   *When disabled (No):* The GPSR information block will be hidden from all product pages, regardless of any mapping you have configured.
-   **Recommended value:** **Yes**. To comply with GPSR and display the information, this should be enabled.
-   **Merchant scenario / example:** If you are actively setting up your GPSR data and want it visible to customers, enable this. If you are still in the process of configuring data or temporarily want to hide the block (e.g., during a site redesign), you can disable it.

### 2.2 Dedicated Admin Screens & Controller Views

The GPSR Free module adds several new menu items under a main "GPSR Free" section in your PrestaShop Back Office. These screens allow you to manage the various pieces of information required for GPSR compliance.

#### 2.2.1 GPSR Free Dashboard (Back Office > GPSR Free > Dashboard)
This screen serves as the main entry point for the module's dedicated administration. It typically provides an overview or quick links to the other management sections.

-   **Available Actions & Settings:** This view usually presents a dashboard-like interface, potentially showing statistics or quick links to manage Manufacturers, Entities, Warnings, and Product Maps.
-   **Effect of changes:** This screen itself doesn't have direct settings that change front-office behavior, but it's your navigation hub for all GPSR data management.
-   **Recommended workflow for daily store management:** Start here to get an overview, then navigate to the specific sections (Manufacturers, Entities, Warnings, Product Map) to add or modify data.

#### 2.2.2 Manufacturers (Back Office > GPSR Free > Manufacturers)
This screen allows you to define and manage the manufacturers of your products.

-   **Available Actions & Settings:**
    -   **Listing Table:** Displays all manufacturers you've added, with columns for name, address, and actions like "Edit" or "Delete".
    -   **"Add New Manufacturer" Button:** Clicking this opens a form to create a new manufacturer entry.
    -   **Form Fields (for adding/editing a manufacturer):**
        -   **Name:** The official name of the manufacturer.
        -   **Address:** The full postal address of the manufacturer.
        -   **Is EU Manufacturer?**: A switch to indicate if this manufacturer is based within the European Union. This is crucial for determining if an "EU Responsible Person" needs to be assigned.
-   **Effect of changes:** Adding or editing manufacturers here creates or updates the central list of manufacturers that you can then associate with your products. This information will be displayed on product pages if mapped.
-   **Recommended workflow for daily store management:** Before mapping products, ensure all your product manufacturers are listed here with accurate details. If a new product line comes from a new manufacturer, add them here first.

#### 2.2.3 EU Responsible Persons (Back Office > GPSR Free > EU Responsible Persons)
This screen is for managing the "EU Responsible Persons" (also referred to as "Entities" in the module's internal naming) who are designated for products manufactured outside the EU.

-   **Available Actions & Settings:**
    -   **Listing Table:** Shows all defined EU Responsible Persons, with their name, address, and actions.
    -   **"Add New EU Responsible Person" Button:** Opens a form to add a new responsible person.
    -   **Form Fields (for adding/editing an EU Responsible Person):**
        -   **Name:** The name of the EU responsible person or entity (e.g., importer, authorized representative).
        -   **Address:** The full postal address of the EU responsible person within the EU.
-   **Effect of changes:** This creates or updates the list of EU Responsible Persons that can be linked to non-EU manufacturers or directly to products. This information is displayed on product pages when applicable.
-   **Recommended workflow for daily store management:** If you import products from outside the EU, ensure you have the correct EU Responsible Person details entered here.

#### 2.2.4 Warnings (Back Office > GPSR Free > Warnings)
This screen allows you to create and manage custom safety warnings or disclaimers.

-   **Available Actions & Settings:**
    -   **Listing Table:** Displays all created warnings, with their text and actions.
    -   **"Add New Warning" Button:** Opens a form to create a new warning.
    -   **Form Fields (for adding/editing a warning):**
        -   **Warning Text:** The actual text of the safety warning or instruction. This field is usually multi-language, allowing you to provide translations for each language enabled in your store (controlled by `PS_LANG_DEFAULT`).
-   **Effect of changes:** Adding or editing warnings here creates or updates the pool of warnings that you can associate with products. The selected warnings will appear on the product page.
-   **Recommended workflow for daily store management:** Create generic warnings that apply to multiple products (e.g., "Keep out of reach of children," "Read instructions before use"). You can then easily select these for individual products.

#### 2.2.5 Product Map (Back Office > GPSR Free > Product Map)
This is the most critical screen where you link your products to the manufacturers, EU responsible persons, and warnings you've defined.

-   **Available Actions & Settings:**
    -   **Listing Table:** Shows existing product mappings, typically displaying the product name, associated manufacturer, EU responsible person, and warnings.
    -   **"Add New Product Map" Button:** Opens a form to create a new mapping.
    -   **Form Fields (for adding/editing a product map):**
        -   **Product Search:** A field to search for and select the specific product you want to map.
        -   **Manufacturer:** A dropdown list to select one of the manufacturers you defined in the "Manufacturers" section.
        -   **EU Responsible Person:** A dropdown list to select one of the EU Responsible Persons you defined. This field might only be mandatory or appear if the selected manufacturer is *not* an EU manufacturer.
        -   **Warnings:** A multi-select box or checklist to choose one or more warnings from the "Warnings" section to associate with this product.
-   **Effect of changes:** When you save a product map, the selected manufacturer, EU responsible person (if applicable), and warnings will be displayed on the front-office product page for that specific product, provided the "Enable GPSR block" setting is active.
-   **Recommended workflow for daily store management:** After setting up your manufacturers, EU responsible persons, and warnings, go through your product catalog and map each relevant product here. This is where the GPSR information comes together for display.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|---|
| Module Configuration | Enable GPSR block | Yes | Controls the visibility of the GPSR information block on product pages. |
| Manufacturers | Name | N/A | Official name of the product manufacturer. |
| Manufacturers | Address | N/A | Full postal address of the manufacturer. |
| Manufacturers | Is EU Manufacturer? | Yes | Indicates if the manufacturer is based in the EU, affecting the need for an EU Responsible Person. |
| EU Responsible Persons | Name | N/A | Name of the designated EU Responsible Person/Entity. |
| EU Responsible Persons | Address | N/A | Full postal address of the EU Responsible Person within the EU. |
| Warnings | Warning Text | N/A | The actual safety warning or instruction text (multi-language). |
| Product Map | Product | N/A | Selects the product to which GPSR information will be mapped. |
| Product Map | Manufacturer | N/A | Associates a defined manufacturer with the selected product. |
| Product Map | EU Responsible Person | N/A | Associates a defined EU Responsible Person with the selected product (if manufacturer is non-EU). |
| Product Map | Warnings | N/A | Selects one or more defined warnings to display for the product. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I've configured everything, but the GPSR block isn't showing on my product pages.**
A:
1.  **Check "Enable GPSR block":** Go to **Modules > Module Manager > GPSR Free > Configure** and ensure the "Enable GPSR block" setting is set to "Yes".
2.  **Clear Cache:** Go to **Advanced Parameters > Performance** and click "Clear cache" (or "Clear Smarty cache" in older versions). Sometimes, PrestaShop's cache prevents new content from appearing immediately.
3.  **Product Mapping:** Double-check that the specific product you are viewing has been mapped in **GPSR Free > Product Map** with a manufacturer and at least one warning/entity.
4.  **Theme Compatibility:** While the module tries to be compatible with most themes, very heavily customized themes might require minor adjustments. If the block is completely missing after checking the above, contact MyPresta.eu support.

**Q: The warning text or manufacturer details are not showing in the correct language.**
A:
1.  **Check Translations:** When editing a warning or manufacturer, ensure you have provided translations for all active languages in your store. Look for language tabs next to the input fields.
2.  **Default Language:** The module uses PrestaShop's default language (`PS_LANG_DEFAULT`) if a specific translation is missing. Ensure your default language is correctly set in **International > Localization**.

**Q: How do I remove the sample data installed with the module?**
A: You can go to each respective management screen (**GPSR Free > Manufacturers**, **GPSR Free > EU Responsible Persons**, **GPSR Free > Warnings**, **GPSR Free > Product Map**) and use the "Delete" action for each sample entry.

**Q: Can I customize the appearance of the GPSR block?**
A: Yes, the module includes a `front.css` file. For basic styling changes (colors, fonts, spacing), you can often override these styles in your theme's custom CSS file without modifying the module directly. For more advanced layout changes, you might need to adjust the `product-footer.tpl` template. (See Section 7 for developer details).

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview
The GPSR Free module follows PrestaShop's MVC (Model-View-Controller) pattern. It utilizes custom Admin Controllers for managing GPSR-related data (Manufacturers, Entities, Warnings, Product Maps) and leverages PrestaShop's `ObjectModel` for data persistence. Front-office display is handled via a hook template. The module uses a repository pattern (`GpsrFreeRepository`) for database interactions, promoting cleaner code and separation of concerns.

### 4.2 Controllers (`controllers/`)

The module primarily uses Back-Office Admin Controllers for data management. There are no dedicated front-office controllers as the front-office display is handled directly via hooks.

-   **Back-Office Admin Controllers**:
    -   `controllers/admin/AdminGpsrFreeController.php`
        -   **Class Name:** `AdminGpsrFreeController` (extends `ModuleAdminController`)
        -   **Tab Name:** GPSR Free (main dashboard entry)
        -   **Responsibility:** Serves as the main entry point for the module's administration, likely displaying a dashboard or links to other specific management screens. It doesn't manage a specific entity but orchestrates access to other controllers.
    -   `controllers/admin/AdminGpsrFreeEntitiesController.php`
        -   **Class Name:** `AdminGpsrFreeEntitiesController` (extends `ModuleAdminController`)
        -   **Tab Name:** EU Responsible Persons
        -   **Managed Entity:** `GpsrFreeEntity` (maps to `ps_gpsrfree_entity` table)
        -   **Responsibility:** Manages the creation, editing, listing, and deletion of EU Responsible Persons (entities). Provides a standard PrestaShop list and form view for this data.
    -   `controllers/admin/AdminGpsrFreeManufacturersController.php`
        -   **Class Name:** `AdminGpsrFreeManufacturersController` (extends `ModuleAdminController`)
        -   **Tab Name:** Manufacturers
        -   **Managed Entity:** `GpsrFreeManufacturer` (maps to `ps_gpsrfree_manufacturer` table)
        -   **Responsibility:** Manages the creation, editing, listing, and deletion of product manufacturers. Includes logic for `is_eu_manufacturer`.
    -   `controllers/admin/AdminGpsrFreeMapController.php`
        -   **Class Name:** `AdminGpsrFreeMapController` (extends `ModuleAdminController`)
        -   **Tab Name:** Product Map
        -   **Managed Entity:** `GpsrFreeProductMap` (maps to `ps_gpsrfree_product_map` table)
        -   **Responsibility:** Manages the mapping between products, manufacturers, EU responsible persons, and warnings. This controller handles the complex relationships between the different GPSR data types.
    -   `controllers/admin/AdminGpsrFreeWarningsController.php`
        -   **Class Name:** `AdminGpsrFreeWarningsController` (extends `ModuleAdminController`)
        -   **Tab Name:** Warnings
        -   **Managed Entity:** `GpsrFreeWarning` (maps to `ps_gpsrfree_warning` table)
        -   **Responsibility:** Manages the creation, editing, listing, and deletion of safety warnings. Supports multi-language fields.
    -   `controllers/admin/GpsrFreeAdminController.php`
        -   **Class Name:** `GpsrFreeAdminController` (extends `ModuleAdminController`)
        -   **Tab Name:** (Likely a base or abstract controller for other admin controllers, or an older/redundant entry point)
        -   **Responsibility:** Given its generic name, it might serve as a base class for other admin controllers in the module, providing common methods or properties, or it could be a legacy entry point.
    -   `controllers/admin/index.php`
        -   **Class Name:** N/A
        -   **Responsibility:** Standard PrestaShop security file to prevent direct directory listing.

### 4.3 Core Classes & Models (`classes/`)

-   `classes/GpsrFreeAdminUi.php`
    -   **Class Name:** `GpsrFreeAdminUi`
    -   **Responsibility:** Likely a helper class for generating or managing UI elements within the Back Office, such as form fields, list configurations, or common admin interface components. It helps standardize the look and feel of the module's admin screens.
-   `classes/GpsrFreeEntity.php`
    -   **Class Name:** `GpsrFreeEntity` (extends `ObjectModel`)
    -   **Database Table:** `ps_gpsrfree_entity`
    -   **`$definition` fields:** Defines fields like `name`, `address`.
    -   **Key public methods:** Standard `ObjectModel` methods for CRUD operations. Represents an EU Responsible Person.
-   `classes/GpsrFreeManufacturer.php`
    -   **Class Name:** `GpsrFreeManufacturer` (extends `ObjectModel`)
    -   **Database Table:** `ps_gpsrfree_manufacturer`
    -   **`$definition` fields:** Defines fields like `name`, `address`, `is_eu_manufacturer`.
    -   **Key public methods:** Standard `ObjectModel` methods for CRUD operations. Represents a product manufacturer.
-   `classes/GpsrFreeProductMap.php`
    -   **Class Name:** `GpsrFreeProductMap` (extends `ObjectModel`)
    -   **Database Table:** `ps_gpsrfree_product_map`
    -   **`$definition` fields:** Defines fields like `id_product`, `id_manufacturer`, `id_entity`, `id_warning`. This table likely stores the many-to-many relationships or direct mappings.
    -   **Key public methods:** Standard `ObjectModel` methods for CRUD operations. Manages the links between products and GPSR data.
-   `classes/GpsrFreeRepository.php`
    -   **Class Name:** `GpsrFreeRepository`
    -   **Responsibility:** Implements the repository pattern. This class is responsible for all direct database interactions, abstracting them away from controllers and models. It contains methods for fetching, inserting, updating, and deleting GPSR-related data, often using PrestaShop's `Db` class. It would contain methods like `getMappedProductData($id_product)`.
-   `classes/GpsrFreeWarning.php`
    -   **Class Name:** `GpsrFreeWarning` (extends `ObjectModel`)
    -   **Database Table:** `ps_gpsrfree_warning`
    -   **`$definition` fields:** Defines fields like `text` (multi-language).
    -   **Key public methods:** Standard `ObjectModel` methods for CRUD operations. Represents a safety warning.
-   `classes/index.php`
    -   **Class Name:** N/A
    -   **Responsibility:** Standard PrestaShop security file to prevent direct directory listing.

### 4.4 JavaScript Assets (`views/js/`)
The provided inventory indicates no custom JavaScript files are included in the module. This suggests that the module relies primarily on PrestaShop's built-in JavaScript functionalities for its admin forms and potentially minimal front-office interactions, or that any dynamic behavior is handled server-side.

### 4.5 CSS Stylesheets (`views/css/`)

-   `views/css/admin.css`
    -   **Scope:** Back-office admin form styling.
    -   **Main UI components and containers it styles:** Likely provides specific styling for the module's custom admin pages, such as list tables, form elements, or dashboard widgets, to ensure a consistent look within the PrestaShop Back Office.
    -   **Key CSS class selectors developers can override:** Any custom classes used in the module's admin templates (e.g., `.gpsrfree-admin-panel`, `.gpsrfree-table`).
-   `views/css/front.css`
    -   **Scope:** Front-office customer styling.
    -   **Main UI components and containers it styles:** Styles the GPSR information block displayed on product pages. This would include styling for the block container, headings, manufacturer details, EU responsible person details, and warning lists.
    -   **Key CSS class selectors developers can override:** Classes like `.gpsrfree-block`, `.gpsrfree-manufacturer`, `.gpsrfree-entity`, `.gpsrfree-warnings`, etc. Developers can target these classes in their theme's `custom.css` or `theme.css` to match the store's branding.

### 4.6 Smarty Template Structure (`views/templates/`)

-   **Hook templates (`views/templates/hook/`)**:
    -   `views/templates/hook/product-footer.tpl`
        -   **Hook:** `displayFooterProduct` (and potentially `displayProductButtons` or similar, though `displayFooterProduct` is explicitly listed).
        -   **Visual Block Output:** This template is responsible for rendering the entire GPSR information block on the product page. It will contain the logic to display the manufacturer's details, the EU responsible person's details (if applicable), and a list of associated warnings, based on the data retrieved from the `GpsrFreeRepository` for the current product.
-   **Admin templates (`views/templates/admin/`)**:
    -   `views/templates/admin/configure.tpl`
        -   **Hook:** Rendered by `getContent()` method of the main `gpsrfree.php` module file.
        -   **Visual Block Output:** This template renders the main module configuration form in the Back Office, specifically the "Enable GPSR block" switch. It might also contain links or introductory text for navigating to the dedicated admin controllers.

### 4.7 Database Schema & Hooks Map

-   **Database Tables**:
    -   `ps_gpsrfree_entity`: Stores information about EU Responsible Persons (id, name, address).
    -   `ps_gpsrfree_manufacturer`: Stores information about product manufacturers (id, name, address, is_eu_manufacturer).
    -   `ps_gpsrfree_product_map`: Stores the mapping relationships between products, manufacturers, EU responsible persons, and warnings (id_product, id_manufacturer, id_entity, id_warning). This table likely handles many-to-many relationships by storing multiple entries for a single product if it has multiple warnings.
    -   `ps_gpsrfree_warning`: Stores the text of safety warnings (id, text - multi-language).
    -   `ps_configuration`: Module settings like `GPSRFREE_ENABLED` are stored here.

-   **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
|---|---|---|
| `displayHeader` | In the `<head>` section of every front-office page. | Potentially used for loading front-office CSS (`front.css`) or JavaScript (if any were present) globally. |
| `displayFooterProduct` | At the bottom of the product page, typically below the main product content. | Primary hook for rendering the GPSR information block (`product-footer.tpl`) on the product page. |
| `displayBackOfficeHeader` | In the `<head>` section of every Back Office page. | Used for loading Back Office CSS (`admin.css`) or JavaScript for the module's admin screens. |
| `displayAdminProductsExtra` | (Implicit, often used for adding tabs/sections to product edit page) | While not explicitly listed as registered, modules often use this or similar hooks to integrate with the product edit page if mapping was done directly there. Given `AdminGpsrFreeMapController`, it's likely a separate screen. |
| `actionValidateOrder` | After an order has been successfully validated. | (Not explicitly listed as registered, but common for modules interacting with orders. If present, it would be for order-related GPSR data processing, which is not indicated by the module's description.) |

*Note: The module dossier listed `DisplayHeader`, `DisplayFooterProduct`, `displayHeader`, `DisplayBackOfficeHeader`, `displayFooterProduct`, `displayBackOfficeHeader`. These are duplicates due to case sensitivity, but functionally refer to the same hooks.*

## 5. Official Support & Updates
For the latest updates, bug fixes, and official support for the GPSR Free module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module's functionality and compatibility.
