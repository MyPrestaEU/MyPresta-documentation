---
title: "The National Bank of Slovakia (NBS) - currency rates - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the The National Bank of Slovakia (NBS) - currency rates PrestaShop module by MyPresta.eu."
sidebar:
  label: "The National Bank of Slovakia (NBS) - currency rates - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy The National Bank of Slovakia (NBS) - currency rates Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/the-national-bank-of-slovakia-nbs-currency-rates.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/the-national-bank-of-slovakia-nbs-currency-rates/)
>
> ---


# The National Bank of Slovakia (NBS) - currency rates

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for fetching external data, which are almost universally available on modern hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the module name to access its settings.

#### **1. Enable / Disable Module**

- **What this setting does:** This is a standard PrestaShop switch to activate or deactivate the module’s core functionality.
- **Effect of changing this setting:**
  - *When enabled:* The module will start fetching and updating currency rates according to your settings.
  - *When disabled:* The module will stop all operations, and your currency rates will no longer be automatically updated by NBS data.
- **Recommended value:** **YES** (to enable the module’s functionality).
- **Merchant scenario / example:** If you temporarily want to stop automatic updates (e.g., during maintenance or if you switch to manual rate management), you can disable it. Otherwise, keep it enabled for continuous updates.

#### **2. CRON URL for automatic updates**

- **What this setting does:** This displays a unique URL that you need to set up as a “cron job” on your web hosting server. A cron job is a scheduled task that tells your server to visit this URL at regular intervals, triggering the module to fetch and update the latest NBS currency rates automatically.
- **Effect of changing this setting:**
  - *When correctly set up as a cron job:* Your currency rates will be updated automatically without any manual intervention.
  - *When not set up as a cron job:* The module will not update rates automatically. You would have to manually visit this URL in your browser to trigger an update (which defeats the purpose of automation).
- **Recommended value:** This is a generated URL. You should **copy this URL** and paste it into your hosting control panel’s cron job scheduler.
- **Merchant scenario / example:** You want your currency rates to update every day at 3 AM. You would copy this URL, go to your hosting panel (e.g., cPanel, Plesk, or ask your host for help), and create a cron job that executes this URL daily at 3 AM.

#### **3. Add percentage margin to exchange rates**

- **What this setting does:** This allows you to add a percentage value on top of the official exchange rates fetched from the NBS. This margin is applied to all currencies updated by the module.
- **Effect of changing this setting:**
  - *When set to 0 (or left empty):* Your exchange rates will be exactly as provided by the NBS.
  - *When set to a positive value (e.g., 2):* The module will increase the NBS exchange rate by that percentage (e.g., if the rate is 1 EUR = 1.10 USD, with a 2% margin, it becomes 1 EUR = 1.122 USD). This effectively makes your products slightly more expensive when paid in the non-base currency.
- **Recommended value:** **0** (if you want exact NBS rates) or a small positive percentage (e.g., **1-3%**) to cover transaction fees or market volatility.
- **Merchant scenario / example:** You want to account for potential bank fees when converting payments or simply want a small buffer on your international sales. Setting this to “2” will add a 2% margin to all updated exchange rates.

#### **4. Update only selected currencies**

- **What this setting does:** This option allows you to choose specific currencies in your PrestaShop store that should be updated by the NBS module. If you have many currencies but only want NBS to manage a few, this is useful.
- **Effect of changing this setting:**
  - *When unchecked:* The module will attempt to update all active currencies in your PrestaShop store that have a corresponding rate available from NBS.
  - *When checked, and specific currencies are selected:* Only the chosen currencies will have their exchange rates updated by the module. Other currencies will retain their existing rates (manual or from other sources).
- **Recommended value:** **Check this box** and select only the currencies you actively manage with NBS data. This prevents unintended changes to other currencies.
- **Merchant scenario / example:** Your base currency is EUR, and you also sell in USD and CZK. You want NBS to update USD and CZK rates, but you manually manage GBP rates. You would check this box and select only USD and CZK from the list.

#### **5. List of currencies to update**

- **What this setting does:** This is a multi-select list that appears only if “Update only selected currencies” is checked. It shows all active currencies in your PrestaShop store, allowing you to pick which ones the module should update.
- **Effect of changing this setting:**
  - *Selecting currencies:* These currencies will have their exchange rates automatically updated by the NBS module.
  - *Deselecting currencies:* These currencies will be ignored by the NBS module and their rates will not be changed.
- **Recommended value:** Select all currencies for which you want to use NBS rates.
- **Merchant scenario / example:** Following the previous example, you would click on “USD” and “CZK” in this list to ensure only those are updated.

#### **6. Save Button**

- **What this setting does:** Applies all the changes you’ve made on the configuration page.
- **Effect of changing this setting:** Your module settings will be saved and will take effect immediately (for future cron job runs or manual updates).
- **Recommended value:** Always click **“Save”** after making any changes.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable / Disable Module | YES | Activates/deactivates module functionality. |
| Module Configuration | CRON URL for automatic updates | Generated URL | Copy and set up as a cron job for automated rate updates. |
| Module Configuration | Add percentage margin to exchange rates | 0 (or 1-3%) | Adds a percentage buffer to NBS rates for pricing strategy. |
| Module Configuration | Update only selected currencies | Check & select | Restricts NBS updates to specific chosen currencies. |
| Module Configuration | List of currencies to update | Select desired | Choose which active currencies receive NBS rate updates. |
| Module Configuration | Save Button | Click after changes | Saves all module configuration settings. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My currency rates are not updating automatically. What should I do?**
A:

1. **Check Module Status:** Ensure the module is enabled in **Modules > Module Manager**.
2. **Verify Cron Job:** The most common issue is an incorrectly set up cron job.
   - Go back to the module configuration page and copy the “CRON URL” again.
   - Log into your hosting control panel (cPanel, Plesk, etc.) and navigate to the “Cron Jobs” or “Scheduled Tasks” section.
   - Double-check that the URL is exactly as provided by the module and that the schedule (e.g., daily, hourly) is correct.
   - Ensure the command uses `wget` or `curl` to execute the URL (e.g., `wget -O /dev/null "YOUR_CRON_URL_HERE"`).
   - If unsure, contact your hosting provider’s support with the CRON URL and ask them to set it up for you.
3. **Check Server Logs:** Your hosting provider might have logs for cron job execution that can indicate if there’s an error.

**Q2: The module is enabled, but some currencies are not updating.**
A:

1. **Check “Update only selected currencies”:** Go to the module configuration. If “Update only selected currencies” is checked, ensure that the specific currencies you expect to update are selected in the “List of currencies to update.”
2. **NBS Data Availability:** The National Bank of Slovakia might not provide rates for all currencies. The module can only update currencies for which NBS publishes data. Check the official NBS website for available currency pairs.
3. **PrestaShop Currency Status:** Ensure the currencies in question are active in your PrestaShop store (**International > Currencies**). Inactive currencies cannot be updated.

**Q3: How often should I run the cron job?**
A: For most stores, running the cron job once a day is sufficient to keep rates current. If your business requires extremely real-time rates due to high-volume international transactions or volatile markets, you could set it to run more frequently (e.g., every 6 or 12 hours), but daily is generally adequate.

**Q4: I added a margin, but the prices don’t seem to reflect it.**
A:

1. **Save Settings:** Ensure you clicked the “Save” button after setting the margin.
2. **Trigger Update:** The margin will only apply when the exchange rates are next updated. This will happen with your next cron job run, or you can manually trigger an update by visiting the CRON URL in your browser.
3. **Clear Cache:** Sometimes, PrestaShop’s cache might hold old values. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions).

**Q5: Will this module affect my base currency?**
A: No, the module updates exchange rates *relative* to your base currency. Your base currency’s value itself remains constant. For example, if your base currency is EUR, the module will update how many USD or CZK equal 1 EUR.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “The National Bank of Slovakia (NBS) - currency rates” module follows a standard PrestaShop module architecture, primarily leveraging a main module class (`cronjob.php`) for configuration and hook management, and a front controller (`cronjob.php`) to handle the cron job execution. It interacts with PrestaShop’s core currency management to update rates. The module’s primary function is to fetch external data (NBS rates) and integrate it into PrestaShop’s `Currency` object model.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `controllers/front/cronjob.php`
    - **Class name & parent class:** `NbsratesCronjobModuleFrontController` extending `ModuleFrontController`.
    - **Responsibility:** This controller is specifically designed to be called by a cron job. When accessed, it initiates the process of fetching the latest currency rates from the National Bank of Slovakia and updating them in the PrestaShop database. It does not render any visual output to the browser but performs background processing. It handles the logic for applying the configured percentage margin and updating only selected currencies.
  - `controllers/front/index.php`
    - **Class name & parent class:** This is typically an empty file or a placeholder, often used to prevent directory listing or to ensure a valid entry point for older PrestaShop versions. It does not contain specific module logic for NBS rates.
- **Back-Office Admin Controllers**: None. All administration is handled via the main module’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

The module does not define custom `ObjectModel` classes. It directly interacts with PrestaShop’s core `Currency` class to update exchange rates.

### 4.4 JavaScript Assets (`views/js/`)

None. The module does not include any custom JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)

None. The module does not include any custom CSS files.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Admin templates (`views/templates/admin/`)**:
  - `views/templates/admin/admin.tpl`
    - **Purpose:** This template is rendered when the module’s configuration page is accessed in the PrestaShop Back Office. It displays the input fields for enabling/disabling the module, the CRON URL, the margin percentage, and the currency selection options. It uses standard PrestaShop form helpers and elements.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  The module does not create custom SQL tables. It stores its configuration settings in PrestaShop’s `ps_configuration` table.

  - `PS_NBS_RATES_ENABLED`: Stores the module’s enabled/disabled status.
  - `PS_NBS_RATES_MARGIN`: Stores the percentage margin to be applied.
  - `PS_NBS_RATES_SELECTED_CURRENCIES`: Stores a serialized array of currency IDs if “Update only selected currencies” is active.
  - `PS_NBS_RATES_CRON_TOKEN`: Stores a unique token for the cron URL for security.
- **Registered Hooks Table**:
  The module primarily uses the `actionFrontControllerSetMedia` hook (implicitly, if it were to load assets, though it doesn’t) and relies on its `install()` and `uninstall()` methods for setup and cleanup. Its core functionality is triggered by the front controller `cronjob.php` rather than a traditional PrestaShop hook.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `install()` | During module installation | Sets up default configuration values in `ps_configuration` and registers the module. |
| `uninstall()` | During module uninstallation | Cleans up configuration values from `ps_configuration`. |
| (Cron Job) | External HTTP request to `controllers/front/cronjob.php` | Fetches NBS rates, applies margin, and updates `ps_currency` table. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for “The National Bank of Slovakia (NBS) - currency rates” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and configuration.
