---
title: "Central Bank of Turkey (TCMB) - currency exchange rates - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Central Bank of Turkey (TCMB) - currency exchange rates PrestaShop module by MyPresta.eu."
sidebar:
  label: "Central Bank of Turkey (TCMB) - currency exchange rates - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Central Bank of Turkey (TCMB) - currency exchange rates Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/central-bank-of-turkey-tcmb-currency-exchange-rates.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/central-bank-of-turkey-tcmb-currency-exchange-rates/)
>
> ---


# Central Bank of Turkey (TCMB) - currency exchange rates

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for fetching external data. Your hosting environment should allow outbound connections to the TCMB website.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the module name to access its settings.

#### General Settings

- **Enable module**

  - **What this setting does:** This is the master switch to activate or deactivate the module’s functionality.
  - **Effect of changing this setting:**
    - *When enabled:* The module will start fetching exchange rates and updating your store’s currency prices according to your other settings.
    - *When disabled:* The module will cease all operations. Exchange rates will not be updated automatically, and your prices will remain static until manually changed or the module is re-enabled.
  - **Recommended value:** YES
  - **Merchant scenario / example:** If you’re setting up the module for the first time, enable it to start using its features. If you need to temporarily stop automatic updates (e.g., for maintenance), you can disable it.
- **CRON URL**

  - **What this setting does:** This field displays a unique URL that, when accessed, triggers the module to fetch the latest exchange rates from the TCMB and update your store’s currency prices.
  - **Effect of changing this setting:** This is a read-only field. Copying and setting this URL in your hosting panel’s CRON job scheduler will automate the rate updates.
  - **Recommended value:** Copy this URL.
  - **Merchant scenario / example:** You will copy this URL and paste it into your hosting control panel (e.g., cPanel, Plesk, or a custom CRON job interface) to schedule automatic updates. For instance, you might set it to run once every 24 hours to ensure daily price accuracy.
- **Margin (%)**

  - **What this setting does:** Allows you to add a percentage margin on top of the official exchange rates fetched from TCMB. This can be used to cover transaction fees, currency conversion costs, or simply to adjust your pricing strategy.
  - **Effect of changing this setting:**
    - *When set to 0:* Your store will use the exact official exchange rates provided by TCMB.
    - *When set to a positive value (e.g., 2):* The module will increase the calculated exchange rate by that percentage. For example, if the official rate is 1 USD = 30 TRY, and you set a 2% margin, the module will use 1 USD = 30.6 TRY for conversions. This means products priced in USD will appear slightly more expensive in TRY, or vice-versa, depending on your base currency.
  - **Recommended value:** 0 (if you want exact official rates) or a small positive percentage (e.g., 1-3%) to cover costs.
  - **Merchant scenario / example:** If your payment gateway charges a 1.5% fee for currency conversions, you might set a “Margin (%)” of 1.5 to absorb this cost and maintain your profit margins.
- **Last update**

  - **What this setting does:** This read-only field shows the date and time when the module last successfully fetched and applied exchange rate updates.
  - **Effect of changing this setting:** This field updates automatically after each successful CRON job execution or manual update. It helps you verify that the module is working correctly and when the rates were last refreshed.
  - **Recommended value:** Monitor this value to ensure regular updates.
  - **Merchant scenario / example:** After setting up your CRON job, you can check this field to confirm that the automated updates are running as expected. If the date is old, it indicates a problem with your CRON job setup.

#### Manual Update

- **Update now** button
  - **What this setting does:** This button allows you to manually trigger the exchange rate update process immediately, without waiting for the CRON job.
  - **Effect of changing this setting:** Clicking this button will instantly fetch the latest rates from TCMB and update your store’s currency prices. This is useful for testing or for urgent updates.
  - **Recommended value:** Click when you need an immediate update or for testing.
  - **Merchant scenario / example:** You’ve just launched a new product and want to ensure its price is based on the very latest exchange rates before customers start ordering. You can click “Update now” to refresh all rates instantly.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable module | YES | Activates/deactivates the module’s core functionality. |
| Module Configuration | CRON URL | Copy this URL | URL to set up automated exchange rate updates via your hosting CRON job. |
| Module Configuration | Margin (%) | 0-3% | Adds a percentage margin on top of official TCMB exchange rates for pricing flexibility. |
| Module Configuration | Last update | Monitor | Displays the date/time of the last successful exchange rate update. |
| Module Configuration | Update now button | Click as needed | Manually triggers an immediate exchange rate update. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My prices are not updating, even after I’ve configured the module.**
A1: First, check if the “Enable module” setting is set to YES. Second, verify your CRON job setup in your hosting panel. Ensure the CRON URL is correct and the job is scheduled to run. You can also try clicking the “Update now” button in the module configuration to see if a manual update works. If it does, the issue is likely with your CRON job.

**Q2: The “Last update” field shows an old date, but my CRON job is set up.**
A2: This usually means your CRON job is not executing correctly or the module is encountering an error when trying to fetch data.
- **Check CRON job logs:** Many hosting providers offer logs for CRON job executions. Look for any errors there.
- **Server access:** Ensure your server has outbound internet access to `www.tcmb.gov.tr` (the Central Bank of Turkey’s website). Firewalls or network restrictions can block this.
- **PHP version:** Confirm your PHP version is within the supported range (PHP 5.6 - 8.5).
- **Module reinstallation:** As a last resort, try uninstalling and reinstalling the module (after backing up your store) to ensure all files are correctly in place.

**Q3: Can I update rates more frequently than once a day?**
A3: Yes, you can configure your CRON job to run more frequently (e.g., every 6 hours, every hour). However, consider the impact on your server resources and the actual frequency of TCMB rate changes. Daily updates are usually sufficient for most e-commerce stores, as official rates typically change once per business day.

**Q4: I have multiple currencies. Will this module update all of them?**
A4: Yes, the module fetches the official exchange rates for the Turkish Lira (TRY) against other major currencies. It then uses these rates to recalculate and update prices for all active currencies in your PrestaShop store based on your base currency and the fetched TRY rates.

**Q5: What happens if the TCMB website is down or unreachable?**
A5: If the module cannot connect to the TCMB website, it will typically fail to update the rates. Your existing currency rates will remain unchanged until a successful connection and update can be made. The “Last update” field will not change, indicating a problem.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The `tcmbrates` module is designed as a standard PrestaShop module, primarily leveraging the `Module` class for its core functionality. Its main purpose is to fetch external data (TCMB exchange rates) and update PrestaShop’s internal currency rates. It uses a front controller for CRON job execution, allowing it to be triggered externally without direct Back Office interaction. The configuration is handled via the `getContent()` method in the main module file, displaying a simple form for settings and a manual update trigger.

### 4.2 Controllers (`controllers/`)

The module includes front controllers for handling external requests, specifically for the CRON job.

- **Front-Office Controllers**:

  - `controllers/front/cronjob.php`
    - **Class name & parent class:** `TcmbratesCronjobModuleFrontController` extending `ModuleFrontController`.
    - **Responsibility:** This controller is designed to be called by an external CRON job scheduler. When accessed, it triggers the module’s core logic to fetch the latest exchange rates from the Central Bank of Turkey and update the currency rates in the PrestaShop database. It typically outputs a success or failure message.
  - `controllers/front/index.php`
    - **Class name & parent class:** `TcmbratesIndexModuleFrontController` extending `ModuleFrontController`.
    - **Responsibility:** This is a placeholder or default front controller, often included in modules but not always actively used for specific functionality. In this module’s context, it likely serves as a fallback or a simple entry point if no other specific front controller is requested. Its primary function is usually to redirect or display a generic message.
- **Back-Office Admin Controllers**: None. All administration is handled via the module’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

The module does not define custom classes extending `ObjectModel`. Its core logic resides within the main module file (`cronjob.php`).

### 4.4 JavaScript Assets (`views/js/`)

No custom JavaScript files are included in this module.

### 4.5 CSS Stylesheets (`views/css/`)

No custom CSS files are included in this module.

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses a single Smarty template for its Back Office configuration interface.

- **Admin templates (`views/templates/admin/`)**:
  - `views/admin.tpl`
    - **Purpose:** This template is rendered by the `getContent()` method of the main module file (`cronjob.php`). It displays the module’s configuration form in the PrestaShop Back Office, including fields for enabling the module, setting the margin, displaying the CRON URL, and providing a manual update button.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: The module does not create any custom SQL tables. It stores its configuration settings (e.g., `PS_TCMBRATES_ENABLED`, `PS_TCMBRATES_MARGIN`, `PS_TCMBRATES_LAST_UPDATE`) in the standard `ps_configuration` table. It directly interacts with PrestaShop’s `ps_currency` table to update exchange rates.
- **Registered Hooks Table**: The module does not explicitly register to standard display hooks like `displayHeader` or `displayFooter` for front-office content. Its primary interaction with the PrestaShop system is through its internal logic triggered by the CRON job or manual update, which then modifies existing currency data.

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `install()` | Module installation | Creates configuration entries in `ps_configuration`. |
  | `uninstall()` | Module uninstallation | Deletes configuration entries from `ps_configuration`. |
  | (No explicit front-office display hooks) | N/A | Module operates in the background to update data, not display content. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Central Bank of Turkey (TCMB) - currency exchange rates” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions regarding the module’s functionality and integration.
