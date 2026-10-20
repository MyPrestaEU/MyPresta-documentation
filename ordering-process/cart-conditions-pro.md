---
title: "Cart conditions pro - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Cart conditions pro PrestaShop module by MyPresta.eu."
sidebar:
  label: "Cart conditions pro - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Cart conditions pro Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/cart-conditions-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/cart-conditions-pro/)
>
> ---


# Cart conditions pro

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and are sufficient for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Cart conditions pro)

This is the main configuration screen for the module, where you set up global behaviors and access the specific condition management areas.

- **What this setting does:** Controls the overall behavior of the module and provides quick links to manage your conditions.
- **Effect of changing this setting:** Determines how broadly the conditions apply and how certain edge cases are handled.

#### General Settings

1. **Exclude customers from conditions**

   - **What this setting does:** Allows you to specify certain customer groups or individual customers who will be exempt from any cart conditions you set up.
   - **Effect of changing this setting:**
     - *When enabled (and customers/groups selected):* The selected customers/groups will always be able to proceed to checkout, regardless of whether their cart meets the conditions.
     - *When disabled (or no customers/groups selected):* All customers will be subject to the cart conditions.
   - **Recommended value:** “Off” by default, unless you have specific B2B clients or VIPs you want to exempt.
   - **Merchant scenario / example:** You have a wholesale customer group that always gets special treatment and shouldn’t be restricted by minimum order values.
2. **Exclude products from conditions**

   - **What this setting does:** Allows you to specify certain products that will not count towards or be affected by any cart conditions. This is useful for free gifts, samples, or specific promotional items.
   - **Effect of changing this setting:**
     - *When enabled (and products selected):* The selected products will be ignored when evaluating cart conditions. For example, if you have a “minimum 3 items” condition, and a customer has 2 regular items + 1 excluded item, the condition might still fail.
     - *When disabled (or no products selected):* All products in the cart will be considered when evaluating conditions.
   - **Recommended value:** “Off” by default. Enable only if you have specific products that should be exempt from conditions.
   - **Merchant scenario / example:** You offer a free sample product with every order. You don’t want this sample to count towards a minimum product quantity condition.
3. **Block order of products with Various availability date**

   - **What this setting does:** This option specifically addresses products that have different availability dates (e.g., pre-order items with staggered release dates). If enabled, it prevents customers from ordering a mix of immediately available and future-available products in the same cart.
   - **Effect of changing this setting:**
     - *When “On”:* If a customer’s cart contains products with different availability dates, they will be blocked from checkout. They would need to place separate orders for items with different availability.
     - *When “Off”:* Customers can order products with various availability dates in a single cart.
   - **Recommended value:** “Off” unless you have specific logistical reasons to separate orders based on availability.
   - **Merchant scenario / example:** You sell both in-stock items and pre-order items. To simplify shipping and avoid holding orders, you want customers to place separate orders for pre-order items.

#### Condition Management Links

Below the general settings, you will find links to manage different types of conditions. These links will take you to dedicated administration screens.

- **Manage Conditions (General):** This is where you define broad conditions based on product associations, categories, or other general rules.
- **Manage Country Conditions:** Define conditions that apply only to customers from specific countries.
- **Manage Quantity Conditions:** Set minimum or maximum quantities of products/categories required in the cart.
- **Manage Value Conditions:** Set minimum or maximum total cart values required.

### 2.2 Dedicated Admin Screens & Controller Views

#### 2.2.1 AdminCartConditionController (Back Office > Modules > Cart conditions pro > Manage Conditions)

This screen allows you to define general conditions, often based on product or category associations.

- **Screen Name & Menu Location:** “Manage Conditions” (accessible from the main module configuration page).
- **Available Actions & Settings:**
  - **Listing Table:** Displays all existing general conditions with their names, associated products/categories, and status.
  - **Add New Condition Button:** Allows you to create a new condition.
    - **Condition Name:** A descriptive name for your internal reference.
    - **Products/Categories:** Select specific products or entire categories that must be present (or not present) in the cart.
    - **Customer Groups:** Apply this condition only to specific customer groups.
    - **Minimum/Maximum Quantity:** Define a range for the number of selected products/categories.
    - **Minimum/Maximum Value:** Define a range for the total value of selected products/categories.
    - **Message:** The message displayed to the customer if the condition is not met.
    - **Active:** Enable or disable the condition.
  - **Edit/Delete Buttons:** Modify or remove existing conditions.
- **Effect of changes:**
  - Adding a new condition immediately applies that rule to customer carts.
  - Modifying a condition updates its criteria and message.
  - Deleting a condition removes the restriction.
- **Recommended workflow for daily store management:** Regularly review your conditions, especially after adding new products, categories, or running promotions, to ensure they align with your current sales strategy.

#### 2.2.2 AdminCartAssociationsConditionController (Back Office > Modules > Cart conditions pro > Manage Conditions > (Specific Condition) > Associations)

This screen is typically accessed when editing a general condition and allows you to specify which products or categories are *associated* with that condition.

- **Screen Name & Menu Location:** Accessed by editing a condition from “Manage Conditions”.
- **Available Actions & Settings:**
  - **Search & Select Products/Categories:** Tools to find and add specific products or entire categories that are part of this condition.
  - **Selected Products/Categories List:** Shows all items currently associated with the condition.
  - **Remove Button:** Remove an item from the association.
- **Effect of changes:** Directly impacts which products or categories are evaluated by the parent condition. For example, if a condition states “Cart must contain at least 2 items from the ‘Electronics’ category,” this screen is where you define which products belong to that “Electronics” category for this specific condition.
- **Recommended workflow for daily store management:** When creating or updating a condition, ensure all relevant products and categories are correctly associated.

#### 2.2.3 AdminCartCountryConditionController (Back Office > Modules > Cart conditions pro > Manage Country Conditions)

This screen allows you to define conditions that are specific to the customer’s shipping country.

- **Screen Name & Menu Location:** “Manage Country Conditions” (accessible from the main module configuration page).
- **Available Actions & Settings:**
  - **Listing Table:** Displays existing country-specific conditions.
  - **Add New Condition Button:**
    - **Country:** Select the target country.
    - **Minimum/Maximum Quantity:** For all products in the cart, or specific products/categories.
    - **Minimum/Maximum Value:** For the total cart value.
    - **Message:** The message displayed if the condition is not met.
    - **Active:** Enable or disable.
- **Effect of changes:** Applies specific cart rules only to customers whose shipping address is in the selected country.
- **Recommended workflow for daily store management:** Useful for international stores with varying shipping costs, customs regulations, or market strategies per country.

#### 2.2.4 AdminCartQuantityConditionController (Back Office > Modules > Cart conditions pro > Manage Quantity Conditions)

This screen focuses on conditions related to the total number of items in the cart, or the quantity of specific items/categories.

- **Screen Name & Menu Location:** “Manage Quantity Conditions” (accessible from the main module configuration page).
- **Available Actions & Settings:**
  - **Listing Table:** Shows all quantity-based conditions.
  - **Add New Condition Button:**
    - **Condition Name:**
    - **Minimum/Maximum Total Quantity:** For the entire cart.
    - **Minimum/Maximum Quantity of Specific Products/Categories:** Select items and set quantity rules for them.
    - **Customer Groups:** Apply to specific groups.
    - **Message:**
    - **Active:**
- **Effect of changes:** Enforces rules based on the count of items in the cart, which can be used to encourage bulk purchases or manage inventory.
- **Recommended workflow for daily store management:** Use this for “buy X get Y” promotions, minimum order quantity (MOQ) for wholesale, or ensuring customers meet a certain threshold for free shipping.

#### 2.2.5 AdminCartValueConditionController (Back Office > Modules > Cart conditions pro > Manage Value Conditions)

This screen is for setting conditions based on the total monetary value of the customer’s cart.

- **Screen Name & Menu Location:** “Manage Value Conditions” (accessible from the main module configuration page).
- **Available Actions & Settings:**
  - **Listing Table:** Displays existing value-based conditions.
  - **Add New Condition Button:**
    - **Condition Name:**
    - **Minimum/Maximum Total Cart Value:** Set a range for the entire cart’s value.
    - **Customer Groups:**
    - **Message:**
    - **Active:**
- **Effect of changes:** Enforces rules based on the monetary value of the cart, directly impacting average order value.
- **Recommended workflow for daily store management:** Ideal for setting a minimum order value for free shipping, or a general minimum order value to ensure profitability.

#### 2.2.6 index.php (cartcon/controllers/admin/index.php)

This file is a standard PrestaShop practice to prevent directory listing and does not represent a configurable screen. It simply contains `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../"); exit;` to redirect if someone tries to access the directory directly.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Exclude customers from conditions | Off | Exempt specific customers/groups from all conditions. |
|  | Exclude products from conditions | Off | Exempt specific products from all conditions. |
|  | Block order of products with Various availability date | Off | Prevent mixed orders of in-stock and pre-order items. |
| **Manage Conditions** | Condition Name | User Defined | Internal label for the condition. |
|  | Products/Categories | User Defined | Select items/categories required or restricted. |
|  | Customer Groups | All | Apply condition to specific customer segments. |
|  | Min/Max Quantity | User Defined | Set quantity range for selected items/categories. |
|  | Min/Max Value | User Defined | Set value range for selected items/categories. |
|  | Message | User Defined | Customer-facing message when condition is not met. |
|  | Active | Yes | Enable/disable the condition. |
| **Manage Country Conditions** | Country | User Defined | Target specific countries for conditions. |
|  | Min/Max Quantity | User Defined | Quantity range for carts from selected country. |
|  | Min/Max Value | User Defined | Value range for carts from selected country. |
|  | Message | User Defined | Customer message for country-specific failure. |
|  | Active | Yes | Enable/disable country condition. |
| **Manage Quantity Conditions** | Condition Name | User Defined | Internal label for quantity condition. |
|  | Min/Max Total Quantity | User Defined | Quantity range for the entire cart. |
|  | Min/Max Quantity of Specific Products/Categories | User Defined | Quantity range for selected items/categories. |
|  | Customer Groups | All | Apply to specific customer segments. |
|  | Message | User Defined | Customer message for quantity failure. |
|  | Active | Yes | Enable/disable quantity condition. |
| **Manage Value Conditions** | Condition Name | User Defined | Internal label for value condition. |
|  | Min/Max Total Cart Value | User Defined | Value range for the entire cart. |
|  | Customer Groups | All | Apply to specific customer segments. |
|  | Message | User Defined | Customer message for value failure. |
|  | Active | Yes | Enable/disable value condition. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My conditions are set, but they don’t seem to be working on the front office. What’s wrong?**
**A1:**

- **Check Condition Status:** Ensure the “Active” switch for each condition you’ve set is turned “Yes”.
- **Clear Cache:** PrestaShop often caches content. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions).
- **Module Position:** Verify the module is hooked correctly. The `displayShoppingCart` and `displayPaymentTop` hooks are crucial. If your theme has custom hooks, you might need developer assistance.
- **Customer Groups:** Double-check if the conditions are applied to the correct customer groups, and if your test customer belongs to that group.
- **Product/Category IDs:** When selecting products or categories, ensure you’ve picked the correct ones. Sometimes similar names can cause confusion.

**Q2: The message displayed to customers is not clear or doesn’t look good with my theme.**
**A2:**

- **Edit Message:** Go to the specific condition (e.g., Manage Value Conditions, then edit the condition) and update the “Message” field with clearer, more helpful text.
- **Theme Styling:** The visual appearance (font, color, size) of the message is controlled by your PrestaShop theme’s CSS. If you need to change the styling, you’ll need to consult a web designer or developer to add custom CSS rules to your theme. The module’s CSS files (`cartcon.css`) provide the base styling.

**Q3: Can I set different conditions for different languages/countries?**
**A3:**

- **Country-Specific Conditions:** Yes, use the “Manage Country Conditions” screen to set rules that apply only to customers from specific countries.
- **Multi-language Messages:** When editing a condition, the “Message” field usually has a language selector (a flag icon). Click it to provide translations for your message in all active languages of your store.

**Q4: I want to exclude a specific product from ALL conditions. How do I do that?**
**A4:**

- On the main module configuration page (Back Office > Modules > Configure > Cart conditions pro), use the setting “Exclude products from conditions”. You can search for and select the specific products you wish to exempt.

**Q5: The module is blocking checkout, but I can’t find which condition is causing it.**
**A5:**

- **Review All Conditions:** Go through “Manage Conditions”, “Manage Country Conditions”, “Manage Quantity Conditions”, and “Manage Value Conditions” one by one. Check the “Active” status of each and review their criteria.
- **Test Systematically:** If you have many conditions, try disabling them one by one (or in groups) and testing the cart until you identify the culprit. Then, re-enable them and adjust the problematic condition.
- **Check Customer Group:** Ensure your test customer is not part of an excluded customer group.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Cart conditions pro” module follows the standard PrestaShop MVC (Model-View-Controller) pattern, primarily extending `Module` for its main configuration and `AdminController` for dedicated management interfaces. It leverages PrestaShop’s hook system to inject logic and display messages at critical points in the front-office (cart, payment) and uses `ObjectModel` implicitly for managing its various condition entities. The module relies on custom database tables to store its complex condition rules.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

The module does not appear to have dedicated front controllers in the provided inventory. Front-office logic and display are likely handled directly via the main `cartcon.php` module file through hook callbacks.

#### Back-Office Admin Controllers

All admin controllers extend `ModuleAdminController` (or `AdminController` in older PrestaShop versions) and are responsible for managing the various types of conditions.

- `cartcon/controllers/admin/AdminCartAssociationsConditionController.php`

  - **Class Name:** `AdminCartAssociationsConditionController`
  - **Parent Class:** `ModuleAdminController`
  - **Responsibility:** Manages the associations (products, categories) linked to a specific general cart condition. This controller provides the interface for searching and selecting products/categories that are part of a condition’s criteria. It interacts with the `cartcon_ass` table.
- `cartcon/controllers/admin/AdminCartConditionController.php`

  - **Class Name:** `AdminCartConditionController`
  - **Parent Class:** `ModuleAdminController`
  - **Responsibility:** Manages the main, general cart conditions. This is the primary interface for creating, editing, and deleting conditions based on product/category presence, quantity, or value. It interacts with the `cartcon` table.
- `cartcon/controllers/admin/AdminCartCountryConditionController.php`

  - **Class Name:** `AdminCartCountryConditionController`
  - **Parent Class:** `ModuleAdminController`
  - **Responsibility:** Manages cart conditions specifically tied to customer countries. It allows defining rules that only apply when the customer’s shipping country matches a specified country. It interacts with the `cartcon_country` table.
- `cartcon/controllers/admin/AdminCartQuantityConditionController.php`

  - **Class Name:** `AdminCartQuantityConditionController`
  - **Parent Class:** `ModuleAdminController`
  - **Responsibility:** Manages conditions based on the total quantity of items in the cart or the quantity of specific products/categories. It interacts with the `cartcon_quantity` table.
- `cartcon/controllers/admin/AdminCartValueConditionController.php`

  - **Class Name:** `AdminCartValueConditionController`
  - **Parent Class:** `ModuleAdminController`
  - **Responsibility:** Manages conditions based on the total monetary value of the cart. It interacts with the `cartcon_value` table.
- `cartcon/controllers/admin/index.php`

  - **Responsibility:** Standard PrestaShop security file to prevent directory listing. It redirects to the parent directory.

### 4.3 Core Classes & Models (`classes/`)

The provided inventory does not list explicit files in a `classes/` directory. This suggests that the module’s core logic and `ObjectModel` definitions (if any) are either embedded within the main `cartcon.php` file or within the admin controller files themselves, which is a common pattern for simpler modules or older PrestaShop versions. If `ObjectModel`s are used, their `$definition` arrays would be found within the respective controller or main module class.

### 4.4 JavaScript Assets (`views/js/`)

- `cartcon/lib/searchTool/views/js/autocomplete.js`

  - **Scope:** Back-office.
  - **Responsibility:** Provides autocomplete functionality for searching products, categories, or customers within the admin forms (e.g., when setting up exclusions or condition associations). It likely binds to input fields, sends AJAX requests to a search endpoint, and displays suggestions.
- `cartcon/views/js/cartcon.js`

  - **Scope:** Front-office and potentially Back-office.
  - **Responsibility:**
    - **Front-office:** Handles the dynamic display of cart condition messages, disabling/enabling the “Proceed to checkout” button based on AJAX responses from the server regarding cart validity. It might listen for cart updates (`prestashop.on('updateCart', ...)` or similar events) to re-evaluate conditions.
    - **Back-office:** Could contain logic for form validation, dynamic field visibility, or other UI enhancements specific to the module’s configuration pages.

### 4.5 CSS Stylesheets (`views/css/`)

- `cartcon/lib/searchTool/views/css/autocomplete.css`

  - **Scope:** Back-office.
  - **Responsibility:** Styles the autocomplete suggestion dropdowns and search input fields used in the admin forms, ensuring a consistent and user-friendly search experience.
- `cartcon/views/css/cartcon.css`

  - **Scope:** Front-office and Back-office.
  - **Responsibility:**
    - **Front-office:** Styles the notification messages displayed on the cart page, payment page, or product page when conditions are not met. It defines the appearance of the warning boxes, text, and potentially the disabled state of the checkout button.
    - **Back-office:** Provides styling for the module’s configuration forms and list tables, ensuring they integrate well with the PrestaShop back office theme.
  - **Key CSS class selectors developers can override:** Look for classes like `.cartcon-alert`, `.cartcon-message`, `.cartcon-disabled-button` or similar within this file to target and customize the module’s front-office output.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

The module’s front-office display logic is likely embedded directly in the main `cartcon.php` file’s hook methods, which then render these templates.

- `cartcon/views/templates/front/displayShoppingCart.tpl`

  - **Rendered in hook:** `displayShoppingCart`
  - **Purpose:** Displays the cart condition messages and potentially disables the checkout button on the main shopping cart page if conditions are not met. It receives variables from the module’s `hookDisplayShoppingCart` method, indicating the validity of the cart and the message to display.
- `cartcon/views/templates/front/displayShoppingCartEmpty.tpl`

  - **Rendered in hook:** Potentially `displayShoppingCart` or a related hook when the cart is empty.
  - **Purpose:** Provides a specific template for displaying messages or alternative content when the shopping cart is empty, potentially related to minimum order requirements.
- `cartcon/views/templates/front/productActions.tpl`

  - **Rendered in hook:** `displayProductActions` (typically near the “Add to Cart” button on the product page).
  - **Purpose:** Can be used to display subtle hints or warnings on the product page itself if adding the product would violate a cart condition or if the product requires other items to be purchased with it.

#### Admin templates (`views/templates/admin/`)

- `cartcon/lib/searchTool/views/scripts.tpl`

  - **Purpose:** Likely includes JavaScript dependencies or initializes the autocomplete scripts for the admin forms.
- `cartcon/views/templates/admin/AdminCartAssociationsCondition.tpl`

  - **Purpose:** The main template for the `AdminCartAssociationsConditionController`, displaying the interface for managing product/category associations for a condition. This would include search fields, selected item lists, and save buttons.
- `cartcon/views/templates/admin/adminSearchCustomer.tpl`

  - **Purpose:** Template for the customer search interface, used when excluding customers from conditions.
- `cartcon/views/templates/admin/script.tpl`

  - **Purpose:** General admin script template, potentially including module-specific JavaScript or configuration variables for the back office.
- `cartcon/views/templates/admin/search-attribute-value-result.tpl`

  - **Purpose:** Template for displaying the results of an attribute/value search within the admin panel, likely used in conjunction with product searches.
- `cartcon/views/templates/admin/search-attribute-value.tpl`

  - **Purpose:** Template for the search input field and associated UI elements for searching product attributes/values in the admin.
- `cartcon/views/templates/admin/selectedProducts.tpl`

  - **Purpose:** Template for displaying the list of products that have been selected and associated with a particular condition in the admin forms.

### 4.7 Database Schema & Hooks Map

#### Database Tables

The module creates custom tables to store its various conditions and associations. These tables are typically prefixed with `ps_cartcon_` or `cartcon_`.

- `ps_cartcon`: Stores general cart conditions (name, message, active status, etc.).
- `ps_cartcon_ass`: Stores associations between conditions and specific products/categories.
- `ps_cartcon_country`: Stores country-specific conditions.
- `ps_cartcon_quantity`: Stores quantity-based conditions.
- `ps_cartcon_value`: Stores value-based conditions.
- `ps_configuration`: Module settings like `CARTCON_CUSTOMERS`, `ccon_visibility_rule`, `CARTCON_FUTURE`, etc., are stored here.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Used to load module’s CSS and JavaScript assets for both front-office and back-office. |
| `displayPaymentTop` | At the top of the payment selection page during checkout. | Critical for re-evaluating cart conditions just before payment and blocking if necessary. |
| `displayShoppingCart` | On the main shopping cart page. | Primary hook for displaying condition messages and disabling the checkout button. |
| `actionAdminControllerSetMedia` | When an admin controller is loaded and its media (JS/CSS) is being set. | Used to load specific JS/CSS assets for the module’s back-office configuration pages. |
| `displayProductActions` | Typically near the “Add to cart” button on the product page. | Can be used to display product-specific condition hints or warnings. |
| `actionCartSave` | After a cart is saved (e.g., product added/removed, quantity changed). | (Implicit/Likely) The module would likely use an `actionCartSave` or similar hook to trigger the re-evaluation of cart conditions on the server-side, which then informs the front-office JS. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the “Cart conditions pro” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to ensuring the module functions optimally with your PrestaShop store.
