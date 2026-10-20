---
title: "Minimal order value by manufacturer - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Minimal order value by manufacturer PrestaShop module by MyPresta.eu."
sidebar:
  label: "Minimal order value by manufacturer - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Minimal order value by manufacturer Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/minimal-order-value-by-manufacturer.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/minimal-order-value-by-manufacturer/)
>
> ---


# Minimal order value by manufacturer

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the module, accessible directly after installation or by clicking “Configure” next to the module in the Module Manager.

- **What this screen does:** This page allows you to enable/disable the module and manage the core settings that control its behavior.

#### Settings & Options

- **Enable / Disable Module:**

  - **What this setting does:** This is a global switch to turn the entire module’s functionality on or off.
  - **Effect of changing this setting:**
    - *When enabled:* The module will actively check for minimum order values by manufacturer in customer carts and apply restrictions if conditions are not met.
    - *When disabled:* The module will cease to function. No minimum order value checks will be performed, and customers can order any amount from any manufacturer.
  - **Recommended value:** **YES** (to activate the module’s core function).
  - **Merchant scenario / example:** If you’re testing the module or temporarily want to disable all minimum order rules without deleting them, you can switch this off.
- **Display message on shopping cart page:**

  - **What this setting does:** Controls whether a warning message is shown to the customer on the shopping cart page if a manufacturer’s minimum order value is not met.
  - **Effect of changing this setting:**
    - *When enabled:* Customers will see a clear, informative message on their cart page, indicating which manufacturer’s minimum is not met and how much more they need to add.
    - *When disabled:* No message will appear on the cart page. The restriction will still apply, but the customer might only discover it later during checkout, potentially leading to frustration.
  - **Recommended value:** **YES**.
  - **Merchant scenario / example:** Enabling this provides a better user experience, guiding customers to resolve the issue early rather than surprising them at checkout.
- **Display message on checkout page:**

  - **What this setting does:** Controls whether a warning message is shown to the customer on the checkout page if a manufacturer’s minimum order value is not met.
  - **Effect of changing this setting:**
    - *When enabled:* Customers will see a message on the checkout page, preventing them from completing the order until the minimum is met.
    - *When disabled:* The checkout process might simply halt without a clear explanation, or the module might prevent progression without a specific message, which can confuse customers.
  - **Recommended value:** **YES**.
  - **Merchant scenario / example:** This is crucial for preventing orders that don’t meet your criteria and for clearly communicating the reason to the customer.
- **Message to display (for shopping cart and checkout pages):**

  - **What this setting does:** Allows you to customize the text of the warning message displayed to customers when a minimum order value is not met. You can use placeholders like `{manufacturer_name}` and `{missing_amount}`.
  - **Effect of changing this setting:**
    - *When changed:* The custom message will appear on the front office.
    - *When left default:* A standard message will be used.
  - **Recommended value:** Customize to be clear and helpful. Example: “To complete your order, you need to add {missing\_amount} more from {manufacturer\_name} products.”
  - **Merchant scenario / example:** You might want to make the message more friendly, include a call to action, or align it with your brand’s tone of voice.

### 2.2 Dedicated Admin Screens: Minimal Order Value by Manufacturer Rules (Back Office > Catalog > Minimal Order Value by Manufacturer)

This screen is where you define and manage the actual minimum order value rules for each manufacturer.

- **Screen Name & Menu Location:** “Minimal Order Value by Manufacturer” under the **Catalog** menu.
- **What this screen does:** This is a dedicated management area to add, edit, and delete rules for minimum order values per manufacturer. It presents a list of all currently configured rules.

#### Available Actions & Settings

- **List of Rules:**

  - **What this does:** Displays a table of all existing minimum order value rules. Each row typically shows the manufacturer’s name, the set minimum value, and options to edit or delete the rule.
  - **Effect of changes:** This table provides an overview of all active rules.
  - **Recommended workflow:** Regularly review this list to ensure your rules are up-to-date with your business needs.
- **“Add new rule” button:**

  - **What this does:** Clicking this button takes you to a form where you can create a new minimum order value rule.
  - **Effect of changes:** Opens a new form.
  - **Recommended workflow:** Use this when you need to set a new minimum for a manufacturer not yet in the list.
- **“Edit” button (for each rule):**

  - **What this does:** Allows you to modify an existing rule’s settings.
  - **Effect of changes:** Opens the rule’s form with pre-filled data, allowing you to change the manufacturer or the minimum value.
  - **Recommended workflow:** Use this to adjust minimums based on new supplier agreements or sales strategies.
- **“Delete” button (for each rule):**

  - **What this does:** Removes a specific minimum order value rule.
  - **Effect of changes:** The rule is immediately removed, and the associated manufacturer will no longer have a minimum order value requirement.
  - **Recommended workflow:** Use this when a manufacturer no longer requires a minimum order, or if you’re discontinuing a brand.

#### Add/Edit Rule Form

When adding a new rule or editing an existing one, you will typically see the following fields:

- **Manufacturer:**

  - **What this setting does:** This field allows you to select the specific manufacturer to whom this minimum order value rule will apply. It usually features an autocomplete search to help you find manufacturers easily.
  - **Effect of changing this setting:** Links the rule to a particular manufacturer.
  - **Recommended value:** Select the exact manufacturer you intend to apply the rule to.
  - **Merchant scenario / example:** You might select “Apple” to set a minimum for all Apple products, or “Samsung” for Samsung products.
- **Minimal Order Value:**

  - **What this setting does:** This is where you enter the numerical value (in your store’s default currency, e.g., USD, EUR) that represents the minimum total amount required for products from the selected manufacturer.
  - **Effect of changing this setting:**
    - *When set to a value (e.g., 50.00):* Customers must have at least 50.00 worth of products from the selected manufacturer in their cart to proceed.
    - *When set to 0 or left empty:* This effectively disables the minimum for that manufacturer (though it’s better to delete the rule if no minimum is needed).
  - **Recommended value:** A positive numerical value reflecting your business requirements.
  - **Merchant scenario / example:** If your supplier for “BrandX” requires you to order at least $100 worth of their products, you would set this to “100.00” for “BrandX”.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable / Disable Module | YES | Global switch for module functionality. |
| Module Configuration | Display message on shopping cart page | YES | Shows warning on cart if minimum not met. |
| Module Configuration | Display message on checkout page | YES | Shows warning on checkout if minimum not met. |
| Module Configuration | Message to display | Customizable | Customizes the warning message text. |
| AdminMobmController | Manufacturer (Add/Edit Rule) | Select from list | Links rule to a specific manufacturer. |
| AdminMobmController | Minimal Order Value (Add/Edit Rule) | Numerical value | Sets the minimum total value for selected manufacturer’s products. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve set a minimum, but it’s not working on the front office. What should I check?**
A1:

- **Is the module enabled?** Go to `Modules > Module Manager` and ensure “Minimal order value by manufacturer” is active.
- **Is the specific rule enabled?** Check `Catalog > Minimal Order Value by Manufacturer` to ensure the rule for the manufacturer in question is correctly configured with a positive value.
- **Clear Cache:** Go to `Advanced Parameters > Performance` and click “Clear cache” (for all caches). Sometimes, PrestaShop’s cache can prevent changes from appearing immediately.
- **Check for Conflicts:** Temporarily disable other modules that modify the cart or checkout process to see if there’s a conflict.

**Q2: The message on the cart/checkout page isn’t showing up.**
A2:

- **Check module configuration:** Go to `Modules > Module Manager > Configure` for “Minimal order value by manufacturer”. Ensure “Display message on shopping cart page” and “Display message on checkout page” are both set to **YES**.
- **Is the minimum actually unmet?** Double-check that the products in the cart from the specific manufacturer truly fall below the set minimum.

**Q3: Can I set different minimums for different customer groups?**
A3: This module, in its standard form, applies a single minimum value per manufacturer to all customers. If you require customer-group-specific minimums, this would require custom development or a different module.

**Q4: How does the module handle multi-currency stores?**
A4: The module uses your store’s default currency (as defined in `Localization > Currencies` and `Localization > Localization`) for the “Minimal Order Value” you set. It will automatically convert the customer’s cart total to the default currency for comparison, ensuring consistency.

**Q5: The module seems to be slowing down my site. What can I do?**
A5:

- **Clear Cache:** Ensure all caches are cleared regularly (`Advanced Parameters > Performance`).
- **Server Resources:** Check your hosting environment’s resources (CPU, RAM). If your store has a very large number of manufacturers or products, ensure your server can handle the load.
- **Module Updates:** Always use the latest version of the module from MyPresta.eu, as updates often include performance improvements.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the “Minimal order value by manufacturer” module for developers and webmasters.

### 4.1 Architecture Overview

The module follows a standard PrestaShop MVC (Model-View-Controller) pattern. It primarily extends `Module` for its core functionality and configuration, utilizes `AdminController` for back-office management of rules, and `ModuleFrontController` for front-office AJAX interactions related to cart validation. It does not appear to use custom `ObjectModel` classes, instead relying on `Configuration` for general settings and direct database interaction (or potentially a simple array structure) for manufacturer-specific rules. Hooks are extensively used to integrate into the cart and checkout flow.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `controllers/front/ajax.php`
  - **Class Name:** `MobmAjaxModuleFrontController` (likely, based on file naming convention) extending `ModuleFrontController`.
  - **Responsibility:** This controller is likely responsible for handling AJAX requests from the front-office, particularly those related to cart updates or checkout progression. It would receive cart data, perform the minimum order value checks, and return a JSON response indicating whether the conditions are met and what messages should be displayed. This is crucial for dynamic updates without full page reloads.
- `controllers/front/index.php`
  - **Class Name:** `MobmIndexModuleFrontController` (likely) extending `ModuleFrontController`.
  - **Responsibility:** This file might be a placeholder or used for a simple front-office page if the module had one. Given the module’s purpose, it’s less likely to render a full page and more likely to be a fallback or part of a redirect chain if the `ajax.php` is the primary interaction point.

#### Back-Office Admin Controllers

- `controllers/admin/AdminMobm.php`
  - **Class Name:** `AdminMobmController` extending `ModuleAdminController`.
  - **Tab Name:** “Minimal Order Value by Manufacturer” (under Catalog).
  - **Managed Entity:** Manages the `mobm` entity, which represents the individual minimum order value rules for manufacturers.
  - **Responsibility:** This is the primary controller for managing the list of manufacturer minimum order rules. It handles:
    - Displaying the list of existing rules (using `renderList()`).
    - Adding new rules (using `renderForm()` for the add form).
    - Editing existing rules (using `renderForm()` for the edit form).
    - Deleting rules.
    - Form validation and saving data.
    - It likely interacts with the `ps_configuration` table or a custom table to store the manufacturer ID and their associated minimum value.
- `controllers/admin/index.php`
  - **Class Name:** `AdminMobmIndexModuleAdminController` (likely) extending `ModuleAdminController`.
  - **Responsibility:** Similar to the front-office `index.php`, this might be a placeholder or a default entry point. In PrestaShop, `index.php` files in controller directories often serve as basic security measures (e.g., `die('Access Denied');`) or simple routing if not explicitly handled by a more specific controller.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes in the `classes/` directory. This suggests that the module either:

1. Stores its manufacturer rules directly in the `ps_configuration` table (e.g., as a serialized array).
2. Uses direct database queries within the main module file or admin controller to manage a custom table.
3. Manages data as a simple array within the module’s context without a formal `ObjectModel`.

Given the `AdminMobmController` manages a `mobm` entity, it’s highly probable that a custom table (e.g., `ps_mobm`) is created during installation, and the `AdminMobmController` implicitly handles CRUD operations for this table without a dedicated `ObjectModel` class in `classes/`. The `$definition` for this entity would then be defined directly within the `AdminMobmController` or the main module file.

### 4.4 JavaScript Assets (`views/js/`)

- `mobm/lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Back-office (likely for the `AdminMobmController` form).
  - **Responsibility:** Provides autocomplete functionality for selecting manufacturers in the “Add/Edit Rule” form. It listens for user input in a text field, sends AJAX requests to a back-office controller (e.g., `AdminManufacturers` or a custom `AdminMobm` method) to fetch matching manufacturer names, and displays suggestions.
- `mobm/views/js/mobm.js`
  - **Scope:** Front-office.
  - **Responsibility:** This is the main front-office JavaScript for the module. It likely:
    - Binds to events on the shopping cart page (e.g., quantity changes, product removals).
    - Binds to events on the checkout page (e.g., “Proceed to checkout” button clicks).
    - Sends AJAX requests to `controllers/front/ajax.php` to validate the cart against manufacturer minimums.
    - Receives JSON responses and dynamically updates the UI with warning messages or prevents progression if minimums are not met.
    - Might handle modal popups or visual cues for the customer.

### 4.5 CSS Stylesheets (`views/css/`)

- `mobm/lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Back-office.
  - **Responsibility:** Styles the autocomplete dropdown and input field used for manufacturer selection in the admin form.
  - **Key CSS Class Selectors:** Likely targets classes like `.autocomplete-suggestions`, `.autocomplete-suggestion`, `.autocomplete-selected`, etc.
- `mobm/views/css/mobm.css`
  - **Scope:** Front-office.
  - **Responsibility:** Styles the warning messages displayed on the shopping cart and checkout pages. Ensures these messages are visually distinct and integrate well with the theme.
  - **Key CSS Class Selectors:** Likely targets custom classes added by the module to the warning message containers, e.g., `.mobm-warning-message`, `.mobm-error-block`.

### 4.6 Smarty Template Structure (`views/templates/`)

- `mobm/lib/searchTool/views/scripts.tpl`
  - **Scope:** Back-office.
  - **Responsibility:** This template likely includes the necessary JavaScript for the autocomplete functionality (from `autocomplete.js`) and potentially some inline script or configuration for it. It would be rendered within the `AdminMobmController`’s `renderForm()` method.
- `mobm/views/templates/front/displayShoppingCart.tpl`
  - **Scope:** Front-office.
  - **Hook:** This template is designed to be rendered in a hook that displays content on the shopping cart page, such as `displayShoppingCartFooter` or `displayBeforeShoppingCartBlock`.
  - **Responsibility:** Displays the warning message to the customer if a manufacturer’s minimum order value is not met. It will contain the logic to show the message only when `{$mobm_warning_message}` (or similar variable passed from the module) is not empty.

### 4.7 Database Schema & Hooks Map

#### Database Tables

- **`ps_configuration`**: Stores general module settings (e.g., `PS_MOVB_ENABLED`, `PS_MOVB_CART_MSG_ENABLED`, `PS_MOVB_CHECKOUT_MSG_ENABLED`, `PS_MOVB_CUSTOM_MESSAGE`).
- **`ps_mobm` (Likely custom table)**: This table is highly probable given the `AdminMobmController` managing a `mobm` entity.
  - **Columns (Hypothetical):**
    - `id_mobm` (Primary Key, INT)
    - `id_manufacturer` (INT, Foreign Key to `ps_manufacturer`)
    - `min_value` (DECIMAL(20,6), stores the minimum order amount)
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of all front-office pages. | To include front-office CSS (`mobm.css`) and JavaScript (`mobm.js`) assets. |
| `actionCartSave` | After a cart is saved (e.g., quantity change, product added/removed). | To perform real-time validation of manufacturer minimums and potentially store validation status. |
| `actionValidateOrder` | Before an order is officially validated. | To prevent order validation if any manufacturer minimums are not met. |
| `displayShoppingCartFooter` (or similar) | At the bottom of the shopping cart page. | To display the warning message (`displayShoppingCart.tpl`) if minimums are not met. |
| `displayPaymentTop` (or similar checkout hook) | At the top of the payment selection step in checkout. | To display the warning message and prevent progression if minimums are not met. |
| `displayAdminProductsExtra` (or similar) | On the product edit page in the back office. | Potentially to display information about the manufacturer’s minimum value directly on product pages (less likely but possible). |
| `displayBackOfficeHeader` | In the `<head>` section of all back-office pages. | To include back-office CSS (`autocomplete.css`) and JavaScript (`autocomplete.js`) for the `AdminMobmController` form. |

## 5. Official Support & Updates

For official updates, technical support, and to ensure you are running the latest, most compatible version of the “Minimal order value by manufacturer” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu). Our support team is available to assist with any issues or questions you may have.
