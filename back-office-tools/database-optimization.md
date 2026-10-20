---
title: "Database Optimization - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Database Optimization PrestaShop module by MyPresta.eu."
sidebar:
  label: "Database Optimization - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Database Optimization Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/database-optimization.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/database-optimization/)
>
> ---


# Database Optimization

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are required.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main and only configuration screen for the Database Optimization module. You’ll find it by navigating to **Modules > Module Manager** and clicking “Configure” next to “Database Optimization”.

#### **Unwanted carts**

- **What this setting does:** This option controls whether the module will remove old, abandoned shopping carts from your database. These are carts that customers started but never completed an order for.
- **Effect of changing this setting:**
  - *When set to “Yes”:* The module will periodically delete these old, incomplete carts. This reduces the size of your database and can improve performance, as PrestaShop doesn’t have to manage data for thousands of abandoned carts.
  - *When set to “No”:* Old shopping carts will remain in your database. While this keeps historical data, it can contribute to database bloat over time.
- **Recommended value:** **Yes**. Unless you have a specific business reason to keep all abandoned cart data (e.g., for very deep historical analysis), cleaning them out is beneficial for performance.
- **Merchant scenario / example:** If you notice your database growing very large and your store slowing down, enabling this option is a quick win to remove a common source of unnecessary data.

#### **Connections**

- **What this setting does:** This option controls whether the module will remove old connection logs from your database. PrestaShop records every visitor’s connection to your store, which can accumulate rapidly.
- **Effect of changing this setting:**
  - *When set to “Yes”:* The module will periodically delete old connection logs. This significantly reduces database size, as connection logs can be one of the largest tables in a busy store.
  - *When set to “No”:* Connection logs will be retained indefinitely, potentially leading to a very large database.
- **Recommended value:** **Yes**. For most stores, very old connection logs are not critical for daily operations and can be safely removed to improve performance.
- **Merchant scenario / example:** If your store has a high volume of traffic, connection logs can grow extremely fast. Enabling this helps prevent your database from becoming excessively large and slow.

#### **Connections Page**

- **What this setting does:** This option specifically targets connection logs related to individual pages visited. It works in conjunction with the “Connections” setting.
- **Effect of changing this setting:**
  - *When set to “Yes”:* If “Connections” is also “Yes”, the module will remove old logs detailing which specific pages visitors viewed.
  - *When set to “No”:* Even if “Connections” is “Yes”, the module will retain the page-specific connection logs.
- **Recommended value:** **Yes**. Similar to general connections, page-specific logs can be very numerous and are often not needed for long-term analysis if you’re using external analytics tools like Google Analytics.
- **Merchant scenario / example:** If you rely on Google Analytics for page view statistics, you likely don’t need PrestaShop to store this granular data indefinitely, making it safe to clean.

#### **Connections Source**

- **What this setting does:** This option specifically targets connection logs related to the source of the visitor (e.g., direct, search engine, referral). It works in conjunction with the “Connections” setting.
- **Effect of changing this setting:**
  - *When set to “Yes”:* If “Connections” is also “Yes”, the module will remove old logs detailing where visitors came from.
  - *When set to “No”:* Even if “Connections” is “Yes”, the module will retain the source-specific connection logs.
- **Recommended value:** **Yes**. Like other connection data, this can often be managed by external analytics tools.
- **Merchant scenario / example:** If your marketing team uses tools like Google Analytics or other CRM systems to track traffic sources, the internal PrestaShop logs might be redundant and can be cleaned to save database space.

#### **Guests**

- **What this setting does:** This option controls whether the module will remove old, inactive guest accounts from your database. These are accounts created for visitors who started a checkout as a guest but never completed it, or simply browsed without registering.
- **Effect of changing this setting:**
  - *When set to “Yes”:* The module will periodically delete these old guest accounts. This helps keep your customer database clean and focused on active or registered users.
  - *When set to “No”:* Old guest accounts will remain in your database indefinitely.
- **Recommended value:** **Yes**. Unless you have a specific need to retain every single guest record, cleaning them out helps maintain a tidy database.
- **Merchant scenario / example:** If your store has many visitors who browse but don’t register or complete purchases, the guest table can grow significantly. Cleaning these helps keep your customer data manageable.

#### **Check updates**

- **What this setting does:** This setting controls whether the module will automatically check for new versions and updates available from MyPresta.eu.
- **Effect of changing this setting:**
  - *When set to “Enable”:* The module will periodically connect to MyPresta.eu to see if a newer version is available. If so, you will receive a notification in your PrestaShop Back Office.
  - *When set to “Disable”:* The module will not check for updates. You will need to manually check your MyPresta.eu account for new versions.
- **Recommended value:** **Enable**. This ensures you are always aware of available updates, which often include bug fixes, performance improvements, and new features.
- **Merchant scenario / example:** You want to ensure your modules are always up-to-date for security and performance. Enabling this provides convenient notifications.

#### **Updates notifications**

- **What this setting does:** This setting controls whether you receive notifications in your PrestaShop Back Office when an update is available (if “Check updates” is enabled).
- **Effect of changing this setting:**
  - *When set to “Enable”:* You will see a notification in your Back Office when a new version of the module is detected.
  - *When set to “Disable”:* Even if “Check updates” is enabled and an update is available, you will not receive a visible notification in the Back Office.
- **Recommended value:** **Enable**. This works hand-in-hand with “Check updates” to keep you informed.
- **Merchant scenario / example:** You want to be immediately alerted when an update is ready so you can plan to install it, ensuring your store benefits from the latest improvements.

#### **Module page**

- **What this setting does:** This setting is likely a display option for the module’s own page or information within the Back Office. (Based on typical MyPresta.eu module structure, this might control a link or a specific display element related to the module itself).
- **Effect of changing this setting:**
  - *When set to “Enable”:* Likely displays a link or section related to the module’s information or other MyPresta.eu modules.
  - *When set to “Disable”:* This link or section will be hidden.
- **Recommended value:** **Enable**. It usually provides quick access to support or other useful resources.
- **Merchant scenario / example:** You want easy access to MyPresta.eu resources directly from your module configuration page.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Unwanted carts | Yes | Removes old, abandoned shopping carts to reduce database size and improve performance. |
| Module Configuration | Connections | Yes | Removes old visitor connection logs to significantly reduce database size. |
| Module Configuration | Connections Page | Yes | Removes old logs of specific pages visited by connections. |
| Module Configuration | Connections Source | Yes | Removes old logs of traffic sources for connections. |
| Module Configuration | Guests | Yes | Removes old, inactive guest accounts to keep customer data clean. |
| Module Configuration | Check updates | Enable | Automatically checks MyPresta.eu for module updates. |
| Module Configuration | Updates notifications | Enable | Displays Back Office notifications when module updates are available. |
| Module Configuration | Module page | Enable | Controls display of module-related links/information on the config page. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: After enabling the module, my store doesn’t seem faster. What gives?**
A: Database optimization is one piece of the performance puzzle. While it cleans up unnecessary data, other factors like server resources, image optimization, heavy modules, or unoptimized custom themes can still slow down your store. Ensure you’ve also cleared your PrestaShop cache (Advanced Parameters > Performance) after configuration.

**Q: Will this module delete important customer data or orders?**
A: No. This module is specifically designed to target *unwanted* and *inactive* data: abandoned carts, old connection logs, and guest accounts that never converted. It does not touch completed orders, active customer accounts, product data, or other critical store information.

**Q: How often does the module clean the database? Is it automatic?**
A: The module performs its cleaning operations when its configuration is saved or when certain background tasks are triggered by PrestaShop. It’s not a continuous, real-time cleaner. The primary benefit comes from the removal of accumulated old data. For continuous, scheduled cleaning, you might need to combine it with a cron job that periodically triggers the module’s cleaning logic (though this module primarily focuses on one-time or on-save cleaning).

**Q: I disabled “Check updates” and “Updates notifications” but now I want to know about updates. How do I re-enable them?**
A: Simply go back to the module’s configuration page (Modules > Module Manager > Configure Database Optimization) and set both “Check updates” and “Updates notifications” to “Enable”. Save your changes, and the module will resume checking and notifying you about new versions.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The Database Optimization module is a straightforward PrestaShop module primarily designed to execute database cleaning operations. It follows the standard PrestaShop module structure, leveraging the `Module` class and its `install()` and `uninstall()` methods for setup and teardown. Its core functionality resides within the `getContent()` method, which handles the Back Office configuration form and triggers the database optimization logic upon form submission. It does not introduce custom controllers, models, or front-office assets, making it a lightweight and focused utility.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. All operations are handled in the Back Office or via the main module class.
- **Back-Office Admin Controllers**: None. The configuration is managed directly within the `dboptimization.php` file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

- **Main Module Class**: `dboptimization/dboptimization.php`
  - **Class Name**: `DbOptimization`
  - **Parent Class**: `Module`
  - **Responsibility**:
    - Handles module installation (`install()`) and uninstallation (`uninstall()`).
    - Manages Back Office configuration form display and submission (`getContent()`).
    - Contains the core logic for database cleaning based on configured options.
    - Registers and unregisters hooks (though this module primarily uses `displayBackOfficeHeader` for update checks, not front-office display).
    - Manages configuration values using `Configuration::get()` and `Configuration::updateValue()`.
    - Includes update checking logic (`checkforupdates()`) and notification display.

### 4.4 JavaScript Assets (`views/js/`)

- None. The module does not include any custom JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)

- None. The module does not include any custom CSS files.

### 4.6 Smarty Template Structure (`views/templates/`)

- None. The module renders its configuration form directly within the `getContent()` method using PrestaShop’s `HelperForm` (or similar internal rendering logic), rather than external `.tpl` files.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any custom database tables.
  - It interacts with existing PrestaShop tables, primarily:
    - `ps_cart`: For “Unwanted carts”.
    - `ps_connections`: For “Connections”.
    - `ps_connections_page`: For “Connections Page”.
    - `ps_connections_source`: For “Connections Source”.
    - `ps_guest`: For “Guests”.
  - Configuration values are stored in the `ps_configuration` table:
    - `dbopt_cart`
    - `dbopt_connections`
    - `dbopt_connections_page`
    - `dbopt_connections_source`
    - `dbopt_guest`
    - `update_dboptimization` (for update check timestamp)
    - `mypresta_updates` (global update notification setting)
    - `dbopt_check_updates`
    - `dbopt_updates_notifications`
    - `dbopt_module_page`
- **Registered Hooks Table**:

| Hook Name | File / Method | Execution Timing | Technical Purpose |
| --- | --- | --- | --- |
| `displayBackOfficeHeader` | `dboptimization.php` | Renders in the header of Back Office pages. | Used by the module to inject update notifications if `dbopt_check_updates` and `dbopt_updates_notifications` are enabled. |
| `actionAdminControllerSetMedia` | `dboptimization.php` | Executed when an admin controller sets its media (CSS/JS). | Potentially used for update checks or to ensure any necessary assets (if they existed) are loaded in the admin. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and comprehensive support for the Database Optimization module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our dedicated support team is available to assist merchants and developers with any questions or issues related to the module’s functionality and integration.
