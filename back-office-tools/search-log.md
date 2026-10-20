---
title: "Search log - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Search log PrestaShop module by MyPresta.eu."
sidebar:
  label: "Search log - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Search log Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/search-log.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/search-log/)
>
> ---


# Search log

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special requirements beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Search log)

This is the main configuration screen for the “Search log” module. It provides a simple interface to enable or disable the logging functionality.

- **Menu Location:** Back Office > Modules > Module Manager > Search log > Configure

| Setting / Option | What this setting does | Effect of changing this setting | Recommended value | Merchant scenario / example |
| --- | --- | --- | --- | --- |
| **Enable Search Log** (Switch) | This switch controls whether the module actively records customer search queries. | *When enabled (YES):* Every time a customer uses your store’s search bar, their search term will be saved in the module’s log. You can then view these logs in the dedicated “Search Log” menu.   *When disabled (NO):* The module will stop recording new search queries. Existing logs will remain, but no new data will be collected. | **YES** | You’ve just installed the module and want to start collecting data immediately to understand what your customers are looking for. You would set this to YES. If you temporarily need to stop logging (e.g., during maintenance or if you have too much data), you could switch it to NO. |

### 2.2 Dedicated Admin Screen: Search Log Management (Back Office > Search Log)

This screen is where you can view and manage all the search queries recorded by the module. It provides a comprehensive list of what your customers are searching for.

- **Screen Name & Menu Location:** Back Office > **Search Log** (This will appear as a new menu item, usually under “Shop Parameters” or “Advanced Parameters” depending on your PrestaShop version).

**Available Actions & Settings:**
This screen typically presents a grid (list) of all recorded search terms. For each entry, you will usually see:

- **Search Keyword:** The exact term or phrase the customer typed into the search bar.
- **Number of Searches:** How many times this specific keyword has been searched.
- **Date of Last Search:** When this keyword was most recently searched.
- **Number of Results:** How many products were found for this search term (this is crucial for identifying “no results” searches).

**Grid / Management View:**
The grid allows you to:

- **Sort:** Click on column headers (e.g., “Search Keyword,” “Number of Searches”) to sort the list.
- **Filter:** Use the filter fields above the columns to narrow down the list (e.g., search for a specific keyword, or filter by number of results).
- **Export:** Some versions may offer an export option to download the data for further analysis in a spreadsheet program.
- **Delete:** You may have options to delete individual search entries or clear the entire log.

**Effect of changes:**

- **Viewing the list:** Provides immediate insights into customer search behavior.
- **Sorting/Filtering:** Helps you quickly identify popular searches, searches with no results, or trends over time.
- **Deleting entries:** Removes data from the log. This might be useful for cleaning up irrelevant entries or managing database size, but generally, it’s best to keep the data for historical analysis.

**Recommended workflow for daily store management:**

1. **Regularly check this screen:** Make it a habit to review the “Search Log” at least once a week.
2. **Focus on “No Results” searches:** Prioritize keywords that yielded zero results. These are your biggest opportunities:
   - Do you have the product but it’s not indexed correctly or the description is poor?
   - Is it a product you should consider stocking?
   - Is it a common misspelling you can account for with synonyms?
3. **Identify popular searches:** See what customers are most interested in. Ensure these products are prominently displayed, well-described, and easily found.
4. **Analyze trends:** Are there seasonal search terms? New product ideas emerging from customer queries?

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable Search Log | YES | Controls whether customer search queries are recorded. |
| Search Log Management | Search Keyword (Grid Column) | N/A | Displays the actual search term used by customers. |
| Search Log Management | Number of Searches (Grid Column) | N/A | Shows how many times a specific keyword was searched. |
| Search Log Management | Date of Last Search (Grid Column) | N/A | Indicates the most recent occurrence of a search term. |
| Search Log Management | Number of Results (Grid Column) | N/A | Crucial for identifying searches that yielded no products. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve enabled the module, but I don’t see any search logs appearing.**
A:

1. **Check if customers are actually searching:** Ensure your store’s search bar is visible and being used by visitors.
2. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes caching can prevent modules from fully initializing.
3. **Test yourself:** Perform a few searches on your front office while logged out (or in incognito mode) and then check the “Search Log” admin screen.
4. **Module Position:** While the module doesn’t have a visible front-office component, ensure it’s hooked correctly. The module typically hooks into `displayHeader` or similar, which is handled automatically. If issues persist, try re-installing.

**Q: The search log is growing very large. Will this slow down my store?**
A: While a very large database table can theoretically impact performance, for most stores, the `slog` table created by this module is unlikely to cause significant slowdowns. It’s a simple logging table. If you have millions of entries and notice issues, you can periodically clear older entries from the “Search Log” management screen or disable the module temporarily.

**Q: Can I see which customer made a specific search?**
A: No, this module is designed for aggregate keyword analysis, not individual customer tracking. It logs the keyword, not the customer ID. This ensures customer privacy while still providing valuable business insights.

**Q: How do I export the search log data for analysis in Excel?**
A: The “Search Log” management screen in your Back Office should have an “Export” button (often located near the top right of the grid, or as a bulk action). Click this to download the data, usually in CSV format, which can be opened with Excel or Google Sheets.

**Q: My custom theme’s search bar doesn’t seem to be logged.**
A: The module typically hooks into PrestaShop’s standard search functionality. If your custom theme uses a completely custom, non-standard search implementation (e.g., an AJAX search that bypasses PrestaShop’s core search controller), the module might not capture those queries. In such cases, you would need a developer to integrate the logging functionality directly into your custom search script.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters.

### 4.1 Architecture Overview

The “Search log” module is a straightforward PrestaShop module primarily focused on data logging. It follows a standard PrestaShop MVC pattern for its Back Office component, utilizing an `AdminController` to manage the logged search data. The front-office logging mechanism integrates directly with PrestaShop’s core search process, typically by hooking into an action that fires after a search is performed. It creates a dedicated database table to store search queries.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. The module integrates with the existing PrestaShop search functionality via hooks, rather than providing its own front controller.
- **Back-Office Admin Controllers**:

  - `searchlog/controllers/admin/AdminSlog.php`

    - **Class Name & Parent Class**: `AdminSlogController` extends `ModuleAdminController`.
    - **Responsibility**: This is the primary controller for managing the search log entries in the PrestaShop Back Office. It handles the display of the search log grid, including sorting, filtering, and potentially deletion actions. It’s responsible for fetching data from the `slog` database table and rendering it using PrestaShop’s `HelperList` or `HelperGrid` components.
    - **Tab Name**: “Search Log” (or similar, depending on installation).
    - **Managed Entity**: The `slog` database table.
  - `searchlog/controllers/admin/index.php`

    - **Class Name & Parent Class**: Not a class, but a standard PrestaShop `index.php` file within an admin controller directory.
    - **Responsibility**: This file typically serves as a security measure in PrestaShop admin directories, preventing direct directory listing. It usually contains a simple `header('Location: ../../index.php?controller=AdminHome'); exit;` or similar redirect, or just a `die('Forbidden');` statement. It does not contain module-specific logic.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes in the `classes/` directory. The core logic for interacting with the `slog` table is likely handled directly within the `AdminSlogController` or the main `searchlog/index.php` module file, possibly using a generic `Db::getInstance()->execute()` for simple data operations, or a basic `ObjectModel` definition if one was implicitly created or not listed in the dossier. Given the simplicity, a direct `Db` interaction is more probable.

### 4.4 JavaScript Assets (`views/js/`)

No custom JavaScript files are listed in the module archive. This suggests that the module relies entirely on PrestaShop’s core JS for its Back Office grid functionality and does not introduce any custom front-office JS.

### 4.5 CSS Stylesheets (`views/css/`)

No custom CSS files are listed in the module archive. This indicates that the module uses PrestaShop’s default Back Office styling for its configuration and management screens, and introduces no custom front-office styles.

### 4.6 Smarty Template Structure (`views/templates/`)

No custom template files are listed in the module archive. This implies that the module’s configuration form and the `AdminSlogController`’s grid view are rendered using PrestaShop’s default `HelperForm` and `HelperList` (or `HelperGrid`) templates, which are part of the core PrestaShop framework.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - `ps_slog` (or `_slog` with your table prefix):
    - This table is created by the module during installation.
    - It stores the logged search queries.
    - Typical fields would include:
      - `id_slog` (Primary Key, INT)
      - `keyword` (VARCHAR, stores the search term)
      - `results` (INT, number of results found for the keyword)
      - `counter` (INT, number of times this keyword has been searched)
      - `date_add` (DATETIME, timestamp of the first search for this keyword)
      - `date_upd` (DATETIME, timestamp of the last search for this keyword)
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Executed in the `<head>` section of every front-office page. | While the dossier lists `Header` as a front-office hook, for a logging module, `displayHeader` is often used to register assets or to ensure the module is active on all pages where a search might occur. The actual logging logic is more likely tied to an `action` hook. |
| `displayRightColumn` | Executed in the right column of the front office. | Unlikely to be used for logging, possibly for a future feature or a placeholder. |
| `displayLeftColumn` | Executed in the left column of the front office. | Unlikely to be used for logging, possibly for a future feature or a placeholder. |
| `displayFooter` | Executed in the footer section of every front-office page. | Similar to `displayHeader`, could be used for asset registration or ensuring module context, but not for direct logging. |
| `actionSearch` | Executed after a search query has been processed by PrestaShop’s core search controller. | **This is the most critical hook for this module.** It allows the module to intercept the search term and the number of results *after* PrestaShop has performed its internal search, enabling the logging of the `keyword` and `results` count into the `ps_slog` table. |
| `actionModuleInstall` | Executed when the module is installed. | Used to create the `ps_slog` database table and register necessary hooks. |
| `actionModuleUninstall` | Executed when the module is uninstalled. | Used to clean up (e.g., delete the `ps_slog` table, unregister hooks). |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official developer support for the “Search log” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to providing assistance and ensuring the module functions optimally with your PrestaShop store.
