---
title: "Exclude group discount from products with specific price - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Exclude group discount from products with specific price PrestaShop module by MyPresta.eu."
sidebar:
  label: "Exclude group discount from products with specific price - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Exclude group discount from products with specific price Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/exclude-group-discount-from-products-with-specific-price.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/exclude-group-discount-from-products-with-specific-price/)
>
> ---


# Exclude group discount from products with specific price

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No unusual server configurations are required.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, navigate to **Modules > Module Manager**, find “Exclude group discount from products with specific price”, and click **Configure**. You will see the main configuration screen.

#### Setting: Disable groups discount for products with specific prices

- **What this setting does:** This is the core control for the module’s functionality. It determines whether the module should actively prevent group discounts from applying to products that already have specific prices.
- **Effect of changing this setting:**
  - **When set to “Enabled”:** If a product has a specific price (e.g., a special sale price you’ve set), and a customer from a group that normally receives a discount (e.g., “VIP Customers” get 10% off) views or buys that product, the 10% group discount will *not* be applied. The customer will pay the specific price you set. This is the module’s intended behavior.
  - **When set to “Disabled”:** The module will be inactive. PrestaShop’s default behavior will resume. This means if a product has a specific price, and a customer from a discounted group views or buys it, *both* the specific price and the group discount will be applied, potentially leading to a much lower final price than intended.
- **Recommended value:** **Enabled**. This is the purpose of the module, to prevent unintended stacking of discounts.
- **Merchant scenario / example:** You have a “Summer Sale” where a specific T-shirt is priced at $15 (down from $25). You also have a “Wholesale” customer group that gets 20% off all orders.
  - If this setting is **Enabled**: A wholesale customer buys the T-shirt. They pay $15. The 20% wholesale discount is ignored for this specific product.
  - If this setting is **Disabled**: A wholesale customer buys the T-shirt. PrestaShop first applies the specific price ($15), then applies the 20% wholesale discount to $15, making the final price $12. This might be lower than your desired profit margin.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Disable groups discount for products with specific prices | Enabled | Controls whether group discounts are prevented from stacking with specific prices. **Enabled** prevents stacking, preserving profit margins. **Disabled** allows stacking, potentially leading to lower prices. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve enabled the module, but group discounts are still applying to my specific prices. What’s wrong?**
A:

1. **Clear Cache:** Always clear your PrestaShop cache after making configuration changes. Go to **Advanced Parameters > Performance**, then click “Clear cache” in the top right.
2. **Module Order:** In rare cases, another module might be overriding price calculations. If you have other pricing or discount modules, try temporarily disabling them one by one to see if there’s a conflict.
3. **Specific Price Setup:** Double-check that your “specific prices” are correctly configured for the products in question. Go to the product edit page, then the “Pricing” tab, and ensure the specific price is active and correctly applied.
4. **Group Discount Setup:** Verify that the customer group discount is correctly set up under **Shop Parameters > Customer Settings > Groups**.

**Q: Will this module affect my regular cart rules or coupon codes?**
A: No, this module specifically targets “group discounts” (discounts applied automatically based on a customer’s assigned group) and their interaction with “specific prices” (manual price overrides for a product). It does not interfere with PrestaShop’s cart rules, coupon codes, or other promotional mechanisms unless those mechanisms are themselves based on specific prices or group discounts.

**Q: Does this module slow down my store?**
A: No, the module is very lightweight. It works by overriding a core PrestaShop class (`Product.php`) to modify how prices are calculated. This is a highly optimized process and should not introduce any noticeable performance degradation.

**Q: What if I want group discounts to *sometimes* apply to specific prices?**
A: This module offers an “all or nothing” approach: either group discounts are excluded from *all* products with specific prices, or they are not. If you need more granular control (e.g., exclude for Product A but allow for Product B, both with specific prices), this module alone won’t achieve that. You would need to manage specific prices and group discounts manually or consider a more advanced pricing module. For this module, the recommendation is to enable it to prevent unintended stacking.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The `Exclude group discount from products with specific price` module implements its core functionality through an override of the `Product` class. This is a common and effective PrestaShop development pattern for modifying core behaviors without directly altering core files. By overriding `Product::getPriceStatic()`, the module intercepts the price calculation logic to prevent group-specific discounts from being applied when a product has an active specific price.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. All front-office logic is handled via the `Product` class override.
- **Back-Office Admin Controllers**: None. The module’s configuration is handled directly within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

The module’s primary functionality resides in its class override.

- **File Path**: `exgdis/override/classes/Product.php`
- **Class Name**: `Product` (overrides the core `Product` class)
- **Parent Class**: `ProductCore`
- **Responsibility**: This override modifies the `getPriceStatic()` method, which is central to how PrestaShop calculates product prices throughout the front office (product pages, cart, checkout) and back office.
  - **Key Logic**: Inside the overridden `getPriceStatic()` method, the module checks if its configuration setting `exgdis_groups` (which corresponds to “Disable groups discount for products with specific prices”) is enabled.
  - If enabled, and if the product currently being priced has an active specific price, the module ensures that the `$use_group_reduction` parameter passed to the original `ProductCore::getPriceStatic()` method is set to `false`. This effectively tells PrestaShop *not* to apply any group-specific discounts for that particular price calculation.
  - The `index.php` file in `override/classes/` is a standard empty file to prevent directory listing.

### 4.4 JavaScript Assets (`views/js/`)

- None. The module has no front-end or back-end JavaScript components.

### 4.5 CSS Stylesheets (`views/css/`)

- None. The module has no custom CSS styling.

### 4.6 Smarty Template Structure (`views/templates/`)

- None. The module’s configuration is rendered directly via `getContent()` in the main module file, and its functionality is purely logic-based, not display-based.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: The module does not create any custom database tables. It stores its configuration in the `ps_configuration` table.

  - `ps_configuration` entry: `exgdis_groups` (stores the enabled/disabled status of the main setting).
- **Registered Hooks Table**: The module does not explicitly register any hooks in the `ps_hook_module` table. Its functionality is implemented via a class override, which is loaded by PrestaShop’s override mechanism.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `override/classes/Product.php` | During `Product::getPriceStatic()` calls | Intercepts price calculation to prevent group discounts on products with specific prices. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Exclude group discount from products with specific price” module, please refer to your MyPresta.eu customer account. You can download the newest versions and access support resources directly from [MyPresta.eu](https://mypresta.eu).
