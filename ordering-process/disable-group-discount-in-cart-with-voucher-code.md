---
title: "Disable group discount in cart with voucher code - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Disable group discount in cart with voucher code PrestaShop module by MyPresta.eu."
sidebar:
  label: "Disable group discount in cart with voucher code - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Disable group discount in cart with voucher code Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-group-discount-in-cart-with-voucher-code.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/disable-group-discount-in-cart-with-voucher-code/)
>
> ---


# Disable group discount in cart with voucher code

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the module name to access its settings.

#### Setting: Disable groups discount in cart with cart rule

This is the main control switch for the module’s functionality.

- **What this setting does:** This setting determines whether the module actively intervenes to disable group discounts when a voucher code is present in the cart.
- **Effect of changing this setting:**
  - ***When Enabled:*** If a customer belongs to a group with a special discount (e.g., 10% off for “Wholesale Customers”) AND they apply a voucher code (cart rule) to their cart, the group discount will be ignored. Only the voucher discount will be applied to the order total. This prevents the customer from receiving both discounts simultaneously.
  - ***When Disabled:*** The module will not intervene. PrestaShop’s default behavior will apply, meaning if a customer is eligible for both a group discount and a voucher discount, both might be applied, potentially stacking the discounts.
- **Recommended value:** **Enabled**. This is the core functionality of the module and is generally recommended to prevent unintended discount stacking and protect your profit margins during voucher campaigns.
- **Merchant scenario / example:**
  - *Scenario 1 (Enabled):* You have a “VIP Customers” group that gets 5% off all products. You also run a “SUMMER20” voucher code for 20% off. A VIP customer adds items to their cart and applies “SUMMER20”. With the module **Enabled**, they will only get the 20% off from the voucher, not 5% + 20%.
  - *Scenario 2 (Disabled):* Using the same example, if the module is **Disabled**, the VIP customer might receive both the 5% group discount and the 20% voucher discount, leading to a 25% total discount (or a more complex calculation depending on PrestaShop’s internal discount application order).

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Disable groups discount in cart with cart rule | Enabled | When enabled, group discounts are ignored if a voucher code is present in the cart, ensuring only the voucher discount is applied. Prevents discount stacking. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I enabled the module, but customers are still getting both discounts. What’s wrong?**
A1: First, ensure the module is indeed “Enabled” in its configuration. Second, clear your PrestaShop cache (Go to **Advanced Parameters > Performance**, then click “Clear cache” in the top right). Sometimes, old cache data can prevent changes from taking effect immediately. Also, test with a fresh cart and a new customer session (e.g., in an incognito browser window).

**Q2: Will this module affect my specific prices or catalog price rules?**
A2: No, this module specifically targets *group discounts* and *cart rules (voucher codes)*. It does not interfere with specific prices set for individual products, product combinations, or catalog price rules that apply based on quantity or other conditions. It only modifies the interaction between customer group discounts and voucher codes.

**Q3: Does this module work with all types of voucher codes (percentage, fixed amount, free shipping)?**
A3: Yes, the module’s logic is designed to detect the presence of *any* active cart rule (voucher code) in the cart. Once a cart rule is detected, it will then disable the group discount, regardless of the type of discount the voucher provides (percentage, fixed amount, free shipping, etc.).

**Q4: What if I want to allow group discounts AND a voucher code for a specific promotion?**
A4: If you have a specific promotion where you *do* want to allow both discounts to stack, you would need to temporarily **Disable** this module in its configuration. Remember to re-enable it once that specific promotion is over if you want to revert to the “voucher-only” discount behavior.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

This module primarily functions through an override of a core PrestaShop class. Instead of using hooks, it directly modifies the behavior of the `Product` class to adjust how prices are calculated when a customer group discount is involved and a cart rule is active. This approach ensures that the discount logic is applied at a fundamental level during product price retrieval.

### 4.2 Controllers (`controllers/`)

- This module does not include any custom front-office or back-office controllers. Its functionality is implemented via class overrides.

### 4.3 Core Classes & Models (`classes/`)

- **File Path**: `exgcr/override/classes/Product.php`

  - **Class Name**: `Product` (overrides the core `Product` class)
  - **Parent Class**: `ProductCore`
  - **Responsibility**: This override modifies the `getPriceStatic` method of the `Product` class. The `getPriceStatic` method is crucial as it’s responsible for calculating the final price of a product, taking into account various factors like taxes, specific prices, customer groups, and cart rules.
  - **Key Logic**:
    - The override checks if the module `exgcr` is enabled.
    - It then checks if there is an active `CartRule` (voucher code) applied to the current cart.
    - If both conditions are met (module enabled AND voucher present), it modifies the parameters passed to the parent `getPriceStatic` method to effectively ignore the customer group discount. Specifically, it sets the `$use_group_reduction` parameter to `false` when calling the parent method, thereby preventing the group discount from being applied.
    - This ensures that when a voucher is in use, the price calculation proceeds as if the customer does not belong to a discounted group, thus preventing the stacking of group discounts with voucher discounts.
- **File Path**: `exgcr/override/classes/index.php`

  - **Purpose**: This is a standard empty `index.php` file placed in directories to prevent directory listing (security measure). It contains no functional code.

### 4.4 JavaScript Assets (`views/js/`)

- This module does not include any custom JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)

- This module does not include any custom CSS files.

### 4.6 Smarty Template Structure (`views/templates/`)

- This module does not include any custom Smarty template files. Its configuration is handled directly within the `getContent()` method of the main module file.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create any custom database tables.
  - It stores its configuration setting (`exgcr`) in the standard `ps_configuration` table.
    - `PS_CONFIGURATION` entry: `EXGCR_ENABLED` (stores `1` for enabled, `0` for disabled).
- **Registered Hooks Table**:

  - This module does not register any specific hooks in the `ps_hook_module` table. Its functionality is implemented through a class override, which is a more direct way to modify core behavior without relying on hook execution.

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the “Disable group discount in cart with voucher code” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and integration with your PrestaShop store.
