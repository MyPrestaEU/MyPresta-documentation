---
title: "Split cart into separate shipments - Merchant Manual & Configuration Guide"
description: ""
sidebar:
  label: "Split cart into separate shipments - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Split cart into separate shipments Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/split-cart-into-separate-shipments.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/split-cart-into-separate-shipments/)
>
> ---


# Split cart into separate shipments

## 1. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The “Split cart into separate shipments” module introduces several powerful new screens and options in your PrestaShop Back Office.

### 1.1 Module Configuration Page (Back Office > Modules > Configure > Split cart into separate shipments)

This is the main configuration page you access immediately after installation or by clicking “Configure” from the Module Manager. It contains general settings for the module’s behavior.

- **Enable Module:**

  - **What this setting does:** This is the master switch to turn the module’s functionality on or off across your store.
  - **Effect of changing this setting:**
    - *When enabled:* The module will actively split carts according to your rules during checkout.
    - *When disabled:* The module’s splitting logic will be bypassed, and PrestaShop will revert to its default single-shipment behavior.
  - **Recommended value:** YES (once you’ve configured your rules).
  - **Merchant scenario / example:** You might disable it temporarily if you are performing maintenance or troubleshooting other parts of your checkout process.
- **Debug Mode:**

  - **What this setting does:** Activates a special mode that can display additional technical information or logs to help identify issues.
  - **Effect of changing this setting:**
    - *When enabled:* May show error messages or detailed processing steps on the front office (visible to customers) or in your browser’s developer console. This is useful for developers.
    - *When disabled:* The module operates silently, without displaying debug information.
  - **Recommended value:** NO (always disable in a live production store).
  - **Merchant scenario / example:** If you’re working with a developer to understand why a specific cart isn’t splitting as expected, they might ask you to enable this temporarily.
- **Display Split Summary on Order Confirmation Page:**

  - **What this setting does:** Controls whether customers see a summary of how their order was split into different shipments on the final order confirmation page.
  - **Effect of changing this setting:**
    - *When enabled:* Customers will see a clear breakdown of which items went into which shipment group and the chosen carrier for each, confirming their selections.
    - *When disabled:* The order confirmation page will show a standard summary without the detailed split information.
  - **Recommended value:** YES.
  - **Merchant scenario / example:** Enabling this improves transparency and reassures customers that their specific shipping choices for each package were correctly applied.
- **Allow Customer to Choose Pickup Points (if applicable):**

  - **What this setting does:** If you have carriers that offer pickup point delivery (e.g., Mondial Relay, Colissimo Point Relais), this setting enables customers to select a specific pickup location for each relevant shipment group.
  - **Effect of changing this setting:**
    - *When enabled:* For carriers configured with pickup points, customers will see an option to choose a pickup location during checkout for the corresponding shipment.
    - *When disabled:* Customers will only be able to select home delivery or other standard shipping options, even if carriers support pickup points.
  - **Recommended value:** YES (if you use carriers with pickup points).
  - **Merchant scenario / example:** If you offer Mondial Relay, enabling this allows customers to have a heavy item delivered to a convenient pickup point near their home or work, improving their experience.

### 1.2 Dedicated Admin Screens: Shipping Rules (Back Office > Shipping > Shipment Splitting Rules)

This screen is where you define the logic for how your cart items should be grouped into separate shipments. It’s the core of the module’s functionality.

- **Screen Name & Menu Location:** **Shipment Splitting Rules** (found under **Shipping** in your PrestaShop Back Office menu).
- **Available Actions & Settings:**
  - **Rule Listing Table:** Displays all your defined grouping rules. Each rule has a name, status (active/inactive), priority, and a summary of its conditions and actions.
  - **“Add New Rule” Button:** Clicking this allows you to create a new rule.
  - **Edit/Delete Actions:** For each rule in the list, you can edit its details or delete it.
  - **Enable/Disable Toggle:** Quickly activate or deactivate a rule without deleting it.
  - **Drag-and-Drop Reordering:** Rules are processed in order of their priority. You can drag and drop rules to change their execution order. Higher priority rules are processed first.
- **Effect of changes:**
  - **Adding/Editing Rules:** Directly impacts how carts are split during checkout. A well-defined rule can ensure specific products always ship separately or together.
  - **Enabling/Disabling Rules:** Controls whether a rule’s logic is applied.
  - **Changing Priority:** Determines which rule takes precedence if multiple rules could apply to the same product. Rules with higher priority (appearing higher in the list) are evaluated first.
- **Recommended workflow for daily store management:**
  1. **Identify Grouping Needs:** Think about your products. Do you have oversized items, fragile items, items from different warehouses, or items that require special handling?
  2. **Create Rules:** For each grouping need, create a new rule.
     - **Conditions:** Define *when* the rule applies. This could be based on:
       - **Product:** Specific products, categories, manufacturers, suppliers, or product features.
       - **Cart:** Total cart value, number of items, specific customer groups.
       - **Shipping:** Specific carriers or zones.
     - **Actions:** Define *what* the rule does. This could be:
       - **Force Separate Shipment:** Always put the matched items into their own shipment group.
       - **Force Same Shipment:** Ensure matched items always stay together in one shipment.
       - **Exclude from Rule Processing:** Prevent other rules from affecting these items.
  3. **Set Priority:** Arrange your rules from most specific (e.g., “Fragile Glassware always ships alone”) to most general (e.g., “All oversized items ship separately”).
  4. **Test Thoroughly:** Use a test customer account to add various combinations of products to the cart and verify that the splitting works as expected during checkout.

### 1.3 Dedicated Admin Screens: Shipment Groups (Back Office > Shipping > Shipment Splits)

This screen provides an overview of how orders have been split by the module after they have been placed. It’s a reporting and management tool.

- **Screen Name & Menu Location:** **Shipment Splits** (found under **Shipping** in your PrestaShop Back Office menu).
- **Available Actions & Settings:**
  - **Split Listing Table:** Shows a list of all orders that have been split by the module.
  - **Order Reference:** Links directly to the original PrestaShop order.
  - **Shipment Group Details:** Provides information about each individual shipment group within an order, including the products it contains, the chosen carrier, and its status.
  - **View Split Details:** Allows you to drill down into a specific split to see more granular information.
- **Effect of changes:** This screen is primarily for viewing and auditing. You don’t directly change how future carts are split here. Any changes you make (e.g., updating a carrier for a specific split) would typically be done within the main PrestaShop order view, and this module would reflect those changes.
- **Recommended workflow for daily store management:**
  - **Monitor Split Orders:** Regularly check this screen to understand how your rules are working in practice.
  - **Troubleshoot:** If a customer has a question about their shipping, this screen can help you quickly see how their order was processed into different shipments.
  - **Integration with Order Management:** While the module creates standard PrestaShop orders, this screen offers a consolidated view of the split logic applied to each order.

### 1.4 Dedicated Admin Screens: Dashboard (Back Office > Shipping > Shipment Splitting Dashboard)

This screen provides a quick overview and statistics related to the module’s activity.

- **Screen Name & Menu Location:** **Shipment Splitting Dashboard** (found under **Shipping** in your PrestaShop Back Office menu).
- **Available Actions & Settings:**
  - **KPI Strip:** Key Performance Indicators (KPIs) like total split orders, average shipments per order, or total shipping revenue from split orders.
  - **Charts & Graphs:** Visual representations of trends, such as the number of split orders over time, most common splitting rules used, or popular carriers for split shipments.
  - **Recent Splits:** A quick list of the most recently split orders.
- **Effect of changes:** This is a reporting dashboard. No direct changes to module behavior are made here. It helps you understand the impact and usage of the module.
- **Recommended workflow for daily store management:**
  - **Performance Monitoring:** Use this dashboard to gauge the effectiveness of your splitting rules and identify any patterns or anomalies.
  - **Strategic Planning:** The data can inform decisions about shipping strategies, carrier partnerships, or product catalog adjustments.

### 1.5 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Enable Module | YES | Master switch for module functionality. |
|  | Debug Mode | NO | Displays technical info (for developers only). |
|  | Display Split Summary on Order Confirmation Page | YES | Shows customers how their order was split. |
|  | Allow Customer to Choose Pickup Points | YES (if applicable) | Enables pickup point selection for relevant carriers. |
| **Shipment Splitting Rules** | Add/Edit Rule (Conditions) | N/A | Defines *when* a rule applies (e.g., by product, category, cart value). |
|  | Add/Edit Rule (Actions) | N/A | Defines *what* the rule does (e.g., force separate shipment, force same shipment). |
|  | Rule Priority | N/A | Determines the order in which rules are processed (higher = first). |
|  | Enable/Disable Rule | N/A | Activates or deactivates a specific grouping rule. |
| **Shipment Splits** | View Split Orders | N/A | Provides a list and details of all orders processed by the module. |
| **Shipment Splitting Dashboard** | KPIs, Charts, Recent Splits | N/A | Offers an overview of module activity and performance. |

## 2. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

- **Q: My cart isn’t splitting, or it’s splitting incorrectly. What should I do?**

  - **A:** First, check if the module is enabled in its main configuration. Then, go to **Shipping > Shipment Splitting Rules** and review your rules. Ensure they are active, and their conditions correctly match the products in your test cart. Pay close attention to rule priority – a more general rule might be overriding a more specific one. If you have “Debug Mode” enabled in the module’s main configuration, check for any messages during checkout. Finally, clear your PrestaShop cache (**Advanced Parameters > Performance > Clear cache**).
- **Q: Why are some carriers not showing up for a specific shipment group?**

  - **A:** The module respects PrestaShop’s standard carrier restrictions. Check the following:
    1. **Carrier Zones:** Ensure the carrier is enabled for the customer’s shipping zone.
    2. **Carrier Weight/Price Ranges:** Verify that the total weight/price of the *individual shipment group* (not the whole cart) falls within the carrier’s defined ranges.
    3. **Carrier Associations:** Make sure the carrier is associated with the products in that shipment group (if you’ve set up product-specific carrier restrictions).
    4. **Module Compatibility:** Some third-party shipping modules might have their own logic that conflicts; check for any known incompatibilities or contact support.
- **Q: How does this module affect my existing shipping costs and free shipping rules?**

  - **A:** The module aggregates shipping costs. If a cart is split into two shipments, and each shipment has a cost of $10, the customer will see a total shipping cost of $20. For free shipping, your existing free shipping rules (e.g., “free shipping over $X”) will apply to *each individual shipment group* if the module allows it, or to the *overall cart total* depending on how your rules are configured and how the module integrates. You might need to adjust your free shipping rules to account for the split shipments.
- **Q: Can I translate the module’s texts into other languages?**

  - **A:** Yes, like most PrestaShop modules, you can translate its front-office and back-office texts. Go to **International > Translations**, select “Installed modules translations,” choose your theme, select “Split cart into separate shipments,” and then choose the language you want to translate.
- **Q: After installing, I see a blank page or an error. What’s wrong?**

  - **A:** This often indicates a PHP error.
    1. **Check PHP Error Logs:** Your web hosting control panel usually provides access to PHP error logs. Look for recent entries related to PrestaShop.
    2. **Enable PrestaShop Debug Mode:** Go to `config/defines.inc.php` in your PrestaShop installation, find `define('_PS_MODE_DEV_', false);` and change `false` to `true`. This will display the error on the screen.
    3. **Module Compatibility:** Ensure you downloaded the correct module version for your PrestaShop version (e.g., PS 8.x, 1.7.x).
    4. **Contact Support:** If you can’t resolve it, provide the error message to MyPresta.eu support.

## 3. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 3.1 Architecture Overview

The “Split cart into separate shipments” module (`multishipsplit`) is built following PrestaShop’s MVC (Model-View-Controller) pattern, with significant use of hooks and overrides to integrate deeply into the checkout process. It introduces a robust rule-based engine for cart splitting, allowing for complex conditions and actions. The core logic revolves around slicing the `Cart` object into multiple `MultishipShipmentGroup` entities, each representing a distinct package with its own carrier selection. It leverages `ObjectModel` for managing rules and split data, and employs a series of service classes to handle the intricate logic of condition evaluation, action building, and checkout presentation. Overrides are used to modify core `Cart` and `PaymentModule` behavior to support multiple shipments.

### 3.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `multishipsplit/controllers/front/groups.php`
  - **Class Name:** `MultishipsplitGroupsModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** Handles AJAX requests related to shipment groups during checkout. This might include updating carrier selections for a specific group, recalculating shipping costs, or fetching pickup point options. It processes `POST` data and returns JSON responses to the checkout page.
- `multishipsplit/controllers/front/index.php`
  - **Class Name:** `MultishipsplitIndexModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** A placeholder or entry point controller. It might be used for general module-related front-office actions or redirects, though its primary function might be minimal if most interactions are AJAX-driven through `groups.php`.
- `multishipsplit/controllers/front/pickup.php`
  - **Class Name:** `MultishipsplitPickupModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** Manages AJAX interactions specifically for pickup point selection. It likely handles requests to display available pickup points for a given carrier and address, and to save the selected pickup point to the cart or session.

#### Back-Office Admin Controllers

- `multishipsplit/controllers/admin/AdminMultishipRules.php`
  - **Class Name:** `AdminMultishipRulesController` (extends `ModuleAdminController`)
  - **Tab Name:** “Shipment Splitting Rules”
  - **Managed Entity:** `MultishipGroupingRule` (maps to `mss_grouping_rule` table)
  - **Responsibility:** Provides the CRUD (Create, Read, Update, Delete) interface for managing shipment grouping rules. It handles the display of the rule list, the form for adding/editing rules (including the condition and action builders), and saving/deleting rule data.
- `multishipsplit/controllers/admin/AdminMultishipSplits.php`
  - **Class Name:** `AdminMultishipSplitsController` (extends `ModuleAdminController`)
  - **Tab Name:** “Shipment Splits”
  - **Managed Entity:** `MultishipSplitGroup` (maps to `mss_split_group` table)
  - **Responsibility:** Displays a list of all orders that have been processed and split by the module. It provides a read-only view of the split groups within each order, linking back to the original PrestaShop order.
- `multishipsplit/controllers/admin/index.php`
  - **Class Name:** `MultishipsplitIndexModuleAdminController` (extends `ModuleAdminController`)
  - **Tab Name:** “Shipment Splitting Dashboard”
  - **Managed Entity:** N/A (dashboard view)
  - **Responsibility:** Serves as the dashboard controller, displaying KPIs, charts, and recent split orders. It aggregates data from the module’s tables to provide an overview of its activity.

### 3.3 Core Classes & Models (`classes/`)

- `multishipsplit/classes/MultishipActionBuilder.php`
  - **Responsibility:** A service class responsible for constructing and interpreting the actions defined within a `MultishipGroupingRule`. It translates the rule’s action configuration into executable logic.
- `multishipsplit/classes/MultishipCartSlicer.php`
  - **Responsibility:** The central class for the cart splitting logic. It takes a `Cart` object and, using the defined `MultishipGroupingRule`s, divides the cart’s products into an array of `MultishipShipmentGroup` objects.
- `multishipsplit/classes/MultishipCheckoutPresenter.php`
  - **Responsibility:** Prepares the data for the front-office checkout page. It takes the `MultishipShipmentGroup`s and formats them for display, including available carriers, costs, and pickup point options, to be rendered by Smarty templates.
- `multishipsplit/classes/MultishipCompatibility.php`
  - **Responsibility:** Handles compatibility layers for different PrestaShop versions or potential conflicts with other modules. It ensures the module functions correctly across various environments.
- `multishipsplit/classes/MultishipConditionBuilder.php`
  - **Responsibility:** Similar to `MultishipActionBuilder`, but for rule conditions. It constructs and interprets the conditions that determine when a `MultishipGroupingRule` should be applied.
- `multishipsplit/classes/MultishipConditionEvaluator.php`
  - **Responsibility:** Evaluates a set of conditions against a given context (e.g., a product, a cart, a customer) to determine if a rule should be triggered.
- `multishipsplit/classes/MultishipConditionTree.php`
  - **Responsibility:** Manages the hierarchical structure of conditions (e.g., AND/OR groups) within a rule, allowing for complex logical expressions.
- `multishipsplit/classes/MultishipConfirmationPresenter.php`
  - **Responsibility:** Prepares data for displaying the split summary on the order confirmation page.
- `multishipsplit/classes/MultishipDashboardPresenter.php`
  - **Responsibility:** Gathers and formats data for the Back Office dashboard, including KPIs and chart data.
- `multishipsplit/classes/MultishipGroupingEngine.php`
  - **Responsibility:** Orchestrates the entire rule-based grouping process. It fetches active rules, applies them sequentially (based on priority) to the cart, and manages the creation of `MultishipShipmentGroup`s.
- `multishipsplit/classes/MultishipGroupingRule.php`
  - **Extends:** `ObjectModel`
  - **Database Table:** `mss_grouping_rule`
  - **`$definition` fields:** Stores the configuration for each splitting rule, including its name, priority, active status, and serialized conditions and actions.
  - **Key public methods:** Methods for saving, loading, and managing rule data.
- `multishipsplit/classes/MultishipOrderLink.php`
  - **Extends:** `ObjectModel`
  - **Database Table:** `mss_order_link`
  - **`$definition` fields:** Links a PrestaShop `Order` to its corresponding `MultishipSplitGroup`s, allowing the module to track how an order was split.
  - **Key public methods:** Methods for creating and retrieving these links.
- `multishipsplit/classes/MultishipPaymentBridge.php`
  - **Responsibility:** Facilitates the payment process when a cart is split. It ensures that the total amount due for all shipment groups is correctly passed to the payment module and that payment confirmation correctly updates the status of all associated orders.
- `multishipsplit/classes/MultishipPayPlugRefundAdapter.php`
  - **Responsibility:** Provides specific integration for refunding split orders when using the PayPlug payment module. This suggests the module might have similar adapters for other payment gateways.
- `multishipsplit/classes/MultishipPickupFactory.php`
  - **Responsibility:** A factory class for creating instances of `MultishipPickupAdapterInterface` based on the carrier or module in use (e.g., for Mondial Relay, Colissimo).
- `multishipsplit/classes/MultishipRefundLog.php`
  - **Extends:** `ObjectModel`
  - **Database Table:** `mss_refund_log`
  - **`$definition` fields:** Logs refund actions related to split orders, especially important when partial refunds or refunds across multiple linked orders are involved.
- `multishipsplit/classes/MultishipRuleContext.php`
  - **Responsibility:** Encapsulates the context (e.g., current cart, customer, product being evaluated) for rule evaluation, making it easier to pass relevant data to condition evaluators.
- `multishipsplit/classes/MultishipShipmentGroup.php`
  - **Responsibility:** Represents a single logical shipment within a split cart. It holds a collection of `MultishipShipmentProduct`s, the selected carrier, and associated costs.
- `multishipsplit/classes/MultishipShipmentProduct.php`
  - **Responsibility:** Represents a product item within a `MultishipShipmentGroup`, including its quantity and specific attributes relevant to that shipment.
- `multishipsplit/classes/MultishipShippingCostAggregator.php`
  - **Responsibility:** Calculates the total shipping cost by summing the costs of all individual `MultishipShipmentGroup`s.
- `multishipsplit/classes/MultishipSplitGroup.php`
  - **Extends:** `ObjectModel`
  - **Database Table:** `mss_split_group`
  - **`$definition` fields:** Stores details about a specific shipment group that was created as part of a split order. This is used for tracking and reporting in the Back Office.
- `multishipsplit/classes/MultishipSplitOrchestrator.php`
  - **Responsibility:** The high-level orchestrator for the entire splitting process, from initial cart slicing to order creation and payment handling.
- `multishipsplit/classes/Pickup/MultishipColissimoPickupAdapter.php`
  - **Implements:** `MultishipPickupAdapterInterface`
  - **Responsibility:** Provides specific logic for integrating with Colissimo pickup points.
- `multishipsplit/classes/Pickup/MultishipMondialRelayPickupAdapter.php`
  - **Implements:** `MultishipPickupAdapterInterface`
  - **Responsibility:** Provides specific logic for integrating with Mondial Relay pickup points.
- `multishipsplit/classes/Pickup/MultishipPickupAdapterInterface.php`
  - **Responsibility:** Defines the contract for all pickup point integration adapters, ensuring a consistent interface for different carriers.
- `multishipsplit/override/classes/Cart.php`
  - **Responsibility:** Overrides core `Cart` methods to intercept and modify how products are added, removed, and how shipping costs are calculated, enabling the module’s splitting logic to take effect. This is a critical override.
- `multishipsplit/override/classes/PaymentModule.php`
  - **Responsibility:** Overrides core `PaymentModule` methods to handle the payment process for multiple orders generated from a single split cart. It ensures that a single payment covers all sub-orders and that their statuses are correctly updated.

### 3.4 JavaScript Assets (`views/js/`)

- `multishipsplit/lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Back-office.
  - **Details:** Provides autocomplete functionality for search inputs, likely used in the rule builder for selecting products, categories, or other entities.
- `multishipsplit/lib/searchTool/views/views/js/autocomplete.js`
  - **Scope:** Back-office.
  - **Details:** Likely a duplicate or alternative path for the autocomplete script, possibly for compatibility or specific view contexts.
- `multishipsplit/views/js/adminActionBuilder.js`
  - **Scope:** Back-office (AdminMultishipRulesController).
  - **Details:** Manages the dynamic interface for building rule actions (e.g., “Force Separate Shipment”). It handles adding/removing action types and their associated parameters.
- `multishipsplit/views/js/adminConditionBuilder.js`
  - **Scope:** Back-office (AdminMultishipRulesController).
  - **Details:** Manages the dynamic interface for building rule conditions. It allows administrators to add multiple conditions, group them with AND/OR logic, and select various criteria (product, category, etc.).
- `multishipsplit/views/js/adminMultishipSearchTool.js`
  - **Scope:** Back-office.
  - **Details:** Integrates the autocomplete search tool into the module’s admin forms, particularly for selecting specific products, categories, or other entities when defining rules.
- `multishipsplit/views/js/admin_dashboard.js`
  - **Scope:** Back-office (AdminMultishipIndexController).
  - **Details:** Handles dynamic elements and data loading for the dashboard, potentially including chart rendering (e.g., using Chart.js) and KPI updates.
- `multishipsplit/views/js/admin_rules.js`
  - **Scope:** Back-office (AdminMultishipRulesController).
  - **Details:** General JavaScript for the rules management page, including drag-and-drop reordering of rules, enable/disable toggles, and form submission handling.
- `multishipsplit/views/js/checkout.js`
  - **Scope:** Front-office (Checkout page).
  - **Details:** This is a critical script for the front-office experience. It binds event listeners to carrier selection changes for each shipment group, sends AJAX requests to `groups.php` or `pickup.php` to update shipping costs or fetch pickup points, and dynamically updates the total order summary on the checkout page. It likely uses `prestashop.on` for custom events.

### 3.5 CSS Stylesheets (`views/css/`)

- `multishipsplit/lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Back-office.
  - **Details:** Styles for the autocomplete dropdowns and search input fields used in the admin forms.
- `multishipsplit/lib/searchTool/views/views/css/autocomplete.css`
  - **Scope:** Back-office.
  - **Details:** Likely a duplicate or alternative path for the autocomplete styles.
- `multishipsplit/views/css/admin_condition_builder.css`
  - **Scope:** Back-office (AdminMultishipRulesController).
  - **Details:** Styles the dynamic interface for building conditions within the rule creation/editing form, ensuring a clear and organized layout.
- `multishipsplit/views/css/admin_dashboard.css`
  - **Scope:** Back-office (AdminMultishipIndexController).
  - **Details:** Styles for the dashboard layout, KPIs, charts, and recent splits table.
- `multishipsplit/views/css/admin_order.css`
  - **Scope:** Back-office (Order view page).
  - **Details:** Styles for the custom widget or information displayed within the standard PrestaShop order view, showing how the order was split.
- `multishipsplit/views/css/admin_rules.css`
  - **Scope:** Back-office (AdminMultishipRulesController).
  - **Details:** General styles for the rule listing table, rule actions (enable/disable), and overall layout of the rules management page.
- `multishipsplit/views/css/checkout.css`
  - **Scope:** Front-office (Checkout page).
  - **Details:** Styles the presentation of the split shipment groups on the checkout page, including how carriers are displayed for each group, the summary of costs, and potentially pickup point selection interfaces. Developers can override these classes in their theme’s `custom.css` or by modifying the module’s templates.

### 3.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `multishipsplit/views/templates/hook/checkout_groups.tpl`
  - **Hook:** Likely `displayCarrierList` or a custom hook injected into the checkout shipping step.
  - **Outputs:** The main visual block on the checkout page that displays the grouped products and allows customers to select a carrier for each individual shipment group. This is where the core front-office interaction happens.
- `multishipsplit/views/templates/hook/order_confirmation_split.tpl`
  - **Hook:** `displayOrderConfirmation` or a similar hook on the order confirmation page.
  - **Outputs:** The summary of how the order was split, showing which items were in each shipment and the chosen carrier, as configured by the “Display Split Summary on Order Confirmation Page” setting.
- `multishipsplit/views/templates/hook/payment_top.tpl`
  - **Hook:** `displayPaymentTop`
  - **Outputs:** Potentially displays a warning or informational message to the customer regarding the split order before they proceed to payment, ensuring they understand the total cost includes multiple shipping fees.

#### Admin templates (`views/templates/admin/`)

- `multishipsplit/lib/searchTool/views/scripts.tpl`
  - **Outputs:** Smarty script block for the search tool, likely including JavaScript and CSS includes.
- `multishipsplit/lib/searchTool/views/views/scripts.tpl`
  - **Outputs:** Duplicate or alternative path for search tool scripts.
- `multishipsplit/views/templates/admin/actionBuilder.tpl`
  - **Outputs:** The HTML structure for the dynamic action builder interface within the rule creation/editing form.
- `multishipsplit/views/templates/admin/dashboard_chart.tpl`
  - **Outputs:** Template for rendering a specific chart on the dashboard, likely using a JavaScript charting library.
- `multishipsplit/views/templates/admin/dashboard_kpi_strip.tpl`
  - **Outputs:** Template for the Key Performance Indicator (KPI) strip at the top of the dashboard.
- `multishipsplit/views/templates/admin/dashboard_recent_splits.tpl`
  - **Outputs:** Template for displaying a list of recently split orders on the dashboard.
- `multishipsplit/views/templates/admin/dashboard_stats.tpl`
  - **Outputs:** General statistics block on the dashboard.
- `multishipsplit/views/templates/admin/menu.tpl`
  - **Outputs:** Defines the module’s custom menu items in the PrestaShop Back Office navigation (e.g., under “Shipping”).
- `multishipsplit/views/templates/admin/order_split_widget.tpl`
  - **Outputs:** A custom widget or block displayed within the standard PrestaShop order detail page in the Back Office, providing a summary of how that specific order was split.
- `multishipsplit/views/templates/admin/policyConditionBuilder.tpl`
  - **Outputs:** The HTML structure for the dynamic condition builder interface within the rule creation/editing form.
- `multishipsplit/views/templates/admin/split_view.tpl`
  - **Outputs:** A detailed view for a specific split order, potentially accessed from the “Shipment Splits” list.

### 3.7 Database Schema & Hooks Map

#### Database Tables

- `ps_mss_grouping_rule`: Stores the definitions of all the shipment grouping rules created by the administrator.
  - `id_mss_grouping_rule` (PK)
  - `name` (VARCHAR)
  - `priority` (INT)
  - `active` (TINYINT)
  - `conditions` (TEXT - serialized array/JSON of conditions)
  - `actions` (TEXT - serialized array/JSON of actions)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_mss_split_group`: Stores details of each individual shipment group created for a split order.
  - `id_mss_split_group` (PK)
  - `id_order` (FK to `ps_orders`)
  - `id_cart` (FK to `ps_cart`)
  - `id_carrier` (FK to `ps_carrier`)
  - `shipping_cost_tax_excl` (DECIMAL)
  - `shipping_cost_tax_incl` (DECIMAL)
  - `products` (TEXT - serialized array of products in this group)
  - `pickup_point_data` (TEXT - serialized data for pickup point, if selected)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_mss_order_link`: Links a single PrestaShop `id_order` (the “parent” order) to multiple `id_order`s (the “child” orders created for each split shipment).
  - `id_mss_order_link` (PK)
  - `id_parent_order` (FK to `ps_orders`)
  - `id_child_order` (FK to `ps_orders`)
  - `id_mss_split_group` (FK to `ps_mss_split_group`)
  - `date_add` (DATETIME)
- `ps_mss_refund_log`: Logs refund events related to split orders.
  - `id_mss_refund_log` (PK)
  - `id_order` (FK to `ps_orders`)
  - `id_order_slip` (FK to `ps_order_slip`)
  - `amount` (DECIMAL)
  - `reason` (TEXT)
  - `date_add` (DATETIME)
- `ps_configuration`: Module settings are stored here with keys like `MULTISHIPSPLIT_ENABLED`, `MULTISHIPSPLIT_DEBUG_MODE`, etc.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of all front-office pages. | Injecting CSS and JS assets for front-office functionality (e.g., `checkout.js`, `checkout.css`). |
| `displayBackOfficeHeader` | In the `<head>` section of all back-office pages. | Injecting CSS and JS assets for admin controllers (e.g., `admin_rules.js`, `admin_condition_builder.css`). |
| `displayAdminProductsExtra` | On the product editing page in the Back Office. | Potentially adds a tab or section to configure product-specific splitting rules or overrides. |
| `actionCartSave` | After a cart is saved or updated. | Intercepts cart modifications to trigger the splitting logic and recalculate shipping groups. |
| `actionValidateOrder` | After an order has been successfully validated. | Processes the split cart into multiple PrestaShop orders, links them, and stores split group data. |
| `actionOrderSlipAdd` | When an order slip (refund) is added. | Handles refund logic for split orders, potentially logging partial refunds across linked orders. |
| `displayCarrierList` | On the checkout shipping step, where carrier options are displayed. | Replaces or augments the standard carrier list with the grouped shipment selection interface (`checkout_groups.tpl`). |
| `displayOrderConfirmation` | On the final order confirmation page. | Displays the split order summary to the customer (`order_confirmation_split.tpl`). |
| `displayPaymentTop` | Before the payment method selection on the checkout page. | Can display important messages or summaries related to split shipping costs (`payment_top.tpl`). |
| `displayAdminOrder` | On the order detail page in the Back Office. | Injects the `order_split_widget.tpl` to show how the specific order was split. |
| `actionObjectCartUpdateAfter` | After a Cart object has been updated. | Similar to `actionCartSave`, ensures splitting logic is re-evaluated. |
| `actionObjectOrderAddAfter` | After a new Order object has been added. | Used to finalize the linking of parent/child orders and split group data. |
| `actionObjectOrderUpdateAfter` | After an Order object has been updated. | Potentially updates split group statuses or related data if an order is modified. |
| `actionFrontControllerSetMedia` | Before a front controller renders its content. | Ensures necessary JS/CSS are loaded for front-office pages. |
| `actionAdminControllerSetMedia` | Before an admin controller renders its content. | Ensures necessary JS/CSS are loaded for back-office pages. |
| `displayAdminStatsModules` | On the Modules > Stats page. | Potentially adds module-specific statistics to the PrestaShop dashboard. |
| `displayDashboardTop` | At the top of the PrestaShop dashboard. | Can display a quick summary or alert from the module. |
| `displayDashboardZoneOne` | In the first zone of the PrestaShop dashboard. | Can display a module-specific widget on the dashboard. |
| `displayDashboardZoneTwo` | In the second zone of the PrestaShop dashboard. | Can display a module-specific widget on the dashboard. |

## 4. Official Support & Updates

For the latest module updates, bug fixes, and official support, please refer to your customer account at MyPresta.eu.

- **Module Updates:** Log in to [MyPresta.eu Order History & Downloads](https://mypresta.eu/my-account/orders/) to download the most recent version of the “Split cart into separate shipments” module.
- **Technical Support:** If you encounter any issues or have questions that are not covered in this guide, please open a support ticket through your MyPresta.eu customer account. Our team is ready to assist you.

## 5. ## Gallery

![Dashboard on module configuration page that shows module statistics](https://mypresta.eu/docs/images/docs/02-shipping-multi-carrier-order-split_1791740311.webp)
