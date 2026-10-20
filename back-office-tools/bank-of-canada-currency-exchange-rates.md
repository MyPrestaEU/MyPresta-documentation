---
title: "Bank of Canada - currency exchange rates - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Bank of Canada - currency exchange rates PrestaShop module by MyPresta.eu."
sidebar:
  label: "Bank of Canada - currency exchange rates - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Bank of Canada - currency exchange rates Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/bank-of-canada-currency-exchange-rates.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/bank-of-canada-currency-exchange-rates/)
>
> ---


# Bank of Canada - currency exchange rates

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for fetching external data, which are almost universally available on modern hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” to access the module’s settings. This is the main screen where you will manage how exchange rates are updated.

#### **1. Update Exchange Rates Manually**

- **What this setting does:** This is a button that, when clicked, immediately triggers the module to fetch the latest exchange rates from the Bank of Canada and update them in your store.
- **Effect of changing this setting:**
  - *When clicked:* The module connects to the Bank of Canada, retrieves the most current rates, calculates cross-rates, and applies them to your store’s currencies. A confirmation message will usually appear.
- **Recommended value:** Use this button for immediate updates or to test the module after initial setup. For ongoing updates, the CRON job (explained below) is recommended.
- **Merchant scenario / example:** You’ve just launched a new product and want to ensure all international prices are absolutely current before a major marketing push. Click this button to force an immediate update.

#### **2. CRON Job URL**

- **What this setting does:** This field displays a unique URL that, when accessed, triggers the module to update exchange rates automatically. This URL is designed to be used with a “CRON job” on your web server.
- **Effect of changing this setting:**
  - *When the URL is accessed (by a CRON job):* The module performs the same rate update process as clicking the manual update button, but it does so automatically at scheduled intervals.
- **Recommended value:** Copy this URL and set it up as a CRON job on your hosting server.
- **Merchant scenario / example:** You want your exchange rates to update every day at 3 AM. You copy this URL and configure your hosting panel (cPanel, Plesk, etc.) to visit this URL daily at 3 AM. This ensures your rates are always fresh without you having to lift a finger.

#### **3. Exchange Rate Margin (%)**

- **What this setting does:** This allows you to add a percentage margin to the exchange rates fetched from the Bank of Canada. For example, if the BOC rate is 1.20 and you set a 2% margin, your store will use a rate of 1.224 (1.20 \* 1.02).
- **Effect of changing this setting:**
  - *When set to a positive value (e.g., 2):* All converted prices in your store will be slightly higher, reflecting the added margin. This can help cover transaction fees, currency conversion costs, or simply increase your profit margin on international sales.
  - *When set to 0 (or left empty):* The module will use the exact exchange rates provided by the Bank of Canada without any additional markup.
- **Recommended value:** Start with 0% and adjust based on your business needs, payment gateway fees, and desired profit margins. A common practice is 1-3% to cover potential costs.
- **Merchant scenario / example:** Your payment gateway charges a 1.5% fee for international currency conversions. You set the “Exchange Rate Margin” to 1.5% to ensure this cost is covered in your product pricing, rather than eroding your profit.

#### **4. Last Update**

- **What this setting does:** This field displays the date and time of the last successful exchange rate update performed by the module.
- **Effect of changing this setting:** This is a read-only field and cannot be changed. It serves as an informational indicator.
- **Recommended value:** Monitor this field to ensure your CRON job is running correctly and rates are being updated regularly.
- **Merchant scenario / example:** You notice your international prices seem outdated. You check “Last Update” and see it hasn’t updated in a week, indicating a potential issue with your CRON job setup.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Update Exchange Rates Manually (Button) | Click to update | Forces an immediate update of all currency exchange rates from BOC. |
| Module Configuration | CRON Job URL | Copy & configure on server | Provides a URL for automated, scheduled updates via your hosting’s CRON service. |
| Module Configuration | Exchange Rate Margin (%) | 0% | Adds a percentage markup to the fetched exchange rates, affecting all converted prices. |
| Module Configuration | Last Update | Read-only | Displays the timestamp of the last successful exchange rate update. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My exchange rates aren’t updating automatically. What should I do?**
A1: This is almost always a CRON job issue.
- **Check your hosting panel:** Log in to your hosting account (cPanel, Plesk, etc.) and verify that the CRON job is correctly set up with the exact URL provided by the module. Ensure the frequency is correct (e.g., daily).
- **Verify the CRON command:** The command usually looks something like `wget -O /dev/null "YOUR_CRON_URL_HERE"` or `curl "YOUR_CRON_URL_HERE"`. Make sure there are no typos.
- **Check “Last Update” in the module:** If this date is old, it confirms the CRON isn’t running.
- **Manually run the CRON URL:** Copy the CRON URL from the module configuration and paste it into your browser. If it updates, then the URL itself is fine, and the issue is purely with your hosting’s CRON setup.

**Q2: Prices in other currencies seem too high/low compared to the default currency.**
A2:
- **Check your “Exchange Rate Margin (%)”:** If this is set too high, prices will be inflated. If it’s negative (though not recommended), prices would be lower.
- **Verify your default currency:** Ensure your PrestaShop store’s default currency (Localization > Currencies) is correctly set to your primary operating currency (e.g., CAD if you’re fetching from Bank of Canada). The module calculates rates relative to your default currency.
- **Clear PrestaShop Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes old prices can be cached.

**Q3: The module says “Last Update” was successful, but I don’t see changes on the front office.**
A3:
- **Clear PrestaShop Cache:** This is the most common reason. Always clear your cache after any significant data update in PrestaShop.
- **Check browser cache:** Try clearing your browser’s cache or viewing your store in an incognito/private window to rule out local caching issues.
- **Verify currency selection:** Ensure you are actually viewing the store in the non-default currency where you expect to see the converted prices.

**Q4: Does this module work with custom themes?**
A4: Yes, this module works in the background by updating the core PrestaShop currency exchange rates. It does not directly interact with your theme’s visual elements, so it should be compatible with any custom theme. The theme’s currency selector will simply display prices based on the rates the module provides.

**Q5: Can I use this module if my default currency is not CAD?**
A5: Yes, you can. The module fetches base rates from the Bank of Canada (e.g., USD to CAD, EUR to CAD). It then intelligently calculates cross-rates relative to *your store’s default currency*. So, if your default currency is EUR, and BOC provides USD/CAD, the module will calculate EUR/USD, EUR/CAD, etc., based on the available data.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Bank of Canada - currency exchange rates” module (`bocrates`) is designed as a lightweight, automated solution for currency rate synchronization. It primarily leverages PrestaShop’s core `Currency` `ObjectModel` to update exchange rates. The module uses a front controller for CRON job execution, ensuring that the rate updates occur outside of the standard Back Office context, which is ideal for scheduled tasks. It adheres to the PrestaShop module architecture, utilizing `install()` and `uninstall()` methods for setup and cleanup, and `getContent()` for Back Office configuration.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `controllers/front/cronjob.php`
    - **Class name & parent class**: `BocratesCronjobModuleFrontController` extending `ModuleFrontController`.
    - **Responsibility**: This controller is the entry point for the automated CRON job. When accessed via its unique URL (provided in the module configuration), it triggers the `processUpdateExchangeRates()` method within the main module class. It’s designed to be called externally by a server-side CRON scheduler, not directly by a user. It typically outputs a simple success or error message.
  - `controllers/front/index.php`
    - **Class name & parent class**: `BocratesIndexModuleFrontController` extending `ModuleFrontController`.
    - **Responsibility**: This is a placeholder or default front controller. In many modules, if a specific action isn’t defined, `index.php` might be used. For this module, its primary function is likely to serve as a fallback or to ensure the module’s front-office routing is correctly established, even if it doesn’t perform a specific user-facing action. The `cronjob.php` is the active front controller for functionality.
- **Back-Office Admin Controllers**:

  - None. All Back Office configuration is handled directly within the `getContent()` method of the main `bocrates.php` module file.

### 4.3 Core Classes & Models (`classes/`)

- None. The module directly interacts with PrestaShop’s core `Currency` `ObjectModel` and `Configuration` class for data storage and manipulation.

### 4.4 JavaScript Assets (`views/js/`)

- None. The module does not use custom JavaScript for its functionality.

### 4.5 CSS Stylesheets (`views/css/`)

- None. The module does not use custom CSS for its functionality.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Admin templates (`views/templates/admin/`)**:
  - `bocrates/views/admin.tpl`
    - **Purpose**: This template is rendered by the `getContent()` method of the main `bocrates.php` module file. It displays the module’s configuration form in the PrestaShop Back Office. This includes the manual update button, the CRON job URL, the exchange rate margin input, and the last update timestamp.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create custom SQL tables.
  - It stores its configuration settings in the `ps_configuration` table using keys such as:
    - `BOCRATES_MARGIN`: Stores the percentage margin for exchange rates.
    - `BOCRATES_LAST_UPDATE`: Stores the timestamp of the last successful update.
    - `MYPRESTA_UPDATES`, `UPDATE_`, `UPDATEV_`: Related to MyPresta.eu’s update mechanism.
- **Registered Hooks Table**:
  The module primarily operates in the background and does not register hooks for front-office display. Its core functionality is triggered by the `cronjob` front controller.

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `actionModuleInstall` | During module installation | Sets default configuration values and registers necessary hooks (if any). |
  | `actionModuleUninstall` | During module uninstallation | Cleans up configuration values. |
  | `displayBackOfficeHeader` | Renders in the Back Office header | Potentially used for including assets or displaying notices in the admin panel (though no specific assets are listed). |

## 5. Official Support & Updates

For the latest updates, bug fixes, and dedicated technical support for the “Bank of Canada - currency exchange rates” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist merchants and developers with any issues or questions regarding the module’s functionality and integration.
