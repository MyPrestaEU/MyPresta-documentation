---
title: "Disable product specific prices when cart has cart rule - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Disable product specific prices when cart has cart rule PrestaShop module by MyPresta.eu."
sidebar:
  label: "Disable product specific prices when cart has cart rule - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Disable product specific prices when cart has cart rule Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-product-specific-prices-when-cart-has-cart-rule.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/disable-product-specific-prices-when-cart-has-cart-rule/)
>
> ---


# Disable product specific prices when cart has cart rule

## 1. Requirements & Compatibility

This module is designed to work seamlessly with modern PrestaShop installations.

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required for PrestaShop itself and are typically available on any modern web hosting environment. No special hosting requirements beyond a standard PrestaShop setup.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

This module has a single, simple configuration screen.

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

To access the configuration, navigate to **Modules > Module Manager**, search for “Disable product specific prices when cart has cart rule”, and click the “Configure” button.

![Module Configuration Screenshot Placeholder]
*(Imagine a screenshot here showing a simple form with a single toggle switch labeled “Disable specific prices usage in cart with cart rule” and “Enabled” / “Disabled” options.)*

**Setting: Disable specific prices usage in cart with cart rule**

- **What this setting does:** This is the main control switch for the module’s core functionality. It determines whether the module actively intervenes to disable specific prices when a cart rule (voucher code) is present in the customer’s cart.
- **Effect of changing this setting:**
  - **When enabled (YES):** If a customer applies any cart rule (voucher code) to their cart, the module will prevent any product-specific prices from being applied to the products in that cart. The product prices will revert to their base price before the cart rule discount is applied, ensuring that only the cart rule’s discount affects the final price. This prevents double-discounting.
  - **When disabled (NO):** The module will be inactive. Specific prices and cart rules will function independently, meaning they can potentially stack on the same product, leading to multiple discounts being applied simultaneously. This is the default PrestaShop behavior.
- **Recommended value:** **Enabled (YES)**. This is the primary purpose of the module and enables you to protect your profit margins and control your discount strategy.
- **Merchant scenario / example:**
  - **Choose “Enabled”** if you want to ensure that when a customer uses a voucher code (e.g., “SAVE10” for 10% off), any existing specific prices on products in their cart are ignored. This means the 10% discount will be applied to the product’s regular price, not an already discounted specific price. This prevents a product from being discounted twice.
  - **Choose “Disabled”** if you prefer the default PrestaShop behavior where specific prices and cart rules can stack, potentially leading to deeper discounts than intended. This might be desired in very specific, aggressive promotional campaigns, but generally, “Enabled” is recommended for profit protection.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Disable specific prices usage in cart with cart rule | Enabled | When enabled, specific prices are ignored if a cart rule is active in the cart, preventing double discounts. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I enabled the module, but specific prices are still showing even with a voucher code. What’s wrong?**

- **A:** First, ensure you’ve saved the configuration after enabling the module.
- **A:** Clear your PrestaShop cache. Go to **Advanced Parameters > Performance**, and click “Clear cache” in the top right.
- **A:** Test with a fresh cart. Sometimes browser cache or session data can interfere. Try in an incognito window.
- **A:** Verify that the cart rule you’re testing with is actually active and correctly applied to the products in the cart.

**Q2: My customers are complaining that their specific prices disappeared when they used a voucher. Is this expected?**

- **A:** Yes, this is the intended behavior of the module. When the module is enabled, and a customer applies a cart rule (voucher), the specific prices on products in the cart are temporarily disabled to prevent double-discounting. The product’s price will then be calculated based on its original price, with the cart rule discount applied. You might want to update your terms and conditions or promotional messages to clarify how discounts interact.

**Q3: Does this module affect other types of discounts, like category discounts or customer group discounts?**

- **A:** This module specifically targets “specific prices” (discounts set directly on individual products or combinations) and their interaction with “cart rules” (voucher codes). It does not directly interfere with other discount mechanisms like category discounts, customer group discounts, or quantity discounts, unless those are implemented as specific prices.

**Q4: Will this module slow down my store?**

- **A:** The module makes minor overrides to core PrestaShop classes to adjust price calculation logic. These changes are highly optimized and should have a negligible impact on your store’s performance. The module only activates its logic when a cart rule is present, so it’s not constantly running.

**Q5: I want to temporarily allow specific prices and cart rules to stack for a special promotion. How do I do that?**

- **A:** Simply go to the module’s configuration page (**Modules > Module Manager > Configure** for “Disable product specific prices when cart has cart rule”) and set the “Disable specific prices usage in cart with cart rule” option to **“Disabled”**. Remember to re-enable it after your special promotion ends to restore the default protective behavior.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters working with the “Disable product specific prices when cart has cart rule” module.

### 4.1 Architecture Overview

This module primarily functions by overriding core PrestaShop classes related to price calculation and specific price management. It leverages PrestaShop’s override mechanism to inject its logic into the `Cart`, `Product`, and `SpecificPrice` classes. The core idea is to detect the presence of a cart rule in the current cart and, if found, modify the behavior of specific price retrieval to effectively ignore them during price calculations.

The module’s main configuration is handled via the `getContent()` method in the main module file, storing a simple boolean flag in `ps_configuration`.

### 4.2 Controllers (`controllers/`)

This module does not introduce any custom front-office or back-office controllers. Its logic is entirely embedded within class overrides.

- **Front-Office Controllers**: None
- **Back-Office Admin Controllers**: None

### 4.3 Core Classes & Models (`classes/`)

The module’s core functionality resides in its class overrides. These files are located in `cartspecdis/override/classes/`. PrestaShop automatically loads these overrides, replacing the original core classes with the module’s modified versions.

- **`cartspecdis/override/classes/Cart.php`**

  - **Class Name & Parent Class**: `Cart` (overrides `\Cart`)
  - **Responsibility**: This override is crucial. It likely introduces a method or modifies an existing one (e.g., `getProducts()`, `getPackageList()`, or a price calculation helper) to check for the presence of cart rules. If cart rules are found, it sets a flag or modifies parameters that influence how specific prices are later retrieved or applied. The `hasCartRules()` method is a likely candidate for checking cart rules.
  - **Key Logic**: The override will likely add a check within price calculation methods to see if `Cart::getCartRules()` returns any active rules. If so, it will then influence the `Product::getPriceStatic()` or `SpecificPrice::getSpecificPrice()` calls to ignore specific prices.
- **`cartspecdis/override/classes/Product.php`**

  - **Class Name & Parent Class**: `Product` (overrides `\Product`)
  - **Responsibility**: This override is expected to modify the `getPriceStatic()` method, which is central to how product prices are retrieved throughout PrestaShop.
  - **Key Logic**: Inside `getPriceStatic()`, the module will likely add a condition. If the current `Cart` object (passed as a parameter or accessible globally) contains active cart rules, and the module’s configuration is enabled, then the parameters passed to `SpecificPrice::getSpecificPrice()` will be altered (e.g., `id_specific_price` or `use_specific_price` flags) to ensure no specific price is returned, or the specific price calculation is bypassed.
- **`cartspecdis/override/classes/SpecificPrice.php`**

  - **Class Name & Parent Class**: `SpecificPrice` (overrides `\SpecificPrice`)
  - **Responsibility**: This override is likely to modify the `getSpecificPrice()` method, which is responsible for fetching specific price details for a given product.
  - **Key Logic**: This override will contain the direct logic to prevent specific prices from being returned. It will check if the current `Cart` has cart rules and if the module is enabled. If both conditions are true, `getSpecificPrice()` will be made to return `false` or an empty array, effectively indicating that no specific price applies, even if one exists in the database. This is the final gatekeeper for specific prices.
- **`cartspecdis/override/classes/index.php`**

  - **Class Name & Parent Class**: None
  - **Responsibility**: This is a standard empty `index.php` file, typically placed in directories to prevent directory listing when accessed directly via a web browser. It has no functional impact on the module’s logic.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include any custom JavaScript files. All its logic is handled server-side.

### 4.5 CSS Stylesheets (`views/css/`)

This module does not include any custom CSS files. It has no front-office visual components and its back-office configuration uses standard PrestaShop form elements.

### 4.6 Smarty Template Structure (`views/templates/`)

This module does not use any custom Smarty templates. Its configuration form is generated dynamically by the `getContent()` method in the main module file using PrestaShop’s helper forms.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any custom SQL tables.
  - It stores its configuration setting in the `ps_configuration` table:
    - `PS_CONFIGURATION` key: `cartspecdis` (stores the boolean value for enabling/disabling the module’s core functionality).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Executed when an Admin Controller is setting up its media assets (CSS/JS). | This hook is typically used by modules to add their own CSS or JavaScript files to the Back Office. For this module, it’s likely used to ensure any necessary admin-side styling or scripts (though none are explicitly listed in the inventory) are loaded, or it might be a remnant from a template module structure. Given no JS/CSS files are listed, its primary purpose here is likely minimal or for future expansion. |

### 4.8 Main Module File (`cartspecdis/cartspecdis.php`)

- **Class Name**: `Cartspecdis` (extends `Module`)
- **`__construct()`**: Initializes module metadata (name, tab, version, author, need\_instance, ps\_versions\_compliancy).
- **`install()`**:
  - Calls `parent::install()`.
  - Registers the `actionAdminControllerSetMedia` hook.
  - Sets the default configuration value for `cartspecdis` to `1` (enabled) in `ps_configuration`.
  - Registers the class overrides (`Cart`, `Product`, `SpecificPrice`).
- **`uninstall()`**:
  - Calls `parent::uninstall()`.
  - Unregisters the `actionAdminControllerSetMedia` hook.
  - Deletes the `cartspecdis` configuration value from `ps_configuration`.
  - Unregisters the class overrides.
- **`getContent()`**:
  - Handles form submission for the module’s configuration.
  - Updates the `cartspecdis` configuration value in `ps_configuration` based on user input.
  - Displays a confirmation message.
  - Renders the configuration form using PrestaShop’s `HelperForm` class, including the single toggle switch for “Disable specific prices usage in cart with cart rule”.
- **`hookActionAdminControllerSetMedia()`**:
  - This method is called when the `actionAdminControllerSetMedia` hook is executed.
  - It’s typically used to add CSS or JavaScript files to the Back Office. In this module’s current state (based on the inventory), it likely contains minimal or no active code for adding assets, or it’s a placeholder.

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Disable product specific prices when cart has cart rule” module, please refer to your customer account at MyPresta.eu.

- **Module Updates**: Log in to your MyPresta.eu account and navigate to your order history and downloads section to get the most recent version of the module.
- **Technical Support**: If you encounter any issues or have questions that are not covered in this documentation, please open a support ticket through your MyPresta.eu customer account. Our team will be happy to assist you.
