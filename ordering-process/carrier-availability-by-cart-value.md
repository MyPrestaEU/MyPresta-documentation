---
title: "Carrier availability by cart value - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Carrier availability by cart value PrestaShop module by MyPresta.eu."
sidebar:
  label: "Carrier availability by cart value - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Carrier availability by cart value Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/carrier-availability-by-cart-value.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/carrier-availability-by-cart-value/)
>
> ---


# Carrier availability by cart value

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and are usually available on any modern hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” will take you to the main configuration page for the module.

- **What this setting does:** This screen primarily handles general module settings, often related to updates or basic functionality.
- **Effect of changing this setting:**
  - `mypresta_updates`: This is a common setting across MyPresta.eu modules.
    - *When enabled:* The module will periodically check for new versions and updates from MyPresta.eu. This helps you stay current with bug fixes and new features.
    - *When disabled:* The module will not check for updates automatically. You would need to manually check for new versions on MyPresta.eu.
  - `update_` and `updatev_`: These are internal settings used by the module’s update mechanism to track the last check and available version. You typically do not need to interact with these directly.
- **Recommended value:**
  - For `mypresta_updates`: **YES** (Enabled). It’s always recommended to keep modules updated for security, performance, and new features.
- **Merchant scenario / example:** Enabling updates ensures your module is always running the latest version, preventing potential compatibility issues with future PrestaShop updates or other modules.

### 2.2 Dedicated Admin Screen: Carrier Availability Rules

This is the core of the module where you define the rules for carrier availability based on cart value.

- **Screen Name & Menu Location:**

  - In your PrestaShop Back Office, navigate to **Shipping > Carrier availability by order value**.
  - This will open a new dedicated screen where you can manage your rules.
- **Available Actions & Settings:**
  This screen presents a list of existing rules and allows you to add new ones or edit/delete existing ones.

  **Listing Table Columns:**

  - **ID**: Unique identifier for the rule.
  - **Carrier**: The name of the shipping carrier to which the rule applies.
  - **Order\_from**: The minimum cart value for this carrier to be available.
  - **Order\_to**: The maximum cart value for this carrier to be available.
  - **Active**: A switch to enable or disable the rule without deleting it.

  **Adding/Editing a Rule (Form Fields):**
  When you click “Add new rule” or edit an existing one, you’ll see a form with the following fields:

  - **Carrier availability by order value**: This is a dropdown list where you select the specific shipping carrier you want to apply the rule to.

    - *Effect:* The rule you define will only affect the availability of this chosen carrier.
    - *Recommended value:* Select the carrier you wish to manage.
    - *Merchant scenario:* If you want to restrict “Express Delivery” to high-value orders, you’d select “Express Delivery” here.
  - **Order value from**: Enter the minimum total cart value (in your default currency) for this carrier to be available.

    - *Effect:* If the customer’s cart value is below this amount, the selected carrier will not be shown during checkout.
    - *Recommended value:* Enter `0` if there’s no minimum, or a specific amount (e.g., `50.00`).
    - *Merchant scenario:* Set to `50.00` for “Free Shipping” to only appear for orders over $50.
  - **Order value to**: Enter the maximum total cart value (in your default currency) for this carrier to be available.

    - *Effect:* If the customer’s cart value is above this amount, the selected carrier will not be shown during checkout.
    - *Recommended value:* Leave empty or set to `0` if there’s no maximum, or a specific amount (e.g., `200.00`).
    - *Merchant scenario:* Set to `200.00` for “Standard Shipping” to prevent it from being chosen for very high-value orders that should use “Insured Shipping.”
  - **Active**: A simple ON/OFF switch.

    - *Effect:*
      - *When enabled:* The rule is active and will filter carrier availability.
      - *When disabled:* The rule is ignored, and the carrier will be available based on other PrestaShop settings (weight, price, zones) regardless of cart value.
    - *Recommended value:* **ON** for active rules.
    - *Merchant scenario:* Temporarily disable a rule during a promotion without deleting it.
  - **Save**: Click this button to apply your changes or create the new rule.
- **Recommended workflow for daily store management:**

  1. **Identify your carriers:** List all your shipping carriers and their intended use cases.
  2. **Define value ranges:** For each carrier, decide if there’s a specific cart value range where it should be available.
     - *Example 1:* “Economy Shipping” for orders $0 - $75.
     - *Example 2:* “Standard Shipping” for orders $75 - $250.
     - *Example 3:* “Premium Insured” for orders $250 and above (set “Order value from” to 250, leave “Order value to” empty/0).
  3. **Add rules:** Go to **Shipping > Carrier availability by order value** and click “Add new rule”.
  4. **Configure each rule:** Select the carrier, enter the “Order value from” and “Order value to”, and ensure “Active” is ON.
  5. **Test thoroughly:** After setting up your rules, perform test purchases with different cart values to ensure carriers are displayed as expected.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | `mypresta_updates` | YES (Enabled) | Enables automatic checks for module updates. |
| Carrier Availability Rules | Carrier | Select from list | The specific shipping carrier this rule applies to. |
| Carrier Availability Rules | Order value from | `0` or specific amount | Minimum cart value for the carrier to be available. |
| Carrier Availability Rules | Order value to | `0` (no max) or specific amount | Maximum cart value for the carrier to be available. |
| Carrier Availability Rules | Active | ON | Enables or disables the specific carrier availability rule. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve set up rules, but the carriers aren’t changing in checkout. What’s wrong?**
A1:

- **Clear Cache:** Always clear your PrestaShop cache after making module configuration changes. Go to **Advanced Parameters > Performance**, then click “Clear cache” in the top right.
- **Rule Conflicts:** Check if you have conflicting rules. For example, if Carrier A is set from $0-$100 and Carrier B is set from $50-$150, ensure your ranges are logical.
- **Carrier Status:** Make sure the carriers themselves are active and properly configured in **Shipping > Carriers** in PrestaShop. This module only filters *available* carriers, it doesn’t activate inactive ones.
- **Other Carrier Restrictions:** Remember PrestaShop has its own carrier restrictions (by zone, weight, price). This module *adds* another layer of filtering. If a carrier is already restricted by weight, this module won’t make it available.

**Q2: My currency symbol isn’t showing correctly, or the values seem off.**
A2: The module uses your shop’s default currency for the “Order value from” and “Order value to” fields. Ensure your default currency is correctly set in **International > Currencies**. The module operates on the numerical value, so the symbol displayed in the back office is for your reference.

**Q3: Can I use this module with other shipping modules?**
A3: Yes, generally. This module hooks into the standard PrestaShop process for filtering carrier lists. It will apply its rules *after* other core PrestaShop conditions (like weight, price, zone) have already narrowed down the list of potential carriers. If another module also filters carriers, the most restrictive rules from all modules will apply.

**Q4: How do I make a carrier *always* available, regardless of cart value?**
A4: You don’t need to create a rule for such a carrier. If a carrier is not listed in your “Carrier availability by order value” rules, it will remain available based on PrestaShop’s default carrier settings (weight, price, zone, etc.) without any cart value restrictions from this module.

**Q5: The module seems to be slowing down my checkout. Is this normal?**
A5: This module is designed to be lightweight and should not significantly impact performance. If you notice a slowdown, ensure your PrestaShop installation is optimized (e.g., caching enabled, latest PHP version, no excessive modules). If the issue persists, contact MyPresta.eu support with details of your setup.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Carrier availability by cart value” module (`cbp`) follows the standard PrestaShop module architecture, primarily leveraging an AdminController for configuration and a Front-Office hook to modify the carrier list during checkout. It uses a custom `ObjectModel` to manage carrier availability rules in its own database table.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:
  This module does not include any dedicated front-office controllers. All front-office logic is handled directly via a hook in the main module file (`cbp.php`).
- **Back-Office Admin Controllers**:

  - `cbp/controllers/admin/AdminCbpr.php`

    - **Class Name:** `AdminCbprController` (extends `ModuleAdminController`)
    - **Responsibility:** This is the primary administrative interface for managing carrier availability rules. It handles the CRUD (Create, Read, Update, Delete) operations for the `cbpr` entity.
    - **Tab Name:** “Carrier availability by order value” (under Shipping menu).
    - **Managed Entity:** `Cbpr` (the custom `ObjectModel` for carrier rules).
    - **Key Features:**
      - Displays a `list` view of all configured rules, including ID, Carrier name, Order\_from, Order\_to, and Active status.
      - Provides `add` and `edit` forms for individual rules, allowing selection of a carrier and input of min/max order values.
      - Handles form submissions and database interactions for saving and updating rules.
      - Utilizes `PS_CURRENCY_DEFAULT` to display currency information in the forms.
  - `cbp/controllers/admin/index.php`

    - **Responsibility:** This file is a standard empty `index.php` file, typically included in PrestaShop directories to prevent directory listing for security reasons. It does not contain any functional controller logic.

### 4.3 Core Classes & Models (`classes/`)

The module does not have a dedicated `classes/` directory. The primary `ObjectModel` for managing carrier rules is likely defined directly within the main module file (`cbp/cbp.php`) or implicitly handled by the `AdminCbprController` using a dynamic `ObjectModel` definition.

Given the `AdminCbprController` manages a table named `cbpr`, there must be an `ObjectModel` class, likely named `Cbpr`, defined somewhere. This class would define the structure of the carrier availability rules.

**Assumed `Cbpr` ObjectModel (likely in `cbp.php`):**

- **Class Name:** `Cbpr` (extends `ObjectModel`)
- **Database Table:** `ps_cbpr` (or `_cbpr` with prefix)
- **`$definition` fields (expected):**
  - `id_cbpr`: Primary key.
  - `id_carrier`: Foreign key to `ps_carrier` table.
  - `order_from`: Decimal field for minimum cart value.
  - `order_to`: Decimal field for maximum cart value.
  - `active`: Boolean field for rule status.
- **Key Methods:** Standard `ObjectModel` methods for `add()`, `update()`, `delete()`.

### 4.4 JavaScript Assets (`views/js/`)

The module does not contain any custom JavaScript files in `views/js/`. All front-office logic is handled server-side via PHP hooks. Back-office forms rely on PrestaShop’s default form handling and jQuery.

### 4.5 CSS Stylesheets (`views/css/`)

The module does not contain any custom CSS files in `views/css/`. The back-office interface uses PrestaShop’s default styling for `ModuleAdminController` forms and lists.

### 4.6 Smarty Template Structure (`views/templates/`)

The module does not contain any custom Smarty template files in `views/templates/`. The configuration forms and lists in the back office are rendered using PrestaShop’s default `ModuleAdminController` templates. Front-office changes are handled by filtering the carrier list directly in PHP, not by rendering new templates.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - `ps_cbpr`: This table stores the carrier availability rules.

    - `id_cbpr` INT(10) UNSIGNED NOT NULL AUTO\_INCREMENT
    - `id_carrier` INT(10) UNSIGNED NOT NULL
    - `order_from` DECIMAL(20,6) NOT NULL DEFAULT ‘0.000000’
    - `order_to` DECIMAL(20,6) NOT NULL DEFAULT ‘0.000000’
    - `active` TINYINT(1) UNSIGNED NOT NULL DEFAULT ‘1’
    - PRIMARY KEY (`id_cbpr`)
    - KEY `id_carrier` (`id_carrier`)
  - `ps_configuration`: The module stores its general settings (like `mypresta_updates`, `update_`, `updatev_`) in the `ps_configuration` table.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Executed when an AdminController is initialized and its media (JS/CSS) are being set. | Used by the module to register its custom AdminController (`AdminCbprController`) in the PrestaShop menu structure. |
| `actionFilterDeliveryOptionList` | Executed during the checkout process, specifically when PrestaShop is building the list of available delivery options. | This is the core front-office hook. The module uses this to iterate through the list of carriers that PrestaShop has already deemed available (based on zones, weight, price) and then further filters this list based on the cart’s total value and the rules defined in `ps_cbpr`. If a carrier’s rule doesn’t match the current cart value, it’s removed from the list presented to the customer. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the “Carrier availability by cart value” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to ensuring the smooth operation and continuous improvement of our modules.
