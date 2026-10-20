---
title: "Specific price tax included field - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Specific price tax included field PrestaShop module by MyPresta.eu."
sidebar:
  label: "Specific price tax included field - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Specific price tax included field Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/specific-price-tax-included-field.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/specific-price-tax-included-field/)
>
> ---


# Specific price tax included field

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Specific price tax included field” module in the Module Manager. This will take you to the module’s main configuration screen.

#### General Settings

- **What this setting does:** This section typically contains general settings related to module updates and version checks.
- **Effect of changing this setting:**
  - *When enabled:* The module will periodically check for new versions available from MyPresta.eu and notify you in the Back Office. This ensures you’re always running the latest, most secure, and feature-rich version.
  - *When disabled:* The module will not perform automatic update checks. You would need to manually check for updates by visiting your MyPresta.eu account.
- **Recommended value:** **YES** (or enabled). Keeping this enabled ensures you stay informed about important updates and bug fixes.
- **Merchant scenario / example:** You want to be notified if a new version of the module is released that includes compatibility fixes for a new PrestaShop version or performance improvements. Keeping this enabled will show a notification in your Back Office.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Update checks (mypresta\_updates, update\_, updatev\_) | Enabled | Periodically checks for new module versions and notifies you in the Back Office. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve installed the module, but I don’t see the new “Price tax included” field.**
A: First, ensure the module is enabled in **Modules > Module Manager**. Then, navigate to a product page, go to the “Pricing” tab, and click “Add a new specific price” or “Edit” an existing one. The new field should appear within the specific price creation/edit form. If it’s still not visible, try clearing your PrestaShop cache (**Advanced Parameters > Performance**, then click “Clear cache”).

**Q: The calculated tax-excluded price seems incorrect.**
A: The module relies on the tax rule assigned to the product.
1. **Check the product’s tax rule:** Go to the product page, “Pricing” tab, and verify that the correct “Tax rule” is selected for the product.
2. **Check the tax rule configuration:** Go to **International > Taxes > Tax Rules** and ensure the tax rates defined for the selected tax rule are correct for your target countries/zones.
3. **Clear cache:** After verifying and potentially correcting tax settings, clear your PrestaShop cache.

**Q: Does this module affect existing specific prices?**
A: No, this module only adds a new input field to the specific price creation/edit form. It does not alter or recalculate any specific prices that were created before its installation or using the default “Price tax excluded” field. It simply provides an alternative way to input new specific prices.

**Q: Will this module work with my custom theme?**
A: Yes, this module primarily modifies a standard PrestaShop Back Office form. It uses standard PrestaShop hooks and JavaScript to inject the new field. It is highly unlikely to conflict with front-office custom themes, as it has no front-office display components.

**Q: I’m getting an error after updating PrestaShop.**
A: After any major PrestaShop update, it’s a good practice to:
1. Clear your PrestaShop cache (**Advanced Parameters > Performance**).
2. Check for a new version of the “Specific price tax included field” module in your MyPresta.eu account, as updates often include compatibility fixes.
3. If the issue persists, contact MyPresta.eu support.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Specific price tax included field” module (`sptincl`) is a lightweight PrestaShop 1.7.x module designed to enhance the specific price management interface in the Back Office. It primarily operates by injecting JavaScript into the `actionAdminControllerSetMedia` hook, which then modifies the DOM of the specific price form to add the “Price tax included” field and implement the necessary client-side calculation logic. It does not introduce new database tables, controllers, or complex business logic on the server-side beyond its configuration.

### 4.2 Controllers (`controllers/`)

This module does not introduce any custom Front-Office or Back-Office Admin Controllers. All its functionality is injected into existing PrestaShop admin pages via hooks and JavaScript.

### 4.3 Core Classes & Models (`classes/`)

This module does not introduce any custom PHP classes or `ObjectModel` definitions. Its core logic resides within the main module file (`sptincl.php`).

### 4.4 JavaScript Assets (`views/js/`)

- **`sptincl/views/js/sptincl.js`**
  - **Scope:** Back-office (specifically, the specific price creation/edit form).
  - **Purpose:** This script is responsible for the module’s primary functionality.
    - **DOM Manipulation:** It dynamically adds a new input field for “Price tax included” to the specific price form. It also modifies the behavior of the existing “Price tax excluded” field.
    - **Event Listeners:** It attaches event listeners (e.g., `keyup`, `change`) to both the new “Price tax included” field and the existing “Price tax excluded” field, as well as the tax rule selector.
    - **Calculation Logic:** When a user inputs a value into the “Price tax included” field, or changes the tax rule, the script calculates the corresponding “Price tax excluded” value using the selected tax rate. Conversely, if the “Price tax excluded” field is modified, it calculates the “Price tax included” value.
    - **AJAX (Implicit):** While not directly performing AJAX calls, it relies on the tax rates available in the DOM or fetched by PrestaShop’s existing mechanisms to perform its calculations. It uses the `getTaxRate()` function (which might be a global PrestaShop JS function or a custom one defined within the script) to retrieve the current tax rate based on the selected tax rule.

### 4.5 CSS Stylesheets (`views/css/`)

This module does not include any custom CSS files. It relies on PrestaShop’s default styling for form elements, ensuring seamless integration with the Back Office UI.

### 4.6 Smarty Template Structure (`views/templates/`)

This module does not utilize custom Smarty template files. Its configuration is handled directly within the `getContent()` method of the main module class, and its front-end modifications are purely JavaScript-driven.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: This module does not create any custom database tables. It stores its configuration settings (like `mypresta_updates`, `update_`, `updatev_`) in the standard `ps_configuration` table.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Executed when an Admin Controller is initialized and its media assets (JS/CSS) are being set. | This is the primary hook used by the module. It injects the `sptincl.js` JavaScript file into the Back Office, specifically targeting the specific price creation/edit form. This allows the module to modify the form’s DOM and add its client-side calculation logic. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Specific price tax included field” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
