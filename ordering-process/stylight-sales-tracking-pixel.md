---
title: "Stylight - sales tracking pixel - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Stylight - sales tracking pixel PrestaShop module by MyPresta.eu."
sidebar:
  label: "Stylight - sales tracking pixel"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Stylight - sales tracking pixel Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/stylight-sales-tracking-pixel.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/stylight-sales-tracking-pixel/)
>
> ---


# Stylight - sales tracking pixel

## 1. Requirements & Compatibility
- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) typically available on most PrestaShop-compatible hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)
The "Stylight - sales tracking pixel" module is designed to be extremely simple to configure, requiring no specific settings from the merchant. Its functionality is primarily self-contained, automatically detecting and transmitting the necessary order data.

Upon navigating to the module's configuration page (Back Office > Modules > Module Manager > Stylight - sales tracking pixel > Configure), you will typically find a confirmation message indicating that the module is installed and active.

-   **What this screen does:** This page serves as a confirmation that the module is correctly installed and ready to track sales. There are no input fields or switches for you to adjust. The module automatically hooks into the order confirmation process and gathers all required data (Total Amount, Currency, Item Count, SKU numbers, Order ID) directly from PrestaShop's order details.
-   **Effect of changing this setting:** Since there are no configurable settings, there's nothing to change. The module works out-of-the-box once installed.
-   **Recommended value:** No action required.
-   **Merchant scenario / example:** After installing the module, you simply visit this page to confirm its presence. You do not need to enter any Stylight-specific IDs or keys, as the pixel itself is generic and designed to work with Stylight's system by sending standard e-commerce data.

### 2.2 Configuration Quick Reference Table
| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|---|
| Module Configuration Page | *(No user-configurable settings)* | N/A | Module automatically tracks sales data (total amount, currency, item count, SKUs, order ID) on the order confirmation page for Stylight.com. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I've installed the module, but I'm not seeing any sales reported in my Stylight account. What should I do?**
A: First, ensure the module is enabled in your PrestaShop Back Office. Then, try clearing your PrestaShop cache (Advanced Parameters > Performance > Clear cache). If the issue persists, perform a test order yourself. If still no data, contact MyPresta.eu support with details of your PrestaShop version and any other modules recently installed.

**Q: Does this module slow down my order confirmation page?**
A: The tracking pixel is very lightweight and loads asynchronously, meaning it generally does not significantly impact page load times or the customer experience. Its effect on performance is minimal.

**Q: Do I need to enter any Stylight ID or API key into the module?**
A: No, this module is designed to work out-of-the-box. It implements a standard Stylight tracking pixel that automatically sends the necessary order data without requiring specific merchant-entered IDs within the module configuration itself. Your Stylight account is linked to your domain, and their system identifies your store based on where the pixel originates.

**Q: Is this module compatible with custom themes?**
A: Yes, the module hooks into a standard PrestaShop hook (`displayOrderConfirmation`) which is typically present in all well-coded themes. It doesn't rely on specific theme elements, so it should work seamlessly with most custom themes.

**Q: I have multiple languages/currencies. Does the module track them correctly?**
A: Yes, the module is designed to automatically capture the order's total amount and currency as processed by PrestaShop, ensuring accurate tracking for multi-currency and multi-language stores.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview
The "Stylight - sales tracking pixel" module is a straightforward PrestaShop module primarily focused on front-office event hooking. It leverages the `displayOrderConfirmation` hook to inject a JavaScript-based tracking pixel onto the final order confirmation page. The module's logic is contained within its main PHP file, `index.php`, which handles installation, uninstallation, and the hook registration. Data collection is dynamic, pulling order details directly from the `Order` and `Product` objects available in the context of the order confirmation page.

### 4.2 Controllers (`controllers/`)
-   **Front-Office Controllers**: None. The module's front-office functionality is entirely handled by hooking into `displayOrderConfirmation` and rendering a Smarty template.
-   **Back-Office Admin Controllers**: None. The module has no dedicated admin interface beyond the standard module configuration page (`getContent()`).

### 4.3 Core Classes & Models (`classes/`)
-   None. The module does not define any custom classes or extend `ObjectModel`. All logic resides within the main `stylightpixel/index.php` file.

### 4.4 JavaScript Assets (`views/js/`)
-   None. The tracking pixel code is directly embedded within the Smarty template (`displayOrderConfirmation.tpl`) to ensure it fires immediately upon page load.

### 4.5 CSS Stylesheets (`views/css/`)
-   None. The module is purely functional and has no visual components or styling requirements.

### 4.6 Smarty Template Structure (`views/templates/`)
-   **Hook templates (`views/templates/hook/`)**:
    *   `stylightpixel/views/templates/hook/displayOrderConfirmation.tpl`
        *   **Hook**: `displayOrderConfirmation`
        *   **Purpose**: This template is rendered on the order confirmation page after a successful purchase. It contains the JavaScript code for the Stylight tracking pixel.
        *   **Data Available**: The template receives `$order` (an `Order` object) and `$products` (an array of `Product` objects associated with the order) from the `hookDisplayOrderConfirmation` method.
        *   **Output**: It outputs a `<script>` block that constructs the Stylight tracking pixel URL with dynamic parameters such as `order_id`, `total_amount`, `currency`, `item_count`, and `sku` for each product.

### 4.7 Database Schema & Hooks Map
-   **Database Tables**: The module does not create any custom database tables. It relies on standard PrestaShop tables (`ps_orders`, `ps_order_detail`, `ps_product`, etc.) to retrieve order information.
-   **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
|---|---|---|
| `displayOrderConfirmation` | Executed on the final order confirmation page after a successful purchase. | Injects the Stylight tracking pixel JavaScript into the page to send conversion data (order ID, total, currency, product SKUs, item count) to Stylight. |

## 5. Official Support & Updates
For official updates, technical support, and any further assistance with the "Stylight - sales tracking pixel" module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to help with module-related inquiries and ensure your tracking pixel functions correctly.
