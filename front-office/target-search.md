---
title: "Target search - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Target search PrestaShop module by MyPresta.eu."
sidebar:
  label: "Target search - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Target search Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/target-search.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/target-search/)
>
> ---


# Target search

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No unusual server configurations are required.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Target search” module to access its settings. This is where you define exactly where the search engine should look for keywords.

The configuration page will present a series of checkboxes, each corresponding to a specific area of your product data.

- **What this setting does:** Each checkbox allows you to enable or disable searching within a particular field of your product information.
- **Effect of changing this setting:**
  - *When checked (enabled):* The PrestaShop search engine will include data from this specific field when processing customer queries. For example, if “Product Name” is checked, a search for “dress” will find products with “dress” in their name.
  - *When unchecked (disabled):* The PrestaShop search engine will *ignore* data from this field. If “Product Description” is unchecked, a product will not appear in search results if the search term is only found within its description.
- **Recommended value:** This depends entirely on your product catalog and how you want customers to find products. A good starting point is to enable the most critical fields and then refine based on testing.
- **Merchant scenario / example:**
  - **Scenario 1: Highly specific products (e.g., electronics parts, books by ISBN):** You might only want to search in “Product Name”, “Reference”, and “EAN13/JAN”. This ensures customers find exact matches quickly, avoiding irrelevant results from long descriptions.
  - **Scenario 2: Fashion or home goods (e.g., “red dress”):** You might enable “Product Name”, “Short Description”, “Long Description”, and “Tags”. This allows customers to find products based on broader terms, colors, or styles mentioned anywhere in the product details.
  - **Scenario 3: Branded products:** Enable “Manufacturer Name” so customers can easily find all products from a specific brand by typing the brand name into the search bar.

Here’s a breakdown of the typical settings you’ll find:

| Setting / Option | Purpose & Impact | Recommended Value | Merchant Scenario |
| --- | --- | --- | --- |
| **Search in Product Name** | If enabled, search queries will match against the product’s name. | **YES** | Essential for most stores. Customers often search by product name. |
| **Search in Product Short Description** | If enabled, search queries will match against the product’s short description. | **YES** | Useful for finding products based on key features or summaries. |
| **Search in Product Long Description** | If enabled, search queries will match against the product’s full, detailed description. | **YES / NO** | **YES** for broad searches (fashion, home goods). **NO** for very specific items (electronics, parts) to avoid noise. |
| **Search in Product Reference** | If enabled, search queries will match against the product’s internal reference number. | **YES / NO** | **YES** for B2B, technical products, or if customers know part numbers. **NO** if references are internal-only. |
| **Search in Product EAN13/JAN** | If enabled, search queries will match against the product’s EAN13 or JAN barcode. | **YES / NO** | **YES** for stores where customers might search by barcode (e.g., books, groceries). |
| **Search in Product UPC** | If enabled, search queries will match against the product’s UPC barcode. | **YES / NO** | Similar to EAN13/JAN, for regions using UPC. |
| **Search in Product Tags** | If enabled, search queries will match against any tags assigned to the product. | **YES** | Excellent for improving discoverability with keywords not in names/descriptions. |
| **Search in Manufacturer Name** | If enabled, search queries will match against the name of the product’s manufacturer. | **YES** | Crucial if customers often search for specific brands. |
| **Search in Supplier Name** | If enabled, search queries will match against the name of the product’s supplier. | **NO / YES** | **NO** for most B2C stores. **YES** for B2B or specialized stores where supplier is relevant to customers. |
| **Search in Category Name** | If enabled, search queries will match against the name of the categories the product belongs to. | **YES** | Helps customers find products by category name (e.g., “dresses” to find products in the “Dresses” category). |
| **Search in Feature Value** | If enabled, search queries will match against the values of product features (e.g., “red” for a “Color” feature). | **YES** | Highly recommended for stores with rich product features (e.g., color, size, material). |

**Important Note:** After making any changes to these settings, always click the “Save” button. It’s also a good practice to clear your PrestaShop cache (Advanced Parameters > Performance) and test the search functionality on your front office to ensure the changes have taken effect as expected.

### 2.2 Dedicated Admin Screens & Controller Views

This module does not introduce any new dedicated admin screens or custom controllers. All configuration is handled directly within the standard module configuration page.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Search in Product Name | YES | Include product names in search. |
| Module Configuration Page | Search in Product Short Description | YES | Include short descriptions in search. |
| Module Configuration Page | Search in Product Long Description | YES / NO | Include full descriptions. |
| Module Configuration Page | Search in Product Reference | YES / NO | Include product reference numbers. |
| Module Configuration Page | Search in Product EAN13/JAN | YES / NO | Include EAN13/JAN barcodes. |
| Module Configuration Page | Search in Product UPC | YES / NO | Include UPC barcodes. |
| Module Configuration Page | Search in Product Tags | YES | Include product tags. |
| Module Configuration Page | Search in Manufacturer Name | YES | Include manufacturer names. |
| Module Configuration Page | Search in Supplier Name | NO / YES | Include supplier names. |
| Module Configuration Page | Search in Category Name | YES | Include category names. |
| Module Configuration Page | Search in Feature Value | YES | Include product feature values. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve changed settings, but the search results haven’t changed. What’s wrong?**
A: PrestaShop uses caching to speed up your store. After changing module settings, you often need to clear the cache.

- **Solution:** Go to **Advanced Parameters > Performance** in your PrestaShop Back Office. Click “Clear cache” (or “Clear Smarty cache” in older versions). Then, test your search again.

**Q2: My custom theme’s search bar looks different. Will this module still work?**
A: Yes, the “Target search” module primarily overrides the *logic* of how PrestaShop processes search queries, not the visual appearance of the search bar itself. It should work seamlessly with most custom themes.

- **Solution:** If you experience any unexpected visual issues or the search doesn’t seem to be working, it might be a rare conflict with your theme’s custom search template. Contact MyPresta.eu support with details of your theme.

**Q3: Does this module affect search engine optimization (SEO)?**
A: Directly, no. This module enhances the *internal* search experience for your customers on your website. It does not directly impact how external search engines (like Google) crawl or rank your site. However, by improving the on-site search experience, you can reduce bounce rates and increase time on site, which are positive signals for SEO.

**Q4: Can I translate the module’s settings or messages?**
A: The “Target search” module primarily works in the background and doesn’t introduce new front-office text that needs translation. The configuration options in the back office are typically in English. If any new text were introduced, you would translate it via **International > Translations** in your PrestaShop Back Office, selecting “Installed modules translations” and then the “Target search” module.

**Q5: What if I want to search in a field not listed in the module settings?**
A: The module provides options for the most common and impactful product fields. If you have a very specific custom field you need to include in the search, this would require custom development.

- **Solution:** Contact MyPresta.eu support or a PrestaShop developer to discuss custom modifications.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Target search” module primarily operates by overriding PrestaShop’s core `Search` class. This allows it to intercept and modify the default search query logic before it hits the database. The module leverages PrestaShop’s override system to inject its custom search parameters based on the merchant’s configuration. It’s a lightweight module, focusing on modifying existing core behavior rather than introducing complex new entities or controllers.

### 4.2 Controllers (`controllers/`)

This module does not introduce any custom Front-Office or Back-Office Admin Controllers. Its functionality is integrated by overriding a core class and through standard module `getContent()` for configuration.

### 4.3 Core Classes & Models (`classes/`)

The core of this module’s functionality resides in its override of the `Search` class.

- **`targetsearch/override/classes/index.php`**:

  - This is a standard empty `index.php` file, typically placed in directories to prevent directory listing for security reasons. It does not contain any functional code.
- **`targetsearch/override/classes/Search.php`**:

  - **Class name**: `Search` (overrides the core `classes/Search.php`)
  - **Parent class**: `SearchCore`
  - **Responsibility**: This class is responsible for modifying the `search` method of the core `Search` class. It reads the configuration settings stored in `ps_configuration` (e.g., `TARGETSEARCH_PRODUCT_NAME`, `TARGETSEARCH_DESCRIPTION`, etc.) and dynamically adjusts the SQL query used for product searching.
  - **Key Public Methods**:
    - `search($id_lang, $expr, $page_number = 1, $page_size = 10, $order_by = 'position', $order_way = 'desc', $ajax = false, $use_cookie = true, Context $context = null)`: This method is overridden to inject the custom search conditions. It constructs the `WHERE` clause of the SQL query based on the enabled search targets. It checks `Configuration::get('TARGETSEARCH_...')` for each target (product name, description, reference, EAN13, UPC, tags, manufacturer, supplier, category, feature value) and adds corresponding `LIKE` conditions to the query.
  - **Database Interaction**: It does not interact with custom database tables. It modifies the query that interacts with standard PrestaShop product, category, manufacturer, supplier, and feature tables.
  - **`$definition`**: Not applicable as it overrides a core class and doesn’t define a new `ObjectModel`.

### 4.4 JavaScript Assets (`views/js/`)

- **`targetsearch/targetsearch.js`**:
  - **Scope**: Back-office (potentially, but typically not used for front-office search logic).
  - **Purpose**: This file is generally empty or contains minimal JavaScript, often for basic UI interactions on the module’s configuration page if any advanced client-side logic were needed. Given the module’s primary function is server-side search logic, this file is unlikely to contain complex front-office search-related JS. It might be a placeholder or for minor back-office form enhancements.
  - **Event Listeners/DOM Manipulation**: Unlikely to contain significant front-office event listeners or DOM manipulation related to search. Its primary role would be for the module’s configuration page in the back office.

### 4.5 CSS Stylesheets (`views/css/`)

- **`targetsearch/targetsearch.css`**:

  - **Scope**: Back-office.
  - **Purpose**: This stylesheet is typically used to style the module’s configuration page in the PrestaShop Back Office, ensuring it looks consistent with the admin theme. It might contain styles for form elements, alerts, or specific layout adjustments for the module’s settings.
  - **Key CSS Class Selectors**: Likely targets standard PrestaShop admin classes or specific IDs/classes within the module’s `getContent()` output.
- **`targetsearch/targetsearch15.css`**:

  - **Scope**: Back-office (specifically for PrestaShop 1.5.x).
  - **Purpose**: This file provides specific styling adjustments for the module’s configuration page when running on PrestaShop 1.5.x, accounting for differences in the admin theme’s structure and CSS.
  - **Key CSS Class Selectors**: Similar to `targetsearch.css` but tailored for the PS 1.5 admin environment.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`targetsearch/targetsearch-top.tpl`**:
  - **Scope**: Front-office.
  - **Hook**: This template is likely designed to be hooked into `displayHeader` or `displayTop` (or similar hooks that render content in the header area).
  - **Purpose**: While the module’s core function is search logic, this template might be used to output a hidden input, a small script, or a specific visual element related to the module’s presence, though it’s not strictly necessary for the search override itself. Given the module’s description, it’s more probable that this template is a placeholder or for a very minor, non-critical visual component, as the module’s main impact is on the search *results*, not the search *input*. It could also be a remnant from an earlier version or a template intended for a future feature.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any custom database tables.
  - It stores its configuration settings in the standard PrestaShop `ps_configuration` table.
    - Keys: `TARGETSEARCH_PRODUCT_NAME`, `TARGETSEARCH_DESCRIPTION`, `TARGETSEARCH_SHORT_DESCRIPTION`, `TARGETSEARCH_REFERENCE`, `TARGETSEARCH_EAN13`, `TARGETSEARCH_UPC`, `TARGETSEARCH_TAGS`, `TARGETSEARCH_MANUFACTURER`, `TARGETSEARCH_SUPPLIER`, `TARGETSEARCH_CATEGORY`, `TARGETSEARCH_FEATURE_VALUE`.
    - Values: `1` (enabled) or `0` (disabled).
- **Registered Hooks Table**:
  The module registers standard hooks primarily for its installation and uninstallation, and potentially for rendering its configuration. Its core functionality is via class override, not directly through hooks.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `install` | During module installation. | Creates configuration entries in `ps_configuration` with default values. |
| `uninstall` | During module uninstallation. | Removes configuration entries from `ps_configuration`. |
| `displayHeader` (or similar) | Renders content in the `<head>` section or top of the page. | Potentially used to include `targetsearch.js` or `targetsearch.css` if they contain front-office assets, or to render `targetsearch-top.tpl`. |
| `displayBackOfficeHeader` | Renders content in the Back Office `<head>` section. | Used to include `targetsearch.css` (and `targetsearch15.css` conditionally) for styling the module’s configuration page. |

## 5. Official Support & Updates

For official updates, technical support, and any further assistance with the “Target search” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to help you with any issues or questions you may have.
