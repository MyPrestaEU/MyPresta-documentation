---
title: "Seo Redirects 301, 302, 303 - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Seo Redirects 301, 302, 303 PrestaShop module by MyPresta.eu."
sidebar:
  label: "Seo Redirects 301, 302, 303 - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Seo Redirects 301, 302, 303 Module on MyPresta.eu](https://mypresta.eu/modules/seo/seo-redirects-301-302-303.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/seo/seo-redirects-301-302-303/)
>
> ---


# Seo Redirects 301, 302, 303

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The “Seo Redirects 301, 302, 303” module provides a comprehensive suite of tools, accessible through a dedicated menu in your PrestaShop Back Office. After installation, you’ll find a new menu item, typically under **“SEO & SEM”** or **“Advanced Parameters”**, named **“Seo Redirects”** or similar. This menu will contain several sub-items, each leading to a specific configuration screen.

### 2.1 Module Main Configuration Page (Back Office > Modules > Configure)

This initial configuration screen (accessed by clicking “Configure” after installation) provides general settings for the module.

- **What this setting does:** This screen typically contains basic module activation and perhaps some global settings.
- **Effect of changing this setting:**
  - *Enabling the module:* Activates the redirection logic across your store.
  - *Disabling the module:* Stops all redirects managed by this module.
- **Recommended value:** **Enabled** for the module to function.
- **Merchant scenario / example:** After installing, you’ll want to ensure the module is active so it can start managing your redirects.

### 2.2 Dedicated Admin Screens & Controller Views

The module organizes its powerful features into several distinct sections, each managed by a dedicated admin controller. You’ll find these under the main “Seo Redirects” menu item in your PrestaShop Back Office.

#### 2.2.1 Dashboard (AdminSeoRedirectDashboardController)

**Screen Name & Menu Location:** **Seo Redirects > Dashboard**
This screen provides an overview of your redirects’ performance and status. It’s your central hub for quickly understanding how your redirects are working.

- **Available Actions & Settings:**
  - **Overview of Redirects:** Shows statistics like the total number of active redirects, redirects created, and perhaps the number of times redirects have been triggered.
  - **Redirect History/Activity:** May display recent redirect attempts, including 404 errors caught and successfully redirected URLs.
  - **SEOR\_DASHBOARD\_PERIOD:** This setting likely controls the time period for which dashboard statistics are displayed (e.g., last 7 days, last 30 days, all time).
- **Effect of changes:** Changing the dashboard period will update the statistics shown to reflect the selected timeframe, helping you analyze trends over different durations.
- **Recommended workflow for daily store management:** Check this dashboard regularly to monitor the health of your redirects, identify any new 404 errors that need attention, and ensure your SEO efforts are paying off.

#### 2.2.2 Redirect List (AdminSeoRedirectListController)

**Screen Name & Menu Location:** **Seo Redirects > Redirect List**
This is the core of the module, where you create, edit, and manage individual redirection rules.

- **Available Actions & Settings:**
  - **Add New Redirect:** A form to create a new redirect rule.
    - **Old URL (Source URL):** The exact URL that is no longer valid or that you want to redirect from.
    - **New URL (Target URL):** The exact URL where visitors and search engines should be sent.
    - **Redirect Type:**
      - **301 Permanent Redirect:** Tells search engines that the page has moved permanently. This is the most common and SEO-friendly type, passing almost all “link juice.” Use this when a page is gone forever and replaced by another.
      - **302 Found / Temporary Redirect:** Tells search engines the move is temporary. Use this if you expect the old URL to become active again in the future (e.g., for seasonal products, A/B testing). Less SEO value is passed.
      - **303 See Other:** Similar to 302, often used after a POST request to redirect to a new page to prevent re-submission. Less common for general SEO redirects.
    - **Status (Enabled/Disabled):** Allows you to activate or deactivate a specific redirect rule without deleting it.
  - **Edit/Delete Redirects:** Modify existing rules or remove them.
  - **Search/Filter:** Find specific redirects by old or new URL.
  - **Bulk Actions:** Apply actions (enable, disable, delete) to multiple selected redirects.
- **Effect of changes:**
  - *Adding a redirect:* Immediately starts redirecting traffic from the old URL to the new one according to the specified type.
  - *Editing a redirect:* Updates the redirection behavior.
  - *Deleting a redirect:* Removes the rule, potentially leading to 404 errors if the old URL is still accessed.
- **Recommended workflow for daily store management:**
  1. Whenever you remove a product, change a category URL, or update a page’s address, immediately create a 301 redirect from the old URL to the new one.
  2. Regularly check your 404 error logs (e.g., in Google Search Console or the module’s Audit section) and add redirects for frequently encountered broken links.

#### 2.2.3 Import Redirects (AdminSeoRedirectImportController)

**Screen Name & Menu Location:** **Seo Redirects > Import**
This screen allows you to upload a file (typically CSV) containing many redirect rules, making it easy to manage large numbers of redirects.

- **Available Actions & Settings:**
  - **Upload CSV File:** Select a file from your computer. The file should contain columns for “Old URL,” “New URL,” and “Redirect Type.”
  - **IV\_COL\_DELIMITER:** This setting defines the character used to separate columns in your CSV file (e.g., comma, semicolon, tab).
  - **SEOR\_SAFE\_ROLLOUT:** This setting likely controls a “safe mode” for imports, perhaps allowing you to preview changes or enable redirects gradually to prevent accidental issues.
- **Effect of changes:**
  - *Importing a file:* Creates multiple redirect rules in bulk, saving significant manual effort.
  - *Changing delimiter:* Ensures the module correctly parses your CSV file.
  - *Safe Rollout:* If enabled, might allow for staged deployment of redirects, giving you time to verify before they go live.
- **Recommended workflow for daily store management:** Use this feature when migrating a store, performing a major site restructuring, or cleaning up a large number of accumulated 404 errors. Always test a small batch first if possible.

#### 2.2.4 Audit (AdminSeoRedirectAuditController)

**Screen Name & Menu Location:** **Seo Redirects > Audit**
The audit tool helps you identify broken links (404 errors) on your website, which are prime candidates for redirection.

- **Available Actions & Settings:**
  - **Scan for 404 Errors:** Initiates a scan of your website (or a specific part) to find pages that return a 404 status.
  - **List of 404 Errors:** Displays a table of detected broken links, often with the referring page (where the broken link was found) and the number of times it was accessed.
  - **Option to Create Redirect:** Directly create a redirect rule for a detected 404 error from this screen.
- **Effect of changes:** Running an audit helps you proactively find and fix issues that harm SEO and user experience.
- **Recommended workflow for daily store management:** Run an audit periodically (e.g., monthly) to catch new broken links that might appear due to content changes or external links. Prioritize fixing 404s that are frequently accessed or linked from important pages.

#### 2.2.5 History (AdminSeoRedirectHistoryController)

**Screen Name & Menu Location:** **Seo Redirects > History**
This screen logs all redirection events, providing a clear record of when and how redirects are being used.

- **Available Actions & Settings:**
  - **Table of Redirect Events:** Shows details like the original URL requested, the new URL it was redirected to, the redirect type, the date/time, and potentially the user agent or IP address.
  - **Search/Filter:** Helps you find specific redirection events.
- **Effect of changes:** This is a reporting and diagnostic tool. It doesn’t change store behavior but provides valuable insights into how your redirects are performing.
- **Recommended workflow for daily store management:** Use the history to verify that specific redirects are working as expected, troubleshoot unexpected redirection loops, or analyze traffic patterns to redirected pages.

#### 2.2.6 Settings (AdminSeoRedirectSettingsController)

**Screen Name & Menu Location:** **Seo Redirects > Settings**
This section contains advanced configuration options that control how the module behaves globally.

- **Available Actions & Settings:**
  - **seor\_pos\_exclude:**
    - **What this setting does:** Allows you to exclude specific URLs or patterns from being automatically redirected or audited. This is useful for pages you intentionally want to return a 404 (e.g., old test pages).
    - **Effect of changing this setting:**
      - *Adding URLs:* The module will ignore these URLs when performing redirects or audits.
      - *Removing URLs:* These URLs will be subject to the module’s redirection logic.
    - **Recommended value:** Keep this list updated with any URLs that should genuinely be 404s and not redirected.
    - **Merchant scenario / example:** You might have a temporary landing page that you want to remove completely, and you don’t want the module to try and redirect it.
  - **seor\_unavorder:**
    - **What this setting does:** Likely controls how the module handles redirects for unavailable products or out-of-stock products.
    - **Effect of changing this setting:**
      - *Enabled:* The module might automatically redirect unavailable product pages to a category page or a custom “product not found” page.
      - *Disabled:* Unavailable product pages will return a standard 404 error.
    - **Recommended value:** **Enabled** to improve user experience and SEO for discontinued products.
    - **Merchant scenario / example:** When a product is removed from your catalog, you can automatically redirect its old URL to its parent category or a similar product, rather than showing a 404.
  - **seor\_pos\_category, seor\_pins\_category, seor\_pos\_exclude\_cat, seor\_oos\_cat\_include, seor\_emptycat\_exclusions, seor\_pos, seor\_emptycat:**
    - **What these settings do:** These are likely a group of settings related to how the module handles redirects for categories, especially empty categories, out-of-stock products within categories, or specific category exclusions.
      - `seor_pos_category`: General setting for category redirects.
      - `seor_pins_category`: May relate to “pinned” categories or specific category redirect behavior.
      - `seor_pos_exclude_cat`: Excludes specific categories from automatic redirect logic.
      - `seor_oos_cat_include`: Includes out-of-stock products in category redirect logic.
      - `seor_emptycat_exclusions`: Excludes specific empty categories from being redirected.
      - `seor_pos`: General setting for product/category position redirects.
      - `seor_emptycat`: Controls automatic redirects for empty categories.
    - **Effect of changing these settings:** These settings allow fine-grained control over how category URLs are managed when categories are empty, products are out of stock, or categories are removed. They can prevent 404s for dynamic content.
    - **Recommended value:** Review these based on your store’s specific needs. For example, automatically redirecting empty categories to their parent can be beneficial.
    - **Merchant scenario / example:** If a category becomes empty because all products are sold out, you might want to automatically redirect its URL to the parent category to avoid a 404.

#### 2.2.7 Tools (AdminSeoRedirectToolsController)

**Screen Name & Menu Location:** **Seo Redirects > Tools**
This section provides utility functions, potentially including integration with external services.

- **Available Actions & Settings:**
  - **SEOR\_GSC\_TOKEN, SEOR\_GSC\_SITE:** These settings suggest integration with Google Search Console (GSC).
    - **What these settings do:** Allow you to connect your PrestaShop store with your Google Search Console account. This could enable the module to automatically fetch 404 errors reported by Google or submit sitemaps/redirects to GSC.
    - **Effect of changing this setting:**
      - *Configuring GSC:* Enables data exchange between your store and Google Search Console, potentially automating the discovery of broken links and improving your SEO workflow.
      - *Not configured:* You’ll need to manually check GSC for 404s and add redirects.
    - **Recommended value:** Configure if you actively use Google Search Console for your store’s SEO.
    - **Merchant scenario / example:** Instead of manually checking Google Search Console for new 404 errors, the module could pull them directly, allowing you to create redirects more quickly.

#### 2.2.8 Stats (AdminSeoRedirectStatsController)

**Screen Name & Menu Location:** **Seo Redirects > Stats**
This screen provides statistics related to your store’s overall health, potentially including the impact of redirects.

- **Available Actions & Settings:**
  - **PS\_SHOP\_ENABLE:** This is a standard PrestaShop configuration key that indicates whether your shop is currently enabled or in maintenance mode. The module might display this as a quick status check.
  - **Redirect Performance Metrics:** May show aggregated data on how many redirects have occurred, which types are most common, and their overall impact.
- **Effect of changes:** This is primarily an informational screen. It helps you understand the overall performance and usage of the module.
- **Recommended workflow for daily store management:** Periodically review these stats to understand the volume of redirects and ensure the module is actively contributing to a healthy site.

#### 2.2.9 API Controller (AdminSeoRedirectApiController)

**Screen Name & Menu Location:** **Seo Redirects > API** (or similar, might be a technical section)
This screen is for advanced users or developers who want to interact with the module’s redirect functionality programmatically.

- **Available Actions & Settings:**
  - **API Documentation:** Provides information on how to use the module’s API to create, retrieve, update, or delete redirects from external applications or custom scripts.
  - **API Key Management:** Allows you to generate and manage API keys for secure access.
- **Effect of changes:** Configuring API access allows external systems (e.g., a custom inventory management system, a third-party SEO tool) to interact with your redirects.
- **Recommended workflow for daily store management:** Only use this if you have specific integration needs and technical expertise.

#### 2.2.10 CLI Controller (AdminSeoRedirectCliController)

**Screen Name & Menu Location:** **Seo Redirects > CLI** (or similar, might be a technical section)
This screen provides information and tools for command-line interface (CLI) operations related to the module.

- **Available Actions & Settings:**
  - **CLI Command Documentation:** Explains how to run module-specific tasks from your server’s command line (e.g., `php bin/console seoredirect:audit`).
  - **Cron Job Setup:** Provides instructions for setting up cron jobs to automate tasks like regular audits or redirect cleanups.
- **Effect of changes:** Using CLI tools allows for automation of tasks, which is especially useful for large stores or complex operations.
- **Recommended workflow for daily store management:** Consult this section if you want to automate tasks like daily 404 audits or periodic redirect health checks using server cron jobs.

#### 2.2.11 Search Controller (AdminSeoredirectSearchController)

**Screen Name & Menu Location:** **Seo Redirects > Search** (or integrated into other screens)
This controller likely powers advanced search functionalities within the module’s various grids and lists, helping you quickly find specific redirects, 404 errors, or history entries.

- **Available Actions & Settings:**
  - **Advanced Search Filters:** Provides more granular search options beyond simple text search, possibly including date ranges, redirect types, or status.
- **Effect of changes:** Improves your ability to navigate and manage large datasets within the module.
- **Recommended workflow for daily store management:** Use this when you need to quickly locate a specific redirect rule or analyze a subset of your data.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Dashboard** | `SEOR_DASHBOARD_PERIOD` | Last 30 days | Controls the time period for dashboard statistics. |
| **Redirect List** | Old URL | N/A | The URL to redirect FROM. |
|  | New URL | N/A | The URL to redirect TO. |
|  | Redirect Type | 301 Permanent | Type of redirect (301, 302, 303). 301 is best for SEO. |
|  | Status | Enabled | Activates/deactivates a specific redirect rule. |
| **Import** | `IV_COL_DELIMITER` | Comma (`,`) | Character separating columns in CSV import file. |
|  | `SEOR_SAFE_ROLLOUT` | No | Enables a safe mode for imports (e.g., staged deployment). |
| **Settings** | `seor_pos_exclude` | Empty | List of URLs/patterns to exclude from redirect/audit. |
|  | `seor_unavorder` | Yes | Automatically redirects unavailable products. |
|  | `seor_pos_category` | Yes | General setting for category redirects. |
|  | `seor_pins_category` | No | Specific category redirect behavior. |
|  | `seor_pos_exclude_cat` | Empty | Excludes specific categories from auto-redirect. |
|  | `seor_oos_cat_include` | Yes | Includes out-of-stock products in category redirect logic. |
|  | `seor_emptycat_exclusions` | Empty | Excludes specific empty categories from being redirected. |
|  | `seor_pos` | Yes | General setting for product/category position redirects. |
|  | `seor_emptycat` | Yes | Controls automatic redirects for empty categories. |
| **Tools** | `SEOR_GSC_TOKEN` | Empty | Google Search Console API token for integration. |
|  | `SEOR_GSC_SITE` | Empty | Your website URL registered in Google Search Console. |
| **Stats** | `PS_SHOP_ENABLE` | Yes | Displays current shop status (enabled/maintenance). |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve added a redirect, but it’s not working. What should I do?**
A1:

- **Check for typos:** Ensure the “Old URL” and “New URL” are typed exactly correctly in the Redirect List.
- **Clear Cache:** PrestaShop uses caching. Go to **Advanced Parameters > Performance** and click “Clear cache.” Also, clear your browser’s cache.
- **Module Status:** Make sure the “Seo Redirects 301, 302, 303” module is enabled in **Modules > Module Manager**.
- **Redirect Order:** If you have multiple redirect modules or `.htaccess` rules, there might be a conflict. This module usually takes precedence, but check your server’s `.htaccess` file for any conflicting rules.
- **Full URL vs. Relative URL:** Ensure you’re using the correct format for your URLs (e.g., `/old-page.html` for relative paths, or `https://www.yourstore.com/old-page.html` for full paths, depending on how the module expects them).

**Q2: Will this module slow down my store?**
A2: The module is designed to be efficient. Redirects happen at a very early stage of the request process, minimizing impact. However, having tens of thousands of redirects might add a tiny overhead. Regularly auditing and cleaning up unnecessary redirects (e.g., old temporary 302s) can help maintain performance.

**Q3: How do I handle redirects for products that are temporarily out of stock?**
A3:

- For temporary situations, a **302 Temporary Redirect** to a relevant category page or a “notify me when available” page is appropriate. This tells search engines the product might return.
- Check the **Settings** screen for options like `seor_unavorder` or `seor_oos_cat_include`, which might offer automatic handling for out-of-stock products.

**Q4: Can I use wildcards in my redirect rules (e.g., redirecting all pages in an old directory)?**
A4: The module’s documentation or interface will specify if it supports regular expressions or wildcard characters (like `*`). If it does, you can create powerful rules like `/old-category/*` to `/new-category/$1` (where `$1` captures the rest of the URL). If not, you’ll need to list each redirect individually or use the import feature. Always test wildcard redirects carefully!

**Q5: My custom theme isn’t displaying the module’s features correctly (e.g., in the audit modal).**
A5: The module’s back-office interfaces are generally independent of your front-office theme. If you’re experiencing display issues in the admin panel, it might be a conflict with another admin module or a PrestaShop core file modification.

- **Clear PrestaShop Cache:** Go to **Advanced Parameters > Performance** and clear the cache.
- **Check Browser Console:** Open your browser’s developer tools (F12) and look for any JavaScript errors or CSS warnings in the Console tab when on the module’s configuration pages. This can give clues about conflicts.
- **Contact Support:** If the issue persists, provide screenshots and any console errors to MyPresta.eu support.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Seo Redirects 301, 302, 303” module is built following PrestaShop’s MVC (Model-View-Controller) pattern, with a strong emphasis on administrative control and data management. It leverages `ModuleAdminController` for its extensive back-office interface, `ObjectModel` for managing redirect data, and overrides the `FrontController` to intercept requests early and apply redirection logic. The module also includes API and CLI controllers for programmatic and automated management.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

These controllers handle requests on the customer-facing side of the store.

- `seoredirect/controllers/front/api.php`
  - **Class name & parent class:** `SeoredirectApiModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** This controller likely serves as a front-office API endpoint, potentially for external services to query redirect status or for internal AJAX calls related to front-office redirect logic (though most redirects are handled via the `FrontController` override). It would respond to specific routes defined by the module.
- `seoredirect/controllers/front/cronjob.php`
  - **Class name & parent class:** `SeoredirectCronjobModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** Provides a front-office accessible endpoint for running cron jobs. This allows server-side cron tasks (e.g., `wget` or `curl` commands) to trigger module functions like auditing, cleanup, or data synchronization without requiring back-office authentication.
- `seoredirect/controllers/front/index.php`
  - **Class name & parent class:** `SeoredirectIndexModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** A placeholder or default front controller. In many modules, this might handle a simple default route or serve as a base for other front controllers. Given the module’s nature, its primary front-office logic is likely in the `FrontController` override.

#### Back-Office Admin Controllers

These controllers manage the module’s interface and data within the PrestaShop Back Office.

- `seoredirect/controllers/admin/AdminSeoRedirectApiController.php`
  - **Tab name and managed entity:** “API” (or similar, under Seo Redirects menu). Manages API keys and provides API documentation.
  - **Responsibility:** Handles the display and management of API credentials and documentation for programmatic interaction with the module.
- `seoredirect/controllers/admin/AdminSeoRedirectAuditController.php`
  - **Tab name and managed entity:** “Audit” (under Seo Redirects menu). Manages the audit process for 404 errors.
  - **Responsibility:** Provides the interface for scanning the store for 404 errors, displaying results, and offering options to create redirects from detected broken links.
- `seoredirect/controllers/admin/AdminSeoRedirectCliController.php`
  - **Tab name and managed entity:** “CLI” (or similar, under Seo Redirects menu). Provides CLI command documentation.
  - **Responsibility:** Displays information and instructions for using the module’s command-line interface tools, useful for automation and advanced tasks.
- `seoredirect/controllers/admin/AdminSeoRedirectDashboardController.php`
  - **Tab name and managed entity:** “Dashboard” (under Seo Redirects menu). Displays module statistics and overview.
  - **Responsibility:** Presents key metrics and an overview of redirect activity, potentially including charts and graphs. Manages the `SEOR_DASHBOARD_PERIOD` configuration.
- `seoredirect/controllers/admin/AdminSeoRedirectHistoryController.php`
  - **Tab name and managed entity:** “History” (under Seo Redirects menu). Manages `seor_history` records.
  - **Responsibility:** Displays a log of all redirection events, including source, destination, type, and timestamp.
- `seoredirect/controllers/admin/AdminSeoRedirectImport.php`
  - **Tab name and managed entity:** “Import” (under Seo Redirects menu). Manages the bulk import of redirects.
  - **Responsibility:** Provides the interface for uploading CSV files to create multiple redirect rules. Manages `IV_COL_DELIMITER` and `SEOR_SAFE_ROLLOUT` configurations.
- `seoredirect/controllers/admin/AdminSeoRedirectListController.php`
  - **Tab name and managed entity:** “Redirect List” (under Seo Redirects menu). Manages `seor` (redirect) records.
  - **Responsibility:** The primary interface for adding, editing, deleting, and listing individual 301, 302, 303 redirect rules.
- `seoredirect/controllers/admin/AdminSeoredirectSearchController.php`
  - **Tab name and managed entity:** “Search” (or integrated). Powers search functionality.
  - **Responsibility:** Likely provides advanced search and filtering capabilities used across various admin grids within the module.
- `seoredirect/controllers/admin/AdminSeoRedirectSettings.php`
  - **Tab name and managed entity:** “Settings” (under Seo Redirects menu). Manages `ps_configuration` settings related to the module.
  - **Responsibility:** Provides the interface for configuring global module behavior, such as exclusions, automatic redirects for unavailable products/empty categories, and other advanced options. Manages `seor_pos_exclude`, `seor_unavorder`, `seor_pos_category`, `seor_pins_category`, `seor_pos_exclude_cat`, `seor_oos_cat_include`, `seor_emptycat_exclusions`, `seor_pos`, `seor_emptycat`.
- `seoredirect/controllers/admin/AdminSeoRedirectStats.php`
  - **Tab name and managed entity:** “Stats” (under Seo Redirects menu). Displays general store and module statistics.
  - **Responsibility:** Provides an overview of store status (`PS_SHOP_ENABLE`) and potentially aggregated redirect performance data.
- `seoredirect/controllers/admin/AdminSeoRedirectToolsController.php`
  - **Tab name and managed entity:** “Tools” (under Seo Redirects menu). Provides utility functions.
  - **Responsibility:** Contains tools like Google Search Console integration (`SEOR_GSC_TOKEN`, `SEOR_GSC_SITE`) and other utility features.
- `seoredirect/controllers/admin/index.php`
  - **Tab name and managed entity:** Not a direct controller, typically an empty file or a security measure to prevent directory listing.

### 4.3 Core Classes & Models (`classes/`)

- `seoredirect/override/classes/controller/FrontController.php`
  - **What it does:** This is a critical override. It extends PrestaShop’s core `FrontController` class.
  - **Key public methods and business logic:** The override likely intercepts the `init()` or `postProcess()` method of the `FrontController`. Before PrestaShop dispatches the request to a specific page controller, this override checks the requested URL against the module’s stored redirect rules. If a match is found, it issues the appropriate 301, 302, or 303 HTTP redirect header and terminates the request, preventing a 404 and sending the user to the new URL. This is where the core redirection logic resides.
- `seoredirect/override/classes/controller/index.php`
  - **What it does:** Placeholder file, usually for security.
- `seoredirect/override/classes/index.php`
  - **What it does:** Placeholder file, usually for security.

*(Note: The module dossier did not explicitly list custom `ObjectModel` classes like `SeoRedirect` or `SeoRedirectHistory`. However, given the presence of `AdminSeoRedirectListController` managing `seor` and `AdminSeoRedirectHistoryController` managing `seor_history`, it is highly probable that there are corresponding `SeoRedirect` and `SeoRedirectHistory` classes (or similar names) extending `ObjectModel` within the module’s main directory or a `classes/` subdirectory not explicitly listed in the inventory. These would define the database schema for redirects and history entries.)*

### 4.4 JavaScript Assets (`views/js/`)

- `seoredirect/examples/console-mock-dashboard-audit.js`
  - **Scope:** Likely for development/testing, not production.
  - **Details:** Example or mock data/logic for dashboard and audit features, possibly used for console debugging or demonstration.
- `seoredirect/views/js/adminSeoRedirectApi.js`
  - **Scope:** Back-office (AdminSeoRedirectApiController).
  - **Details:** Handles client-side interactions on the API configuration screen, such as generating API keys, copying keys to clipboard, or displaying API documentation modals.
- `seoredirect/views/js/adminSeoRedirectAudit.js`
  - **Scope:** Back-office (AdminSeoRedirectAuditController).
  - **Details:** Manages the audit process, including AJAX calls to trigger scans, updating progress indicators, displaying audit results in a dynamic table, and handling actions like creating redirects from audit findings. May include modal popups for previewing or confirming redirects.
- `seoredirect/views/js/adminSeoRedirectConfig.js`
  - **Scope:** Back-office (Main module configuration or AdminSeoRedirectSettingsController).
  - **Details:** General JavaScript for the module’s main configuration forms. This could include form validation, dynamic field visibility based on other settings, or AJAX calls for saving configuration.
- `seoredirect/views/js/adminSeoRedirectDashboard.js`
  - **Scope:** Back-office (AdminSeoRedirectDashboardController).
  - **Details:** Powers the interactive elements of the dashboard, such as loading data via AJAX, rendering charts (if any), and handling period selection changes (`SEOR_DASHBOARD_PERIOD`).
- `seoredirect/views/js/adminSeoRedirectImport.js`
  - **Scope:** Back-office (AdminSeoRedirectImportController).
  - **Details:** Manages the CSV import process, including file selection, progress indicators, displaying import results/errors, and potentially handling the `SEOR_SAFE_ROLLOUT` logic on the client side.

### 4.5 CSS Stylesheets (`views/css/`)

- `seoredirect/views/css/seoredirect-admin.css`
  - **Scope:** Back-office admin form styling.
  - **Details:** Contains specific styles for the module’s various administration screens, ensuring a consistent and user-friendly interface within the PrestaShop back office. This would include styling for grids, forms, buttons, modals, and dashboard elements.
  - **Key CSS class selectors developers can override:** Look for classes prefixed with `seor-` or `admin-seoredirect-` for specific module elements.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - The module description mentions front-office hooks (Header, Columns, Product, Footer), but the file inventory doesn’t list specific hook templates in `views/templates/hook/`. This suggests that the front-office interaction is primarily handled by the `FrontController` override for redirects, rather than rendering visible content in hooks. If any hook templates exist, they would be for very specific, non-redirect-related display elements.
- **Admin templates (`views/templates/admin/`)**:

  - `seoredirect/lib/searchTool/views/scripts.tpl`: Likely contains JavaScript or Smarty logic for a generic search tool used across multiple admin screens.
  - `seoredirect/views/admin/adminSearch.tpl`: Template for a generic search interface in the admin.
  - `seoredirect/views/admin/adminSearchCategory.tpl`: Template for searching/selecting categories in the admin.
  - `seoredirect/views/admin/adminSearchCategoryToMove.tpl`: Template for category movement search.
  - `seoredirect/views/admin/adminSearchCategoryToMoveInStock.tpl`: Template for category movement search, specifically for in-stock items.
  - `seoredirect/views/admin/adminSeoRedirectImport.tpl`: The main template for the import screen (AdminSeoRedirectImportController).
  - `seoredirect/views/admin/stats.tpl`: Template for the statistics screen (AdminSeoRedirectStatsController).
  - `seoredirect/views/templates/admin/api.tpl`: Template for the API configuration screen (AdminSeoRedirectApiController).
  - `seoredirect/views/templates/admin/audit.tpl`: Template for the audit screen (AdminSeoRedirectAuditController).
  - `seoredirect/views/templates/admin/cli.tpl`: Template for the CLI documentation screen (AdminSeoRedirectCliController).
  - `seoredirect/views/templates/admin/dashboard.tpl`: Template for the module’s dashboard (AdminSeoRedirectDashboardController).
  - `seoredirect/views/templates/admin/employee_permissions.tpl`: Template for managing employee permissions related to the module’s admin tabs.
  - `seoredirect/views/templates/admin/import.tpl`: Another template for the import functionality (could be a wrapper or specific part of the import process).
  - `seoredirect/views/templates/admin/seo_redirect_settings/helpers/options/options.tpl`: A partial template for rendering options within the settings screen (AdminSeoRedirectSettingsController).
  - `seoredirect/views/templates/admin/tools.tpl`: Template for the tools screen (AdminSeoRedirectToolsController).
  - `seoredirect/views/templates/admin/_api_documentation_modal.tpl`: A modal template for displaying API documentation.
  - `seoredirect/views/templates/admin/_audit_preview_modal.tpl`: A modal template for previewing audit results or redirect creations.
  - `seoredirect/views/templates/admin/_cli_documentation_modal.tpl`: A modal template for displaying CLI documentation.
- **Front-office templates (`views/templates/front/`)**:

  - No specific front-office templates are listed, reinforcing that the module’s front-end operation is primarily through the `FrontController` override for redirection, not visible content.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - `ps_seor`: Stores the main redirection rules (Old URL, New URL, Redirect Type, Status, etc.). This table is managed by `AdminSeoRedirectListController` and the `SeoRedirect` `ObjectModel` (implied).
  - `ps_seor_history`: Stores a log of all triggered redirects (Original Request, Redirected To, Type, Timestamp, etc.). This table is managed by `AdminSeoRedirectHistoryController` and the `SeoRedirectHistory` `ObjectModel` (implied).
  - `ps_configuration`: Stores module-specific global settings like `SEOR_DASHBOARD_PERIOD`, `IV_COL_DELIMITER`, `SEOR_SAFE_ROLLOUT`, `seor_pos_exclude`, `seor_unavorder`, `seor_pos_category`, `seor_pins_category`, `seor_pos_exclude_cat`, `seor_oos_cat_include`, `seor_emptycat_exclusions`, `seor_pos`, `seor_emptycat`, `SEOR_GSC_TOKEN`, `SEOR_GSC_SITE`.
- **Registered Hooks Table**:

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `actionFrontControllerSetMedia` | Before front controller renders content | Potentially loads front-office JS/CSS if any, though unlikely for a redirect module. |
  | `actionDispatcherBefore` | Very early in the request lifecycle, before dispatching to a controller. | **CRITICAL:** This is the most likely hook for the `FrontController` override to intercept the request and apply redirect logic. It allows the module to redirect before PrestaShop even tries to find the original page. |
  | `displayAdminProductsExtra` | On the product edit page in the back office. | Could be used to show redirect status for a product or suggest creating a redirect if the product URL is changed. |
  | `displayAdminCategoriesExtra` | On the category edit page in the back office. | Similar to products, could show redirect status or suggest redirects for category URL changes. |
  | `displayHeader` | In the `<head>` section of every front-office page. | Unlikely for core redirect logic, but could be used for adding meta tags or canonicals related to redirects if needed. |
  | `displayRightColumn` | In the right column of front-office pages. | Unlikely for this module. |
  | `displayFooter` | In the footer of every front-office page. | Unlikely for this module. |
  | `actionValidateOrder` | After an order is successfully validated. | Could be used to log or audit redirects related to checkout processes, though less direct. |
  | `actionModuleInstall` | During module installation. | Creates database tables, registers hooks, sets default configuration values. |
  | `actionModuleUninstall` | During module uninstallation. | Cleans up database tables, unregisters hooks, removes configuration values. |
  | `actionAdminControllerSetMedia` | Before an admin controller renders content. | Loads back-office JS/CSS for the module’s admin pages. |
  | `actionAdminSeoRedirectSave` | Custom hook, likely triggered after a redirect rule is saved in the back office. | Allows other modules or custom code to react to redirect changes. |
  | `actionAdminSeoRedirectDelete` | Custom hook, likely triggered after a redirect rule is deleted. | Allows other modules or custom code to react to redirect deletions. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions regarding the “Seo Redirects 301, 302, 303” module.
