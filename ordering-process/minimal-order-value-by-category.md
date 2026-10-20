---
title: "Minimal order value by category - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Minimal order value by category PrestaShop module by MyPresta.eu."
sidebar:
  label: "Minimal order value by category - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Minimal order value by category Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/minimal-order-value-by-category.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/minimal-order-value-by-category/)
>
> ---


# Minimal order value by category

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and are usually available by default on most hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the module, accessed immediately after installation or by clicking “Configure” from the Module Manager.

- **What this setting does:** This screen primarily serves as an entry point. While the module’s core logic is managed through a dedicated administration screen, this initial configuration page ensures the module is correctly installed and provides a link or redirection to the main management interface.
- **Effect of changing this setting:** Typically, this screen doesn’t have direct switches or input fields for the merchant. Its main purpose is to confirm the module’s status and guide you to the next step.
- **Recommended value:** No direct values to set here. Just ensure the module is enabled.
- **Merchant scenario / example:** After installing, you’ll land here. You might see a message confirming installation and a button or link to “Manage Minimal Order Values” or similar, which will take you to the dedicated AdminMobcController screen.

### 2.2 Dedicated Admin Screen: Minimal Order Value by Category Management (Back Office > Modules > Minimal order value by category)

This is the core management interface where you define and control all your category-specific minimum order values. You’ll typically find a new menu item under “Modules” or “Catalog” (depending on your PrestaShop version and module’s hook) named “Minimal order value by category” or similar.

**Screen Name & Menu Location:**
You will find this screen by navigating to **Modules > Minimal order value by category** in your PrestaShop Back Office menu.

**Available Actions & Settings:**
This screen presents a list (grid) of all your currently defined minimum order value rules. For each rule, you will typically see:

- **Category Name:** The name of the PrestaShop category to which the rule applies.
- **Minimum Value:** The required minimum order amount for products within that category.
- **Currency:** The currency in which the minimum value is set (usually your shop’s default currency, e.g., USD, EUR).
- **Actions:** Buttons to “Edit” or “Delete” an existing rule.

You will also find a button, usually at the top right, to **“Add New Rule”** or **“Add New Minimal Order Value”**. Clicking this will open a form where you can:

1. **Select Category:**

   - **What this setting does:** Allows you to choose which existing PrestaShop category this minimum order value rule will apply to.
   - **Effect of changing this setting:** Selecting a category links the rule to all products within that category (and its subcategories, depending on module logic).
   - **Recommended value:** Select the specific category you wish to apply the minimum order value to.
   - **Merchant scenario / example:** You want to set a minimum for your “Wholesale” category. You’d select “Wholesale” from the dropdown.
2. **Minimum Order Value:**

   - **What this setting does:** Defines the monetary amount that customers must spend on products *within the selected category* before they can proceed with their order.
   - **Effect of changing this setting:**
     - *When set to a value (e.g., 50.00):* Customers must have at least 50.00 units of your default currency worth of products from the selected category in their cart. If not, they will be blocked at checkout with a message.
     - *When left empty or set to 0:* This rule would effectively be disabled for the category, allowing any value. However, it’s best to delete the rule if you don’t need it.
   - **Recommended value:** A positive numerical value reflecting your desired minimum (e.g., `25.00`, `100.00`).
   - **Merchant scenario / example:** For your “Wholesale” category, you set this to `100.00`. A customer with $90 of wholesale products cannot check out until they add another $10.
3. **Save Button:**

   - **What this does:** Applies the changes or creates the new rule.
   - **Effect:** The new rule will be active immediately, and the system will start enforcing the minimum order value for the selected category.

**Recommended workflow for daily store management:**

1. **Review existing rules:** Periodically check your list of rules to ensure they are still relevant to your business strategy.
2. **Add new rules:** If you introduce new product categories that require specific minimums (e.g., a new B2B line), add a rule for them.
3. **Edit existing rules:** Adjust minimum values based on product pricing changes, market conditions, or promotional strategies.
4. **Delete obsolete rules:** Remove rules for categories that no longer require a minimum or have been discontinued.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | (No direct settings) | N/A | Entry point to the module; confirms installation and directs to management screen. |
| Minimal Order Value by Category Management | Add New Rule / Edit Rule > Select Category | N/A | Links a minimum order value to a specific PrestaShop product category. |
| Minimal Order Value by Category Management | Add New Rule / Edit Rule > Minimum Order Value | Your desired minimum (e.g., `50.00`) | Sets the required monetary amount for products within the chosen category. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve set a minimum value, but it’s not working. Customers can still check out with less.**
A:

- **Check Module Status:** Ensure the module is enabled in **Modules > Module Manager**.
- **Verify Rule Configuration:** Go to **Modules > Minimal order value by category** and confirm that the rule for the specific category is active, has a value greater than zero, and is correctly assigned to the intended category.
- **Clear Cache:** Sometimes PrestaShop’s cache can prevent changes from appearing immediately. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions).
- **Product Category Assignment:** Double-check that the products in question are indeed assigned to the category for which you set the minimum.

**Q2: The message displayed to customers is not clear or doesn’t match my store’s language.**
A:

- **Module Translations:** The module should support PrestaShop’s translation system. Go to **International > Translations**, select “Installed modules translations”, choose your theme, and then select “Minimal order value by category”. You can then customize the warning messages to be more specific or translate them into other languages.
- **Custom Theme Styling:** If the message appears but looks out of place, your theme’s CSS might be overriding the module’s styles. A webmaster can help adjust the `mobc.css` file or add custom CSS to your theme to ensure proper display.

**Q3: Can I set different minimums for different customer groups (e.g., retail vs. wholesale)?**
A: The current version of the “Minimal order value by category” module focuses on category-wide minimums, not customer group-specific ones. If you need this advanced functionality, you might need to use separate categories for different customer groups (e.g., “Wholesale Products” vs. “Retail Products”) and apply rules to those distinct categories.

**Q4: What happens if a product is in multiple categories, and only one has a minimum?**
A: The module calculates the total value of products within *each* category that has a minimum rule. If a product is in Category A (no minimum) and Category B (minimum $50), its value will contribute to the Category B total if added to the cart. The customer must meet the minimum for Category B based on the sum of all products in their cart that belong to Category B.

**Q5: I deleted a category, but the rule for it is still showing in the module’s configuration.**
A: If you delete a category directly from PrestaShop’s Catalog menu, the module’s rule associated with that category might become orphaned. You should manually go to **Modules > Minimal order value by category** and delete the corresponding rule from the list to keep your configuration clean.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Minimal order value by category” module (`mobc`) follows a standard PrestaShop MVC pattern. It primarily extends `Module` for its core functionality and `AdminController` for its back-office management interface. Front-office interactions are handled via `ModuleFrontController` for AJAX requests and template rendering. The module does not use custom `ObjectModel` classes but relies on PrestaShop’s core `Category` and `Product` entities for data retrieval. Configuration is stored in `ps_configuration` and a custom database table for the category-value mappings.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `controllers/front/ajax.php`
    - **Class Name:** `MobcAjaxModuleFrontController` (extends `ModuleFrontController`)
    - **Responsibility:** Handles AJAX requests from the front-office, primarily to check cart contents against defined minimum order values by category. It likely receives cart data and returns a JSON response indicating whether the minimums are met and, if not, which categories are deficient and by how much. This is crucial for real-time validation on the cart page without full page reloads.
  - `controllers/front/index.php`
    - **Class Name:** `MobcIndexModuleFrontController` (extends `ModuleFrontController`)
    - **Responsibility:** This controller might serve as a fallback or a simple entry point, but given the module’s functionality, its primary role is likely minimal, possibly redirecting or serving a basic page if directly accessed. The core front-office logic is expected in `ajax.php`.
- **Back-Office Admin Controllers**:

  - `controllers/admin/AdminMobc.php`
    - **Class Name:** `AdminMobcController` (extends `ModuleAdminController`)
    - **Tab Name:** Minimal order value by category (or similar, typically under “Modules” or “Catalog”).
    - **Managed Entity:** Manages the custom `mobc` entity, which represents the category-minimum value mappings.
    - **Responsibility:** Provides the CRUD (Create, Read, Update, Delete) interface for managing minimal order value rules. It handles listing existing rules in a grid, displaying forms for adding/editing rules (selecting categories, inputting minimum values), and processing form submissions. It interacts with the module’s database table for `mobc` entries.
  - `controllers/admin/index.php`
    - **Class Name:** `AdminMobcIndexController` (extends `ModuleAdminController`)
    - **Responsibility:** Similar to the front-office `index.php`, this might be a placeholder or a simple redirector. The main admin logic resides in `AdminMobc.php`.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes in the `classes/` directory. This suggests that the module’s data handling for the category-value mappings is either done directly within the `AdminMobcController` or `index.php` (main module file) using `Db::getInstance()` or by extending a generic `ObjectModel` within the main module file itself without creating a dedicated class file.

Given the `AdminMobcController` manages a “mobc” entity, it’s highly probable that the `AdminMobcController` defines its `$this->object` and `$this->fields_list` directly, or there’s an implicit `ObjectModel` definition within the main `mobc.php` file that the controller leverages.

### 4.4 JavaScript Assets (`views/js/`)

- `mobc/views/js/mobc.js`
  - **Scope:** Front-office.
  - **Responsibility:** This script is crucial for the real-time validation of the cart. It likely:
    - Binds event listeners to cart quantity changes, product removals, or page loads on the shopping cart page.
    - Triggers AJAX calls to `controllers/front/ajax.php` to send current cart data.
    - Receives the JSON response from the AJAX controller.
    - Dynamically updates the DOM on the cart page to display warning messages if minimums are not met.
    - Disables/enables the checkout button based on the validation result.
    - May include logic for displaying pop-up messages or highlighting problematic categories.

### 4.5 CSS Stylesheets (`views/css/`)

- `mobc/views/css/mobc.css`
  - **Scope:** Front-office customer styling.
  - **Main UI components and containers it styles:** This stylesheet is responsible for the visual presentation of the warning messages displayed on the shopping cart page. It will define styles for:
    - Containers holding the warning messages (e.g., `div.mobc-warning-message`).
    - Text elements within the warnings (e.g., `span.mobc-category-name`, `span.mobc-remaining-amount`).
    - Potentially styling for the disabled checkout button or other visual cues.
  - **Key CSS class selectors developers can override in their theme:** Developers can inspect the generated HTML on the cart page to identify the specific class names (e.g., `.mobc-alert`, `.mobc-error-list`, `.mobc-checkout-blocked`) and override them in their theme’s `custom.css` or `theme.css` to match the store’s branding.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `mobc/views/templates/front/displayShoppingCart.tpl`
    - **Hook:** This template is likely rendered in a hook on the shopping cart page, such as `displayShoppingCartFooter` or `displayShoppingCartExtraContent`.
    - **Visual Block Output:** It outputs the HTML structure for the warning messages that inform customers about unmet minimum order values for categories. This template will contain placeholders for category names, required amounts, and the remaining amount needed, which are populated by the JavaScript and AJAX controller.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - `ps_mobc_category_value` (or similar, based on `AdminMobcController`’s entity): This custom table stores the mapping between category IDs and their respective minimum order values.
    - `id_mobc_category_value` (Primary Key, INT)
    - `id_category` (INT, Foreign Key to `ps_category.id_category`)
    - `min_value` (DECIMAL, stores the minimum monetary amount)
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
  - `ps_configuration`: Standard PrestaShop configuration table. The module might store its general settings (if any, though none explicitly detected) here, prefixed with `MOBC_`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | To include `mobc.css` and `mobc.js` for front-office functionality. |
| `displayShoppingCart` | On the shopping cart page, typically before or after the cart summary. | To render `displayShoppingCart.tpl` for displaying warning messages. |
| `actionCartSave` | After a cart is saved (e.g., product added/removed, quantity changed). | To trigger the module’s logic to re-evaluate category minimums and potentially update the cart status or session variables. |
| `actionFrontControllerSetMedia` | Before a front controller renders its output, allowing modules to add JS/CSS. | To register module-specific JavaScript and CSS files for the front-office. |
| `actionAdminControllerSetMedia` | Before an admin controller renders its output. | To register module-specific JavaScript and CSS files for the back-office (e.g., for the `AdminMobcController`). |
| `displayAdminProductsExtra` (or similar) | On the product edit page in the back office. | Potentially to display information about category minimums related to the current product, though not explicitly confirmed by dossier. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Minimal order value by category” module, please refer to your customer account at MyPresta.eu. Our support team is available to assist you with any issues or questions regarding the module’s functionality and configuration.
