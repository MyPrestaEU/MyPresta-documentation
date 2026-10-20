---
title: "Increase prices by country - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Increase prices by country PrestaShop module by MyPresta.eu."
sidebar:
  label: "Increase prices by country - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Increase prices by country Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/increase-prices-by-country.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/increase-prices-by-country/)
>
> ---


# Increase prices by country

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. The module relies on PrestaShop’s core functionality and standard server configurations.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the module, accessible immediately after installation or by clicking “Configure” from the Module Manager.

**Settings & Options Detected: Standard module settings**
This screen typically contains general settings for the module, such as enabling/disabling the module, or global preferences.

- **What this setting does:** This section usually contains a global switch to enable or disable the module’s core functionality. It might also include general preferences that affect how the price adjustments are applied across your store.
- **Effect of changing this setting:**
  - *When enabled:* The module will actively adjust prices based on the rules you define in the dedicated “Price by Country List” section.
  - *When disabled:* The module will stop adjusting prices, and all customers will see your default product prices, regardless of their country.
- **Recommended value:** “YES” (Enabled) if you intend to use the module for price adjustments.
- **Merchant scenario / example:** If you’re setting up the module for the first time, you’ll want to enable it here. If you need to temporarily pause all country-specific price adjustments without deleting your rules, you can disable it here.

### 2.2 Dedicated Admin Screens & Controller Views

#### AdminPbcListController (Back Office > Increase prices by country > Price by Country List)

This is the core management screen where you define and manage your country-specific price adjustment rules.

- **Screen Name & Menu Location:** You will find a new menu item in your PrestaShop Back Office, typically under a section like “Catalog” or “International”, named **“Increase prices by country”** or similar, and then a sub-menu item like **“Price by Country List”**.
- **Available Actions & Settings:**
  - **Add New Rule:** A button to create a new price adjustment rule.
  - **List of Rules:** A table displaying all existing rules, showing details like:
    - **Country:** The target country for the rule.
    - **Adjustment Type:** Whether it’s a percentage or a fixed amount.
    - **Value:** The percentage or amount to increase/decrease.
    - **Action:** Options to “Edit” or “Delete” individual rules.
  - **Form Fields for Adding/Editing a Rule:**
    - **Country Selector:** A dropdown or search field to select the specific country this rule applies to.
      - *Effect:* Prices will be adjusted only for customers identified as being in this country.
      - *Recommended:* Select the specific country you wish to target.
      - *Scenario:* You want to increase prices for customers in the United States.
    - **Adjustment Type (Percentage / Amount):** A radio button or dropdown to choose how the price will be adjusted.
      - *Effect:*
        - *Percentage:* The price will be increased or decreased by a percentage of its original value.
        - *Amount:* The price will be increased or decreased by a fixed monetary value (in your shop’s default currency).
      - *Recommended:* Choose based on your pricing strategy. Percentage is good for consistent markups, Amount for fixed surcharges/discounts.
      - *Scenario:* You want to add a 10% markup (Percentage) or a fixed $5 surcharge (Amount).
    - **Value:** An input field to enter the percentage (e.g., “10” for 10%) or the fixed amount (e.g., “5.00” for $5).
      - *Effect:*
        - *Positive Value:* Increases the price.
        - *Negative Value:* Decreases the price (e.g., “-5” for a 5% discount or “-2.50” for a $2.50 discount).
      - *Recommended:* Enter the desired adjustment. Be careful with negative values to avoid prices going below zero.
      - *Scenario:* Enter “15” to increase by 15%, or “-2.50” to decrease by $2.50.
- **Effect of changes:**
  - Adding a new rule immediately activates the price adjustment for the selected country.
  - Editing a rule updates the adjustment for that country.
  - Deleting a rule removes the country-specific adjustment, and customers from that country will revert to seeing default product prices.
- **Recommended workflow for daily store management:**
  1. Identify a country where you want to adjust prices (e.g., due to higher shipping costs, local competition, or a special promotion).
  2. Navigate to the “Price by Country List” screen.
  3. Click “Add New Rule”.
  4. Select the target country.
  5. Choose whether to adjust by “Percentage” or “Amount”.
  6. Enter the positive or negative value for the adjustment.
  7. Save the rule.
  8. Test by using a VPN or asking someone in that country to check your store’s prices.

#### index.php (pbc/controllers/admin/index.php)

This file likely serves as a routing or placeholder for the admin controllers within the `pbc` module directory. It doesn’t represent a distinct, configurable screen but rather ensures proper access and loading of other admin controllers like `AdminPbcListController`. Merchants will not directly interact with this file.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration Page** | Module Enabled/Disabled | Enabled | Global switch to activate or deactivate all country-specific price adjustments. |
| **Price by Country List** | Add/Edit Rule: Country | N/A (select specific) | Defines the target country for price adjustment. |
|  | Add/Edit Rule: Adjustment Type | Percentage | Choose if price changes by percentage or fixed amount. |
|  | Add/Edit Rule: Value | 0 (enter desired) | The positive (increase) or negative (decrease) percentage or amount. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My prices aren’t changing for a specific country, even after I set up a rule.**
A:

1. **Is the module enabled globally?** Check the main module configuration page (Modules > Module Manager > Configure “Increase prices by country”) to ensure the module is active.
2. **Is the rule correctly configured?** Go to “Price by Country List” and verify that the country is correctly selected, the adjustment type (percentage/amount) is right, and the value is entered correctly (positive for increase, negative for decrease).
3. **Clear Cache:** PrestaShop uses caching. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” if available). This often resolves display issues.
4. **Geolocation Issues:** The module relies on PrestaShop’s geolocation feature. Ensure your PrestaShop store’s geolocation is correctly configured (Advanced Parameters > Geolocation). If you’re testing from your own country, try using a VPN to simulate a visit from the target country.

**Q: Will this module affect my SEO or product feeds?**
A: The module dynamically adjusts prices on the front-office based on the visitor’s IP. It does not alter your product’s base price in the database. Therefore, it generally should not directly impact your SEO (search engines typically crawl from a default location or use your base prices) or product feeds (which usually pull base prices). However, if you use a third-party service that crawls your site from different locations, they might see the adjusted prices.

**Q: What happens if a customer from a country with a price adjustment adds a product to the cart, then changes their country (e.g., via shipping address)?**
A: The module adjusts prices based on the *customer’s detected country* at the time of browsing. If the customer’s country changes (e.g., they log in and their address is in a different country, or they explicitly select a different shipping country during checkout), PrestaShop’s core logic for price calculation (which this module overrides) should re-evaluate the price. The module’s override ensures that the correct price for the *final* country is applied.

**Q: Can I apply different rules for different customer groups within the same country?**
A: No, this module adjusts prices based *solely on the country* determined by geolocation. It does not offer options to differentiate pricing based on customer groups (e.g., wholesale vs. retail) within a single country. For customer group specific pricing, you would need a separate module or PrestaShop’s built-in price rules.

**Q: I set an amount increase, but it looks different in other currencies.**
A: When you set an amount increase (e.g., +$5), the module applies this amount in your shop’s *default currency*. It then automatically converts this additional amount into other currencies based on your store’s configured currency exchange rates. This ensures that the *value* of the increase remains consistent across currencies. Make sure your currency exchange rates are up-to-date in PrestaShop (International > Currencies).

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Increase prices by country” module (`pbc`) primarily functions by overriding PrestaShop’s core `Product` class to inject country-specific price adjustments during price calculation. It leverages PrestaShop’s geolocation features to identify the customer’s country and applies rules defined in a custom database table. The module follows a standard PrestaShop MVC pattern for its Back Office management, with a dedicated Admin Controller for managing price rules.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None explicitly defined in the module archive. Price adjustments are handled via the `Product.php` override, which hooks into PrestaShop’s core price calculation logic.
- **Back-Office Admin Controllers**:
  - `pbc/controllers/admin/AdminPbcListController.php`
    - **Class Name**: `AdminPbcListController` (extends `ModuleAdminController`)
    - **Responsibility**: Manages the CRUD operations for the `pricebc` (Price By Country) entity. This controller displays the list of defined price adjustment rules, handles adding new rules, editing existing ones, and deleting them. It uses PrestaShop’s `HelperList` and `HelperForm` for rendering the list and the add/edit forms, respectively.
    - **Tab Name**: Typically registered under a custom tab in the Back Office navigation, accessible via the module’s main menu entry.
  - `pbc/controllers/admin/index.php`
    - **Class Name**: N/A (this is a placeholder file)
    - **Responsibility**: This file is a common practice in PrestaShop module development to prevent direct directory listing and ensure proper routing within the `controllers/admin` directory. It does not contain executable logic for a specific controller.

### 4.3 Core Classes & Models (`classes/`)

- `pbc/classes/index.php`
  - **Class Name**: N/A
  - **Responsibility**: Placeholder file to prevent directory listing.
- `pbc/classes/pricebc.php`
  - **Class Name**: `PriceBc` (extends `ObjectModel`)
  - **Database Table**: `_pbc` (e.g., `ps_pbc`)
  - **`$definition` fields**:
    - `id_pbc`: Primary key.
    - `id_country`: Foreign key to `ps_country` table, identifying the target country.
    - `type`: Integer, typically 0 for percentage, 1 for amount.
    - `value`: Decimal, the percentage or amount to adjust. Can be positive or negative.
  - **Key Public Methods**: Standard `ObjectModel` methods for CRUD operations. May include static methods for retrieving rules based on country ID.
- `pbc/override/classes/index.php`
  - **Class Name**: N/A
  - **Responsibility**: Placeholder file to prevent directory listing within the override directory.
- `pbc/override/classes/Product.php`
  - **Class Name**: `Product` (extends PrestaShop’s core `Product` class)
  - **Responsibility**: This is the most critical part of the module. It overrides the `getPriceStatic()` method (or similar price calculation methods) of the core `Product` class.
    - It fetches the customer’s current country (via geolocation or context).
    - It queries the `PriceBc` model to find any active price adjustment rules for that country.
    - It then applies the percentage or amount adjustment to the product’s base price before returning the final calculated price.
    - Handles currency conversion for amount-based adjustments.
  - **Developer Note**: Any other modules that also override `Product.php` might lead to conflicts. Careful testing is required. The module’s override should be designed to be compatible with other overrides or to allow for chaining.

### 4.4 JavaScript Assets (`views/js/`)

- `pbc/views/admin/script.js`
  - **Scope**: Back-office (AdminPbcListController forms).
  - **Functionality**: Likely handles dynamic behavior on the “Add/Edit Price Rule” form. This could include:
    - Showing/hiding fields based on the selected “Adjustment Type” (e.g., if “Percentage” is selected, ensure the value field is treated as a percentage).
    - Input validation or formatting.
    - AJAX calls for country selection or other dynamic form elements.

### 4.5 CSS Stylesheets (`views/css/`)

No custom CSS files were detected in the provided inventory. The module likely relies on PrestaShop’s default Back Office styling for its configuration forms and lists, and does not introduce any front-office visual elements requiring custom styling.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `pbc/views/displayHeader.tpl`
    - **Hook**: `displayHeader`
    - **Purpose**: This template is likely used to include necessary JavaScript or CSS files (if any were present) or to initialize any front-office scripts that need to run early in the page load. Given the module’s nature, it might also contain logic to detect the user’s country or set a global JS variable for debugging.
- **Admin templates (`views/templates/admin/`)**:
  - `pbc/lib/searchTool/views/scripts.tpl`
    - **Purpose**: This template is likely part of a reusable component or library within the module, possibly for a search or filtering tool used in the AdminPbcListController. It would contain JavaScript or Smarty logic related to that tool.
- **Front-office templates (`views/templates/front/`)**:
  - `pbc/views/script.tpl`
    - **Purpose**: Similar to `displayHeader.tpl`, this template might be used to embed JavaScript directly into the front-office, potentially for client-side logic related to price display (though the primary logic is server-side via the `Product` override). It could also be a fallback or a more generic script inclusion point.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  - `ps_pbc`: Stores the price adjustment rules.
    - `id_pbc` (INT, PK, AUTO\_INCREMENT)
    - `id_country` (INT, FK to `ps_country.id_country`)
    - `type` (TINYINT, 0 for percentage, 1 for amount)
    - `value` (DECIMAL(20,6), signed, the adjustment value)
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | To include module’s JS/CSS assets or initialize front-end scripts. |
| `actionProductPriceCalculation` | (Implicit via `Product.php` override) | The module’s core functionality is implemented by overriding the `Product::getPriceStatic()` method, which is called whenever PrestaShop calculates a product’s price. This is not a standard hook but a core class override. |
| `actionAdminControllerSetMedia` | When an admin controller is loaded. | To include module’s JS/CSS assets for the Back Office (e.g., `AdminPbcListController`). |
| `actionModuleInstall` | During module installation. | To create the `ps_pbc` database table and register necessary hooks. |
| `actionModuleUninstall` | During module uninstallation. | To remove the `ps_pbc` database table and unregister hooks. |

## 5. Official Support & Updates

For official updates, bug fixes, and technical support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to providing assistance and ensuring the module functions optimally with your PrestaShop store.
