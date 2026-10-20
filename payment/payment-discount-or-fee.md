---
title: "Payment Discount or Fee - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Payment Discount or Fee PrestaShop module by MyPresta.eu."
sidebar:
  label: "Payment Discount or Fee - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Payment Discount or Fee Module on MyPresta.eu](https://mypresta.eu/modules/payment-process/payment-discount-or-fee.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/payment/payment-discount-or-fee/)
>
> ---


# Payment Discount or Fee

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required, which are typically available on most modern web hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The “Payment Discount or Fee” module provides a comprehensive set of options to precisely control how discounts or fees are applied.

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Payment Discount or Fee)

This is the main configuration screen where you enable and set up the core behavior of the module.

- **Enable Module:**

  - **What this setting does:** This is the master switch to turn the module’s functionality on or off across your store.
  - **Effect of changing this setting:**
    - *When enabled:* The module will start applying discounts or fees based on your defined rules during checkout.
    - *When disabled:* The module will cease all operations, and no discounts or fees will be applied.
  - **Recommended value:** YES (once you’ve configured your rules).
  - **Merchant scenario / example:** You’ve finished setting up all your rules and are ready to go live. Enable this to activate the module. If you need to temporarily disable it for maintenance, set it to NO.
- **Display Fee/Discount on Cart Summary:**

  - **What this setting does:** Controls whether the payment method adjustment is shown as a separate line item in the cart summary *before* the customer reaches the payment step.
  - **Effect of changing this setting:**
    - *When enabled:* Customers will see a line item like “Payment Method Adjustment” in their cart summary, even before selecting a payment method, indicating that the final price might change.
    - *When disabled:* The adjustment will only appear once the customer selects a payment method on the checkout page.
  - **Recommended value:** YES (for transparency).
  - **Merchant scenario / example:** You want customers to be fully aware of potential payment adjustments as early as possible. Enabling this provides maximum transparency.
- **Apply Fee/Discount to Shipping Cost:**

  - **What this setting does:** Determines if the calculated discount or fee should also be applied to the shipping cost of the order, or only to the product total.
  - **Effect of changing this setting:**
    - *When enabled:* If you have a 2% fee, and the product total is $100 and shipping is $10, the fee will be 2% of $110 ($2.20).
    - *When disabled:* The 2% fee would only apply to the $100 product total ($2.00), and shipping would remain separate.
  - **Recommended value:** YES (if your payment gateway fees also apply to the total order value including shipping).
  - **Merchant scenario / example:** Most payment gateways charge a percentage fee on the *entire* transaction amount, including shipping. Enabling this ensures your fee accurately reflects your costs.
- **Apply Fee/Discount to Tax:**

  - **What this setting does:** Determines if the calculated discount or fee should also be applied to the tax amount of the order, or only to the product total (and potentially shipping).
  - **Effect of changing this setting:**
    - *When enabled:* If you have a 2% fee, and the product total is $100, shipping $10, and tax $20, the fee will be 2% of $130 ($2.60).
    - *When disabled:* The 2% fee would only apply to the product total (and shipping if enabled), and tax would remain separate.
  - **Recommended value:** YES (if your payment gateway fees also apply to the total order value including tax).
  - **Merchant scenario / example:** Similar to shipping, payment gateways typically charge on the grand total. Enabling this ensures your fee calculation is comprehensive.
- **Fee/Discount Label in Cart/Order:**

  - **What this setting does:** Allows you to customize the text label that appears next to the discount or fee amount in the cart summary and order details.
  - **Effect of changing this setting:**
    - *When set to “Payment Method Surcharge”:* This text will be displayed.
    - *When set to “Payment Discount”:* This text will be displayed.
  - **Recommended value:** “Payment Method Adjustment” or “Payment Surcharge” / “Payment Discount” depending on your primary use.
  - **Merchant scenario / example:** You primarily use the module to add fees. Setting the label to “Payment Surcharge” makes it clear to customers. If you offer discounts, “Payment Discount” is more appropriate.
- **Cron Job URL for Audit Log Cleanup:**

  - **What this setting does:** Provides a URL that you can set up as a cron job on your server to automatically clean up old entries from the module’s audit log, preventing the database from growing too large.
  - **Effect of changing this setting:**
    - *When configured as a cron job:* The audit log will be regularly purged of old entries, improving database performance.
    - *When not configured:* The audit log will grow indefinitely, potentially slowing down your Back Office over time.
  - **Recommended value:** Set up a cron job to run this URL daily or weekly.
  - **Merchant scenario / example:** You want to keep your database lean and fast. Copy this URL and add it to your hosting control panel’s cron job scheduler.

### 2.2 Dedicated Admin Screen: Payment Discount or Fee Rules (Back Office > Payment > Payment Discount or Fee Rules)

This screen is where you define and manage all the rules for applying discounts or fees.

- **Screen Name & Menu Location:** **Payment Discount or Fee Rules** (found under **Payment** in the main PrestaShop Back Office menu).
- **Available Actions & Settings:**

  - **Rule Listing Table:** Displays all your currently active and inactive rules, showing their name, payment method, type (discount/fee), value, and status.
  - **“Add New Rule” Button:** Click this to create a new discount or fee rule.
  - **Edit/Delete Actions:** For each rule in the list, you can click to edit its details or delete it.
  - **Form Fields for Adding/Editing a Rule:**
    - **Rule Name:**
      - **What this setting does:** A descriptive name for your rule, visible only in the Back Office.
      - **Effect of changing this setting:** Helps you identify and manage your rules easily.
      - **Recommended value:** Clear and descriptive (e.g., “PayPal 2% Fee,” “Bank Transfer 5% Discount”).
    - **Payment Method:**
      - **What this setting does:** Selects which specific payment gateway or method this rule applies to.
      - **Effect of changing this setting:** The rule will only activate when a customer chooses this payment method.
      - **Recommended value:** Choose the exact payment method you want to target.
      - **Merchant scenario / example:** You want to add a fee for “PayPal,” so you select “PayPal” from the dropdown.
    - **Type:**
      - **What this setting does:** Determines if the rule applies a “Discount” or a “Fee.”
      - **Effect of changing this setting:**
        - *Discount:* Reduces the order total.
        - *Fee:* Increases the order total.
      - **Recommended value:** Select based on your goal (e.g., “Fee” for credit card processing costs).
    - **Value:**
      - **What this setting does:** The amount or percentage of the discount/fee.
      - **Effect of changing this setting:**
        - *If “Type” is “Percentage”:* Enter “2” for 2%.
        - *If “Type” is “Fixed Amount”:* Enter “5.00” for $5.00.
      - **Recommended value:** The exact percentage or fixed amount you wish to apply.
    - **Value Type:**
      - **What this setting does:** Choose whether the “Value” is a “Percentage” of the order total or a “Fixed Amount.”
      - **Effect of changing this setting:** Dictates how the “Value” field is interpreted.
      - **Recommended value:** Percentage is common for fees; fixed amount for specific discounts.
    - **Minimum Cart Amount (Optional):**
      - **What this setting does:** The minimum order total (before the discount/fee) required for this rule to apply.
      - **Effect of changing this setting:** If the cart total is below this amount, the rule will not be applied.
      - **Recommended value:** Leave empty if no minimum is required.
      - **Merchant scenario / example:** You only want to apply a fee on larger orders to avoid micro-fees on small purchases.
    - **Maximum Cart Amount (Optional):**
      - **What this setting does:** The maximum order total (before the discount/fee) for this rule to apply.
      - **Effect of changing this setting:** If the cart total is above this amount, the rule will not be applied.
      - **Recommended value:** Leave empty if no maximum is required.
    - **Customer Groups (Optional):**
      - **What this setting does:** Restricts the rule to specific customer groups (e.g., “Wholesalers,” “Guests”).
      - **Effect of changing this setting:** Only customers belonging to the selected groups will be affected by this rule.
      - **Recommended value:** Select “All Customer Groups” unless you have specific group-based pricing strategies.
      - **Merchant scenario / example:** You want to offer a special discount for your “VIP Customers” when they pay by bank transfer.
    - **Countries (Optional):**
      - **What this setting does:** Restricts the rule to customers from specific countries.
      - **Effect of changing this setting:** The rule will only apply if the customer’s shipping address is in one of the selected countries.
      - **Recommended value:** Select “All Countries” unless you have country-specific payment strategies.
      - **Merchant scenario / example:** You have higher processing fees for international credit card payments from certain regions.
    - **Products to Exclude (Optional):**
      - **What this setting does:** Allows you to specify individual products that should *not* be included in the calculation of the discount or fee.
      - **Effect of changing this setting:** The value of these products will be subtracted from the cart total *before* the percentage or fixed amount is calculated.
      - **Recommended value:** Leave empty unless specific products should be exempt.
      - **Merchant scenario / example:** You sell some low-margin products where applying a fee would make them unprofitable, so you exclude them.
    - **Status (Enable/Disable):**
      - **What this setting does:** Activates or deactivates an individual rule without deleting it.
      - **Effect of changing this setting:**
        - *Enabled:* The rule is active and will be applied.
        - *Disabled:* The rule is inactive and will not be applied.
      - **Recommended value:** Enabled for active rules.
      - **Merchant scenario / example:** You want to temporarily pause a rule for a promotion without losing its configuration.
- **Recommended workflow for daily store management:**

  1. Start by identifying which payment methods incur costs or offer benefits you want to pass on.
  2. Click “Add New Rule.”
  3. Give the rule a clear name.
  4. Select the target payment method.
  5. Choose “Fee” or “Discount” and enter the value (percentage or fixed).
  6. Refine the rule with minimum/maximum cart amounts, customer groups, countries, or product exclusions as needed.
  7. Enable the rule and save.
  8. Test the rule on your front office by placing a test order.

### 2.3 Dedicated Admin Screen: Payment Discount or Fee Audit Log (Back Office > Payment > Payment Discount or Fee Audit Log)

This screen provides a historical record of all instances where the module has applied a discount or fee.

- **Screen Name & Menu Location:** **Payment Discount or Fee Audit Log** (found under **Payment** in the main PrestaShop Back Office menu).
- **Available Actions & Settings:**
  - **Log Listing Table:** Displays entries with details such as:
    - **Order ID:** The ID of the order where the adjustment was applied.
    - **Customer Name:** The customer who placed the order.
    - **Payment Method:** The payment method chosen.
    - **Rule Applied:** The name of the rule that triggered the adjustment.
    - **Adjustment Type:** Whether it was a discount or a fee.
    - **Adjustment Value:** The amount of the discount or fee.
    - **Date:** When the adjustment was applied.
  - **Filtering and Searching:** You can filter the log by order ID, customer, payment method, or date to quickly find specific entries.
  - **Effect of changes:** This screen is for viewing only; you cannot directly modify log entries here. It serves as a valuable record for troubleshooting and analysis.
- **Recommended workflow for daily store management:**
  - Regularly review the audit log to ensure rules are being applied correctly.
  - Use it to troubleshoot customer inquiries about pricing discrepancies.
  - Monitor the volume of adjustments to understand the impact of your rules.

### 2.4 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Enable Module | YES | Master switch for module functionality. |
|  | Display Fee/Discount on Cart Summary | YES | Shows adjustment early in cart for transparency. |
|  | Apply Fee/Discount to Shipping Cost | YES | Includes shipping in fee/discount calculation. |
|  | Apply Fee/Discount to Tax | YES | Includes tax in fee/discount calculation. |
|  | Fee/Discount Label in Cart/Order | “Payment Method Adjustment” | Customizes the label shown to customers. |
|  | Cron Job URL for Audit Log Cleanup | (URL provided) | Automates cleanup of old audit log entries. |
| **Payment Discount or Fee Rules** | Rule Name | (Descriptive name) | Internal name for the rule. |
|  | Payment Method | (Specific method) | Selects the payment method for the rule. |
|  | Type | Fee / Discount | Determines if it’s an increase or decrease. |
|  | Value | (Numeric value) | The amount or percentage of the adjustment. |
|  | Value Type | Percentage / Fixed Amount | How the ‘Value’ is interpreted. |
|  | Minimum Cart Amount | (Empty) | Minimum order total for rule to apply. |
|  | Maximum Cart Amount | (Empty) | Maximum order total for rule to apply. |
|  | Customer Groups | All Customer Groups | Restricts rule to specific customer groups. |
|  | Countries | All Countries | Restricts rule to specific countries. |
|  | Products to Exclude | (Empty) | Products whose value is excluded from calculation. |
|  | Status | Enabled | Activates or deactivates the rule. |
| **Payment Discount or Fee Audit Log** | (All fields) | (View Only) | Provides a historical record of applied adjustments. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My discounts/fees aren’t showing up on the checkout page. What should I check?**
A1:

- **Module Enabled?** Go to **Modules > Module Manager** and ensure “Payment Discount or Fee” is enabled.
- **Rules Active?** Navigate to **Payment > Payment Discount or Fee Rules** and check that your specific rules are enabled (Status column).
- **Rule Conditions Met?** Double-check if the cart total, customer group, country, or excluded products conditions of your rules are being met by your test order.
- **Payment Method Selected?** The adjustment only appears *after* a payment method is selected on the checkout page (unless “Display Fee/Discount on Cart Summary” is enabled).
- **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (top right). Sometimes, old cached data prevents changes from appearing immediately.

**Q2: The discount/fee amount seems incorrect.**
A2:

- **Value Type (Percentage vs. Fixed):** Ensure you’ve selected the correct “Value Type” (Percentage or Fixed Amount) for your rule.
- **Apply to Shipping/Tax:** Check the main module configuration if “Apply Fee/Discount to Shipping Cost” and “Apply Fee/Discount to Tax” are enabled or disabled, as this affects the base amount for percentage calculations.
- **Excluded Products:** If you have products excluded from the calculation, ensure their value is correctly subtracted before the percentage/fixed amount is applied.
- **Currency:** Ensure your store’s default currency is correctly set in PrestaShop, as the module relies on this for fixed amounts.

**Q3: The module is causing a conflict with another module or my theme.**
A3:

- **Identify the Conflict:** Try disabling other modules one by one to pinpoint which one is causing the conflict.
- **Theme Overrides:** If you have a heavily customized theme, it might be overriding core PrestaShop checkout templates that the module relies on. Check your theme’s `templates/checkout/` folder for files like `payment.tpl` or `cart-summary.tpl`.
- **Contact Support:** If you suspect a conflict, gather details (error messages, steps to reproduce) and contact MyPresta.eu support.

**Q4: How do I translate the “Fee/Discount Label” into other languages?**
A4:

- Go to **International > Translations**.
- Select “Installed modules translations,” your theme, and the language you want to translate.
- Find the “Payment Discount or Fee” module. You should see the field for translating the “Fee/Discount Label in Cart/Order” setting.

**Q5: My audit log is getting too big. How do I manage it?**
A5:

- In the module’s main configuration, you’ll find a “Cron Job URL for Audit Log Cleanup.”
- Copy this URL and set it up as a cron job on your hosting server. Most hosting control panels (cPanel, Plesk) have a “Cron Jobs” section where you can add a new job.
- Set it to run daily or weekly (e.g., `wget -q -O /dev/null "YOUR_CRON_URL_HERE"`). This will automatically remove old log entries and keep your database optimized.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview of the “Payment Discount or Fee” module for developers, webmasters, and technical agencies.

### 4.1 Architecture Overview

The “Payment Discount or Fee” module follows a standard PrestaShop MVC (Model-View-Controller) pattern, with a strong emphasis on hooks to integrate into the checkout flow. It utilizes `ObjectModel` for managing rules and audit logs, and custom controllers for both front-office AJAX interactions and back-office management. The core logic for calculating and applying fees/discounts is encapsulated in dedicated engine classes, ensuring separation of concerns. Compatibility classes are used to bridge differences between PrestaShop 1.7, 8, and 9.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `controllers/front/ajax.php`
  - **Class Name:** `PaydisorfeeAjaxModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** Handles AJAX requests from the checkout page. When a customer selects a payment method, this controller receives the request, calculates the applicable discount/fee based on the active rules, and returns the updated cart summary data (e.g., new total, fee/discount line item) to be displayed dynamically.
- `controllers/front/cron.php`
  - **Class Name:** `PaydisorfeeCronModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** Provides the endpoint for the audit log cleanup cron job. When accessed, it triggers the cleanup logic within the module, removing old log entries based on configured retention policies.
- `controllers/front/index.php`
  - **Class Name:** `PaydisorfeeIndexModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** A placeholder front controller, typically used for default module pages or to prevent directory listing. In this module, its primary function might be to handle default routing if no specific action is requested, or it might redirect to the main shop page.

#### Back-Office Admin Controllers

- `controllers/admin/AdminPaydisorfeeAuditLog.php`
  - **Class Name:** `AdminPaydisorfeeAuditLogController` (extends `ModuleAdminController`)
  - **Tab Name:** Payment Discount or Fee Audit Log
  - **Managed Entity:** `PaydisorfeeAuditLog` (maps to `paydisorfee_log` database table)
  - **Responsibility:** Manages the display and filtering of the audit log entries in the PrestaShop Back Office. It uses `HelperList` to render the grid view of log records.
- `controllers/admin/AdminPaydisorfeeRules.php`
  - **Class Name:** `AdminPaydisorfeeRulesController` (extends `ModuleAdminController`)
  - **Tab Name:** Payment Discount or Fee Rules
  - **Managed Entity:** `PaydisorfeeRule` (maps to `paydisorfee_rule` database table)
  - **Responsibility:** Provides the interface for creating, editing, deleting, and listing payment discount/fee rules. It uses `HelperList` for the rule overview and `HelperForm` for the add/edit rule forms, including dynamic selectors for products, customer groups, and countries.
- `controllers/admin/index.php`
  - **Class Name:** `PaydisorfeeAdminIndexModuleFrontController` (extends `ModuleAdminController`)
  - **Responsibility:** Similar to the front `index.php`, this might serve as a default admin controller or a redirector if no specific action is requested for the admin context.

### 4.3 Core Classes & Models (`classes/`)

- `classes/index.php`: Standard empty file to prevent directory listing.
- `classes/PaydisorfeeAdmin.php`
  - **Responsibility:** Likely contains helper methods or utility functions specific to the Back Office administration, potentially for handling form submissions, data validation, or rendering specific admin components.
- `classes/PaydisorfeeAuditLog.php`
  - **Extends:** `ObjectModel`
  - **Database Table:** `paydisorfee_log`
  - **`$definition` fields:** Defines the structure of audit log entries (e.g., `id_order`, `id_customer`, `payment_method`, `rule_name`, `type`, `value`, `date_add`).
  - **Key Public Methods:** Methods for adding new log entries, retrieving log data, and potentially for cleanup operations.
- `classes/PaydisorfeeCartState.php`
  - **Responsibility:** Manages the state of the cart during the checkout process, specifically related to the module’s applied discount/fee. It likely stores and retrieves the calculated adjustment to ensure it persists across different steps of the checkout and is correctly applied to the order.
- `classes/PaydisorfeeCompatibility.php`
  - **Responsibility:** Contains methods to handle compatibility issues across different PrestaShop versions (1.7.x, 8.x, 9.x). This class abstracts away version-specific code, such as differences in hook names, class structures, or API calls, ensuring the module functions correctly on all supported versions.
- `classes/PaydisorfeeDashboard.php`
  - **Responsibility:** Likely provides data or logic for a potential dashboard or analytics view within the module’s admin interface, summarizing the impact of discounts/fees.
- `classes/PaydisorfeeEngine.php`
  - **Responsibility:** This is the core logic class for calculating and applying the discount or fee. It takes the current cart, selected payment method, and active rules as input, then determines the final adjustment amount. It handles percentage vs. fixed calculations, minimum/maximum cart amounts, and product exclusions.
- `classes/PaydisorfeeFeeProduct.php`
  - **Responsibility:** Potentially a helper class for creating a “virtual product” to represent the fee/discount in the cart, allowing it to be displayed as a line item. This is a common technique in PrestaShop to integrate dynamic price adjustments into the cart summary.
- `classes/PaydisorfeeLog.php`
  - **Responsibility:** This might be an alias or an older version of `PaydisorfeeAuditLog.php`, or a simpler logging mechanism for debugging purposes.
- `classes/PaydisorfeeRule.php`
  - **Extends:** `ObjectModel`
  - **Database Table:** `paydisorfee_rule`
  - **`$definition` fields:** Defines the structure of a payment rule (e.g., `name`, `id_payment_module`, `type`, `value`, `value_type`, `min_cart_amount`, `max_cart_amount`, `customer_groups`, `countries`, `excluded_products`, `active`).
  - **Key Public Methods:** Methods for CRUD operations on rules, retrieving active rules, and validating rule conditions.

### 4.4 JavaScript Assets (`views/js/`)

- `paydisorfee/lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Back-office (used in `AdminPaydisorfeeRules` for product exclusion selector).
  - **Description:** Provides autocomplete functionality for searching products when configuring the “Products to Exclude” field in a rule. It likely sends AJAX requests to a back-office controller to fetch product suggestions.
- `paydisorfee/views/js/adminPaydisorfeeDashboard.js`
  - **Scope:** Back-office (if a dashboard view exists).
  - **Description:** JavaScript for any dashboard or analytics features within the module’s admin interface. This could include chart rendering, data filtering, or dynamic content loading.
- `paydisorfee/views/js/adminPaydisorfeeSelector.js`
  - **Scope:** Back-office (used in `AdminPaydisorfeeRules`).
  - **Description:** Handles the dynamic selection of customer groups, countries, and potentially payment methods within the rule configuration form. It might manage multi-select boxes or provide interactive elements for these fields.
- `paydisorfee/views/js/checkout.js`
  - **Scope:** Front-office (checkout page).
  - **Description:** This is a critical script for the front-office functionality. It listens for changes in the selected payment method on the checkout page. When a payment method is chosen, it triggers an AJAX call to `controllers/front/ajax.php` to recalculate the cart total and dynamically update the order summary with the new discount/fee line item. It also handles the display logic for these updates.

### 4.5 CSS Stylesheets (`views/css/`)

- `paydisorfee/lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Back-office.
  - **Description:** Styles for the autocomplete search input and its suggestion dropdown, used in the product exclusion selector within the rule configuration.
- `paydisorfee/views/css/admin_paydisorfee.css`
  - **Scope:** Back-office.
  - **Description:** General styling for the module’s Back Office pages, including the rule list, audit log, and configuration forms. It ensures a consistent look and feel with the PrestaShop admin theme.
- `paydisorfee/views/css/front.css`
  - **Scope:** Front-office.
  - **Description:** Styles for displaying the discount/fee line item and any related messages on the checkout page or cart summary. It ensures the adjustment is clearly visible and well-integrated into the store’s design.

### 4.6 Smarty Template Structure (`views/templates/`)

- `paydisorfee/lib/searchTool/views/scripts.tpl`
  - **Scope:** Back-office.
  - **Description:** Contains Smarty code to include JavaScript and potentially CSS for the search tool (e.g., `autocomplete.js`). It’s likely included in the `AdminPaydisorfeeRules` form.
- `paydisorfee/views/templates/admin/auditPreview.tpl`
  - **Scope:** Back-office (AdminPaydisorfeeAuditLogController).
  - **Description:** Template for rendering the audit log entries, typically used by `HelperList` to display the data grid.
- `paydisorfee/views/templates/admin/cron_setup.tpl`
  - **Scope:** Back-office (Module Main Configuration).
  - **Description:** Displays the cron job URL and instructions for setting it up, as seen in the module’s main configuration page.
- `paydisorfee/views/templates/admin/rulesPreview.tpl`
  - **Scope:** Back-office (AdminPaydisorfeeRulesController).
  - **Description:** Template for rendering the list of payment rules, used by `HelperList` to display the data grid.
- `paydisorfee/views/templates/admin/scopeSelector.tpl`
  - **Scope:** Back-office (AdminPaydisorfeeRulesController).
  - **Description:** Template for the dynamic selectors (customer groups, countries, products to exclude) within the rule configuration form, often used in conjunction with `adminPaydisorfeeSelector.js`.
- `paydisorfee/views/templates/hook/admin_order.tpl`
  - **Scope:** Back-office (Hook `displayAdminOrderTabContent` or similar).
  - **Description:** Displays information about the applied payment discount or fee within the PrestaShop order detail page in the Back Office. This allows administrators to see the adjustment directly on the order.
- `paydisorfee/views/templates/hook/payment_top.tpl`
  - **Scope:** Front-office (Hook `displayPaymentTop` or similar).
  - **Description:** This template is likely used to display the dynamic discount/fee information on the checkout page, usually above the payment method selection, or as part of the order summary. It’s updated by `checkout.js` via AJAX.

### 4.7 Database Schema & Hooks Map

#### Database Tables

- `ps_paydisorfee_log`: Stores audit log entries for every applied discount or fee.
  - `id_paydisorfee_log` (PRIMARY KEY)
  - `id_order` (INT)
  - `id_customer` (INT)
  - `payment_method` (VARCHAR)
  - `rule_name` (VARCHAR)
  - `type` (VARCHAR, ‘discount’ or ‘fee’)
  - `value` (DECIMAL)
  - `date_add` (DATETIME)
- `ps_paydisorfee_rule`: Stores the configuration for each payment discount/fee rule.
  - `id_paydisorfee_rule` (PRIMARY KEY)
  - `name` (VARCHAR)
  - `id_payment_module` (INT)
  - `type` (VARCHAR, ‘discount’ or ‘fee’)
  - `value` (DECIMAL)
  - `value_type` (VARCHAR, ‘percentage’ or ‘fixed’)
  - `min_cart_amount` (DECIMAL)
  - `max_cart_amount` (DECIMAL)
  - `customer_groups` (TEXT, serialized array of IDs)
  - `countries` (TEXT, serialized array of IDs)
  - `excluded_products` (TEXT, serialized array of IDs)
  - `active` (TINYINT)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_configuration`: Module settings are stored here with keys like `PAYDISORFEE_ENABLED`, `PAYDISORFEE_DISPLAY_CART`, `PAYDISORFEE_APPLY_SHIPPING`, `PAYDISORFEE_APPLY_TAX`, `PAYDISORFEE_LABEL`.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionFrontControllerSetMedia` | Before front controller renders | Registers front-office CSS (`front.css`) and JS (`checkout.js`). |
| `actionAdminControllerSetMedia` | Before admin controller renders | Registers back-office CSS (`admin_paydisorfee.css`, `autocomplete.css`) and JS (`adminPaydisorfeeDashboard.js`, `adminPaydisorfeeSelector.js`, `autocomplete.js`). |
| `displayHeader` | In the `<head>` section of every page | Potentially for loading global JS/CSS or meta tags. |
| `displayPaymentTop` | At the top of the payment selection block on the checkout page | Displays the dynamic fee/discount information to the customer. |
| `actionCartSummary` | After cart summary is generated | Used to inject the fee/discount line item into the cart summary. |
| `actionPaymentConfirmation` | After an order is successfully placed | Records the applied discount/fee in the audit log. |
| `actionValidateOrder` | When an order is validated | Ensures the final order total reflects the payment method adjustment. |
| `displayAdminOrderTabContent` | Within the order detail page in the Back Office | Displays the payment adjustment details for the order. |
| `displayAdminOrder` | On the order detail page in the Back Office | Similar to `displayAdminOrderTabContent`, for displaying order-specific module data. |
| `actionGetExtraMailTemplateVars` | Before sending an order confirmation email | Injects the fee/discount details into email templates. |
| `actionObjectOrderAddAfter` | After a new order object is added | Potentially for final processing or logging related to the order. |
| `actionObjectOrderUpdateAfter` | After an order object is updated | Potentially for re-evaluating fees if an order is modified. |
| `actionObjectCartUpdateAfter` | After a cart object is updated | Triggers recalculation of potential fees/discounts. |
| `actionObjectCartAddAfter` | After a new cart object is added | Triggers recalculation of potential fees/discounts. |
| `actionAjaxDie` | Before `die()` in AJAX context | Allows module to perform actions before AJAX response is sent. |
| `displayBackOfficeHeader` | In the `<head>` section of every Back Office page | Registers global admin JS/CSS. |
| `displayModuleConfigureExtraButtons` | On the module configuration page | Adds extra buttons (e.g., “Manage Rules,” “View Audit Log”). |
| `displayPaymentOptions` | Displays payment options on checkout | Potentially modifies payment options based on rules. |
| `actionPaymentOptionsModifier` | Modifies payment options before display | Allows module to add/remove/modify payment options. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Payment Discount or Fee” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu). Our support team is available to assist you with any issues or questions regarding the module’s functionality and integration.
