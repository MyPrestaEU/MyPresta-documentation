---
title: "CBR Currency Exchange & Rates (Bank of Russia) - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the CBR Currency Exchange & Rates (Bank of Russia) PrestaShop module by MyPresta.eu."
sidebar:
  label: "CBR Currency Exchange & Rates (Bank of Russia) - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy CBR Currency Exchange & Rates (Bank of Russia) Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/cbr-currency-exchange-rates-bank-of-russia.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/cbr-currency-exchange-rates-bank-of-russia/)
>
> ---


# CBR Currency Exchange & Rates (Bank of Russia)

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for external API communication, which are common on most web hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installing the module, click “Configure” to access its settings. This is the main screen where you will manage all aspects of the CBR Currency Exchange & Rates module.

#### **General Settings**

- **Enable automatic updates:**

  - **What this setting does:** This switch controls whether the module will automatically check for and apply new currency rates from the Central Bank of Russia.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The module will periodically fetch the latest exchange rates from the CBR website. This is crucial for keeping your RUB prices accurate without manual intervention. You will need to set up a CRON job (explained below) for this to work.
    - *When disabled (NO):* The module will not automatically update rates. You would have to manually update rates if this option is off, which defeats the purpose of the module.
  - **Recommended value:** YES
  - **Merchant scenario / example:** You want your prices in RUB to always reflect the current official exchange rate without having to log in daily and update them. Enabling this ensures your store is always up-to-date.
- **Update frequency (in hours):**

  - **What this setting does:** Defines how often the module should attempt to fetch new exchange rates from the CBR.
  - **Effect of changing this setting:**
    - *Setting a lower number (e.g., 1 hour):* Rates will be checked and updated more frequently. This is ideal if your business requires very precise, near real-time conversions.
    - *Setting a higher number (e.g., 24 hours):* Rates will be checked less frequently. This might be suitable if your prices don’t fluctuate dramatically or if you prefer to reduce server load from frequent external calls.
  - **Recommended value:** 24 (Daily updates are usually sufficient, as CBR rates change once a day).
  - **Merchant scenario / example:** You want to ensure your RUB prices are updated daily, so you set this to 24 hours. If you sell high-value items with tight margins, you might set it to 12 hours to capture mid-day changes if the CBR publishes them (though typically it’s once a day).
- **Margin on exchange rate (%):**

  - **What this setting does:** Allows you to add a percentage margin on top of the official CBR exchange rate. This can be used to cover transaction fees, currency conversion costs, or to slightly adjust your pricing strategy.
  - **Effect of changing this setting:**
    - *Setting a positive value (e.g., 2):* The module will increase the calculated exchange rate by 2%. This means that for every unit of your base currency, you will get slightly more RUB, effectively increasing your RUB prices.
    - *Setting 0 or leaving empty:* The module will use the exact official CBR exchange rate without any adjustment.
    - *Setting a negative value (e.g., -1):* The module will decrease the calculated exchange rate by 1%. This means you will get slightly less RUB for every unit of your base currency, effectively decreasing your RUB prices.
  - **Recommended value:** 0 (Unless you have specific business reasons to add a margin).
  - **Merchant scenario / example:** Your payment gateway charges a 1.5% fee for converting RUB to your base currency. You can set a margin of 1.5% here to offset that cost and maintain your profit margins.
- **CRON Job URL:**

  - **What this setting does:** This displays the unique URL that you need to set up as a CRON job on your hosting server. When this URL is accessed, it triggers the module to fetch and update the currency rates.
  - **Effect of changing this setting:** This is not a setting you change, but rather a URL you *use*.
    - *When correctly configured as a CRON job:* The module will automatically run in the background at your specified frequency (based on the “Update frequency” setting) to update rates.
    - *If not configured as a CRON job:* Automatic updates will not occur, even if “Enable automatic updates” is set to YES.
  - **Recommended value:** Copy this URL and set it up as a CRON job on your server.
  - **Merchant scenario / example:** After configuring the module, you copy this URL and add it to your hosting control panel’s CRON job scheduler to run daily at 3 AM, ensuring rates are updated before your business day starts.

#### **Currency Settings**

- **Currency to update:**
  - **What this setting does:** This dropdown allows you to select which specific currency in your PrestaShop store should be updated with CBR rates. It will list all currencies you have enabled in your PrestaShop Back Office.
  - **Effect of changing this setting:**
    - *Selecting “Russian Ruble (RUB)”:* The module will specifically target and update the exchange rate for the Russian Ruble against your store’s base currency using CBR data.
    - *Selecting any other currency:* This module is specifically designed for CBR rates, which are for the Russian Ruble. Selecting another currency might lead to unexpected behavior or no updates for that currency.
  - **Recommended value:** Russian Ruble (RUB)
  - **Merchant scenario / example:** Your store’s base currency is EUR, and you want to ensure that when customers select RUB, the conversion from EUR to RUB is accurate based on CBR. You select “Russian Ruble (RUB)” here.

#### **Save Button**

- **Save:**
  - **What this does:** Applies all the changes you’ve made on the configuration page.
  - **Effect of clicking:** Your settings will be stored in the database, and the module will operate according to the new parameters.
  - **Recommended action:** Always click “Save” after making any changes.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable automatic updates | YES | Controls automatic fetching of CBR rates. YES for hands-free updates. |
| Module Configuration | Update frequency (in hours) | 24 | How often the CRON job should trigger rate updates. 24 for daily. |
| Module Configuration | Margin on exchange rate (%) | 0 | Adds a percentage to the official rate. Use for fees or pricing strategy. |
| Module Configuration | CRON Job URL | (Unique URL) | URL to be configured on your server for automated updates. |
| Module Configuration | Currency to update | Russian Ruble (RUB) | Specifies which PrestaShop currency to update with CBR rates. Must be RUB. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My RUB prices are not updating automatically. What should I check?**
A1:

- **Is “Enable automatic updates” set to YES?** Check the module configuration.
- **Have you set up the CRON job on your hosting server?** This is the most common reason. Copy the “CRON Job URL” from the module configuration and add it to your hosting panel’s CRON scheduler. Ensure it’s set to run at least as frequently as your “Update frequency” setting.
- **Is the “Currency to update” set to “Russian Ruble (RUB)”?** The module is designed for RUB.
- **Check your server’s CRON job logs (if available):** Your hosting provider might offer logs that show if the CRON job is running and if it encountered any errors.
- **Clear PrestaShop cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” to ensure your store is displaying the latest data.

**Q2: The exchange rate seems incorrect or hasn’t changed in a while.**
A2:

- **Verify the official CBR rate:** Check the official Central Bank of Russia website for today’s exchange rate to confirm what it should be.
- **Check your “Update frequency”:** If it’s set to 24 hours, it will only update once a day.
- **Bank Holidays:** The CBR does not update rates on bank holidays. The module intelligently uses the last available rate. If there’s a long holiday period, the rate might remain static for several days.
- **CRON job issues:** Refer to Q1 for troubleshooting CRON jobs.

**Q3: Can I use this module for other currencies besides RUB?**
A3: No, this module is specifically designed to integrate with the Central Bank of Russia’s exchange rate data, which is primarily for the Russian Ruble. It will only accurately update the RUB currency in your store.

**Q4: I’ve changed my theme, and now the prices look odd in RUB.**
A4: This module only handles the *value* of the currency conversion. The *display* of prices (fonts, colors, layout) is handled by your PrestaShop theme. If prices look odd after a theme change, it’s likely a CSS or template issue with your new theme, not the module itself. You might need to adjust your theme’s styling.

**Q5: How do I manually update the rates if needed?**
A5: While the module is designed for automatic updates, you can force an update by manually visiting the CRON Job URL in your web browser. This will trigger the update process once. Remember to clear your PrestaShop cache afterward.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters working with the CBR Currency Exchange & Rates module.

### 4.1 Architecture Overview

The `cbrrates` module follows a standard PrestaShop module architecture, primarily utilizing the `Module` class for its core functionality and configuration. It leverages front controllers for CRON job execution and a simple `getContent()` method for back-office configuration. The module fetches XML data from the CBR API, parses it, and updates PrestaShop’s `Currency` exchange rates.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `controllers/front/cronjob.php`
    - **Class name & parent class**: `CbrratesCronjobModuleFrontController` extending `ModuleFrontController`.
    - **Responsibility**: This controller is designed to be called by an external CRON job. When accessed, it initiates the currency rate update process. It checks the `update_` and `updatev_` configuration values to determine if an update is due based on the configured frequency. It then calls the main module’s logic to fetch and apply the latest CBR rates. It outputs a simple success or error message.
  - `controllers/front/index.php`
    - **Class name & parent class**: `CbrratesIndexModuleFrontController` extending `ModuleFrontController`.
    - **Responsibility**: This is a placeholder or default front controller. In many modules, if no specific action is defined, `index.php` might serve as a fallback or simply redirect. For `cbrrates`, its primary function is likely minimal, as the core front-office interaction is via `cronjob.php`. It might be present to ensure a valid front-office route exists for the module, even if not actively used for display.
- **Back-Office Admin Controllers**:

  - No dedicated admin controllers are present in this module. All back-office configuration is handled directly within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

No custom classes or `ObjectModel` definitions are present in the `classes/` directory for this module. All core logic resides within the main `cbrrates.php` file.

### 4.4 JavaScript Assets (`views/js/`)

No custom JavaScript files are present in the module.

### 4.5 CSS Stylesheets (`views/css/`)

No custom CSS files are present in the module.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Admin templates (`views/templates/admin/`)**:
  - `cbrrates/views/admin.tpl`
    - **Purpose**: This template is rendered by the `getContent()` method in `cbrrates.php` to display the module’s configuration form in the PrestaShop Back Office.
    - **Contents**: It typically contains the HTML structure for the input fields, switches, and buttons for settings like `mypresta_updates`, `update_`, `updatev_`, `currency_`, and the CRON job URL display. It uses standard PrestaShop form helpers and styling.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any custom SQL tables.
  - It stores its configuration settings in the `ps_configuration` table (or `_configuration` depending on prefix).
    - `PS_CBRRATES_UPDATE_ENABLED`: Boolean (0/1) for “Enable automatic updates”.
    - `PS_CBRRATES_UPDATE_FREQUENCY`: Integer for “Update frequency (in hours)”.
    - `PS_CBRRATES_MARGIN`: Float for “Margin on exchange rate (%)”.
    - `PS_CBRRATES_CURRENCY_ID`: Integer, ID of the PrestaShop currency to update (e.g., ID for RUB).
    - `PS_CBRRATES_LAST_UPDATE`: Timestamp of the last successful update.
    - `PS_CBRRATES_CRON_TOKEN`: A unique string used in the CRON job URL for security.
- **Registered Hooks Table**:
  The module does not explicitly register hooks for front-office display (e.g., `displayHeader`, `displayFooter`). Its primary interaction with PrestaShop’s core is through the `actionUpdateCurrency` hook (implicitly, by updating currency rates) and its own internal CRON mechanism.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionUpdateCurrency` | Triggered when a currency is updated (implicitly by this module) | Not explicitly registered by the module, but the module’s core function is to update currency rates, which might trigger this core PrestaShop hook. |
| (Internal CRON) | Via `controllers/front/cronjob.php` | Triggers the fetching and updating of CBR exchange rates based on configured frequency. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “CBR Currency Exchange & Rates (Bank of Russia)” module, please refer to your customer account at MyPresta.eu. Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and integration.
