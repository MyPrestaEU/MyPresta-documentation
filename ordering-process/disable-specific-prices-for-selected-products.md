---
title: "Disable specific prices for selected products - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Disable specific prices for selected products PrestaShop module by MyPresta.eu."
sidebar:
  label: "Disable specific prices for selected products - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Disable specific prices for selected products Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-specific-prices-for-selected-products.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/disable-specific-prices-for-selected-products/)
>
> ---


# Disable specific prices for selected products

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the module name to access its settings. This is the main and only configuration screen for this module.

#### **General Settings**

- **Disable specific prices for selected products**
  - **What this setting does:** This is the master switch to enable or disable the module’s core functionality.
  - **Effect of changing this setting:**
    - *When Enabled (YES):* The module will actively prevent specific prices from being applied to the products and categories you select below.
    - *When Disabled (NO):* The module will be inactive. All specific prices and catalog price rules will apply to all products as normal, regardless of your selections in the “Categories” or “Specific products” fields.
  - **Recommended value:** **YES** if you intend to use the module’s functionality to exclude products from discounts. **NO** if you want to temporarily disable it without losing your saved configurations.
  - **Merchant scenario / example:** You’ve just launched a new line of premium products and want to ensure they are never discounted. You enable this setting and then add those products to the exclusion list.

#### **Exclusion Criteria**

- **Categories**

  - **What this setting does:** This field allows you to select entire product categories whose products should be excluded from specific prices.
  - **Effect of changing this setting:**
    - *When categories are selected:* All products belonging to the selected categories (including subcategories, depending on PrestaShop’s category structure and how specific prices are applied) will have specific prices disabled.
    - *When no categories are selected:* Only products explicitly listed in the “Specific products” field will be affected.
  - **Recommended value:** Select categories that contain products you consistently want to protect from discounts, such as “New Arrivals,” “Luxury Goods,” or “Clearance (if you only want to apply manual discounts).”
  - **Merchant scenario / example:** You have a “Premium Brands” category. By selecting it here, all products within that category will automatically be excluded from specific price calculations, saving you from listing each product individually.
- **Specific products**

  - **What this setting does:** This field allows you to search for and select individual products that should be excluded from specific prices. It uses an autocomplete search tool to help you find products quickly.
  - **Effect of changing this setting:**
    - *When products are selected:* The chosen individual products will have specific prices disabled, regardless of their category.
    - *When no products are selected:* Only products within the selected “Categories” will be affected.
  - **Recommended value:** Use this for individual items that don’t fit into a broader category exclusion, or for specific best-sellers you want to keep at full price.
  - **Merchant scenario / example:** You have a few high-demand gadgets that always sell well at full price. You search for “iPhone 15” and “Samsung Galaxy S24” and add them to this list to ensure they are never discounted by specific prices.

#### **Saving Your Changes**

After making any changes to the settings, remember to click the **“Save”** button at the bottom of the configuration page to apply them.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Disable specific prices for selected products | YES | Master switch to enable/disable the module’s functionality. YES means exclusions are active. |
| Module Configuration Page | Categories | None selected | Select categories whose products will be excluded from specific prices. |
| Module Configuration Page | Specific products | None selected | Search for and select individual products to be excluded from specific prices. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve configured the module, but specific prices are still applying to my excluded products. What’s wrong?**
A1:

- **Check Module Status:** First, ensure the “Disable specific prices for selected products” setting on the module’s configuration page is set to **YES (Enabled)**.
- **Verify Exclusions:** Double-check that the specific products or categories you intend to exclude are correctly selected in the module’s settings. Use the search function carefully for products.
- **Clear Cache:** PrestaShop often caches pricing information. Go to **Advanced Parameters > Performance** and click “Clear cache” at the top right. Also, clear your browser’s cache.
- **Specific Price Priority:** Ensure the specific price rule you’re testing isn’t somehow overriding the module. This module works by overriding PrestaShop’s core specific price calculation. If you have other modules that also modify pricing, there might be a conflict. Try disabling other pricing-related modules temporarily to diagnose.

**Q2: Will this module affect my Cart Rules (vouchers)?**
A2: Yes, indirectly. This module prevents specific prices from being applied to selected products. If a Cart Rule (voucher) offers a discount that *relies* on or interacts with PrestaShop’s specific price mechanism (e.g., a percentage discount that calculates based on the product’s current price *after* specific prices), then the excluded products will not receive that specific price reduction before the voucher is applied. The voucher will then apply to the product’s base price (or its price after other non-specific price discounts).

**Q3: Does this module work with multi-store setups?**
A3: The module’s configuration is typically global or tied to the context you are in when configuring it. If you have a multi-store setup, test thoroughly to ensure the exclusions apply as expected across all relevant stores. PrestaShop’s `override` mechanism usually applies globally, but specific price rules themselves can be store-specific.

**Q4: I’ve added a new product to an excluded category, but it’s still getting specific prices. Why?**
A4:

- **Cache:** Always clear your PrestaShop cache (**Advanced Parameters > Performance**) after making changes to categories or products, especially if you’re adding new items or moving them between categories.
- **Category Structure:** Ensure the specific price rule isn’t being applied in a way that bypasses the category exclusion (e.g., a rule for “all products” that doesn’t respect category hierarchy). The module should intercept the specific price calculation regardless, but caching is often the culprit.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Disable specific prices for selected products” module leverages PrestaShop’s override system to modify core pricing logic. Specifically, it overrides the `Product` and `SpecificPrice` classes to inject its exclusion logic directly into the price calculation process. This ensures that when PrestaShop attempts to determine a product’s price, the module first checks if the product or its category is on the exclusion list, and if so, it prevents specific prices from being applied. The module uses a standard PrestaShop module structure, with a main module file, overrides, and `views` for assets and templates.

### 4.2 Controllers (`controllers/`)

This module does not contain any custom Front-Office or Back-Office Admin Controllers. Its configuration is handled directly within the `getContent()` method of the main module file, and its core functionality is implemented via class overrides.

### 4.3 Core Classes & Models (`classes/`)

- **`exsp/override/classes/index.php`**:

  - This is a standard empty `index.php` file, typically placed in directories to prevent directory listing. It has no functional impact on the module’s logic.
- **`exsp/override/classes/Product.php`**:

  - **Class Name & Parent Class**: `Product` (overrides PrestaShop’s core `Product` class).
  - **Responsibility**: This override is the primary mechanism for intercepting product price calculations. It modifies the `getPrice()` method (or related methods) to check if the current product (or its category) is configured for exclusion. If it is, the specific price component of the calculation is bypassed, ensuring the product’s base price is returned without any specific price reductions. This is crucial for preventing specific prices from being applied at the product level.
  - **Key Public Methods**: The overridden `getPrice()` method (or similar price calculation methods within the `Product` class) will contain the logic to check `exsp_categories` and `exsp_products` configuration values.
- **`exsp/override/classes/SpecificPrice.php`**:

  - **Class Name & Parent Class**: `SpecificPrice` (overrides PrestaShop’s core `SpecificPrice` class).
  - **Responsibility**: This override directly impacts how specific prices are fetched and applied. It modifies methods like `getSpecificPrice()` or `getSpecificPrices()` to filter out or ignore specific price rules for products that are on the exclusion list. This acts as a secondary layer of defense, ensuring that even if a specific price rule exists, it won’t be considered for excluded products.
  - **Key Public Methods**: Overridden methods related to fetching or applying specific prices will incorporate checks against the module’s exclusion lists.

### 4.4 JavaScript Assets (`views/js/`)

- **`exsp/lib/searchTool/views/js/autocomplete.js`**:

  - **Scope**: Back-office (module configuration page).
  - **Description**: This script provides the autocomplete functionality for the “Specific products” input field on the module’s configuration page. It likely uses AJAX to query PrestaShop’s product database as the user types, suggesting matching product names. It handles the display of suggestions and the selection of products to be added to the exclusion list.
  - **Event Listeners**: Keyup events on the product search input, click events on autocomplete suggestions.
  - **DOM Manipulation**: Dynamically creates and updates the suggestion list, adds selected products to a hidden input or display area.
- **`exsp/views/js/exsp.js`**:

  - **Scope**: Back-office (module configuration page).
  - **Description**: This is the main JavaScript file for the module’s configuration interface. It handles the initialization of the autocomplete search tool, manages the display and removal of selected products/categories, and potentially performs other UI interactions specific to the module’s settings.
  - **Event Listeners**: Click events for removing selected products/categories, potentially change events for the main enable/disable switch.
  - **DOM Manipulation**: Manages the visual representation of selected categories and products, updates hidden input fields that store the configuration values.

### 4.5 CSS Stylesheets (`views/css/`)

- **`exsp/lib/searchTool/views/css/autocomplete.css`**:
  - **Scope**: Back-office (module configuration page).
  - **Description**: This stylesheet provides the visual styling for the autocomplete search input and its suggestion list. It defines the appearance of the search box, the dropdown suggestions, and potentially hover/active states for better user experience.
  - **Main UI components**: `.autocomplete-container`, `.autocomplete-suggestions`, `.autocomplete-suggestion`.
  - **Key CSS class selectors**: `.exsp-product-search-input`, `.exsp-selected-item`, `.exsp-remove-item`.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`exsp/lib/searchTool/views/scripts.tpl`**:

  - **Scope**: Back-office (module configuration page).
  - **Description**: This template likely includes the necessary JavaScript and CSS files for the autocomplete search tool, or it might contain inline JavaScript for initializing the autocomplete widget with specific parameters (e.g., AJAX URL for product search).
  - **Rendered in**: `ActionAdminControllerSetMedia` hook or directly within `getContent()`.
- **`exsp/views/script.tpl`**:

  - **Scope**: Back-office (module configuration page).
  - **Description**: This template is responsible for rendering the main configuration form of the module. It includes the HTML structure for the enable/disable switch, the category selection field, and the product search input with its associated display for selected products. It also likely includes the `exsp.js` and `autocomplete.js` scripts.
  - **Rendered in**: `getContent()` method of `exsp.php`.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create any custom SQL tables.
  - It stores its configuration settings (enabled status, excluded categories, excluded products) in PrestaShop’s `ps_configuration` table.
    - `exsp_categories`: Stores a serialized array or comma-separated list of category IDs to be excluded.
    - `exsp_products`: Stores a serialized array or comma-separated list of product IDs to be excluded.
    - `exsp_enabled`: Stores the module’s enabled/disabled status (e.g., `1` for enabled, `0` for disabled).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Executed when an admin controller is loaded, before its content is rendered. | Used to register and include the module’s JavaScript and CSS assets (e.g., for the autocomplete search tool) on the module’s configuration page. |
| (Implicit Hooks via Overrides) | During product price calculation (`Product::getPrice()`) and specific price fetching (`SpecificPrice::getSpecificPrices()`). | The core functionality of the module is implemented by overriding PrestaShop’s `Product` and `SpecificPrice` classes. This means the module’s logic is executed whenever these core methods are called, effectively “hooking into” the price calculation process without explicitly registering a `display` or `action` hook. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Disable specific prices for selected products” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any technical issues or questions you may have regarding the module’s functionality.
