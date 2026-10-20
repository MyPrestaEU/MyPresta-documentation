---
title: "Kelkoo sales tracking integration - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Kelkoo sales tracking integration PrestaShop module by MyPresta.eu."
sidebar:
  label: "Kelkoo sales tracking integration"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Kelkoo sales tracking integration Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/kelkoo-sales-tracking-integration.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/kelkoo-sales-tracking-integration/)
>
> ---


# Kelkoo sales tracking integration

## 1. Requirements & Compatibility
- **Supported PrestaShop Versions**: PrestaShop 8.x, 1.7.x, 1.6.x, 1.5.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for most PrestaShop modules and are usually available on any modern hosting environment. No special or unusual requirements for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)
After installation, click "Configure" next to the "Kelkoo sales tracking integration" module. You will be presented with a simple configuration screen.

#### Kelkoo Tracking ID
-   **What this setting does:** This is the most crucial setting. It's where you enter your unique tracking ID provided by Kelkoo. This ID tells Kelkoo which merchant (your store) the sales data belongs to.
-   **Effect of changing this setting:**
    -   *When correctly entered:* The module will use this ID to send sales data to your specific Kelkoo account, allowing Kelkoo to attribute sales to your campaigns.
    -   *When left empty or incorrect:* Sales tracking will not work correctly, and Kelkoo will not receive data about purchases made through their platform, making it impossible to measure your campaign performance.
-   **Recommended value:** Enter the exact tracking ID provided to you by Kelkoo. This is usually a numerical or alphanumeric string.
-   **Merchant scenario / example:** You've set up a merchant account with Kelkoo. They will provide you with a unique "Kelkoo Tracking ID" or "Merchant ID." You must copy and paste this ID precisely into this field. Without it, the integration is incomplete.

#### Enable Tracking
-   **What this setting does:** This is a simple ON/OFF switch to activate or deactivate the Kelkoo sales tracking functionality across your store.
-   **Effect of changing this setting:**
    -   *When enabled (YES):* The module will actively inject the necessary tracking scripts and send sales data to Kelkoo on the order confirmation page.
    -   *When disabled (NO):* The module will cease all tracking activities. No scripts will be injected, and no sales data will be sent to Kelkoo.
-   **Recommended value:** YES. You should only disable this if you temporarily want to stop tracking sales via Kelkoo or are troubleshooting.
-   **Merchant scenario / example:** You've completed your Kelkoo setup and want to start tracking sales immediately. Set this to YES. If you decide to pause your Kelkoo campaigns or need to perform maintenance, you might temporarily set it to NO.

### 2.2 Configuration Quick Reference Table
| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|---|
| Module Configuration | Kelkoo Tracking ID | Your Kelkoo ID | Unique identifier for your Kelkoo merchant account. Essential for sales attribution. |
| Module Configuration | Enable Tracking | YES | Activates/deactivates the Kelkoo sales tracking functionality. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I've configured the module, but Kelkoo isn't showing any sales. What should I do?**
A:
1.  **Double-check your Kelkoo Tracking ID:** Ensure it's entered precisely as provided by Kelkoo, with no extra spaces or characters.
2.  **Ensure "Enable Tracking" is YES:** This switch must be active for the module to work.
3.  **Clear PrestaShop Cache:** Go to **Advanced Parameters > Performance** and click "Clear cache" (or "Clear Smarty cache" in older versions). Sometimes, cached content can prevent new module settings from taking effect.
4.  **Make a test purchase:** Complete a full order on your store to trigger the tracking.
5.  **Contact Kelkoo Support:** If all settings are correct and you've cleared the cache, reach out to Kelkoo's support team. They can often check their end to see if any data is being received or if there's an issue with your account setup on their platform.

**Q: Will this module slow down my website?**
A: No, the module is very lightweight. It only injects a small, non-blocking JavaScript snippet into the header and sends data on the order confirmation page. This process is optimized not to impact your store's loading speed or customer experience.

**Q: Does this module work with multi-store setups?**
A: Yes, the module should work correctly in a multi-store environment. You will configure the Kelkoo Tracking ID for each store individually if they have separate Kelkoo accounts, or use the same ID if you're tracking all stores under one Kelkoo account.

**Q: I'm using a custom theme. Will this module still work?**
A: Yes, the module uses standard PrestaShop hooks (`displayHeader`, `displayOrderConfirmation`) which are almost universally present in all well-coded themes. It doesn't rely on specific theme elements, so it should be compatible with custom themes. If you encounter issues, ensure your custom theme correctly implements these core PrestaShop hooks.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview
The "Kelkoo sales tracking integration" module is a straightforward PrestaShop module designed to integrate Kelkoo's sales tracking pixel. It primarily leverages PrestaShop's hook system to inject a global tracking script into the header and a conversion tracking script on the order confirmation page. It follows a basic PrestaShop module structure, with its core logic contained within the main module file and template files for hook rendering. There are no custom controllers, models, or complex JavaScript/CSS assets beyond what's necessary for the tracking pixel.

### 4.2 Controllers (`controllers/`)
- **Front-Office Controllers**: None. All front-office functionality is handled via hooks within the main module file.
- **Back-Office Admin Controllers**: None. Configuration is handled directly by the `getContent()` method in the main module file.

### 4.3 Core Classes & Models (`classes/`)
- No custom classes or `ObjectModel` definitions are present in this module. All logic resides within the `Kelkoo.php` (or `index.php` in older structures) main module file.

### 4.4 JavaScript Assets (`views/js/`)
- No dedicated JavaScript files are included in the module. The necessary Kelkoo tracking script is dynamically generated and injected directly into the HTML via Smarty templates or the `displayHeader` hook.

### 4.5 CSS Stylesheets (`views/css/`)
- No dedicated CSS files are included in the module. The module has no visual front-office components and its back-office configuration uses standard PrestaShop form styling.

### 4.6 Smarty Template Structure (`views/templates/`)
- **Hook templates (`views/templates/hook/`)**:
    *   `kelkoo/views/templates/hook/displayOrderConfirmation.tpl`:
        *   **Hook**: `displayOrderConfirmation`
        *   **Purpose**: This template is rendered on the order confirmation page after a successful purchase. It's responsible for generating the Kelkoo sales tracking pixel (KST) with dynamic order details (order ID, total, product details). It retrieves order information passed to the hook and formats it according to Kelkoo's specifications.
    *   `kelkoo/views/templates/hook/header.tpl`:
        *   **Hook**: `displayHeader`
        *   **Purpose**: This template is rendered within the `<head>` section of every page. It's intended to include any global Kelkoo tracking scripts or initializers that need to be present across the entire site, though for simple sales tracking, the primary logic is often in `displayOrderConfirmation`. It might contain a basic Kelkoo base pixel or a placeholder for future Kelkoo features.

- **Admin templates (`views/templates/admin/`)**: None. The configuration form is built directly within `getContent()` using PrestaShop's helper form classes.
- **Front-office templates (`views/templates/front/`)**: None.

### 4.7 Database Schema & Hooks Map
- **Database Tables**:
    *   The module does not create any custom SQL tables.
    *   Configuration settings (`Kelkoo Tracking ID`, `Enable Tracking`) are stored in the `ps_configuration` table (or `_configuration` prefix) using keys like `KELKOO_TRACKING_ID` and `KELKOO_ENABLED`.

- **Registered Hooks Table**:
  | Hook Name | Execution Timing | Technical Purpose |
  |---|---|---|
  | `displayHeader` | Renders in the `<head>` section of every page. | Injects global Kelkoo tracking scripts or base pixel. |
  | `displayOrderConfirmation` | Renders on the order confirmation page after a successful purchase. | Sends detailed sales data (order ID, amount, products) to Kelkoo for conversion tracking. |

## 5. Official Support & Updates
For official updates, technical support, and to access the latest versions of the "Kelkoo sales tracking integration" module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have regarding the module's functionality and integration.
