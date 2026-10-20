---
title: "Disable free shipping to selected countries - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Disable free shipping to selected countries PrestaShop module by MyPresta.eu."
sidebar:
  label: "Disable free shipping to selected countries - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Disable free shipping to selected countries Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-free-shipping-to-selected-countries.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/disable-free-shipping-to-selected-countries/)
>
> ---


# Disable free shipping to selected countries

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main and only configuration screen for the “Disable free shipping to selected countries” module. You will find it by navigating to **Modules > Module Manager**, searching for “Disable free shipping to selected countries”, and clicking “Configure”.

#### Exclude free shipping from countries:

- **What this setting does:** This is the core setting of the module. It allows you to select one or more countries where free shipping should *not* be offered, regardless of other free shipping rules you might have in place (e.g., free shipping over a certain order amount).
- **Effect of changing this setting:**
  - *When countries are selected:* If a customer’s delivery address is in any of the selected countries, the “Free Shipping” option will be removed from the list of available carriers during checkout. They will only see paid shipping options.
  - *When no countries are selected:* The module will have no effect, and free shipping will be offered to all countries according to your standard PrestaShop settings.
- **Recommended value:** Select only those countries where offering free shipping is genuinely unprofitable or problematic for your business.
- **Merchant scenario / example:** You ship internationally, but shipping to Australia and New Zealand is significantly more expensive due to distance and customs. You would select “Australia” and “New Zealand” from this list. Now, customers from these countries will always be charged for shipping, even if their order value qualifies for free shipping in other regions like the EU or USA.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Exclude free shipping from countries: | None selected | Select countries where free shipping should NOT be offered. If a customer’s delivery address is in a selected country, free shipping will be unavailable for their order. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve configured the module, but free shipping is still showing for a selected country. What’s wrong?**
A:

1. **Clear Cache:** Always clear your PrestaShop cache after making configuration changes. Go to **Advanced Parameters > Performance** and click “Clear cache” in the top right.
2. **Test with a New Cart:** Ensure you’re testing with a fresh cart and a delivery address set to the excluded country. Sometimes browser cache or session data can interfere.
3. **Check Carrier Settings:** Verify that your free shipping carrier (or the carrier offering free shipping) is correctly configured in **Shipping > Carriers**. Ensure it’s active and has “Free shipping” enabled. This module *disables* the free shipping option, it doesn’t create new shipping rules.
4. **Module Order:** In rare cases, if you have multiple shipping-related modules, there might be a conflict. Try temporarily disabling other shipping modules to isolate the issue.

**Q: Does this module affect other shipping costs?**
A: No, this module *only* affects the availability of the “Free Shipping” option. It does not modify or remove any paid shipping options or their costs. If free shipping is disabled for a country, customers will simply be presented with the standard paid shipping options available for their cart and destination.

**Q: Can I disable free shipping for specific products or categories instead of countries?**
A: No, this module is designed specifically to disable free shipping based on the *delivery country*. It does not offer options to exclude free shipping based on product, category, or customer group. If you need such functionality, you would require a different, more advanced shipping rules module.

**Q: What if I want to offer free shipping to a country for orders over a certain amount, but disable it for lower amounts?**
A: This module disables *all* free shipping for the selected countries. If you want conditional free shipping (e.g., free shipping over $X), you should configure that directly within your PrestaShop carriers settings (Shipping > Carriers). This module would then override that setting for the excluded countries, making free shipping unavailable at *any* amount for those specific destinations.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Disable free shipping to selected countries” module operates by overriding core PrestaShop classes related to carrier and cart behavior. Specifically, it modifies the logic that determines if a carrier offers free shipping and if a cart qualifies for it, based on the customer’s delivery country. This is achieved through PrestaShop’s override system, ensuring that the module’s logic is applied whenever shipping calculations are performed.

### 4.2 Controllers (`controllers/`)

This module does not utilize any custom Front-Office or Back-Office Admin Controllers. Its logic is injected directly into core PrestaShop functionality via class overrides.

### 4.3 Core Classes & Models (`classes/`)

The module implements its functionality primarily through class overrides, located in the `override/classes/` directory within the module folder.

- **`exfsc/override/classes/Carrier.php`**

  - **Class Name & Parent Class:** `Carrier` (overrides the core `Carrier` class)
  - **Responsibility:** This override modifies the `isFree()` method of the `Carrier` class. When PrestaShop checks if a particular carrier offers free shipping, this override intercepts the call. It checks if the current cart’s delivery country is among those configured to exclude free shipping. If it is, and the original `isFree()` method would have returned `true`, this override forces it to return `false`, effectively disabling free shipping for that carrier for the excluded country.
  - **Key Methods:**
    - `isFree($cart)`: Modified to check `exfsc_country` configuration and return `false` if the cart’s delivery country is excluded and the original method would have returned `true`.
- **`exfsc/override/classes/Cart.php`**

  - **Class Name & Parent Class:** `Cart` (overrides the core `Cart` class)
  - **Responsibility:** This override modifies the `getDeliveryOptionList()` method. This method is responsible for generating the list of available delivery options (including carriers and their services) during checkout. The override ensures that if a carrier is marked as “free shipping” but the delivery country is excluded by the module, that carrier is correctly presented with its *paid* shipping options, or if it only offers free shipping, it is excluded entirely.
  - **Key Methods:**
    - `getDeliveryOptionList(Country $default_country = null, $product_list = null, $id_zone = null)`: Modified to ensure that carriers marked as free are correctly evaluated against the module’s country exclusion list.
- **`exfsc/override/classes/index.php`**

  - **Purpose:** This is an empty `index.php` file, typically included in directories to prevent directory listing when accessed directly via a web browser, enhancing security. It has no functional impact on the module’s logic.

### 4.4 JavaScript Assets (`views/js/`)

The module does not include any custom JavaScript files. All functionality is handled server-side.

### 4.5 CSS Stylesheets (`views/css/`)

The module does not include any custom CSS files. All functionality is handled server-side.

### 4.6 Smarty Template Structure (`views/templates/`)

The module does not include any custom Smarty template files. Its effects are integrated into existing PrestaShop checkout templates by modifying the underlying data passed to them.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any custom SQL tables.
  - Configuration settings are stored in the `ps_configuration` table.
    - `exfsc_country`: Stores a comma-separated list of `id_country` values for countries where free shipping is disabled.
    - `mypresta_updates`, `update_`, `updatev_`: Internal configuration keys used by MyPresta.eu modules for update checks.
    - `exfsc_visibility_cat`, `exfsc_visibility_products`: These keys are present in the `getContent()` method but are not actively used by the module’s core logic as described in the feature set. They might be remnants or placeholders for potential future features.
- **Registered Hooks Table**:
  The module does not explicitly register any front-office hooks. Its functionality is implemented through class overrides, which are triggered automatically by PrestaShop’s core processes when shipping options are calculated.
  The module’s `install()` method may register standard back-office hooks for module management (e.g., `displayBackOfficeHeader`), but these are for administrative purposes and do not affect front-office behavior.

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the “Disable free shipping to selected countries” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to ensuring your module functions perfectly with your PrestaShop store.
