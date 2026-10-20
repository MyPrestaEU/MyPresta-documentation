---
title: "Disable vouchers for items on sale - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Disable vouchers for items on sale PrestaShop module by MyPresta.eu."
sidebar:
  label: "Disable vouchers for items on sale - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Disable vouchers for items on sale Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/disable-vouchers-for-items-on-sale.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/disable-vouchers-for-items-on-sale/)
>
> ---


# Disable vouchers for items on sale

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required, which are typically available on any modern PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main and only configuration screen for the “Disable vouchers for items on sale” module. You can access it by navigating to **Modules > Module Manager** and searching for “Disable vouchers for items on sale”, then clicking the “Configure” button.

#### **General Settings**

- **Disable vouchers for items on sale:**

  - **What this setting does:** This is the primary switch to activate or deactivate the module’s core functionality.
  - **Effect of changing this setting:**
    - *When enabled (YES):* If a customer’s cart contains *any* product that is currently on sale (has a special price), they will be prevented from applying *any* voucher code.
    - *When disabled (NO):* The module will be inactive. Customers will be able to apply voucher codes even if their cart contains sale items, allowing for “double-discounting.”
  - **Recommended value:** **YES** if you want to prevent double-discounting and protect your margins.
  - **Merchant scenario / example:** You’re running a “Summer Sale” with 20% off selected items. You also have a “Welcome10” voucher for new customers. If this setting is **YES**, a new customer cannot use “Welcome10” if their cart includes any item from the Summer Sale.
- **Disable module for codes that starts with:**

  - **What this setting does:** This allows you to create an exception. If a voucher code starts with a specific string you define here, the module’s restriction will *not* apply to that voucher, even if there are sale items in the cart.
  - **Effect of changing this setting:**
    - *When a string is entered (e.g., “FREESHIP”):* Any voucher code starting with “FREESHIP” (e.g., “FREESHIP2023”, “FREESHIPNOW”) will bypass the module’s restriction. Customers can use these specific vouchers even with sale items in their cart.
    - *When left empty:* No exceptions are made based on voucher code prefixes. All vouchers are subject to the “Disable vouchers for items on sale” rule.
  - **Recommended value:** Leave empty unless you have specific vouchers you *always* want to allow, regardless of sale items.
  - **Merchant scenario / example:** You have a special “FREESHIP” voucher that gives free shipping. You decide that free shipping should always be allowed, even on sale items, to encourage larger orders. You would enter “FREESHIP” in this field.
- **Message for customer:**

  - **What this setting does:** This is the custom message that customers will see in their cart when they try to apply a voucher code but are blocked because of sale items.
  - **Effect of changing this setting:**
    - *When a message is entered (e.g., “Vouchers cannot be used with sale items.”):* This exact message will be displayed to the customer.
    - *When left empty:* The module will likely display a default or generic error message, which might be less clear to the customer.
  - **Recommended value:** A clear, polite, and informative message.
  - **Merchant scenario / example:** You want to inform customers clearly: “This voucher cannot be applied because your cart contains items already on sale. Please remove sale items or use a different voucher.”

#### **Configuration Quick Reference Table**

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Disable vouchers for items on sale | YES | Activates/deactivates the core functionality to block vouchers on sale items. |
| Module Configuration | Disable module for codes that starts with: | Leave empty | Allows specific voucher codes (by prefix) to bypass the module’s restrictions. |
| Module Configuration | Message for customer | “Vouchers cannot be used with sale items.” (or similar) | Customizes the error message shown to customers when a voucher is blocked. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve enabled the module, but customers can still use vouchers on sale items. What’s wrong?**
A:

1. **Check the “Disable vouchers for items on sale” setting:** Ensure it is set to **YES** in the module configuration.
2. **Clear Cache:** Go to **Advanced Parameters > Performance** in your PrestaShop Back Office and click “Clear cache” (or “Clear Smarty cache” in older versions). Module changes sometimes require a cache refresh.
3. **Verify Sale Status:** Double-check that the products you are testing with are genuinely marked as “on sale” in PrestaShop (e.g., they have a specific price defined that makes them cheaper than their regular price).
4. **Check Voucher Code Prefix Exception:** If you’ve entered a string in “Disable module for codes that starts with:”, ensure the voucher you’re testing doesn’t start with that string.

**Q: The module is blocking vouchers, but the message isn’t showing up, or it’s showing a generic error.**
A:

1. **Customize the Message:** Go to the module configuration and make sure you’ve entered a custom message in the “Message for customer” field.
2. **Theme Compatibility:** While the module tries to integrate seamlessly, some highly customized themes might override default PrestaShop error display mechanisms. If the message isn’t appearing, it might be a front-office theme issue. Contact your theme developer or a webmaster for assistance.

**Q: Can I disable this module for specific customer groups or individual products?**
A: No, this module operates globally based on the presence of *any* sale item in the cart. It does not offer granular control for specific customer groups or product exclusions beyond the voucher code prefix exception. If you need more advanced logic, custom development might be required.

**Q: Will this module affect my SEO or product listings?**
A: No, this module operates purely on the logic of applying vouchers in the cart. It does not alter product prices, descriptions, URLs, or any other front-office elements that would impact SEO.

**Q: I updated my PrestaShop version, and now the module isn’t working.**
A:

1. **Check Module Compatibility:** Ensure you have downloaded and installed the version of the module specifically designed for your PrestaShop version from your MyPresta.eu account.
2. **Reinstall/Reconfigure:** Sometimes, after a major PrestaShop update, modules might need to be reinstalled or reconfigured. Try uninstalling and then reinstalling the module (remember to back up your settings if possible, though this module has minimal data).
3. **Clear Cache:** Always clear your PrestaShop cache after any update or module change.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Disable vouchers for items on sale” module (`dvfis`) primarily functions by overriding the core `CartController` to intercept the voucher application process. It leverages PrestaShop’s override mechanism to inject its logic before a voucher is validated and applied. The module’s configuration is stored in `ps_configuration` and accessed via the main module class.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `dvfis/override/controllers/front/CartController.php`
    - **Class name & parent class**: `CartController` (overrides the core `CartController` class)
    - **Responsibility**: This is the most critical file. It extends the core `CartController` to modify the `postProcess()` method. Specifically, it intercepts the logic when a customer attempts to add a voucher (`addDiscount()`). It checks if the module is enabled and if the cart contains any products with a special price. If both conditions are met (and the voucher code doesn’t match an exclusion prefix), it prevents the voucher from being added and displays a custom error message.
  - `dvfis/override/controllers/front/index.php`
    - **Class name & parent class**: Not a class file, typically an empty file or a file with a basic `<?php exit;` to prevent direct directory listing. It’s a standard practice for PrestaShop override directories.
- **Back-Office Admin Controllers**: None. The module uses the standard `getContent()` method within its main module file for configuration.

### 4.3 Core Classes & Models (`classes/`)

None. The module does not define any custom `ObjectModel` classes or other standalone PHP classes in the `classes/` directory. All logic is contained within the main module file and the `CartController` override.

### 4.4 JavaScript Assets (`views/js/`)

None. The module does not include any custom JavaScript files. All front-office interactions are handled server-side by the `CartController` override.

### 4.5 CSS Stylesheets (`views/css/`)

None. The module does not include any custom CSS files. Any messages displayed to the customer will inherit the styling of the active PrestaShop theme’s error/notification messages.

### 4.6 Smarty Template Structure (`views/templates/`)

None. The module does not use custom Smarty template files. Error messages are passed directly to the `CartController`’s `errors` array, which are then rendered by the theme’s standard error display mechanism.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  The module does not create any custom database tables. All its configuration settings are stored in the `ps_configuration` table:

  - `DVFIS_MESSAGE`: Stores the custom message for customers.
  - `DVFIS_ENABLED`: Stores the boolean (0 or 1) value for enabling/disabling the module.
  - `DVFIS_STR`: Stores the string prefix for voucher code exceptions.
  - `DVFIS_STRV`: (Likely a legacy or internal versioning key, not directly user-configurable).
  - `mypresta_updates`, `update_`, `updatev_`: Keys related to MyPresta.eu’s update system.
  - `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Standard PrestaShop configuration keys used for language handling in the module’s `getContent()`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | During Back Office controller initialization | Used by the module to include its own CSS/JS files (if any) in the Back Office. In this module’s case, it’s likely used for MyPresta.eu’s update system or general module setup, not for custom styling/scripting. |
| `actionFrontControllerInitAfter` | After a Front Office controller has been initialized | Used by the module to potentially perform actions or modify controller behavior early in the request lifecycle. For this module, it’s likely used to ensure the `CartController` override is correctly loaded and active. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Disable vouchers for items on sale” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
