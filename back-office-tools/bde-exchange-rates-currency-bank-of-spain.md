---
title: "BdE Exchange Rates & Currency (Bank of Spain) - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the BdE Exchange Rates & Currency (Bank of Spain) PrestaShop module by MyPresta.eu."
sidebar:
  label: "BdE Exchange Rates & Currency (Bank of Spain) - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy BdE Exchange Rates & Currency (Bank of Spain) Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/bde-exchange-rates-currency-bank-of-spain.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/bde-exchange-rates-currency-bank-of-spain/)
>
> ---


# BdE Exchange Rates & Currency (Bank of Spain)

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions like cURL (for fetching external data), JSON (for processing data), and OpenSSL (for secure connections) are typically required and are standard on most modern hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” will take you to the main settings page for the “BdE Exchange Rates & Currency (Bank of Spain)” module. This is where you control how the module fetches and applies exchange rates.

#### **MyPresta.eu Live Updates**

- **What this setting does:** This section allows you to manage the module’s connection to MyPresta.eu for automatic updates and support.
- **Effect of changing this setting:**
  - *Entering your MyPresta.eu order ID and email:* Enables the module to check for new versions and receive updates directly from MyPresta.eu. This ensures you always have the latest features and bug fixes.
  - *Leaving it empty:* The module will not be able to check for automatic updates. You would need to manually download and install new versions from your MyPresta.eu account.
- **Recommended value:** Always enter your MyPresta.eu order ID and the email address associated with your purchase. This is crucial for receiving timely updates and support.
- **Merchant scenario / example:** You bought the module using `your.email@example.com` and your order ID was `MP12345`. Entering these details here means you’ll be notified directly in your PrestaShop back office when a new version of the module is released, and you can update with a single click.

#### **CRON Job URL**

- **What this setting does:** This displays a unique URL that you can use to set up a “CRON job” on your server. A CRON job is a scheduled task that automatically runs a specific command or URL at regular intervals (e.g., once a day).
- **Effect of changing this setting:**
  - *Setting up a CRON job with this URL:* The module will automatically fetch the latest exchange rates from the Bank of Spain at the frequency you define (e.g., daily). This ensures your currency rates are always up-to-date without any manual intervention.
  - *Not setting up a CRON job:* The exchange rates will not be automatically updated. You would need to manually visit this URL in your browser each time you want to update the rates, which is highly impractical and defeats the purpose of automation.
- **Recommended value:** Copy this URL and set up a daily CRON job on your hosting server. Most hosting control panels (like cPanel, Plesk) have a “Cron Jobs” section where you can easily add this URL to run once every 24 hours.
- **Merchant scenario / example:** You want your Euro exchange rates to update every morning at 3:00 AM. You copy the provided CRON URL, go to your hosting control panel, create a new CRON job, paste the URL, and set it to run daily at 3:00 AM. From then on, your rates will be automatically updated.

#### **Margin Adjustment (%)**

- **What this setting does:** This allows you to add a small percentage margin to the fetched exchange rates. This can be useful to cover potential transaction fees, currency conversion costs, or simply to give yourself a small buffer.
- **Effect of changing this setting:**
  - *Setting a positive percentage (e.g., 2%):* The module will increase the official exchange rate by that percentage. For example, if the official rate is 1 EUR = 1.10 USD, and you set a 2% margin, the module will use 1 EUR = 1.122 USD (1.10 \* 1.02). This means products priced in EUR will appear slightly more expensive when converted to USD.
  - *Setting 0% (default):* The module will use the exact official exchange rates without any adjustment.
- **Recommended value:** 0% unless you have specific business reasons (like covering bank fees) to add a margin. Transparency is often best for customer trust.
- **Merchant scenario / example:** Your payment gateway charges a 1.5% fee for international currency conversions. To offset this, you could set the Margin Adjustment to 1.5%. This ensures that your converted prices slightly account for this cost.

#### **Update Currency Rates**

- **What this setting does:** This is a manual trigger button to immediately fetch and update all exchange rates from the Bank of Spain.
- **Effect of changing this setting:**
  - *Clicking the button:* The module will instantly connect to the Bank of Spain, retrieve the latest rates, and update them in your PrestaShop store. This is useful for testing or for an immediate update outside of your CRON job schedule.
- **Recommended value:** Use this button for initial setup testing or if you need an immediate update. For regular updates, rely on the CRON job.
- **Merchant scenario / example:** You’ve just installed the module and want to verify that it’s working correctly and fetching the latest rates. You click this button to see the immediate effect.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | MyPresta.eu Order ID | Your Order ID | Enables automatic module updates and support. |
| Module Configuration | MyPresta.eu Email | Your Email | Enables automatic module updates and support. |
| Module Configuration | CRON Job URL | (Unique URL) | Set up a daily CRON job with this URL for automatic rate updates. |
| Module Configuration | Margin Adjustment (%) | 0% | Add a percentage buffer to exchange rates (e.g., for fees). |
| Module Configuration | Update Currency Rates | Click to trigger | Manually fetch and update exchange rates immediately. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My currency rates are not updating automatically.**
A:

1. **Check your CRON job setup:** Double-check that you have correctly set up the CRON job on your hosting server using the exact URL provided in the module configuration. Ensure it’s scheduled to run at least once a day.
2. **Verify CRON job execution:** Some hosting panels provide logs for CRON job execution. Check these logs to see if the CRON job is actually running and if there are any errors.
3. **Server connectivity:** Ensure your server has outbound access to external websites (specifically the Bank of Spain’s API). Sometimes firewalls can block this. Contact your hosting provider if you suspect this is the issue.
4. **Module configuration:** Ensure your MyPresta.eu details are entered correctly for potential update issues.

**Q: The prices in EUR seem slightly off, even after an update.**
A:

1. **Check Margin Adjustment:** Review the “Margin Adjustment (%)” setting in the module configuration. If it’s set to a value greater than 0, your prices will be adjusted by that percentage. Set it to 0% if you want exact official rates.
2. **PrestaShop rounding:** PrestaShop has its own rounding rules for prices. Ensure your currency settings in **International > Currencies** are configured to your desired decimal precision.
3. **Cache:** Clear your PrestaShop cache (Advanced Parameters > Performance) and your browser cache.

**Q: What happens on bank holidays or weekends when the Bank of Spain doesn’t publish new rates?**
A: The module is designed to handle this intelligently. If new rates are not available for a given day, it will continue to use the last successfully fetched rates. Once new rates are published, the module will update them on its next scheduled run.

**Q: Can I use this module with other currency modules?**
A: This module focuses specifically on fetching and applying official Bank of Spain rates. It generally works well alongside PrestaShop’s native multi-currency features. However, if you have other modules that *also* attempt to fetch or override exchange rates from different sources, there might be conflicts. It’s best to use one primary source for exchange rate updates to avoid inconsistencies.

**Q: I see a “MyPresta.eu Updates” section. What is it for?**
A: This section allows you to enter your MyPresta.eu order ID and email. This enables the module to check for new versions and receive updates directly from MyPresta.eu, ensuring you always have the latest features and bug fixes. It’s highly recommended to fill this out.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The `BdE Exchange Rates & Currency` module is a lightweight PrestaShop module primarily designed to integrate with the Bank of Spain’s official exchange rate API. It follows a standard PrestaShop module structure, leveraging the `Module` class for installation and configuration, and `ModuleFrontController` for handling CRON job requests. Its core functionality revolves around fetching external data, parsing it, and updating PrestaShop’s native `Currency` exchange rates.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- **`controllers/front/cronjob.php`**
  - **Class name & parent class:** `BderatesCronjobModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** This controller is the entry point for the scheduled CRON job. When accessed, it initiates the process of fetching the latest exchange rates from the Bank of Spain. It handles the API request, parses the response, and updates the exchange rates for the configured currencies in PrestaShop. It’s designed to be called externally by a server-side CRON scheduler and typically returns a simple success/failure message.
- **`controllers/front/index.php`**
  - **Class name & parent class:** `BderatesIndexModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** This is a placeholder controller, often included in modules but not actively used in this specific module’s core functionality. It might be present for routing purposes or as a default entry point, but the primary logic for rate updates is within `cronjob.php`.

#### Back-Office Admin Controllers

This module does not implement any custom Back-Office Admin Controllers. All configuration is handled via the main module’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or `ObjectModel`s in the `classes/` directory. It directly interacts with PrestaShop’s core `Currency` class to update exchange rates.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include any custom JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)

This module does not include any custom CSS files.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Admin templates (`views/templates/admin/`)

- **`views/templates/admin/admin.tpl`**
  - **Purpose:** This template is used to render the module’s configuration form in the PrestaShop Back Office. It displays the input fields for MyPresta.eu updates, the CRON job URL, margin adjustment, and the manual update button.
  - **Context:** Rendered by the `getContent()` method of the main `bderates.php` module file.
  - **Key elements:** Form elements for `mypresta_updates`, `update_`, `updatev_`, `currency_` settings.

### 4.7 Database Schema & Hooks Map

#### Database Tables

This module does not create any custom SQL tables. It stores its configuration settings directly in PrestaShop’s `ps_configuration` table using keys such as:

- `BDERATES_MYPRESTA_ID`
- `BDERATES_MYPRESTA_EMAIL`
- `BDERATES_MARGIN`
- `BDERATES_LAST_UPDATE`

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Not actively used for visual output by this module, but often registered by modules for general setup or asset loading. |
| `displayRightColumn` | In the right column of front-office pages. | Not actively used for visual output by this module. |
| `displayLeftColumn` | In the left column of front-office pages. | Not actively used for visual output by this module. |
| `displayFooter` | In the footer section of every front-office page. | Not actively used for visual output by this module. |
| `displayProductAdditionalInfo` | On the product page, below the main product information. | Not actively used for visual output by this module. |
| `actionUpdateCurrency` | Triggered after a currency’s exchange rate is updated. | This module *triggers* this hook when it updates currency rates, allowing other modules to react to the change. |
| `actionCronJob` | A custom hook often used by modules to register their CRON tasks. | The module’s `cronjob.php` controller is the primary mechanism for scheduled updates, but this hook might be registered for compatibility or future expansion. |

## 5. Official Support & Updates

For official updates, technical support, and the latest versions of the “BdE Exchange Rates & Currency (Bank of Spain)” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and integration.
