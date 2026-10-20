---
title: "Bank of Israel - currency exchange rates - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Bank of Israel - currency exchange rates PrestaShop module by MyPresta.eu."
sidebar:
  label: "Bank of Israel - currency exchange rates - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Bank of Israel - currency exchange rates Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/bank-of-israel-currency-exchange-rates.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/bank-of-israel-currency-exchange-rates/)
>
> ---


# Bank of Israel - currency exchange rates

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for fetching external data. Your hosting environment must also support CRON jobs for automated updates.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” to access the module’s settings. This is the main screen where you will set up how the module fetches and applies exchange rates.

#### **MyPresta.eu updates**

- **What this setting does:** This section provides information about updates from MyPresta.eu, including the current module version and available updates. It helps you keep your module current.
- **Effect of changing this setting:**
  - *When an update is available:* You will see a notification and a link to download the latest version from your MyPresta.eu account.
  - *When no update is available:* The section will simply show your current version.
- **Recommended value:** Always keep your modules updated to benefit from new features, bug fixes, and security improvements.
- **Merchant scenario / example:** Regularly check this section to ensure your module is up-to-date, especially after major PrestaShop version upgrades.

#### **Update interval**

- **What this setting does:** This determines how often the module attempts to fetch and update exchange rates from the Bank of Israel.
- **Effect of changing this setting:**
  - *Setting a shorter interval (e.g., 1 hour):* Exchange rates will be updated more frequently, ensuring your prices are always very close to real-time. This is good for highly volatile currencies or high-volume international sales.
  - *Setting a longer interval (e.g., 24 hours):* Exchange rates will be updated less frequently. This might be suitable if currency fluctuations are not a major concern for your business or if you prefer less frequent external calls.
- **Recommended value:** “24 hours” for most stores. If you have high sales volume with international customers and frequently changing currency rates, consider “12 hours” or “6 hours”.
- **Merchant scenario / example:** If you sell high-value electronics to international customers, you might choose “6 hours” to ensure your prices reflect the latest market conditions. For a local boutique with occasional international sales, “24 hours” is sufficient.

#### **Update margin (%)**

- **What this setting does:** This allows you to add a percentage margin to the exchange rates fetched from the Bank of Israel. This margin is applied on top of the official rate.
- **Effect of changing this setting:**
  - *Setting a positive margin (e.g., 2%):* Your converted prices in other currencies will be slightly higher than the direct official exchange rate, helping you cover potential transaction fees, currency conversion costs, or simply increase your profit margin.
  - *Setting a zero margin (0%):* Your prices will reflect the exact official exchange rate without any additional markup.
- **Recommended value:** “0” if you want exact official rates. A small positive value (e.g., “1” or “2”) is often recommended to cover potential banking fees or provide a buffer against minor fluctuations.
- **Merchant scenario / example:** If your payment gateway charges a 1.5% fee for international transactions, setting a “1.5” or “2” percent margin can help you absorb that cost without impacting your product’s base price in your default currency.

#### **Currencies to update**

- **What this setting does:** This is a list of all currencies currently active in your PrestaShop store. You can select which of these currencies should have their exchange rates automatically updated by this module.
- **Effect of changing this setting:**
  - *Selecting a currency (checkbox checked):* The module will fetch the exchange rate for this currency (relative to ILS) from the Bank of Israel and update it in your store.
  - *Deselecting a currency (checkbox unchecked):* The module will ignore this currency, and its exchange rate will *not* be automatically updated. You would need to update it manually if required.
- **Recommended value:** Select all currencies that you actively use for international sales and want to keep updated. Ensure your default currency (e.g., ILS) is correctly configured in PrestaShop.
- **Merchant scenario / example:** If you sell to customers in the US, Europe, and the UK, you would check the boxes for USD, EUR, and GBP. If you only sell locally in ILS and occasionally to the US, you might only check USD.

#### **CRON Job URL**

- **What this setting does:** This displays the unique URL that needs to be configured as a CRON job on your web server. A CRON job is a scheduled task that tells your server to visit this URL at regular intervals, triggering the module to fetch and update the exchange rates automatically.
- **Effect of changing this setting:** This is not a setting you change, but rather a URL you *use*.
  - *When the CRON job is correctly set up:* The module will run automatically at your specified “Update interval,” keeping your exchange rates current without any manual intervention.
  - *When the CRON job is NOT set up:* Exchange rates will *not* be updated automatically. You would have to manually visit this URL in your browser (which is not recommended for regular use) or manually update rates in PrestaShop.
- **Recommended value:** Copy this URL and set it up as a CRON job on your hosting panel (e.g., cPanel, Plesk, or via SSH). The frequency of the CRON job should match or be slightly more frequent than your “Update interval” setting. For example, if your update interval is 24 hours, set the CRON job to run once every 24 hours.
- **Merchant scenario / example:** After configuring all other settings, copy this URL and paste it into your hosting provider’s CRON job scheduler. Set it to run daily at a low-traffic time (e.g., 3 AM).

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | MyPresta.eu updates | N/A | Displays module version and update availability. |
| Module Configuration | Update interval | 24 hours | How often exchange rates are fetched (e.g., 6, 12, 24 hours). |
| Module Configuration | Update margin (%) | 0-2% | Adds a percentage markup to fetched exchange rates. |
| Module Configuration | Currencies to update | All active currencies | Selects which currencies to automatically update. |
| Module Configuration | CRON Job URL | N/A | URL to configure on your server for automated updates. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My exchange rates are not updating automatically. What should I do?**
A:

1. **Check CRON Job:** The most common reason is an incorrectly configured or missing CRON job. Double-check the CRON job URL provided in the module’s configuration and ensure it’s correctly set up on your hosting server to run at the desired frequency.
2. **Module Settings:** Verify that the “Update interval” is set and that the desired “Currencies to update” are checked in the module’s configuration.
3. **Server Access:** Ensure your server can make external requests to the Bank of Israel’s API. Sometimes firewalls or security settings can block this. Contact your hosting provider if you suspect this.
4. **PrestaShop Cache:** Clear your PrestaShop cache (Advanced Parameters > Performance > Clear cache) after making any changes to module settings.

**Q: Can I manually override an exchange rate after the module updates it?**
A: Yes, you can. After the module runs, the rates are stored in PrestaShop’s standard currency settings (International > Currencies). You can manually edit a specific currency’s exchange rate there. However, be aware that the next time the CRON job runs, it will overwrite your manual change with the latest rate from the Bank of Israel (plus your margin).

**Q: What happens if the Bank of Israel’s API is temporarily unavailable?**
A: If the module cannot fetch data, it will typically retain the last successfully updated exchange rates. It won’t delete or reset your rates to zero. It will simply try again during the next scheduled CRON job run.

**Q: My prices look slightly off after the update. Why?**
A:

1. **Update Margin:** Check the “Update margin (%)” setting in the module configuration. If you have a positive margin set, your prices will be slightly higher than the direct official rate.
2. **Rounding:** PrestaShop’s currency settings also have a “Decimal places” option. Ensure this is set appropriately for your currencies to avoid unexpected rounding issues.
3. **Base Currency:** Ensure your default currency in PrestaShop (International > Currencies) is correctly set as the Israeli Shekel (ILS) if that’s your base currency for these updates.

**Q: How do I set up a CRON job?**
A: This process varies by hosting provider. Generally, you’ll log into your hosting control panel (e.g., cPanel, Plesk). Look for a section named “Cron Jobs,” “Scheduled Tasks,” or “Automated Tasks.” You’ll need to add a new CRON job, specify the frequency (e.g., once daily), and paste the “CRON Job URL” provided by the module. If you’re unsure, contact your hosting provider’s support, providing them with the URL and desired frequency.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Bank of Israel - currency exchange rates” module (`boirates`) follows a standard PrestaShop module architecture. It leverages a main module class (`boirates.php`) for installation, uninstallation, and configuration handling. Exchange rate updates are primarily triggered via a front controller (`cronjob.php`) designed to be called by a server-side CRON job. The module fetches XML data from the Bank of Israel’s official API, parses it, and updates PrestaShop’s `ps_currency` table.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `controllers/front/cronjob.php`
    - **Class name**: `BoiratesCronjobModuleFrontController` (extends `ModuleFrontController`)
    - **Responsibility**: This controller is designed to be invoked by an external CRON job. It contains the core logic for fetching exchange rates from the Bank of Israel’s API, parsing the XML response, applying the configured margin, and updating the `ps_currency` table in PrestaShop. It does not render any front-office content but performs background data processing. It’s crucial for the automated functionality of the module.
  - `controllers/front/index.php`
    - **Class name**: `BoiratesIndexModuleFrontController` (extends `ModuleFrontController`)
    - **Responsibility**: This is a placeholder or default front controller. In many modules, if a specific action isn’t routed, `index.php` might be called. For this module, its primary function is likely to prevent directory listing or provide a minimal default response if accessed directly without specific parameters. The core logic resides in `cronjob.php`.
- **Back-Office Admin Controllers**:

  - None. All configuration is handled directly within the main module’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

- None. The module’s logic is primarily encapsulated within the main `boirates.php` file and the `BoiratesCronjobModuleFrontController`. Data interaction is direct with PrestaShop’s `Currency` class and `ps_configuration` table.

### 4.4 JavaScript Assets (`views/js/`)

- None. The module does not include any custom JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)

- None. The module does not include any custom CSS files.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Admin templates (`views/templates/admin/`)**:
  - `views/templates/admin/admin.tpl`
    - **Purpose**: This template is rendered by the `getContent()` method of the `boirates.php` module file. It defines the structure and layout of the module’s configuration page in the PrestaShop Back Office. It includes the form elements for `mypresta_updates`, `update_`, `updatev_`, and `currency_` settings, as well as displaying the CRON job URL.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any custom SQL tables.
  - It interacts with the standard PrestaShop `ps_configuration` table to store its settings (e.g., `BOIRATES_UPDATE_INTERVAL`, `BOIRATES_UPDATE_MARGIN`, `BOIRATES_CURRENCIES_TO_UPDATE`).
  - It updates the `exchange_rate` column in the `ps_currency` table for selected currencies.
- **Registered Hooks Table**:
  The module does not explicitly register any front-office display hooks (like `displayHeader`, `displayRightColumn`, `displayProductButtons`, `displayFooter`) in its `install()` method for rendering content. Its primary function is background data processing.
  It likely uses internal PrestaShop hooks for its core functionality, such as:

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `actionModuleInstall` | During module installation | Sets up default configuration values and registers necessary elements. |
  | `actionModuleUninstall` | During module uninstallation | Cleans up configuration values. |
  | `displayBackOfficeHeader` | Renders content in the Back Office header | Potentially used for adding CSS/JS or notifications, though not explicitly detected in the inventory. |

## 5. Official Support & Updates

For official support, updates, and to download the latest versions of the “Bank of Israel - currency exchange rates” module, please visit your customer account at [MyPresta.eu](https://mypresta.eu). Our support team is available to assist with any issues or questions regarding the module’s functionality and compatibility.
