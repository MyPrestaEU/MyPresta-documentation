---
title: "Assign customers to group by purchased products - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Assign customers to group by purchased products PrestaShop module by MyPresta.eu."
sidebar:
  label: "Assign customers to group by purchased products - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Assign customers to group by purchased products Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/assign-customers-to-group-by-purchased-products.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/assign-customers-to-group-by-purchased-products/)
>
> ---


# Assign customers to group by purchased products

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen where you manage the core settings of the module.

- **What this setting does:** This section typically contains general settings for the module, such as enabling/disabling its core functionality.
- **Effect of changing this setting:**
  - *When enabled:* The module will actively monitor customer purchases and apply your defined group assignment rules.
  - *When disabled:* The module will stop processing new orders for group assignments. Existing assignments will remain, but no new ones will be made automatically.
- **Recommended value:** **YES** (Enabled) to allow the module to function.
- **Merchant scenario / example:** If you’re setting up the module for the first time, you’ll want to enable it immediately after configuration. If you need to temporarily stop automatic assignments (e.g., during a major store migration), you can disable it here.

### 2.2 Dedicated Admin Screen: Product Group Associations

This is the core management area where you define the rules for assigning customers to groups based on their purchases.

**Screen Name & Menu Location:**
You can access this screen by navigating to **Modules > Module Manager**, finding “Assign customers to group by purchased products”, and clicking “Configure”. Within the module’s configuration, you will find a section or tab dedicated to “Product Group Associations” or similar.

**Available Actions & Settings:**
On this screen, you will typically find a list of existing assignment rules. You’ll have options to:

- **Add New Rule:** Create a new condition for group assignment.
- **Edit Rule:** Modify an existing rule.
- **Delete Rule:** Remove a rule.

When adding or editing a rule, you will configure the following:

1. **Select Customer Group:**

   - **What this setting does:** This is the target group to which customers will be assigned if they meet the rule’s conditions.
   - **Effect of changing this setting:** When a customer’s purchase triggers this rule, they will be moved into (or added to) the selected customer group.
   - **Recommended value:** Choose the specific customer group you want to segment (e.g., “Wholesale Customers”, “VIP Buyers”, “Electronics Enthusiasts”).
   - **Merchant scenario / example:** You want to create a rule to assign customers to your “VIP Buyers” group.
2. **Select Products / Categories:**

   - **What this setting does:** Here you define *which* products or product categories, when purchased, will trigger the group assignment. You can usually select multiple products or categories. The module likely includes a search tool to easily find products.
   - **Effect of changing this setting:** Only purchases containing the specified products or from the specified categories will activate this rule.
   - **Recommended value:** Be precise. Use the search tool to select all relevant products or categories.
   - **Merchant scenario / example:** For the “VIP Buyers” group, you might select high-value products like “Luxury Watch X” and “Diamond Necklace Y”. For “Electronics Enthusiasts”, you might select the entire “Electronics” category.
3. **Minimum Quantity (Optional):**

   - **What this setting does:** If specified, the customer must purchase at least this quantity of the selected products/categories in a single order to be assigned to the group.
   - **Effect of changing this setting:** If a customer buys less than the minimum quantity, the rule won’t apply, even if they bought the specified products.
   - **Recommended value:** Leave empty for any quantity, or set a value like “1” for at least one item, or “5” for bulk buyers.
   - **Merchant scenario / example:** To be a “Wholesale Customer”, they must buy at least 10 units of any product from the “Bulk Goods” category.
4. **Order Status to Trigger Assignment:**

   - **What this setting does:** This determines at which order status the customer group assignment should occur. For example, you might only want to assign groups once an order is “Payment accepted” or “Delivered”.
   - **Effect of changing this setting:** The module will only process the group assignment when an order reaches the selected status. If an order never reaches that status (e.g., “Canceled”), the assignment won’t happen.
   - **Recommended value:** “Payment accepted” or “Delivered” are generally safe choices to ensure the purchase is confirmed.
   - **Merchant scenario / example:** You want to ensure customers have actually paid before they are added to a special group, so you select “Payment accepted”.
5. **Assign to Group (Add or Replace):**

   - **What this setting does:** This crucial option determines how the customer’s group membership is handled.
     - **Add to Group:** The customer will be added to the selected group *in addition* to any groups they are already in.
     - **Replace Current Group:** The customer’s *primary* group will be changed to the selected group, potentially removing them from their previous primary group.
   - **Effect of changing this setting:**
     - *Add to Group:* Customers can belong to multiple groups, allowing for flexible segmentation.
     - *Replace Current Group:* Customers will only belong to one primary group, simplifying management but potentially losing other group affiliations.
   - **Recommended value:** “Add to Group” offers more flexibility for most scenarios. Use “Replace Current Group” carefully, especially if other modules rely on primary group assignments.
   - **Merchant scenario / example:**
     - *Add to Group:* A customer who buys a specific product is added to “VIP Buyers” but remains in “General Customers”.
     - *Replace Current Group:* A customer who buys a specific product is moved from “General Customers” to “Wholesale Customers”, becoming their new primary group.

**Recommended workflow for daily store management:**

1. **Plan your customer segments:** Before creating rules, decide which customer groups you want to have and what criteria define them.
2. **Create your customer groups:** Go to **Customers > Groups** in your PrestaShop Back Office and create any new groups you need (e.g., “Wholesale”, “VIP”, “Product X Buyers”).
3. **Define rules:** For each customer group, create a new association rule in the module’s configuration.
4. **Test thoroughly:** Make a test purchase with a test customer account to ensure the group assignment happens as expected.
5. **Review regularly:** Periodically check your rules and customer group assignments to ensure they are still relevant to your business goals.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration Page** | Module Enabled/Disabled | Enabled | Controls whether the module actively processes orders for group assignments. |
| **Product Group Associations** | Target Customer Group | N/A (User Defined) | The group customers will be assigned to. |
|  | Products / Categories | N/A (User Defined) | The specific products or categories whose purchase triggers the assignment. |
|  | Minimum Quantity | Empty (Any quantity) | Minimum number of items from the rule’s products/categories required in an order. |
|  | Order Status to Trigger | Payment accepted / Delivered | The order status at which the group assignment is processed. |
|  | Assignment Type | Add to Group | Determines if the customer is added to the group or if their primary group is replaced. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My customers aren’t being assigned to groups after they purchase. What’s wrong?**
A:

1. **Check Module Status:** Ensure the module is enabled in **Modules > Module Manager** and on its main configuration page.
2. **Verify Order Status:** Check your rule’s “Order Status to Trigger Assignment” setting. Has the customer’s order actually reached that specific status (e.g., “Payment accepted”, “Delivered”)? Orders in “Pending” or “Canceled” status won’t trigger the assignment if your rule specifies a later status.
3. **Review Rule Conditions:** Double-check the products/categories selected in your rule. Are they exactly what the customer purchased? Is the “Minimum Quantity” met?
4. **Clear Cache:** Sometimes PrestaShop’s cache can cause issues. Go to **Advanced Parameters > Performance** and click “Clear cache”.
5. **Check for Conflicts:** Temporarily disable other modules that modify customer groups or order processing to see if there’s a conflict.

**Q: Can a customer be in multiple groups?**
A: Yes, if you use the “Add to Group” option when creating your rules. This allows customers to accumulate group memberships based on various purchase behaviors. If you use “Replace Current Group”, they will only be in one primary group.

**Q: What happens if a customer buys products that trigger multiple rules?**
A: The module will process all applicable rules. If rules use “Add to Group”, the customer will be added to all relevant groups. If rules use “Replace Current Group”, the last rule processed (based on internal module logic or order of rule creation) might determine the final primary group, but it’s best practice to avoid conflicting “Replace” rules.

**Q: I’ve changed a rule, but old orders aren’t updating. Why?**
A: The module typically processes group assignments when an order *changes* to the specified status. It does not retroactively apply rules to already completed and processed orders. If you need to re-evaluate past customers, you might need to manually assign them or consider a custom script (for developers) to re-run the logic.

**Q: How do I translate the module’s text?**
A: Go to **International > Translations** in your PrestaShop Back Office. Select “Installed modules translations”, choose your theme, and then select “Assign customers to group by purchased products” from the module list. You can then translate all visible strings.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Assign customers to group by purchased products” module (`pgroup`) follows a standard PrestaShop module architecture, primarily leveraging the MVC pattern for its Back Office components. It integrates with PrestaShop’s core functionality through hooks, specifically by reacting to order status changes to trigger its customer group assignment logic. The module does not introduce any front-office controllers, as its functionality is entirely backend-driven. It utilizes a custom AdminController for managing product-to-group association rules and relies on PrestaShop’s `ObjectModel` for data persistence.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. All logic is handled in the Back Office or via hooks.
- **Back-Office Admin Controllers**:

  - `pgroup/controllers/admin/AdminProductGroupsAssociationsController.php`
    - **Class Name:** `AdminProductGroupsAssociationsController` (extends `ModuleAdminController`)
    - **Responsibility:** This is the primary controller for managing the product-to-customer-group association rules. It handles the display of the list of rules (using `HelperList`), and the creation/editing of individual rules (using `HelperForm`). It interacts with the `PgAssign` `ObjectModel` to persist and retrieve the association data. This controller is responsible for rendering the grid of associations and the form for adding/editing them.
  - `pgroup/controllers/admin/index.php`
    - **Class Name:** Not a class, typically an empty file or a simple redirect to prevent direct directory access. In PrestaShop, `index.php` files within controller directories usually serve as security placeholders.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes in the `classes/` directory. This suggests that the primary data model for the product-group assignments is likely defined directly within the main module file (`pgroup/index.php`) as an `ObjectModel` or handled through direct database queries.

- **Likely Model (within `pgroup/index.php`):**
  - **Class Name:** `PgAssign` (or similar, extending `ObjectModel`)
  - **Database Table:** `ps_pgassign` (or similar, based on the `AdminProductGroupsAssociationsController` managing `pgassign` entity).
  - **`$definition` fields:** Would typically include fields like:
    - `id_pgassign` (Primary Key)
    - `id_group` (ID of the target customer group)
    - `id_product` (ID of the product, if rule is product-specific)
    - `id_category` (ID of the category, if rule is category-specific)
    - `min_quantity` (Minimum quantity required)
    - `id_order_state` (Order status to trigger the assignment)
    - `assignment_type` (e.g., ‘add’ or ‘replace’)
  - **Key Public Methods:**
    - `add()`: To save a new association rule.
    - `update()`: To modify an existing association rule.
    - `delete()`: To remove an association rule.
    - `getAssociationsByProduct($id_product)`: To retrieve rules based on a product.
    - `getAssociationsByCategory($id_category)`: To retrieve rules based on a category.

### 4.4 JavaScript Assets (`views/js/`)

- `pgroup/lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Back-office (likely used in the `AdminProductGroupsAssociationsController` form).
  - **Functionality:** Implements an autocomplete search feature, probably for selecting products or categories when creating/editing an assignment rule. It listens for user input in a specific text field, sends AJAX requests to a backend endpoint (likely a dedicated admin AJAX controller or the main module’s `ajaxProcess` method) to fetch matching products/categories, and displays suggestions. It then handles the selection of an item, populating hidden input fields with IDs.

### 4.5 CSS Stylesheets (`views/css/`)

- `pgroup/css.css`
  - **Scope:** Back-office (general module styling).
  - **Functionality:** Contains general styling rules for the module’s configuration page and potentially the `AdminProductGroupsAssociationsController` interface. This might include styles for form elements, buttons, or layout adjustments specific to the module.
- `pgroup/lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Back-office (autocomplete specific styling).
  - **Functionality:** Provides styling for the autocomplete search input field, the dropdown list of suggestions, and highlighted items within the list. Developers can override these classes to match custom Back Office themes.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**: None explicitly listed, indicating the module’s front-office impact is indirect and not through direct content injection via hooks.
- **Admin templates (`views/templates/admin/`)**:

  - `pgroup/lib/searchTool/views/scripts.tpl`
    - **Scope:** Back-office.
    - **Functionality:** Likely includes JavaScript initialization scripts for the autocomplete functionality. This template would be included in the `AdminProductGroupsAssociationsController`’s form to render the necessary JS for the product/category search tool.
  - `pgroup/views/templates/admin/orderstates.tpl`
    - **Scope:** Back-office.
    - **Functionality:** This template probably renders a dropdown or list of PrestaShop order statuses, allowing the merchant to select which status should trigger the customer group assignment. It would be part of the `HelperForm` used in `AdminProductGroupsAssociationsController`.
  - `pgroup/views/templates/admin/script.tpl`
    - **Scope:** Back-office.
    - **Functionality:** Could contain additional JavaScript or Smarty logic specific to the module’s configuration page or the `AdminProductGroupsAssociationsController` forms, such as conditional display of fields or AJAX calls.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - `ps_pgassign`: This table is created by the module during installation. It stores the product-to-group association rules.
    - `id_pgassign` (INT, PRIMARY KEY, AUTO\_INCREMENT)
    - `id_group` (INT, foreign key to `ps_group`)
    - `id_product` (INT, foreign key to `ps_product`, nullable if rule is category-based)
    - `id_category` (INT, foreign key to `ps_category`, nullable if rule is product-based)
    - `min_quantity` (INT, default 1)
    - `id_order_state` (INT, foreign key to `ps_order_state`)
    - `assignment_type` (VARCHAR, e.g., ‘add’, ‘replace’)
  - Configuration records in `ps_configuration`: The module might store its main `PS_PGROUP_ENABLED` (or similar) setting here.
- **Registered Hooks Table**:
  The module’s core functionality relies on hooks that trigger when an order status changes.

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `actionOrderStatusPostUpdate` | Executed immediately after an order’s status has been updated. | This is the most likely hook used by the module to check if an order has reached the configured status and then apply the group assignment rules based on the products in that order. |
  | `actionObjectOrderUpdateAfter` | Executed after an Order object has been updated. | Could also be used, similar to `actionOrderStatusPostUpdate`, to react to order changes. |
  | `displayHeader` | Renders content in the `<head>` section of front-office pages. | Not directly used for core functionality, but could be used to load global JS/CSS if the module had front-office components (which it doesn’t seem to have). |
  | `displayRightColumn` / `displayLeftColumn` | Renders content in the side columns of front-office pages. | Not directly used for core functionality. |
  | `displayProductAdditionalInfo` / `displayProductButtons` | Renders content on the product page. | Not directly used for core functionality. |
  | `displayFooter` | Renders content in the footer of front-office pages. | Not directly used for core functionality. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Assign customers to group by purchased products” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and integration.
