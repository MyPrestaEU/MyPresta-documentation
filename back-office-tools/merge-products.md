---
title: "Merge Products - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Merge Products PrestaShop module by MyPresta.eu."
sidebar:
  label: "Merge Products - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Merge Products Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/merge-products.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/merge-products/)
>
> ---


# Merge Products

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The Merge Products module offers a dedicated administration screen to manage the merging process, accessible from your PrestaShop back office.

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

When you first click “Configure” after installation, you’ll be taken to a dashboard-like page. This page primarily serves as an entry point to the main merging tool.

- **What this screen does:** This initial configuration page provides a brief overview and a direct link to the main “Merge Products” tool. It doesn’t contain specific settings itself but guides you to where the actual merging happens.
- **Effect of changing this setting:** There are no direct settings to change on this initial screen.
- **Recommended value:** N/A
- **Merchant scenario / example:** This is your starting point. From here, you’ll click a button or link to access the core functionality of the module.

### 2.2 Dedicated Admin Screen: Merge Products Tool (Back Office > Catalog > Merge Products)

This is the main interface where you will perform all product merging operations. You can find it by navigating to **Catalog > Merge Products** in your PrestaShop back office menu.

This screen is divided into several sections to guide you through the merging process:

#### Step 1: Select Master Product

- **What this section does:** Here, you define the “master” product. This is the product that all other selected “source” products will be merged into, becoming its combinations.
- **Input field: “Search for a product”**
  - **What this setting does:** Allows you to search for an existing product in your catalog to designate as the master product. You can search by product name, ID, EAN, or reference.
  - **Effect of changing this setting:** As you type, an autocomplete list will appear. Selecting a product populates the “Master Product” area with its details. This product will be the base for the new combinations.
  - **Recommended value:** Choose the product that best represents the consolidated listing. For example, if merging “Red T-shirt S”, “Red T-shirt M”, “Red T-shirt L” into one, you might pick “Red T-shirt S” as the master, and the others become its combinations.
  - **Merchant scenario / example:** You have “iPhone 13 (New)” and “iPhone 13 (Refurbished)” as separate products. You would search for and select “iPhone 13 (New)” as your master product.

#### Step 2: Select Source Products

- **What this section does:** Here, you select the products that will be converted into combinations and added to the master product.
- **Input field: “Search for products to merge”**
  - **What this setting does:** Similar to the master product search, this field allows you to find and select multiple products that will become combinations.
  - **Effect of changing this setting:** Each selected product is added to a list below. These are the products whose data (price, stock, attributes) will be transferred to the master product as new combinations.
  - **Recommended value:** Select all products that are variations of your chosen master product and should be consolidated.
  - **Merchant scenario / example:** Following the iPhone example, you would search for and select “iPhone 13 (Refurbished)” here. If you also had “iPhone 13 (Used - Grade A)”, you would select that too.

#### Step 3: Configure Merge Options

This section contains critical settings that control how the merge operation is performed.

- **Option: Merge Mode**

  - **What this setting does:** Determines how the attributes of the source products are handled when creating combinations.
  - **Effect of changing this setting:**
    - *Add a new attribute group:* The module will create a new attribute group (e.g., “Condition”) and an attribute for each source product (e.g., “New”, “Refurbished”, “Used”). This is ideal when source products differ by a characteristic not already covered by existing attributes.
    - *Use existing attribute group:* If your source products already share a common attribute group (e.g., “Size” or “Color”) and you want to merge them based on that, you can select this. This is less common for merging entirely separate products but useful for consolidating variations within an existing attribute structure.
  - **Recommended value:** **“Add a new attribute group”** is generally recommended for merging distinct products, as it provides a clear way to differentiate the new combinations.
  - **Merchant scenario / example:** You’re merging “Product X - New” and “Product X - Used”. Selecting “Add a new attribute group” will create an attribute group “Condition” with attributes “New” and “Used” for the combinations.
- **Input field: New Attribute Group Name (only visible if “Add a new attribute group” is selected)**

  - **What this setting does:** Specifies the name for the new attribute group that will be created to differentiate the merged combinations.
  - **Effect of changing this setting:** This name will appear on your product page (e.g., “Condition”, “Grade”, “Version”).
  - **Recommended value:** A descriptive name like “Condition”, “Status”, “Type”, or “Grade”.
  - **Merchant scenario / example:** If merging “New” and “Used” products, you might enter “Condition”.
- **Option: Master Product Rule**

  - **What this setting does:** Defines how the master product itself is treated during the merge.
  - **Effect of changing this setting:**
    - *Keep as master product:* The master product remains as the default product, and source products become its combinations. Its existing combinations (if any) are preserved.
    - *Convert to combination:* The master product itself is also converted into a combination under its own listing. This is useful if you want all variations, including the original master, to be selectable via the new attribute group.
  - **Recommended value:** **“Keep as master product”** is often sufficient. Choose “Convert to combination” if you want the master product’s original state to be explicitly selectable as a combination.
  - **Merchant scenario / example:** If “iPhone 13 (New)” is your master, and you merge “iPhone 13 (Refurbished)” into it, “Keep as master product” means “iPhone 13 (New)” is the default. If you choose “Convert to combination”, then “New” would become a selectable option alongside “Refurbished”.
- **Option: Source Product Action**

  - **What this setting does:** Determines what happens to the original source products after they have been merged into the master product as combinations.
  - **Effect of changing this setting:**
    - *Deactivate:* The original source product pages will be disabled, making them inaccessible to customers. This is generally the safest option.
    - *Delete:* The original source product pages will be permanently removed from your catalog. Use with caution, as this action is irreversible.
    - *Do nothing:* The original source product pages remain active. This is generally not recommended as it can lead to duplicate content and confusion.
  - **Recommended value:** **“Deactivate”** is the safest and most common choice. If you’re confident in your merge and redirects, “Delete” can clean up your catalog, but ensure you have backups.
  - **Merchant scenario / example:** After merging “iPhone 13 (Refurbished)” into “iPhone 13 (New)”, you would typically choose “Deactivate” to prevent customers from finding the old “Refurbished” product page.
- **Option: Create 301 Redirects**

  - **What this setting does:** If enabled, the module will create permanent (301) redirects from the old URLs of the source products to the new URL of the master product.
  - **Effect of changing this setting:**
    - *Enabled:* Any customer or search engine trying to access an old source product URL will be automatically sent to the master product page. This is crucial for SEO, preserving link equity, and preventing broken links.
    - *Disabled:* Old source product URLs will lead to a “page not found” error if the source product is deactivated or deleted.
  - **Recommended value:** **YES (Enabled)**. This is highly recommended for SEO and user experience.
  - **Merchant scenario / example:** A customer bookmarked the old “iPhone 13 (Refurbished)” page. With redirects enabled, they will automatically land on the “iPhone 13” master page.
- **Option: Batch Size**

  - **What this setting does:** Controls how many products are processed in a single batch during the merge operation. This is a technical setting to prevent server timeouts for large merges.
  - **Effect of changing this setting:** A lower number reduces server load but makes the process take longer. A higher number speeds it up but might cause issues on less powerful hosting.
  - **Recommended value:** Leave at default unless you experience timeouts. If you do, try reducing it.
  - **Merchant scenario / example:** If you’re merging hundreds of products and the process fails, reducing the batch size might help.
- **Option: Only Active Products**

  - **What this setting does:** If enabled, only active source products will be considered for merging.
  - **Effect of changing this setting:**
    - *Enabled:* Prevents inactive products from being merged, which can simplify the process and avoid creating combinations for products you don’t intend to sell.
    - *Disabled:* All products, active or inactive, can be merged.
  - **Recommended value:** **YES (Enabled)**, unless you specifically need to merge inactive products.
  - **Merchant scenario / example:** You only want to merge products that are currently visible and purchasable on your store.
- **Option: Exclude Packs**

  - **What this setting does:** If enabled, products configured as “packs” (bundles of other products) will be excluded from the source product selection.
  - **Effect of changing this setting:** Prevents accidental merging of product packs, which have complex relationships and might not behave as expected when converted to combinations.
  - **Recommended value:** **YES (Enabled)**. Merging packs can lead to unexpected behavior.
  - **Merchant scenario / example:** You have a “Starter Kit” pack. You don’t want this to be merged as a combination into another product.
- **Option: Exclude Virtual Products**

  - **What this setting does:** If enabled, virtual products (e.g., downloadable files, services) will be excluded from the source product selection.
  - **Effect of changing this setting:** Prevents accidental merging of virtual products, which typically don’t have physical attributes or stock and might not be suitable for combination conversion.
  - **Recommended value:** **YES (Enabled)**. Virtual products are usually not good candidates for merging into physical product combinations.
  - **Merchant scenario / example:** You sell a downloadable e-book. You don’t want this to be merged as a combination into a physical book product.
- **Option: Minimum Group Size**

  - **What this setting does:** Sets a minimum number of source products required to form a new attribute group.
  - **Effect of changing this setting:** This is a safeguard. If you select “Add a new attribute group” but only merge one source product, this setting can prevent the creation of an unnecessary attribute group with only one option.
  - **Recommended value:** Leave at default (usually 2).
  - **Merchant scenario / example:** If you accidentally select only one source product, this can prevent the module from creating an attribute group with just one option, which is redundant.
- **Option: Attribute Group to Use (only visible if “Use existing attribute group” is selected)**

  - **What this setting does:** Allows you to select an existing attribute group from your store to categorize the new combinations.
  - **Effect of changing this setting:** The module will attempt to map the source products to attributes within this chosen group. This requires careful planning to ensure your source products logically fit into the existing attribute structure.
  - **Recommended value:** Only use if you have a very specific scenario where source products are already variations of an existing attribute. Otherwise, “Add a new attribute group” is safer.
  - **Merchant scenario / example:** You have products “Shirt - Blue” and “Shirt - Red” as separate products, and you want to merge them into a “Shirt” master product, using the existing “Color” attribute group.

#### Step 4: Review & Merge

- **Button: “Merge Products”**
  - **What this button does:** Initiates the actual merging process based on your selections and configurations.
  - **Effect of clicking:** The module will process the selected source products, convert them into combinations, assign them to the master product, update stock and prices, and perform redirects/deactivations as configured. A progress bar or success message will be displayed.
  - **Recommended action:** Review all your selections carefully before clicking. Ensure you have a backup of your store.
  - **Merchant scenario / example:** After selecting “iPhone 13 (New)” as master, “iPhone 13 (Refurbished)” as source, setting “Condition” as the new attribute group, and enabling 301 redirects, you click “Merge Products” to execute the consolidation.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Merge Products Tool** | **Master Product Search** | N/A | Selects the primary product to which others will be merged. |
|  | **Source Products Search** | N/A | Selects products to be converted into combinations under the master. |
|  | **Merge Mode** | Add a new attribute group | Determines if a new attribute group is created or an existing one is used for combinations. |
|  | **New Attribute Group Name** | Descriptive name (e.g., “Condition”) | Name for the attribute group created to differentiate merged combinations. |
|  | **Master Product Rule** | Keep as master product | Defines if the master product itself becomes a combination or remains the default. |
|  | **Source Product Action** | Deactivate | What happens to the original source product pages after merging (Deactivate, Delete, Do nothing). |
|  | **Create 301 Redirects** | YES | Creates permanent redirects from old source URLs to the new master URL. Crucial for SEO. |
|  | **Batch Size** | Default (e.g., 10) | Number of products processed per batch. Adjust for server performance. |
|  | **Only Active Products** | YES | Limits source product selection to only active products. |
|  | **Exclude Packs** | YES | Prevents product packs from being selected as source products. |
|  | **Exclude Virtual Products** | YES | Prevents virtual products from being selected as source products. |
|  | **Minimum Group Size** | Default (e.g., 2) | Minimum number of source products to create a new attribute group. |
|  | **Attribute Group to Use** | N/A (only if “Use existing…” mode) | Selects an existing attribute group for combination mapping. |
|  | **Merge Products Button** | Click after review | Executes the merge operation. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: After merging, I don’t see the new combinations on my product page.**
A1: First, clear your PrestaShop cache. Go to **Advanced Parameters > Performance** and click “Clear cache” in the top right. If the issue persists, check the master product in your Back Office to ensure the combinations were created correctly and are active. Also, verify that the attribute group created by the module is enabled and associated with the master product.

**Q2: My old product URLs are showing “Page Not Found” errors.**
A2: This usually means the 301 redirects were not created or are not working.
1. Go back to the “Merge Products” tool (**Catalog > Merge Products**).
2. Check if the “Create 301 Redirects” option was enabled during the merge. If not, you’ll need to manually set up redirects or re-merge (after restoring a backup if you deleted the source products).
3. Ensure your server’s `.htaccess` file is correctly configured to handle PrestaShop’s friendly URLs and redirects. Sometimes, server configurations can interfere.

**Q3: The module seems to get stuck or times out during the merge process.**
A3: This can happen with a large number of products or on servers with limited resources.
1. Try reducing the **“Batch Size”** setting in the “Configure Merge Options” section of the module. A smaller batch size (e.g., 5 or 10) will process fewer products at once, reducing server load.
2. Check your server’s PHP `max_execution_time` and `memory_limit` settings. You might need to temporarily increase these values (contact your hosting provider if unsure).

**Q4: Can I undo a merge operation?**
A4: The module does not have an “undo” button. This is why **backups are absolutely critical**. If you need to revert, you must restore your store from a backup taken *before* the merge. If you only deactivated source products and didn’t delete them, you could manually reactivate them and delete the newly created combinations from the master product, but this is a complex manual process.

**Q5: What if my custom theme doesn’t display the new attribute group correctly?**
A5: The module creates standard PrestaShop attribute groups and combinations. If your theme isn’t displaying them properly, it’s likely a CSS or Smarty template issue within your theme.
1. Check if default PrestaShop themes (e.g., Classic) display the combinations correctly. If they do, the issue is with your custom theme.
2. You may need to consult with a web developer to adjust your theme’s `product.tpl` or associated CSS to properly render the new attribute selectors.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The `Merge Products` module follows a standard PrestaShop MVC pattern for its Back Office components. It leverages PrestaShop’s `ObjectModel` for data manipulation (though it primarily interacts with core `Product` and `Combination` objects directly rather than custom module-specific models). The core logic for finding, building, and merging products and their combinations is encapsulated in dedicated service classes. The module uses a custom Admin Controller for its main interface, providing a user-friendly grid and form for the merging process. It also implements a logging mechanism for tracking merge operations.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. The module is purely a Back-Office administration tool.
- **Back-Office Admin Controllers**:

  - `controllers/admin/AdminMyMergeProductsController.php`

    - **Class Name**: `AdminMyMergeProductsController`
    - **Parent Class**: `ModuleAdminController`
    - **Responsibility**: This is the primary controller for the module’s administrative interface. It handles the display of the merge tool, including product search (autocomplete), configuration options, and the initiation of the merge process. It orchestrates calls to the core service classes (`MmpFinder`, `MmpMergeEngine`, `MmpLogger`, `MmpRedirector`) to perform the actual merging. It manages the form submission and displays feedback to the user.
    - **Tab Name**: “Merge Products” (under Catalog menu)
    - **Managed Entity**: Products and their combinations, attributes.
  - `controllers/admin/index.php`

    - **Class Name**: N/A (empty file)
    - **Parent Class**: N/A
    - **Responsibility**: This is a standard empty `index.php` file, often placed in directories to prevent directory listing on web servers. It has no functional role in the module’s logic.

### 4.3 Core Classes & Models (`classes/`)

- `classes/index.php`

  - **Responsibility**: Standard empty `index.php` file to prevent directory listing.
- `classes/MmpCombinationBuilder.php`

  - **Class Name**: `MmpCombinationBuilder`
  - **Parent Class**: None (standalone service class)
  - **Responsibility**: This class is responsible for the intricate logic of creating new product combinations based on the source products. It handles:
    - Mapping source product data (price, quantity, EAN, reference) to new combinations.
    - Creating new attributes and attribute groups if `MMP_MERGE_MODE` is set to “Add a new attribute group”.
    - Assigning existing attributes to new combinations.
    - Handling images for combinations.
    - Ensuring stock and price rules are correctly applied to the new combinations.
- `classes/MmpFinder.php`

  - **Class Name**: `MmpFinder`
  - **Parent Class**: None (standalone service class)
  - **Responsibility**: Provides methods for searching and retrieving products based on various criteria (ID, name, EAN, reference). This class is used by the `AdminMyMergeProductsController` for the autocomplete search functionality for both master and source products. It also filters products based on module configuration (e.g., `MMP_ACTIVE_ONLY`, `MMP_EXCLUDE_PACKS`, `MMP_EXCLUDE_VIRTUAL`).
- `classes/MmpLogger.php`

  - **Class Name**: `MmpLogger`
  - **Parent Class**: None (standalone service class)
  - **Responsibility**: Handles logging of merge operations. It records details of each merge, including the master product, source products, and configuration settings used. This is crucial for debugging and auditing. It likely stores logs in a custom database table or a file.
- `classes/MmpMergeEngine.php`

  - **Class Name**: `MmpMergeEngine`
  - **Parent Class**: None (standalone service class)
  - **Responsibility**: This is the central orchestrator for the merge process. It takes the master product and source products, along with the configuration settings, and coordinates the actions:
    - Calls `MmpCombinationBuilder` to create combinations.
    - Updates the master product.
    - Handles the `MMP_SOURCE_ACTION` (deactivate or delete source products).
    - Manages the batch processing (`MMP_BATCH_SIZE`).
    - Interacts with `MmpRedirector` for 301 redirects.
    - Utilizes `MmpLogger` to record the operation.
- `classes/MmpRedirector.php`

  - **Class Name**: `MmpRedirector`
  - **Parent Class**: None (standalone service class)
  - **Responsibility**: Manages the creation of 301 redirects. When `MMP_REDIRECT` is enabled, this class creates entries in PrestaShop’s `ps_product_redirect` table (or similar mechanism) to redirect old source product URLs to the new master product URL.

### 4.4 JavaScript Assets (`views/js/`)

- `lib/searchTool/views/js/autocomplete.js`

  - **Scope**: Back-office.
  - **Responsibility**: Provides the JavaScript logic for the product autocomplete search fields used in the `AdminMyMergeProductsController`. It likely uses AJAX to query `MmpFinder` for product suggestions as the user types, displaying results in a dropdown. It handles selection and populating the respective product fields.
- `views/js/admin.js`

  - **Scope**: Back-office.
  - **Responsibility**: Contains general JavaScript functionalities for the module’s admin interface. This might include:
    - Conditional display of configuration fields (e.g., `New Attribute Group Name` only visible if “Add a new attribute group” is selected).
    - Form validation.
    - AJAX calls for initiating the merge process and displaying progress.
    - Event listeners for buttons and form changes.

### 4.5 CSS Stylesheets (`views/css/`)

- `lib/searchTool/views/css/autocomplete.css`

  - **Scope**: Back-office admin styling.
  - **Responsibility**: Styles the autocomplete dropdown and search input fields, ensuring they are visually consistent and user-friendly within the PrestaShop Back Office.
- `views/css/admin.css`

  - **Scope**: Back-office admin styling.
  - **Responsibility**: Provides specific styling for the `AdminMyMergeProductsController` interface, including layout of the sections, styling of product lists, and general visual enhancements for the module’s configuration page.

### 4.6 Smarty Template Structure (`views/templates/`)

- `lib/searchTool/views/scripts.tpl`

  - **Scope**: Back-office.
  - **Responsibility**: This template likely includes the necessary JavaScript and CSS for the autocomplete search tool, ensuring it’s loaded on the relevant admin pages. It might contain `script` and `link` tags.
- `views/templates/admin/configure_shell.tpl`

  - **Scope**: Back-office admin.
  - **Responsibility**: This template serves as a wrapper or shell for the module’s main configuration content. It might include common header/footer elements, navigation, or general layout structure for the module’s admin pages. It likely includes `dashboard.tpl`.
- `views/templates/admin/dashboard.tpl`

  - **Scope**: Back-office admin.
  - **Responsibility**: This is the main template for the `AdminMyMergeProductsController` view. It renders the entire merge tool interface, including:
    - The master product selection area.
    - The source products selection area.
    - The merge configuration options form (with all the settings like `MMP_MERGE_MODE`, `MMP_REDIRECT`, etc.).
    - The “Merge Products” button.
    - Any status messages or progress indicators during the merge.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module primarily interacts with existing PrestaShop core tables:
    - `ps_product`: For retrieving product information and updating product status (active/inactive).
    - `ps_product_attribute`: For creating and managing product combinations.
    - `ps_product_attribute_shop`: For shop-specific combination data.
    - `ps_product_attribute_combination`: Links combinations to attributes.
    - `ps_attribute_group`, `ps_attribute_group_lang`, `ps_attribute_group_shop`: For creating new attribute groups.
    - `ps_attribute`, `ps_attribute_lang`, `ps_attribute_shop`: For creating new attributes.
    - `ps_stock_available`: For updating stock quantities for combinations.
    - `ps_product_lang`: For product names and descriptions.
    - `ps_product_shop`: For shop-specific product data.
    - `ps_url_rewrite`: For managing friendly URLs.
    - `ps_configuration`: Stores module configuration settings (e.g., `MMP_MERGE_MODE`, `MMP_MASTER_RULE`, `MMP_SOURCE_ACTION`, `MMP_REDIRECT`, `MMP_BATCH_SIZE`, `MMP_ACTIVE_ONLY`, `MMP_EXCLUDE_PACKS`, `MMP_EXCLUDE_VIRTUAL`, `MMP_MIN_GROUP`, `MMP_ATTRIBUTE_GROUP`, `MMP_ATTRIBUTE_GROUP_NAME`).
  - The module might create a custom table for logging merge operations (e.g., `ps_mmp_log` or similar), though this is not explicitly detailed in the provided inventory. If it exists, it would store records of each merge event.
  - For 301 redirects, it likely uses PrestaShop’s `ps_product_redirect` table (or similar mechanism if the module implements its own redirect handler).
- **Registered Hooks Table**:
  The module does not explicitly register any front-office hooks (like `displayHeader`, `displayProductButtons`, etc.) as it’s a back-office tool. Its primary interaction with PrestaShop’s hook system would be for:

  - `actionAdminControllerSetMedia`: To load its specific CSS and JS files in the Back Office.
  - `actionProductUpdate` / `actionProductAdd` / `actionProductDelete`: While not explicitly listed, the module’s internal logic for modifying products might trigger these core PrestaShop hooks, which other modules might listen to.
  - `actionObjectProductAddAfter`, `actionObjectProductUpdateAfter`, `actionObjectProductDeleteAfter`: ObjectModel hooks that would be triggered when the module creates, updates, or deletes `Product` or `ProductAttribute` objects.

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Merge Products” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any technical issues or questions you may have regarding the module’s functionality.
