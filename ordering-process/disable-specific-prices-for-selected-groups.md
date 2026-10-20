---
title: "Disable specific prices for selected groups - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Disable specific prices for selected groups PrestaShop module by MyPresta.eu."
sidebar:
  label: "Disable specific prices for selected groups - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Disable specific prices for selected groups Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-specific-prices-for-selected-groups.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/disable-specific-prices-for-selected-groups/)
>
> ---


# Disable specific prices for selected groups

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main and only configuration screen for the “Disable specific prices for selected groups” module. You will find it by navigating to **Modules > Module Manager**, searching for “Disable specific prices for selected groups”, and clicking “Configure”.

#### **1. Disable specific prices discounts for selected groups**

This is the core setting of the module. It determines which customer groups will *not* receive specific price discounts.

- **What this setting does:** This section presents a list of all customer groups defined in your PrestaShop store. You can select one or more groups from this list.
- **Effect of changing this setting:**
  - *When one or more groups are selected:* Customers belonging to any of the selected groups will *not* see or benefit from any specific price discounts configured for products. They will always see and pay the standard product price.
  - *When no groups are selected:* The module will not disable specific prices for any group. All customers will receive specific price discounts as configured in your product settings.
- **Recommended value:** Select the specific customer groups for whom you wish to disable specific price discounts. For example, if you have a “Wholesale” group that you want to always pay the standard price, select that group.
- **Merchant scenario / example:** You have a “Guest” customer group and a “New Customers” group. You want to reserve specific price discounts (like bulk pricing or temporary promotions) only for your “Loyal Customers” group. By selecting “Guest” and “New Customers” here, these two groups will always see the regular price, while “Loyal Customers” will still benefit from any specific prices you’ve set up.

#### **2. Enabled**

This is the global on/off switch for the module’s functionality.

- **What this setting does:** This is a simple toggle to activate or deactivate the module’s core logic.
- **Effect of changing this setting:**
  - *When enabled (YES):* The module will actively disable specific prices for the groups you’ve selected in the “Disable specific prices discounts for selected groups” section.
  - *When disabled (NO):* The module will be inactive. All specific prices will function as standard PrestaShop behavior, regardless of the groups selected in the section above. This effectively turns off the module’s impact without uninstalling it.
- **Recommended value:** **YES** if you intend to use the module’s functionality. **NO** if you want to temporarily disable it without losing your group selections.
- **Merchant scenario / example:** You’ve configured the module to disable specific prices for your “Retail” customer group. If you want to run a temporary promotion where *all* groups, including “Retail”, should receive specific price discounts, you can simply set “Enabled” to **NO**. Once the promotion is over, switch it back to **YES** to re-enable the specific price disabling for “Retail” customers.

#### **3. Return always lowest price**

This setting offers an additional layer of control, especially when specific prices might interact with other pricing rules.

- **What this setting does:** This toggle determines whether the module should strictly enforce the standard price for selected groups, or if it should still consider the *lowest possible price* (which might include other types of discounts not managed by specific prices) if it happens to be lower than the standard price.
- **Effect of changing this setting:**
  - *When enabled (YES):* For the selected groups, specific prices will be ignored. However, if there’s *another* mechanism (e.g., a cart rule, a global discount, or a different type of price reduction) that results in a price lower than the standard price, the module will allow that lowest price to be applied. This ensures customers always get the absolute lowest price available *outside* of specific prices.
  - *When disabled (NO):* For the selected groups, specific prices will be ignored, and the module will strictly enforce the *standard product price*. No other potential lower prices (unless they are part of the base price itself) will be considered. This provides the most rigid control over pricing for the selected groups.
- **Recommended value:** **NO** for strict control, ensuring selected groups always pay the standard price. **YES** if you want to disable specific prices but still allow other, non-specific-price-related discounts to apply if they result in a lower price.
- **Merchant scenario / example:**
  - *Scenario 1 (Recommended: NO):* You want your “Wholesale” group to *always* pay the full, standard price, and never benefit from any specific price discounts or any other potential price reductions. You would set this to **NO**.
  - *Scenario 2 (Recommended: YES):* You want to disable specific prices for your “Guest” group, but you also have a general “5% off all products” cart rule that applies to everyone. If you set “Return always lowest price” to **YES**, guests will not get specific price discounts, but they *will* still get the 5% cart rule discount if it makes the price lower than the standard price. If set to **NO**, they would pay the full standard price, ignoring even the 5% cart rule.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Disable specific prices discounts for selected groups | Select groups as needed | Select customer groups for whom specific price discounts will be ignored. |
| Module Configuration | Enabled | YES | Global ON/OFF switch for the module’s functionality. |
| Module Configuration | Return always lowest price | NO (for strict control) / YES (for flexibility) | Determines if other non-specific price discounts can still apply if they result in a lower price for affected groups. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve configured the module, but customers in the selected group are still seeing specific prices. What’s wrong?**
A:

1. **Check “Enabled” setting:** Ensure the “Enabled” switch in the module’s configuration is set to **YES**.
2. **Verify Group Selection:** Double-check that the correct customer group(s) are selected under “Disable specific prices discounts for selected groups”.
3. **Clear PrestaShop Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache”. PrestaShop often caches pricing information.
4. **Check Customer’s Group:** Make sure the customer you are testing with is actually assigned to the group you’ve selected in the module. You can check this in **Customers > Customers** in the Back Office.
5. **Theme Compatibility:** While rare, some heavily customized themes might interfere. If the issue persists, try switching to the default PrestaShop theme temporarily to rule out theme conflicts.

**Q: What happens if a customer is in multiple groups, and one group is selected for disabling specific prices while another is not?**
A: PrestaShop’s core logic typically prioritizes the lowest price. This module’s override will attempt to remove specific prices for *any* group selected. If a customer is in a group that *should* have specific prices disabled, the module will attempt to enforce the standard price. The “Return always lowest price” setting will then determine if other non-specific price discounts are still considered.

**Q: Does this module affect other types of discounts, like cart rules or catalog price rules?**
A: This module specifically targets “specific prices” as defined in PrestaShop (the discounts set directly on product pages or via CSV import).

- If “Return always lowest price” is **NO**, the module will strictly enforce the standard price for selected groups, potentially overriding other discounts if they result in a lower price than the standard price.
- If “Return always lowest price” is **YES**, the module will disable specific prices but will still allow other types of discounts (like cart rules or catalog price rules) to apply if they result in a price lower than the standard price.

**Q: I want to temporarily disable the module without losing my settings. How do I do that?**
A: Simply go to the module’s configuration page and set the “Enabled” switch to **NO**. All your selected groups and other settings will be preserved, and you can re-enable it at any time by switching it back to **YES**.

**Q: How do I translate the module’s text into other languages?**
A: Go to **International > Translations** in your PrestaShop Back Office. Select “Installed modules translations”, choose your theme, and then select “Disable specific prices for selected groups”. You can then translate any visible text strings.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Disable specific prices for selected groups” module primarily functions by overriding core PrestaShop classes related to product pricing, specifically `Product.php` and `SpecificPrice.php`. This allows it to intercept and modify the logic that determines whether specific prices are applied to a product, based on the current customer’s group and the module’s configuration. It follows a standard PrestaShop module structure with a main module file and class overrides.

### 4.2 Controllers (`controllers/`)

This module does not utilize any custom Front-Office or Back-Office Admin Controllers. All configuration is handled via the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)

The module’s core functionality is implemented through class overrides.

- **`exsdis/override/classes/index.php`**:

  - This is a standard empty `index.php` file, typically placed in directories to prevent directory listing. It has no functional impact on the module’s logic.
- **`exsdis/override/classes/Product.php`**:

  - **Original Class**: `classes/Product.php`
  - **Purpose**: This override modifies the `Product` class, which is central to how product information, including prices, is retrieved and calculated in PrestaShop. The module’s logic within this override intercepts calls to retrieve specific prices for a product.
  - **Key Logic**: It checks if the module is enabled and if the current customer’s group is among those selected to have specific prices disabled. If so, it manipulates the specific price retrieval process to ensure that no specific prices are returned for that customer. It also considers the `exsdis_lowest` configuration to determine if the absolute lowest price (excluding specific prices) should still be returned.
- **`exsdis/override/classes/SpecificPrice.php`**:

  - **Original Class**: `classes/SpecificPrice.php`
  - **Purpose**: This override targets the `SpecificPrice` class, which is responsible for managing and applying specific price rules.
  - **Key Logic**: It likely modifies methods within this class (e.g., `getSpecificPrice()`, `getSpecificPrices()`) to prevent specific price objects from being created or returned for customers in the designated groups. This works in conjunction with the `Product.php` override to ensure specific prices are effectively ignored.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include any custom JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)

This module does not include any custom CSS files.

### 4.6 Smarty Template Structure (`views/templates/`)

This module does not include any custom Smarty template files. The configuration form is rendered dynamically by the `getContent()` method in `exsdis.php`.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  The module does not create any custom database tables. It stores its configuration settings in the standard `ps_configuration` table.

  - `ps_configuration` entries:
    - `exsdis_`: (Prefix for module’s general settings)
    - `exsdis_groups`: Stores a serialized array or comma-separated string of customer group IDs for which specific prices are disabled.
    - `exsdis_lowest`: Stores the value (0 or 1) for the “Return always lowest price” setting.
    - `mypresta_updates`, `update_`, `updatev_`: Related to MyPresta.eu update checks.
- **Registered Hooks Table**:
  The module does not explicitly register any standard PrestaShop hooks in its `install()` method. Its functionality is primarily achieved through class overrides, which modify core PrestaShop behavior directly rather than reacting to hook events.
  The module’s description mentions “Front-Office Hooks: Header, Columns, Product, or Footer” but this is likely a generic statement about where *pricing* might be displayed, not where the module itself injects content via hooks. The overrides handle the pricing logic at a lower level.

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Disable specific prices for selected groups” module, please refer to your MyPresta.eu customer account. You can download the newest versions from your order history and access the dedicated support channels provided by MyPresta.eu.
