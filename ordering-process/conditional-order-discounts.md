---
title: "Conditional Order Discounts - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Conditional Order Discounts PrestaShop module by MyPresta.eu."
sidebar:
  label: "Conditional Order Discounts - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Conditional Order Discounts Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/conditional-order-discounts.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/conditional-order-discounts/)
>
> ---


# Conditional Order Discounts

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” will take you to the main settings page for the module.

- **Enable Conditional Order Discounts:**
  - **What this setting does:** This is the master switch for the entire module. When enabled, the module’s logic for applying conditional discounts will be active on your store. When disabled, no conditional discounts will be applied, regardless of any policies you’ve created.
  - **Effect of changing this setting:**
    - *When enabled:* The module will start evaluating your defined discount policies and applying discounts or free gifts to customer carts as they qualify.
    - *When disabled:* All conditional discount policies created with this module will be ignored, and no discounts will be applied.
  - **Recommended value:** YES
  - **Merchant scenario / example:** You’ve just finished setting up your first “Buy 2 Get 1 Free” policy and want it to go live. You would enable this setting. If you need to temporarily pause all conditional discounts for a store-wide sale managed by other means, you would disable it.

### 2.2 Dedicated Admin Screens & Controller Views

The Conditional Order Discounts module adds a new main menu item to your PrestaShop Back Office, usually under **Catalog** or **Marketing**, named **“Conditional Discounts”**. This menu contains several sub-items for managing your policies and reviewing logs.

#### 2.2.1 Conditional Discounts > Policies (AdminConorderdisPoliciesController)

This is where you define and manage all your conditional discount policies.

- **Screen Name & Menu Location:** Back Office > Conditional Discounts > Policies
- **Available Actions & Settings:**

  - **Policy List:** You’ll see a table listing all your existing discount policies. Each policy will show its name, status (active/inactive), and other key details.
  - **Add New Policy:** Click the “Add new policy” button to create a brand new conditional discount rule.
  - **Edit Policy:** Click the “Edit” icon next to an existing policy to modify its conditions, promotions, or settings.
  - **Duplicate Policy:** This is a very useful feature! Click the “Duplicate” icon to create an exact copy of an existing policy. This saves a lot of time if you need to create similar promotions.
  - **Enable/Disable Policy:** You can quickly activate or deactivate individual policies directly from the list.
  - **Delete Policy:** Remove a policy from your store.
  - **Policy Configuration Form (when adding/editing):**
    - **Policy Name:** A descriptive name for your internal reference (e.g., “BOGO T-Shirts,” “Spend $100 Get 10% Off”).
    - **Status (Active/Inactive):** Controls whether this specific policy is currently live on your store.
    - **Conditions Builder:** This is the core of the module. You’ll use a visual interface to define *when* the discount applies. Examples:
      - “Cart total is greater than $100”
      - “Customer is in group ‘Wholesalers’”
      - “Product ‘X’ is in cart with quantity >= 2”
      - “Any product from category ‘Summer Sale’ is in cart”
      - You can combine multiple conditions with “AND” or “OR” logic.
    - **Promotions Builder:** This defines *what* discount or gift the customer receives if the conditions are met. Examples:
      - “Apply 10% discount to the entire order”
      - “Give cheapest item from category ‘Accessories’ for free”
      - “Add product ‘Gift Box’ to cart for free”
      - “Apply 50% discount to the second unit of product ‘Y’”
    - **Scope Selector:** Define which stores (for multistore setups), customer groups, or currencies this policy applies to.
    - **Priority:** If multiple policies could apply to a single cart, this determines which one takes precedence. Lower numbers mean higher priority.
    - **Validity Dates:** Set a start and end date for the promotion.
    - **Cart Simulator:** A powerful tool within the policy editor that allows you to add products to a simulated cart and instantly see if your policy applies and what discount is given. This is crucial for testing!
- **Effect of changes:**

  - Adding a new policy makes a new promotion available (if active) on your store.
  - Editing a policy changes the conditions or promotions of an existing offer.
  - Enabling/disabling policies directly controls their visibility and application on the front office.
  - Duplicating policies allows for rapid creation of similar promotions without starting from scratch.
- **Recommended workflow for daily store management:**

  1. **Plan your promotion:** Decide on the offer (e.g., “Buy 3, get 1 free on all socks”).
  2. **Create a new policy:** Go to “Policies” and click “Add new policy.”
  3. **Define conditions:** Use the visual builder to specify which products, categories, quantities, or cart values trigger the discount.
  4. **Define promotions:** Specify the discount type (percentage, fixed amount, free gift) and what it applies to.
  5. **Test thoroughly with the Cart Simulator:** Before saving, use the simulator to add various products and quantities to ensure the discount applies exactly as intended.
  6. **Set validity dates and priority:** Ensure the promotion runs only when you want it to and interacts correctly with other promotions.
  7. **Activate the policy:** Once tested and ready, set its status to “Active.”
  8. **Monitor with Audit Log:** Check the Audit Log (see next section) to confirm policies are being applied correctly in live carts.

#### 2.2.2 Conditional Discounts > Audit Log (AdminConorderdisAuditLogController)

This screen provides a detailed history of how your conditional discount policies have been applied (or attempted to be applied) to customer carts.

- **Screen Name & Menu Location:** Back Office > Conditional Discounts > Audit Log
- **Available Actions & Settings:**
  - **Log List:** A table displaying entries for each time a policy was evaluated. Each entry typically includes:
    - **Date/Time:** When the event occurred.
    - **Customer:** Which customer (if logged in) was involved.
    - **Cart ID:** The ID of the shopping cart.
    - **Policy Name:** Which policy was evaluated.
    - **Result:** Whether the policy conditions were met, and if a discount was applied.
    - **Details:** More specific information about the conditions met, the discount applied, or why it wasn’t applied.
  - **Filtering and Searching:** You can filter the log by date, customer, policy, or result to quickly find specific events.
- **Effect of changes:** This is a read-only screen. You don’t make changes here, but rather observe the module’s behavior.
- **Recommended workflow for daily store management:**
  - **Troubleshooting:** If a customer reports an issue with a discount not applying, or if you suspect a policy isn’t working as expected, check the audit log. You can see exactly what happened when their cart was evaluated.
  - **Monitoring:** Regularly review the log to ensure your promotions are being triggered correctly and to identify any unexpected behavior.
  - **Understanding Policy Interactions:** If you have multiple policies, the log can help you understand which policies are being considered and which one ultimately applies based on priorities.

#### 2.2.3 Conditional Discounts > Dashboard (AdminConorderdisDashboardController)

This screen provides an overview and potentially quick access to key module functionalities.

- **Screen Name & Menu Location:** Back Office > Conditional Discounts > Dashboard
- **Available Actions & Settings:** This dashboard typically provides:
  - **Summary Statistics:** Quick counts of active policies, total policies, or recent audit log entries.
  - **Quick Links:** Shortcuts to “Add New Policy,” “View Policies,” or “View Audit Log.”
  - **Simulator Access:** A prominent link or embedded tool for the Cart Simulator to quickly test policies.
  - **Module Status:** Indication if the module is enabled or disabled.
- **Effect of changes:** This is primarily an informational and navigation screen. Changes are made through the linked “Policies” or “Audit Log” sections.
- **Recommended workflow for daily store management:** Use this as a starting point for managing your promotions, getting a quick overview of your active campaigns, and accessing the simulator for testing.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable Conditional Order Discounts | YES | Master switch for activating/deactivating all module functionalities. |
| Policies (Add/Edit) | Policy Name | Descriptive Name | Internal label for your promotion. |
| Policies (Add/Edit) | Status | Active | Controls if a specific policy is live on the store. |
| Policies (Add/Edit) | Conditions Builder | Varies | Defines criteria for discount eligibility (e.g., cart total, products in cart). |
| Policies (Add/Edit) | Promotions Builder | Varies | Defines the discount or free gift applied (e.g., % off, free product). |
| Policies (Add/Edit) | Scope Selector | All Stores/Groups/Currencies | Limits policy application to specific contexts. |
| Policies (Add/Edit) | Priority | Lower number = higher priority | Determines which policy applies if multiple are eligible. |
| Policies (Add/Edit) | Validity Dates | No end date | Sets the active period for the promotion. |
| Policies (Add/Edit) | Cart Simulator | N/A | Tool to test policy application before saving. |
| Policies (List) | Duplicate Policy Action | N/A | Creates a copy of an existing policy, saving setup time. |
| Audit Log | Log Entries | N/A | Records every policy evaluation, showing success/failure and details. |
| Dashboard | Quick Links / Summary | N/A | Provides an overview and shortcuts to key module features. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My discount isn’t applying, even though I’ve set up a policy.**
A1:

- **Is the module enabled?** Check **Modules > Module Manager > Conditional Order Discounts** and ensure the main switch is ON.
- **Is the specific policy active?** Go to **Conditional Discounts > Policies** and check the “Status” column for your policy.
- **Are the conditions met?** Use the **Cart Simulator** within the policy editor. Add products to the simulated cart exactly as a customer would. Does the simulator show the discount applying? If not, review your conditions carefully.
- **Check validity dates:** Is the policy within its active date range?
- **Check priority:** If multiple policies could apply, ensure the one you expect to apply has the correct priority (lower number = higher priority).
- **Clear PrestaShop Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache.” Sometimes, cached data can prevent new rules from taking effect immediately.

**Q2: The discount is applying, but it’s not the correct amount or product.**
A2:

- **Review your Promotions Builder:** Double-check the discount type (percentage, fixed amount), the value, and what it applies to (entire order, specific products, cheapest item, etc.).
- **Check conditions again:** Sometimes, a subtle condition might lead to an unexpected outcome. For example, if you have “any product from category X” but the customer has products from other categories that also meet a “cheapest item” rule.
- **Use the Cart Simulator extensively:** This is your best friend for verifying complex rules. Test edge cases.
- **Audit Log:** Check **Conditional Discounts > Audit Log** to see the exact details of how the module evaluated the cart and what discount it attempted to apply. This can reveal discrepancies.

**Q3: My custom theme doesn’t display the discount messages or free gifts clearly.**
A3:

- The module integrates with PrestaShop’s native cart rules, so the discount itself should appear in the cart summary. However, if you want custom messages like “You qualified for a free gift!” or “Buy 2, Get 1 Free!” to appear dynamically on product pages or in the cart, this usually requires custom theme modifications.
- **Consult a developer:** Your webmaster or a PrestaShop developer can help you integrate dynamic messages into your theme’s `product.tpl`, `cart.tpl`, or `checkout.tpl` files, potentially using the module’s hooks (see Developer Guide).

**Q4: Can I use this module with other discount modules or native cart rules?**
A4:

- Yes, this module works by creating and managing native PrestaShop cart rules in the background. This means it’s generally compatible with other modules that also rely on PrestaShop’s core discount system.
- **Priority is key:** Be mindful of the priority settings for your Conditional Order Discounts policies and any other native cart rules you’ve created manually. PrestaShop applies discounts based on their priority. Test thoroughly with the Cart Simulator and review the Audit Log if you have many overlapping promotions.

**Q5: How do I manage multi-language translations for policy names or descriptions?**
A5:

- Policy names and any custom text you enter for conditions or promotions are typically managed directly within the policy editing screen. PrestaShop’s standard translation interface (under **International > Translations**) may not directly apply to dynamic content generated by the module’s policy builder.
- If the module provides specific fields for different languages within the policy editor, use those. Otherwise, ensure your policy names are clear and concise, or consider adding static informational blocks in your theme for different languages to explain promotions.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical architecture of the Conditional Order Discounts module, detailing its file structure, classes, controllers, and integration points for developers and webmasters.

### 4.1 Architecture Overview

The Conditional Order Discounts module is built following PrestaShop’s MVC (Model-View-Controller) pattern. It heavily leverages PrestaShop’s native `CartRule` system, effectively acting as an advanced rule builder and manager for these core objects. It introduces several custom `ObjectModel` classes for managing policies, conditions, promotions, and an audit log. The module uses a robust engine to evaluate complex conditions against a customer’s cart state and then materializes the appropriate `CartRule` objects. It also includes a sophisticated condition builder and simulator in the Back Office for ease of use.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `conorderdis/controllers/front/index.php`
  - **Class Name:** `ConorderdisIndexModuleFrontController` (or similar, depending on PrestaShop version and module structure, often `ModuleFrontController`).
  - **Responsibility:** This file typically serves as a placeholder or a default entry point for front-office module interactions. In this module’s context, direct front-office controllers are less critical as most logic is handled via hooks that interact with the cart and order process. It might handle AJAX requests related to cart updates or specific front-end interactions if implemented, but the core discount logic runs via hooks.

#### Back-Office Admin Controllers

- `conorderdis/controllers/admin/AdminconorderdisAuditLog.php`
  - **Tab Name:** Conditional Discounts > Audit Log
  - **Managed Entity:** `ConorderdisAuditLog` (maps to `ps_conorderdis_log` table).
  - **Responsibility:** Manages the display and filtering of the audit log entries. Extends `AdminController` and uses `HelperList` to render the log table, allowing administrators to review how policies were applied or evaluated against customer carts.
- `conorderdis/controllers/admin/AdminconorderdisPolicies.php`
  - **Tab Name:** Conditional Discounts > Policies
  - **Managed Entity:** `ConorderdisPolicy` (maps to `ps_conorderdis_policy` table).
  - **Responsibility:** This is the primary controller for managing discount policies. It extends `AdminController` and provides CRUD (Create, Read, Update, Delete) functionality for policies. It integrates the visual condition and promotion builders, the product picker, and the cart simulator. It uses `HelperList` for the policy overview and `HelperForm` for the add/edit policy forms.
- `conorderdis/controllers/admin/index.php`
  - **Responsibility:** This is a standard PrestaShop practice to prevent directory listing. It typically contains a simple `die('No direct script access allowed');` statement. It does not manage any specific entity or provide functionality beyond security.

### 4.3 Core Classes & Models (`classes/`)

- `conorderdis/classes/ConorderdisAdmin.php`
  - **Responsibility:** Likely contains helper methods or utilities specifically for the Back Office administration, such as rendering specific form elements, handling AJAX requests from admin forms, or managing module-specific configurations.
- `conorderdis/classes/ConorderdisAuditLog.php`
  - **Extends:** `ObjectModel`
  - **Database Table:** `ps_conorderdis_log`
  - **`$definition` fields:** Stores details about policy evaluations, including `id_cart`, `id_customer`, `id_policy`, `result`, `details`, `date_add`.
  - **Responsibility:** Represents an entry in the audit log. Provides methods for logging policy application events, successes, and failures.
- `conorderdis/classes/ConorderdisCartRuleManager.php`
  - **Responsibility:** Manages the creation, update, and deletion of native PrestaShop `CartRule` objects based on the module’s `ConorderdisPolicy` definitions. This class is crucial for translating the module’s complex rules into standard PrestaShop discounts.
- `conorderdis/classes/ConorderdisCartState.php`
  - **Responsibility:** Encapsulates the current state of a customer’s cart, providing an abstraction layer for the discount engine to evaluate conditions. It might include methods to retrieve cart total, product quantities, customer group, etc.
- `conorderdis/classes/ConorderdisCompatibility.php`
  - **Responsibility:** Handles compatibility layers for different PrestaShop versions (e.g., 1.7.x, 8.x, 9.x) or specific PHP versions. It ensures the module functions correctly across the supported environment range by providing polyfills or alternative implementations for deprecated functions/methods.
- `conorderdis/classes/ConorderdisConditionTree.php`
  - **Responsibility:** Manages the complex logical structure of conditions (e.g., “AND,” “OR” groups, nested conditions). It likely parses the condition data from the database and provides methods to evaluate whether a given `ConorderdisCartState` meets the defined conditions.
- `conorderdis/classes/ConorderdisContext.php`
  - **Responsibility:** A wrapper around PrestaShop’s global `Context` object, potentially adding module-specific context data or simplifying access to common context properties.
- `conorderdis/classes/ConorderdisDashboard.php`
  - **Responsibility:** Provides data and logic for the Back Office dashboard view, summarizing key statistics and providing quick links.
- `conorderdis/classes/ConorderdisEngine.php`
  - **Responsibility:** The core logic engine of the module. This class orchestrates the evaluation of policies. It takes a `ConorderdisCartState`, iterates through active `ConorderdisPolicy` objects, evaluates their `ConorderdisConditionTree`, and if conditions are met, instructs `ConorderdisPromoMaterializer` to apply the discount.
- `conorderdis/classes/ConorderdisFreeGift.php`
  - **Responsibility:** Specifically handles the logic for adding free gift products to the cart when a promotion dictates it. It interacts with the `Cart` object to ensure the product is added correctly and marked as free.
- `conorderdis/classes/ConorderdisListRenderer.php`
  - **Responsibility:** A helper class for rendering lists in the Back Office, potentially extending `HelperList` or providing custom rendering logic for specific columns or actions (e.g., the duplicate action).
- `conorderdis/classes/ConorderdisLog.php`
  - **Extends:** `ObjectModel` (likely an alias or an older version of `ConorderdisAuditLog`).
  - **Database Table:** `ps_conorderdis_log`
  - **Responsibility:** Similar to `ConorderdisAuditLog`, handles logging of module events.
- `conorderdis/classes/ConorderdisPolicy.php`
  - **Extends:** `ObjectModel`
  - **Database Table:** `ps_conorderdis_policy`
  - **`$definition` fields:** Stores all policy-related data, including `name`, `active`, `conditions_data` (serialized JSON/array), `promotions_data` (serialized JSON/array), `priority`, `date_from`, `date_to`, `id_shop`, `id_customer_group`, `id_currency`.
  - **Responsibility:** Represents a single conditional discount policy. Provides methods for saving, loading, and managing policy data, including its conditions and promotions.
- `conorderdis/classes/ConorderdisPolicyDuplicator.php`
  - **Responsibility:** Handles the logic for duplicating `ConorderdisPolicy` objects, ensuring all associated data (conditions, promotions) are correctly copied.
- `conorderdis/classes/ConorderdisProductPicker.php`
  - **Responsibility:** Provides functionality for selecting products, categories, or manufacturers within the Back Office policy builder, likely via an AJAX-driven search tool.
- `conorderdis/classes/ConorderdisPromoMaterializer.php`
  - **Responsibility:** Takes the output of the `ConorderdisEngine` (i.e., “this promotion should apply”) and translates it into actual changes in the PrestaShop cart, primarily by creating or modifying `CartRule` objects via `ConorderdisCartRuleManager`.
- `conorderdis/classes/ConorderdisPromotionCalculator.php`
  - **Responsibility:** Calculates the exact discount amount or identifies the free product based on the defined promotion rules and the current cart state.
- `conorderdis/classes/ConorderdisPromotionType.php`
  - **Responsibility:** Defines and manages different types of promotions (e.g., percentage discount, fixed amount, free gift, cheapest item free). It likely contains logic specific to each promotion type.
- `conorderdis/classes/ConorderdisRule.php`
  - **Responsibility:** A generic class representing a single rule or condition within the `ConorderdisConditionTree`.
- `conorderdis/classes/ConorderdisSchema.php`
  - **Responsibility:** Manages the module’s database schema, including installation and uninstallation of custom tables (`ps_conorderdis_policy`, `ps_conorderdis_log`).
- `conorderdis/classes/ConorderdisUnitPool.php`
  - **Responsibility:** Likely used in complex “Buy N Get M” or “cheapest item free” scenarios to manage and track individual product units within the cart for discount calculation.
- `conorderdis/classes/index.php`
  - **Responsibility:** Standard PrestaShop practice to prevent directory listing.

### 4.4 JavaScript Assets (`views/js/`)

- `conorderdis/lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Back-office (used in admin forms).
  - **Details:** Provides autocomplete functionality for input fields, likely used in the policy builder for selecting products, categories, or manufacturers. Binds to input fields, makes AJAX calls to a search controller, and displays suggestions.
- `conorderdis/views/js/adminConditionBuilder.js`
  - **Scope:** Back-office (AdminConorderdisPolicies controller).
  - **Details:** Powers the visual condition builder interface. Handles adding/removing conditions, grouping conditions (AND/OR), selecting condition types, and updating the UI dynamically based on user input. Manages the data structure representing the condition tree.
- `conorderdis/views/js/adminConorderdisDashboard.js`
  - **Scope:** Back-office (AdminConorderdisDashboard controller).
  - **Details:** Provides interactive elements or dynamic content for the module’s dashboard, such as fetching summary statistics via AJAX or handling quick link clicks.
- `conorderdis/views/js/adminConorderdisSearchTool.js`
  - **Scope:** Back-office (AdminConorderdisPolicies controller).
  - **Details:** A more general search tool, potentially used for product/category selection within the policy builder, similar to `autocomplete.js` but possibly with more advanced filtering or display options.
- `conorderdis/views/js/adminConorderdisSimulator.js`
  - **Scope:** Back-office (AdminConorderdisPolicies controller).
  - **Details:** Implements the interactive cart simulator. Binds to input fields for adding simulated products, makes AJAX calls to a simulation endpoint (likely in `AdminConorderdisPolicies`), and updates the UI with the simulated cart state and applied discounts.
- `conorderdis/views/js/adminPolicyRules.js`
  - **Scope:** Back-office (AdminConorderdisPolicies controller).
  - **Details:** Manages the overall interaction and logic for the policy creation/editing form, coordinating between the condition builder, promotion builder, and simulator.
- `conorderdis/views/js/adminPromotionBuilder.js`
  - **Scope:** Back-office (AdminConorderdisPolicies controller).
  - **Details:** Powers the visual promotion builder interface. Handles adding/removing promotions, selecting promotion types (e.g., percentage, free gift), and updating the UI dynamically based on the chosen promotion type.

### 4.5 CSS Stylesheets (`views/css/`)

- `conorderdis/lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Back-office (admin forms).
  - **Details:** Styles the autocomplete dropdowns and search results provided by the `autocomplete.js` script.
- `conorderdis/views/css/admin_conorderdis.css`
  - **Scope:** Back-office (admin forms and pages).
  - **Details:** Contains general styling for the module’s Back Office interfaces, including the policy list, policy editor (condition and promotion builders), dashboard, and audit log. Defines layouts, colors, and specific UI components for a consistent look and feel within the PrestaShop admin.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `conorderdis/views/templates/hook/admin_order.tpl`
  - **Hook:** `displayAdminOrder`
  - **Output:** This template is rendered in the Back Office when viewing an order. It likely displays information related to any conditional discounts applied to that specific order, potentially linking to the audit log or showing which policies were active.

#### Admin templates (`views/templates/admin/`)

- `conorderdis/lib/searchTool/views/scripts.tpl`
  - **Output:** Contains JavaScript initialization or configuration for the search tool, often included in admin forms where the search tool is used.
- `conorderdis/views/templates/admin/auditPreview.tpl`
  - **Output:** Renders a preview or detailed view of an audit log entry, possibly within a modal or a specific section of the `AdminconorderdisAuditLog` page.
- `conorderdis/views/templates/admin/dashboard.tpl`
  - **Output:** The main template for the `AdminConorderdisDashboard` controller, displaying summary statistics, quick links, and potentially the embedded simulator.
- `conorderdis/views/templates/admin/helpers/list/list_action_duplicate.tpl`
  - **Output:** A custom template for rendering the “Duplicate” action icon and link within a `HelperList` table, specifically for policies.
- `conorderdis/views/templates/admin/policiesPreview.tpl`
  - **Output:** Renders a preview or detailed view of a policy, possibly within a modal or a specific section of the `AdminconorderdisPolicies` page.
- `conorderdis/views/templates/admin/policyConditionBuilder.tpl`
  - **Output:** The Smarty template for the visual condition builder interface within the policy editor. It defines the structure for adding, grouping, and configuring conditions.
- `conorderdis/views/templates/admin/policyRuleCard.tpl`
  - **Output:** A reusable template for displaying a single rule or condition within the condition builder, often used for dynamic rendering via JavaScript.
- `conorderdis/views/templates/admin/policyRulesTable.tpl`
  - **Output:** Renders the table or list of rules/conditions within the policy editor.
- `conorderdis/views/templates/admin/scopeSelector.tpl`
  - **Output:** Renders the interface for selecting shops, customer groups, and currencies for a policy.

#### Front-office templates (`views/templates/front/`)

- `conorderdis/controllers/front/index.php` (No specific `.tpl` files listed for front-office, implying minimal direct front-end rendering, relying on hooks to inject content or modify existing elements.)

### 4.7 Database Schema & Hooks Map

#### Database Tables

- `ps_conorderdis_policy`: Stores the definition of each conditional discount policy.
  - `id_conorderdis_policy` (Primary Key)
  - `name` (Policy name)
  - `active` (Boolean, 1 for active, 0 for inactive)
  - `conditions_data` (TEXT, JSON-encoded array of conditions)
  - `promotions_data` (TEXT, JSON-encoded array of promotions)
  - `priority` (INT, lower number = higher priority)
  - `date_from` (DATETIME)
  - `date_to` (DATETIME)
  - `id_shop` (INT, for multistore scope)
  - `id_customer_group` (INT, for customer group scope)
  - `id_currency` (INT, for currency scope)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_conorderdis_log`: Stores audit log entries for policy evaluations.
  - `id_conorderdis_log` (Primary Key)
  - `id_cart` (INT)
  - `id_customer` (INT)
  - `id_policy` (INT, foreign key to `ps_conorderdis_policy`)
  - `result` (VARCHAR, e.g., ‘applied’, ‘not\_met’, ‘error’)
  - `details` (TEXT, JSON-encoded details of the evaluation)
  - `date_add` (DATETIME)
- `ps_configuration`: Module stores its main `CONORDERDIS_ENABLED` setting here.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Used to include module’s front-office CSS/JS, if any, or to inject meta tags. |
| `actionFrontControllerInitAfter` | After the front controller has been initialized. | Early point to modify context, register services, or prepare for cart rule evaluation. |
| `actionCartSave` | After a cart has been saved (e.g., product added/removed). | Primary hook for re-evaluating conditional discount policies based on the updated cart content. |
| `actionValidateCartRule` | Before a cart rule is validated/applied. | Allows the module to intervene or modify native cart rule behavior, though less likely for this module which creates its own. |
| `actionValidateOrderBefore` | Before an order is validated. | Final check for conditional discounts before order creation, ensuring all rules are correctly applied. |
| `actionValidateOrder` | After an order has been successfully validated. | Used to finalize any module-specific actions post-order, such as logging the final discount application or clearing temporary data. |
| `actionObjectProductInCartDeleteBefore` | Before a product is deleted from the cart. | Allows the module to react to product removal, potentially adjusting discounts or free gifts. |
| `actionObjectProductInCartDeleteAfter` | After a product has been deleted from the cart. | Similar to `DeleteBefore`, but for post-deletion logic, potentially triggering a re-evaluation of cart rules. |
| `actionAdminControllerSetMedia` | When an admin controller is setting its media (CSS/JS). | Used to include the module’s Back Office CSS and JavaScript files for its configuration pages and custom controllers. |
| `displayAdminOrder` | On the Back Office order detail page. | Used to display module-specific information related to conditional discounts applied to the viewed order (e.g., via `admin_order.tpl`). |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please log in to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). You will find your purchased modules and access to our support channels there.
