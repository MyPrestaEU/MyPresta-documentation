---
title: "Shipping methods (carriers) from the most expensive product - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Shipping methods (carriers) from the most expensive product PrestaShop module by MyPresta.eu."
sidebar:
  label: "Shipping methods (carriers) from the most expensive product - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Shipping methods (carriers) from the most expensive product Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/shipping-methods-carriers-from-the-most-expensive-product.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/shipping-methods-carriers-from-the-most-expensive-product/)
>
> ---


# Shipping methods (carriers) from the most expensive product

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the module name to access its settings.

#### **Enable / Disable Module**

- **What this setting does:** This is the main switch to activate or deactivate the module’s core functionality.
- **Effect of changing this setting:**
  - *When enabled:* The module will modify PrestaShop’s default carrier selection logic, ensuring that only carriers associated with the most expensive product in the cart are displayed during checkout.
  - *When disabled:* PrestaShop will revert to its default behavior, where carriers are only shown if they can ship *all* products in the cart.
- **Recommended value:** “Enabled” if you want to use the module’s functionality.
- **Merchant scenario / example:** If you’re testing the module or temporarily want to revert to default PrestaShop behavior without uninstalling, you can disable it here.

#### **How to get carriers?**

- **What this setting does:** This crucial setting defines *how* the module identifies the “most expensive product” and subsequently determines the available carriers. It offers two distinct methods.
- **Effect of changing this setting:**
  - *When set to “From the most expensive product (by price)”:* The module will calculate the total price of each unique product in the cart (quantity \* unit price) and identify the product with the highest total price. The carriers associated with *that specific product* will then be used to filter the available shipping options.
  - *When set to “From the most expensive product (by price) - FREE SHIPPING”:* This option works similarly to the first, but it also considers if the most expensive product qualifies for free shipping. If the most expensive product has free shipping enabled, then free shipping options will be prioritized or made available according to your carrier settings.
  - *When set to “From the most expensive product (by price) - COST”:* This option also identifies the most expensive product by price, but it specifically focuses on the *cost* associated with shipping that product. It ensures that the shipping costs and options presented are directly tied to the most expensive item’s shipping configuration.
- **Recommended value:**
  - “From the most expensive product (by price)” is the most common and recommended choice for general use, as it directly implements the module’s core promise.
  - Choose “From the most expensive product (by price) - FREE SHIPPING” if you frequently offer free shipping on high-value items and want this to be a primary consideration in carrier selection.
  - Choose “From the most expensive product (by price) - COST” if you have complex shipping cost rules tied to specific high-value products and want those rules to dictate the available carriers.
- **Merchant scenario / example:**
  - You sell a $1000 TV and a $10 remote. If the TV is configured with specific carriers (e.g., insured freight) and the remote with standard postal service, choosing “From the most expensive product (by price)” will ensure the TV’s carriers are shown.
  - If your $1000 TV comes with free shipping, selecting “From the most expensive product (by price) - FREE SHIPPING” would ensure that free shipping options are presented if available for the TV.

#### **Configuration Quick Reference Table**

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Enable / Disable Module | Enabled | Activates/deactivates the module’s logic for carrier selection based on the most expensive product. |
| Module Configuration Page | How to get carriers? | From the most expensive product (by price) | Defines the method for identifying the “most expensive product” and its associated carriers. Options: “by price”, “by price - FREE SHIPPING”, “by price - COST”. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve enabled the module, but I’m still seeing the old carrier options or no carriers at all.**
A:

1. **Clear Cache:** Always clear your PrestaShop cache after making module configuration changes. Go to **Advanced Parameters > Performance** and click “Clear cache” in the top right.
2. **Check Product Carrier Associations:** Ensure that your products, especially your most expensive ones, are correctly associated with the desired carriers in their product settings (**Catalog > Products > Edit Product > Shipping tab**).
3. **Verify Module is Enabled:** Double-check that the “Enable / Disable Module” setting is set to “Enabled” in the module’s configuration.
4. **Theme Compatibility:** While rare for this type of module, a highly customized theme might interfere. Temporarily switch to the default PrestaShop theme to rule this out.

**Q: How does the module handle two products with the exact same highest price?**
A: In cases where two or more products share the exact highest price, the module will typically select one of them based on internal PrestaShop product ID order or the order they were added to the cart. It will then use the carriers associated with that selected product. For consistency, it’s best to ensure your carrier configurations are robust enough to cover similar high-value items.

**Q: Does this module affect shipping costs or only carrier availability?**
A: This module primarily affects *carrier availability*. It determines *which* carriers are shown. The actual shipping costs for the chosen carrier will still be calculated by PrestaShop’s standard mechanisms (based on weight, price, zone, etc.) for the *entire cart*, but only for the carriers that are made available by this module’s logic.

**Q: What if the most expensive product has no carriers associated with it?**
A: If the most expensive product in the cart has no carriers explicitly associated with it in its product settings, then no carriers will be displayed during checkout, potentially leading to a “no shipping method available” message. Always ensure your high-value products have appropriate carriers assigned.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Shipping methods (carriers) from the most expensive product” module achieves its functionality by overriding a core PrestaShop class, `Cart`. This is a common and powerful method in PrestaShop for altering fundamental behaviors without modifying core files directly. By overriding `Cart::getAvailableCarriers()`, the module injects its custom logic to filter carriers based on the most expensive product, rather than the default “all products must be compatible” rule.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. The module operates by overriding a core class, not by introducing new front-office routes or pages.
- **Back-Office Admin Controllers**: None. The module’s configuration is handled directly within the main module class’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

The module’s core logic resides in an override of the `Cart` class.

- **`cfep/override/classes/Cart.php`**

  - **Class name**: `Cart` (overrides `PrestaShop\Classes\Cart\Cart` or `CartCore` depending on PrestaShop version and context).
  - **Parent class**: `CartCore`
  - **Responsibility**: This file contains the overridden `getAvailableCarriers()` method. This method is crucial for determining which shipping carriers are presented to the customer during checkout. The override introduces the logic to:
    1. Identify the most expensive product in the current cart based on the module’s configuration (`CFEP`, `CFEP_FREE`, `CFEP_COST`).
    2. Retrieve the carriers specifically associated with this most expensive product.
    3. Filter the list of all available carriers to only include those compatible with the most expensive product.
    4. Return this filtered list of carriers.
  - **Key public methods**:
    - `getAvailableCarriers(bool $return_full_list = false, int $id_zone = null, bool $use_cache = true)`: This is the overridden method. It extends the original `CartCore::getAvailableCarriers` to implement the custom carrier filtering logic. It first calls the parent method to get all potentially available carriers, then applies its own filtering based on the most expensive product.
- **`cfep/override/classes/index.php`**

  - **Responsibility**: This is a standard empty `index.php` file, typically placed in directories to prevent directory listing when accessed directly via a web browser. It has no functional impact on the module’s logic.

### 4.4 JavaScript Assets (`views/js/`)

- None. The module does not add any custom JavaScript to the front or back office.

### 4.5 CSS Stylesheets (`views/css/`)

- None. The module does not add any custom CSS to the front or back office.

### 4.6 Smarty Template Structure (`views/templates/`)

- None. The module does not use any custom Smarty templates. Its configuration interface is generated dynamically by `getContent()` in the main module file.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  The module does not create any custom database tables. It stores its configuration settings in the standard `ps_configuration` table.

  - `ps_configuration` entries:
    - `CFEP`: Stores the selected method for getting carriers (e.g., ‘price’, ‘free’, ‘cost’).
    - `mypresta_updates`: Used for internal MyPresta.eu update checks.
    - `update_`: Used for internal MyPresta.eu update checks.
    - `updatev_`: Used for internal MyPresta.eu update checks.
- **Registered Hooks Table**:
  The module does not explicitly register any hooks in the `ps_hook_module` table. Its functionality is implemented through a class override, which is a more direct way to alter core PrestaShop behavior without relying on specific hook execution points.

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the “Shipping methods (carriers) from the most expensive product” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
