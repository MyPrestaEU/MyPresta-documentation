---
title: "Conditional Optional Order Services - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Conditional Optional Order Services PrestaShop module by MyPresta.eu."
sidebar:
  label: "Conditional Optional Order Services - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Conditional Optional Order Services Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/conditional-optional-order-services.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/conditional-optional-order-services/)
>
> ---


# Conditional Optional Order Services

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required, which are typically available on most modern hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The “Conditional Optional Order Services” module offers a powerful set of tools to manage your optional services. You’ll primarily interact with the module through its dedicated menu entries in your PrestaShop Back Office.

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the initial screen you see after installing the module or clicking “Configure” from the Module Manager. It provides a quick way to enable or disable the module’s core functionality.

- **Setting Name:** Enable Conditional Optional Order Services
- **What this setting does:** This is the master switch for the entire module. When enabled, the module’s logic will run, and your defined services will be offered to customers based on your policies. When disabled, no services will be offered, and the module will effectively be inactive on your front-office.
- **Effect of changing this setting:**
  - *When enabled:* The module will start evaluating your service policies and displaying relevant services to customers in the front-office (e.g., checkout page).
  - *When disabled:* All conditional services will be hidden from customers, and the module’s logic will not execute.
- **Recommended value:** **YES** (Enabled) once you have configured your policies.
- **Merchant scenario / example:** You’ve just installed the module and are ready to start defining your services. You would enable this setting to make your services visible to customers once they are configured. If you need to temporarily stop offering all services (e.g., during maintenance or a holiday period), you can quickly disable it here without deleting your policies.

### 2.2 Dedicated Admin Screens & Controller Views

After the initial configuration, you’ll find new menu entries under **Sell > Order Services** (or a similar location, depending on your PrestaShop version and theme).

#### 2.2.1 Policies (Back Office > Sell > Order Services > Policies)

This is where you define and manage all your conditional optional order services. Each “Policy” represents a specific service you want to offer, along with the rules that determine when and to whom it’s offered.

- **Screen Name & Menu Location:** Policies (Under **Sell > Order Services** in the main PrestaShop menu).
- **Available Actions & Settings:**

  - **Policy List:** A table displaying all your created policies, showing their name, status (active/inactive), and other key information.
  - **Add New Policy:** Click this button to create a brand new optional service.
  - **Edit Policy:** Click the “Edit” icon next to an existing policy to modify its details, conditions, and rules.
  - **Duplicate Policy:** A very useful feature! Click the “Duplicate” icon to create an exact copy of an existing policy. This saves time if you need to create similar services.
  - **Delete Policy:** Remove a policy permanently.
  - **Bulk Actions:** Select multiple policies and perform actions like “Enable,” “Disable,” or “Delete” them simultaneously.
- **When adding/editing a Policy, you’ll configure:**

  - **General Information:**
    - **Name:** A clear, internal name for your policy (e.g., “Gift Wrapping Service,” “Express Shipping Insurance”).
    - **Status:** Enable or disable this specific policy. An inactive policy will never be shown to customers.
    - **Description:** The text customers will see explaining the service. Be concise and highlight benefits.
    - **Price:** The cost of this optional service. This will be added to the customer’s cart if selected.
    - **Tax Rule:** Select the applicable tax rule for this service (e.g., “Standard Rate,” “Reduced Rate”).
    - **Image/Icon:** Upload an image or icon to visually represent the service to customers. This makes it more appealing and easier to identify.
  - **Conditions:** This is the core of the module’s power. Here you build rules using a visual condition builder to determine *when* this service should be offered.
    - You can combine multiple conditions using “AND” or “OR” logic.
    - **Examples of conditions:**
      - **Cart Value:** Offer service only if cart total is above/below a certain amount.
      - **Product in Cart:** Offer service only if specific products or products from certain categories/manufacturers are in the cart.
      - **Customer Group:** Offer service only to specific customer groups (e.g., “Wholesalers,” “VIP Customers”).
      - **Shipping Carrier:** Offer service only if a specific shipping carrier is selected.
      - **Date Range:** Offer service only during a specific promotional period.
      - **Country/Zone:** Offer service only to customers from certain countries or shipping zones.
  - **Display Settings:** Control how the service appears on the front-office.
    - **Position:** If multiple services are offered, you can set their display order.
    - **Visibility:** Where exactly in the checkout process the service appears.
- **Effect of changes:**

  - Adding a new policy makes a new optional service available for display to customers, subject to its conditions.
  - Editing a policy changes its name, price, description, image, or the conditions under which it’s offered. These changes are immediately reflected in the front-office.
  - Enabling/disabling a policy controls its visibility to customers.
  - Deleting a policy removes it entirely, and it will no longer be offered.
- **Recommended workflow for daily store management:**

  1. Start by defining your most common services (e.g., gift wrapping, insurance).
  2. Use the condition builder to make these services highly relevant. For example, gift wrapping might only be offered for physical products, not digital downloads.
  3. Regularly review your policies, especially before promotions or seasonal sales, to ensure they are active and correctly configured.
  4. Utilize the “Duplicate” feature to quickly create variations of existing services (e.g., “Premium Gift Wrapping” vs. “Standard Gift Wrapping”).

#### 2.2.2 Audit Log (Back Office > Sell > Order Services > Audit Log)

This screen provides a detailed history of all actions related to the module’s policies and services. It’s an invaluable tool for tracking changes and troubleshooting.

- **Screen Name & Menu Location:** Audit Log (Under **Sell > Order Services** in the main PrestaShop menu).
- **Available Actions & Settings:**
  - **Log List:** A table showing a chronological list of events.
  - **Columns typically include:**
    - **Date:** When the event occurred.
    - **Employee:** Which Back Office user performed the action.
    - **Action:** What action was taken (e.g., “Policy Added,” “Policy Edited,” “Policy Deleted,” “Module Enabled/Disabled”).
    - **Details:** Specific information about the change (e.g., which policy was affected, what values were changed).
  - **Filtering/Searching:** Tools to filter the log by date, employee, or action type to find specific events.
- **Effect of changes:** This screen is for viewing only; you cannot make direct changes here. It serves as a record of all modifications made to the module’s configuration and policies.
- **Recommended workflow for daily store management:**
  - Use the audit log to track who made changes to your service policies, especially in multi-user environments.
  - If a service isn’t appearing as expected, check the audit log to see if a policy was accidentally disabled or modified.
  - Monitor for any unexpected module behavior recorded in the logs.

#### 2.2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Enable Conditional Optional Order Services | YES (after setup) | Master switch for the module’s front-office functionality. |
| **Policies (List)** | Add New Policy | N/A | Create a new optional service with its own rules and pricing. |
| **Policies (List)** | Edit Policy | N/A | Modify an existing service’s details, conditions, or display. |
| **Policies (List)** | Duplicate Policy | N/A | Quickly create a copy of an existing policy to save time. |
| **Policies (List)** | Delete Policy | N/A | Permanently remove an optional service. |
| **Policies (Edit Form)** | Name | Descriptive Name | Internal identifier for the service. |
| **Policies (Edit Form)** | Status | Enabled | Controls if this specific service is active and visible to customers. |
| **Policies (Edit Form)** | Description | Clear explanation | Text displayed to customers about the service. |
| **Policies (Edit Form)** | Price | 0.00 (set value) | Cost added to cart if service is selected. |
| **Policies (Edit Form)** | Tax Rule | Default Tax Rule | Applicable tax for the service. |
| **Policies (Edit Form)** | Image/Icon | Uploaded image | Visual representation of the service for customers. |
| **Policies (Edit Form)** | Conditions (Builder) | Custom rules | Defines *when* and *to whom* the service is offered (e.g., cart value, product in cart, customer group). |
| **Policies (Edit Form)** | Position | Auto (set value) | Order of display if multiple services are offered. |
| **Audit Log** | (All entries) | N/A | Provides a historical record of all changes made to module settings and policies. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My optional services aren’t showing up on the checkout page. What should I check?**
A1:

1. **Module Enabled?** Go to **Modules > Module Manager**, find “Conditional Optional Order Services,” and ensure it’s enabled.
2. **Policy Status?** Go to **Sell > Order Services > Policies**. Make sure the specific policy you expect to see is “Active.”
3. **Policy Conditions Met?** This is the most common reason. Carefully review the conditions you’ve set for the policy. Is your current test cart meeting *all* the “AND” conditions and *any* of the “OR” conditions? For example, if you set “Cart Total > $50” and your cart is $45, the service won’t show.
4. **Cache?** Clear your PrestaShop cache under **Advanced Parameters > Performance**. Sometimes, old cached data can prevent new module configurations from appearing.
5. **Theme Compatibility?** While the module is designed for broad compatibility, very heavily customized themes might require minor adjustments. Check your browser’s developer console for JavaScript errors.

**Q2: The price of my service isn’t being added correctly to the cart total.**
A2:

1. **Policy Price Set?** Double-check the “Price” field in your policy configuration.
2. **Tax Rule Applied?** Ensure the correct “Tax Rule” is selected for the service. The final price includes taxes based on this rule.
3. **Currency?** Verify that the price is set in your store’s default currency or that multi-currency settings are correctly handled by PrestaShop.

**Q3: How do I translate the service names and descriptions into other languages?**
A3:

1. Go to **International > Translations** in your PrestaShop Back Office.
2. Select “Installed modules translations,” choose your theme, and then select your language.
3. Find the “Conditional Optional Order Services” module. You should be able to translate the names and descriptions of your policies directly within the module’s configuration forms, as they are usually stored as translatable fields. If not, they will appear here.

**Q4: Can I change the order in which services appear on the checkout page?**
A4: Yes, within each policy’s configuration, there should be a “Position” setting. You can set a numerical value (e.g., 10, 20, 30) to control the display order. Lower numbers appear first.

**Q5: The module is causing a visual issue or conflict with another module.**
A5:

1. **Isolate the issue:** Temporarily disable other recently installed or updated modules to see if the conflict disappears.
2. **Check for errors:** Use your browser’s developer console (F12) to look for JavaScript or CSS errors.
3. **Contact Support:** If you can’t resolve it, provide MyPresta.eu support with details about the issue, your PrestaShop version, and any other modules you suspect might be conflicting.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the “Conditional Optional Order Services” module, intended for developers and webmasters.

### 4.1 Architecture Overview

The module follows a robust MVC (Model-View-Controller) pattern typical for PrestaShop modules. It heavily relies on PrestaShop’s hook system to inject its functionality at various points in the front-office (checkout, product page) and back-office (admin order view, module configuration).
Key architectural components include:

- **Policies (`conorderservicesPolicy`):** The core entity representing an optional service, extending `ObjectModel`.
- **Conditions (`conorderservicesCondition`, `conorderservicesConditionGroup`, `conorderservicesConditionTree`):** A sophisticated system for building complex rules to determine service eligibility.
- **Engine (`conorderservicesEngine`):** The central class responsible for evaluating conditions and determining which services to present to the customer.
- **Audit Log (`conorderservicesAuditLog`):** Records all significant actions within the module for traceability.
- **Compatibility Layer (`conorderservicesCompatibility`):** Handles differences between PrestaShop 1.7, 8, and 9.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `conorderservices/controllers/front/ajax.php`
  - **Class Name:** `ConorderservicesAjaxModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** Handles AJAX requests from the front-office, primarily for dynamically updating service selections or recalculating cart totals when a service is added/removed by the customer. It likely dispatches to the `conorderservicesEngine` to perform calculations and returns JSON responses.
- `conorderservices/controllers/front/index.php`
  - **Class Name:** `ConorderservicesIndexModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** A placeholder or fallback controller. Often used for direct module access if needed, though most front-office interaction is via hooks or AJAX.

#### Back-Office Admin Controllers

- `conorderservices/controllers/admin/AdminconorderservicesAuditLog.php`
  - **Class Name:** `AdminconorderservicesAuditLogController` (extends `ModuleAdminController`)
  - **Tab Name:** Audit Log (under “Sell > Order Services”)
  - **Managed Entity:** `conorderservicesAuditLog`
  - **Responsibility:** Manages the display and filtering of the audit log entries. It uses PrestaShop’s `HelperList` to render the log table.
- `conorderservices/controllers/admin/AdminconorderservicesPolicies.php`
  - **Class Name:** `AdminconorderservicesPoliciesController` (extends `ModuleAdminController`)
  - **Tab Name:** Policies (under “Sell > Order Services”)
  - **Managed Entity:** `conorderservicesPolicy`
  - **Responsibility:** The primary controller for managing optional service policies. It handles listing, adding, editing, duplicating, and deleting `conorderservicesPolicy` objects. It uses `HelperList` for the policy list and `HelperForm` for the add/edit policy forms, including the complex condition builder.
- `conorderservices/controllers/admin/index.php`
  - **Class Name:** `AdminconorderservicesIndexController` (extends `ModuleAdminController`)
  - **Tab Name:** (Likely the main “Order Services” entry point)
  - **Managed Entity:** None directly, often redirects to `AdminconorderservicesPolicies` or displays a dashboard.
  - **Responsibility:** Serves as the main entry point for the module’s admin section, potentially displaying a dashboard or redirecting to the policies list.

### 4.3 Core Classes & Models (`classes/`)

- `conorderservices/classes/conorderservicesAdmin.php`
  - **Purpose:** Utility class for admin-specific functions, potentially handling permissions, menu generation, or common admin tasks.
- `conorderservices/classes/conorderservicesAuditLog.php`
  - **Extends:** `ObjectModel`
  - **Database Table:** `ps_conorderservices_log`
  - **`$definition` fields:** `id_conorderservices_log`, `id_employee`, `action`, `details`, `date_add`
  - **Purpose:** Represents an entry in the module’s audit log. Provides methods for adding new log entries.
- `conorderservices/classes/conorderservicesCartState.php`
  - **Purpose:** Manages and persists the state of selected optional services within the customer’s cart. Likely interacts with `Context::getContext()->cart` and stores service selections.
- `conorderservices/classes/conorderservicesCompatibility.php`
  - **Purpose:** Provides a layer of abstraction for PrestaShop version-specific functions or behaviors, ensuring the module works across 1.7, 8, and 9.
- `conorderservices/classes/conorderservicesCondition.php`
  - **Extends:** `ObjectModel` (likely, or a base class for conditions)
  - **Database Table:** `ps_conorderservices_condition`
  - **`$definition` fields:** `id_conorderservices_condition`, `id_conorderservices_condition_group`, `type`, `operator`, `value`
  - **Purpose:** Represents a single condition within a condition group (e.g., “Cart Total” “is greater than” “100”).
- `conorderservices/classes/conorderservicesConditionEvaluator.php`
  - **Purpose:** The logic engine for evaluating a set of conditions against the current cart, customer, and product context. Determines if a policy’s conditions are met.
- `conorderservices/classes/conorderservicesConditionGroup.php`
  - **Extends:** `ObjectModel` (likely)
  - **Database Table:** `ps_conorderservices_condition_group`
  - **`$definition` fields:** `id_conorderservices_condition_group`, `id_conorderservices_policy`, `logic_operator` (AND/OR)
  - **Purpose:** Groups multiple `conorderservicesCondition` objects together, defining the logical relationship between them (AND/OR).
- `conorderservices/classes/conorderservicesConditionTree.php`
  - **Purpose:** Manages the hierarchical structure of condition groups and individual conditions, allowing for complex rule building.
- `conorderservices/classes/conorderservicesContext.php`
  - **Purpose:** A wrapper or extension of PrestaShop’s `Context` class, providing module-specific context data (e.g., current cart, customer, language) for condition evaluation.
- `conorderservices/classes/conorderservicesDashboard.php`
  - **Purpose:** Provides data and logic for the module’s dashboard view (if any), potentially showing analytics or quick stats.
- `conorderservices/classes/conorderservicesEngine.php`
  - **Purpose:** The central processing unit of the module. It retrieves active policies, passes them to the `ConditionEvaluator`, and determines which services are eligible for the current cart. It also handles adding/removing service products from the cart.
- `conorderservices/classes/conorderservicesListRenderer.php`
  - **Purpose:** Helper class for rendering lists in the Back Office, potentially extending `HelperList` or providing custom rendering logic.
- `conorderservices/classes/conorderservicesLog.php`
  - **Purpose:** Alias or specific implementation for logging, possibly distinct from `conorderservicesAuditLog` for different types of logging.
- `conorderservices/classes/conorderservicesPolicy.php`
  - **Extends:** `ObjectModel`
  - **Database Table:** `ps_conorderservices_policy`
  - **`$definition` fields:** `id_conorderservices_policy`, `name`, `description`, `price`, `id_tax_rule`, `image`, `active`, `position`, `date_add`, `date_upd` (and `_lang` fields for translatable `name`, `description`).
  - **Purpose:** The core model for an optional service. Stores all configuration for a service, including its details, price, image, and associated condition groups.
- `conorderservices/classes/conorderservicesPolicyDuplicator.php`
  - **Purpose:** Handles the logic for duplicating an entire policy, including its conditions and associated data.
- `conorderservices/classes/conorderservicesPreset.php`
  - **Purpose:** Likely provides predefined sets of conditions or policies that can be quickly loaded by the merchant.
- `conorderservices/classes/conorderservicesRule.php`
  - **Purpose:** A more generic term for a condition or a set of conditions. Could be an abstract base class or a specific type of rule.
- `conorderservices/classes/ConorderservicesRuleImage.php`
  - **Purpose:** Manages the images/icons associated with policies or rules.
- `conorderservices/classes/ConorderservicesServiceProduct.php`
  - **Extends:** `Product` (or a wrapper around it)
  - **Purpose:** Represents the “virtual product” that is added to the cart when a customer selects an optional service. It ensures the service behaves like a regular product for cart and order processing.
- `conorderservices/classes/conorderservicesTreeRepository.php`
  - **Purpose:** Manages the storage and retrieval of the condition tree structure.
- `conorderservices/classes/index.php`
  - **Purpose:** Standard empty file to prevent directory listing.
- `conorderservices/classes/load.php`
  - **Purpose:** Autoloading file or a file that includes other class definitions.

### 4.4 JavaScript Assets (`views/js/`)

- `conorderservices/lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Back-office (for product/category selection in condition builder)
  - **Details:** Provides autocomplete functionality for input fields, likely used when selecting products, categories, or manufacturers within the condition builder.
- `conorderservices/lib/searchTool/views/views/js/autocomplete.js`
  - **Scope:** Back-office (redundant or specific to a different view of the search tool)
  - **Details:** Similar to the above, likely a duplicate or specific version of the autocomplete script.
- `conorderservices/views/js/adminConditionBuilder.js`
  - **Scope:** Back-office (AdminconorderservicesPoliciesController)
  - **Details:** Core JS for the visual condition builder. Handles adding/removing conditions and condition groups, managing logic operators (AND/OR), and updating the UI based on user input.
- `conorderservices/views/js/adminconorderservicesDashboard.js`
  - **Scope:** Back-office (AdminconorderservicesIndexController or Dashboard view)
  - **Details:** Scripts for interactive elements on the module’s dashboard, such as charts, statistics, or quick links.
- `conorderservices/views/js/adminconorderservicesSearchTool.js`
  - **Scope:** Back-office (AdminconorderservicesPoliciesController)
  - **Details:** Integrates the search tool (autocomplete) with the condition builder, allowing administrators to easily find and select entities (products, categories, etc.) for conditions.
- `conorderservices/views/js/adminconorderservicesSimulator.js`
  - **Scope:** Back-office (AdminconorderservicesPoliciesController - likely a dedicated tab or modal)
  - **Details:** Provides functionality for a policy simulator, allowing administrators to test conditions with mock cart data to see which services would be offered.
- `conorderservices/views/js/adminPolicyRuleImage.js`
  - **Scope:** Back-office (AdminconorderservicesPoliciesController)
  - **Details:** Handles image upload and preview functionality for policy icons/images.
- `conorderservices/views/js/adminPolicyRules.js`
  - **Scope:** Back-office (AdminconorderservicesPoliciesController)
  - **Details:** General scripts for managing policy rules, potentially including drag-and-drop reordering or other UI interactions on the policy edit page.
- `conorderservices/views/js/adminSettingsOfferDisplay.js`
  - **Scope:** Back-office (Module Main Configuration or Policy Edit)
  - **Details:** Scripts related to configuring how and where the optional services are displayed on the front-office.
- `conorderservices/views/js/checkout.js`
  - **Scope:** Front-office (Checkout page)
  - **Details:** This is the critical front-office script. It listens for user interactions (e.g., checking/unchecking a service), sends AJAX requests to `ajax.php` to update the cart, and dynamically updates the cart summary and total on the checkout page. It likely binds to `prestashop.on` events for cart updates.

### 4.5 CSS Stylesheets (`views/css/`)

- `conorderservices/lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Back-office
  - **Details:** Styles for the autocomplete dropdowns and input fields used in the admin search tool.
- `conorderservices/lib/searchTool/views/views/css/autocomplete.css`
  - **Scope:** Back-office (redundant or specific to a different view of the search tool)
  - **Details:** Similar to the above, likely a duplicate or specific version of the autocomplete styles.
- `conorderservices/views/css/admin_conorderservices.css`
  - **Scope:** Back-office
  - **Details:** General styling for the module’s admin pages, including the policy list, condition builder, and audit log. Contains styles for form elements, tables, and custom UI components.
- `conorderservices/views/css/front.css`
  - **Scope:** Front-office
  - **Details:** Styles for how the optional services are displayed on the checkout page. Includes styling for the service block, individual service rows, checkboxes, prices, and icons. Developers can override these classes in their theme’s `custom.css` or `theme.css`.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `conorderservices/views/templates/hook/admin_order.tpl`
  - **Hook:** `displayAdminOrder`
  - **Output:** Displays information about selected optional services within the PrestaShop Back Office order view. This allows administrators to see which services were purchased with an order.
- `conorderservices/views/templates/hook/checkout_services.tpl`
  - **Hook:** `displayShoppingCart`, `displayShoppingCartFooter` (or similar checkout hooks)
  - **Output:** The main template for rendering the list of available optional services on the front-office checkout page. It iterates through eligible policies and displays them.
- `conorderservices/views/templates/hook/partials/checkout_offer_row.tpl`
  - **Hook:** Included by `checkout_services.tpl`
  - **Output:** Renders a single row or card for an optional service within the checkout list, including its name, description, price, and selection input (e.g., checkbox).

#### Admin templates (`views/templates/admin/`)

- `conorderservices/views/templates/admin/auditPreview.tpl`
  - **Purpose:** Renders a detailed view or preview of an audit log entry.
- `conorderservices/views/templates/admin/dashboard.tpl`
  - **Purpose:** The main template for the module’s dashboard in the Back Office, potentially displaying analytics or summary information.
- `conorderservices/views/templates/admin/helpers/list/list_action_duplicate.tpl`
  - **Purpose:** Custom template for the “Duplicate” action button in `HelperList` views (specifically for policies).
- `conorderservices/views/templates/admin/policiesPreview.tpl`
  - **Purpose:** Renders a preview of a policy, potentially used in a simulator or quick view.
- `conorderservices/views/templates/admin/policyConditionBuilder.tpl`
  - **Purpose:** The template for the visual condition builder interface within the policy edit form. This is a complex template that dynamically adds/removes condition groups and individual conditions.
- `conorderservices/views/templates/admin/policyRuleCard.tpl`
  - **Purpose:** Renders a single rule or condition group as a card within the condition builder, making it visually distinct.
- `conorderservices/views/templates/admin/policyRulesTable.tpl`
  - **Purpose:** Renders a table-like structure for displaying rules, possibly an alternative or component within the condition builder.
- `conorderservices/views/templates/admin/scopeSelector.tpl`
  - **Purpose:** Template for selecting the scope of a condition (e.g., product, category, customer).

#### Library Templates (`conorderservices/lib/searchTool/views/`)

- `conorderservices/lib/searchTool/views/helpers.tpl`
  - **Purpose:** Helper templates for the search tool, possibly for rendering search results or input fields.
- `conorderservices/lib/searchTool/views/scripts.tpl`
  - **Purpose:** Includes JavaScript for the search tool.
- `conorderservices/lib/searchTool/views/views/scripts.tpl`
  - **Purpose:** Duplicate or specific version of search tool scripts.

### 4.7 Database Schema & Hooks Map

#### Database Tables

- `ps_conorderservices_policy`
  - Stores core policy information: `id_conorderservices_policy`, `name`, `description`, `price`, `id_tax_rule`, `image`, `active`, `position`, `date_add`, `date_upd`.
  - Also includes language-specific fields for `name` and `description` (e.g., `ps_conorderservices_policy_lang`).
- `ps_conorderservices_condition_group`
  - Stores condition groups: `id_conorderservices_condition_group`, `id_conorderservices_policy`, `logic_operator` (AND/OR).
- `ps_conorderservices_condition`
  - Stores individual conditions: `id_conorderservices_condition`, `id_conorderservices_condition_group`, `type`, `operator`, `value`.
- `ps_conorderservices_log`
  - Stores audit log entries: `id_conorderservices_log`, `id_employee`, `action`, `details`, `date_add`.
- `ps_conorderservices_cart_state` (likely)
  - Stores which services are selected for a given cart: `id_cart`, `id_conorderservices_policy`, `date_add`.
- `ps_configuration`
  - `CONORDERSERVICES_ENABLED`: Stores the module’s master enable/disable status.
  - `PS_CURRENCY_DEFAULT`: Used for displaying prices in the admin.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `ActionObjectProductInCartDeleteBefore` | Before a product is deleted from the cart. | Ensures that if a product required for a service is removed, the service is also removed or re-evaluated. |
| `actionPresentCart` | When the cart data is presented (e.g., on checkout page). | Injects the list of eligible optional services into the cart presentation data. |
| `ActionAdminControllerSetMedia` | When an admin controller is loaded and its media (JS/CSS) is set. | Injects module-specific JS and CSS for Back Office pages (policies, audit log, condition builder). |
| `ActionPresentProductListing` | When product data is presented in a listing (e.g., category page). | Potentially used to display service availability indicators on product listings. |
| `ActionValidateOrderBefore` | Before an order is validated. | Performs final checks on selected services, ensures they are still valid, and adds them as order details. |
| `ActionGetProductPropertiesAfter` | After product properties are retrieved. | Potentially modifies product properties if a service affects them (e.g., adding a virtual product for the service). |
| `DisplayAdminOrder` | On the Back Office order detail page. | Displays the selected optional services associated with the order. |
| `ActionFrontControllerInitAfter` | After a front controller is initialized. | Initializes module-specific front-office context or logic. |
| `ActionPresentProduct` | When a single product’s data is presented (e.g., product page). | Potentially used to display service availability indicators on product pages. |
| `ActionPresentCartProduct` | When a product in the cart is presented. | Modifies the presentation of cart products if services are attached to them. |
| `ActionProductPriceCalculation` | During product price calculation. | Ensures that service prices are correctly factored into the total. |
| `DisplayShoppingCart` | On the shopping cart page. | Displays the block of optional services. |
| `DisplayShoppingCartFooter` | In the footer of the shopping cart page. | Alternative or additional placement for the optional services block. |
| `ActionCartSave` | After a cart is saved. | Persists the state of selected optional services in the cart. |
| `ActionValidateOrder` | After an order has been validated. | Finalizes the order with the selected services, potentially updating inventory or triggering follow-up actions. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Conditional Optional Order Services” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu). Our support team is available to assist you with any issues or questions regarding the module’s functionality and compatibility.
