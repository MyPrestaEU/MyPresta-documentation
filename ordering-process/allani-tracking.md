---
title: "Allani tracking - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Allani tracking PrestaShop module by MyPresta.eu."
sidebar:
  label: "Allani tracking - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Allani tracking Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/allani-tracking.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/allani-tracking/)
>
> ---


# Allani tracking

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **PHP Compatibility**: PHP 5.6 - 8.5 (The module is designed to work across a broad range of PHP versions, up to the latest stable release supported by PrestaShop 1.7.x and future versions.)
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) typically available on any modern PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Allani tracking” module to access its settings.

#### Order Identification

This section controls how the module identifies and sends order data to Allani.

- **What this setting does:** This is the core setting for the module. It determines whether the module is active and sending order data to Allani.
- **Effect of changing this setting:**
  - *When enabled (YES):* The module will automatically send order details (product IDs, order value, order ID) to the Allani platform every time a customer successfully completes an order on your PrestaShop store. This is essential for Allani to track your sales.
  - *When disabled (NO):* The module will cease sending any order data to Allani. This means Allani will not receive real-time updates on your sales, potentially impacting your analytics and reporting on their platform.
- **Recommended value:** **YES**. To fully utilize the Allani tracking service, this setting should always be enabled.
- **Merchant scenario / example:** If you’ve just signed up for Allani and want to start tracking your sales immediately, you would enable this setting. If you temporarily want to pause data transmission to Allani for maintenance or testing purposes, you might disable it, but remember to re-enable it afterward.

#### Other Internal Settings (Not directly configurable by merchant)

You might see other configuration keys like `mypresta_updates`, `update_`, `updatev_`, `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`. These are internal settings used by the module for its own update checks or to interact with PrestaShop’s core functionalities (like language handling). You do not need to configure these, and they are not exposed as user-editable options.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Order Identification | YES | Controls whether order data is sent to Allani. **Enable** for Allani tracking. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve installed the module, but I don’t see any changes on my store. Is it working?**
A: Yes, this is normal! The Allani tracking module works entirely in the background. It doesn’t add any visible elements to your store’s front office. Its function is to send data to Allani after an order is placed. To confirm it’s working, place a test order and then check your Allani account for the new order data.

**Q: Allani isn’t receiving my order data. What should I check?**
A:

1. **Module Enabled:** Go to **Modules > Module Manager**, find “Allani tracking”, and ensure it’s installed and enabled.
2. **Configuration Setting:** Click “Configure” for the module and make sure “Order Identification” is set to **YES**.
3. **Clear Cache:** Sometimes, PrestaShop’s cache can prevent new settings from taking effect. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions).
4. **Allani Account:** Double-check your Allani account settings or contact Allani support to ensure your store is correctly linked on their end.
5. **PrestaShop Version:** Ensure you downloaded the correct module version for your PrestaShop installation (e.g., 1.7.x, 1.6.x).

**Q: Will this module slow down my store?**
A: No, the impact on your store’s performance is negligible. The tracking script is only executed on the order confirmation page, which is typically the last step in the customer journey. The data transfer is quick and asynchronous, meaning it won’t hold up the page load for your customers.

**Q: Does this module support multi-language or multi-store setups?**
A: The module primarily sends numerical and product ID data, which is language-agnostic. For multi-store, as long as the module is enabled and configured for each store context where you want to track orders, it should function correctly.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The `Allani tracking` module is a lightweight PrestaShop module designed for a single purpose: sending order confirmation data to the Allani platform. It follows a standard PrestaShop module structure, primarily utilizing hooks to inject its tracking logic. The core functionality resides within the main module class (`allanitracking.php`), which handles installation, uninstallation, configuration, and hook registration. It does not introduce custom controllers, models, or complex JavaScript/CSS assets, focusing solely on data transmission via a Smarty template injected into the `displayOrderConfirmation` hook.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. The module’s front-office logic is handled directly within the `displayOrderConfirmation` hook via a Smarty template.
- **Back-Office Admin Controllers**: None. Configuration is managed directly through the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)

- No custom classes or `ObjectModel` definitions are introduced by this module. All logic is self-contained within `allanitracking.php`.

### 4.4 JavaScript Assets (`views/js/`)

- No custom JavaScript files are included or used by this module. The tracking script is embedded directly into the `displayOrderConfirmation.tpl` template.

### 4.5 CSS Stylesheets (`views/css/`)

- No custom CSS files are included or used by this module, as it has no visible front-office components.

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses Smarty templates to inject the tracking script into the front office.

- **Hook templates (`views/templates/hook/`)**:

  - `allanitracking/views/templates/hook/displayOrderConfirmation.tpl`
    - **Hook**: `displayOrderConfirmation`
    - **Purpose**: This template is rendered on the order confirmation page (after a successful purchase). It contains the core logic for sending order data to Allani. It accesses the `$order` and `$products` Smarty variables, which are passed by PrestaShop to this hook, to extract `orderValue`, `orderID`, and `productIds`. The template then constructs and executes the necessary JavaScript to transmit this data to the Allani platform.
  - `allanitracking/views/templates/hook/header.tpl`
    - **Hook**: `displayHeader` (or `header` in older versions)
    - **Purpose**: This template is typically used to include global JavaScript or CSS in the `<head>` section of the page. In this module’s context, it might be used to include any necessary global Allani scripts or meta tags, though the primary data transmission is handled by `displayOrderConfirmation.tpl`. Given the module’s description, it likely includes a minimal setup or a placeholder.
- **Admin templates (`views/templates/admin/`)**: None.
- **Front-office templates (`views/templates/front/`)**: None.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any custom SQL tables.
  - It stores its configuration in the `ps_configuration` table, specifically the `ALLANI_ORDER_TRACK` key.
  - It also uses standard PrestaShop configuration keys for update checks (`mypresta_updates`, `update_`, `updatev_`).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` / `header` | In the `<head>` section of every front-office page. | Potentially used for global Allani script initialization or meta tags. |
| `displayOrderConfirmation` | On the order confirmation page, after a successful purchase. | **Primary hook for this module.** Injects the JavaScript code to send order details (product IDs, order value, order ID) to the Allani platform. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Allani tracking” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist you with any technical issues or questions you may have regarding the module’s functionality.
