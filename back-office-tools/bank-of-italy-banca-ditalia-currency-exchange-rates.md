---
title: "Bank of Italy (Banca dItalia) - currency exchange rates - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Bank of Italy (Banca dItalia) - currency exchange rates PrestaShop module by MyPresta.eu."
sidebar:
  label: "Bank of Italy (Banca dItalia) - currency exchange rates - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Bank of Italy (Banca dItalia) - currency exchange rates Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/bank-of-italy-banca-ditalia-currency-exchange-rates.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/bank-of-italy-banca-ditalia-currency-exchange-rates/)
>
> ---


# Bank of Italy (Banca dItalia) - currency exchange rates

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for external API communication, which are almost universally available on modern hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click the “Configure” button next to the module name in the Module Manager. This will take you to the main configuration screen for the “Bank of Italy (Banca dItalia) - currency exchange rates” module.

#### General Settings

- **What this setting does:** This section allows you to control how the module updates your currency exchange rates and manage its core functionality.
- **Effect of changing this setting:** These settings directly impact the accuracy and frequency of your store’s exchange rates.

#### Specific Settings & Options:

1. **“Update rates” button**

   - **What this setting does:** This is a manual trigger to immediately fetch the latest exchange rates from the Bank of Italy and apply them to your store’s currencies.
   - **Effect of changing this setting:**
     - *When clicked:* The module will connect to the Bank of Italy’s data source, retrieve the most recent Euro reference rates, and update all active currencies in your PrestaShop store (except your default currency, which is usually EUR). This is useful for testing or for an immediate update outside of your scheduled cron jobs.
   - **Recommended value:** Click this button after initial setup to ensure your rates are current. Use it manually whenever you need an immediate update.
   - **Merchant scenario / example:** You’ve just added a new currency to your store, or there’s been a significant market fluctuation, and you want to ensure your prices are instantly updated before a major sale.
2. **“CRON URL for automatic updates” field**

   - **What this setting does:** This field displays a unique URL that you can use with your hosting provider’s “cron job” service. A cron job is a scheduled task that runs automatically at specified intervals (e.g., once a day, every hour).
   - **Effect of changing this setting:**
     - *When configured with your hosting provider:* Your store’s exchange rates will be automatically updated at the frequency you define in your cron job settings, without you needing to manually click any buttons. This ensures your rates are always fresh.
     - *When not configured:* You will need to manually click the “Update rates” button to refresh your exchange rates.
   - **Recommended value:** Copy this URL and set up a cron job on your server to run at least once every 24 hours. A daily update is usually sufficient for most e-commerce stores.
   - **Merchant scenario / example:** You want your store’s exchange rates to be updated every morning at 3 AM, ensuring all prices are current for the start of the business day, without you having to remember to do it.
3. **“Add margin to exchange rates (%)” field**

   - **What this setting does:** This allows you to add a percentage margin to the fetched exchange rates. For example, if the official rate is 1 EUR = 1.10 USD, and you set a 2% margin, the module will use 1 EUR = 1.078 USD (1.10 \* 0.98) or 1 EUR = 1.122 USD (1.10 \* 1.02) depending on the direction of conversion. This helps cover potential transaction fees, currency conversion costs, or simply to give you a slight buffer.
   - **Effect of changing this setting:**
     - *When set to a positive value (e.g., 2):* The module will adjust the fetched exchange rates by that percentage. This typically means you’ll get slightly more local currency for your Euro-based products, or slightly fewer Euros for local currency products, helping to protect your profit margins.
     - *When set to 0 (or empty):* The module will use the exact exchange rates provided by the Bank of Italy without any adjustment.
   - **Recommended value:** Start with 0. If you experience issues with profitability due to currency fluctuations or transaction fees, consider adding a small margin (e.g., 1-3%).
   - **Merchant scenario / example:** Your payment gateway charges a 1.5% fee for international transactions. By setting a 2% margin, you can absorb this cost and ensure your profitability isn’t eroded by currency conversions.
4. **“Check for module updates” switch**

   - **What this setting does:** This toggle controls whether the module periodically checks MyPresta.eu for newer versions of the module.
   - **Effect of changing this setting:**
     - *When enabled (YES):* The module will occasionally connect to MyPresta.eu to see if a newer version is available. If an update is found, you’ll see a notification in your PrestaShop back office, prompting you to download and install the latest version. This helps you stay current with bug fixes, new features, and compatibility updates.
     - *When disabled (NO):* The module will not check for updates, and you will not be notified of new versions. You would need to manually check your MyPresta.eu account for updates.
   - **Recommended value:** **YES**. Keeping your modules updated is crucial for security, performance, and compatibility with future PrestaShop versions.
   - **Merchant scenario / example:** You want to be automatically informed when a new version of the module is released, so you can benefit from the latest improvements and ensure your store remains secure and functional.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | “Update rates” button | Click after setup / manually as needed | Immediately fetches and applies latest exchange rates from Bank of Italy. |
| Module Configuration Page | “CRON URL for automatic updates” | Copy and configure on hosting | Automates daily/hourly exchange rate updates, ensuring constant accuracy. |
| Module Configuration Page | “Add margin to exchange rates (%)” | 0 (or 1-3% if needed) | Adds a percentage buffer to exchange rates to cover fees or protect profit margins. |
| Module Configuration Page | “Check for module updates” | YES | Notifies you of new module versions for bug fixes, features, and compatibility. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My exchange rates aren’t updating automatically. What should I do?**
A1: This is almost always related to the cron job setup.
- **Check your hosting:** Log in to your hosting control panel (cPanel, Plesk, etc.) and verify that the cron job for the module’s URL is correctly set up and running at the specified intervals. Ensure the URL copied from the module configuration is exact.
- **Test the URL manually:** Copy the “CRON URL for automatic updates” from the module configuration and paste it directly into your web browser. If it runs successfully, you should see a simple “OK” message or similar. If you see an error, there might be a server-side issue or a problem with the URL itself.
- **Check module status:** Ensure the module is enabled in your PrestaShop back office.

**Q2: I clicked “Update rates” but my prices in other currencies didn’t change.**
A2:
- **Clear PrestaShop Cache:** Go to **Advanced Parameters > Performance** in your PrestaShop back office and click “Clear cache” (or “Clear Smarty cache” in older versions). PrestaShop often caches currency conversions.
- **Verify active currencies:** Ensure the currencies you expect to be updated are actually enabled in **International > Currencies**. The module only updates active currencies.
- **Check default currency:** The module updates *other* currencies relative to your default currency (usually EUR). If your default currency is not EUR, the module will still fetch EUR rates and convert from there. Ensure your default currency is correctly set.

**Q3: Can I set different margins for different currencies?**
A3: No, the “Add margin to exchange rates (%)” setting applies a single, uniform percentage margin to *all* exchange rates fetched by the module. If you require highly specific, per-currency margins, you would need a custom development solution or a more advanced currency management module.

**Q4: The module says it fetches rates from Banca d’Italia. Is this reliable?**
A4: Yes, Banca d’Italia (Bank of Italy) is a central bank within the European System of Central Banks (ESCB) and provides official Euro reference rates. These rates are highly reliable and widely used for financial transactions across Europe.

**Q5: After updating the module, my store looks a bit off or I see errors.**
A5:
- **Clear Cache:** Always clear your PrestaShop cache (**Advanced Parameters > Performance**) after any module update.
- **Browser Cache:** Clear your web browser’s cache and cookies, or try accessing your store in incognito/private mode.
- **Revert (if necessary):** If the issue persists, you may need to temporarily disable or uninstall the module and revert to a previous backup of your store. Then, contact MyPresta.eu support with details of the issue.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Bank of Italy (Banca dItalia) - currency exchange rates” module (`birates`) is a lightweight PrestaShop module designed to automate currency rate updates. It follows a standard PrestaShop MVC pattern where applicable, primarily focusing on a single configuration interface and a front controller for cron job execution. It leverages PrestaShop’s `Currency` `ObjectModel` to update exchange rates. The core logic resides in the main module file, handling installation, uninstallation, configuration, and the rate fetching process.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `controllers/front/cronjob.php`
    - **Class name & parent class**: `BiratesCronjobModuleFrontController` extends `ModuleFrontController`.
    - **Responsibility**: This controller is designed to be called by an external cron job. Its `initContent()` method (or similar logic within `postProcess()`) triggers the `updateRates()` method of the main `birates` module. It does not render any visual content to the user; its purpose is purely to execute the rate update logic in the background. It typically outputs a simple success message or status.
  - `controllers/front/index.php`
    - **Class name & parent class**: `BiratesIndexModuleFrontController` extends `ModuleFrontController`.
    - **Responsibility**: This is a placeholder or fallback front controller. In many modules, `index.php` controllers are used to define a default route or handle cases where a specific action isn’t provided. For this module, it likely serves as a basic entry point but the primary functionality for rate updates is handled by `cronjob.php`. It might redirect or simply display a minimal page.
- **Back-Office Admin Controllers**:

  - No dedicated admin controllers are present in this module. All back-office configuration is handled directly within the `getContent()` method of the main `birates.php` module file.

### 4.3 Core Classes & Models (`classes/`)

No custom classes or `ObjectModel` definitions are present in the `classes/` directory. The module directly interacts with PrestaShop’s core `Currency` `ObjectModel` to update existing currency exchange rates.

### 4.4 JavaScript Assets (`views/js/`)

No custom JavaScript files are present in the module.

### 4.5 CSS Stylesheets (`views/css/`)

No custom CSS files are present in the module.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Admin templates (`views/templates/admin/`)**:

  - `birates/views/admin.tpl`
    - **Purpose**: This template is rendered by the `getContent()` method of the main `birates.php` module file. It displays the entire configuration form for the module in the PrestaShop back office.
    - **Contents**: It includes the “Update rates” button, the CRON URL field, the “Add margin to exchange rates (%)” input, and the “Check for module updates” switch. It uses standard PrestaShop form helpers and styling.
- **Hook templates (`views/templates/hook/`)**: None.
- **Front-office templates (`views/templates/front/`)**: None.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any custom SQL tables.
  - It stores its configuration settings (e.g., `mypresta_updates`, `update_`, `updatev_`, `currency_`) in the `ps_configuration` table (or `_configuration` depending on your table prefix). These keys are typically prefixed with the module’s name or a unique identifier.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Not directly used for visual output, but could be used for loading assets (though none are present). |
| `displayRightColumn` | In the right column of front-office pages. | Not used for visual output. |
| `displayLeftColumn` | In the left column of front-office pages. | Not used for visual output. |
| `displayFooter` | At the bottom of every front-office page. | Not used for visual output. |
| `displayProductExtraContent` | On the product page, typically below the main product information. | Not used for visual output. |
| `actionUpdateCurrency` | After a currency has been updated. | The module itself *triggers* currency updates, but does not explicitly hook into this for its own logic. |
| `actionModuleInstall` | During module installation. | Used to set default configuration values and register hooks. |
| `actionModuleUninstall` | During module uninstallation. | Used to clean up configuration values and unregister hooks. |

*Note: The module’s primary function (updating rates) is initiated by its `cronjob.php` front controller, which is called externally, rather than through a standard PrestaShop hook.*

## 5. Official Support & Updates

For official support, updates, and to download the latest version of the “Bank of Italy (Banca dItalia) - currency exchange rates” module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and configuration.
