---
title: "Maximum purchase value by categories - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Maximum purchase value by categories PrestaShop module by MyPresta.eu."
sidebar:
  label: "Maximum purchase value by categories - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Maximum purchase value by categories Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/maximum-purchase-value-by-categories.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/maximum-purchase-value-by-categories/)
>
> ---


# Maximum purchase value by categories

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special hosting requirements beyond a standard PrestaShop setup.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the module, where you manage the overall settings and access the rules for maximum purchase values.

- **What this setting does:** This page provides general information about the module and often includes a link or button to manage the actual rules.
- **Effect of changing this setting:** While this specific screen might not have direct “settings” to change, it serves as the entry point to the module’s functionality.
- **Recommended value:** N/A (This is an informational screen).
- **Merchant scenario / example:** After installation, you’ll land here. You’ll then click a button or link (e.g., “Manage Rules” or “Configure Maximum Values”) to proceed to the dedicated screen where you define your category limits.

### 2.2 Dedicated Admin Screen: Maximum Purchase Value Rules (Back Office > Modules > Maximum purchase value by categories > Configure)

This is the core of the module where you define and manage your maximum purchase value rules for different categories. You will typically find this screen by clicking “Configure” after installing the module, or by navigating to **Modules > Module Manager**, finding the module, and clicking “Configure”.

**Screen Name & Menu Location:**
You will access this screen by navigating to **Modules > Module Manager**, searching for “Maximum purchase value by categories”, and clicking the “Configure” button. This will take you to a dedicated administration interface for managing your rules.

**Available Actions & Settings:**
On this screen, you will see a list (grid) of all your currently defined maximum purchase value rules. For each rule, you will typically see:

- **Category Name:** The name of the product category to which the rule applies.
- **Maximum Value:** The highest total value (in your default currency) allowed for products from this category in a single order.
- **Actions:** Buttons to “Edit” an existing rule or “Delete” it.

You will also find:

- **“Add New Rule” Button:** A prominent button to create a new maximum purchase value rule.

**When adding or editing a rule, you will typically encounter the following fields:**

1. **Select Category:**

   - **What this setting does:** Allows you to choose which specific product category this maximum purchase value rule will apply to. You will usually see a dropdown or a category tree selector.
   - **Effect of changing this setting:**
     - *When a category is selected:* The rule will apply to all products within that category (and often its subcategories, depending on the module’s logic).
     - *When no category is selected (or if you change it):* The rule will either be invalid or apply to a different category.
   - **Recommended value:** Select the specific category you wish to limit.
   - **Merchant scenario / example:** You want to limit purchases of “Electronics” products. You would select “Electronics” from the list.
2. **Maximum Purchase Value:**

   - **What this setting does:** This is the numerical value (in your shop’s default currency) that represents the highest allowed total for products from the selected category in a customer’s cart.
   - **Effect of changing this setting:**
     - *When set to a specific value (e.g., 500):* Customers will not be able to have more than 500 units of your default currency’s worth of products from the selected category in their cart.
     - *When set to 0 or left empty (if allowed):* This might disable the rule for the category or be considered an invalid entry.
   - **Recommended value:** A positive numerical value representing your desired limit (e.g., `250.00`).
   - **Merchant scenario / example:** You want to limit “Limited Edition Art Prints” to a maximum of $250 per order. You would enter `250` here. The module will automatically calculate equivalent values for other currencies if your store supports them.

**Effect of changes:**

- **Adding a new rule:** Immediately enforces the maximum purchase value for the selected category across your store. Customers will be prevented from exceeding this limit.
- **Editing a rule:** Updates the maximum value for an existing category. The new limit takes effect immediately.
- **Deleting a rule:** Removes the restriction for that category. Customers will no longer be limited in their purchases from that category.

**Recommended workflow for daily store management:**

1. Periodically review your product categories and identify any that might benefit from a purchase value limit (e.g., new high-demand products, items with limited stock, or products with specific distribution agreements).
2. Navigate to the “Maximum purchase value by categories” configuration screen.
3. Use the “Add New Rule” button to create new limits.
4. Monitor customer feedback or order patterns to adjust existing limits as needed using the “Edit” action.
5. If a product line or category no longer requires a limit, use the “Delete” action to remove the rule.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| AdminMaobcController (Rule Management) | **Select Category** | Specific Category Name | Defines which product category the maximum value applies to. |
| AdminMaobcController (Rule Management) | **Maximum Purchase Value** | Numerical value (e.g., `250.00`) | Sets the highest total value allowed for products from the selected category in a single order (in default currency). Automatically converts for other currencies. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve set a limit, but customers can still exceed it. What’s wrong?**
A1:

- **Check Category Assignment:** Ensure the products in question are correctly assigned to the category for which you set the limit.
- **Module Enabled:** Verify that the “Maximum purchase value by categories” module is enabled in **Modules > Module Manager**.
- **Rule is Active:** Go to the module’s configuration and confirm that the rule for the specific category is present and has a valid maximum value.
- **Clear Cache:** Sometimes PrestaShop’s cache can prevent changes from taking effect immediately. Go to **Advanced Parameters > Performance** and click “Clear cache”.

**Q2: The module is showing the wrong currency or not converting correctly.**
A2: The module automatically uses your shop’s default currency for the value you enter and then converts it for other currencies.

- **Default Currency:** Ensure your default currency is correctly set in **International > Currencies**. The value you enter in the module’s configuration should always be in this default currency.
- **Exchange Rates:** Check your exchange rates in **International > Currencies** to ensure they are up-to-date and accurate for the currencies you support.

**Q3: Can I set different limits for different customer groups?**
A3: This specific module sets a global limit per category, applying to all customers. If you require different limits for specific customer groups (e.g., wholesale vs. retail), you would need a more advanced module or custom development.

**Q4: How do I translate the error messages shown to customers?**
A4: The module’s front-office messages are usually translatable through PrestaShop’s translation system:

1. Go to **International > Translations**.
2. Select “Installed modules translations”.
3. Choose your theme, the language, and then select “Maximum purchase value by categories” from the module list.
4. You can then find and edit the text strings displayed by the module to your customers.

**Q5: The module seems to be conflicting with another module in my cart/checkout.**
A5: Module conflicts can sometimes occur.

- **Isolate the Issue:** Temporarily disable other modules that interact with the cart or product page one by one to see if the conflict resolves.
- **Theme Compatibility:** If you are using a custom theme, it might have specific overrides that interfere. Check if the issue persists with the default PrestaShop theme.
- **Contact Support:** If you cannot identify the conflict, gather details (which modules, what exact error) and contact MyPresta.eu support for assistance.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Maximum purchase value by categories” module (`maobc`) follows a standard PrestaShop MVC (Model-View-Controller) pattern. It primarily uses an Admin Controller to manage the configuration and rules, and a Front Controller to intercept AJAX requests related to cart updates. The core logic resides within the main module class, which hooks into various PrestaShop events to enforce the category-based value limits. It stores its configuration in the `ps_configuration` table and manages its rules via a custom table and an Admin Controller.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `controllers/front/ajax.php`
    - **Class Name**: `MaobcAjaxModuleFrontController` (extends `ModuleFrontController`)
    - **Responsibility**: This controller is responsible for handling AJAX requests from the front-office, primarily those related to adding products to the cart or updating cart quantities. It intercepts these requests to perform real-time validation against the defined maximum purchase value rules before PrestaShop processes the cart update. It returns JSON responses indicating success or failure with appropriate messages.
  - `controllers/front/index.php`
    - **Class Name**: `MaobcIndexModuleFrontController` (extends `ModuleFrontController`)
    - **Responsibility**: This controller might serve as a fallback or a simple entry point, but given the module’s functionality, `ajax.php` is the primary front-office interaction point. It might render a simple page or redirect if accessed directly.
- **Back-Office Admin Controllers**:

  - `controllers/admin/AdminMaobc.php`
    - **Class Name**: `AdminMaobcController` (extends `ModuleAdminController`)
    - **Tab Name**: “Maximum purchase value by categories” (or similar, accessible via the module’s “Configure” button).
    - **Managed Entity**: This controller manages the custom `maobc` entity, which represents the individual rules for maximum purchase values per category. It handles the CRUD (Create, Read, Update, Delete) operations for these rules.
    - **Responsibility**: Displays a list (grid) of all configured rules, allows administrators to add new rules, edit existing ones (selecting a category and setting a maximum value), and delete rules. It interacts with the module’s internal data storage (likely a custom database table or `ps_configuration` entries).
  - `controllers/admin/index.php`
    - **Class Name**: `AdminMaobcIndexController` (extends `ModuleAdminController`)
    - **Responsibility**: Similar to the front-office `index.php`, this might be a simple entry point or a fallback. The `AdminMaobcController` is the primary controller for managing the module’s rules.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes in the `classes/` directory. This suggests that the module’s core logic and data handling are likely integrated directly into the main module file (`maobc/index.php`) or managed through standard PrestaShop `Configuration` class for settings and potentially a custom database table managed directly by the `AdminMaobcController` without a dedicated `ObjectModel`.

### 4.4 JavaScript Assets (`views/js/`)

- `views/js/maobc.js`
  - **Scope**: Front-office.
  - **Details**: This script is likely responsible for client-side interactions related to cart updates. It might:
    - Override or extend default PrestaShop AJAX cart functions (e.g., `add to cart` button clicks).
    - Intercept AJAX responses from `controllers/front/ajax.php` to display custom error messages to the user if a maximum value is exceeded.
    - Potentially update the UI (e.g., disable buttons, show alerts) based on validation results.
    - It will likely use `jQuery` or `prestashop.on` events to bind its logic.

### 4.5 CSS Stylesheets (`views/css/`)

- `views/css/maobc.css`
  - **Scope**: Front-office.
  - **Details**: This stylesheet provides custom styling for the module’s front-office elements, primarily the notification messages displayed to customers when a maximum purchase value is exceeded.
  - **Key CSS Class Selectors**: Developers should inspect this file for classes like `.maobc-error-message`, `.maobc-alert`, or similar, which can be overridden in their theme’s `custom.css` or `theme.css` to match the store’s branding.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - The module dossier does not explicitly list templates in `views/templates/hook/`. This suggests that any messages or dynamic content might be injected directly via JavaScript or rendered by the main module file using `display()` methods.
- **Admin templates (`views/templates/admin/`)**:

  - The module dossier does not explicitly list templates in `views/templates/admin/`. The `AdminMaobcController` likely uses standard PrestaShop helper forms (`HelperList`, `HelperForm`) for its grid and configuration forms, which generate their HTML dynamically.
- **Front-office templates (`views/templates/front/`)**:

  - `views/templates/front/displayShoppingCart.tpl`
    - **Purpose**: This template is likely used to display the custom error message on the shopping cart page if the maximum purchase value for a category is exceeded. It would contain the HTML structure for the alert or notification that informs the customer about the limit. It’s probably hooked into a `displayShoppingCartFooter` or similar hook.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module likely creates a custom database table (e.g., `ps_maobc_rules`) to store the category ID and the associated maximum purchase value for each rule.
  - Configuration values (e.g., module enabled status, general settings) are stored in `ps_configuration` table, typically with keys prefixed `MAOBC_`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Renders in the `<head>` section of all front-office pages. | Potentially used to load `maobc.js` and `maobc.css` assets, or to inject JavaScript variables. |
| `displayRightColumn` / `displayLeftColumn` | Renders content in the side columns. | Less likely for this module, but could be used to display a static message about purchase limits. |
| `displayProductAdditionalInfo` / `displayProductButtons` | Renders on the product page. | Could be used to display a warning message on the product page if the item belongs to a restricted category. |
| `displayShoppingCartFooter` / `displayShoppingCart` | Renders on the shopping cart page. | Used to display the `displayShoppingCart.tpl` template with error messages if limits are exceeded. |
| `actionCartSave` | Executed after a cart is saved (e.g., product added/removed, quantity changed). | Crucial for server-side validation of cart contents against category limits. This is where the core logic prevents invalid cart states. |
| `actionAjaxDieCartController` | Executed before an AJAX response from the CartController. | Allows the module to intercept and modify AJAX responses, injecting custom error messages if limits are exceeded during AJAX cart updates. |
| `actionFrontControllerSetMedia` | Executed before a front controller renders its output. | Used to register front-office CSS and JavaScript files. |

## 5. Official Support & Updates

For official updates, technical support, and to download the latest versions of the “Maximum purchase value by categories” module, please log in to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality or integration.
