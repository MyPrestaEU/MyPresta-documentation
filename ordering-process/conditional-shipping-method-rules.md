---
title: "Conditional Shipping Method Rules - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Conditional Shipping Method Rules PrestaShop module by MyPresta.eu."
sidebar:
  label: "Conditional Shipping Method Rules"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Conditional Shipping Method Rules Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/conditional-shipping-method-rules.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/conditional-shipping-method-rules/)
>
> ---


# Conditional Shipping Method Rules

## 1. Requirements & Compatibility

-   **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
-   **PHP Compatibility**: PHP 7.1 - 8.5
-   **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required, which are typically available on most modern PrestaShop hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)
You can access this screen by navigating to **Modules > Module Manager**, searching for "Conditional Shipping Method Rules", and clicking "Configure".

This page provides general settings for the module's behavior.

-   **Enable Module:**
    -   **What this setting does:** This is the master switch to turn the entire module's functionality on or off.
    -   **Effect of changing this setting:**
        -   *When enabled:* All your defined shipping rules will be active and influence the shipping methods displayed at checkout.
        -   *When disabled:* The module will be inactive, and PrestaShop's default shipping method selection will apply, ignoring all your custom rules.
    -   **Recommended value:** YES
    -   **Merchant scenario / example:** You might disable it temporarily during maintenance or if you need to revert to default shipping behavior quickly. For normal operation, keep it enabled.

-   **Merge Strategy for Multiple Rules:**
    -   **What this setting does:** Determines how the module combines the outcomes of multiple active rules when they apply to the same shipping method.
    -   **Effect of changing this setting:**
        -   *Option A (Prioritize "SHOW"):* If *any* active rule says "SHOW" a carrier, it will be shown, even if other rules say "HIDE" it. This is a more permissive strategy.
        -   *Option B (Prioritize "HIDE"):* If *any* active rule says "HIDE" a carrier, it will be hidden, even if other rules say "SHOW" it. This is a more restrictive strategy.
        -   *Option C (Custom Merge Strategy 1):* [Detailed explanation of specific logic, e.g., "Only show if ALL applicable rules say SHOW"]
        -   *Option D (Custom Merge Strategy 2):* [Detailed explanation of specific logic]
        -   *Option E (Custom Merge Strategy 3):* [Detailed explanation of specific logic]
    -   **Recommended value:** Prioritize "HIDE" (for safety, ensuring no unwanted carriers are shown). However, this depends heavily on your specific rule setup.
    -   **Merchant scenario / example:** If you have a rule to "SHOW" free shipping for orders over $100, but another rule to "HIDE" free shipping for a specific product, the merge strategy determines which rule wins. "Prioritize HIDE" would hide free shipping for that product, even if the order is over $100.

-   **Display Unavailable Shipping Method Messages:**
    -   **What this setting does:** Controls whether customers see an explanation when a shipping method is hidden by a rule.
    -   **Effect of changing this setting:**
        -   *When enabled:* If a carrier is hidden, a message (which you define per rule) will be displayed to the customer, explaining why it's not available.
        -   *When disabled:* Hidden carriers will simply disappear from the list without any explanation.
    -   **Recommended value:** YES (Improves customer experience and reduces confusion).
    -   **Merchant scenario / example:** If "Express Shipping" is hidden because the customer's cart contains a "Fragile Item" that cannot be shipped via express, enabling this will show a message like "Express Shipping is not available for fragile items."

-   **Audit Log Retention (Days):**
    -   **What this setting does:** Defines how long the module keeps records of rule evaluations and their outcomes in the audit log.
    -   **Effect of changing this setting:**
        -   *Setting a number (e.g., 30):* The module will automatically delete log entries older than this many days.
        -   *Setting to 0 or empty:* The module will keep all log entries indefinitely (can lead to a large database over time).
    -   **Recommended value:** 30-90 days (sufficient for troubleshooting without excessive database growth).
    -   **Merchant scenario / example:** If a customer complains about not seeing a specific shipping method, you can check the audit log for recent evaluations. Keeping logs for 30 days allows you to investigate recent issues without storing years of data.

-   **Enable Checkout Simulator:**
    -   **What this setting does:** Activates a tool in the back office that allows you to test your shipping rules by simulating different customer and cart scenarios.
    -   **Effect of changing this setting:**
        -   *When enabled:* The "Checkout Simulator" tab will appear in the module's configuration, providing a powerful testing environment.
        -   *When disabled:* The simulator will not be available.
    -   **Recommended value:** YES (Essential for testing complex rules before deployment).
    -   **Merchant scenario / example:** Before launching a new shipping promotion, you can use the simulator to ensure your rules correctly show/hide the promotional shipping for various cart values, customer groups, and addresses.

### 2.2 Dedicated Admin Screens & Controller Views

#### 2.2.1 Shipping Policies (Back Office > Modules > Conditional Shipping Method Rules > Shipping Policies)
This is the core screen where you define and manage all your shipping rules.

-   **Screen Name & Menu Location:** **Conditional Shipping Method Rules > Shipping Policies** (found under the "Modules" section in your PrestaShop back office menu).
-   **Available Actions & Settings:**
    -   **Policy List:** A table displaying all your created shipping policies. Each policy has a name, status (enabled/disabled), and actions.
    -   **Add New Policy:** A button to create a new shipping policy.
    -   **Edit Policy:** Click on an existing policy to modify its rules, conditions, and settings.
    -   **Duplicate Policy:** Quickly create a copy of an existing policy, useful for making minor variations.
    -   **Enable/Disable Policy:** Toggle a policy's active status without deleting it.
    -   **Delete Policy:** Remove a policy permanently.
    -   **Policy Configuration Form (when adding/editing):**
        -   **Policy Name:** A descriptive name for your rule set (e.g., "Free Shipping over $100", "Express Shipping Restrictions").
        -   **Status:** Enable or disable this specific policy.
        -   **Priority:** If multiple policies apply, this determines the order in which they are evaluated. Lower numbers mean higher priority.
        -   **Target Carriers:** Select which specific shipping carriers this policy will affect.
        -   **Action (SHOW/HIDE):** Choose whether this policy will *show* the selected carriers if conditions are met, or *hide* them.
        -   **Unavailable Message:** If you chose "HIDE" and "Display Unavailable Shipping Method Messages" is enabled in the main config, this is the message customers will see (multilingual).
        -   **Conditions Builder:** This is where you define the "IF" part of your rule. You can add multiple condition groups (AND/OR logic) based on:
            -   Cart total, weight, quantity
            -   Specific products or categories in the cart
            -   Customer group, country, state, postcode
            -   Date and time
            -   And many more criteria.
-   **Effect of changes:**
    -   Adding, editing, or deleting policies directly impacts which shipping methods are presented to customers at checkout, based on the defined conditions.
    -   Changing a policy's status (enable/disable) immediately activates or deactivates its effect on the front office.
    -   Adjusting priority can resolve conflicts if multiple policies apply to the same carrier.
-   **Recommended workflow for daily store management:**
    1.  **Plan your rule:** Before creating, clearly define what you want to achieve (e.g., "If cart total > $50 AND customer is in USA, THEN SHOW 'Standard Shipping'").
    2.  **Create a new policy:** Give it a clear name.
    3.  **Select Target Carriers:** Choose the carriers this policy will affect.
    4.  **Set Action:** Decide if the policy should SHOW or HIDE these carriers.
    5.  **Build Conditions:** Use the intuitive condition builder to set up your "IF" statements. Use "Add Condition Group" for OR logic and "Add Condition" within a group for AND logic.
    6.  **Test with Simulator:** Crucially, use the "Checkout Simulator" (see next section) to verify your rules work as expected for various scenarios.
    7.  **Enable:** Once tested, enable the policy.

#### 2.2.2 Audit Log (Back Office > Modules > Conditional Shipping Method Rules > Audit Log)
This screen provides a historical record of how your shipping rules have been evaluated.

-   **Screen Name & Menu Location:** **Conditional Shipping Method Rules > Audit Log** (found under the "Modules" section in your PrestaShop back office menu).
-   **Available Actions & Settings:**
    -   **Log Table:** A detailed list of every time the module evaluated shipping rules for a customer's cart.
    -   **Columns:** Includes information like:
        -   Date and Time of evaluation
        -   Customer ID (if logged in)
        -   Cart ID
        -   Applied Policies: Which policies were considered.
        -   Outcome: Which carriers were shown/hidden and why.
        -   Order Snapshot: A link to view the exact state of the cart at the time of evaluation.
    -   **Filtering & Sorting:** Standard PrestaShop list features to filter by date, customer, or cart ID.
-   **Effect of changes:** This is a read-only screen for monitoring and troubleshooting. You cannot make direct changes here, but the data helps you understand how your rules are performing.
-   **Recommended workflow for daily store management:**
    -   Use this log to diagnose issues reported by customers (e.g., "I didn't see free shipping"). You can find their cart ID or customer ID and see exactly which rules were applied and what the outcome was.
    -   Periodically review the log to ensure rules are firing as expected, especially after making changes to policies.

#### 2.2.3 Checkout Simulator (Back Office > Modules > Conditional Shipping Method Rules > Checkout Simulator)
This powerful tool allows you to test your shipping rules without placing a real order.

-   **Screen Name & Menu Location:** **Conditional Shipping Method Rules > Checkout Simulator** (found under the "Modules" section in your PrestaShop back office menu, only visible if "Enable Checkout Simulator" is active in the main configuration).
-   **Available Actions & Settings:**
    -   **Customer Selection:** Choose an existing customer from your store, or simulate a guest.
    -   **Address Selection:** Select a specific address for the chosen customer, or manually enter address details.
    -   **Cart Content:** Add specific products, quantities, and combinations to simulate a customer's cart.
    -   **Simulate Button:** Click this to run the simulation.
    -   **Results Display:** Shows which shipping methods would be available (and which would be hidden with their messages) for the simulated scenario. It also details which policies were applied and why.
-   **Effect of changes:** This screen does not change any live store data. It's purely a testing environment.
-   **Recommended workflow for daily store management:**
    -   **Before activating new policies:** Always test them thoroughly here.
    -   **Troubleshooting:** Recreate a customer's reported issue by simulating their exact cart and address to see why a carrier was or wasn't shown.
    -   **Complex Scenarios:** Test edge cases, like minimum/maximum order values, specific product combinations, or different customer groups.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|---|
| **Module Configuration** | Enable Module | YES | Master switch for module functionality. |
| | Merge Strategy for Multiple Rules | Prioritize "HIDE" | How conflicting rules are resolved (SHOW vs. HIDE). |
| | Display Unavailable Shipping Method Messages | YES | Show explanations for hidden carriers to customers. |
| | Audit Log Retention (Days) | 30-90 | How long rule evaluation logs are kept. |
| | Enable Checkout Simulator | YES | Activates the testing tool in the back office. |
| **Shipping Policies** | Policy Name | Descriptive Name | Identifies the rule set. |
| | Status | Enabled | Activates/deactivates this specific policy. |
| | Priority | Lower number = higher priority | Determines evaluation order for conflicting policies. |
| | Target Carriers | Specific Carriers | Which shipping methods this policy affects. |
| | Action (SHOW/HIDE) | SHOW/HIDE | Whether to show or hide target carriers if conditions met. |
| | Unavailable Message | Custom Text (multilingual) | Message shown when carrier is hidden (if enabled). |
| | Conditions Builder | Varies | Defines the "IF" criteria for the policy to apply. |
| **Audit Log** | (All columns) | N/A (Read-only) | Provides historical records of rule evaluations for troubleshooting. |
| **Checkout Simulator** | (All fields) | N/A (Testing tool) | Allows simulating customer/cart scenarios to test rules. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My rules aren't working, or I'm seeing unexpected shipping options. What should I do?**
A1:
1.  **Check Module Status:** Ensure the "Enable Module" setting on the main configuration page is set to YES.
2.  **Check Policy Status:** Go to "Shipping Policies" and verify that the specific policies you expect to be active are enabled.
3.  **Clear Cache:** Go to **Advanced Parameters > Performance** and click "Clear cache". Sometimes PrestaShop caches old configurations.
4.  **Use the Checkout Simulator:** This is your best friend! Recreate the exact scenario (customer, address, cart contents) in the simulator. It will show you exactly which rules were applied and why, helping you pinpoint the issue.
5.  **Review Audit Log:** If a customer reported an issue, check the "Audit Log" for their cart/customer ID to see how the rules were evaluated for their specific order.
6.  **Merge Strategy:** Review your "Merge Strategy for Multiple Rules" setting. If you have conflicting SHOW and HIDE rules, this setting determines the outcome.

**Q2: Why isn't my custom "Unavailable Message" showing up?**
A2:
1.  **Enable Display Messages:** On the main module configuration page, ensure "Display Unavailable Shipping Method Messages" is set to YES.
2.  **Policy Action:** Verify that the policy's "Action" is set to "HIDE" for the target carrier. Messages only display when a carrier is hidden.
3.  **Message Content:** Make sure you've actually entered a message in the "Unavailable Message" field for the specific policy, and that it's translated for the relevant languages.

**Q3: The module is slowing down my checkout. Is this normal?**
A3: The module is highly optimized, but very complex rules (e.g., hundreds of conditions, many policies) can add a slight overhead.
1.  **Simplify Rules:** Review your policies. Can any be combined or simplified?
2.  **Prioritize:** Ensure your most frequently triggered rules have higher priority (lower number) so they are evaluated first.
3.  **Database Size:** Check your "Audit Log Retention" setting. If set to keep logs indefinitely, a very large log table can impact performance. Set it to a reasonable number of days (e.g., 30-90).

**Q4: How do I make sure my custom theme displays the shipping options correctly?**
A4: The module integrates with PrestaShop's standard checkout process.
1.  **Standard Hooks:** The module uses standard PrestaShop hooks. If your theme heavily customizes the checkout, ensure it still correctly calls the `displayCarrierList` or similar hooks where shipping options are rendered.
2.  **CSS Conflicts:** If the display looks off (e.g., messages are misaligned), there might be a CSS conflict with your theme. Use your browser's developer tools (F12) to inspect the elements and identify conflicting CSS rules. You might need to add custom CSS to your theme to override module or theme styles.
3.  **Contact Support:** If you're using a highly customized theme and encounter persistent display issues, provide details to MyPresta.eu support.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview
The "Conditional Shipping Method Rules" module (`shipmethodrules`) is built following PrestaShop's MVC (Model-View-Controller) pattern, heavily leveraging `ObjectModel` for data persistence and a custom policy engine for rule evaluation. It introduces several custom admin controllers for managing policies, viewing audit logs, and simulating checkout scenarios. The core logic revolves around `ShipmethodrulesPolicy` objects, which encapsulate `ShipmethodrulesConditionGroup` and `ShipmethodrulesCondition` entities, allowing for complex nested AND/OR logic. The `ShipmethodrulesEngine` is responsible for evaluating these policies against a given `ShipmethodrulesContext` (representing the current cart, customer, and address) and determining the visibility of shipping carriers.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers
-   `controllers/front/index.php`:
    -   Class name: `ShipmethodrulesIndexModuleFrontController`
    -   Parent class: `ModuleFrontController`
    -   Responsibility: Likely a placeholder or base controller. In many modules, this might handle initial setup or redirection if a dedicated front-office page is needed. For this module, the primary front-office logic is integrated via hooks into the checkout process.
-   `controllers/front/simulate.php`:
    -   Class name: `ShipmethodrulesSimulateModuleFrontController`
    -   Parent class: `ModuleFrontController`
    -   Responsibility: Handles AJAX requests related to the checkout simulator. It receives simulated cart, customer, and address data, then uses the `ShipmethodrulesEngine` to evaluate policies and returns the resulting carrier visibility.
-   `controllers/front/visibility.php`:
    -   Class name: `ShipmethodrulesVisibilityModuleFrontController`
    -   Parent class: `ModuleFrontController`
    -   Responsibility: This controller is crucial for real-time updates on the checkout page. It responds to AJAX requests (e.g., when a customer changes address or cart contents) to re-evaluate shipping rules and return the updated list of available carriers and their associated messages.

#### Back-Office Admin Controllers
-   `controllers/admin/AdminShipmethodrulesAuditLog.php`:
    -   Class name: `AdminShipmethodrulesAuditLogController`
    -   Parent class: `ModuleAdminController`
    -   Tab name: "Audit Log"
    -   Managed entity: `ShipmethodrulesLog`
    -   Responsibility: Manages the display and filtering of the `shipmethodrules_log` table. It provides a grid view of all rule evaluations, including details about the cart, customer, applied policies, and the final outcome (which carriers were shown/hidden).
-   `controllers/admin/AdminShipmethodrulesPolicies.php`:
    -   Class name: `AdminShipmethodrulesPoliciesController`
    -   Parent class: `ModuleAdminController`
    -   Tab name: "Shipping Policies"
    -   Managed entity: `ShipmethodrulesPolicy`
    -   Responsibility: This is the primary controller for managing shipping policies. It handles listing, adding, editing, duplicating, enabling/disabling, and deleting `ShipmethodrulesPolicy` objects. It also orchestrates the condition builder interface.
-   `controllers/admin/index.php`:
    -   Class name: `ShipmethodrulesAdminController` (or similar, if it's a base controller for the module's admin section)
    -   Parent class: `ModuleAdminController`
    -   Responsibility: Often acts as a dispatcher or a default controller for the module's main admin menu entry, redirecting to the primary configuration or policy list.

### 4.3 Core Classes & Models (`classes/`)

-   `classes/ShipmethodrulesAdmin.php`: Likely a helper class for common admin-related functionalities or dashboard statistics.
-   `classes/ShipmethodrulesAuditLog.php`: Extends `ObjectModel`. Maps to `ps_shipmethodrules_log` table. Stores details of each rule evaluation event for auditing purposes.
    -   `$definition` fields: `id_cart`, `id_customer`, `id_address_delivery`, `policies_applied`, `carriers_visibility`, `timestamp`.
-   `classes/ShipmethodrulesCompatibility.php`: Provides methods to handle differences between PrestaShop 1.7, 8, and 9, ensuring cross-version compatibility for core functionalities (e.g., hook registration, configuration access).
-   `classes/ShipmethodrulesCondition.php`: Extends `ObjectModel`. Represents a single condition within a condition group (e.g., "Cart Total > $100").
    -   `$definition` fields: `id_shipmethodrules_condition_group`, `type`, `operator`, `value`, `id_product`, `id_category`, etc.
-   `classes/ShipmethodrulesConditionEvaluator.php`: Contains the logic to evaluate a single `ShipmethodrulesCondition` against the current `ShipmethodrulesContext`.
-   `classes/ShipmethodrulesConditionGroup.php`: Extends `ObjectModel`. Represents a group of conditions linked by an AND operator. Multiple groups can be linked by an OR operator within a policy.
    -   `$definition` fields: `id_shipmethodrules_policy`, `logic_operator` (implicitly AND for conditions within, OR for groups).
-   `classes/ShipmethodrulesConditionTree.php`: Manages the hierarchical structure of conditions and condition groups for a policy, facilitating their storage and retrieval.
-   `classes/ShipmethodrulesContext.php`: An object that encapsulates all relevant data for rule evaluation: current `Cart`, `Customer`, `Address`, `Currency`, `Language`, etc. This provides a consistent interface for the `ShipmethodrulesEngine`.
-   `classes/ShipmethodrulesDashboard.php`: Helper class for generating dashboard statistics or summaries related to the module's activity.
-   `classes/ShipmethodrulesEngine.php`: The central class for rule evaluation. It takes a `ShipmethodrulesContext` and a list of `ShipmethodrulesPolicy` objects, applies the configured merge strategy, and returns the final visibility status for each carrier.
-   `classes/ShipmethodrulesListRenderer.php`: Custom renderer for admin lists, potentially adding specific actions (like duplicate) or custom column formatting.
-   `classes/ShipmethodrulesLog.php`: Alias or specific implementation for `ShipmethodrulesAuditLog`.
-   `classes/ShipmethodrulesOrderSnapshot.php`: Captures and stores a snapshot of an order's state (cart, customer, address) at the time of rule evaluation, useful for debugging.
-   `classes/ShipmethodrulesPolicy.php`: Extends `ObjectModel`. The main model for a shipping rule. It contains the policy's name, status, priority, target carriers, action (SHOW/HIDE), unavailable message, and a collection of `ShipmethodrulesConditionGroup` objects.
    -   `$definition` fields: `name`, `active`, `priority`, `action`, `unavailable_message`, `target_carriers`.
-   `classes/ShipmethodrulesPolicyDuplicator.php`: Handles the logic for duplicating a `ShipmethodrulesPolicy`, including all its associated condition groups and conditions.
-   `classes/ShipmethodrulesPreset.php`: Likely manages predefined sets of conditions or policies that can be quickly applied.
-   `classes/ShipmethodrulesRule.php`: A more generic representation of a rule, possibly an abstract base class or an older iteration of `ShipmethodrulesPolicy`.
-   `classes/ShipmethodrulesTreeRepository.php`: Manages the persistence and retrieval of the condition tree structure.

### 4.4 JavaScript Assets (`views/js/`)

-   `shipmethodrules/lib/searchTool/views/js/autocomplete.js`: Generic autocomplete functionality, likely used for searching products, categories, or customers in the condition builder.
-   `shipmethodrules/lib/searchTool/views/views/js/autocomplete.js`: Duplicate or specific instance of the autocomplete script.
-   `shipmethodrules/views/js/adminConditionBuilder.js`: Handles the dynamic creation, modification, and deletion of conditions and condition groups within the policy editing interface. Manages the complex UI for building rules.
-   `shipmethodrules/views/js/adminPolicyRules.js`: Specific JS for the `AdminShipmethodrulesPolicies` controller, managing the list of policies, bulk actions, and potentially interactions with the condition builder.
-   `shipmethodrules/views/js/adminShipmethodrulesDashboard.js`: Scripts for any dashboard widgets or statistics displayed in the module's admin section.
-   `shipmethodrules/views/js/adminShipmethodrulesSearchTool.js`: Integrates the search tool (autocomplete) specifically for the module's admin forms.
-   `shipmethodrules/views/js/adminShipmethodrulesSimulator.js`: Powers the "Checkout Simulator" interface, handling user input for customer, address, and cart, and making AJAX calls to `controllers/front/simulate.php`.
-   `shipmethodrules/views/js/checkout.js`: Front-office script injected into the checkout process. It listens for changes in the cart or delivery address, then makes AJAX calls to `controllers/front/visibility.php` to update the displayed shipping methods dynamically.
-   `shipmethodrules/views/js/unavailableUi.js`: Handles the display and styling of unavailable shipping method messages on the front office checkout page.

### 4.5 CSS Stylesheets (`views/css/`)

-   `shipmethodrules/lib/searchTool/views/css/autocomplete.css`: Styles for the autocomplete search tool.
-   `shipmethodrules/lib/searchTool/views/views/css/autocomplete.css`: Duplicate or specific instance of autocomplete styles.
-   `shipmethodrules/views/css/admin_order_snapshot.css`: Styles for displaying the order snapshot details in the audit log or simulator.
-   `shipmethodrules/views/css/admin_shipmethodrules.css`: General styling for the module's back-office interfaces, including policy lists, condition builder, and simulator.
-   `shipmethodrules/views/css/front.css`: Front-office styles for displaying unavailable shipping method messages or highlighting specific shipping options on the checkout page.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)
-   `shipmethodrules/views/templates/hook/carrier_guard.tpl`: Renders a hidden input or script to "guard" against invalid carrier selections, ensuring that only allowed carriers can be submitted.
-   `shipmethodrules/views/templates/hook/carrier_list.tpl`: Overrides or extends the default carrier list template in the checkout to apply visibility rules and display unavailable messages. This is where the filtered list of carriers is actually rendered.

#### Admin templates (`views/templates/admin/`)
-   `shipmethodrules/views/templates/admin/auditPreview.tpl`: Template for displaying a detailed preview of an audit log entry.
-   `shipmethodrules/views/templates/admin/dashboard.tpl`: Template for the module's main configuration or dashboard view.
-   `shipmethodrules/views/templates/admin/helpers/list/list_action_duplicate.tpl`: Custom template for the "duplicate" action button in admin lists (e.g., for policies).
-   `shipmethodrules/views/templates/admin/policiesPreview.tpl`: Template for displaying a preview of a shipping policy.
-   `shipmethodrules/views/templates/admin/policyConditionBuilder.tpl`: The complex template that renders the UI for building conditions (dropdowns, input fields, AND/OR logic).
-   `shipmethodrules/views/templates/admin/policyRuleCard.tpl`: Renders a single rule or policy as a card in a list view.
-   `shipmethodrules/views/templates/admin/policyRulesTable.tpl`: Renders the table of shipping policies.
-   `shipmethodrules/views/templates/admin/scopeSelector.tpl`: Template for selecting the scope of a condition (e.g., "Cart Total", "Customer Group").

#### Other templates
-   `shipmethodrules/lib/searchTool/views/scripts.tpl`: Includes JavaScript for the search tool.
-   `shipmethodrules/lib/searchTool/views/views/scripts.tpl`: Duplicate or specific instance of search tool scripts.

### 4.7 Database Schema & Hooks Map

#### Database Tables
-   `ps_shipmethodrules_policy`: Stores the main shipping policy definitions (name, active status, priority, action, unavailable message, target carriers).
-   `ps_shipmethodrules_condition_group`: Stores groups of conditions associated with a policy.
-   `ps_shipmethodrules_condition`: Stores individual conditions (type, operator, value, associated entities like product/category IDs).
-   `ps_shipmethodrules_log`: Stores audit log entries of rule evaluations (cart ID, customer ID, timestamp, policies applied, carriers visibility).
-   `ps_shipmethodrules_order_snapshot`: Stores detailed snapshots of cart/order data for audit log entries.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
|---|---|---|
| `displayHeader` | In the `<head>` section of all front-office pages. | Injects necessary CSS and JS files for front-office functionality (e.g., `checkout.js`, `front.css`). |
| `displayCarrierList` | On the checkout page, where shipping methods are listed. | The primary hook for filtering and rendering the available shipping methods based on defined policies. |
| `actionCarrierProcess` | After a carrier has been selected but before the order is validated. | Acts as a "guard" to re-validate the selected carrier against the rules, preventing submission of an invalid choice. |
| `actionValidateOrder` | After an order has been successfully validated. | Potentially logs the final shipping method chosen and the rules applied to the audit log. |
| `actionAdminControllerSetMedia` | In the back office, when an admin controller is loaded. | Injects CSS and JS for the module's admin interfaces (policy builder, simulator, audit log). |
| `actionObjectCarrierAddAfter` | After a new carrier is added. | Potentially updates internal module data or caches related to carriers. |
| `actionObjectCarrierUpdateAfter` | After a carrier is updated. | Potentially updates internal module data or caches related to carriers. |
| `actionObjectCarrierDeleteAfter` | After a carrier is deleted. | Cleans up any references to the deleted carrier in policies. |
| `displayBackOfficeHeader` | In the header of all back-office pages. | Injects global admin CSS/JS or specific scripts for module's admin pages. |

## 5. Official Support & Updates
For the latest updates, bug fixes, and official support for the "Conditional Shipping Method Rules" module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist merchants and developers with any issues or questions regarding the module's functionality and integration.
