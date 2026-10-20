---
title: "VAT 0% for selected groups of customers - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the VAT 0% for selected groups of customers PrestaShop module by MyPresta.eu."
sidebar:
  label: "VAT 0% for selected groups of customers"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy VAT 0% for selected groups of customers Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/vat-0-for-selected-groups-of-customers.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/vat-0-for-selected-groups-of-customers/)
>
> ---


# VAT 0% for selected groups of customers

## 1. Requirements & Compatibility
-   **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
-   **PHP Compatibility**: PHP 7.1 - 8.5
-   **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required for PrestaShop itself and for the module's update checks.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)
After installation, clicking "Configure" will take you to the main configuration page for the "VAT 0% for selected groups of customers" module. This page is divided into several sections.

#### Settings Tab

This is the primary tab where you define which customer groups will benefit from 0% VAT.

**1. Groups of customers that will have VAT 0%**
-   **What this setting does:** This is the most crucial setting. It allows you to select one or more customer groups from your PrestaShop store that will be exempt from VAT.
-   **Effect of changing this setting:**
    -   *When one or more groups are selected:* Any customer belonging to *at least one* of the selected groups will have all product prices, shipping, and order totals calculated with 0% VAT.
    -   *When no groups are selected:* The module will not apply any VAT exemptions, and all customers will be charged VAT according to your standard PrestaShop tax rules.
-   **Recommended value:** Select all customer groups that you intend to be VAT-exempt (e.g., "Wholesale Customers", "B2B Clients").
-   **Merchant scenario / example:** You run a B2B store. You have a customer group called "Wholesale Clients" who are all VAT-registered businesses. You would select "Wholesale Clients" from this list. When a customer from this group logs in, they will see all prices without VAT.

**2. Select Tax rule**
-   **What this setting does:** This option allows you to specify a particular tax rule that the module should use when applying the 0% VAT. While the module sets the tax rate to 0%, PrestaShop often requires a valid tax rule to be associated with the calculation.
-   **Effect of changing this setting:**
    -   *When a specific tax rule is selected:* The module will attempt to use this tax rule, but with a 0% rate, for the exempt customer groups. This can be useful for ensuring compatibility with other modules or specific accounting setups that expect a tax rule to always be present.
    -   *When "None" or no specific rule is selected (default behavior):* The module will handle the 0% VAT application directly, often by overriding the tax rate to 0% without strictly adhering to a pre-defined tax rule, which is usually sufficient.
-   **Recommended value:** Leave as default unless you encounter specific compatibility issues with other modules or have a very particular accounting requirement. If you do select one, choose a generic 0% tax rule if you have one, or a standard tax rule that the module can then override to 0%.
-   **Merchant scenario / example:** Your accountant requires that all transactions, even 0% VAT ones, are linked to a specific tax rule ID for reporting purposes. You might create a "VAT 0% (Exempt)" tax rule in PrestaShop and select it here.

#### Hook repair Tab
This tab is for advanced troubleshooting and ensuring the module's hooks are correctly registered.

-   **What this setting does:** This section provides tools to re-register the module's hooks in case they become unregistered or corrupted, which can sometimes happen after theme changes, module conflicts, or database issues.
-   **Effect of changing this setting:**
    -   *Clicking "Repair hooks":* This action will attempt to re-register all the necessary hooks that the module uses to function correctly. If the module wasn't working as expected (e.g., VAT wasn't being removed), this might resolve the issue.
-   **Recommended value:** Only use this if you suspect the module is not functioning correctly (e.g., VAT is still being charged to exempt groups) and after confirming your main settings are correct.
-   **Merchant scenario / example:** You've just updated your PrestaShop theme, and now your VAT-exempt customers are suddenly being charged VAT. You've checked your group settings, and they are correct. Clicking "Repair hooks" here might fix the underlying issue.

#### Updates Tab
This tab provides information about module updates.

-   **What this setting does:** This section checks for available updates for the module and provides information about your current version.
-   **Effect of changing this setting:**
    -   *Checking for updates:* Informs you if a newer version of the module is available, allowing you to keep your module up-to-date with the latest features and bug fixes.
-   **Recommended value:** Periodically check this tab to ensure you are running the latest version for optimal performance and security.
-   **Merchant scenario / example:** You want to ensure your store is always running the most stable and secure software. You visit this tab once a month to see if there are any new updates for your MyPresta.eu modules.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|---|
| Module Configuration Page | **Groups of customers that will have VAT 0%** | Select relevant groups (e.g., "Wholesale Clients") | Defines which customer groups will have 0% VAT applied to all prices and totals. |
| Module Configuration Page | **Select Tax rule** | Leave as default (or select a 0% tax rule if needed for accounting) | Associates the 0% VAT calculation with a specific tax rule for compatibility or reporting. |
| Hook repair Tab | **Repair hooks button** | Only use for troubleshooting | Re-registers module hooks to resolve functionality issues (e.g., VAT not being removed). |
| Updates Tab | **Check for updates** | Periodically check | Informs about available module updates for new features and bug fixes. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: VAT is still being charged even though I've selected the customer group.**
A1:
*   **Check Group Assignment:** Ensure the customer you are testing with is actually assigned to one of the selected VAT-exempt groups. Log in as the customer, go to their account details, or check in the Back Office under `Customers > Customers`.
*   **Module Configuration:** Double-check that the correct groups are selected in the module's configuration page (`Modules > Module Manager > Configure` for "VAT 0% for selected groups of customers").
*   **Cache:** Clear your PrestaShop cache (under `Advanced Parameters > Performance`) and your browser cache. Sometimes old data can be displayed.
*   **Hook Repair:** Go to the "Hook repair" tab in the module configuration and click the "Repair hooks" button. This can resolve issues where the module's integration points with PrestaShop might have become unregistered.

**Q2: Will this module affect my existing tax rules for non-exempt customers?**
A2: No, this module is designed to *only* apply 0% VAT to customers belonging to the specific groups you select. For all other customers, your standard PrestaShop tax rules and configurations will apply as usual.

**Q3: Does this module work for shipping costs as well?**
A3: Yes, the module is designed to apply 0% VAT to all aspects of the order, including product prices, shipping costs, and any other taxable elements, resulting in a total order value with 0% VAT for the selected customer groups.

**Q4: I have a custom theme. Will this module work with it?**
A4: Yes, this module works by modifying PrestaShop's core tax calculation logic through hooks, rather than directly altering front-office templates. Therefore, it should be compatible with most custom themes without issues. If you experience display problems (e.g., prices not updating), it's likely a caching issue or a conflict with another module that also heavily modifies tax calculations.

**Q5: How do I translate the module's text into other languages?**
A5: If the module introduces any new text strings (though this module primarily works in the background), you can translate them via PrestaShop's translation interface:
1.  Go to `International > Translations`.
2.  Select "Installed modules translations".
3.  Choose your theme, the language, and then select "VAT 0% for selected groups of customers" from the module list.
4.  You can then modify any translatable strings.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview
The "VAT 0% for selected groups of customers" module operates by leveraging PrestaShop's hook system to intercept and modify tax calculations at various stages of the ordering process. It primarily uses the `actionTaxManager` and `actionProductPriceCalculation` hooks to dynamically adjust the tax rate to 0% for customers belonging to specified groups. It also includes a custom `TaxManager` class to handle the tax override logic. The module follows a standard PrestaShop module structure, with a main module file, a dedicated class for tax management, and Smarty templates for its Back Office configuration.

### 4.2 Controllers (`controllers/`)
This module does not utilize custom Front-Office or Back-Office Admin Controllers. All configuration is handled via the `getContent()` method in the main module file.

### 4.3 Core Classes & Models (`classes/`)

-   **`groupvat/classes/GroupvatTaxManager.php`**
    *   **Class Name:** `GroupvatTaxManager`
    *   **Parent Class:** `TaxManager` (PrestaShop's core `TaxManager` class)
    *   **Responsibility:** This class is the core of the module's functionality. It extends PrestaShop's default `TaxManager` to override its behavior. Its primary method, `getTaxCalculator()`, is crucial. When a customer is identified as belonging to a VAT-exempt group, this class ensures that the `TaxCalculator` returns a 0% tax rate, effectively removing VAT from prices. It also contains logic to check if the current customer is in one of the configured exempt groups.
    *   **Key Methods:**
        *   `getTaxCalculator(array $params)`: Overrides the default tax calculator to return a 0% tax rate if the customer is in an exempt group.
        *   `isCustomerInGroup(int $id_customer)`: Helper method to determine if a given customer ID belongs to any of the configured VAT-exempt groups.

-   **`groupvat/classes/index.php`**
    *   **Responsibility:** Standard empty `index.php` file to prevent directory listing.

### 4.4 JavaScript Assets (`views/js/`)
This module does not include any custom JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)
This module does not include any custom CSS files. Styling for the Back Office configuration is handled by PrestaShop's default admin theme.

### 4.6 Smarty Template Structure (`views/templates/`)

-   **`groupvat/views/templates/admin/configure.tpl`**
    *   **Scope:** Back-office admin configuration.
    *   **Purpose:** This is the main template for the module's configuration page, rendered by `getContent()` in `groupvat.php`. It includes other templates for specific sections like customer group selection and hook repair. It typically wraps the entire configuration form.

-   **`groupvat/views/templates/admin/customerGroups.tpl`**
    *   **Scope:** Back-office admin configuration.
    *   **Purpose:** This template renders the section where the merchant selects the customer groups that will have 0% VAT. It displays a list of available customer groups with checkboxes.
    *   **Variables:** Likely uses `$groups` (array of customer groups), `$selected_groups` (array of IDs of currently selected groups), `$tax_rules` (array of available tax rules), `$selected_tax_rule` (ID of the currently selected tax rule).

-   **`groupvat/views/templates/admin/hooksRepair.tpl`**
    *   **Scope:** Back-office admin configuration.
    *   **Purpose:** This template renders the "Hook repair" section, providing a button to re-register the module's hooks.

### 4.7 Database Schema & Hooks Map

-   **Database Tables**:
    *   This module does not create custom database tables.
    *   It stores its configuration settings in PrestaShop's `ps_configuration` table.
        *   `groupvat_groups`: Stores a comma-separated list of customer group IDs selected for VAT exemption.
        *   `groupvat_tax`: Stores the ID of the selected tax rule (if any).
        *   `mypresta_updates`: Stores information related to module updates.

-   **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
|---|---|---|
| `actionDispatcher` | Before a controller is dispatched. | Used to potentially override or modify dispatch behavior, though often used for general setup. |
| `ActionDispatcher` | (Alias of `actionDispatcher`) | Same as above. |
| `actionCartGetPackageShippingCost` | When calculating shipping costs for a package in the cart. | Crucial for ensuring shipping costs are also calculated with 0% VAT for exempt groups. |
| `displayTaxManager` | (Deprecated/less common) | Historically used for displaying tax-related information. |
| `ActionGetProductPropertiesAfter` | After product properties are retrieved. | Allows modification of product data, including price and tax, before display. |
| `taxManager` | (Deprecated/less common) | Historically used for tax management. |
| `ActionAuthentication` | After a customer authenticates (logs in). | Can be used to set session variables or perform actions based on customer group after login. |
| `ActionTaxManager` | When the `TaxManager` class is instantiated or its methods are called. | **Primary hook for this module.** Allows the module to inject its custom `GroupvatTaxManager` or modify tax calculation logic. |
| `ActionPresentCart` | Before the cart is presented to the user. | Allows modification of cart data, including prices and totals, before rendering. |
| `ActionProductPriceCalculation` | During the product price calculation process. | **Primary hook for this module.** Allows the module to modify the tax rate applied to product prices. |
| `actionGetProductPropertiesAfter` | (Alias of `ActionGetProductPropertiesAfter`) | Same as above. |
| `ActionFilterDeliveryOptionList` | Before the list of delivery options is displayed. | Allows modification of delivery options, potentially affecting their prices (and thus tax). |

## 5. Official Support & Updates
For official support, updates, and the latest versions of the "VAT 0% for selected groups of customers" module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have.
