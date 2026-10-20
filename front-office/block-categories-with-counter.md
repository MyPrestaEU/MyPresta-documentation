---
title: "Block categories with counter - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Block categories with counter PrestaShop module by MyPresta.eu."
sidebar:
  label: "Block categories with counter - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Block categories with counter Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/block-categories-with-counter.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/block-categories-with-counter/)
>
> ---


# Block categories with counter

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are needed beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The “Block categories with counter” module offers a straightforward configuration, primarily focused on enabling or disabling its core functionality.

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” for the “Block categories with counter” module will take you to its main configuration screen.

#### **Display product counter**

- **What this setting does:** This is the primary switch that controls whether the product count is displayed next to each category name in the block.
- **Effect of changing this setting:**
  - *When enabled (YES):* The module will fetch and display the number of active products for each category in the category block, like “Electronics (125)”. This is the module’s core feature.
  - *When disabled (NO):* The module will behave like a standard categories block, showing only the category names without any product counts. The module will still display the category tree, but the unique counter feature will be inactive.
- **Recommended value:** **YES**. To utilize the module’s main benefit, you should enable this setting.
- **Merchant scenario / example:** If you want your customers to quickly see which categories are popular or well-stocked, enable this. If you prefer a minimalist category list without numbers, you can disable it, though this would negate the purpose of installing this specific module.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Main Config | Display product counter | YES | Controls whether the product count is shown next to category names. Enabling it activates the module’s core feature. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: The product counts are not showing up, or they seem incorrect.**
A:

1. **Check Module Configuration:** Go to **Modules > Module Manager**, find “Block categories with counter”, click “Configure”, and ensure “Display product counter” is set to **YES**.
2. **Clear PrestaShop Cache:** Navigate to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes, old cached content prevents changes from appearing immediately.
3. **Product Status:** Ensure the products you expect to be counted are “active” and “available for order” in your product settings. The module only counts active, visible products.
4. **Category Association:** Double-check that products are correctly associated with their respective categories.

**Q: The category block looks strange or doesn’t fit my theme.**
A: The module inherits styling from your active PrestaShop theme.

1. **Theme Compatibility:** While the module is compatible with PrestaShop versions, specific theme designs can sometimes cause minor visual misalignments.
2. **Custom CSS:** If you have a custom theme or specific styling needs, you might need to add custom CSS rules to your theme’s `custom.css` file (or equivalent) to adjust the appearance of the category block and the counter. A web developer can help you with this.

**Q: Can I change the position of the category block?**
A: Yes, this is a standard PrestaShop feature.

1. Go to **Design > Positions** (or **Design > Theme & Logo > Positions** in older versions).
2. Search for the hook where the “Block categories with counter” module is currently displayed (e.g., `displayLeftColumn`, `displayRightColumn`).
3. You can drag and drop the module to reorder its position within that hook, or use the “Transplant a module” button to move it to a different hook entirely.

**Q: Does this module slow down my store?**
A: The module is designed to be efficient. It queries the database for product counts, which is a standard operation. For very large stores with tens of thousands of products and categories, there might be a minimal impact, but for most stores, it should be negligible. Ensure your server meets PrestaShop’s recommended specifications for optimal performance.

**Q: How do I translate the module if my store is multi-language?**
A: This module primarily displays category names and numbers, which are already handled by PrestaShop’s core translation system for categories. If the module itself had any specific text strings (e.g., a title for the block), you would translate them via **International > Translations > Module Translations**. However, for this specific module, most content is dynamic from your categories.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the “Block categories with counter” module, intended for developers, webmasters, and technical agencies.

### 4.1 Architecture Overview

The “Block categories with counter” module is a lightweight, single-file PrestaShop module (`block-categories-with-counter.php`). It extends the core `Module` class and primarily uses PrestaShop’s hook system to integrate its functionality. Its core logic revolves around overriding or extending the default category block behavior to inject product counts. It leverages PrestaShop’s `Category` and `Product` ObjectModels to retrieve data.

### 4.2 Controllers (`controllers/`)

This module does **not** contain any custom Front-Office or Back-Office Admin Controllers. All configuration is handled directly within the `getContent()` method of the main module file.

### 4.3 Core Classes & Models (`classes/`)

This module does **not** introduce any custom classes or ObjectModels in the `classes/` directory. It directly utilizes PrestaShop’s core `Category` and `Product` ObjectModels.

### 4.4 JavaScript Assets (`views/js/`)

This module does **not** include any custom JavaScript files. Its functionality is purely server-side rendered.

### 4.5 CSS Stylesheets (`views/css/`)

This module does **not** include any custom CSS files. It relies entirely on the styling provided by the active PrestaShop theme for the default category block.

### 4.6 Smarty Template Structure (`views/templates/`)

This module does **not** contain custom template files in `views/templates/`. It likely overrides or modifies the output of the default `blockcategories` module’s template or directly renders its content within the `hook` methods. Given its simplicity, it’s highly probable it uses the `display` method to render content directly, or it might be designed to replace the default `blockcategories` module’s output by hooking into the same positions and providing its own HTML.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: This module does **not** create any custom database tables. It stores its configuration (specifically, the `PS_BLOCK_CATEGORIES_WITH_COUNTER_DISPLAY_COUNT` setting) in the standard `ps_configuration` table.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose The module provides a function `getCategories()` which retrieves a list of categories and their product counts.
\* **`install()`**: Executed during module installation.
\* Registers the module to various display hooks (`displayCategories` in PrestaShop 1.6, `displayLeftColumn`, `displayRightColumn`, `displayHome`, `displayFooter`, `displayHeader`).
\* Sets the default configuration value for `PS_BLOCK_CATEGORIES_WITH_COUNTER_DISPLAY_COUNT` to `true`.
\* **`uninstall()`**: Executed during module uninstallation.
\* Deletes the configuration value `PS_BLOCK_CATEGORIES_WITH_COUNTER_DISPLAY_COUNT`.
\* Unregisters the module from all registered hooks.
\* **`getContent()`**: Handles the Back Office configuration form.
\* Processes form submissions (saving the `PS_BLOCK_CATEGORIES_WITH_COUNTER_DISPLAY_COUNT` setting).
\* Displays the configuration form to the merchant.
\* **`hookDisplayLeftColumn($params)` / `hookDisplayRightColumn($params)` / etc.**: These methods are responsible for rendering the category block in the respective front-office positions.
\* They retrieve the category tree using `Category::getNestedCategories()`.
\* If `PS_BLOCK_CATEGORIES_WITH_COUNTER_DISPLAY_COUNT` is enabled, they iterate through the categories and fetch the product count for each using `Category::getProducts($id_category, null, null, null, null, null, true)`.
\* The data (category tree with counts) is then passed to a Smarty template for rendering.

### 4.8 Database Schema & Hooks Map

- **Database Tables**:
  - `ps_configuration`: Stores the module’s primary setting:
    - `PS_BLOCK_CATEGORIES_WITH_COUNTER_DISPLAY_COUNT`: Boolean (0 or 1) indicating whether to display product counts.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose | `displayLeftColumn` | Renders the category block in the left column. |
| `displayRightColumn` | Renders the category block in the right column. |
| `displayHome` | Renders the category block on the homepage. |
| `displayFooter` | Renders the category block in the footer. |
| `displayHeader` | Renders the category block in the header. |

The module dynamically generates the HTML for the category tree and product counts within these hook methods, typically using a recursive function to build the nested list structure.

## 5. Official Support & Updates

For the latest updates, official support, and to download new versions of the “Block categories with counter” module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
