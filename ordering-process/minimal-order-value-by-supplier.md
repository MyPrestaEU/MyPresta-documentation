---
title: "Minimal order value by supplier - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Minimal order value by supplier PrestaShop module by MyPresta.eu."
sidebar:
  label: "Minimal order value by supplier - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Minimal order value by supplier Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/minimal-order-value-by-supplier.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/minimal-order-value-by-supplier/)
>
> ---


# Minimal order value by supplier

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” will take you to the main module configuration page. This is where you can enable or disable the module and access the core management screen for your supplier minimums.

- **What this setting does:** This screen serves as the central hub for the module. It allows you to enable or disable the entire module functionality and provides a direct link to manage your minimum order values for suppliers.
- **Effect of changing this setting:**
  - *When enabled:* The module will actively check customer carts against your defined minimum supplier order values and block checkout if requirements are not met.
  - *When disabled:* The module will cease to function. No minimum order value checks will be performed, and customers will be able to checkout regardless of supplier order totals.
- **Recommended value:** “YES” (Enabled) if you intend to use the module’s features.
- **Merchant scenario / example:** If you’re setting up the module for the first time, you’ll enable it here. If you need to temporarily suspend the rules (e.g., during a store-wide promotion where you want to allow all orders), you can disable it here.

On this screen, you will also find a button or link to **“Manage Minimal Order Values by Supplier”**. Clicking this will take you to the dedicated administration screen where you define the actual rules.

### 2.2 Dedicated Admin Screens & Controller Views

#### AdminMobsController (Back Office > Modules > Minimal order value by supplier > Manage Minimal Order Values)

This is the primary screen where you define and manage the minimum order values for each of your suppliers.

- **Screen Name & Menu Location:** You access this screen by navigating to **Modules > Module Manager**, finding “Minimal order value by supplier”, clicking “Configure”, and then clicking the “Manage Minimal Order Values by Supplier” button/link.
- **Available Actions & Settings:**
  - **Listing Table:** This screen displays a table of all currently configured minimum order values. Each row typically shows:
    - **Supplier Name:** The name of the supplier for whom the rule applies.
    - **Minimum Order Value:** The monetary amount that products from this supplier must reach in the cart.
    - **Actions:** Usually “Edit” and “Delete” buttons to modify or remove an existing rule.
  - **Add New Rule Button:** A button (e.g., “Add New Minimal Order Value”) to create a new rule.
  - **Add/Edit Form:** When adding a new rule or editing an existing one, you will typically see a form with the following fields:
    - **Supplier Selection:** A dropdown or search field to select one of your existing suppliers.
    - **Minimum Value:** An input field where you enter the numerical minimum order amount required for products from the selected supplier. This value will be in your shop’s default currency (e.g., EUR, USD).
    - **Save Button:** To apply your changes.
- **Effect of changes:**
  - *Adding a rule:* Once saved, the new minimum order value for the selected supplier becomes active immediately. Customers will be required to meet this value for products from that supplier.
  - *Editing a rule:* Modifying the minimum value or changing the supplier for an existing rule updates the active requirement.
  - *Deleting a rule:* Removes the minimum order value requirement for that specific supplier. Customers will no longer be restricted by a minimum purchase from that supplier.
- **Recommended workflow for daily store management:**
  1. **Identify Suppliers:** Determine which suppliers require minimum order values based on your business needs (e.g., high shipping costs, dropshipping agreements).
  2. **Add Rules:** For each identified supplier, click “Add New Minimal Order Value”, select the supplier, enter the minimum amount, and save.
  3. **Monitor & Adjust:** Regularly review your supplier agreements and sales data. If a supplier changes their terms, or if you notice a trend of unprofitable small orders, come back to this screen to adjust or add new rules.
  4. **Test:** After adding or modifying rules, always test the functionality by adding products from the affected suppliers to your cart in the front office and attempting to checkout.

#### index.php (mobs/controllers/admin/index.php)

This file typically serves as a placeholder or a redirector within the admin controllers directory and does not present a direct configuration screen to the merchant. Its primary function is usually to ensure that direct access to the directory is handled gracefully, often redirecting to the main module configuration or an error page. Merchants will not directly interact with this file.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration Page** | Enable/Disable Module | Enabled | Controls whether the module’s functionality (minimum order value checks) is active or inactive. |
| **AdminMobsController** | Add New Rule (Supplier) | N/A | Selects a supplier to apply a minimum order value rule to. |
| **AdminMobsController** | Add New Rule (Minimum Value) | N/A | Sets the monetary threshold for products from the selected supplier. |
| **AdminMobsController** | Edit Rule (Supplier) | N/A | Modifies the supplier associated with an existing rule. |
| **AdminMobsController** | Edit Rule (Minimum Value) | N/A | Changes the monetary threshold for an existing supplier rule. |
| **AdminMobsController** | Delete Rule | N/A | Removes a minimum order value requirement for a specific supplier. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve set a minimum value, but it’s not working in the cart. What should I check?**
A1:

1. **Is the module enabled?** Go to **Modules > Module Manager**, find “Minimal order value by supplier”, and ensure it’s enabled.
2. **Is the rule correctly configured?** Go to the “Manage Minimal Order Values by Supplier” screen and verify that the supplier is correctly selected and the minimum value is entered as a number (without currency symbols).
3. **Are the products correctly assigned to the supplier?** Double-check the products in the customer’s cart to ensure they are indeed associated with the supplier for whom you’ve set the rule.
4. **Clear Cache:** Sometimes, PrestaShop’s cache can prevent changes from appearing immediately. Go to **Advanced Parameters > Performance** and click “Clear cache”.

**Q2: The notification message is showing, but it’s not in my store’s language.**
A2: The module’s front-office messages are translatable.

1. Go to **International > Translations**.
2. Select “Installed modules translations”, choose your theme, select your language, and click “Modify”.
3. Find the “mobs” module (Minimal order value by supplier) and translate the relevant strings. Save your changes.

**Q3: The module is blocking checkout, but I want to allow an exception for a specific customer or order.**
A3: The module enforces rules globally. To make an exception, you would need to temporarily disable the specific supplier’s rule in the module’s configuration (**Modules > Minimal order value by supplier > Manage Minimal Order Values**) or disable the entire module if multiple rules are active. Remember to re-enable it afterward. There is no built-in “override” function per customer or order.

**Q4: The module is active, but the styling of the notification message doesn’t match my theme.**
A4: The module comes with basic styling. If it clashes with your custom theme, your webmaster or developer can override the module’s CSS. The module’s CSS file is `mobs/views/css/mobs.css`. They can add custom styles to your theme’s `custom.css` or `theme.css` file, targeting the module’s notification elements to match your brand.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Minimal order value by supplier” module (`mobs`) follows a standard PrestaShop module architecture, leveraging MVC principles. It primarily consists of a main module class, a dedicated Admin Controller for managing rules, and a Front Controller for AJAX interactions and displaying notifications. It does not use custom `ObjectModel` classes but stores configuration directly in `ps_configuration` and manages supplier-specific minimums via the `AdminMobsController` which likely interacts with a custom table or extends a generic `AdminController` to manage data. Front-office interaction is handled via a dedicated template for the shopping cart and an AJAX controller for dynamic checks.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `controllers/front/ajax.php`
    - **Class name & parent class**: `MobsAjaxModuleFrontController` extends `ModuleFrontController`.
    - **Responsibility**: This controller is responsible for handling AJAX requests from the front-office, typically initiated from the shopping cart page. It likely performs real-time checks on the cart content against the configured minimum supplier order values. It returns JSON responses indicating whether the minimums are met and providing relevant messages if not. This allows for dynamic updates to the cart display without full page reloads.
  - `controllers/front/index.php`
    - **Class name & parent class**: `MobsIndexModuleFrontController` extends `ModuleFrontController`.
    - **Responsibility**: This controller might serve as a default entry point for the front-office part of the module, though its primary function is often to redirect or serve a basic page if the module has no dedicated front-office page. Given the module’s functionality, it’s more likely that the `ajax.php` controller handles the core front-office logic, and `index.php` is a fallback or minimal page.
- **Back-Office Admin Controllers**:

  - `controllers/admin/AdminMobs.php`
    - **Class name & parent class**: `AdminMobsController` extends `ModuleAdminController`.
    - **Tab name and managed entity**: This controller manages the “Minimal Order Values by Supplier” rules. It provides the interface for listing, adding, editing, and deleting these rules. It likely interacts with a custom database table (e.g., `ps_mobs_rules`) to store the supplier ID and the associated minimum value. The grid view and form fields are rendered using PrestaShop’s `HelperList` and `HelperForm` classes.
  - `controllers/admin/index.php`
    - **Class name & parent class**: No specific class, typically a simple PHP file.
    - **Responsibility**: This file is usually a placeholder or a security measure to prevent direct directory listing. It often contains a simple `header('Location: ../../../index.php?controller=AdminHome');` or similar redirect to the PrestaShop back office dashboard, ensuring that accessing `yourshop.com/modules/mobs/controllers/admin/` directly doesn’t expose sensitive information or cause errors. It does not present a user-facing screen.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes in the `classes/` directory. This suggests that the module either:

1. Stores its configuration directly in `ps_configuration` for simple settings.
2. Manages its data (supplier minimums) directly within the `AdminMobsController` using standard PrestaShop database query methods, potentially interacting with a custom table created during installation, without a dedicated `ObjectModel`.

If a custom table is used, its structure would be defined in the `install()` method of the main module file (`mobs/index.php`).

### 4.4 JavaScript Assets (`views/js/`)

- `views/js/mobs.js`
  - **Scope**: Front-office.
  - **Description**: This JavaScript file is responsible for client-side interactions related to the minimum order value checks. It likely:
    - Binds event listeners to cart quantity changes, product removals, or the “Proceed to checkout” button.
    - Sends AJAX requests to `controllers/front/ajax.php` to validate the cart against supplier minimums.
    - Receives JSON responses from the AJAX controller.
    - Dynamically updates the shopping cart display, showing notification messages if minimums are not met.
    - Disables or enables the “Proceed to checkout” button based on the validation results.
    - May include logic for displaying modal popups or inline error messages.

### 4.5 CSS Stylesheets (`views/css/`)

- `views/css/mobs.css`
  - **Scope**: Front-office customer styling.
  - **Description**: This stylesheet provides the visual presentation for the module’s front-office elements, primarily the notification messages displayed in the shopping cart.
  - **Main UI components and containers it styles**: It will likely target specific CSS classes added by the module to the shopping cart template, such as `div.mobs-notification`, `p.mobs-error-message`, or similar elements that display the warnings about unmet minimum order values.
  - **Key CSS class selectors developers can override**: Developers can inspect the HTML output of the module’s notifications to identify the exact class names (e.g., `.mobs-alert`, `.mobs-supplier-name`, `.mobs-required-value`) and override them in their theme’s `custom.css` to match the store’s branding.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - No specific hook templates are listed in the inventory, suggesting that the module’s front-office output is primarily injected into an existing template like `displayShoppingCart.tpl` or via a direct template render within a controller.
- **Admin templates (`views/templates/admin/`)**:

  - The module dossier does not list specific admin templates. The `AdminMobsController` likely uses PrestaShop’s default `HelperList` and `HelperForm` templates for its grid and form views, which are part of the core PrestaShop framework.
- **Front-office templates (`views/templates/front/`)**:

  - `views/templates/front/displayShoppingCart.tpl`
    - **Description**: This template is specifically designed to be included or rendered within the shopping cart page. It contains the HTML structure for displaying the minimum order value notifications to the customer. It will likely iterate through any unmet supplier minimums and display a message for each, possibly including the supplier name and the remaining amount needed. This template is dynamically updated by the `mobs.js` script based on AJAX responses.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module dossier does not explicitly list custom classes or SQL files, but for the `AdminMobsController` to manage “Minimal Order Values by Supplier”, it must store this data. It is highly probable that the module creates a custom table during its `install()` method in `mobs/index.php`.
  - **Likely Table Name**: `ps_mobs_rules` (or similar, e.g., `ps_minimal_order_by_supplier`).
  - **Likely Table Structure**:
    - `id_mobs_rule` (PRIMARY KEY, INT)
    - `id_supplier` (INT, FOREIGN KEY to `ps_supplier.id_supplier`)
    - `min_value` (DECIMAL(20,6))
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
  - **Configuration Records**: The module’s main enable/disable status is likely stored in `ps_configuration` with a key like `MOBS_ENABLED`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | To include CSS (`mobs.css`) and JavaScript (`mobs.js`) files for front-office functionality. |
| `displayShoppingCartFooter` | At the bottom of the shopping cart page. | To display the `displayShoppingCart.tpl` template, which contains the notification messages for unmet minimum order values. |
| `actionCartSave` | After a cart is saved (e.g., quantity change, product add/remove). | To trigger the logic that checks for minimum order values and potentially updates cart status or session variables. |
| `actionValidateOrder` | Before an order is officially validated. | To perform a final check on minimum order values and prevent order validation if requirements are not met. |
| `displayBeforeCarrier` | Before the carrier selection step in checkout. | To display warnings or block progression if minimums are not met at an earlier stage of checkout. |
| `displayPaymentTop` | At the top of the payment selection page. | To display warnings or block progression if minimums are not met before payment. |

*Note: The module dossier mentions “Header, Columns, Product, or Footer” as front-office hooks. While `displayHeader` is certain, the module likely uses `displayShoppingCartFooter` or a similar cart-specific hook for its main output, and `actionCartSave`/`actionValidateOrder` for its core logic. `displayRightColumn` or `displayLeftColumn` could be used for optional static blocks, but are less likely for the core functionality.*

## 5. Official Support & Updates

For official updates, technical support, and to access the latest versions of the “Minimal order value by supplier” module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and configuration.
