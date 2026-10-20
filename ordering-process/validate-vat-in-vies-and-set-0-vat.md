---
title: "Validate VAT in VIES and set 0% VAT - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Validate VAT in VIES and set 0% VAT PrestaShop module by MyPresta.eu."
sidebar:
  label: "Validate VAT in VIES and set 0% VAT"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Validate VAT in VIES and set 0% VAT Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/validate-vat-in-vies-and-set-0-vat.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/validate-vat-in-vies-and-set-0-vat/)
>
> ---


# Validate VAT in VIES and set 0% VAT

## 1. Requirements & Compatibility

To ensure the smooth operation of the "Validate VAT in VIES and set 0% VAT" module, please review the following requirements:

*   **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
*   **PHP Compatibility**: PHP 7.1 - 8.5
*   **Hosting Requirements**: Your hosting environment must support standard PHP extensions such as `cURL` (for communicating with the VIES system), `JSON`, and `OpenSSL`. These are typically enabled by default on most modern hosting providers.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration area for the module, where you control its behavior and appearance. Navigate to **Modules > Module Manager**, search for "Validate VAT in VIES and set 0% VAT", and click "Configure".

#### **General Settings**

*   **Your country:**
    *   **What this setting does:** Defines the country where your business is registered. This is crucial for determining if a customer's VAT number qualifies for 0% VAT (i.e., if they are from a *different* EU country).
    *   **Effect of changing this setting:**
        *   *When set to your country:* The module will correctly identify intra-community sales.
        *   *When set incorrectly:* VAT validation logic might fail or apply 0% VAT incorrectly.
    *   **Recommended value:** Your store's official country of registration (e.g., "Poland").
    *   **Merchant scenario / example:** If your store is based in Germany, you would select "Germany". A customer from France with a valid French VAT number would then be eligible for 0% VAT.
*   **Eligible countries:**
    *   **What this setting does:** Allows you to select which EU countries are eligible for the 0% VAT rule. You can choose specific countries or select all EU countries.
    *   **Effect of changing this setting:**
        *   *When specific countries are selected:* Only customers from those countries (with valid VAT) will get 0% VAT.
        *   *When all EU countries are selected:* All EU countries (excluding your own) will be eligible.
    *   **Recommended value:** Select all EU countries unless you have specific business reasons to exclude some.
    *   **Merchant scenario / example:** If you only want to offer 0% VAT to businesses in France, Germany, and Spain, you would select only those countries.
*   **Select Tax rule:**
    *   **What this setting does:** Specifies which PrestaShop tax rule should be applied when a customer's VAT is validated as 0%. You should have a tax rule set up in PrestaShop for 0% VAT.
    *   **Effect of changing this setting:**
        *   *When a 0% tax rule is selected:* The module will apply this rule to eligible orders.
        *   *When an incorrect tax rule is selected:* The wrong tax rate might be applied, or the module might not function as expected.
    *   **Recommended value:** A tax rule you have created in PrestaShop with a 0% tax rate.
    *   **Merchant scenario / example:** You would create a tax rule named "EU B2B 0% VAT" with a 0% rate and select it here.
*   **Disable module for selected languages:**
    *   **What this setting does:** Allows you to disable the VAT validation functionality for specific languages in your store. This can be useful if you operate in non-EU countries with different tax regulations, but still use the same PrestaShop instance.
    *   **Effect of changing this setting:**
        *   *When languages are selected:* The VAT validation form and logic will not appear or apply for customers browsing in those languages.
        *   *When no languages are selected:* The module will be active for all languages.
    *   **Recommended value:** Leave empty unless you have specific language-based tax requirements.
    *   **Merchant scenario / example:** If you have an English version of your store targeting both EU and US customers, but only want VAT validation for EU customers, you might not disable it. However, if you have a separate store view for a non-EU country (e.g., "Japan"), you might disable it for the Japanese language.

#### **Display Settings (Front-Office Visibility)**

These settings control where the VAT input form and status messages appear to your customers.

*   **Show VAT change form in heading bar:**
    *   **What this setting does:** Displays a small form or notification in your store's header area, prompting customers to enter their VAT number.
    *   **Effect of changing this setting:**
        *   *When enabled:* A bar appears at the top of your site.
        *   *When disabled:* No VAT form/notification in the header.
    *   **Recommended value:** "Off" unless you want high visibility for B2B customers.
    *   **Merchant scenario / example:** You might enable this if your store is primarily B2B and you want to immediately inform business customers about 0% VAT.
*   **Show VAT change form in displayCustomhtml1 (custom theme sp_topdeals):**
    *   **What this setting does:** This is a specific hook often used by custom themes (like 'sp_topdeals') for displaying custom content. Enabling this will place the VAT form in that specific area.
    *   **Effect of changing this setting:**
        *   *When enabled:* The VAT form appears in the `displayCustomhtml1` hook area.
        *   *When disabled:* The form will not appear in this specific custom area.
    *   **Recommended value:** "Off" unless your theme uses this hook and you want the form there.
    *   **Merchant scenario / example:** If your theme has a prominent banner area at the top and you want the VAT form there, you would enable this.
*   **Show VAT status bar for logged-in customers:**
    *   **What this setting does:** Displays a bar or message to logged-in customers, indicating their current VAT status (e.g., "Your VAT is valid, 0% applied").
    *   **Effect of changing this setting:**
        *   *When enabled:* Logged-in customers see their VAT status.
        *   *When disabled:* No specific VAT status bar for logged-in users.
    *   **Recommended value:** "On" to provide clarity and reassurance to your B2B customers.
    *   **Merchant scenario / example:** A returning business customer logs in and immediately sees "Your VAT is valid, 0% VAT applied to your cart," which improves their shopping experience.
*   **Show VAT bar on checkout personal information step:**
    *   **What this setting does:** Displays the VAT input field and validation status on the first step of the checkout process (where customers enter their name, address, etc.). This is the most common and recommended location.
    *   **Effect of changing this setting:**
        *   *When enabled:* The VAT field is visible and interactive on the personal information step.
        *   *When disabled:* The VAT field will not appear on this step, potentially making it harder for customers to apply 0% VAT.
    *   **Recommended value:** "On" (Highly Recommended).
    *   **Merchant scenario / example:** A customer reaches checkout, enters their company address, and then enters their VAT number in the dedicated field. The module validates it, and the price updates.
*   **Show VAT bar on checkout summary:**
    *   **What this setting does:** Displays the VAT status (e.g., "VAT: 0%") on the checkout summary page, before the final payment.
    *   **Effect of changing this setting:**
        *   *When enabled:* Customers see their VAT status on the summary.
        *   *When disabled:* No specific VAT status on the summary.
    *   **Recommended value:** "On" for transparency.
    *   **Merchant scenario / example:** A customer reviews their order before payment and sees a clear confirmation that 0% VAT has been applied.
*   **Show VAT bar on payment step:**
    *   **What this setting does:** Displays the VAT status on the final payment step of the checkout.
    *   **Effect of changing this setting:**
        *   *When enabled:* Customers see their VAT status on the payment step.
        *   *When disabled:* No specific VAT status on the payment step.
    *   **Recommended value:** "On" for final confirmation.
    *   **Merchant scenario / example:** Just before clicking "Pay Now," the customer sees "Total: €100.00 (VAT 0%)", confirming the correct tax application.
*   **Show VAT change bar on product page:**
    *   **What this setting does:** Displays a VAT input form or status message directly on individual product pages.
    *   **Effect of changing this setting:**
        *   *When enabled:* A VAT form/message appears on product pages.
        *   *When disabled:* No VAT form/message on product pages.
    *   **Recommended value:** "Off" to avoid clutter, unless you have a strong B2B focus and want to show VAT-exclusive prices early.
    *   **Merchant scenario / example:** A business customer browsing a product page can enter their VAT number to immediately see the price without VAT, helping them with purchasing decisions.
*   **Show VAT change form in displayProductAdditionalInfo:**
    *   **What this setting does:** This is a standard PrestaShop hook on the product page, typically used for additional information. Enabling this will place the VAT form in that area.
    *   **Effect of changing this setting:**
        *   *When enabled:* The VAT form appears in the `displayProductAdditionalInfo` hook area.
        *   *When disabled:* The form will not appear in this specific area.
    *   **Recommended value:** "Off" unless you specifically want it there.
    *   **Merchant scenario / example:** Similar to the "Show VAT change bar on product page" setting, but targets a specific hook.
*   **Show VAT change form in displayBanner:**
    *   **What this setting does:** Displays the VAT form or status in the `displayBanner` hook, which is often used for top banners or promotional messages.
    *   **Effect of changing this setting:**
        *   *When enabled:* The VAT form/status appears in the banner area.
        *   *When disabled:* No VAT form/status in the banner area.
    *   **Recommended value:** "Off" to avoid clutter, unless you have a specific banner design for this.
    *   **Merchant scenario / example:** You could use this to display a "Are you a business? Enter your VAT for 0% tax!" message in a prominent banner.
*   **Show VAT change form in displayCustomhtml1 (custom theme sp_topdeals):** (Duplicate, already covered above)
*   **Show VAT status bar for logged-in customers:** (Duplicate, already covered above)
*   **Show VAT bar on checkout personal information step:** (Duplicate, already covered above)
*   **Show VAT bar on checkout summary:** (Duplicate, already covered above)
*   **Show VAT bar on payment step:** (Duplicate, already covered above)
*   **Reverse charge note on invoice:**
    *   **What this setting does:** When 0% VAT is applied due to a valid VIES check, this setting ensures that a "Reverse Charge" note is automatically added to the customer's invoice. This is a legal requirement for intra-community B2B sales.
    *   **Effect of changing this setting:**
        *   *When enabled:* Invoices for 0% VAT orders will include the reverse charge note.
        *   *When disabled:* Invoices will not include the note, potentially leading to non-compliance.
    *   **Recommended value:** "On" (Highly Recommended for legal compliance).
    *   **Merchant scenario / example:** A German business customer buys from your Polish store with a valid VAT number. The invoice automatically states "Reverse Charge - VAT not applicable under Article 196 of Council Directive 2006/112/EC".

#### **Advanced Settings**

*   **Revalidate customer VAT number on every order:**
    *   **What this setting does:** If enabled, the module will re-check the customer's VAT number with VIES every time they place an order, even if it was previously validated.
    *   **Effect of changing this setting:**
        *   *When enabled:* Ensures the VAT number is always current and valid, but adds a slight delay to checkout.
        *   *When disabled:* Relies on the initial validation, which is faster but might miss changes in VAT status.
    *   **Recommended value:** "On" for maximum compliance and accuracy.
    *   **Merchant scenario / example:** A business customer's VAT number might become invalid over time. Revalidation ensures you don't mistakenly apply 0% VAT to an invalid number.
*   **Prevent flood of VIES requests (block for X minutes):**
    *   **What this setting does:** If a customer repeatedly enters invalid VAT numbers, this setting temporarily blocks further validation attempts for a specified period to prevent abuse or overloading the VIES system.
    *   **Effect of changing this setting:**
        *   *When enabled:* After multiple failed attempts, the customer is temporarily blocked from trying again.
        *   *When disabled:* No flood protection, allowing unlimited attempts.
    *   **Recommended value:** "On" with a reasonable block time (e.g., 5-10 minutes).
    *   **Merchant scenario / example:** A bot or malicious user tries to guess VAT numbers. This setting prevents them from continuously hitting the VIES API.
*   **Cache VIES validation results for X hours:**
    *   **What this setting does:** Stores the results of successful VIES validations for a specified number of hours. This reduces the number of direct calls to the VIES system, speeding up the process and reducing external API usage.
    *   **Effect of changing this setting:**
        *   *When enabled:* Faster validation for repeat customers or within the cache period.
        *   *When disabled:* Every validation is a live VIES call, which can be slower.
    *   **Recommended value:** "On" with a cache time of 24-72 hours (e.g., 48 hours).
    *   **Merchant scenario / example:** A customer validates their VAT number. If they return to your site within 48 hours, the module uses the cached result instead of making a new VIES request.
*   **Recheck cart VAT status every X seconds:**
    *   **What this setting does:** Defines how often the module re-checks the cart's VAT status in the background, especially useful if prices are dynamic or if the customer changes their address/VAT number during checkout.
    *   **Effect of changing this setting:**
        *   *When set to a low value:* More frequent updates, potentially smoother experience but more server load.
        *   *When set to a high value:* Less frequent updates, might require manual page refresh for VAT changes to reflect.
    *   **Recommended value:** 5-10 seconds.
    *   **Merchant scenario / example:** A customer enters their VAT number, and within 5 seconds, the cart total updates to reflect 0% VAT without a page reload.
*   **Enable automatic VAT number revalidation (Cron Job):**
    *   **What this setting does:** Activates a background task (cron job) that periodically revalidates all stored customer VAT numbers with VIES. This ensures that even old VAT numbers remain valid.
    *   **Effect of changing this setting:**
        *   *When enabled:* VAT numbers are periodically checked for validity, ensuring compliance.
        *   *When disabled:* VAT numbers are only checked at the time of entry or order, potentially leading to outdated information.
    *   **Recommended value:** "On" (Highly Recommended for long-term compliance).
    *   **Merchant scenario / example:** A customer made an order 6 months ago with a valid VAT number. The cron job re-checks it and finds it's now invalid, allowing you to flag it for future orders.
*   **Cron Job revalidation interval (days):**
    *   **What this setting does:** Sets how often the cron job runs to revalidate VAT numbers.
    *   **Effect of changing this setting:**
        *   *When set to a low number:* More frequent revalidations, higher accuracy, but more VIES requests.
        *   *When set to a high number:* Less frequent revalidations, lower accuracy, fewer VIES requests.
    *   **Recommended value:** 30-90 days (e.g., 60 days).
    *   **Merchant scenario / example:** Setting it to 30 days means all VAT numbers are re-checked once a month.
*   **VIES API Key (Optional):**
    *   **What this setting does:** Allows you to use alternative VAT validation APIs (like Apilayer, AbstractAPI, VATStack) instead of the default VIES system. These can sometimes offer more robust features or fallback options.
    *   **Effect of changing this setting:**
        *   *When a key is entered:* The module will attempt to use the specified third-party API for validation.
        *   *When empty:* The module defaults to the official VIES system.
    *   **Recommended value:** Leave empty unless you experience issues with VIES or require specific features from a third-party API. If you use one, enter the key provided by that service.
    *   **Merchant scenario / example:** If the VIES system is frequently down or slow, you might subscribe to Apilayer's VAT validation service and enter your API key here as a reliable alternative.

#### **API Keys (Optional - for alternative VAT validation services)**

*   **Apilayer API Key:**
    *   **What this setting does:** Enter your API key if you subscribe to Apilayer's VAT validation service.
    *   **Effect of changing this setting:** Enables validation via Apilayer.
    *   **Recommended value:** Leave empty unless you have an Apilayer account.
*   **AbstractAPI Key:**
    *   **What this setting does:** Enter your API key if you subscribe to AbstractAPI's VAT validation service.
    *   **Effect of changing this setting:** Enables validation via AbstractAPI.
    *   **Recommended value:** Leave empty unless you have an AbstractAPI account.
*   **VATStack API Key:**
    *   **What this setting does:** Enter your API key if you subscribe to VATStack's VAT validation service.
    *   **Effect of changing this setting:** Enables validation via VATStack.
    *   **Recommended value:** Leave empty unless you have a VATStack account.

#### **Configuration Quick Reference Table**

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Main Config   | Your country     | Your Store's Country  | Defines your business country for intra-community sales. |
| Main Config   | Eligible countries | All EU Countries      | Selects EU countries where 0% VAT applies. |
| Main Config   | Select Tax rule  | Your 0% Tax Rule      | Specifies the PrestaShop tax rule for 0% VAT. |
| Main Config   | Disable module for selected languages | Empty | Disables module for specific languages. |
| Main Config   | Show VAT change form in heading bar | Off | Displays VAT form in header. |
| Main Config   | Show VAT change form in displayCustomhtml1 | Off | Displays VAT form in custom theme hook. |
| Main Config   | Show VAT status bar for logged-in customers | On | Shows VAT status to logged-in users. |
| Main Config   | Show VAT bar on checkout personal information step | On (Highly Recommended) | Displays VAT field on first checkout step. |
| Main Config   | Show VAT bar on checkout summary | On | Displays VAT status on checkout summary. |
| Main Config   | Show VAT bar on payment step | On | Displays VAT status on payment step. |
| Main Config   | Show VAT change bar on product page | Off | Displays VAT form on product pages. |
| Main Config   | Show VAT change form in displayProductAdditionalInfo | Off | Displays VAT form in product additional info hook. |
| Main Config   | Show VAT change form in displayBanner | Off | Displays VAT form in banner hook. |
| Main Config   | Reverse charge note on invoice | On (Highly Recommended) | Adds legal "Reverse Charge" note to invoices. |
| Main Config   | Revalidate customer VAT number on every order | On | Re-checks VAT for each new order. |
| Main Config   | Prevent flood of VIES requests (block for X minutes) | On (5-10 minutes) | Blocks repeated invalid VAT attempts. |
| Main Config   | Cache VIES validation results for X hours | On (24-72 hours) | Caches VIES results to speed up validation. |
| Main Config   | Recheck cart VAT status every X seconds | 5-10 seconds | How often cart VAT status is updated. |
| Main Config   | Enable automatic VAT number revalidation (Cron Job) | On (Highly Recommended) | Activates background revalidation of all VAT numbers. |
| Main Config   | Cron Job revalidation interval (days) | 30-90 days (e.g., 60) | Frequency of cron job revalidation. |
| Main Config   | Apilayer API Key | Empty | Key for Apilayer VAT validation service. |
| Main Config   | AbstractAPI Key | Empty | Key for AbstractAPI VAT validation service. |
| Main Config   | VATStack API Key | Empty | Key for VATStack VAT validation service. |

### 2.2 Dedicated Admin Screens & Controller Views

#### **VAT Validation Audit (Back Office > Customers > VAT Validation Audit)**

This dedicated section allows you to review and manage all VAT validation attempts made through your store.

*   **Screen Name & Menu Location:** **Customers > VAT Validation Audit** (This new menu item is added by the module).
*   **Available Actions & Settings:**
    *   **Grid / Management View:** This screen presents a table (grid) of all VAT validation attempts. For each entry, you will typically see:
        *   **Customer Name:** The name of the customer associated with the validation.
        *   **VAT Number:** The VAT number that was entered.
        *   **Country:** The country code associated with the VAT number.
        *   **Validation Status:** Whether the VAT number was "Valid," "Invalid," or "Error" (e.g., VIES system unavailable).
        *   **Validation Date:** When the validation attempt occurred.
        *   **Order ID:** If the validation led to an order, the associated order ID.
        *   **Source:** Where the validation took place (e.g., "Checkout," "Customer Account").
        *   **Details/Reason:** More information about the validation result, especially for invalid entries.
    *   **Filtering and Sorting:** You can usually filter the list by customer, VAT number, status, or date range to find specific entries. Sorting allows you to organize the data.
    *   **Export:** The module may offer an option to export this audit log, which is useful for accounting and tax audits.
*   **Effect of changes:** This screen is primarily for auditing and reporting. You cannot directly change a customer's VAT status here, but you can review the history of validations. This data is crucial for proving compliance during tax inspections.
*   **Recommended workflow for daily store management:**
    1.  Periodically review this audit log, especially if you notice discrepancies in VAT application or receive customer inquiries about VAT.
    2.  Look for "Invalid" or "Error" statuses to identify potential issues with customer input or VIES system availability.
    3.  Use the export feature to provide data to your accountant or tax authorities if requested.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| :------------ | :--------------- | :-------------------- | :--------------- |
| VAT Validation Audit | Grid View | N/A | Displays a historical log of all VAT validation attempts. |
| VAT Validation Audit | Filters & Sorting | N/A | Helps locate specific validation entries. |
| VAT Validation Audit | Export Data | N/A | Allows exporting the audit log for record-keeping and tax purposes. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My customers are entering valid VAT numbers, but 0% VAT isn't being applied.**
*   **A:**
    1.  **Check "Your country" setting:** Ensure it's correctly set to your store's country in the module configuration.
    2.  **Verify "Eligible countries":** Make sure the customer's country is selected in the list of eligible countries.
    3.  **Confirm "Select Tax rule":** Ensure you have a 0% tax rule created in PrestaShop (**International > Taxes > Tax Rules**) and that it's correctly selected in the module settings.
    4.  **Clear PrestaShop Cache:** Go to **Advanced Parameters > Performance** and click "Clear cache". Sometimes old cache can prevent new settings from taking effect.
    5.  **Check VIES availability:** The VIES system can sometimes be temporarily unavailable. You can check its status on the official European Commission website.

**Q2: The VAT validation form isn't appearing on my checkout page.**
*   **A:**
    1.  **Check Display Settings:** In the module configuration, ensure "Show VAT bar on checkout personal information step" (and other relevant display options) is set to "On".
    2.  **Theme Compatibility:** If you're using a highly customized theme, it might override standard PrestaShop hooks. Check if your theme has specific areas for `displayProductAdditionalInfo`, `displayCustomhtml1`, or other hooks where you've tried to place the form. You might need to consult your theme developer.
    3.  **Module Conflicts:** Temporarily disable other checkout-related modules to see if there's a conflict.

**Q3: I'm seeing "Error" or "VIES Unavailable" messages during validation.**
*   **A:**
    1.  **VIES System Status:** The VIES system can experience downtime. Check the official VIES website for current status.
    2.  **cURL Extension:** Ensure your hosting provider has the `cURL` PHP extension enabled. This is essential for the module to communicate with external APIs like VIES. Contact your host if unsure.
    3.  **Firewall/Security:** Your server's firewall or security settings might be blocking outgoing connections to the VIES server. Again, contact your hosting provider.
    4.  **API Keys:** If you're trying to use a third-party API (Apilayer, AbstractAPI, VATStack), ensure the API key is correctly entered and active with that service.

**Q4: How do I make sure the cron job for revalidation is running?**
*   **A:**
    1.  **Enable Cron Job:** In the module configuration, ensure "Enable automatic VAT number revalidation (Cron Job)" is "On".
    2.  **PrestaShop Cron Module:** You need a separate PrestaShop cron job module (e.g., "Cron tasks manager" by PrestaShop) installed and configured to periodically trigger the module's cron task.
    3.  **Hosting Cron:** Alternatively, you can set up a server-level cron job (via cPanel, Plesk, or SSH) to call the module's cron URL. The module configuration usually provides the exact URL to use.
    4.  **Check Audit Log:** After the cron job should have run, check the "VAT Validation Audit" screen in the Back Office. You should see new validation entries with a "Cron" source.

**Q5: Why are some EU countries not showing up in the "Eligible countries" list?**
*   **A:** The module relies on PrestaShop's list of countries. Ensure that all desired EU countries are enabled in your PrestaShop store (**International > Locations > Countries**) and that they are marked as "Is an EU country" and "Contains states" (if applicable).

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the "Validate VAT in VIES and set 0% VAT" module, designed for developers and webmasters.

### 4.1 Architecture Overview

The module follows a standard PrestaShop MVC (Model-View-Controller) pattern, heavily leveraging hooks for integration into the front and back office. It introduces several custom classes for business logic, API interaction, and data management. Key components include:

*   **Main Module Class (`eurovat.php`):** Handles installation, uninstallation, hook registration, and the primary configuration form (`getContent()`).
*   **Front Controllers:** Manage AJAX requests for VAT validation and form submissions.
*   **Admin Controllers:** Provide dedicated interfaces for VAT validation auditing.
*   **Core Classes:** Encapsulate business logic for VIES interaction, tax management, analytics, and data persistence (often extending `ObjectModel` or using a repository pattern).
*   **Templates:** Smarty templates for rendering front-office forms, back-office configuration, and audit views.
*   **Hooks:** Extensive use of hooks to inject functionality at various points in the PrestaShop lifecycle (e.g., product page, checkout, order processing, admin customer view).

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

*   `controllers/front/cron.php`
    *   **Class Name:** `EurovatCronModuleFrontController` (extends `ModuleFrontController`)
    *   **Responsibility:** Handles the execution of the module's cron job. This controller is typically called by an external cron service (e.g., server cron or PrestaShop's `Cron tasks manager` module) to trigger background tasks like revalidating VAT numbers. It processes the `ActionCronJob` hook.
*   `controllers/front/form.php`
    *   **Class Name:** `EurovatFormModuleFrontController` (extends `ModuleFrontController`)
    *   **Responsibility:** Likely handles the display and submission of the VAT input form in various front-office contexts (e.g., product page, custom HTML blocks). It might render `views/templates/front/form.tpl`.
*   `controllers/front/index.php`
    *   **Class Name:** `EurovatIndexModuleFrontController` (extends `ModuleFrontController`)
    *   **Responsibility:** A generic front controller, potentially used for fallback or simple display logic. Often, `index.php` in a controller directory serves as a placeholder or a base for other controllers.
*   `controllers/front/validate.php`
    *   **Class Name:** `EurovatValidateModuleFrontController` (extends `ModuleFrontController`)
    *   **Responsibility:** The core AJAX endpoint for real-time VAT number validation. It receives VAT number and country data, interacts with the VIES client, and returns a JSON response indicating validity and potentially updating the cart's tax status.

#### Back-Office Admin Controllers

*   `controllers/admin/AdminEurovatVatValidationAuditController.php`
    *   **Class Name:** `AdminEurovatVatValidationAuditController` (extends `ModuleAdminController`)
    *   **Tab Name:** "VAT Validation Audit" (under Customers menu)
    *   **Managed Entity:** `EurovatValidation` (custom table `ps_eurovat_validation`)
    *   **Responsibility:** Provides the administrative interface for viewing, filtering, and managing the audit log of all VAT validation attempts. It uses PrestaShop's `HelperList` or `Grid` components to display the data from the `ps_eurovat_validation` table.
*   `controllers/admin/index.php`
    *   **Class Name:** `EurovatIndexAdminController` (extends `ModuleAdminController`)
    *   **Responsibility:** Similar to the front-office `index.php`, this is likely a placeholder or a base controller. It might redirect to the main configuration or the audit controller.

### 4.3 Core Classes & Models (`classes/`)

*   `classes/EurovatAlertService.php`
    *   **Responsibility:** Manages and displays alerts or notifications within the module, possibly related to VIES status, API key issues, or configuration problems.
*   `classes/EurovatAlertsHelper.php`
    *   **Responsibility:** A helper class for `EurovatAlertService`, providing utility functions for alert management.
*   `classes/EurovatAnalyticsService.php`
    *   **Responsibility:** Collects and processes data related to VAT validation, such as success rates, error types, and API usage, potentially for display in a dashboard widget.
*   `classes/EurovatApiUsageHelper.php`
    *   **Responsibility:** Tracks and manages usage of external VAT validation APIs (VIES, Apilayer, etc.), potentially implementing rate limiting or monitoring.
*   `classes/EurovatAuditHelper.php`
    *   **Responsibility:** Assists `AdminEurovatVatValidationAuditController` in managing and querying the `ps_eurovat_validation` table.
*   `classes/EurovatConfiguration.php`
    *   **Responsibility:** A static or singleton class to centralize access to module configuration values (`Configuration::get('EUROVAT_...')`). Provides a cleaner way to retrieve settings.
*   `classes/EurovatCronHelper.php`
    *   **Responsibility:** Contains the logic executed by the cron job, such as iterating through customer VAT numbers and initiating revalidation.
*   `classes/EurovatErrorClassifier.php`
    *   **Responsibility:** Categorizes and provides user-friendly messages for different types of VAT validation errors (e.g., invalid format, VIES unavailable, country mismatch).
*   `classes/EurovatExportService.php`
    *   **Responsibility:** Handles the export of VAT validation audit data, likely into CSV or Excel format.
*   `classes/EurovatOrderProofHelper.php`
    *   **Responsibility:** Gathers and prepares data related to VAT validation for a specific order, used for generating proof of 0% VAT application.
*   `classes/EurovatOrderTaxNormalizer.php`
    *   **Responsibility:** Adjusts order tax details when 0% VAT is applied, ensuring consistency across cart, order, and invoice.
*   `classes/EurovatProofPackService.php`
    *   **Responsibility:** Potentially creates a "proof pack" (e.g., a PDF document) containing all necessary evidence for a 0% VAT transaction.
*   `classes/EurovatTaxManager.php`
    *   **Responsibility:** The central class for applying and managing tax changes based on VAT validation results, interacting with PrestaShop's tax system.
*   `classes/EurovatTaxService.php`
    *   **Responsibility:** Provides utility methods related to tax calculations and application within the module.
*   `classes/EurovatValidationRepository.php`
    *   **What database table it interacts with:** `ps_eurovat_validation`
    *   **Whether it extends `ObjectModel`:** Likely not directly, but manages `EurovatValidation` objects or raw database queries.
    *   **Key public methods and business logic encapsulated:** CRUD operations for VAT validation records, querying validation history, storing validation results.
*   `classes/EurovatViesClient.php`
    *   **Responsibility:** The primary interface for communicating with the VIES system (or alternative APIs like Apilayer, AbstractAPI, VATStack). Handles API requests, responses, and error handling.
*   `classes/index.php`
    *   **Responsibility:** A security placeholder to prevent directory listing.

### 4.4 JavaScript Assets (`views/js/`)

*   `eurovat/views/js/adminEurovatAlerts.js`
    *   **Scope:** Back-office
    *   **Description:** Handles display and interaction with alerts in the admin panel, potentially dynamic updates or dismissible messages.
*   `eurovat/views/js/adminEurovatCountries.js`
    *   **Scope:** Back-office
    *   **Description:** Manages the country selection interface in the module configuration, possibly with multi-select functionality or dynamic filtering.
*   `eurovat/views/js/adminEurovatCron.js`
    *   **Scope:** Back-office
    *   **Description:** Provides UI logic for the cron job settings, potentially displaying last run times, next scheduled run, or manual trigger options.
*   `eurovat/views/js/adminEurovatDashboard.js`
    *   **Scope:** Back-office
    *   **Description:** Powers the dashboard widget (if any) displaying analytics or key metrics related to VAT validation. Uses AJAX to fetch data and potentially charting libraries.
*   `eurovat/views/js/adminEurovatTooltips.js`
    *   **Scope:** Back-office
    *   **Description:** Initializes and manages tooltips for configuration options in the admin panel, providing helpful context.
*   `eurovat/views/js/eurovat.js`
    *   **Scope:** Front-office
    *   **Description:** The main front-office JavaScript.
        *   **Event listeners:** Binds to input events on the VAT number field (e.g., `keyup`, `change`), form submissions, and potentially `prestashop.on('updateCart')` or similar events.
        *   **DOM manipulation:** Dynamically displays validation status messages (valid/invalid), updates cart totals, shows/hides elements based on VAT status.
        *   **AJAX calls:** Sends VAT number and country data to `controllers/front/validate.php` for real-time validation.
        *   **Other:** Implements the "recheck cart VAT status" interval, flood protection logic.
*   `eurovat/views/js/eurovatBoMockConsole.js`
    *   **Scope:** Back-office (development/debugging)
    *   **Description:** Likely a utility for mocking console output or providing enhanced debugging capabilities within the PrestaShop Back Office, not typically used in production.

### 4.5 CSS Stylesheets (`views/css/`)

*   `eurovat/views/css/admin_eurovat.css`
    *   **Scope:** Back-office admin form styling.
    *   **Main UI components and containers it styles:** Configuration page elements, audit list table, dashboard widgets, alerts, and tooltips within the module's admin interface.
    *   **Key CSS class selectors developers can override:** `.eurovat-admin-config`, `.eurovat-alert`, `.eurovat-dashboard-widget`, `.eurovat-audit-table`.
*   `eurovat/views/css/eurovat.css`
    *   **Scope:** Front-office customer styling.
    *   **Main UI components and containers it styles:** VAT input fields, validation status messages (success/error), VAT status bars in header/product page/checkout, reverse charge notes.
    *   **Key CSS class selectors developers can override:** `.eurovat-vat-form`, `.eurovat-status-message.valid`, `.eurovat-status-message.invalid`, `.eurovat-header-bar`, `.eurovat-product-vat-info`, `.eurovat-checkout-vat-status`.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

*   `eurovat/views/templates/hook/adminDashboardWidget.tpl`
    *   **Hook:** Potentially `displayAdminHomeQuickview` or a custom dashboard hook.
    *   **Outputs:** A widget for the PrestaShop admin dashboard, displaying analytics or quick stats related to VAT validation.
*   `eurovat/views/templates/hook/adminOrderProofPack.tpl`
    *   **Hook:** `displayAdminOrder` or `displayAdminOrderTabContent` (on the order view page).
    *   **Outputs:** A block or tab within the admin order details page, allowing administrators to view or generate VAT proof documents for a specific order.
*   `eurovat/views/templates/hook/customerHistory.tpl`
    *   **Hook:** `displayCustomerAccount` or `displayMyAccountBlock`.
    *   **Outputs:** Information about the customer's VAT validation history or current status within their personal account area.
*   `eurovat/views/templates/hook/displayBanner.tpl`
    *   **Hook:** `displayBanner` (or similar global banner hook).
    *   **Outputs:** The VAT input form or a promotional message about 0% VAT, typically displayed at the top of the store.

#### Admin templates (`views/templates/admin/`)

*   `eurovat/views/templates/admin/alerts.tpl`
    *   **Outputs:** HTML structure for displaying various alerts and notifications in the Back Office.
*   `eurovat/views/templates/admin/audit.tpl`
    *   **Outputs:** The main template for the `AdminEurovatVatValidationAuditController`, rendering the VAT validation audit list.
*   `eurovat/views/templates/admin/configure.tpl`
    *   **Outputs:** The primary configuration form for the module, rendered by `getContent()` in `eurovat.php`. Contains all the settings described in section 4.1.
*   `eurovat/views/templates/admin/countriesSelector.tpl`
    *   **Outputs:** A reusable template for the country selection interface within the configuration.
*   `eurovat/views/templates/admin/cron.tpl`
    *   **Outputs:** The configuration section related to the cron job settings, including interval and activation.
*   `eurovat/views/templates/admin/dashboard.tpl`
    *   **Outputs:** The full dashboard view, potentially integrating `adminDashboardWidget.tpl` and other analytics.
*   `eurovat/views/templates/admin/hooksRepair.tpl`
    *   **Outputs:** A utility template, possibly for diagnosing and repairing missing or incorrectly registered hooks.
*   `eurovat/views/templates/admin/proof_pack_view.tpl`
    *   **Outputs:** A detailed view for a VAT proof pack, likely within the order details page.
*   `eurovat/views/templates/admin/vat_audit_list_settings.tpl`
    *   **Outputs:** Settings or filters specific to the VAT audit list display.
*   `eurovat/views/templates/admin/vat_audit_tabs.tpl`
    *   **Outputs:** Tab navigation for the VAT audit section, if there are multiple sub-sections (e.g., audit log, analytics).

#### Front-office templates (`views/templates/front/`)

*   `eurovat/views/templates/front/form.tpl`
    *   **Outputs:** The core HTML structure for the VAT number input form, used in various front-office hooks (product page, checkout, header).

### 4.7 Database Schema & Hooks Map

#### Database Tables

*   `ps_eurovat_validation`
    *   **Purpose:** Stores a historical log of all VAT validation attempts.
    *   **Key Fields (expected):**
        *   `id_eurovat_validation` (Primary Key)
        *   `id_customer` (Foreign key to `ps_customer`)
        *   `id_cart` (Foreign key to `ps_cart`)
        *   `id_order` (Foreign key to `ps_order`)
        *   `vat_number` (The VAT number entered)
        *   `country_code` (The country associated with the VAT number)
        *   `validation_status` (e.g., 'valid', 'invalid', 'error')
        *   `validation_response` (Raw response from VIES/API)
        *   `validation_date` (Timestamp of the validation)
        *   `source` (e.g., 'checkout', 'customer_account', 'cron')
        *   `ip_address` (IP address of the user who performed the validation)

*   `ps_configuration`
    *   **Purpose:** Stores all module configuration settings.
    *   **Key Configuration Keys:**
        *   `EUROVAT_YOUR_COUNTRY`
        *   `EUROVAT_ELIGIBLE_COUNTRIES`
        *   `EUROVAT_TAX_RULE`
        *   `EUROVAT_DISPLAY_HEADER`
        *   `EUROVAT_DISPLAY_CUSTOMHTML1`
        *   `EUROVAT_DISPLAY_LOGGED_STATUS`
        *   `EUROVAT_DISPLAY_CHECKOUT_PERSONAL`
        *   `EUROVAT_DISPLAY_CHECKOUT_SUMMARY`
        *   `EUROVAT_DISPLAY_CHECKOUT_PAYMENT`
        *   `EUROVAT_DISPLAY_PRODUCT_PAGE`
        *   `EUROVAT_REVERSE_CHARGE_NOTE`
        *   `EUROVAT_REVALIDATE_ON_ORDER`
        *   `EUROVAT_FLOOD_OFF_MINUTES`
        *   `EUROVAT_CACHE_TTL_HOURS`
        *   `EUROVAT_CART_RECHECK_INTERVAL`
        *   `EUROVAT_CRON_REVALIDATE_ENABLED`
        *   `EUROVAT_CRON_INTERVAL_DAYS`
        *   `EUROVAT_APILAYER_KEY`
        *   `EUROVAT_ABSTRACTAPI_KEY`
        *   `EUROVAT_VATSTACK_KEY`
        *   `EUROVAT_DISABLED_LANGS`

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | In the `<head>` section of every page. | Inject CSS/JS, or display a global VAT status bar. |
| `displayProductAdditionalInfo` | On the product page, typically below the product description. | Display VAT input form or status on product pages. |
| `displayCustomhtml1` | Custom hook, often in theme's top section (e.g., `sp_topdeals`). | Display VAT input form in specific theme areas. |
| `displayPaymentTop` | At the top of the payment step in checkout. | Display VAT status or form before payment. |
| `displayBanner` | In a banner area, typically at the top of the site. | Display VAT input form or promotional message. |
| `displayAdminCustomers` | On the customer list or customer detail page in BO. | Add VAT-related information or actions for customers. |
| `ActionDispatcher` | Before a controller is dispatched. | Modify routing or context based on VAT status. |
| `ActionGetProductPropertiesAfter` | After product properties are retrieved. | Adjust product prices based on customer's VAT status. |
| `ActionProductPriceCalculation` | During product price calculation. | Apply 0% VAT to product prices if eligible. |
| `ActionBeforeValidateOrder` | Just before an order is validated. | Perform final VAT validation, adjust order taxes. |
| `ActionCronJob` | Triggered by PrestaShop's cron module. | Execute background tasks like VAT revalidation. |
| `ActionObjectAddressUpdateAfter` | After an address object is updated (e.g., in customer account). | Revalidate VAT if address details change. |
| `ActionTaxManager` | When tax rules are being managed or applied. | Intercept and modify tax application based on VAT validation. |
| `ActionPresentCart` | Before the cart is displayed. | Update cart totals and display VAT status. |
| `ActionFilterDeliveryOptionList` | Filters available delivery options. | Potentially adjust delivery costs based on VAT status (less common). |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please refer to your customer account at MyPresta.eu. Our team is dedicated to ensuring the module functions optimally and remains compatible with the newest PrestaShop versions.

*   **MyPresta.eu Order History & Downloads:** [https://mypresta.eu/my-account/orders/](https://mypresta.eu/my-account/orders/)
*   **MyPresta.eu Support:** [https://mypresta.eu/contact](https://mypresta.eu/contact)
