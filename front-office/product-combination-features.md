---
title: "Product combination features - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Product combination features PrestaShop module by MyPresta.eu."
sidebar:
  label: "Product combination features - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Product combination features Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-combination-features.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/product-combination-features/)
>
> ---


# Product combination features

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the “Product combination features” module. You can access it by navigating to **Modules > Module Manager**, searching for “Product combination features”, and clicking “Configure”.

#### **Turn on features for combinations**

- **What this setting does:** This is the master switch for enabling or disabling the core functionality of assigning unique features to product combinations.
- **Effect of changing this setting:**
  - *When enabled:* You will see a new section on your product edit pages (under the “Modules” tab) where you can assign specific features and their values to each combination. When customers select a combination on the front office, the product’s data sheet will dynamically update to show these combination-specific features.
  - *When disabled:* The combination feature management section will not appear on product edit pages, and the front office will revert to showing only the main product’s features, regardless of the selected combination.
- **Recommended value:** **Enabled** (if you want to use the module’s primary function).
- **Merchant scenario / example:** If you sell t-shirts and want “Material: 100% Cotton” for the white shirt and “Material: 50% Cotton, 50% Polyester” for the grey shirt, you *must* enable this.

#### **Data sheet css class**

- **What this setting does:** This allows you to specify a CSS class or HTML element ID that the module should target when updating the features section on the product page. This is crucial for the module to correctly identify where to display the combination-specific features in your theme.
- **Effect of changing this setting:**
  - *When set correctly:* The module will find the specified element and dynamically insert or update the combination features within it.
  - *When set incorrectly or left empty:* The combination features might not appear on the front office, or they might appear in an unexpected location, as the module won’t know where to put them.
- **Recommended value:** This depends entirely on your PrestaShop theme. A common class is `.product-features` or `.data-sheet`. You might need to inspect your product page’s HTML to find the correct selector. If unsure, consult your theme developer or a webmaster.
- **Merchant scenario / example:** Your theme displays product features inside a `div` with the class `product-specifications`. You would enter `.product-specifications` here.

#### **Workflow**

- **What this setting does:** This controls how the module handles features when a combination is selected.
- **Effect of changing this setting:**
  - *When set to “Append”:* Combination-specific features will be *added* to the main product’s features. So, you’ll see both the general product features and the unique combination features.
  - *When set to “Replace”:* Combination-specific features will *replace* the main product’s features. Only the features relevant to the selected combination will be shown.
- **Recommended value:** **Replace** for most cases, as it provides the most precise information. Choose “Append” if you have general features that apply to all combinations, plus specific ones.
- **Merchant scenario / example:**
  - *Replace:* For a laptop, you might want “Processor: i7”, “RAM: 16GB” to completely replace “Processor: i5”, “RAM: 8GB” when a customer selects the i7/16GB combination.
  - *Append:* For a t-shirt, you might always want “Brand: MyBrand” to show (general feature), but then *add* “Material: Organic Cotton” when a specific combination is chosen.

#### **Turn on descriptions for combinations**

- **What this setting does:** This enables or disables the ability to assign unique descriptions to each product combination.
- **Effect of changing this setting:**
  - *When enabled:* A new field will appear on your product edit pages (under the “Modules” tab) allowing you to enter a specific description for each combination. When customers select a combination, this description will dynamically replace the main product description.
  - *When disabled:* The combination description field will not appear, and the front office will always show the main product’s description.
- **Recommended value:** **Enabled** (if you need combination-specific descriptions).
- **Merchant scenario / example:** You sell custom jewelry. A “Silver Ring” product might have a combination “Engraved: Yes”. You could use a combination description to explain the engraving process and character limits, which isn’t relevant for the “Engraved: No” combination.

#### **Description of css class / object ID**

- **What this setting does:** Similar to the “Data sheet css class”, this tells the module which HTML element on your product page contains the main product description that should be replaced by the combination-specific description.
- **Effect of changing this setting:**
  - *When set correctly:* The module will find the specified element and dynamically update its content with the combination description.
  - *When set incorrectly or left empty:* The combination description might not appear, or it might appear in an unexpected place.
- **Recommended value:** This depends on your theme. Common selectors are `.product-description`, `#description_short`, or `#product-description-short`. You’ll need to inspect your product page’s HTML.
- **Merchant scenario / example:** Your theme uses a `div` with the ID `product-description-full` for the main description. You would enter `#product-description-full` here.

#### **Turn on meta title for combinations**

- **What this setting does:** This enables or disables the ability to set a unique meta title for each product combination. This meta title is what appears in the browser tab and is used by search engines.
- **Effect of changing this setting:**
  - *When enabled:* A new field will appear on your product edit pages (under the “Modules” tab) allowing you to enter a specific meta title for each combination. When a customer selects a combination, the browser tab title will dynamically update.
  - *When disabled:* The combination meta title field will not appear, and the browser tab will always show the main product’s meta title.
- **Recommended value:** **Enabled** (if you want to improve SEO for specific combinations or provide clearer browser tab titles).
- **Merchant scenario / example:** For a “Smartphone” product, you might have a combination “Color: Blue, Storage: 128GB”. You could set its meta title to “Blue Smartphone 128GB - [Your Store Name]” for better search engine visibility.

#### **Default title mode**

- **What this setting does:** This defines how the combination meta title is constructed if you don’t explicitly set one for a combination, or if you want to combine the product title with combination attributes.
- **Effect of changing this setting:**
  - *When set to “Product name + combination name”:* The meta title will be the main product name followed by the selected combination’s attribute names (e.g., “T-Shirt - Red, Large”).
  - *When set to “Combination name + product name”:* The meta title will be the selected combination’s attribute names followed by the main product name (e.g., “Red, Large - T-Shirt”).
  - *When set to “Combination name”:* Only the combination’s attribute names will be used (e.g., “Red, Large”).
  - *When set to “Product name”:* The meta title will always be the main product name, ignoring combinations.
- **Recommended value:** **“Product name + combination name”** or **“Combination name + product name”** for good balance between product identity and combination specificity.
- **Merchant scenario / example:** You sell shoes. If a customer selects “Size 10, Color Black”, and “Product name + combination name” is chosen, the title becomes “Running Shoes - Size 10, Black”.

#### **Title separator**

- **What this setting does:** This allows you to define the character or string used to separate the different parts of the dynamically generated meta title (e.g., between product name and combination name).
- **Effect of changing this setting:**
  - *When set to ”-”:* The title might look like “Product Name - Combination”.
  - *When set to ”|”:* The title might look like “Product Name | Combination”.
  - *When left empty:* The parts of the title might run together without a clear separator.
- **Recommended value:** **-** (hyphen) or **|** (pipe) are common and clear separators.
- **Merchant scenario / example:** If your default title mode is “Product name + combination name” and separator is set to ”|”, a title might become “My Awesome T-Shirt | Red, Large”.

### 2.2 Dedicated Admin Screens & Controller Views

This module does not create dedicated top-level admin screens. Instead, it integrates directly into the existing **Product Edit Page** in your PrestaShop Back Office.

- **Screen Name & Menu Location:**

  - Navigate to **Catalog > Products**.
  - Edit an existing product or create a new one.
  - Within the product edit page, click on the **“Modules”** tab.
  - You will find a new section titled **“Product combination features”** (or similar, depending on module version/translations).
- **Available Actions & Settings:**

  - Inside this section, you will see a list of all combinations configured for the current product.
  - For each combination, you will have fields to:
    - **Assign Features:** You can select existing features and their values, or even create new feature values, specifically for that combination. The module supports multi-features, meaning a combination can have several values for the same feature (e.g., “Material: Cotton, Material: Spandex”).
    - **Enter Combination Description:** A rich text editor (like the standard PrestaShop description editor) will be available to input a unique description for that combination.
    - **Enter Combination Meta Title:** A text field to input a unique meta title for that combination.
  - **Saving Changes:** Remember to click the main “Save” button for the product to apply all combination-specific changes.
- **Effect of changes:**

  - Any features, descriptions, or meta titles you set here will be stored in the database and dynamically displayed on the front office product page when the corresponding combination is selected by a customer.
  - If you delete a combination, its associated features, descriptions, and meta titles will also be removed.
- **Recommended workflow for daily store management:**

  1. First, create your product and its combinations as usual in PrestaShop (under the “Combinations” tab).
  2. Once combinations are created, go to the **“Modules”** tab on the product edit page.
  3. For each combination, carefully assign the relevant features, write a specific description, and set an optimized meta title.
  4. Save the product.
  5. Always test on the front office to ensure the features, descriptions, and titles update correctly when combinations are selected.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Turn on features for combinations | Enabled | Master switch for combination features. |
| Module Configuration | Data sheet css class | `.product-features` (theme dependent) | CSS selector for where combination features are displayed. |
| Module Configuration | Workflow | Replace | How combination features interact with main product features (append or replace). |
| Module Configuration | Turn on descriptions for combinations | Enabled | Master switch for combination descriptions. |
| Module Configuration | Description of css class / object ID | `#product-description-short` (theme dependent) | CSS selector for where combination descriptions are displayed. |
| Module Configuration | Turn on meta title for combinations | Enabled | Master switch for combination meta titles. |
| Module Configuration | Default title mode | Product name + combination name | How meta titles are generated if not explicitly set. |
| Module Configuration | Title separator | `-` | Character used to separate parts of the meta title. |
| Product Edit Page > Modules Tab | Assign Features per Combination | N/A | Assign unique features and values to each combination. |
| Product Edit Page > Modules Tab | Combination Description | N/A | Enter unique rich text description for each combination. |
| Product Edit Page > Modules Tab | Combination Meta Title | N/A | Enter unique meta title for each combination. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My combination features/descriptions aren’t showing up on the product page.**
A:

1. **Check module configuration:** Ensure “Turn on features for combinations” and/or “Turn on descriptions for combinations” are enabled in the module’s configuration.
2. **Verify CSS selectors:** The “Data sheet css class” and “Description of css class / object ID” settings are crucial. These must exactly match the CSS class or ID of the elements in your theme where the features/description are displayed. Use your browser’s developer tools (F12) to inspect your product page and find the correct selectors. If unsure, consult your theme developer.
3. **Clear PrestaShop cache:** Go to **Advanced Parameters > Performance** and click “Clear cache”. Sometimes, old cached content prevents new module output from appearing.
4. **Check product settings:** Ensure you have actually assigned features/descriptions to the specific combinations on the product edit page under the “Modules” tab.

**Q: The combination features/descriptions appear, but they look unstyled or out of place.**
A: This is usually a CSS conflict with your theme.

1. **Inspect with browser tools:** Use F12 to see what CSS rules are being applied to the module’s output.
2. **Adjust CSS class:** If the module’s output is wrapped in a generic `div`, you might need to adjust the “Data sheet css class” or “Description of css class / object ID” to a more specific container that your theme already styles.
3. **Custom CSS:** You might need to add custom CSS to your theme’s stylesheet (or via a custom CSS module) to style the combination features/descriptions to match your theme’s look.

**Q: My combination meta titles aren’t changing in the browser tab.**
A:

1. **Enable the setting:** Make sure “Turn on meta title for combinations” is enabled in the module configuration.
2. **Set titles:** Ensure you’ve entered specific meta titles for your combinations on the product edit page.
3. **Browser behavior:** Some browsers might not immediately update the tab title for already open tabs. Try opening the product page in a new tab or clearing your browser cache.
4. **SEO implications:** While the module updates the client-side title, for search engines to pick up these combination-specific titles, they need to be able to crawl and index the dynamically generated content. Ensure your site is crawlable and consider if these dynamic titles are truly beneficial for your SEO strategy compared to static product titles.

**Q: Can I use this module with multi-language stores?**
A: Yes, the module fully supports multi-language. When you edit combination features, descriptions, or meta titles on the product page, you will see the standard PrestaShop language selector, allowing you to enter content for each language.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Product combination features” module (`combfeat`) extends PrestaShop’s core product management by injecting custom fields and logic into the Back Office product edit page and dynamically updating Front Office content based on selected product combinations. It leverages PrestaShop’s hook system to integrate seamlessly without modifying core files. The module primarily operates through JavaScript on the front end for dynamic updates and PHP on the back end for configuration and data management. It does not introduce new database tables but stores its data in existing PrestaShop structures (likely `ps_product_attribute_feature` for features and `ps_product_attribute_lang` for descriptions/titles, or `ps_configuration` for module settings).

### 4.2 Controllers (`controllers/`)

This module does not use dedicated Front-Office or Back-Office Admin Controllers. Its logic for displaying and saving combination data is integrated directly into the `combfeat.php` main module file and via JavaScript.

### 4.3 Core Classes & Models (`classes/`)

This module does not define custom classes in the `classes/` directory. Its core logic is contained within the main `combfeat.php` file, interacting directly with PrestaShop’s `Product` and `Combination` (ProductAttribute) `ObjectModel`s.

### 4.4 JavaScript Assets (`views/js/`)

- **`combfeat/views/js/acplt.js`**

  - **Scope:** Likely Back-office (admin product page).
  - **Responsibility:** This script appears to be a custom autocomplete library or a component used for selecting features and their values for combinations. It would handle AJAX requests to fetch available features and values, and manage the UI for adding/removing them from a combination.
  - **Key interactions:** Event listeners for input fields, AJAX calls to a module hook or admin controller for data, DOM manipulation to display suggestions and selected items.
- **`combfeat/views/js/admin-combfeat.js`**

  - **Scope:** Back-office (admin product page, “Modules” tab).
  - **Responsibility:** This is the main script for the module’s functionality within the PrestaShop Back Office product edit page. It initializes the combination feature, description, and meta title fields. It likely listens for changes in combination selection (if any) and manages the display and saving of data for each combination.
  - **Key interactions:** DOM manipulation to inject custom fields, event listeners for input changes, potentially AJAX calls to save combination-specific data.
- **`combfeat/views/js/combfeat-append.js`**

  - **Scope:** Front-office (product page).
  - **Responsibility:** This script is specifically for the “Append” workflow option. When a combination is selected, it dynamically fetches and *adds* the combination-specific features to the existing product features on the front end.
  - **Key interactions:** Listens for `updateProduct` or similar events (triggered by combination selection), AJAX calls to fetch combination data, DOM manipulation to append features to the element specified by `combfeat_ds`.
- **`combfeat/views/js/combfeat-title.js`**

  - **Scope:** Front-office (product page).
  - **Responsibility:** This script handles the dynamic updating of the browser’s meta title based on the selected product combination.
  - **Key interactions:** Listens for `updateProduct` or similar events, retrieves the combination’s meta title (either custom or generated based on module settings), and updates `document.title`.
- **`combfeat/views/js/combfeat.js`**

  - **Scope:** Front-office (product page).
  - **Responsibility:** This is the primary front-office script for the module. It orchestrates the dynamic display of combination-specific features and descriptions. It likely listens for changes in product combinations (e.g., attribute selection) and triggers updates to the relevant DOM elements. This script would handle the “Replace” workflow for features and the description update.
  - **Key interactions:** Listens for `updateProduct` or similar events (e.g., `prestashop.on('updatedProduct', ...)`), AJAX calls to retrieve combination data, DOM manipulation to update the elements specified by `combfeat_ds` and `combfeat_description`.

### 4.5 CSS Stylesheets (`views/css/`)

- **`combfeat/views/css/combfeat.css`**
  - **Scope:** Both Front-office and Back-office.
  - **Responsibility:** Provides basic styling for the module’s injected elements. This could include styling for the combination feature/description input fields in the Back Office, or for the dynamically updated feature/description blocks on the Front Office.
  - **Key CSS class selectors:** Likely targets classes used by the module’s templates and JavaScript, such as `.combfeat-feature-list`, `.combfeat-description-wrapper`, or specific styles for the autocomplete component. Developers might need to override these in their theme’s `custom.css` or `theme.css` for perfect integration.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`combfeat/views/templates/admin/combfeat.tpl`**

  - **Scope:** Admin template.
  - **Responsibility:** This template renders the custom section within the “Modules” tab on the product edit page in the Back Office. It displays the interface for managing combination-specific features, descriptions, and meta titles. It likely iterates through all product combinations and provides input fields for each.
  - **Key elements:** Loops for combinations, input fields for feature selection (possibly using the `acplt.js` component), rich text editor for descriptions, text input for meta titles.
- **`combfeat/views/templates/hook/product-details.tpl`**

  - **Scope:** Front-office hook template.
  - **Responsibility:** This template is likely hooked into `displayProductAdditionalInfo` or similar hooks to render the combination-specific features and/or description on the front office product page. It provides the HTML structure that `combfeat.js` and `combfeat-append.js` will populate and update dynamically.
  - **Key elements:** Placeholders (e.g., empty `div`s with specific IDs or classes) where the combination features and descriptions will be injected by JavaScript.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create new custom tables. It likely stores combination-specific features by extending the `ps_product_attribute_feature` relationship or similar, and combination descriptions/meta titles in `ps_product_attribute_lang` or a similar structure, associating them with `id_product_attribute` and `id_lang`.
  - Module configuration settings (`combfeat_ds`, `combfeat_description`, etc.) are stored in the `ps_configuration` table.
- **Registered Hooks Table**:

| Hook Name | Scope | Execution Timing | Technical Purpose |
| --- | --- | --- | --- |
| `displayHeader` | Front-office | In the `<head>` section of all front-office pages. | Registers front-office CSS and JS assets (`combfeat.css`, `combfeat.js`, `combfeat-append.js`, `combfeat-title.js`). |
| `DisplayHeader` | Front-office | Alias for `displayHeader`. | Same as `displayHeader`. |
| `displayProductAdditionalInfo` | Front-office | On the product page, typically below the main product information. | Renders the `product-details.tpl` template, providing a placeholder for combination features/descriptions. |
| `ActionAdminControllerSetMedia` | Back-office | When an admin controller is loaded and its media assets are set. | Registers back-office CSS and JS assets (`combfeat.css`, `acplt.js`, `admin-combfeat.js`) for the product edit page. |
| `ActionProductUpdate` | Back-office | After a product is updated (including combinations). | Potentially used to save or synchronize combination-specific data when the product form is submitted. |
| `actionProductUpdate` | Back-office | Alias for `ActionProductUpdate`. | Same as `ActionProductUpdate`. |
| `displayAdminProductsExtra` | Back-office | On the product edit page, typically as a new tab or section. | Renders the `admin/combfeat.tpl` template, creating the “Product combination features” section under the “Modules” tab. |
| `DisplayAdminProductsExtra` | Back-office | Alias for `displayAdminProductsExtra`. | Same as `displayAdminProductsExtra`. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Product combination features” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and integration.
