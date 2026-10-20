---
title: "Currency rates from Česká národní banka (CNB) - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Currency rates from Česká národní banka (CNB) PrestaShop module by MyPresta.eu."
sidebar:
  label: "Currency rates from Česká národní banka (CNB) - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Currency rates from Česká národní banka (CNB) Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/currency-rates-from-ceska-narodni-banka-cnb.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/currency-rates-from-ceska-narodni-banka-cnb/)
>
> ---


# Currency rates from Česká národní banka (CNB)

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for fetching external data, which are almost universally available on modern hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the module name to access its settings. This is the main and only configuration screen for the module.

#### **Settings & Options**

**1. `mypresta_updates` (MyPresta.eu Updates)**

- **What this setting does:** This is a standard setting found in many MyPresta.eu modules. It controls whether the module checks for updates from MyPresta.eu and displays notifications in your PrestaShop back office.
- **Effect of changing this setting:**
  - *When enabled (YES):* The module will periodically check for new versions available on MyPresta.eu. If an update is found, you might see a notification in your PrestaShop admin panel, prompting you to download and install the newer version. This helps you stay up-to-date with bug fixes and new features.
  - *When disabled (NO):* The module will not check for updates. You will not receive any notifications about new versions, meaning you would need to manually check your MyPresta.eu account for updates.
- **Recommended value:** **YES**. It’s always recommended to keep modules updated for security, compatibility, and new features.
- **Merchant scenario / example:** You want to ensure your module is always running the latest, most stable version without constantly checking manually. Enabling this will give you a heads-up when an update is available.

**2. `update_` (Update Frequency)**

- **What this setting does:** This setting determines how often the module attempts to fetch and update currency rates from the CNB feed.
- **Effect of changing this setting:**
  - *When set to a shorter interval (e.g., “Every hour”):* Your currency rates will be refreshed more frequently, ensuring your prices are very current, which is beneficial in volatile markets. However, it might slightly increase server load (though typically negligible for this type of operation).
  - *When set to a longer interval (e.g., “Once a day”):* Rates are updated less frequently. This is generally sufficient as the CNB typically provides daily rates. It reduces server load.
- **Recommended value:** **Once a day**. The CNB usually publishes daily rates, so updating more frequently than once a day is often unnecessary and doesn’t provide newer data.
- **Merchant scenario / example:** You run an international store where exchange rate fluctuations can impact your profit margins. Setting this to “Once a day” ensures you always have the latest official rates without over-burdening your server.

**3. `updatev_` (Update Method)**

- **What this setting does:** This setting defines how the module triggers the currency rate update process.
- **Effect of changing this setting:**
  - *When set to “Cron Job”:* The module expects you to set up a server-side cron job (a scheduled task) that will periodically call a specific URL provided by the module. This is the most reliable and recommended method as it ensures updates happen precisely when scheduled, even if no one visits your store.
  - *When set to “On page load”:* The module will attempt to update rates when a customer or administrator visits any page of your store. This is less reliable as updates only occur when traffic hits your site, and if your site has low traffic, updates might be delayed. It can also slightly slow down the first page load for a visitor if an update is due.
- **Recommended value:** **Cron Job**. This is the most robust and efficient method for scheduled tasks. The module will provide you with the exact URL to use for your cron job.
- **Merchant scenario / example:** You want to guarantee that currency rates are updated every morning at 3 AM, regardless of website traffic. Setting this to “Cron Job” and configuring your server’s cron will achieve this reliably.

**4. `currency_` (Currencies to Update)**

- **What this setting does:** This allows you to select which specific currencies in your PrestaShop store should have their exchange rates updated by the CNB feed.
- **Effect of changing this setting:**
  - *When specific currencies are selected:* Only the chosen currencies will have their exchange rates updated by the module. Other currencies (if you have any) will retain their manually set rates or PrestaShop’s default update mechanism (if active). This gives you granular control.
  - *When no currencies are selected (or all are selected):* The module will attempt to update all active currencies in your store that are present in the CNB feed.
- **Recommended value:** Select **all currencies that you actively use for transactions and that are supported by the CNB feed**. Typically, this includes EUR, USD, GBP, and other major currencies.
- **Merchant scenario / example:** Your store accepts payments in EUR, USD, and CZK. You want the EUR and USD rates to be updated by the CNB, but CZK is your default currency and doesn’t need external updates. You would select EUR and USD from this list.

#### **Cron Job URL (Displayed after saving settings)**

- **What this does:** After you configure and save the module settings, especially if you choose “Cron Job” for the update method, the module will display a unique URL. This URL is what your server’s cron job needs to call to trigger the update process.
- **Effect of using this URL:** When this URL is accessed (either by your server’s cron job or manually in a browser), the module executes its logic to fetch the latest currency rates from the CNB and updates them in your PrestaShop database.
- **Recommended action:** Copy this URL and set it up as a cron job on your hosting server. Consult your hosting provider’s documentation or support for how to set up a cron job. A typical cron job might look like `wget -q -O /dev/null "YOUR_CRON_URL_HERE"`.
- **Merchant scenario / example:** You’ve set the update frequency to “Once a day” and the method to “Cron Job”. The module displays `https://yourstore.com/module/cnbrates/cronjob?token=YOUR_UNIQUE_TOKEN`. You would then configure your server’s cron to run `wget -q -O /dev/null "https://yourstore.com/module/cnbrates/cronjob?token=YOUR_UNIQUE_TOKEN"` once every 24 hours.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | MyPresta.eu Updates | YES | Controls update notifications from MyPresta.eu. |
| Module Configuration | Update Frequency | Once a day | How often the module fetches new rates from CNB. |
| Module Configuration | Update Method | Cron Job | How the update process is triggered (scheduled task vs. page load). |
| Module Configuration | Currencies to Update | Select all relevant | Specifies which currencies in your store get updated by CNB. |
| Module Configuration | Cron Job URL | (Displayed after save) | The URL to use for server-side cron jobs to trigger updates. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My currency rates aren’t updating. What should I check first?**
A: The most common reason is an issue with the cron job.

1. Go to **Modules > Module Manager > Configure** for the CNB Rates module.
2. Check the “Update Method” setting. If it’s “Cron Job,” ensure you have correctly set up the cron job on your hosting server using the provided URL. Contact your hosting provider’s support if you’re unsure how to do this.
3. If “On page load” is selected, ensure your store receives regular traffic. If not, switch to “Cron Job” for more reliable updates.
4. Also, verify that the currencies you expect to be updated are selected in the “Currencies to Update” list.

**Q: Does this module work if my default store currency is not CZK?**
A: Yes, absolutely! The module is designed to work even if your default currency is not CZK. It fetches rates from CNB, which provides exchange rates for various currencies against the CZK. The module then intelligently converts these to update your store’s non-default currencies relative to your actual default currency.

**Q: How often does the CNB update its rates?**
A: The Česká národní banka (CNB) typically publishes its official exchange rates once a day, usually on business days. Therefore, setting your module’s “Update Frequency” to “Once a day” is generally sufficient to capture the latest available data.

**Q: I’ve updated the module, but I don’t see any changes. What can I do?**
A: Sometimes, PrestaShop’s caching system can prevent immediate display of changes.

1. Go to **Advanced Parameters > Performance** in your PrestaShop back office.
2. Click “Clear cache” (or “Clear Smarty cache” if available).
3. Refresh your browser (Ctrl+F5 or Cmd+R) to ensure you’re not seeing a cached version of the page.

**Q: Can I manually trigger an update?**
A: Yes, if your “Update Method” is set to “Cron Job,” you can manually visit the cron job URL (displayed in the module configuration) in your web browser. This will trigger an immediate update. However, this is for testing/troubleshooting only; for regular updates, rely on the automated cron job.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Currency rates from Česká národní banka (CNB)” module is a lightweight PrestaShop module designed for a single, focused task: fetching and updating currency exchange rates. It primarily leverages a front-office controller to expose a cron job endpoint, allowing for scheduled, automated updates. The module does not introduce new database tables or complex `ObjectModel` structures, relying instead on PrestaShop’s existing `Currency` class and `Configuration` for its settings. It follows a basic PrestaShop module structure, integrating with the `install()` and `uninstall()` methods for setup and cleanup.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `controllers/front/cronjob.php`
    - **Class name & parent class**: `CnbratesCronjobModuleFrontController` extends `ModuleFrontController`.
    - **Responsibility**: This controller is the core of the module’s automation. It responds to requests to the cron job URL (e.g., `yourstore.com/module/cnbrates/cronjob?token=...`). Its `initContent()` method (or similar lifecycle method) contains the logic to:
      1. Validate the `token` parameter against the stored configuration to prevent unauthorized access.
      2. Fetch the latest exchange rates from the CNB XML feed (typically `https://www.cnb.cz/cs/financni_trhy/devizovy_trh/kurzy_devizoveho_trhu/denni_kurz.xml`).
      3. Parse the XML data.
      4. Iterate through the configured currencies in PrestaShop.
      5. For each selected currency, calculate its new exchange rate based on the CNB data (which is usually relative to CZK) and the store’s default currency.
      6. Update the `exchange_rate` field for the respective `Currency` object in the `ps_currency` table.
      7. Outputs a simple success or error message, primarily for cron job logging.
  - `controllers/front/index.php`
    - **Class name & parent class**: `CnbratesIndexModuleFrontController` extends `ModuleFrontController`.
    - **Responsibility**: This is a placeholder or fallback controller. In many modules, an `index.php` front controller serves as a default entry point if no specific action is requested. For this module, its primary function is likely to redirect to the homepage or display a simple message, as the main functionality is handled by `cronjob.php`. It doesn’t contain significant business logic for currency updates.
- **Back-Office Admin Controllers**: None. The module’s configuration is handled entirely within `cnbrates.php` via `getContent()`.

### 4.3 Core Classes & Models (`classes/`)

There are no custom classes or `ObjectModel` definitions within the `classes/` directory for this module. The module directly interacts with PrestaShop’s core `Currency` class and `Configuration` class for data management.

### 4.4 JavaScript Assets (`views/js/`)

There are no custom JavaScript files in this module. All functionality is server-side PHP.

### 4.5 CSS Stylesheets (`views/css/`)

There are no custom CSS files in this module. The module does not introduce any front-office visual elements or complex back-office styling beyond standard PrestaShop form elements.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**: None. The module does not display content via hooks.
- **Admin templates (`views/templates/admin/`)**:
  - `views/admin.tpl`
    - **Purpose**: This template is rendered by the `getContent()` method in `cnbrates.php` to display the module’s configuration form in the PrestaShop back office.
    - **Content**: It contains the HTML structure for the settings described in Section 4.1, including input fields for update frequency, update method, currency selection, and the display of the cron job URL. It uses standard PrestaShop form helpers and styling.
- **Front-office templates (`views/templates/front/`)**: None.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does **not** create any custom SQL tables.
  - It stores its configuration settings in PrestaShop’s `ps_configuration` table. Key configuration keys include:
    - `CNBRATES_UPDATE_FREQUENCY`
    - `CNBRATES_UPDATE_METHOD`
    - `CNBRATES_CURRENCIES` (likely a comma-separated list of currency IDs)
    - `CNBRATES_CRON_TOKEN` (a unique token for cron job security)
    - `MYPRESTA_UPDATES_CNBRATES` (for MyPresta.eu update checks)
  - It updates the `exchange_rate` column in the `ps_currency` table for selected currencies.
- **Registered Hooks Table**:
  The module registers the following hooks, primarily for its own lifecycle management and potentially for update checks, rather than displaying content:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | On every page load in the front office (before HTML output). | Often used for JS/CSS inclusion, or in this case, potentially for the “On page load” update method if configured, or for MyPresta.eu update checks. |
| `displayRightColumn` | Renders content in the right column of the front office. | Not used for content display by this module, possibly a legacy hook registration or for internal checks. |
| `displayLeftColumn` | Renders content in the left column of the front office. | Not used for content display by this module, possibly a legacy hook registration or for internal checks. |
| `displayFooter` | Renders content in the footer of the front office. | Not used for content display by this module, possibly a legacy hook registration or for internal checks. |
| `displayBackOfficeHeader` | On every page load in the back office. | Used to include module-specific CSS/JS for the configuration page, or to display update notifications from MyPresta.eu. |
| `actionAdminCurrenciesControllerSaveAfter` | After a currency is saved in the back office. | Could be used to re-evaluate currency settings or trigger an update if a currency’s status changes. |
| `actionAdminCurrenciesControllerDeleteAfter` | After a currency is deleted in the back office. | Could be used to remove the deleted currency from the module’s update list. |

## 5. Official Support & Updates

For official updates, technical support, and the latest versions of the “Currency rates from Česká národní banka (CNB)” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality or integration.
