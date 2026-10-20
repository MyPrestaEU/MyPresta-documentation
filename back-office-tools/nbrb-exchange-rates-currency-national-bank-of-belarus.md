---
title: "NBRB Exchange Rates & Currency (National Bank of Belarus) - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the NBRB Exchange Rates & Currency (National Bank of Belarus) PrestaShop module by MyPresta.eu."
sidebar:
  label: "NBRB Exchange Rates & Currency (National Bank of Belarus) - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy NBRB Exchange Rates & Currency (National Bank of Belarus) Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/nbrb-exchange-rates-currency-national-bank-of-belarus.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/nbrb-exchange-rates-currency-national-bank-of-belarus/)
>
> ---


# NBRB Exchange Rates & Currency (National Bank of Belarus)

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required and are present on most modern hosting environments. Access to set up a CRON job is essential for automatic updates.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “NBRB Exchange Rates & Currency” module to access its settings.

#### **Enable NBRB Exchange Rates**

- **What this setting does:** This is the master switch to activate or deactivate the module’s core functionality.
- **Effect of changing this setting:**
  - *When enabled (YES):* The module will start fetching and applying NBRB exchange rates for BYN currency conversions in your store.
  - *When disabled (NO):* The module will stop fetching rates, and your BYN currency rates will revert to whatever was manually set in PrestaShop’s “Currencies” section or by another active currency module.
- **Recommended value:** YES
- **Merchant scenario / example:** If you primarily sell to Belarus, enable this to ensure all BYN prices are official. If you temporarily stop selling to Belarus, you might disable it.

#### **CRON Job URL**

- **What this setting does:** This displays the unique URL that you need to set up as a CRON job on your server. When this URL is accessed, the module will automatically fetch the latest exchange rates from the NBRB.
- **Effect of changing this setting:** This is a display-only field. You copy this URL and paste it into your hosting control panel’s CRON job scheduler.
- **Recommended value:** Copy this URL exactly as shown.
- **Merchant scenario / example:** You would copy this URL and set up a CRON job to run, for instance, once every 24 hours (e.g., at 3 AM local time) to ensure your rates are always fresh. Consult your hosting provider’s documentation or support for setting up CRON jobs.

#### **Margin Adjustment (%)**

- **What this setting does:** Allows you to add a percentage margin (markup or markdown) to the fetched NBRB exchange rates. This is useful for covering transaction fees, hedging against minor fluctuations, or applying a slight discount/premium.
- **Effect of changing this setting:**
  - *Entering a positive value (e.g., 2):* The BYN conversion rate will be increased by 2%, effectively making products slightly more expensive in BYN.
  - *Entering a negative value (e.g., -1):* The BYN conversion rate will be decreased by 1%, making products slightly cheaper in BYN.
  - *Leaving it at 0:* The official NBRB rate will be used without any modification.
- **Recommended value:** 0 (unless you have a specific business reason to adjust rates).
- **Merchant scenario / example:** If your payment gateway charges a 1.5% fee for BYN transactions, you might set this to “1.5” to absorb that cost into the exchange rate.

#### **Last Update**

- **What this setting does:** This field displays the date and time when the exchange rates were last successfully updated by the module (either manually or via CRON job).
- **Effect of changing this setting:** This is a read-only informational field. It helps you verify that your CRON job is running correctly and that rates are being updated.
- **Recommended value:** N/A (monitor this to ensure regular updates).
- **Merchant scenario / example:** If you notice this date is several days old, it indicates an issue with your CRON job setup, and you should investigate.

#### **Manually Update Rates Button**

- **What this setting does:** This button allows you to manually trigger an immediate update of the exchange rates from the NBRB, outside of the CRON job schedule.
- **Effect of changing this setting:** Clicking this button will instantly fetch the latest rates and update them in your PrestaShop store. The “Last Update” field will reflect the new time.
- **Recommended value:** Use as needed for immediate updates or testing.
- **Merchant scenario / example:** If there’s a significant economic event and you want to ensure your rates are absolutely current before your next scheduled CRON job, you can click this button.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable NBRB Exchange Rates | YES | Activates/deactivates the module’s rate fetching and application. |
| Module Configuration | CRON Job URL | N/A (copy & paste) | URL for setting up automatic rate updates on your server. |
| Module Configuration | Margin Adjustment (%) | 0 | Adds a percentage markup/markdown to the fetched NBRB rates. |
| Module Configuration | Last Update | N/A (read-only) | Shows the timestamp of the last successful rate update. |
| Module Configuration | Manually Update Rates Button | N/A (click to activate) | Triggers an immediate, manual update of exchange rates. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My BYN prices aren’t updating, or they seem incorrect.**
A:

1. **Check “Enable NBRB Exchange Rates”:** Make sure this setting is set to “YES” in the module configuration.
2. **Verify CRON Job:** Ensure your CRON job is correctly set up on your server using the provided URL and is running regularly. Check the “Last Update” timestamp in the module.
3. **Manually Update:** Try clicking the “Manually Update Rates” button. If this works, the issue is likely with your CRON job setup.
4. **Check BYN Currency Status:** Go to **International > Currencies** and ensure “Belarusian Ruble (BYN)” is enabled and its ISO code is `BYN`.
5. **Clear Cache:** Sometimes PrestaShop’s cache can hold old values. Go to **Advanced Parameters > Performance** and click “Clear cache”.

**Q: What happens on bank holidays or weekends when NBRB doesn’t publish new rates?**
A: The module is designed to handle this intelligently. If the NBRB API does not provide new rates for a given day (e.g., due to a weekend or public holiday), the module will continue to use the last successfully fetched rate. It will only update when new official rates become available.

**Q: Can I use this module with other currency conversion modules?**
A: It’s generally not recommended to run multiple currency conversion modules simultaneously, as they can conflict and lead to unpredictable results. This module specifically targets NBRB rates for BYN. If you need other currencies, ensure this module is the primary source for BYN, and other modules handle different currencies without overlapping.

**Q: I’ve set a margin, but prices don’t seem to reflect it.**
A:

1. **Save Changes:** Ensure you’ve saved the module configuration after setting the margin.
2. **Update Rates:** The margin is applied when rates are fetched. Either wait for the next CRON job run or click “Manually Update Rates”.
3. **Clear Cache:** Clear your PrestaShop cache (**Advanced Parameters > Performance**).
4. **Check Base Currency:** The margin is applied to the conversion from your store’s base currency to BYN. Ensure your base currency is correctly set in PrestaShop.

**Q: I’m getting an error when trying to install or configure the module.**
A:

1. **PrestaShop Version:** Ensure you downloaded the correct module ZIP file for your specific PrestaShop version (1.6, 1.7, 8.x, 9.x).
2. **PHP Compatibility:** Verify your server’s PHP version is within the supported range (PHP 5.6 - 8.5).
3. **Server Logs:** Check your server’s PHP error logs (often found in your hosting control panel) for more detailed error messages. This can help pinpoint the exact problem.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The NBRB Exchange Rates & Currency module is a lightweight PrestaShop module primarily focused on a single, critical task: fetching and updating the Belarusian Ruble (BYN) exchange rate from the National Bank of the Republic of Belarus (NBRB) API. It leverages PrestaShop’s `Currency` object to update the `conversion_rate` for BYN. The module uses a CRON job for automated updates and provides a manual trigger in the back office. It adheres to PrestaShop’s MVC pattern for its configuration and front-office cronjob execution.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `controllers/front/cronjob.php`
    - **Class name & parent class:** `NbrbratesCronjobModuleFrontController` extending `ModuleFrontController`.
    - **Responsibility:** This controller is designed to be called by an external CRON job. When accessed, it triggers the module’s rate fetching logic (`$this->module->updateRates()`). It outputs a simple success/failure message, making it suitable for automated execution without a browser. It does not render a full page.
  - `controllers/front/index.php`
    - **Class name & parent class:** `NbrbratesIndexModuleFrontController` extending `ModuleFrontController`.
    - **Responsibility:** This is a placeholder controller, often included in modules to prevent directory listing or provide a default “empty” page if the module’s front controller is accessed directly without specific actions. In this module’s context, it likely serves as a fallback and doesn’t have specific business logic.
- **Back-Office Admin Controllers**:

  - This module does not utilize dedicated Admin Controllers. All back-office configuration is handled directly within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes in the `classes/` directory. Its core logic for fetching and updating rates is encapsulated within the main module file `nbrbrates/cronjob.php`.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include any custom JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)

This module does not include any custom CSS files. Styling for the admin configuration page is typically handled by PrestaShop’s default back-office CSS.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Admin templates (`views/templates/admin/`)**:
  - `nbrbrates/views/admin.tpl`
    - **Purpose:** This template is rendered by the `getContent()` method in the main module file (`nbrbrates/cronjob.php`). It defines the structure and display of the module’s configuration form in the PrestaShop Back Office. It includes input fields for enabling/disabling the module, margin adjustment, displaying the CRON job URL, last update time, and the manual update button.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create any custom SQL tables.
  - It stores its configuration settings in PrestaShop’s `ps_configuration` table. Key configuration keys include:
    - `Nbrbrates_ENABLED`: (int) 1 if enabled, 0 if disabled.
    - `Nbrbrates_MARGIN`: (float) The percentage margin to apply.
    - `Nbrbrates_LAST_UPDATE`: (datetime) Timestamp of the last successful rate update.
- **Registered Hooks Table**:
  This module does not explicitly register hooks that display content in the front office (like `displayHeader`, `displayRightColumn`, `displayFooter`). Its primary interaction with PrestaShop is through:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionModuleInstall` | Executed when the module is installed. | Initializes default configuration values in `ps_configuration`. |
| `actionModuleUninstall` | Executed when the module is uninstalled. | Cleans up configuration values from `ps_configuration`. |
| `actionUpdateCurrency` | (Implicit) Triggered when a currency is updated. | The module’s `updateRates()` method directly modifies the `conversion_rate` of the BYN currency object, effectively acting on currency updates. |

The front-office `cronjob.php` controller acts as an external entry point, not a traditional PrestaShop hook.

## 5. Official Support & Updates

For official updates, technical support, and to access the latest versions of the NBRB Exchange Rates & Currency module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality or integration.
