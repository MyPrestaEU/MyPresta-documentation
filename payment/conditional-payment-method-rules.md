---
title: "Conditional Payment Method Rules - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Conditional Payment Method Rules PrestaShop module by MyPresta.eu."
sidebar:
  label: "Conditional Payment Method Rules - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Conditional Payment Method Rules Module on MyPresta.eu](https://mypresta.eu/modules/payment-process/conditional-payment-method-rules.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/payment/conditional-payment-method-rules/)
>
> ---


# Conditional Payment Method Rules

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The module’s configuration is primarily managed through dedicated administration screens, allowing you to create and manage your payment method policies.

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main entry point for the module. After installation, clicking “Configure” will take you to a dashboard or a general settings page.

#### General Settings & Dashboard

This screen provides an overview of your module’s status and quick access to key features.

- **What this screen does:** Displays a summary of your active policies, recent audit log entries, and quick links to manage policies or view the audit log. It’s your central hub for monitoring the module’s activity.
- **Effect of changing settings:** This screen primarily provides information and navigation. Any changes you make here (e.g., enabling/disabling a policy) will directly impact how payment methods are displayed at checkout.
- **Recommended value:** Keep an eye on the dashboard for any policy conflicts or unexpected behavior.

### 2.2 Dedicated Admin Screens & Controller Views

The module introduces several new menu items under the “Payment” section in your PrestaShop Back Office.

#### 2.2.1 Payment Method Policies (Back Office > Payment > Payment Method Rules > Policies)

This is where you define and manage all your rules for showing or hiding payment methods.

- **Screen Name & Menu Location:** **Payment > Payment Method Rules > Policies**
- **Available Actions & Settings:**

  - **Policy List:** A table showing all your created policies, their status (enabled/disabled), and the payment methods they affect.
  - **Add New Policy:** Click this button to create a new rule.
  - **Edit/Delete Policy:** Manage individual policies from the list.
  - **Duplicate Policy:** Quickly create a copy of an existing policy to modify it.
  - **Enable/Disable Policy:** Toggle the active status of a policy without deleting it.
  - **Import/Export Policies (JSON):** Backup your policies or transfer them between stores.
- **Creating/Editing a Policy:**
  When you add or edit a policy, you’ll configure several key aspects:

  1. **Policy Name:**

     - **What this setting does:** A descriptive name for your policy (e.g., “Hide COD for international orders”).
     - **Effect of changing this setting:** Helps you identify the policy in the list.
     - **Recommended value:** Make it clear and concise.
     - **Merchant scenario:** Naming a policy “Free Shipping Only with PayPal” immediately tells you its purpose.
  2. **Status (Enabled/Disabled):**

     - **What this setting does:** Controls whether the policy is active and applied at checkout.
     - **Effect of changing this setting:**
       - *When enabled:* The rules within this policy will be evaluated and affect payment method visibility.
       - *When disabled:* The policy is ignored, and its rules have no effect.
     - **Recommended value:** Enable policies only when you are sure they are correctly configured.
     - **Merchant scenario:** You might disable a policy temporarily during a promotion or if you’re troubleshooting.
  3. **Payment Methods Affected:**

     - **What this setting does:** Select which specific payment methods this policy will control.
     - **Effect of changing this setting:** Only the selected payment methods will be subject to this policy’s rules.
     - **Recommended value:** Select all payment methods relevant to this policy.
     - **Merchant scenario:** If you want to hide “Cash on Delivery” and “Bank Wire” under certain conditions, you’d select both here.
  4. **Policy Type (Show/Hide):**

     - **What this setting does:** Determines whether the policy’s conditions will *show* the selected payment methods or *hide* them.
     - **Effect of changing this setting:**
       - *When set to “Show”:* The selected payment methods will *only* be visible if ALL conditions in this policy are met. If conditions are not met, they are hidden.
       - *When set to “Hide”:* The selected payment methods will be hidden if ALL conditions in this policy are met. If conditions are not met, they are visible.
     - **Recommended value:** Choose based on your primary goal. “Hide” is often easier for specific restrictions, while “Show” is good for exclusive offers.
     - **Merchant scenario:**
       - *Hide:* “Hide Cash on Delivery if cart total is over $500.”
       - *Show:* “Show ‘Installment Plan’ ONLY if customer group is ‘VIP’ AND cart total is over $1000.”
  5. **Conditions Builder:**

     - **What this setting does:** This is the core of your policy. You build complex rules using “AND” and “OR” logic based on various criteria.
     - **Effect of changing this setting:** The conditions you define here determine *when* the policy’s “Show” or “Hide” action is triggered.
     - **Available Conditions (Examples):**
       - **Cart Total:** Based on the total value of the customer’s cart.
       - **Customer Group:** Based on the group the customer belongs to (e.g., Guest, Customer, VIP, Wholesaler).
       - **Country:** Based on the customer’s shipping or billing country.
       - **Carrier:** Based on the selected shipping carrier.
       - **Products in Cart:** Based on specific products, categories, manufacturers, or suppliers in the cart.
       - **Currency:** Based on the currency used for the order.
       - **Weight:** Based on the total weight of the cart.
       - **Date/Time:** Based on specific dates or times (e.g., for promotions).
       - **Shop:** For multi-store setups.
     - **Recommended value:** Start with simple conditions and test thoroughly. Use “AND” for stricter requirements and “OR” for broader applicability.
     - **Merchant scenario:**
       - “Hide PayPal if (Country IS ‘USA’ AND Cart Total IS LESS THAN $10) OR (Customer Group IS ‘Wholesaler’).”
       - “Show Bank Wire if (Customer Group IS ‘B2B’) AND (Cart Total IS GREATER THAN $1000).”
  6. **Unavailable Message:**

     - **What this setting does:** A custom message displayed to the customer if a payment method is hidden by this policy.
     - **Effect of changing this setting:** Provides clear communication to the customer about why a payment option isn’t available, preventing confusion.
     - **Recommended value:** Keep it polite and informative (e.g., “Cash on Delivery is not available for orders over $500. Please choose another payment method.”).
     - **Merchant scenario:** “This payment method is only available for VIP customers.” or “Please select a different shipping method to use this payment option.”
- **Recommended workflow for daily store management:**

  1. **Identify a need:** “I want to stop offering Cash on Delivery for orders over $200.”
  2. **Create a new policy:** Name it “COD Limit $200”.
  3. **Select “Hide”** as the policy type.
  4. **Select “Cash on Delivery”** as the affected payment method.
  5. **Add a condition:** “Cart Total IS GREATER THAN $200”.
  6. **Add an unavailable message:** “Cash on Delivery is not available for orders exceeding $200. Please choose another payment method.”
  7. **Enable and Save.**
  8. **Test using the Simulator** (see next section).

#### 2.2.2 Audit Log (Back Office > Payment > Payment Method Rules > Audit Log)

This screen provides a detailed history of how your payment rules have been applied.

- **Screen Name & Menu Location:** **Payment > Payment Method Rules > Audit Log**
- **Available Actions & Settings:**
  - **Log List:** A table showing each instance where a payment method’s visibility was affected by a policy.
  - **Details:** View specific information about each log entry, including the customer, cart details, policies evaluated, and the final outcome (which payment methods were shown/hidden).
  - **Filtering:** Filter log entries by date, customer, policy, or payment method to quickly find specific events.
- **Effect of changes:** This screen is for viewing and auditing. You cannot make changes here, but it’s invaluable for understanding why certain payment methods were or weren’t shown to a customer.
- **Recommended workflow for daily store management:** Regularly check the audit log if you receive customer inquiries about missing payment methods or if you suspect a policy isn’t working as expected. It’s your debugging tool.

#### 2.2.3 Simulator (Back Office > Payment > Payment Method Rules > Simulator)

The simulator is a powerful tool to test your policies without placing a real order.

- **Screen Name & Menu Location:** **Payment > Payment Method Rules > Simulator**
- **Available Actions & Settings:**
  - **Input Fields:** Enter various criteria like customer group, country, carrier, cart total, and even add specific products to a simulated cart.
  - **Simulate Button:** Click to see which payment methods would be available based on your entered criteria and active policies.
  - **Results Display:** Shows a list of available and unavailable payment methods, along with the reasons (which policies caused them to be hidden/shown).
- **Effect of changes:** This screen allows you to experiment with different scenarios and immediately see the impact of your policies. It does not affect your live store.
- **Recommended workflow for daily store management:** *Always* use the simulator after creating or modifying a policy. Test edge cases and common scenarios to ensure your rules work exactly as intended before they go live.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Policies (Add/Edit)** | Policy Name | Descriptive Name | Internal identification of the rule. |
|  | Status | Enabled | Activates/deactivates the policy. |
|  | Payment Methods Affected | Select relevant methods | Specifies which payment gateways this policy controls. |
|  | Policy Type | Hide | Determines if conditions *hide* or *show* selected methods. |
|  | Conditions Builder | Varies by rule | Defines the criteria (e.g., cart total, customer group) for the policy to apply. |
|  | Unavailable Message | Clear, informative text | Message shown to customers when a payment method is hidden. |
| **Audit Log** | Log Entries | N/A | Provides a historical record of policy evaluations. |
|  | Filters | N/A | Helps search and analyze specific log events. |
| **Simulator** | Simulation Inputs | N/A | Allows testing policies with various customer/cart scenarios. |
|  | Simulation Results | N/A | Shows which payment methods would be available/unavailable for the simulated scenario. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: A payment method isn’t showing up, but I don’t have any policies set to hide it. What’s wrong?**
A: First, check the module’s **Audit Log** for any entries related to that payment method and customer. The log will tell you if a policy *did* hide it. If not, the issue might be outside this module:
\* Is the payment method itself enabled in **Payment > Payment Methods**?
\* Are there any restrictions set directly on the payment module (e.g., country, currency, group restrictions within the payment module’s own configuration)?
\* Clear your PrestaShop cache (**Advanced Parameters > Performance**).

**Q: My policies don’t seem to be working. What should I do?**
A:
1. **Check Policy Status:** Ensure the policy is “Enabled” on the **Policies** screen.
2. **Use the Simulator:** Go to **Payment > Payment Method Rules > Simulator** and input the exact conditions you’re testing. See what the simulator predicts. This is the fastest way to debug your conditions.
3. **Review Conditions:** Double-check your “AND” and “OR” logic. A single incorrect condition can prevent the entire policy from triggering.
4. **Check Affected Payment Methods:** Make sure the payment method you expect to be affected is actually selected in the policy.
5. **Clear Cache:** Always clear your PrestaShop cache (**Advanced Parameters > Performance**) after making significant changes to module settings or policies.

**Q: How do I handle multiple policies that affect the same payment method?**
A: The module evaluates all active policies.
\* If multiple “Hide” policies apply to the same payment method, and *any* of them trigger, the payment method will be hidden.
\* If multiple “Show” policies apply to the same payment method, and *any* of them trigger, the payment method will be shown.
\* **Conflict Resolution:** If one policy says “Show” and another says “Hide” for the same payment method under the same conditions, the module has a defined merge strategy (typically, “Hide” takes precedence to ensure security and prevent unintended availability). Use the **Simulator** and **Audit Log** to understand the exact outcome of conflicting policies.

**Q: Can I translate the “Unavailable Message” for different languages?**
A: Yes, when editing a policy, the “Unavailable Message” field will typically have a language selector (a flag icon) next to it. Click the flag to enter translations for each language enabled in your store.

**Q: My custom theme is not displaying the unavailable messages correctly. What can I do?**
A: This usually indicates a CSS conflict or a missing template override in your theme.
\* **Check `front.css`:** The module includes its own `front.css` for basic styling. Your theme might be overriding it.
\* **Inspect Element:** Use your browser’s developer tools (F12) to inspect the area where the message should appear. Look for CSS rules that might be hiding it or mispositioning it.
\* **Contact Theme Developer:** If you’re not comfortable with CSS, contact your theme developer or a PrestaShop expert for assistance. They can help integrate the module’s styling with your theme.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The Conditional Payment Method Rules module follows a robust, object-oriented design pattern within the PrestaShop MVC framework. It heavily utilizes `ObjectModel` for managing policies and audit logs, a dedicated `ConditionTree` structure for complex rule evaluation, and a `PaymethodrulesEngine` to apply these rules at the checkout stage. The module injects its logic primarily via hooks, specifically `actionPaymentOptionsModifier` (or similar for older PS versions) to manipulate the list of available payment methods. Admin controllers provide a rich UI for policy management, simulation, and auditing.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `controllers/front/index.php`
  - **Class Name:** `PaymethodrulesIndexModuleFrontController` (or similar, typically extending `ModuleFrontController`)
  - **Responsibility:** This controller might serve as a fallback or a simple entry point, but the core logic for payment method modification is usually handled via hooks. It could be used for specific AJAX requests related to front-office rule evaluation if needed, though the primary evaluation occurs during the payment options rendering.
- `controllers/front/simulate.php`
  - **Class Name:** `PaymethodrulesSimulateModuleFrontController` (or similar, extending `ModuleFrontController`)
  - **Responsibility:** While the main simulator is in the BO, a front controller might exist for a simplified front-end simulation or to expose simulation results via AJAX for debugging purposes.

#### Back-Office Admin Controllers

- `controllers/admin/AdminPaymethodrulesAuditLog.php`
  - **Class Name:** `AdminPaymethodrulesAuditLogController` (extends `ModuleAdminController`)
  - **Tab Name:** Payment Method Rules -> Audit Log
  - **Managed Entity:** `PaymethodrulesAuditLog` (mapped to `ps_paymethodrules_log` table)
  - **Responsibility:** Manages the display and filtering of the audit log entries. It uses `HelperList` to render the grid view and provides actions for viewing log details.
- `controllers/admin/AdminPaymethodrulesPolicies.php`
  - **Class Name:** `AdminPaymethodrulesPoliciesController` (extends `ModuleAdminController`)
  - **Tab Name:** Payment Method Rules -> Policies
  - **Managed Entity:** `PaymethodrulesPolicy` (mapped to `ps_paymethodrules_policy` table)
  - **Responsibility:** This is the central controller for managing payment policies. It handles:
    - Listing policies using `HelperList`.
    - Adding/editing policies using `HelperForm` with complex field rendering for the condition builder.
    - Enabling/disabling, duplicating, and deleting policies.
    - Handling JSON import/export of policies.
- `controllers/admin/index.php`
  - **Class Name:** `AdminPaymethodrulesDashboardController` (or similar, extends `ModuleAdminController`)
  - **Tab Name:** Payment Method Rules -> Dashboard (or main module configuration link)
  - **Managed Entity:** N/A (dashboard view)
  - **Responsibility:** Provides the main entry point and dashboard view for the module in the Back Office. It aggregates information from other controllers (e.g., policy counts, recent log entries) and provides navigation. It typically uses Smarty templates for rendering the dashboard widgets.

### 4.3 Core Classes & Models (`classes/`)

- `classes/index.php`: Standard empty file to prevent directory listing.
- `classes/PaymethodrulesAdmin.php`: Likely a helper class for common admin-related functions, such as menu registration, tab management, or shared form rendering logic.
- `classes/PaymethodrulesAuditLog.php`
  - **Extends:** `ObjectModel`
  - **Database Table:** `ps_paymethodrules_log`
  - **`$definition` fields:** `id_paymethodrules_log`, `id_cart`, `id_customer`, `id_shop`, `context_data` (JSON), `policies_applied` (JSON), `payment_methods_before` (JSON), `payment_methods_after` (JSON), `date_add`.
  - **Key Public Methods:** Methods for logging events, retrieving log entries, and possibly cleaning up old logs.
- `classes/PaymethodrulesCompatibility.php`: Handles compatibility layers for different PrestaShop versions (e.g., differences in hook names, object structures, or `Tools` functions).
- `classes/PaymethodrulesCondition.php`
  - **Extends:** `ObjectModel` (or a base class for conditions)
  - **Database Table:** `ps_paymethodrules_condition` (if conditions are stored individually)
  - **`$definition` fields:** `id_paymethodrules_condition`, `id_paymethodrules_policy`, `type`, `operator`, `value`, `id_parent_group`.
  - **Key Public Methods:** Methods for defining condition types, operators, and values. Part of the condition tree structure.
- `classes/PaymethodrulesConditionEvaluator.php`: Contains the core logic for evaluating a single `PaymethodrulesCondition` against a given context (cart, customer, etc.).
- `classes/PaymethodrulesConditionGroup.php`
  - **Extends:** `ObjectModel` (or a base class for condition groups)
  - **Database Table:** `ps_paymethodrules_condition_group` (if groups are stored individually)
  - **`$definition` fields:** `id_paymethodrules_condition_group`, `id_paymethodrules_policy`, `operator` (`AND`/`OR`), `id_parent_group`.
  - **Key Public Methods:** Manages a collection of conditions or nested condition groups, applying the `AND`/`OR` logic.
- `classes/PaymethodrulesConditionTree.php`: Represents the entire hierarchical structure of conditions and condition groups for a policy. Provides methods to build, traverse, and evaluate the tree.
- `classes/PaymethodrulesContext.php`: A utility class that encapsulates all relevant data needed for rule evaluation (current cart, customer, address, carrier, currency, etc.). It acts as a data provider for the `PaymethodrulesEngine`.
- `classes/PaymethodrulesDashboard.php`: Helper class for fetching data and preparing statistics/summaries for the module’s dashboard view.
- `classes/PaymethodrulesEngine.php`: The central class responsible for orchestrating the rule evaluation.
  - **Key Public Methods:** `evaluatePolicies(PaymethodrulesContext $context, array $payment_options)`: Takes the current context and a list of available payment options, applies all active policies, and returns the modified list. It uses `PaymethodrulesConditionTree` and `PaymethodrulesConditionEvaluator`.
- `classes/PaymethodrulesListRenderer.php`: A specialized helper for rendering lists in the Back Office, potentially extending `HelperList` or providing custom column rendering.
- `classes/PaymethodrulesLog.php`: Alias or specific implementation for `PaymethodrulesAuditLog`.
- `classes/PaymethodrulesPolicy.php`
  - **Extends:** `ObjectModel`
  - **Database Table:** `ps_paymethodrules_policy`
  - **`$definition` fields:** `id_paymethodrules_policy`, `name`, `active`, `policy_type` (`show`/`hide`), `payment_methods` (JSON array of module names), `unavailable_message` (multilingual), `conditions_tree` (JSON representation of the condition tree), `date_add`, `date_upd`.
  - **Key Public Methods:** Methods for saving/loading policy data, retrieving associated conditions, and providing policy-specific logic.
- `classes/PaymethodrulesPolicyDuplicator.php`: Utility class specifically for duplicating `PaymethodrulesPolicy` objects, ensuring all associated conditions and groups are also copied correctly.
- `classes/PaymethodrulesPreset.php`: Likely handles predefined sets of conditions or policies that can be quickly loaded by the merchant.
- `classes/PaymethodrulesRule.php`: Could be an older or alternative name for `PaymethodrulesCondition` or `PaymethodrulesPolicy`, or a base class for rule components.
- `classes/PaymethodrulesTreeRepository.php`: Manages the persistence and retrieval of the `PaymethodrulesConditionTree` structure, likely converting it to/from JSON for storage in the `PaymethodrulesPolicy` object.

### 4.4 JavaScript Assets (`views/js/`)

- `paymethodrules/lib/searchTool/views/js/autocomplete.js`: Generic autocomplete functionality, likely used for selecting products, categories, or other entities within the condition builder.
- `paymethodrules/lib/searchTool/views/views/js/autocomplete.js`: Duplicate or specific version of the autocomplete script.
- `paymethodrules/views/js/adminConditionBuilder.js`:
  - **Scope:** Back-office (Policy creation/editing screen).
  - **Functionality:** Handles the dynamic creation, modification, and deletion of conditions and condition groups within the policy form. Manages the “AND”/“OR” logic, adds new condition rows, handles condition type changes (e.g., showing different input fields for “Cart Total” vs. “Product”).
- `paymethodrules/views/js/adminPaymethodrulesDashboard.js`:
  - **Scope:** Back-office (Dashboard screen).
  - **Functionality:** Might handle AJAX calls for dashboard widgets, refresh data, or provide interactive elements on the dashboard.
- `paymethodrules/views/js/adminPaymethodrulesSearchTool.js`:
  - **Scope:** Back-office (Condition builder).
  - **Functionality:** Integrates the `autocomplete.js` library for searching and selecting entities (products, categories, customers, carriers) when building conditions.
- `paymethodrules/views/js/adminPaymethodrulesSimulator.js`:
  - **Scope:** Back-office (Simulator screen).
  - **Functionality:** Captures user input for simulation criteria, sends AJAX requests to the simulator controller, and dynamically updates the display with the simulated payment method availability.
- `paymethodrules/views/js/adminPolicyRules.js`:
  - **Scope:** Back-office (Policy list and edit screens).
  - **Functionality:** General JS for policy management, such as handling enable/disable toggles, duplicate actions, and potentially form submission logic for policy details.
- `paymethodrules/views/js/checkout.js`:
  - **Scope:** Front-office (Checkout page).
  - **Functionality:** This is crucial. It listens for changes in the checkout process (e.g., shipping method selection, address change, cart update) and might trigger AJAX calls to re-evaluate payment method availability or dynamically update the display of unavailable messages. It ensures the payment options are always up-to-date.
- `paymethodrules/views/js/unavailableUi.js`:
  - **Scope:** Front-office (Checkout page).
  - **Functionality:** Manages the display and styling of the “unavailable message” for hidden payment methods. It might dynamically inject the message, apply CSS classes, or handle animations.

### 4.5 CSS Stylesheets (`views/css/`)

- `paymethodrules/lib/searchTool/views/css/autocomplete.css`: Styles for the autocomplete search tool in the Back Office.
- `paymethodrules/lib/searchTool/views/views/css/autocomplete.css`: Duplicate or specific version of the autocomplete CSS.
- `paymethodrules/views/css/admin_paymethodrules.css`:
  - **Scope:** Back-office (All module admin screens).
  - **Functionality:** Provides styling for the policy list, condition builder, dashboard, simulator, and audit log. Includes styles for form elements, tables, and custom UI components specific to the module.
  - **Key CSS class selectors:** `.paymethodrules-policy-card`, `.condition-group`, `.condition-row`, `.paymethodrules-dashboard-widget`.
- `paymethodrules/views/css/front.css`:
  - **Scope:** Front-office (Checkout page).
  - **Functionality:** Provides basic styling for the unavailable payment method messages or any visual cues related to hidden payment options on the checkout page.
  - **Key CSS class selectors:** `.paymethodrules-unavailable-message`, `.paymethodrules-hidden-payment`.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `paymethodrules/views/templates/hook/payment_top.tpl`:
  - **Hook:** `displayPaymentTop` (or similar, depending on PS version)
  - **Visual Block:** This template might be used to display a general message or information related to payment rules at the top of the payment selection section. However, the primary interaction is usually directly modifying the payment options array. It could also be used to inject the `checkout.js` and `unavailableUi.js` scripts.

#### Admin templates (`views/templates/admin/`)

- `paymethodrules/lib/searchTool/views/scripts.tpl`: Includes JS/CSS for the search tool in admin.
- `paymethodrules/lib/searchTool/views/views/scripts.tpl`: Duplicate or specific version of search tool scripts.
- `paymethodrules/views/templates/admin/auditPreview.tpl`: Renders the detailed view for a single audit log entry, showing context, policies applied, and payment method changes.
- `paymethodrules/views/templates/admin/dashboard.tpl`: Renders the main module dashboard, including widgets for policy summary, recent logs, and quick links.
- `paymethodrules/views/templates/admin/helpers/list/list_action_duplicate.tpl`: Custom template for the “duplicate” action button in the `HelperList` for policies.
- `paymethodrules/views/templates/admin/policiesPreview.tpl`: Might be used for a quick preview of a policy’s rules without entering the full edit form, or for displaying policy details in the audit log.
- `paymethodrules/views/templates/admin/policyConditionBuilder.tpl`: The core template for rendering the dynamic condition builder interface within the policy add/edit form. It includes partials for individual conditions and groups.
- `paymethodrules/views/templates/admin/policyRuleCard.tpl`: Renders a single policy as a card or a row in a list, potentially used in the dashboard or a simplified policy view.
- `paymethodrules/views/templates/admin/policyRulesTable.tpl`: Renders the main table of policies on the `AdminPaymethodrulesPolicies` screen.
- `paymethodrules/views/templates/admin/scopeSelector.tpl`: A reusable template for selecting scope (e.g., shop, language) within admin forms.

#### Front-office templates (`views/templates/front/`)

- No dedicated front-office page templates are listed, indicating that the module primarily integrates into existing checkout templates by modifying data, rather than rendering entirely new pages.

### 4.7 Database Schema & Hooks Map

#### Database Tables

- `ps_paymethodrules_policy`: Stores the main policy definitions, including name, status, affected payment methods, policy type, unavailable messages (multilingual), and the JSON representation of the condition tree.
- `ps_paymethodrules_log`: Stores audit log entries, including `id_cart`, `id_customer`, `context_data`, `policies_applied`, `payment_methods_before`, `payment_methods_after`, and `date_add`.
- (Potentially) `ps_paymethodrules_condition` and `ps_paymethodrules_condition_group` if the condition tree is stored in a normalized way rather than entirely as JSON within `ps_paymethodrules_policy`. The `install.sql` file will confirm this.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionPaymentOptionsModifier` | During the checkout process, before payment methods are displayed. | **Primary hook:** The module’s `PaymethodrulesEngine` is invoked here to filter and modify the array of available payment options based on active policies and the current cart context. |
| `displayBackOfficeHeader` | On every Back Office page load. | Injects module-specific CSS and JS for admin controllers (e.g., `admin_paymethodrules.css`, `adminConditionBuilder.js`). |
| `displayHeader` | On every front-office page load. | Injects module-specific CSS and JS for the front office (e.g., `front.css`, `checkout.js`, `unavailableUi.js`), particularly on the checkout page. |
| `moduleRoutes` | During PrestaShop’s route compilation. | Registers custom front-office and back-office routes for the module’s controllers (e.g., `/module/paymethodrules/simulate`). |
| `actionAdminControllerSetMedia` | When an admin controller is loaded. | Injects module-specific CSS and JS for the current admin controller, ensuring assets are loaded only when needed. |
| `actionObject*AddAfter` / `actionObject*UpdateAfter` | After an object (e.g., `Cart`, `Customer`) is added or updated. | Potentially used to clear internal caches or trigger re-evaluation if the module maintains any cached data. |
| `displayAdminProductsExtra` (or similar) | On product edit page in BO. | Could be used to add product-specific conditions directly on the product page, though not explicitly mentioned in the file list. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Conditional Payment Method Rules” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist merchants and developers with any issues or questions regarding the module’s functionality and integration.
