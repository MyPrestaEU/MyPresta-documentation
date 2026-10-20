---
title: "Limit number of allowed orders - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Limit number of allowed orders PrestaShop module by MyPresta.eu."
sidebar:
  label: "Limit number of allowed orders - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Limit number of allowed orders Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/limit-number-of-allowed-orders.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/limit-number-of-allowed-orders/)
>
> ---


# Limit number of allowed orders

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the module, where you define the global limits for your customers.

- **What this setting does:** This is the core setting of the module. It defines the maximum number of orders *any* customer can place in your store before being prevented from placing more.
- **Effect of changing this setting:**
  - *When set to a specific number (e.g., 3):* Any customer who has successfully placed 3 orders will no longer be able to place a 4th order. They will see a message preventing them from completing checkout.
  - *When set to 0 or left empty:* The module will effectively be disabled for global limits, meaning customers can place an unlimited number of orders (unless specific customer limits are set, see section 4.2).
- **Recommended value:** Start with a value that aligns with your business goal (e.g., 1 for a strict “one per customer” promotion, 5 for a general limit). If you only want to limit specific customers, you can leave this empty and use the dedicated customer management screen.
- **Merchant scenario / example:** You’re running a flash sale for a highly sought-after product and want to ensure every customer gets only one chance to buy. You would set this value to `1`.

### 2.2 Dedicated Admin Screen: Customer Order Limits (Back Office > Modules > Limit number of allowed orders > Customer Order Limits)

This screen allows you to manage individual order limits for specific customers, overriding the global limit set in section 4.1.

- **Screen Name & Menu Location:** You can access this screen by navigating to **Modules > Module Manager**, finding “Limit number of allowed orders”, clicking “Configure”, and then looking for a tab or link labeled “Customer Order Limits” or similar. Alternatively, it might appear directly in your main PrestaShop menu under a new entry created by the module (e.g., **Customers > Customer Order Limits**).
- **Available Actions & Settings:**

  - **Customer Search/Selection:** You’ll typically find a search bar or a dropdown to select an existing customer from your store.
  - **Set Individual Limit:** Once a customer is selected, you can input a specific number of allowed orders for *that particular customer*.
  - **View/Edit Existing Limits:** A table or list will display all customers for whom you’ve set custom limits, along with their current limit and possibly their current order count. You can edit or delete these entries.
  - **Currency Display:** The module might display currency information (e.g., `PS_CURRENCY_DEFAULT`) in the context of customer orders, though the limits themselves are numerical counts of orders, not monetary values.
- **Effect of changes:**

  - *Adding a new customer limit:* The selected customer will now be restricted by the specific number of orders you set for them, overriding the global limit (if one is set).
  - *Editing an existing customer limit:* The customer’s allowed order count will be updated immediately.
  - *Deleting a customer limit:* The customer will revert to being governed by the global order limit (if set), or will have no limit if no global limit is active.
- **Recommended workflow for daily store management:**

  1. **Identify specific needs:** Determine if certain VIP customers, problematic customers, or customers participating in special programs require unique order limits.
  2. **Search and add:** Use the search functionality to find the customer.
  3. **Apply limit:** Enter the desired maximum number of orders for that customer.
  4. **Monitor:** Periodically review the list of custom-limited customers to ensure the settings are still appropriate.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | **Maximum Allowed Orders (Global)** | 0 (Unlimited) / Your Business Need | Sets a store-wide maximum number of orders for *all* customers. Prevents checkout if exceeded. |
| Customer Order Limits | **Customer Search & Selection** | N/A | Allows finding and selecting specific customers to apply individual limits. |
| Customer Order Limits | **Individual Customer Order Limit** | N/A | Overrides the global limit for a specific customer. Prevents checkout for that customer if their individual limit is exceeded. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My customers are still able to place unlimited orders, even after I set a global limit. What’s wrong?**
A:

1. **Check the setting:** Double-check that you’ve saved the “Maximum Allowed Orders (Global)” setting on the main module configuration page.
2. **Clear Cache:** PrestaShop uses caching. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). This ensures your new settings are applied immediately.
3. **Module Status:** Ensure the module is enabled in **Modules > Module Manager**.
4. **Specific Customer Overrides:** Check the “Customer Order Limits” screen. If a specific customer has an individual limit set to `0` or a very high number, it will override the global limit for them.

**Q: Can I set a limit for a customer based on the *value* of their orders, not just the count?**
A: This module specifically limits the *number* of orders. It does not currently support limiting based on monetary value. For value-based limits, you would need a different type of module or custom development.

**Q: What happens when a customer reaches their limit? What do they see?**
A: When a customer attempts to place an order that would exceed their limit, the module will prevent the order from being finalized. Typically, a clear message will be displayed on the checkout page or in the shopping cart, informing them that they have reached their maximum allowed orders and cannot proceed. The exact wording might depend on your PrestaShop version and theme.

**Q: Does this module affect past orders?**
A: No, this module only affects *future* orders. It counts existing successful orders to determine if a new order attempt would exceed the limit, but it does not modify or cancel any previously placed orders.

**Q: I want to temporarily lift a limit for a specific customer. How do I do that?**
A: Go to the “Customer Order Limits” screen. Find the customer, edit their individual limit, and set it to `0` (for unlimited) or a very high number. Remember to save your changes. You can always re-apply a stricter limit later.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Limit number of allowed orders” module follows a standard PrestaShop module architecture, leveraging hooks for integration and an AdminController for managing specific customer limits. It primarily operates by checking customer order history against configured limits during the order validation process. The module relies on PrestaShop’s configuration system for global settings and a custom database table for individual customer limits.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: This module does not use dedicated front-office controllers. Its logic for checking limits is integrated directly into PrestaShop’s order process via hooks.
- **Back-Office Admin Controllers**:
  - `controllers/admin/AdminLimitOrdersUserController.php`
    - **Class Name**: `AdminLimitOrdersUserController` (extends `ModuleAdminController`)
    - **Responsibility**: This controller manages the custom order limits for individual customers. It provides a standard PrestaShop `list` and `form` interface for adding, editing, and deleting customer-specific order limits. It interacts with the `LimitOrdersUser` ObjectModel (though no explicit `classes/` file was identified, it’s implied by the controller’s name and function). It likely uses `PS_CURRENCY_DEFAULT` for displaying currency context, though the limits themselves are numerical.
    - **Tab Name**: Likely “Customer Order Limits” or similar, accessible from the module’s configuration page or a dedicated menu entry.
  - `controllers/admin/index.php`
    - **Class Name**: (Not a class, typically an empty file or a redirect for security)
    - **Responsibility**: This file is usually a placeholder or a security measure to prevent direct directory listing. It does not contain active controller logic.

### 4.3 Core Classes & Models (`classes/`)

Based on the provided information, no explicit custom classes were identified in the `classes/` directory. However, the `AdminLimitOrdersUserController` strongly implies the existence of an `ObjectModel` class, likely named `LimitOrdersUser`, which would map to a custom database table (e.g., `ps_limitorders_user`). This `ObjectModel` would define fields such as `id_customer` and `max_orders`.

### 4.4 JavaScript Assets (`views/js/`)

- `lib/searchTool/views/js/autocomplete.js`
  - **Scope**: Likely Back-office.
  - **Purpose**: Provides autocomplete functionality, probably for searching and selecting customers within the `AdminLimitOrdersUserController` form when setting individual limits. It would bind to input fields, send AJAX requests to a backend controller (possibly the `AdminLimitOrdersUserController` itself or a dedicated AJAX endpoint), and display suggestions.
- `views/js/limitorders.js`
  - **Scope**: Potentially both Front-office (for displaying messages) and Back-office (for general module functionality).
  - **Purpose**: This file would contain the core JavaScript logic for the module. In the Back-office, it might handle form validations or dynamic UI elements on the configuration pages. In the Front-office, if any dynamic messages or interactions are needed when a customer hits their limit (e.g., a modal popup, dynamic cart update), this script would manage that.

### 4.5 CSS Stylesheets (`views/css/`)

- `lib/searchTool/views/css/autocomplete.css`
  - **Scope**: Back-office admin styling.
  - **Purpose**: Styles the autocomplete dropdown and input fields used in the admin panel, ensuring a consistent and user-friendly search experience for customers.
- `views/css/limitorders.css`
  - **Scope**: Both Front-office and Back-office.
  - **Purpose**: Contains general styling for any visible elements introduced by the module. In the Back-office, it would style the configuration forms and tables. In the Front-office, it would style the messages displayed to customers when they reach their order limit, ensuring they integrate well with the store’s theme.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - This module does not explicitly list templates in the `hook/` directory, but its functionality implies it would hook into `displayShoppingCart` or `displayShoppingCartFooter` to show messages.
- **Admin templates (`views/templates/admin/`)**:
  - Templates for the `AdminLimitOrdersUserController` (e.g., `list.tpl`, `form.tpl`) would reside here, defining the structure of the customer limit management interface.
- **Front-office templates (`views/templates/front/`)**:
  - `views/templates/front/displayShoppingCart.tpl`
    - **Purpose**: This template is likely rendered when the module hooks into `displayShoppingCart`. It would contain the logic to display a message to the customer *within their shopping cart* if they have reached their order limit, preventing them from proceeding to checkout.
  - `views/templates/front/displayShoppingCartEmpty.tpl`
    - **Purpose**: This template might be used in a specific scenario where the module needs to display a message related to order limits even when the cart is empty, or as a fallback/alternative message display. Its exact use case would depend on the module’s internal logic for different states.
- `lib/searchTool/views/scripts.tpl`
  - **Purpose**: This template likely includes the necessary JavaScript and CSS files for the `autocomplete.js` and `autocomplete.css` components, ensuring they are loaded correctly in the Back-office.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  - `ps_configuration`: Stores the global maximum allowed orders (e.g., `LIMITORDERS_MAX_ORDERS`).
  - `ps_limitorders_user`: (Implied custom table) Stores individual customer order limits.
    - `id_limitorders_user` (Primary Key)
    - `id_customer` (Foreign Key to `ps_customer`)
    - `max_orders` (INT, the maximum number of orders allowed for this specific customer)
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Renders in the `<head>` section of all front-office pages. | Potentially for loading front-office CSS/JS assets or for early checks. |
| `displayRightColumn` / `displayLeftColumn` | Renders in the right/left column of front-office pages. | Could be used to display a subtle message about order limits, though less likely for this module. |
| `displayProductButtons` / `displayProductExtraContent` | Renders on the product page. | Could be used to display a message if a customer has reached their limit and cannot add to cart. |
| `displayShoppingCart` | Renders within the shopping cart summary. | **CRITICAL:** Likely used to display messages to the customer if they have reached their order limit, preventing checkout. |
| `displayShoppingCartFooter` | Renders below the shopping cart summary. | Similar to `displayShoppingCart`, for displaying messages or warnings. |
| `displayFooter` | Renders in the footer of all front-office pages. | Less likely for core functionality, possibly for general module information or scripts. |
| `actionValidateOrder` | Executed *after* an order has been successfully validated and saved to the database. | **CRITICAL:** This hook is essential for the module to increment the order count for a customer and potentially update their status if they’ve reached their limit. |
| `actionBeforeCartUpdateQuantity` | Executed before a product quantity is updated in the cart. | Could be used to perform a preliminary check on limits before allowing an item to be added/updated. |
| `actionFrontControllerSetMedia` | Allows adding CSS/JS to front-office pages. | Used to load `limitorders.js` and `limitorders.css` on relevant front-office pages. |
| `actionAdminControllerSetMedia` | Allows adding CSS/JS to back-office pages. | Used to load admin-specific CSS/JS for the configuration and `AdminLimitOrdersUserController` screens. |
| `displayBackOfficeHeader` | Renders in the `<head>` section of all back-office pages. | For loading admin-specific CSS/JS or displaying admin notices. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the “Limit number of allowed orders” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to ensuring your module functions perfectly and helps you achieve your e-commerce goals.
