---
title: "Hungarian National Bank (MNB) - currency exchange rates - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Hungarian National Bank (MNB) - currency exchange rates PrestaShop module by MyPresta.eu."
sidebar:
  label: "Hungarian National Bank (MNB) - currency exchange rates - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Hungarian National Bank (MNB) - currency exchange rates Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/hungarian-national-bank-mnb-currency-exchange-rates.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/hungarian-national-bank-mnb-currency-exchange-rates/)
>
> ---


# Hungarian National Bank (MNB) - currency exchange rates

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for external API communication, which is common for exchange rate modules. Ensure your hosting environment supports these.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” will take you to the module’s main configuration screen. This is where you set up how the module fetches and applies exchange rates.

#### **Settings & Options**

The configuration page for the “Hungarian National Bank (MNB) - currency exchange rates” module will typically present a form with various options to control its behavior. While specific field names might vary slightly, the core functionality revolves around enabling the update process and potentially scheduling it.

1. **Enable MNB Exchange Rate Updates**

   - **What this setting does:** This is the master switch to activate or deactivate the automatic exchange rate updates from the Hungarian National Bank.
   - **Effect of changing this setting:**
     - *When enabled (YES):* The module will periodically fetch the latest exchange rates from the MNB and apply them to your store’s configured currencies. This ensures your prices are always up-to-date.
     - *When disabled (NO):* The module will stop fetching and applying MNB exchange rates. Your store’s currency rates will remain as they were last set (either manually or by the module before it was disabled).
   - **Recommended value:** YES
   - **Merchant scenario / example:** If you want your store to automatically reflect the latest MNB exchange rates for HUF, EUR, USD, etc., you must enable this setting. If you prefer to manage rates manually or use a different system, you would disable it.
2. **Cron Job URL (for automatic updates)**

   - **What this setting does:** This field displays a unique URL that you can use to set up a “cron job” on your web server. A cron job is a scheduled task that tells your server to visit this URL at regular intervals, triggering the module to update exchange rates automatically.
   - **Effect of changing this setting:** This is not a setting you change directly, but rather a URL you copy.
     - *When the cron job is set up:* Your server will periodically call this URL, and the module will run its update process in the background without you needing to do anything.
     - *When the cron job is NOT set up:* You would need to manually visit this URL in your browser (or click a “Run Update Now” button if available) to trigger an update. This is not recommended for regular use.
   - **Recommended value:** Copy this URL and set up a cron job on your hosting panel (e.g., cPanel, Plesk, or server command line) to run at least once a day, or more frequently if your business requires it.
   - **Merchant scenario / example:** You want your exchange rates to update every morning at 3 AM. You would copy this URL, go to your hosting control panel’s “Cron Jobs” section, and create a new cron job that executes `wget -O /dev/null -q "YOUR_CRON_JOB_URL_HERE"` (or similar command) daily at 3 AM.
3. **Last Update Time** (Informational Display)

   - **What this setting does:** This is a display-only field that shows you when the exchange rates were last successfully updated by the module.
   - **Effect of changing this setting:** This is not a configurable setting. It simply provides feedback on the module’s activity.
   - **Recommended value:** N/A (informational)
   - **Merchant scenario / example:** You can quickly check this timestamp to confirm that your cron job is running correctly and that the rates are being updated as expected. If the time is old, it indicates a problem with your cron job setup.

#### **Configuration Quick Reference Table**

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Config | Enable MNB Exchange Rate Updates | YES | Activates/deactivates automatic fetching and application of MNB exchange rates. |
| Module Config | Cron Job URL | N/A (Copy & Configure) | URL to set up a scheduled task (cron job) for automatic rate updates. |
| Module Config | Last Update Time | N/A (Informational) | Displays the timestamp of the last successful exchange rate update. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My exchange rates are not updating. What should I do?**
A1:

1. **Check “Enable MNB Exchange Rate Updates”:** Make sure this setting is set to YES in the module’s configuration.
2. **Verify Cron Job Setup:** The most common reason for non-updates is an incorrectly configured cron job.
   - Ensure you’ve copied the exact “Cron Job URL” from the module.
   - Check your hosting control panel (cPanel, Plesk, etc.) for the cron job settings.
   - Confirm the command is correct (e.g., `wget -O /dev/null -q "YOUR_CRON_JOB_URL"`).
   - Check the schedule (e.g., `* * * * *` for every minute, `0 3 * * *` for 3 AM daily).
   - Look for any error logs related to the cron job in your hosting panel.
3. **Check “Last Update Time”:** If this timestamp is old, it confirms the cron job isn’t running.
4. **Server Connectivity:** Ensure your server can make outgoing connections to external websites (like the MNB API). Sometimes firewalls or security settings can block this. Contact your hosting provider if you suspect this.

**Q2: I’ve enabled the module, but some currencies are not updating.**
A2:

1. **Currency Activation:** Go to **International > Currencies** in your PrestaShop Back Office. Ensure that the currencies you expect to be updated are enabled (active). The module only updates active currencies.
2. **MNB Support:** The MNB provides rates for specific currencies. If a currency is not supported by the MNB, the module cannot update it. You might need to manually set rates for such currencies or use another module for them.

**Q3: My custom theme doesn’t display prices correctly after the update.**
A3: This module primarily updates the *data* (exchange rates) in your PrestaShop database. It does not directly affect how prices are *displayed* by your theme. If you see display issues:

1. **Clear PrestaShop Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache”).
2. **Theme Customization:** If your theme has heavily customized price display logic, it might be interfering. Check your theme’s documentation or contact your theme developer.
3. **Browser Cache:** Ask your customers to clear their browser cache or try a different browser to rule out client-side caching issues.

**Q4: Can I manually override an exchange rate after the module updates it?**
A4: Yes, you can. After the module runs, the rates are stored in PrestaShop’s database. You can go to **International > Currencies**, edit a specific currency, and manually adjust its exchange rate. However, be aware that the next time the cron job runs, the module will overwrite your manual changes with the latest MNB data. If you need permanent manual control over a specific currency, you might consider disabling the module’s updates for that currency (if the module offers such a granular setting, which is rare) or disabling the module entirely and managing all rates manually.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Hungarian National Bank (MNB) - currency exchange rates” module follows a standard PrestaShop module architecture, primarily focusing on background processing. It leverages PrestaShop’s `Module` class for installation and configuration, and `ModuleFrontController` for handling the cron job execution. The core logic involves making an HTTP request to the MNB’s official exchange rate API (likely an XML feed), parsing the response, and then updating the `ps_currency` table in the PrestaShop database.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `mnbrates/controllers/front/cronjob.php`
    - **Class name & parent class**: `MnbratesCronjobModuleFrontController` extending `ModuleFrontController`
    - **Responsibility**: This controller is the entry point for the scheduled cron job. When its URL is accessed (e.g., `yourstore.com/module/mnbrates/cronjob`), it triggers the module’s core logic to fetch and update exchange rates. It typically handles the HTTP request, calls the main module’s update method, and returns a simple success/failure message or no output (for silent cron execution).
  - `mnbrates/controllers/front/index.php`
    - **Class name & parent class**: `MnbratesIndexModuleFrontController` extending `ModuleFrontController`
    - **Responsibility**: This is a standard placeholder controller often included in modules. In many cases, it might simply redirect to the homepage or serve as a fallback. For this specific module, its primary purpose is likely to prevent directory listing if someone tries to access `/module/mnbrates/` directly, or it could be a vestigial file. It’s unlikely to contain core business logic for exchange rate updates.
- **Back-Office Admin Controllers**:

  - No dedicated admin controllers (`controllers/admin/`) are identified. This means all back-office configuration is handled directly within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

No custom classes or models are identified in the `classes/` directory. This suggests that the module likely performs its operations directly within the main `cronjob.php` module file, potentially using PrestaShop’s core `Currency` `ObjectModel` to update rates.

### 4.4 JavaScript Assets (`views/js/`)

No JavaScript files are identified. This confirms the module’s backend-focused nature, with no interactive front-office components or complex back-office forms requiring dynamic JS.

### 4.5 CSS Stylesheets (`views/css/`)

No CSS files are identified. This indicates that the module does not introduce any custom styling for either the front-office or back-office. The back-office configuration will inherit PrestaShop’s default admin theme styles.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Admin templates (`views/templates/admin/`)**:
  - `mnbrates/views/admin.tpl`
    - **Purpose**: This template is rendered by the `getContent()` method of the main module file (`mnbrates/cronjob.php`). It defines the structure and content of the module’s configuration page in the PrestaShop Back Office. It will contain the form elements for enabling/disabling updates, displaying the cron job URL, and showing the last update timestamp.
- **Hook templates (`views/templates/hook/`)**: None identified.
- **Front-office templates (`views/templates/front/`)**: None identified.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create custom SQL tables. It interacts with PrestaShop’s core `ps_currency` table to update the `conversion_rate` field for each currency.
  - Configuration settings (like `PS_MNBRATES_ENABLED`, `PS_MNBRATES_LAST_UPDATE`) are stored in the `ps_configuration` table.
- **Registered Hooks Table**:
  The module likely registers hooks during its `install()` method. Given its functionality, the most crucial hook is for the cron job, which is handled by a front controller. Other hooks might be for informational purposes or to ensure compatibility.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Renders in the `<head>` section of all front-office pages. | Unlikely to be used for core logic, possibly for adding a meta tag or a very simple JS/CSS (though none identified). |
| `displayRightColumn` | Renders in the right column of pages where it’s available. | Unlikely to be used for core logic, possibly for a small informational block if the module had a front-office component. |
| `displayLeftColumn` | Renders in the left column of pages where it’s available. | Similar to `displayRightColumn`. |
| `displayFooter` | Renders in the footer of all front-office pages. | Similar to `displayHeader`, but at the bottom. |
| `displayProductExtraContent` | Renders additional content on the product page. | Unlikely for this module. |
| `actionModuleInstall` | Executed when a module is installed. | Registers necessary hooks and sets default configuration values. |
| `actionModuleUninstall` | Executed when a module is uninstalled. | Cleans up configuration values and unregisters hooks. |
| `actionModuleUpdate` | Executed when a module is updated. | Handles schema changes or configuration migrations between versions. |
| (Implicit) `frontController` dispatch | When `mnbrates/controllers/front/cronjob.php` is accessed. | Triggers the main exchange rate update logic. This is the primary “hook” for the cron job. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the “Hungarian National Bank (MNB) - currency exchange rates” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our team is dedicated to ensuring your module functions optimally and your store benefits from the most current features and compatibility.
