---
title: "Currency rates from Banca Nationala a Romaniei - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Currency rates from Banca Nationala a Romaniei PrestaShop module by MyPresta.eu."
sidebar:
  label: "Currency rates from Banca Nationala a Romaniei - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Currency rates from Banca Nationala a Romaniei Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/currency-rates-from-banca-nationala-a-romaniei.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/currency-rates-from-banca-nationala-a-romaniei/)
>
> ---


# Currency rates from Banca Nationala a Romaniei

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for fetching external data feeds, which are standard on most modern hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the module name to access its settings.

#### **Settings & Options**

1. **Check for module updates**

   - **What this setting does:** This switch controls whether the module periodically checks MyPresta.eu for new versions or important updates.
   - **Effect of changing this setting:**
     - *When enabled (YES):* The module will occasionally connect to MyPresta.eu to see if a newer version is available. If an update is found, a notification might appear in your PrestaShop back office, prompting you to download and install it.
     - *When disabled (NO):* The module will not check for updates automatically. You will need to manually check your MyPresta.eu account for new versions.
   - **Recommended value:** **YES**. It’s always recommended to keep your modules updated to benefit from new features, bug fixes, and security improvements.
   - **Merchant scenario / example:** You want to ensure your currency rates module is always running the latest, most stable version without constantly checking manually. Enabling this will give you a heads-up when an update is ready.
2. **Update currency rates**

   - **What this setting does:** This is the core function of the module. When you click this button, the module will immediately fetch the latest exchange rates from the Banca Naţională a României (BNR) and apply them to the currencies configured in your PrestaShop store.
   - **Effect of changing this setting:** Clicking this button triggers an immediate update of all exchange rates in your store based on the BNR feed. This is a manual trigger for the update process.
   - **Recommended value:** This is an action button, not a setting. Click it whenever you need an immediate update, or after configuring your currencies.
   - **Merchant scenario / example:** It’s the beginning of the trading day, and you want to ensure all your prices reflect the very latest exchange rates before customers start placing orders. You would click this button.
3. **Cronjob URL**

   - **What this setting does:** This field displays a unique URL that you can use to automate the currency rate updates. This URL is designed to be called by a “cron job” on your web server, which is a scheduled task that runs automatically at specified intervals (e.g., once a day, every hour).
   - **Effect of changing this setting:** This is a display-only field. Copying and setting this URL in your hosting panel’s cron job scheduler will ensure that your currency rates are updated automatically without you having to manually click the “Update currency rates” button.
   - **Recommended value:** Copy this URL and set up a cron job on your server to run it at least once a day, or more frequently if your business requires it.
   - **Merchant scenario / example:** You want your currency rates to update every morning at 6 AM automatically, even when you’re not at your computer. You would copy this URL and configure a cron job on your hosting server to execute it daily at 6 AM.
4. **Currency to update**

   - **What this setting does:** This dropdown list allows you to select which specific currencies in your PrestaShop store should be updated by the BNR feed. The BNR feed primarily provides rates against RON. The module will then convert these to your shop’s default currency and then to other selected currencies.
   - **Effect of changing this setting:**
     - *When a specific currency is selected:* Only that currency’s exchange rate will be updated by the module.
     - *When “All currencies” is selected:* The module will attempt to update all active currencies in your PrestaShop store using the BNR feed.
   - **Recommended value:** **All currencies**, unless you have a specific reason to only update one. This ensures all your international pricing is consistent.
   - **Merchant scenario / example:** Your store accepts EUR, USD, and GBP. You want all these currencies to be updated daily based on the BNR feed’s conversion to RON and then to your shop’s default currency. You would select “All currencies”. If you only wanted to update EUR for some reason, you would select “EUR”.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Check for module updates | YES | Enables automatic checks for new module versions. |
| Module Configuration | Update currency rates | N/A (Action Button) | Manually triggers an immediate update of all selected currency rates from BNR. |
| Module Configuration | Cronjob URL | N/A (Display Only) | Provides the URL to set up an automated scheduled task for currency rate updates. |
| Module Configuration | Currency to update | All currencies | Determines which currencies in your shop will receive automatic rate updates from BNR. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My currency rates aren’t updating. What should I check first?**
A1:

1. **Manual Update:** Go to the module’s configuration page and click the “Update currency rates” button. If this works, the issue is likely with your cron job setup.
2. **Cron Job:** Double-check that your cron job is correctly configured on your hosting server using the exact “Cronjob URL” provided by the module. Ensure it’s set to run at the desired frequency.
3. **Module Settings:** Verify that “All currencies” or the specific currencies you want to update are selected in the “Currency to update” dropdown.
4. **PrestaShop Currencies:** Ensure the currencies you expect to be updated are active in your PrestaShop store (International > Currencies).
5. **Server Connectivity:** Make sure your server can access external websites (specifically the BNR feed). Sometimes firewall rules or network issues can prevent this.

**Q2: The module says it updated, but the prices on my front office don’t seem right.**
A2:

1. **Clear Cache:** PrestaShop uses caching. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). This ensures your store displays the latest data.
2. **Browser Cache:** Clear your browser’s cache and cookies, or try viewing your store in an incognito/private browsing window to rule out local caching issues.
3. **Currency Selection:** Ensure you are viewing the prices in the correct currency on the front office.

**Q3: Can I update rates more frequently than once a day?**
A3: Yes, you can. When setting up your cron job, you can configure it to run every hour, every few hours, or at any interval supported by your hosting provider’s cron scheduler. Just be mindful of potential server load if you set it to run extremely frequently (e.g., every minute), though for currency updates, this is rarely an issue.

**Q4: What if the BNR feed is temporarily unavailable?**
A4: If the BNR feed is unavailable, the module will likely fail to fetch new rates. It will not delete or reset your existing rates; they will simply remain unchanged until the feed becomes available again and a successful update occurs. You might see an error message in your server’s cron job logs if the update fails.

**Q5: My store’s default currency is not RON. Will this module still work?**
A5: Yes, absolutely. The module is designed to work regardless of your store’s default currency. It fetches the BNR rates (which are typically against RON) and then intelligently converts them to your shop’s default currency, and subsequently to any other active currencies you have enabled for update.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters.

### 4.1 Architecture Overview

The “Currency rates from Banca Nationala a Romaniei” module is a straightforward PrestaShop module primarily focused on a single task: fetching and updating currency exchange rates. It follows a basic PrestaShop module structure, leveraging the `Module` class for installation and configuration, and `ModuleFrontController` for its cron job functionality. It does not introduce custom `ObjectModel` classes or database tables, relying instead on PrestaShop’s core `Currency` class and `Configuration` table for settings. The core logic involves parsing an XML feed from BNR and updating existing currency rates.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

These controllers are designed to be accessed externally, primarily for cron job automation.

- `controllers/front/cronjob.php`
  - **Class name & parent class:** `BnrratesCronjobModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** This is the dedicated endpoint for the automated currency update cron job. When accessed, it triggers the module’s core logic to fetch the latest exchange rates from BNR and update them in the PrestaShop database. It typically returns a simple success or error message, suitable for cron job logging. It does not render any visual output for a browser.
- `controllers/front/index.php`
  - **Class name & parent class:** `BnrratesIndexModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** This controller likely serves as a fallback or a default entry point, though its primary function might be minimal given the explicit `cronjob.php` controller. In many modules, an `index.php` front controller might redirect or display a simple message if accessed directly without specific parameters. For this module, its practical use is likely limited, with `cronjob.php` handling the main front-office interaction.

#### Back-Office Admin Controllers

The module does not implement any custom `AdminController` classes. All back-office configuration is handled directly within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

The module does not introduce any custom classes or `ObjectModel` definitions in the `classes/` directory. It directly interacts with PrestaShop’s core `Currency` class and `Configuration` class.

### 4.4 JavaScript Assets (`views/js/`)

The module does not include any custom JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)

The module does not include any custom CSS files.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Admin templates (`views/templates/admin/`)**:
  - `bnrrates/views/admin.tpl`
    - **Purpose:** This template is responsible for rendering the module’s configuration form in the PrestaShop Back Office. It displays the settings like “Check for module updates,” the “Update currency rates” button, the “Cronjob URL,” and the “Currency to update” dropdown.
    - **Variables:** It would typically receive variables from the `getContent()` method of the main module file, such as the current values of the configuration settings and the generated cron job URL.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any custom SQL tables.
  - It stores its configuration settings in PrestaShop’s `ps_configuration` table. The relevant configuration keys are:
    - `BNRRATES_MYPRESTA_UPDATES`: Stores the boolean value for checking module updates.
    - `BNRRATES_CURRENCY_TO_UPDATE`: Stores the ID of the currency to update, or a special value (e.g., `0` or `all`) for all currencies.
    - `BNRRATES_LAST_UPDATE_TIME`: (Likely) Stores a timestamp of the last successful update.
    - `BNRRATES_CRON_TOKEN`: Stores a unique token used in the cron job URL for security.
- **Registered Hooks Table**:
  The module primarily uses the `action` hooks for its core functionality and potentially `display` hooks for notifications or specific content (though no specific front-office display hooks are explicitly listed in the provided info, the module description mentions “Header, Columns, Product, or Footer” as potential areas, which would imply `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayProductButtons`, `displayFooter` etc. However, given the module’s purpose, these would likely be for displaying a notification or status, not for core functionality).

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionModuleInstall` | During module installation | Registers module configuration, creates default settings. |
| `actionModuleUninstall` | During module uninstallation | Cleans up module configuration from `ps_configuration`. |
| `actionAdminControllerSetMedia` | When an admin controller is loaded | Potentially registers CSS/JS for the admin configuration page (though none are present in this module). |
| `displayBackOfficeHeader` | In the header of the Back Office | Potentially displays update notifications or other admin-specific content. |
| `displayHeader` | In the `<head>` section of the front office | Not directly used for core functionality, but could be used for meta tags or JS/CSS if needed. |
| `displayLeftColumn` | In the left column of the front office | Not directly used for core functionality, but could be used for displaying a currency block. |
| `displayRightColumn` | In the right column of the front office | Not directly used for core functionality, but could be used for displaying a currency block. |
| `displayProductButtons` | On the product page, near add to cart | Not directly used for core functionality, but could be used for currency-related info. |
| `displayFooter` | In the footer of the front office | Not directly used for core functionality, but could be used for currency-related info. |

The core currency update logic is triggered by accessing the `cronjob.php` front controller, which is not a standard PrestaShop hook but an external endpoint.

## 5. Official Support & Updates

For official updates, technical support, and to download the latest versions of the “Currency rates from Banca Nationala a Romaniei” module, please log in to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and configuration.
