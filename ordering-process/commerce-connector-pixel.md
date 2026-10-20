---
title: "Commerce Connector pixel - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Commerce Connector pixel PrestaShop module by MyPresta.eu."
sidebar:
  label: "Commerce Connector pixel - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Commerce Connector pixel Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/commerce-connector-pixel.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/commerce-connector-pixel/)
>
> ---


# Commerce Connector pixel

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient for PrestaShop modules. No special server configurations are usually needed for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Commerce Connector pixel” module to access its settings.

#### **Shop ident**

- **What this setting does:** This is the unique identifier provided to you by Commerce Connector for your specific shop or merchant account. It’s crucial for Commerce Connector to correctly attribute sales data to your account.
- **Effect of changing this setting:**
  - *When set to your correct Shop ID:* The pixel will fire with your unique identifier, allowing Commerce Connector to accurately track sales for your store.
  - *When incorrect or empty:* The pixel might not fire correctly, or sales data might be attributed to the wrong account, leading to inaccurate tracking and potentially lost marketing insights.
- **Recommended value:** Enter the exact “Shop ident” string provided by Commerce Connector. This is usually a combination of letters and numbers.
- **Merchant scenario / example:** Commerce Connector tells you your Shop ID is “MYSTORE12345”. You would enter “MYSTORE12345” into this field. Without it, Commerce Connector won’t know which store the sale came from.

#### **Log pixel launches**

- **What this setting does:** This setting controls whether the module records a log of every time the Commerce Connector pixel is launched (i.e., every time a customer reaches the order confirmation page and the pixel attempts to fire). This log can be useful for troubleshooting.
- **Effect of changing this setting:**
  - *When enabled (“On”):* The module will create a log file (usually in the module’s directory) detailing each pixel launch, including order details. This can help you verify if the pixel is firing as expected.
  - *When disabled (“Off”):* No log file will be generated, which is the standard setting for a production store to save disk space and processing.
- **Recommended value:** “Off” for a live production store. Only enable “On” temporarily if you are troubleshooting issues and need to verify pixel activity.
- **Merchant scenario / example:** You suspect the pixel isn’t tracking all sales. You enable “Log pixel launches” to “On”, make a test order, and then check the log file to see if your test order was recorded, confirming the pixel fired. Once confirmed, you switch it back to “Off”.

#### **Enable / Disable Module**

- **What this setting does:** This is a standard PrestaShop module toggle that allows you to globally enable or disable the entire Commerce Connector pixel module.
- **Effect of changing this setting:**
  - *When enabled:* The module will be active, and the Commerce Connector pixel will be injected into your order confirmation page, tracking sales.
  - *When disabled:* The module will be inactive, and the Commerce Connector pixel will NOT be present on your order confirmation page, meaning no sales will be tracked via this module.
- **Recommended value:** “On” if you are actively using Commerce Connector for sales tracking.
- **Merchant scenario / example:** You’ve completed your Commerce Connector integration and want to start tracking sales. You ensure this setting is “On”. If you temporarily pause your Commerce Connector campaigns, you might switch it to “Off” to prevent unnecessary pixel firing.

#### Other Configuration Keys (Internal)

The module also uses internal configuration keys like `mypresta_updates`, `update_`, `updatev_`, `COMCONN_SIDENT_`, `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`. These are typically for internal module management, update checks, and language handling within the PrestaShop back office. Merchants generally do not need to interact with these directly.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Shop ident | Your unique Commerce Connector ID | Crucial for attributing sales data to your specific Commerce Connector account. |
| Module Configuration | Log pixel launches | Off | Controls whether the module creates a log file of pixel firings. Enable for troubleshooting, disable for production. |
| Module Configuration | Enable / Disable Module | On | Globally activates or deactivates the entire module and its pixel tracking. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve installed the module, but Commerce Connector isn’t showing any sales. What should I do?**
A:

1. **Check “Shop ident”:** Go to the module configuration and ensure your “Shop ident” is entered correctly and exactly matches what Commerce Connector provided.
2. **Module Enabled:** Make sure the module is enabled in the configuration page.
3. **Clear Cache:** Go to **Advanced Parameters > Performance** in your PrestaShop back office and clear the Smarty cache and all caches.
4. **Test Purchase:** Perform a full test purchase on your store, going all the way to the order confirmation page.
5. **Enable Logging:** Temporarily enable “Log pixel launches” in the module configuration, perform another test purchase, and then check the `logFile.tpl` (or similar log file) within the module’s directory via FTP to see if the pixel launch was recorded.
6. **Contact Support:** If issues persist, contact MyPresta.eu support with details of your configuration and any log entries.

**Q: Will this module slow down my website?**
A: No. The Commerce Connector pixel is a very lightweight script that only loads on the order confirmation page. This page is typically reached after the main shopping experience, and the pixel’s execution is minimal, so it will not noticeably impact your store’s performance or loading speed for customers.

**Q: Can I use this module with other tracking pixels (e.g., Google Analytics, Facebook Pixel)?**
A: Yes, absolutely. This module is designed to integrate specifically with Commerce Connector. It operates independently and will not conflict with other tracking pixels or analytics scripts you have installed on your PrestaShop store.

**Q: Where can I find the log file if I enable “Log pixel launches”?**
A: If enabled, the log file is typically generated within the module’s directory. You would need FTP access to your server to navigate to `your_prestashop_root/modules/comconn/views/templates/hook/logFile.tpl` (or a similar path) to view its contents. Remember to disable logging once troubleshooting is complete.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The Commerce Connector pixel module (`comconn`) is a straightforward PrestaShop module designed to inject a specific JavaScript pixel onto the order confirmation page. It adheres to the PrestaShop module architecture, primarily leveraging the `displayOrderConfirmation` hook to render its tracking script. The module’s logic is contained within its main PHP file, with configuration managed via `getContent()` and templates for rendering the pixel and an optional log.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. The module directly hooks into `displayOrderConfirmation` and renders its content via a template.
- **Back-Office Admin Controllers**: None. All configuration is handled within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

- None. The module does not define any custom classes or `ObjectModel` instances. All logic is self-contained within `comconn.php`.

### 4.4 JavaScript Assets (`views/js/`)

- None. The module directly embeds the Commerce Connector pixel script within its Smarty template, rather than linking to external `.js` files.

### 4.5 CSS Stylesheets (`views/css/`)

- None. The module does not add any custom styling to the front or back office.

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses Smarty templates to render its output.

- **Hook templates (`views/templates/hook/`)**:

  - `comconn/views/templates/hook/displayOrderConfirmation.tpl`
    - **Hook**: `displayOrderConfirmation`
    - **Purpose**: This is the primary template responsible for rendering the Commerce Connector pixel script. It dynamically inserts the `Shop ident` (from `COMCONN_SIDENT` configuration) and order details (order ID, total, currency, products) into the JavaScript code that fires the pixel. This template is crucial for the module’s core functionality.
  - `comconn/views/templates/hook/logFile.tpl`
    - **Hook**: Not directly hooked, but used by the module’s internal logging mechanism.
    - **Purpose**: This template is used to format and store log entries when the “Log pixel launches” option is enabled. It records details of each pixel launch, including the timestamp, order ID, and the data sent to Commerce Connector. Developers can inspect this file via FTP for troubleshooting.
- **Admin templates (`views/templates/admin/`)**: None.
- **Front-office templates (`views/templates/front/`)**: None.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: The module does not create any custom database tables. It stores its configuration settings in the standard `ps_configuration` table.

  - `PS_CONFIGURATION` entries:
    - `COMCONN_SIDENT`: Stores the merchant’s Commerce Connector Shop ID.
    - `COMCONN_LOG`: Stores the boolean value (0 or 1) for enabling/disabling pixel launch logging.
    - `mypresta_updates`, `update_`, `updatev_`: Internal keys for module updates and versioning.
- **Registered Hooks Table**:

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `displayOrderConfirmation` | After a customer successfully completes an order and reaches the confirmation page. | Injects the Commerce Connector pixel script into the page to track the completed purchase. |

## 5. Official Support & Updates

For official updates, technical support, and further assistance with the “Commerce Connector pixel” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu). Our support team is available to help with any issues or questions you may have regarding the module’s functionality and integration.
