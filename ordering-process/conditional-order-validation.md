---
title: "Conditional Order Validation - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Conditional Order Validation PrestaShop module by MyPresta.eu."
sidebar:
  label: "Conditional Order Validation - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Conditional Order Validation Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/conditional-order-validation.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/conditional-order-validation/)
>
> ---


# Conditional Order Validation

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Conditional Order Validation)

This is the main entry point for global module settings.

- **Menu Location:** Back Office > Modules > Module Manager > Conditional Order Validation > Configure

#### 2.1.1 General Settings

| Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- |
| **Enable Conditional Order Validation** | YES | **What this setting does:** This is the master switch for the entire module. If disabled, none of your defined policies will be active, and customers will be able to check out without any restrictions from this module.   **Effect of changing this setting:**   *When enabled:* The module will start evaluating all active policies you’ve created. If a cart violates a policy, the customer will see warnings or be blocked from checkout as per your policy settings.   *When disabled:* The module becomes inactive. No policies are checked, and no messages are displayed.   **Recommended value:** YES (once you’ve configured your policies).   **Merchant scenario:** Enable this after you’ve set up your first few policies and tested them using the simulator. |
| **Display Validation Messages On** | Cart & Checkout | **What this setting does:** Controls where the module’s warning or blocking messages are shown to the customer.   **Effect of changing this setting:**   *When set to “Cart & Checkout”:* Messages will appear on both the shopping cart page and during the various steps of the checkout process. This provides maximum visibility and early feedback to the customer.   *When set to “Cart Only”:* Messages will only appear on the shopping cart page. Customers might proceed further into checkout before being blocked if they ignore the cart warning.   *When set to “Checkout Only”:* Messages will only appear during the checkout process. Customers won’t see warnings on the cart page, potentially leading to frustration later in the process.   **Recommended value:** Cart & Checkout.   **Merchant scenario:** For best customer experience, show messages early and often (Cart & Checkout) so customers can fix their cart before investing time in the checkout process. |
| **Allow Checkout with Warnings** | NO | **What this setting does:** Determines if customers can proceed to checkout even if their cart triggers a “warning” policy (as opposed to a “blocking” policy).   **Effect of changing this setting:**   *When enabled (YES):* If a policy is set to “Warning,” the customer will see the warning message but will still be able to click the “Proceed to checkout” or “Place order” button. This is useful for soft recommendations or non-critical issues.   *When disabled (NO):* If a policy is set to “Warning,” the customer will see the warning message, and the “Proceed to checkout” or “Place order” button will be disabled until the warning condition is resolved. This effectively makes “warnings” behave like “blocks” at the checkout stage.   **Recommended value:** NO (unless you have very specific “soft” warnings).   **Merchant scenario:** If you have a policy like “Customers buying over $100 get free shipping,” and you want to *suggest* they add more to their cart but not *force* it, you might enable this. However, for most business rules, you’ll want to disable it to ensure compliance. |

### 2.2 Dedicated Admin Screens & Controller Views

The module introduces two powerful new sections in your PrestaShop Back Office menu: “Policies” and “Audit Log”.

#### 2.2.1 Policies (Back Office > Conditional Order Validation > Policies)

This is where you define, manage, and activate your conditional order validation rules. Each “policy” is a set of conditions that, if met, will either block or warn the customer.

- **Menu Location:** Back Office > Conditional Order Validation > Policies
- **Available Actions & Settings:**

  - **Policy List:** A table displaying all your created policies, showing their name, status (enabled/disabled), type (blocking/warning), and priority.
  - **Add New Policy:** Click this button to create a new validation policy.
  - **Edit Policy:** Modify an existing policy’s name, conditions, messages, and status.
  - **Duplicate Policy:** Quickly create a copy of an existing policy to use as a starting point for a new one. This saves time when creating similar rules.
  - **Enable/Disable Policy:** Toggle a policy’s active status without deleting it.
  - **Delete Policy:** Remove a policy permanently.
  - **Simulator:** A crucial tool (often found on the policy creation/edit screen or as a dedicated tab) that allows you to test your policies with a simulated cart before they go live. This helps prevent unintended blocking of legitimate orders.
- **Policy Creation/Edit Form:**

  - **Policy Name:** A descriptive name for your policy (e.g., “Minimum Order Value for Wholesale,” “Age Restriction for Alcohol”).
  - **Status:** Enable or Disable the policy.
  - **Policy Type:**
    - **Blocking:** If the conditions are met, the customer is *prevented* from checking out.
    - **Warning:** If the conditions are met, the customer sees a warning message but *may or may not* be able to proceed, depending on the global “Allow Checkout with Warnings” setting.
  - **Priority:** If multiple policies are active and triggered, this determines the order in which messages are displayed or which policy takes precedence (lower number = higher priority).
  - **Conditions Builder:** This is the core of the policy. You’ll build a tree of conditions using “AND” / “OR” logic.
    - **Condition Types:** You can typically choose from a wide range of conditions:
      - **Cart-level:** Total cart value, total quantity of items, number of unique products.
      - **Product-level:** Specific product IDs, categories, manufacturers, suppliers, product attributes, minimum/maximum quantity of a specific product.
      - **Customer-level:** Customer group, specific customer ID, customer’s country.
      - **Shipping-level:** Selected carrier, shipping zone.
    - **Operators:** (e.g., “is equal to,” “is greater than,” “contains,” “is not”).
    - **Values:** The specific data point to compare against (e.g., “100” for a minimum value, “Electronics” for a category).
  - **Customer Message:** The message displayed to the customer in the front office when this policy is triggered. Make it clear, helpful, and actionable (e.g., “Your cart must contain at least 5 units of product X to proceed.”).
  - **Admin Message (Optional):** An internal note for yourself or other administrators.
- **Effect of changes:**

  - Adding/modifying a policy directly impacts the front-office checkout experience for customers.
  - Enabling a policy activates its rules. Disabling it deactivates them without deletion.
  - The simulator allows you to test changes without affecting live customers.
- **Recommended workflow for daily store management:**

  1. Identify a business rule you want to enforce (e.g., “Wholesale customers must order a minimum of $500”).
  2. Go to “Policies” and click “Add New Policy.”
  3. Give it a clear name, set it to “Blocking,” and define the conditions (e.g., “Customer Group IS Wholesale” AND “Cart Total IS GREATER THAN OR EQUAL TO 500”).
  4. Write a helpful customer message (e.g., “Wholesale orders require a minimum total of $500. Please add more items to your cart.”).
  5. Use the “Simulator” to test various scenarios (e.g., a wholesale customer with a $400 cart, a retail customer with a $400 cart, a wholesale customer with a $600 cart).
  6. Once satisfied, enable the policy.

#### 2.2.2 Audit Log (Back Office > Conditional Order Validation > Audit Log)

The Audit Log provides a historical record of when policies were triggered, by whom, and what the outcome was. This is invaluable for troubleshooting and understanding customer behavior.

- **Menu Location:** Back Office > Conditional Order Validation > Audit Log
- **Available Actions & Settings:**

  - **Log List:** A table showing entries for each time a policy was evaluated and triggered.
  - **Columns:**
    - **Date/Time:** When the event occurred.
    - **Customer:** The customer who triggered the policy (if logged in).
    - **Cart ID:** The ID of the shopping cart involved.
    - **Policy Name:** The name of the policy that was triggered.
    - **Policy Type:** Whether it was a “Blocking” or “Warning” policy.
    - **Message:** The message displayed to the customer.
    - **Status:** Whether the order was ultimately validated, blocked, or warned.
  - **Filtering/Searching:** Standard PrestaShop list filtering allows you to search by customer, policy, date range, etc.
  - **View Cart Details:** Often, you can click on a cart ID to inspect the cart’s contents at the time the policy was triggered.
- **Effect of changes:** This screen is for viewing and auditing only; you cannot make changes here. It’s a record of events.
- **Recommended workflow for daily store management:**

  - If a customer reports an issue with checkout, check the Audit Log to see if any policies were triggered for their cart. This can quickly identify if a policy is misconfigured or if the customer simply didn’t meet the requirements.
  - Periodically review the log to understand which policies are most frequently triggered and if any adjustments are needed.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|
| **Module Configuration** | Enable Conditional Order Validation | YES | Master switch for the module’s functionality. |
| **Module Configuration** | Display Validation Messages On | Cart & Checkout | Where customer messages appear (cart, checkout, or both). |
| **Module Configuration** | Allow Checkout with Warnings | NO | Determines if “warning” policies block checkout or merely inform. |
| **Policies (Admin)** | Policy Name | N/A | Descriptive identifier for your rule. |
| **Policies (Admin)** | Status | Enabled | Activates or deactivates a specific policy. |
| **Policies (Admin)** | Policy Type | Blocking / Warning | Defines if the policy prevents checkout or just displays a message. |
| **Policies (Admin)** | Priority | N/A | Order of evaluation/display for multiple triggered policies. |
| **Policies (Admin)** | Conditions Builder | N/A | Defines the logical rules for when the policy is triggered. |
| **Policies (Admin)** | Customer Message | N/A | The message shown to the customer when the policy is triggered. |
| **Policies (Admin)** | Admin Message | N/A | Internal notes for administrators. |
| **Audit Log (Admin)** | (All Columns) | N/A | Records all instances of policies being triggered for review. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My policies aren’t working, or customers are still checking out when they shouldn’t be.**
A:

1. **Is the module enabled?** Check “Enable Conditional Order Validation” in the main module configuration.
2. **Are the specific policies enabled?** Go to “Policies” and ensure the “Status” column for your policies is set to “Enabled.”
3. **Check Policy Type:** Is it set to “Blocking” or “Warning”? If “Warning,” check the global “Allow Checkout with Warnings” setting. If that’s enabled, customers can bypass warnings.
4. **Clear Cache:** Sometimes PrestaShop’s cache can prevent changes from taking effect immediately. Go to **Advanced Parameters > Performance** and click “Clear cache.”
5. **Simulator:** Use the built-in “Simulator” on the policy creation/edit screen to test your conditions with various cart scenarios. This is the most effective way to debug.
6. **Audit Log:** Check the “Audit Log” to see if your policies are being triggered at all and what the outcome was.

**Q: The warning/blocking messages don’t look good on my theme.**
A: The module uses standard PrestaShop styling where possible, but custom themes might override or require specific CSS adjustments.

1. **Basic CSS:** The module’s CSS is designed to be generic. If your theme has very specific styling, you might need a webmaster to add custom CSS to your theme’s `custom.css` file to match your brand.
2. **Template Overrides:** Advanced users can override the module’s template files (e.g., `views/templates/hook/validation_banner.tpl`) in their theme to completely customize the HTML structure and appearance.

**Q: Can I translate the messages for different languages?**
A: Yes, all customer-facing messages you define in your policies are translatable.

1. Go to **International > Translations** in your Back Office.
2. Select “Installed modules translations,” choose your theme, and select the language.
3. Find the “Conditional Order Validation” module and translate the policy messages there.

**Q: I’ve created a policy, but it’s blocking *all* orders, even valid ones.**
A: This usually means your conditions are too broad or incorrectly configured.

1. **Review Conditions:** Carefully re-read each condition in your policy. Ensure the operators (e.g., “IS,” “IS NOT,” “GREATER THAN”) and values are correct.
2. **AND/OR Logic:** Pay close attention to whether you’re using “AND” or “OR” between condition groups. “AND” means *all* conditions must be true; “OR” means *any* one condition must be true. A common mistake is using “OR” when “AND” is intended, or vice-versa.
3. **Use the Simulator:** This is critical. Simulate various “good” and “bad” carts to see exactly why the policy is triggering.

**Q: How do I handle multi-store setups?**
A: The module is designed to be multi-store compatible. When creating or editing policies, you should see an option to select which stores the policy applies to. Ensure your policies are assigned to the correct store contexts.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the Conditional Order Validation module for developers and webmasters.

### 4.1 Architecture Overview

The Conditional Order Validation module follows a robust MVC (Model-View-Controller) pattern within the PrestaShop framework. It heavily leverages `ObjectModel` for data persistence (policies, audit logs), custom admin controllers for managing these entities, and a sophisticated condition evaluation engine to process rules in real-time. The module integrates deeply into the order validation and cart presentation hooks, ensuring policies are enforced at critical stages of the customer journey. A key aspect is the `ConordervalidEngine` which orchestrates the evaluation of `ConordervalidPolicy` objects, each containing a `ConordervalidConditionTree`.

### 4.2 Controllers (`controllers/`)

#### 4.2.1 Front-Office Controllers

- `conordervalid/controllers/front/index.php`
  - **Class Name:** `ConordervalidIndexModuleFrontController` (likely extends `ModuleFrontController`)
  - **Responsibility:** This controller might serve as a general entry point or handle specific front-office AJAX requests related to cart validation or displaying messages. Given its name, it could be a fallback or a simple display controller.
- `conordervalid/controllers/front/validate.php`
  - **Class Name:** `ConordervalidValidateModuleFrontController` (likely extends `ModuleFrontController`)
  - **Responsibility:** This controller is crucial for real-time cart validation. It likely handles AJAX requests from the cart or checkout pages to check if the current cart state violates any active policies. It would return JSON responses indicating whether the cart is valid, any warning messages, or blocking reasons. This is where the `ConordervalidEngine` would be invoked.

#### 4.2.2 Back-Office Admin Controllers

- `conordervalid/controllers/admin/AdminconordervalidAuditLog.php`
  - **Class Name:** `AdminconordervalidAuditLogController` (extends `ModuleAdminController`)
  - **Tab Name:** Audit Log (under Conditional Order Validation menu)
  - **Managed Entity:** `ConordervalidAuditLog` (mapped to `ps_conordervalid_log` table)
  - **Responsibility:** Manages the display and filtering of the audit log entries. It uses `HelperList` for rendering the grid, allowing administrators to view historical records of policy triggers.
- `conordervalid/controllers/admin/AdminconordervalidPolicies.php`
  - **Class Name:** `AdminconordervalidPoliciesController` (extends `ModuleAdminController`)
  - **Tab Name:** Policies (under Conditional Order Validation menu)
  - **Managed Entity:** `ConordervalidPolicy` (mapped to `ps_conordervalid_policy` table)
  - **Responsibility:** This is the primary controller for managing validation policies. It handles the CRUD operations for policies, including the complex condition builder interface. It uses `HelperList` for the policy overview and `HelperForm` for policy creation/editing, integrating the `ConordervalidConditionTree` and `ConordervalidConditionBuilder` logic.
- `conordervalid/controllers/admin/index.php`
  - **Class Name:** (Likely a simple redirect or placeholder)
  - **Responsibility:** Often, `index.php` in a controller directory is a security measure to prevent direct directory listing or a simple redirect to the main module configuration or dashboard.

### 4.3 Core Classes & Models (`classes/`)

- `conordervalid/classes/ConordervalidAdmin.php`
  - **Responsibility:** Likely contains helper methods or utilities specifically for the admin interface, such as menu registration, tab management, or common form rendering logic.
- `conordervalid/classes/ConordervalidAuditLog.php`
  - **Extends:** `ObjectModel`
  - **Database Table:** `ps_conordervalid_log`
  - **`$definition` fields:** `id_conordervalid_log`, `id_cart`, `id_customer`, `id_policy`, `policy_name`, `policy_type`, `message`, `date_add`.
  - **Responsibility:** Represents a single entry in the audit log, storing details about a triggered policy.
- `conordervalid/classes/ConordervalidCartState.php`
  - **Responsibility:** A utility class to encapsulate the current state of a customer’s cart (products, quantities, total, customer info, selected carrier, etc.). This object is passed to the `ConordervalidConditionEvaluator`.
- `conordervalid/classes/ConordervalidCompatibility.php`
  - **Responsibility:** Handles compatibility layers for different PrestaShop versions (e.g., differences in hook names, class structures, or API calls between PS 1.7, 8.x, and 9.x).
- `conordervalid/classes/ConordervalidCondition.php`
  - **Extends:** (Likely a base class or `ObjectModel` if conditions are stored individually)
  - **Responsibility:** Represents a single condition within a policy (e.g., “Cart Total > 100”). It defines the condition type, operator, and value.
- `conordervalid/classes/ConordervalidConditionEvaluator.php`
  - **Responsibility:** The core logic for evaluating a `ConordervalidCondition` or `ConordervalidConditionGroup` against a `ConordervalidCartState` object. It contains methods for comparing different data types and applying operators.
- `conordervalid/classes/ConordervalidConditionGroup.php`
  - **Extends:** (Likely a base class)
  - **Responsibility:** Represents a logical grouping of conditions (e.g., “Condition A AND (Condition B OR Condition C)”). Manages the `AND`/`OR` logic.
- `conordervalid/classes/ConordervalidConditionTree.php`
  - **Extends:** (Likely a base class or `ObjectModel`)
  - **Responsibility:** Represents the entire hierarchical structure of conditions for a policy. It’s a tree-like data structure composed of `ConordervalidConditionGroup` and `ConordervalidCondition` objects.
- `conordervalid/classes/ConordervalidContext.php`
  - **Responsibility:** A wrapper or extension of PrestaShop’s `Context` class, potentially adding module-specific context data or helper methods.
- `conordervalid/classes/ConordervalidDashboard.php`
  - **Responsibility:** Likely provides data and logic for a potential module dashboard in the Back Office, summarizing policy performance or audit log statistics.
- `conordervalid/classes/ConordervalidEngine.php`
  - **Responsibility:** The central orchestrator. It fetches active `ConordervalidPolicy` objects, iterates through them, and uses `ConordervalidConditionEvaluator` to check if a given cart violates any policy. It determines the final outcome (blocked, warned, valid) and collects messages.
- `conordervalid/classes/ConordervalidListRenderer.php`
  - **Responsibility:** A utility class for rendering lists or tables in the Back Office, potentially customizing `HelperList` behavior or providing specific column formatting.
- `conordervalid/classes/ConordervalidLog.php`
  - **Extends:** `ObjectModel` (likely an alias or older version of `ConordervalidAuditLog`)
  - **Database Table:** `ps_conordervalid_log`
  - **`$definition` fields:** Similar to `ConordervalidAuditLog`.
  - **Responsibility:** Stores audit log entries.
- `conordervalid/classes/ConordervalidPolicy.php`
  - **Extends:** `ObjectModel`
  - **Database Table:** `ps_conordervalid_policy`
  - **`$definition` fields:** `id_conordervalid_policy`, `name`, `active`, `type` (blocking/warning), `priority`, `conditions_json` (stores the `ConordervalidConditionTree` as JSON), `customer_message`, `admin_message`, `date_add`, `date_upd`.
  - **Responsibility:** Represents a single validation policy, including its conditions, messages, and settings.
- `conordervalid/classes/ConordervalidPolicyDuplicator.php`
  - **Responsibility:** Handles the logic for duplicating `ConordervalidPolicy` objects, ensuring all associated conditions and settings are correctly copied.
- `conordervalid/classes/ConordervalidPreset.php`
  - **Responsibility:** Likely defines predefined sets of conditions or policy templates that can be quickly loaded by administrators.
- `conordervalid/classes/ConordervalidRule.php`
  - **Extends:** (Likely a base class or `ObjectModel`)
  - **Responsibility:** Could be an alias for `ConordervalidCondition` or a higher-level abstraction for a single rule within a policy.
- `conordervalid/classes/ConordervalidTreeRepository.php`
  - **Responsibility:** Manages the storage and retrieval of `ConordervalidConditionTree` objects, likely serializing/deserializing them to/from the `conditions_json` field in `ConordervalidPolicy`.
- `conordervalid/classes/index.php`
  - **Responsibility:** Standard security measure to prevent directory listing.

### 4.4 JavaScript Assets (`views/js/`)

- `conordervalid/lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Back-office (admin forms)
  - **Responsibility:** Provides autocomplete functionality for input fields in the admin, likely used when selecting products, categories, customers, etc., within the condition builder.
- `conordervalid/lib/searchTool/views/views/js/autocomplete.js`
  - **Scope:** Back-office (admin forms)
  - **Responsibility:** Duplicate of the above, likely an error in packaging or a legacy path.
- `conordervalid/views/js/adminConditionBuilder.js`
  - **Scope:** Back-office (AdminconordervalidPoliciesController)
  - **Responsibility:** Powers the interactive condition building interface in the policy creation/edit form. Handles adding/removing conditions, managing AND/OR logic, and updating the underlying JSON structure of the condition tree.
- `conordervalid/views/js/adminConordervalidDashboard.js`
  - **Scope:** Back-office (Admin Dashboard, if implemented)
  - **Responsibility:** Provides dynamic functionality for a potential module dashboard, such as chart rendering, data filtering, or AJAX updates.
- `conordervalid/views/js/adminConordervalidSearchTool.js`
  - **Scope:** Back-office (admin forms)
  - **Responsibility:** Integrates the search tool (e.g., for products, categories) into various admin forms, likely used by the condition builder.
- `conordervalid/views/js/adminConordervalidSimulator.js`
  - **Scope:** Back-office (AdminconordervalidPoliciesController)
  - **Responsibility:** Handles the logic for the policy simulator. It captures simulated cart data, sends it via AJAX to a front controller (e.g., `validate.php`), and displays the validation results.
- `conordervalid/views/js/adminPolicyRules.js`
  - **Scope:** Back-office (AdminconordervalidPoliciesController)
  - **Responsibility:** Contains specific JS logic for managing the display and interaction of policy rules within the admin interface, potentially related to drag-and-drop reordering or quick edits.
- `conordervalid/views/js/validation.js`
  - **Scope:** Front-office (Cart, Checkout pages)
  - **Responsibility:** This is the primary front-office JS. It listens for cart changes (e.g., quantity update, product removal), triggers AJAX calls to the `validate.php` front controller, and then dynamically updates the UI to display warning/blocking messages or enable/disable checkout buttons based on the response. It likely uses `prestashop.on` for event binding.

### 4.5 CSS Stylesheets (`views/css/`)

- `conordervalid/lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Back-office (admin forms)
  - **Main UI components:** Styles for the autocomplete dropdowns and input fields used in the admin search tool.
  - **Key selectors:** `.autocomplete-suggestions`, `.autocomplete-selected`, `.autocomplete-suggestion`.
- `conordervalid/lib/searchTool/views/views/css/autocomplete.css`
  - **Scope:** Back-office (admin forms)
  - **Main UI components:** Duplicate of the above.
  - **Key selectors:** Same as above.
- `conordervalid/views/css/admin_conordervalid.css`
  - **Scope:** Back-office (admin forms and lists)
  - **Main UI components:** Styles for the policy list, policy creation/edit form, condition builder, and audit log.
  - **Key selectors:** `.conordervalid-policy-card`, `.conordervalid-condition-group`, `.conordervalid-condition-row`, `.conordervalid-simulator-results`.
- `conordervalid/views/css/front.css`
  - **Scope:** Front-office (Cart, Checkout pages)
  - **Main UI components:** Styles for the warning/blocking banners and messages displayed to customers.
  - **Key selectors:** `.conordervalid-validation-banner`, `.conordervalid-warning`, `.conordervalid-blocking`, `.conordervalid-message-list`.

### 4.6 Smarty Template Structure (`views/templates/`)

#### 4.6.1 Hook templates (`views/templates/hook/`)

- `conordervalid/views/templates/hook/admin_order.tpl`
  - **Hook:** `DisplayAdminOrder`
  - **Outputs:** A block within the Back Office order view, potentially showing which policies were triggered for a specific order or cart.
- `conordervalid/views/templates/hook/validation_banner.tpl`
  - **Hook:** `DisplayPaymentTop`, `DisplayShoppingCartFooter`, `DisplayCheckoutSummaryTop`
  - **Outputs:** The HTML structure for the front-office warning/blocking messages displayed to the customer. This template receives variables like `$validation_messages`, `$is_blocked`, etc.

#### 4.6.2 Admin templates (`views/templates/admin/`)

- `conordervalid/lib/searchTool/views/scripts.tpl`
  - **Outputs:** Smarty template for including JS/CSS assets related to the search tool in the admin.
- `conordervalid/lib/searchTool/views/views/scripts.tpl`
  - **Outputs:** Duplicate of the above.
- `conordervalid/views/templates/admin/auditPreview.tpl`
  - **Outputs:** A partial template for displaying a preview or summary of audit log entries, possibly used within a dashboard or a specific view.
- `conordervalid/views/templates/admin/dashboard.tpl`
  - **Outputs:** The main template for a potential module dashboard in the Back Office, displaying statistics, recent logs, or policy summaries.
- `conordervalid/views/templates/admin/helpers/list/list_action_duplicate.tpl`
  - **Outputs:** Custom action button for duplicating policies within the `HelperList` view for `AdminconordervalidPoliciesController`.
- `conordervalid/views/templates/admin/policiesPreview.tpl`
  - **Outputs:** A partial template for displaying a preview or summary of policies, similar to `auditPreview.tpl`.
- `conordervalid/views/templates/admin/policyConditionBuilder.tpl`
  - **Outputs:** The complex HTML structure for the interactive condition builder interface used when creating or editing a policy. This template works closely with `adminConditionBuilder.js`.
- `conordervalid/views/templates/admin/policyRuleCard.tpl`
  - **Outputs:** A smaller, reusable template for displaying a single rule or condition within the condition builder.
- `conordervalid/views/templates/admin/policyRulesTable.tpl`
  - **Outputs:** A table-like structure for displaying a list of rules, possibly used in the policy overview or simulator.
- `conordervalid/views/templates/admin/scopeSelector.tpl`
  - **Outputs:** Template for selecting the scope of a policy (e.g., specific shops in a multi-store environment).

#### 4.6.3 Front-office templates (`views/templates/front/`)

- (No dedicated standalone front-office templates identified, as front-office display is handled via hook templates like `validation_banner.tpl`.)

### 4.7 Database Schema & Hooks Map

#### 4.7.1 Database Tables

- `ps_conordervalid_policy`
  - **Purpose:** Stores the definition of each validation policy.
  - **Key Fields:** `id_conordervalid_policy` (PK), `name`, `active` (boolean), `type` (enum: ‘blocking’, ‘warning’), `priority`, `conditions_json` (TEXT, stores serialized `ConordervalidConditionTree`), `customer_message` (TEXT), `admin_message` (TEXT), `date_add`, `date_upd`.
- `ps_conordervalid_log`
  - **Purpose:** Stores audit trail entries for triggered policies.
  - **Key Fields:** `id_conordervalid_log` (PK), `id_cart`, `id_customer`, `id_policy`, `policy_name`, `policy_type`, `message`, `date_add`.
- `ps_configuration`
  - **Purpose:** Stores global module settings.
  - **Key Fields:** `CONORDERVALID_DISPLAY_SURFACES` (e.g., ‘cart,checkout’), `CONORDERVALID_ENABLED` (boolean), `CONORDERVALID_ALLOW_WARN_CHECKOUT` (boolean).

#### 4.7.2 Registered Hooks Table

| Hook Name | Execution Timing & Context | Technical Purpose |
| --- | --- | --- |
| `DisplayHeader` | Renders in the `<head>` section of all front-office pages. | Injects front-office CSS (`front.css`) and JS (`validation.js`) assets. |
| `ActionFrontControllerInitAfter` | After a front controller has been initialized. | Potentially used to initialize module context, load policies, or perform early validation checks. |
| `ActionObjectProductInCartDeleteBefore` | Before a product is removed from the cart. | Could be used to log the cart state before a change, or to prevent deletion if it violates a policy. |
| `ActionObjectProductInCartDeleteAfter` | After a product has been removed from the cart. | Re-evaluate cart policies after a product removal, trigger AJAX update. |
| `ActionCartSave` | After a cart has been saved (e.g., quantity update, product add/remove). | Triggers re-evaluation of all active policies against the updated cart. |
| `actionPresentCart` | When the cart is being prepared for display (e.g., on the cart page). | Injects validation messages into the cart page template. |
| `DisplayShoppingCartFooter` | At the bottom of the shopping cart page. | Renders the `validation_banner.tpl` with any warning/blocking messages. |
| `DisplayPaymentTop` | At the top of the payment selection section during checkout. | Renders the `validation_banner.tpl` with any warning/blocking messages, potentially disabling payment options. |
| `DisplayCheckoutSummaryTop` | At the top of the checkout summary page (before final order confirmation). | Renders the `validation_banner.tpl` with any warning/blocking messages, potentially disabling the order confirmation button. |
| `ActionFilterPaymentOptions` | Filters available payment options during checkout. | Can be used to hide or disable payment methods if a policy is violated (e.g., “COD not allowed for orders over $X”). |
| `ActionValidateOrderBefore` | Just before an order is officially validated. | The final critical check to block an order if any blocking policies are violated. Logs the attempt. |
| `ActionValidateOrder` | After an order has been successfully validated and created. | Logs the successful order validation, potentially records which policies were *not* violated. |
| `DisplayAdminOrder` | Renders a block within the Back Office order detail page. | Displays information about policies that were triggered (or passed) for the specific order, using `admin_order.tpl`. |
| `ActionAdminControllerSetMedia` | When an admin controller is setting its media (JS/CSS). | Injects Back Office specific JS (`adminConditionBuilder.js`, `adminConordervalidSimulator.js`) and CSS (`admin_conordervalid.css`) for policy management. |
| `DisplayReassurance` | Often used for displaying trust elements (e.g., secure payment icons). | Could potentially be used to display a small, persistent warning or status if a cart is invalid. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the Conditional Order Validation module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and configuration.
