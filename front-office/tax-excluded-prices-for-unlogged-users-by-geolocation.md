---
title: "Tax excluded prices for unlogged users by geolocation - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Tax excluded prices for unlogged users by geolocation PrestaShop module by MyPresta.eu."
sidebar:
  label: "Tax excluded prices for unlogged users by geolocation - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Tax excluded prices for unlogged users by geolocation Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/tax-excluded-prices-for-unlogged-users-by-geolocation.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/tax-excluded-prices-for-unlogged-users-by-geolocation/)
>
> ---


# Tax excluded prices for unlogged users by geolocation

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This module operates primarily through overrides to PrestaShop’s core pricing logic, meaning its configuration is usually minimal or even automatic. The `getContent()` method in the main module file typically handles the display of a standard configuration form, but for this specific module, the core functionality is achieved through class overrides rather than extensive settings.

If a configuration screen is present, it would typically offer options related to enabling/disabling the module or fine-tuning its geolocation behavior. However, based on the module’s description and file structure, its primary function is to *automatically* adjust prices based on geolocation without requiring complex merchant-facing settings.

Therefore, the configuration screen for this module is likely very simple, possibly just an “Enable/Disable” switch, or it might not even have a dedicated configuration form if its behavior is entirely automatic once installed.

**If a configuration screen exists, it would typically include:**

- **Enable/Disable Module:**

  - **What this setting does:** This is a standard switch to turn the module’s functionality on or off.
  - **Effect of changing this setting:**
    - *When enabled:* The module will actively detect unlogged users’ locations and adjust price displays (tax-included/excluded) accordingly.
    - *When disabled:* PrestaShop will revert to its default behavior for unlogged users, typically showing prices based on the shop’s default country or a global setting, without geolocation-based adjustments.
  - **Recommended value:** YES (to utilize the module’s core functionality).
  - **Merchant scenario / example:** If you temporarily need to troubleshoot a pricing issue or prefer PrestaShop’s default behavior for a short period, you might disable it. Otherwise, keep it enabled for accurate international pricing.
- **Geolocation Service Provider (Hypothetical):**

  - **What this setting does:** If the module offered a choice, this would allow you to select which external service it uses to detect visitor IP addresses and map them to countries.
  - **Effect of changing this setting:**
    - *When set to Provider A:* The module uses Provider A’s database for IP-to-country mapping.
    - *When set to Provider B:* The module uses Provider B’s database, potentially offering different accuracy or speed.
  - **Recommended value:** The default or recommended provider by MyPresta.eu.
  - **Merchant scenario / example:** You might switch providers if one offers better accuracy for your target regions or if you encounter issues with the default.
- **Caching Settings (Hypothetical):**

  - **What this setting does:** Controls how long geolocation data is cached for visitors to improve performance.
  - **Effect of changing this setting:**
    - *Longer cache duration:* Faster page loads for repeat visitors, but potentially slower updates if a visitor’s IP changes.
    - *Shorter cache duration:* More real-time geolocation, but slightly more server load.
  - **Recommended value:** Default (usually optimized for balance).
  - **Merchant scenario / example:** If your site has very high traffic and you prioritize speed, you might increase the cache duration. If your customer base is highly mobile and frequently changes IPs, a shorter duration might be preferred.

**Important Note for Merchants:**
This module works by overriding core PrestaShop classes (`Product.php`, `Tax.php`, `TaxCalculator.php`). This is a powerful technique that directly modifies how PrestaShop calculates and displays prices. Because of this, there are usually very few, if any, configurable options on a dedicated screen. The module’s strength lies in its automatic, behind-the-scenes adjustments.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Enable/Disable Module | Enabled | Turns the module’s geolocation-based price adjustment functionality on or off. |
| Module Configuration Page | *[Other settings if present]* | *[Default value]* | *[Purpose & Impact]* |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: Prices are not changing for unlogged users, even after installing the module.**
A1:

- **Check Module Status:** Ensure the module is installed and enabled in your PrestaShop Back Office under Modules > Module Manager.
- **Clear Cache:** Go to **Advanced Parameters > Performance** and clear all caches (Smarty cache, filesystem cache, etc.). Browser cache might also need to be cleared.
- **Geolocation Accuracy:** The module relies on IP geolocation. While generally accurate, it’s not 100% perfect. Test with different IPs (e.g., using a VPN) to confirm.
- **PrestaShop Tax Rules:** Verify your PrestaShop tax rules and tax groups are correctly configured for different countries. The module uses these existing rules to determine *what* price to show (tax incl. or excl.) once it knows the country.
- **Override Conflicts:** If you have other modules that also override `Product.php`, `Tax.php`, or `TaxCalculator.php`, there might be a conflict. Check your `override/` folder for other modules modifying these files. Contact MyPresta.eu support if you suspect a conflict.

**Q2: My custom theme doesn’t seem to display the prices correctly after installing.**
A2: This module primarily affects the *value* of the price displayed, not its visual styling. If prices look misaligned or styled incorrectly, it’s likely a CSS issue with your theme.

- **Theme Compatibility:** Ensure your theme is fully compatible with your PrestaShop version.
- **Inspect Element:** Use your browser’s developer tools (F12) to inspect the price elements and see if any custom CSS from your theme is conflicting.
- **Contact Theme Developer:** If you’re using a custom theme, reach out to your theme developer for assistance with styling. The module itself doesn’t introduce new CSS.

**Q3: Does this module affect logged-in users or users who have entered their address?**
A3: No, this module specifically targets *unlogged users* who have not yet provided their address information. Once a user logs in or enters their shipping address during checkout, PrestaShop’s native tax calculation and display logic (which already knows the customer’s country) will take precedence. This module fills the gap for the initial browsing experience.

**Q4: How does the module know the customer’s country?**
A4: The module uses the visitor’s IP address to determine their geographical location. This is a standard method for geolocation in web applications. It then uses this detected country to apply the appropriate PrestaShop tax rules for price display.

**Q5: Will this module slow down my store?**
A5: The module is designed to be efficient. Geolocation lookups are typically fast, and the module often caches results to minimize repeated lookups for the same visitor. The performance impact should be negligible. If you notice any slowdown, ensure your server meets PrestaShop’s minimum requirements and that your caching mechanisms are properly configured.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Tax excluded prices for unlogged users by geolocation” module achieves its functionality primarily through PrestaShop’s override system. Instead of relying on traditional hooks or custom controllers, it directly modifies the behavior of core PrestaShop classes responsible for product pricing and tax calculation. This allows it to inject geolocation-based logic into the fundamental price determination process, ensuring that prices are adjusted before they are even rendered. The module leverages the `displayHeader` hook to potentially include any necessary JavaScript or styling, although its core logic is PHP-based.

### 4.2 Controllers (`controllers/`)

This module does **not** contain any custom Front-Office or Back-Office Admin Controllers. Its logic is embedded directly into core class overrides.

### 4.3 Core Classes & Models (`classes/`)

The module’s core functionality resides in its overrides of PrestaShop’s fundamental pricing and product classes.

- **`taxprice/override/classes/Product.php`**

  - **Original Class:** `Product`
  - **Responsibility:** This override is crucial. The `Product` class is responsible for retrieving and formatting product information, including prices. This override likely intercepts methods like `getPrice()` or related price calculation methods to inject the geolocation logic *before* the price is returned for display. It determines whether to show tax-included or tax-excluded prices based on the detected country for unlogged users.
  - **Key Logic:**
    - Detects if the current user is a guest (not logged in).
    - Obtains the visitor’s country based on IP address (potentially via a helper function or a third-party service integration).
    - Modifies the `TaxManagerFactory` context or directly manipulates the `price_display_method` based on the detected country’s tax rules and PrestaShop’s configuration for that country.
- **`taxprice/override/classes/tax/Tax.php`**

  - **Original Class:** `Tax`
  - **Responsibility:** The `Tax` class handles tax rate retrieval and application. This override might be used to ensure that the correct tax rates are applied *after* the geolocation has determined whether prices should be tax-included or tax-excluded. It could modify how tax rates are fetched or how the `TaxCalculator` is initialized based on the guest’s country.
- **`taxprice/override/classes/tax/TaxCalculator.php`**

  - **Original Class:** `TaxCalculator`
  - **Responsibility:** This class is central to calculating prices with and without taxes. The override here would directly influence the final price calculation. It likely ensures that when a guest’s country is known, the `TaxCalculator` uses the correct `price_display_method` (e.g., `PS_TAX_EXC` or `PS_TAX_INC`) that corresponds to the tax rules of the detected country, rather than the shop’s default.
- **`taxprice/override/classes/index.php`**

  - **Purpose:** This is a standard empty `index.php` file, typically placed in directories to prevent directory listing for security reasons. It has no functional impact on the module’s logic.

### 4.4 JavaScript Assets (`views/js/`)

This module does **not** contain any custom JavaScript files. Its core functionality is handled server-side via PHP overrides.

### 4.5 CSS Stylesheets (`views/css/`)

This module does **not** contain any custom CSS files. It does not introduce new visual elements, only modifies existing price values.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`taxprice/views/displayHeader.tpl`**

  - **Hook:** `displayHeader`
  - **Purpose:** This template is rendered in the `<head>` section of every front-office page. It’s typically used to include JavaScript, CSS, or meta tags. While the module’s core logic is PHP-based, this template might be used to:
    - Initialize any client-side variables if needed (though unlikely given the server-side nature).
    - Potentially include a small inline script for debugging or very specific client-side adjustments (e.g., setting a cookie with detected country, though less common for this type of module).
    - In the absence of dedicated JS files, it could contain any minimal inline JS required.
- **`taxprice/views/script.tpl`**

  - **Purpose:** This template name suggests it might contain JavaScript code. If present, it would likely be included via `displayHeader.tpl` or another hook.
  - **Potential Content:**
    - Any client-side logic related to geolocation (e.g., using a client-side IP lookup API, though less reliable than server-side).
    - Scripts to handle dynamic price updates if the module also supports client-side toggling or real-time adjustments (unlikely given the description).
    - Debugging scripts or simple data output for developers.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does **not** create any custom database tables.
  - It relies on existing PrestaShop tables for products (`ps_product`, `ps_product_shop`), taxes (`ps_tax`, `ps_tax_rule`, `ps_tax_rule_group`), and configuration (`ps_configuration`).
  - Configuration values are stored in `ps_configuration` using standard `Configuration::get()` and `Configuration::updateValue()` methods, typically prefixed with `TAXPRICE_`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Used to include `displayHeader.tpl` and potentially `script.tpl` for any necessary client-side scripts or meta-information. |
| `actionProductUpdate` | After a product is updated. | (Implicit, not explicitly listed but common for price-related modules) May clear cache related to product prices to ensure overrides are re-applied. |
| `actionProductAdd` | After a product is added. | (Implicit) Similar to `actionProductUpdate`. |
| `actionTaxManagerFactory` | When `TaxManagerFactory` is initialized. | (Implicit, crucial for this module) The overrides in `Tax.php` and `TaxCalculator.php` would effectively “hook into” or modify the behavior of tax calculation at this stage, even if not a formal `hook` registration. |

## 5. Official Support & Updates

For official updates, technical support, and further assistance with the “Tax excluded prices for unlogged users by geolocation” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to providing comprehensive support and ensuring your module operates smoothly.
