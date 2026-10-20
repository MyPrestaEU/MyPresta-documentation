---
title: "Free mass products prices update - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Free mass products prices update PrestaShop module by MyPresta.eu."
sidebar:
  label: "Free mass products prices update - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Free mass products prices update Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/free-mass-products-prices-update.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/free-mass-products-prices-update/)
>
> ---


# Free mass products prices update

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are required beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Free mass products prices update)

This is the main and only configuration screen for the “Free mass products prices update” module. Here, you will define how you want to adjust your product prices.

#### **Price Adjustment Type**

- **What this setting does:** This crucial setting determines whether you want to increase or decrease your product prices.
- **Effect of changing this setting:**
  - *When set to “Increase”:* The module will add the specified percentage to the current price of each product.
  - *When set to “Decrease”:* The module will subtract the specified percentage from the current price of each product.
- **Recommended value:** Choose based on your immediate business need (e.g., “Increase” for a general price hike, “Decrease” for a sale).
- **Merchant scenario / example:** If your supplier costs have gone up, you’d select “Increase”. If you’re running a flash sale, you’d select “Decrease”.

#### **Percentage Value**

- **What this setting does:** This field allows you to enter the exact percentage by which you want to adjust your prices.
- **Effect of changing this setting:**
  - *When set to “10”:* If “Increase” is selected, prices will go up by 10%. If “Decrease” is selected, prices will go down by 10%.
  - *When set to “0”:* No price change will occur.
- **Recommended value:** Enter the precise percentage you need. Use whole numbers or decimals (e.g., “5” for 5%, “2.5” for 2.5%).
- **Merchant scenario / example:** To offer a 15% discount store-wide, you’d set “Price Adjustment Type” to “Decrease” and “Percentage Value” to “15”. To increase prices by 7.5%, you’d set “Price Adjustment Type” to “Increase” and “Percentage Value” to “7.5”.

#### **Apply Changes Button**

- **What this does:** This button initiates the actual price update process.
- **Effect of clicking this button:** Once clicked, the module will process all products in your store according to the “Price Adjustment Type” and “Percentage Value” you have set. **This action is irreversible without a database backup.**
- **Recommended action:** Always double-check your “Price Adjustment Type” and “Percentage Value” before clicking this button. Ensure you have a recent database backup.
- **Merchant scenario / example:** After carefully setting “Decrease” and “20” for a weekend sale, you click “Apply Changes” to instantly update all product prices by -20%.

:::warning IMPORTANT NOTE
The “Free mass products prices update” module performs a direct update on your product prices. **There is no “undo” button.** Before applying any changes, it is **CRITICAL** that you create a full backup of your PrestaShop database. This will allow you to restore your prices to their previous state if you make a mistake or change your mind.
:::

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Price Adjustment Type | (Select Increase/Decrease) | Determines if prices will go up or down. |
| Module Configuration | Percentage Value | (Enter desired percentage) | The exact percentage for price adjustment. |
| Module Configuration | Apply Changes Button | (Click with caution) | Executes the mass price update. **Irreversible without backup.** |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve updated prices, but they don’t show on my store. What’s wrong?**
A1: After any significant data change in PrestaShop, especially related to products, it’s a good practice to clear your store’s cache.
\* Go to **Advanced Parameters > Performance** in your Back Office.
\* Click the “Clear cache” button in the top right corner.
\* Also, ensure your browser cache is cleared, or try viewing your store in an incognito/private browsing window.

**Q2: I made a mistake and updated prices incorrectly. How can I revert?**
A2: As mentioned, this module does not have an “undo” button. This is why a database backup is crucial.
\* If you made a backup *before* applying the changes, you will need to restore your database from that backup. This usually requires access to your hosting control panel (e.g., cPanel, Plesk) or using a PrestaShop backup module.
\* If you *did not* make a backup, you will have to manually re-enter the correct prices for your products, or use the module again with an inverse calculation (e.g., if you decreased by 20%, you’d need to increase by 25% to get back to the original value, but this might not be perfectly accurate due to rounding).

**Q3: Does this module affect specific prices or combinations?**
A3: The module updates the *base price* of your products. It does not directly manage specific prices (discounts, quantity discounts) or price impacts of product combinations. If you have specific prices set up, the base price change will affect the starting point for those specific prices.

**Q4: Is it possible to update prices only for specific categories or manufacturers?**
A4: No, this free version of the module performs a mass update across *all* products in your store. It does not offer filtering by category, manufacturer, or other criteria. For more advanced, filtered price updates, you would typically need a more sophisticated, often paid, import/export or mass update module.

**Q5: The module seems stuck or doesn’t respond when I click “Apply Changes”.**
A5: For stores with a very large number of products (thousands), the update process can take some time.
\* Ensure your server’s PHP execution time limit is sufficient. You might see a “500 Internal Server Error” or a timeout if it’s too low. This is a server configuration issue, not a module bug.
\* Check your PrestaShop error logs (located in `var/logs/` in PrestaShop 1.7/8/9) for any specific errors.
\* If the issue persists, contact your hosting provider or a web developer to check server logs and PHP settings.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Free mass products prices update” module is a straightforward PrestaShop module primarily designed for Back Office administration. It follows a basic PrestaShop module structure, leveraging the `Module` class and its `getContent()` method for configuration. It directly interacts with the PrestaShop database to update product prices without custom controllers, models, or complex JavaScript interactions. The module’s logic is self-contained within its main PHP file.

### 4.2 Controllers (`controllers/`)

This module does **not** utilize any custom Front-Office or Back-Office Admin Controllers. All functionality is handled directly within the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)

This module does **not** define any custom classes or extend `ObjectModel`. It directly interacts with the `Product` and `Product::updatePrice()` methods provided by PrestaShop’s core.

### 4.4 JavaScript Assets (`views/js/`)

This module does **not** include any custom JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)

This module does **not** include any custom CSS files. Styling for the configuration page is handled by PrestaShop’s default Back Office theme.

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses two simple Smarty templates:

- **`masspricefree/views/advert.tpl`**:
  - **Scope:** Back-office (module configuration page).
  - **Purpose:** Likely used to display an advertisement or promotional message from MyPresta.eu within the module’s configuration interface. It’s typically rendered at the top or bottom of the `getContent()` output.
- **`masspricefree/views/script.tpl`**:
  - **Scope:** Back-office (module configuration page).
  - **Purpose:** This template might contain inline JavaScript or simple HTML elements that are part of the module’s configuration form, though the module description suggests minimal JS. Given the module’s simplicity, it’s more likely to be a placeholder or contain very basic UI elements.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does **not** create any custom database tables.
  - It directly modifies data in the `ps_product` table (specifically the `price` column) and potentially `ps_product_shop` (for multi-store contexts) by calling core PrestaShop methods.
  - Configuration settings (Price Adjustment Type, Percentage Value) are stored in the `ps_configuration` table using standard PrestaShop configuration keys (e.g., `PS_MASS_PRICE_FREE_TYPE`, `PS_MASS_PRICE_FREE_VALUE`).
- **Registered Hooks Table**:
  This module does **not** register any specific hooks for front-office display or back-office actions beyond the standard `displayBackOfficeHeader` (implicitly for module configuration) and `actionModuleInstall`/`actionModuleUninstall`. Its primary function is a direct database manipulation triggered by the admin form submission.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayBackOfficeHeader` | Renders in the `<head>` section of the Back Office. | Used by `getContent()` to potentially load assets or display notices, though not explicitly used for custom assets in this module. |
| `actionModuleInstall` | Triggered when the module is installed. | Used to set default configuration values in `ps_configuration`. |
| `actionModuleUninstall` | Triggered when the module is uninstalled. | Used to clean up configuration values from `ps_configuration`. |

### 4.8 Main Module File (`masspricefree/index.php`)

The core logic resides in `masspricefree/index.php`.

- **Class Name:** `MassPriceFree`
- **Parent Class:** `Module`
- **Key Methods:**
  - `__construct()`: Initializes module properties (name, tab, version, author, need\_instance, bootstrap).
  - `install()`: Registers the module, sets default configuration values (e.g., `PS_MASS_PRICE_FREE_TYPE` to ‘increase’, `PS_MASS_PRICE_FREE_VALUE` to ‘0’).
  - `uninstall()`: Deletes configuration values.
  - `getContent()`: This is the primary method for the module’s functionality.
    - Handles form submission (`Tools::isSubmit('submitMassPriceFree')`).
    - Retrieves `price_type` and `price_value` from the submitted form.
    - Updates `ps_configuration` with the new settings.
    - **Crucially, it iterates through all active products (`Product::getProducts(Context::getContext()->language->id, 0, 0, 'id_product', 'ASC', false, true)`) and updates their prices based on the configured percentage and type.** It uses `Product::updatePrice()` for this.
    - Renders the configuration form using `displayForm()` and includes the `advert.tpl` and `script.tpl` templates.
  - `displayForm()`: Generates the HTML for the module’s configuration form, including the radio buttons for increase/decrease and the input field for the percentage.

## 5. Official Support & Updates

For official updates, bug fixes, and dedicated support for the “Free mass products prices update” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality.
