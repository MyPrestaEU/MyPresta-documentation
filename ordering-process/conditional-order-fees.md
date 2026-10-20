---
title: "Conditional Order Fees - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Conditional Order Fees PrestaShop module by MyPresta.eu."
sidebar:
  label: "Conditional Order Fees - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Conditional Order Fees Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/conditional-order-fees.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/conditional-order-fees/)
>
> ---


# Conditional Order Fees

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) typically available on most PrestaShop-compatible hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Conditional Order Fees)

This is the main configuration screen where you enable or disable the module and set up the foundational “product” that represents your fees.

- **Menu Location:** Back Office > Modules > Module Manager > Conditional Order Fees > Configure

#### General Settings

- **Enable Module:**

  - **What this setting does:** This is the master switch for the entire module.
  - **Effect of changing this setting:**
    - *When enabled:* The module will actively evaluate your defined fee policies and apply fees to carts that meet the conditions.
    - *When disabled:* No fees will be applied by this module, regardless of your policy settings.
  - **Recommended value:** YES (once you have configured your policies).
  - **Merchant scenario / example:** You’ve finished setting up all your fee policies and are ready to go live. Enable this to start charging fees. If you need to temporarily stop all fees for maintenance or a promotion, disable it.
- **Fee Product ID:**

  - **What this setting does:** This crucial setting links your fees to a specific, hidden product in your catalog. PrestaShop needs a “product” to represent any item added to the cart, even if it’s a service or a fee. This module creates a special, non-visible product for this purpose during installation.
  - **Effect of changing this setting:**
    - *When set to a valid Product ID:* The module will use this product to represent the fee in the cart, checkout, and order details. The product’s name will be replaced by the fee’s custom label, and its price will be overridden by the calculated fee.
    - *When set to an invalid or non-existent Product ID:* The module will not be able to add fees to the cart, as it won’t have a valid “placeholder” product to use.
  - **Recommended value:** Use the ID of the special “Conditional Order Fee” product created by the module during installation. You can find this ID by searching for “Conditional Order Fee” in your Products list (though it’s usually hidden from the front office). The module will often pre-fill this for you.
  - **Merchant scenario / example:** The module automatically creates a product named “Conditional Order Fee” (or similar) and sets its ID here. You should generally not change this unless you intentionally want to use a different product as the fee placeholder (which is not recommended for most users).

### 2.2 Dedicated Admin Screens & Controller Views

The module provides dedicated sections in your PrestaShop Back Office to manage your fee policies and review their application.

#### 2.2.1 Conditional Order Fees Dashboard (Back Office > Conditional Order Fees > Dashboard)

This screen provides an overview of your module’s activity, including a summary of applied fees and quick access to policy management.

- **Screen Name & Menu Location:** **Conditional Order Fees > Dashboard** (found under the main “Conditional Order Fees” menu item in the left sidebar).
- **Available Actions & Settings:**
  - **Summary Statistics:** View key metrics like total fees collected, number of orders with fees, and average fee per order. This helps you understand the impact of your fee policies.
  - **Recent Fees Applied:** A quick list of the most recent orders where a conditional fee was applied, including the order ID, customer, and fee amount.
  - **Quick Links:** Direct links to “Manage Policies” and “View Audit Log.”
- **Effect of changes:** This screen is primarily for monitoring and navigation. No direct changes are made here, but it reflects the impact of your fee policies.
- **Recommended workflow for daily store management:** Check this dashboard periodically to monitor the performance of your fee policies and ensure they are working as expected.

#### 2.2.2 Manage Fee Policies (Back Office > Conditional Order Fees > Policies)

This is where you define, edit, and manage all your conditional fee rules. Each “policy” is a set of conditions that, when met, will apply a specific fee.

- **Screen Name & Menu Location:** **Conditional Order Fees > Policies** (found under the main “Conditional Order Fees” menu item in the left sidebar).
- **Available Actions & Settings:**
  - **Policies List:** A table displaying all your existing fee policies, including their name, status (enabled/disabled), priority, and the fee amount/type.
  - **Add New Policy:** Click the “Add new policy” button to create a new fee rule.
    - **Policy Name:** A descriptive name for your internal reference (e.g., “Small Order Handling Fee,” “Fragile Packaging Surcharge”).
    - **Status:** Enable or disable the policy.
    - **Priority:** If multiple policies could apply to the same cart, the one with the highest priority (lowest number) will be evaluated first. If “Stop processing further rules” is enabled, only the highest priority matching rule will apply.
    - **Fee Type:**
      - **Fixed Amount:** A specific monetary value (e.g., $5.00).
      - **Percentage of Cart Total:** A percentage of the cart’s subtotal (e.g., 2%).
      - **Percentage of Products in Cart:** A percentage of the total price of products in the cart (excluding shipping/taxes).
    - **Fee Value:** The actual amount or percentage based on the selected fee type.
    - **Fee Label (Multi-language):** The text that customers will see in their cart and order summary (e.g., “Handling Fee,” “Service Charge”). This can be translated for different languages.
    - **Conditions Builder:** This is the core of the policy. You can build complex rules using “AND” / “OR” groups, combining conditions like:
      - Cart value (total, subtotal, quantity)
      - Customer group
      - Country, state, or zone
      - Carrier
      - Specific products in cart (by ID, category, manufacturer, supplier)
      - Payment method
      - And more…
    - **Stop processing further rules:** If enabled, once this policy applies, no other lower-priority policies will be evaluated for the same cart.
  - **Edit/Delete Policies:** Modify existing policies or remove them.
  - **Duplicate Policy:** Quickly create a new policy based on an existing one, saving time when creating similar rules.
- **Effect of changes:** Adding, editing, or deleting policies directly impacts which fees are applied to customer carts and under what circumstances. Incorrectly configured policies can lead to unexpected charges or missed revenue.
- **Recommended workflow for daily store management:**
  1. Start by defining your most common fee scenarios.
  2. Use the “Add new policy” button to create each rule.
  3. Carefully construct your conditions using the builder. Test thoroughly using the simulator (if available, see audit log) to ensure they work as expected.
  4. Set appropriate priorities, especially if you have overlapping conditions.
  5. Regularly review and update policies as your business needs or promotions change.

#### 2.2.3 Audit Log (Back Office > Conditional Order Fees > Audit Log)

The audit log provides a detailed history of every instance where the module evaluated a cart and applied (or didn’t apply) a fee. This is invaluable for troubleshooting and understanding why certain fees were or weren’t charged.

- **Screen Name & Menu Location:** **Conditional Order Fees > Audit Log** (found under the main “Conditional Order Fees” menu item in the left sidebar).
- **Available Actions & Settings:**
  - **Log Entries:** A table showing each evaluation event, including:
    - Date and time
    - Customer (if logged in)
    - Cart ID
    - Applied Policy (if any)
    - Fee Amount (if applied)
    - Status (e.g., “Fee Applied,” “No Fee Applied,” “Policy Not Met”)
  - **Detailed View:** Click on a log entry to see a full breakdown of how the conditions were evaluated for that specific cart, showing which conditions passed and which failed. This is like a “simulator” for past events.
  - **Filtering & Searching:** Filter log entries by date, customer, cart ID, or policy to quickly find specific events.
- **Effect of changes:** This screen is for review and debugging. No direct changes are made here, but it provides critical insights into the module’s behavior.
- **Recommended workflow for daily store management:**
  1. If a customer reports an unexpected fee or the absence of an expected fee, use the audit log to investigate.
  2. Filter by the customer’s name or cart ID to see exactly which policies were evaluated and why.
  3. Use the detailed view to pinpoint which specific condition caused a policy to pass or fail.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Enable Module | YES | Master switch to activate/deactivate all module functionality. |
|  | Fee Product ID | Auto-generated ID | Links fees to a hidden product for PrestaShop’s cart system. Do not change unless instructed. |
| **Policies** | Policy Name | N/A | Internal label for your fee rule. |
|  | Status | Enabled | Activates/deactivates an individual fee policy. |
|  | Priority | 1 (lowest number = highest priority) | Determines evaluation order if multiple policies could apply. |
|  | Fee Type | Fixed Amount | Choose how the fee is calculated (fixed, % of cart, % of products). |
|  | Fee Value | 0.00 | The amount or percentage of the fee. |
|  | Fee Label | “Handling Fee” (example) | Customer-facing text for the fee in cart/order. |
|  | Conditions Builder | N/A | Define the specific criteria (cart, customer, product, etc.) for the fee to apply. |
|  | Stop processing further rules | No | If enabled, prevents lower-priority policies from applying once this one matches. |
| **Audit Log** | (All entries) | N/A | Provides detailed history of fee evaluations for troubleshooting and monitoring. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve set up a policy, but the fee isn’t appearing in the cart.**
A1:

- **Check Module Status:** Ensure the “Enable Module” setting on the main configuration page is set to YES.
- **Check Policy Status:** Make sure the specific policy you expect to apply is “Enabled” in the Policies list.
- **Review Conditions:** Double-check your policy’s conditions. Are they all truly met by the current cart? Use the Audit Log (Conditional Order Fees > Audit Log) to see how your conditions were evaluated for a test cart.
- **Fee Product ID:** Verify that the “Fee Product ID” on the main configuration page is correct and points to the special product created by the module.
- **Cache:** Clear your PrestaShop cache (Advanced Parameters > Performance) and your browser cache.

**Q2: The fee is showing up, but the label or amount is wrong.**
A2:

- **Policy Settings:** Go to the specific policy in “Conditional Order Fees > Policies” and verify the “Fee Value” and “Fee Label” settings. Ensure the label is translated correctly for the language you are testing.
- **Multiple Policies:** If multiple policies could potentially apply, check their “Priority” and the “Stop processing further rules” setting. A higher priority policy might be applying instead of the one you expect.

**Q3: Can I translate the fee label for different languages?**
A3: Yes! When editing a policy, the “Fee Label” field will typically have a language selector (a flag icon). Click this to enter translations for each language installed in your store.

**Q4: What happens if I delete the “Fee Product” that the module uses?**
A4: If you delete the product specified in the “Fee Product ID” setting, the module will no longer be able to add fees to the cart. It’s crucial not to delete this product. If it’s accidentally deleted, you may need to reinstall the module (which will recreate it) or manually create a new hidden product and update the “Fee Product ID” setting.

**Q5: The module seems to be slowing down my checkout process.**
A5: While the module is optimized for performance, complex policies with many conditions, especially those involving extensive product checks, can add a slight overhead.

- **Simplify Conditions:** Review your policies. Can any conditions be simplified or combined?
- **Prioritize:** Use the “Priority” and “Stop processing further rules” settings effectively to minimize the number of policies that need full evaluation for a given cart.
- **Server Resources:** Ensure your hosting environment meets PrestaShop’s recommended specifications.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The Conditional Order Fees module is built following PrestaShop’s MVC pattern, heavily leveraging `ObjectModel` for data persistence and a robust event-driven architecture through PrestaShop hooks. It introduces a sophisticated condition evaluation engine, allowing for complex, nested `AND`/`OR` logic to determine fee applicability. The module integrates seamlessly into the cart and order processing flow by dynamically adding a “virtual product” to the cart when conditions are met. Admin interfaces are built using PrestaShop’s `AdminController` and `HelperList`/`HelperForm` components, with custom JavaScript for the condition builder and simulator.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `conorderfee/controllers/front/index.php`
  - **Class Name:** `ConorderfeeIndexModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** This controller likely serves as a fallback or a simple entry point, but the core logic for applying fees is primarily handled through hooks, not direct front-controller routes. It might be used for basic module information or redirection if accessed directly.

#### Back-Office Admin Controllers

- `conorderfee/controllers/admin/AdminconorderfeeAuditLog.php`
  - **Class Name:** `AdminconorderfeeAuditLogController` (extends `ModuleAdminController`)
  - **Tab Name:** Conditional Order Fees > Audit Log
  - **Managed Entity:** `ConorderfeeLog` (ORM for `ps_conorderfee_log` table).
  - **Responsibility:** Manages the display and filtering of the fee audit log. It uses `HelperList` to render the table of log entries and provides detailed views for individual log entries, showing the condition evaluation process.
- `conorderfee/controllers/admin/AdminconorderfeePolicies.php`
  - **Class Name:** `AdminconorderfeePoliciesController` (extends `ModuleAdminController`)
  - **Tab Name:** Conditional Order Fees > Policies
  - **Managed Entity:** `ConorderfeePolicy` (ORM for `ps_conorderfee_policy` table).
  - **Responsibility:** Manages the creation, editing, duplication, and deletion of fee policies. It uses `HelperList` for the policy overview and `HelperForm` for the policy creation/edit form, which includes the complex condition builder interface.
- `conorderfee/controllers/admin/index.php`
  - **Class Name:** `ConorderfeeIndexModuleAdminController` (extends `ModuleAdminController`)
  - **Tab Name:** Conditional Order Fees > Dashboard
  - **Managed Entity:** N/A (dashboard view)
  - **Responsibility:** Serves as the main dashboard for the module in the back office, displaying statistics and quick links. It’s the default controller loaded when clicking the main module menu item.

### 4.3 Core Classes & Models (`classes/`)

- `conorderfee/classes/ConorderfeeAdmin.php`
  - **Responsibility:** Utility class for admin-specific functionalities, potentially handling menu registration, tab management, and general admin-related helpers.
- `conorderfee/classes/ConorderfeeAuditLog.php`
  - **Database Table:** `ps_conorderfee_log`
  - **Extends ObjectModel:** Yes.
  - **`$definition` fields:** `id_conorderfee_log`, `id_cart`, `id_order`, `id_customer`, `id_conorderfee_policy`, `fee_amount`, `fee_label`, `conditions_snapshot`, `evaluation_result`, `date_add`.
  - **Key public methods:** Methods for saving log entries, retrieving log data, and potentially formatting log details for display.
- `conorderfee/classes/ConorderfeeCartState.php`
  - **Responsibility:** A helper class to encapsulate the current state of the cart and related context (customer, address, carrier, etc.) for condition evaluation. It provides methods to retrieve various cart properties needed by conditions.
- `conorderfee/classes/ConorderfeeCompatibility.php`
  - **Responsibility:** Handles compatibility layers for different PrestaShop versions (e.g., 1.7 vs. 8.x vs. 9.x) to ensure the module functions correctly across supported versions.
- `conorderfee/classes/ConorderfeeCondition.php`
  - **Database Table:** `ps_conorderfee_condition`
  - **Extends ObjectModel:** Yes.
  - **`$definition` fields:** `id_conorderfee_condition`, `id_conorderfee_condition_group`, `type`, `operator`, `value`, `is_inverted`.
  - **Key public methods:** Represents a single condition within a policy (e.g., “Cart Total > 100”). Methods for saving, loading, and potentially validating condition data.
- `conorderfee/classes/ConorderfeeConditionEvaluator.php`
  - **Responsibility:** The core logic engine for evaluating a `ConorderfeeConditionTree` against a `ConorderfeeCartState`. It recursively processes condition groups and individual conditions to determine if a policy applies.
- `conorderfee/classes/ConorderfeeConditionGroup.php`
  - **Database Table:** `ps_conorderfee_condition_group`
  - **Extends ObjectModel:** Yes.
  - **`$definition` fields:** `id_conorderfee_condition_group`, `id_conorderfee_policy`, `id_parent_group`, `operator` (`AND`/`OR`).
  - **Key public methods:** Represents a group of conditions (e.g., “Condition A AND (Condition B OR Condition C)”). Manages its child conditions and sub-groups.
- `conorderfee/classes/ConorderfeeConditionTree.php`
  - **Responsibility:** Represents the hierarchical structure of conditions for a policy (root group, sub-groups, individual conditions). Used by the `ConorderfeeConditionEvaluator`.
- `conorderfee/classes/ConorderfeeContext.php`
  - **Responsibility:** A wrapper around PrestaShop’s `Context` object, potentially adding module-specific context data or simplifying access to common context elements.
- `conorderfee/classes/ConorderfeeDashboard.php`
  - **Responsibility:** Provides data and logic for the module’s dashboard view, fetching statistics and recent log entries.
- `conorderfee/classes/ConorderfeeEngine.php`
  - **Responsibility:** The central orchestrator for the module’s front-office logic. It hooks into various PrestaShop events, retrieves active policies, uses the `ConorderfeeConditionEvaluator` to check conditions, and adds the fee product to the cart if applicable.
- `conorderfee/classes/ConorderfeeFeeProduct.php`
  - **Responsibility:** Manages the special “fee product” that represents the conditional charge in the cart. It handles its creation during installation and ensures it’s properly configured as a virtual, non-visible product.
- `conorderfee/classes/ConorderfeeListRenderer.php`
  - **Responsibility:** A helper class for rendering lists in the back office, potentially extending `HelperList` or providing custom column rendering logic.
- `conorderfee/classes/ConorderfeeLog.php`
  - **Database Table:** `ps_conorderfee_log` (same as `ConorderfeeAuditLog`, likely an alias or base class)
  - **Extends ObjectModel:** Yes.
  - **`$definition` fields:** Same as `ConorderfeeAuditLog`.
  - **Key public methods:** Methods for logging events, storing evaluation results, and retrieving log data.
- `conorderfee/classes/ConorderfeePolicy.php`
  - **Database Table:** `ps_conorderfee_policy`
  - **Extends ObjectModel:** Yes.
  - **`$definition` fields:** `id_conorderfee_policy`, `name`, `active`, `priority`, `fee_type`, `fee_value`, `fee_label`, `stop_further_rules`, `date_add`, `date_upd`.
  - **Key public methods:** Represents a complete fee policy. Methods for saving, loading, and managing its associated `ConorderfeeConditionGroup`s.
- `conorderfee/classes/ConorderfeePolicyDuplicator.php`
  - **Responsibility:** Handles the logic for duplicating an existing fee policy, including all its associated conditions and groups, to streamline policy creation.
- `conorderfee/classes/ConorderfeePreset.php`
  - **Responsibility:** Manages predefined condition types and operators for the condition builder (e.g., “Cart Total”, “Customer Group”, “is greater than”, “is one of”).
- `conorderfee/classes/ConorderfeeRule.php`
  - **Responsibility:** Likely an abstract or base class for defining rules, or a specific type of rule within the condition builder.
- `conorderfee/classes/ConorderfeeTreeRepository.php`
  - **Responsibility:** Manages the persistence and retrieval of the condition tree structure (policies, groups, conditions) from the database.
- `conorderfee/classes/index.php`
  - **Responsibility:** Empty file, typically used to prevent directory listing.

### 4.4 JavaScript Assets (`views/js/`)

- `conorderfee/lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Back-office.
  - **Description:** Provides autocomplete functionality for search inputs, likely used for selecting products, categories, customers, etc., within the condition builder.
- `conorderfee/lib/searchTool/views/views/js/autocomplete.js`
  - **Scope:** Back-office.
  - **Description:** Duplicate of the above, likely a pathing error or legacy file.
- `conorderfee/views/js/adminConditionBuilder.js`
  - **Scope:** Back-office (AdminconorderfeePoliciesController).
  - **Description:** The core JavaScript for the interactive condition builder interface. It handles adding/removing conditions and groups, managing `AND`/`OR` logic, dynamically loading condition types and operators, and updating the UI based on user input.
- `conorderfee/views/js/adminConorderfeeDashboard.js`
  - **Scope:** Back-office (AdminconorderfeeDashboardController).
  - **Description:** JavaScript for the dashboard, potentially handling AJAX updates for statistics, chart rendering, or interactive elements on the dashboard.
- `conorderfee/views/js/adminConorderfeeSearchTool.js`
  - **Scope:** Back-office.
  - **Description:** Integrates the autocomplete search tool (from `lib/searchTool`) into various admin forms, particularly for selecting entities in conditions.
- `conorderfee/views/js/adminConorderfeeSimulator.js`
  - **Scope:** Back-office (likely on the policy edit page or audit log).
  - **Description:** Provides a real-time or simulated condition evaluation tool in the back office, allowing administrators to test policies against hypothetical cart scenarios without placing a real order.
- `conorderfee/views/js/adminPolicyRules.js`
  - **Scope:** Back-office (AdminconorderfeePoliciesController).
  - **Description:** Handles general JavaScript interactions on the policy list and edit pages, such as enabling/disabling policies, handling duplication, and managing the overall policy form.
- `conorderfee/views/js/checkout.js`
  - **Scope:** Front-office.
  - **Description:** This script likely monitors changes in the cart during the checkout process (e.g., quantity updates, carrier selection) and triggers AJAX calls to re-evaluate fees, ensuring the cart total is always accurate. It might also update the display of the fee line item.

### 4.5 CSS Stylesheets (`views/css/`)

- `conorderfee/lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Back-office (Admin).
  - **Description:** Styles for the autocomplete search input fields and their dropdown suggestions.
- `conorderfee/lib/searchTool/views/views/css/autocomplete.css`
  - **Scope:** Back-office (Admin).
  - **Description:** Duplicate of the above, likely a pathing error or legacy file.
- `conorderfee/views/css/admin_conorderfee.css`
  - **Scope:** Back-office (Admin).
  - **Description:** General styling for the module’s back-office interfaces, including the dashboard, policy list, audit log, and especially the complex condition builder, ensuring a consistent and user-friendly layout.
- `conorderfee/views/css/front.css`
  - **Scope:** Front-office (Customer).
  - **Description:** Minimal styling for how the fee line item appears in the cart summary and checkout pages, ensuring it integrates visually with the store’s theme.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `conorderfee/views/templates/hook/admin_order.tpl`
  - **Hook:** `displayAdminOrder`
  - **Output:** Displays information about applied conditional fees within the PrestaShop Back Office order view, allowing administrators to see which policies were applied to a specific order.

#### Admin templates (`views/templates/admin/`)

- `conorderfee/lib/searchTool/views/scripts.tpl`
  - **Output:** Includes the necessary JavaScript and CSS for the search tool in the back office.
- `conorderfee/lib/searchTool/views/views/scripts.tpl`
  - **Output:** Duplicate of the above, likely a pathing error or legacy file.
- `conorderfee/views/templates/admin/auditPreview.tpl`
  - **Output:** Renders the detailed view of an individual audit log entry, showing the full condition evaluation process.
- `conorderfee/views/templates/admin/dashboard.tpl`
  - **Output:** The main dashboard view for the module, displaying statistics and quick links.
- `conorderfee/views/templates/admin/helpers/list/list_action_duplicate.tpl`
  - **Output:** Custom template for the “duplicate” action button in `HelperList` views, specifically for policies.
- `conorderfee/views/templates/admin/policiesPreview.tpl`
  - **Output:** Renders a preview or summary of a policy, potentially used within the audit log or a simulator.
- `conorderfee/views/templates/admin/policyConditionBuilder.tpl`
  - **Output:** The complex HTML structure for the interactive condition builder interface used when creating or editing a policy.
- `conorderfee/views/templates/admin/policyRuleCard.tpl`
  - **Output:** Renders a single rule or condition within the condition builder, typically a visual card or block.
- `conorderfee/views/templates/admin/policyRulesTable.tpl`
  - **Output:** Renders the table of policies on the `AdminconorderfeePolicies` list view.
- `conorderfee/views/templates/admin/scopeSelector.tpl`
  - **Output:** A template for selecting the scope of a condition (e.g., “Cart,” “Product,” “Customer”), used within the condition builder.

#### Front-office templates (`views/templates/front/`)

- `conorderfee/controllers/front/index.php` (No specific .tpl file listed, likely handles output directly or redirects)

### 4.7 Database Schema & Hooks Map

#### Database Tables

- `ps_conorderfee_policy`: Stores the main fee policy definitions (name, active status, fee type, value, label, priority).
- `ps_conorderfee_condition_group`: Stores the hierarchical structure of condition groups (AND/OR logic) within each policy.
- `ps_conorderfee_condition`: Stores individual conditions (type, operator, value) linked to condition groups.
- `ps_conorderfee_log`: Stores an audit trail of every time a fee was evaluated, including cart details, policy applied, fee amount, and a snapshot of the evaluation result.
- `ps_configuration`: Stores module-specific configuration values like `CONORDERFEE_ENABLED` and `CONORDERFEE_FEE_PRODUCT_ID`.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Not explicitly listed in module info, but often used to load front-office CSS/JS. |
| `displayBeforeCarrier` | Before the carrier selection on the checkout page. | Potentially used to re-evaluate fees if carrier selection impacts conditions. |
| `actionObjectProductInCartDeleteBefore` | Before a product is removed from the cart. | Re-evaluate fees to adjust if the removed product was part of a condition. |
| `actionPresentCart` | When the cart data is presented to the front office. | **CRITICAL:** Main hook for injecting the fee line item into the cart summary. |
| `actionAdminControllerSetMedia` | When an admin controller is loaded, before its content. | Loads back-office CSS and JavaScript for the module’s admin interfaces. |
| `actionPresentProductListing` | When product listings are presented. | Not directly related to fees, but might be used for product-specific fee indicators. |
| `actionValidateOrderBefore` | Just before an order is validated. | Final check and application of fees to ensure the order total is correct. |
| `actionGetProductPropertiesAfter` | After product properties are retrieved. | Potentially used to identify specific products that trigger fees. |
| `displayAdminOrder` | In the Back Office order detail page. | Displays information about applied fees for a specific order. |
| `actionFrontControllerInitAfter` | After a front controller is initialized. | General front-office initialization, potentially setting up context for fee evaluation. |
| `actionPresentProduct` | When a single product is presented. | Similar to `actionPresentProductListing`. |
| `actionPresentCartProduct` | When a product in the cart is presented. | Allows modification of cart product data, potentially for fee-related display. |
| `actionProductPriceCalculation` | During product price calculation. | Ensures the fee product’s price is correctly overridden by the calculated fee. |
| `actionFrontControllerSetVariables` | Before Smarty variables are assigned in a front controller. | Passes fee-related data to front-office templates. |
| `actionCartSave` | After a cart is saved (e.g., quantity change, product add/remove). | **CRITICAL:** Triggers the main fee evaluation logic whenever the cart content changes. |
| `actionValidateOrder` | After an order has been successfully validated. | Logs the final fee application and associates it with the new order ID. |

## 5. Official Support & Updates

For official updates, bug fixes, and dedicated developer support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Ensure you always download the latest version compatible with your PrestaShop installation.
