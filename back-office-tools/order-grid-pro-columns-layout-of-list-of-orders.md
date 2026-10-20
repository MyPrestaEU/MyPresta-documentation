---
title: "Order Grid Pro - columns & layout of list of orders - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Order Grid Pro - columns & layout of list of orders PrestaShop module by MyPresta.eu."
sidebar:
  label: "Order Grid Pro - columns & layout of list of orders - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Order Grid Pro - columns & layout of list of orders Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-grid-pro-columns-layout-of-list-of-orders.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/order-grid-pro-columns-layout-of-list-of-orders/)
>
> ---


# Order Grid Pro - columns & layout of list of orders

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.7.x, 1.7.8.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” will take you to the main configuration page for Order Grid Pro. This page is where you define which columns appear in your order list and their arrangement.

The configuration is typically divided into several tabs or sections, allowing you to manage different aspects of the order grid.

**General Settings / Column Visibility & Order:**
This is the core of the module. You will typically see a list of all available columns, both default PrestaShop columns and the new ones added by Order Grid Pro.

- **What this setting does:** This section allows you to choose which columns are visible in your Back Office order list and to arrange their display order. You’ll usually see two lists: “Available Columns” and “Active Columns” (or similar).
- **Effect of changing this setting:**
  - *Moving a column from “Available” to “Active”:* The column will appear in your Back Office order list.
  - *Moving a column from “Active” to “Available”:* The column will be hidden from your Back Office order list.
  - *Dragging and dropping columns within “Active Columns”:* Changes the left-to-right display order of columns in your order list.
- **Recommended value:** This is entirely dependent on your team’s needs. Start by enabling columns you frequently check and hiding those you never use. Arrange them in a logical flow for your daily tasks.
- **Merchant scenario / example:**
  - **Warehouse Manager:** Might enable “Product Thumbnail,” “Product Weight,” “Tracking Number,” and “Carrier” and place them prominently on the left for quick dispatch processing. They might hide “Customer Email” or “Payment Method” if not relevant to their role.
  - **Customer Service Agent:** Would prioritize “Customer Phone,” “Customer Email,” “Customer Service Thread Snippet,” and “Order Message” to quickly address inquiries without opening each order.
  - **Finance Department:** Might focus on “Payment Method,” “Currency ISO,” “Total Paid,” and “Cart Rules” to verify transactions and discounts.

**Specific Column Options (Examples of new columns you can enable):**

- **Customer Phone:**

  - **What this setting does:** Displays the customer’s phone number directly in the order list.
  - **Effect of changing this setting:**
    - *When enabled:* Phone numbers appear, making it easy to call customers without navigating to their order details.
    - *When disabled:* Phone numbers are hidden.
  - **Recommended value:** YES, if your customer service or shipping team frequently needs to contact customers.
  - **Merchant scenario / example:** A customer service agent can quickly call a customer about a delivery issue directly from the order list.
- **Tracking Number:**

  - **What this setting does:** Shows the tracking number associated with the order.
  - **Effect of changing this setting:**
    - *When enabled:* Tracking numbers are visible, allowing quick copy-pasting for tracking updates.
    - *When disabled:* Tracking numbers are hidden.
  - **Recommended value:** YES, essential for warehouse and customer service teams.
  - **Merchant scenario / example:** Warehouse staff can quickly verify if a tracking number has been added before dispatch, or customer service can provide it to a customer.
- **First-line Product Thumbnail:**

  - **What this setting does:** Displays a small image of the first product in the order.
  - **Effect of changing this setting:**
    - *When enabled:* A visual cue of the order’s contents appears, aiding quick identification.
    - *When disabled:* No product image is shown.
  - **Recommended value:** YES, very helpful for visual confirmation, especially for warehouse picking.
  - **Merchant scenario / example:** Warehouse staff can visually confirm the type of product in an order without opening it, speeding up picking.
- **Order Weight:**

  - **What this setting does:** Shows the total weight of the order.
  - **Effect of changing this setting:**
    - *When enabled:* Order weight is displayed, useful for shipping calculations or carrier selection.
    - *When disabled:* Order weight is hidden.
  - **Recommended value:** YES, if you deal with physical products and weight is a factor in shipping.
  - **Merchant scenario / example:** Shipping managers can quickly assess package sizes and weights for bulk shipments.
- **Customer Service Thread Snippet:**

  - **What this setting does:** Displays a short snippet from the latest customer service message related to the order.
  - **Effect of changing this setting:**
    - *When enabled:* Provides immediate context on recent customer communications.
    - *When disabled:* No snippet is shown.
  - **Recommended value:** YES, invaluable for customer service teams.
  - **Merchant scenario / example:** A customer service agent can see if a customer has recently inquired about an order without opening the full thread.
- **Currency ISO:**

  - **What this setting does:** Shows the ISO code of the currency used for the order (e.g., EUR, USD).
  - **Effect of changing this setting:**
    - *When enabled:* Useful for international stores to quickly identify the currency.
    - *When disabled:* Currency ISO is hidden.
  - **Recommended value:** YES, if you operate a multi-currency store.
  - **Merchant scenario / example:** Finance staff can quickly sort or filter orders by currency for reconciliation.
- **Cart Rules (Discounts) Applied:**

  - **What this setting does:** Indicates if any cart rules (discounts) were applied to the order.
  - **Effect of changing this setting:**
    - *When enabled:* Provides a quick overview of discounted orders.
    - *When disabled:* Information about applied discounts is hidden.
  - **Recommended value:** YES, for finance, marketing, or customer service to understand pricing.
  - **Merchant scenario / example:** Marketing can quickly identify orders that used a specific promotion code.

**Saving Changes:**
Always remember to click the “Save” or “Update” button after making any changes to your column selections or order. The module saves the column order as JSON, ensuring your custom layout persists.

### 2.2 Dedicated Admin Screens & Controller Views

#### 2.2.1 AdminMyordergridproAjaxController (Back Office > Modules > Configure > Order Grid Pro)

This controller primarily handles the dynamic interactions on the module’s configuration page. It doesn’t have a separate menu item in the PrestaShop navigation.

- **Screen Name & Menu Location:** This controller is activated when you are on the “Modules > Module Manager > Order Grid Pro > Configure” page. It processes AJAX requests made by the JavaScript on that page.
- **Available Actions & Settings:** It manages the saving and loading of your custom grid configurations (which columns are visible and their order). When you drag and drop columns or toggle their visibility on the module’s configuration page, this controller receives the data and saves it.
- **Effect of changes:** Any changes you make to the column layout on the module’s configuration page are sent to this controller, which then updates the stored preferences for your order grid. This ensures that when you navigate to “Orders > Orders,” your custom layout is applied.
- **Recommended workflow for daily store management:** You interact with this controller indirectly by simply configuring the module on its main page. There’s no direct “management view” for merchants here; it’s the backend processor for your configuration choices.

#### 2.2.2 index.php (myordergridpro/controllers/admin/index.php)

This file is a standard placeholder or entry point for admin controllers within a module, ensuring that direct access to the directory is prevented and that PrestaShop’s security mechanisms are respected. It does not represent a distinct, configurable screen for the merchant.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration Page** | **Column Visibility & Order** | Varies by role | Selects which columns appear in the Back Office order list and their display order. Directly impacts team efficiency. |
|  | *Customer Phone* | YES | Displays customer phone number for quick contact. |
|  | *Tracking Number* | YES | Shows order tracking number for dispatch/support. |
|  | *First-line Product Thumbnail* | YES | Visual cue of the first product in the order. |
|  | *Order Weight* | YES (for physical goods) | Displays total order weight for shipping. |
|  | *Customer Service Thread Snippet* | YES | Provides context on recent customer communications. |
|  | *Currency ISO* | YES (for multi-currency) | Shows currency code for international stores. |
|  | *Cart Rules Applied* | YES | Indicates if discounts were used on the order. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve configured the columns, but I don’t see the changes on the Orders page.**
A:

1. **Clear PrestaShop Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” in the top right. Sometimes, PrestaShop caches module configurations.
2. **Browser Cache:** Try clearing your browser’s cache or opening the Back Office in an incognito/private window to ensure you’re not seeing an old cached version of the page.
3. **Save Configuration:** Double-check that you clicked the “Save” or “Update” button on the module’s configuration page after making your changes.

**Q: Some columns I enabled are empty or show “N/A”. Why?**
A: This usually means the data for that specific column is not available for that particular order. For example:

- “Tracking Number” will be empty if no tracking number has been added to the order.
- “Customer Service Thread Snippet” will be empty if there are no customer service messages for that order.
- “Order Weight” might be empty if product weights are not defined or if the order contains only virtual products.
  This is normal behavior and indicates missing data rather than a module error.

**Q: The drag-and-drop for reordering columns isn’t working.**
A:

1. **JavaScript Conflict:** Another module or your theme might have a JavaScript conflict. Try disabling other recently installed modules one by one to identify the culprit.
2. **Browser Issue:** Test in a different browser (Chrome, Firefox, Edge) to rule out a browser-specific problem.
3. **Clear Cache:** Clear both PrestaShop and browser cache as described above.

**Q: Will this module slow down my Back Office?**
A: The module is designed to use official PrestaShop grid hooks and avoid core overrides, which helps maintain performance and compatibility. While adding many new columns requires PrestaShop to fetch more data, the impact is generally minimal. If you notice significant slowdowns, consider reducing the number of highly complex custom columns you’ve enabled.

**Q: Is this module compatible with my custom theme?**
A: Yes, this module works within the PrestaShop Back Office, which uses its own default theme (New Classic or similar). It does not affect your front-office theme, so there should be no compatibility issues with custom front-office themes.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Order Grid Pro” module extends the PrestaShop Back Office order list functionality, specifically targeting the Symfony grid system introduced in PrestaShop 1.7.7+. It adheres to PrestaShop’s module development best practices by utilizing official hooks (`actionGet and actionSet` for grid definitions) rather than direct core overrides. This ensures upgrade compatibility and stability. The module primarily injects new column definitions and data providers into the existing order grid, and stores user preferences for column visibility and order using standard PrestaShop configuration. AJAX calls handle dynamic updates to these preferences.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. This module is purely Back-Office.
- **Back-Office Admin Controllers**:

  - `controllers/admin/AdminMyordergridproAjaxController.php`
    - **Class name & parent class**: `AdminMyordergridproAjaxController` extends `ModuleAdminController`.
    - **Responsibility**: This controller is responsible for handling AJAX requests from the module’s configuration page. It processes requests to save and load the custom order grid configuration (column visibility and order). It typically receives JSON data representing the desired grid layout and stores it in `Configuration::updateValue()`.
    - **Routes**: Responds to AJAX calls made to `index.php?controller=AdminMyordergridproAjax&token=...&ajax=1`.
  - `controllers/admin/index.php`
    - **Class name & parent class**: Not a class, but a security file.
    - **Responsibility**: This is a standard empty `index.php` file placed in controller directories to prevent directory listing and direct access, enhancing security. It typically contains `<?php header('Expires: Mon, 26 Jul 1997 05:00:00 GMT'); header('Last-Modified: '.gmdate('D, d M Y H:i:s').' GMT'); header('Cache-Control: no-store, no-cache, must-revalidate'); header('Cache-Control: post-check=0, pre-check=0', false); header('Pragma: no-cache'); header('Location: ../'); exit;`.

### 4.3 Core Classes & Models (`classes/`)

The module does not appear to define custom `ObjectModel` classes or database tables. It primarily works by extending existing PrestaShop grid definitions and storing configuration data in `ps_configuration`.

### 4.4 JavaScript Assets (`views/js/`)

- `views/js/grid_pro.js`

  - **Scope**: Back-office (Order List page).
  - **Description**: This script likely contains the core logic for manipulating the PrestaShop Symfony grid on the “Orders > Orders” page. It would be responsible for:
    - Reading the saved column configuration from `Configuration::get()`.
    - Dynamically adding/removing columns to the grid based on the configuration.
    - Applying the custom order of columns.
    - Potentially handling live updates or specific column rendering logic.
    - Binding to PrestaShop’s grid events (e.g., `prestashop.on('grid.loaded', ...)`).
- `views/js/order_grid_admin.js`

  - **Scope**: Back-office (Module Configuration page).
  - **Description**: This script is primarily used on the module’s configuration page (`getContent()`). It handles the user interface for selecting and ordering columns. This includes:
    - Implementing drag-and-drop functionality for column reordering.
    - Managing the “Available Columns” and “Active Columns” lists.
    - Binding event listeners to switches/checkboxes for column visibility.
    - Making AJAX calls to `AdminMyordergridproAjaxController.php` to save the updated configuration.
- `views/js/order_list_live_status.js`

  - **Scope**: Back-office (Order List page).
  - **Description**: This script likely provides functionality for live updates or interactive elements directly within the order list. This could include:
    - AJAX-based status updates for orders without page refresh.
    - Tooltips or popovers for additional information on specific columns.
    - Potentially enhancing the default status change dropdowns or adding custom quick actions.

### 4.5 CSS Stylesheets (`views/css/`)

- `views/css/order_grid_admin.css`
  - **Scope**: Back-office (Module Configuration page and potentially Order List page).
  - **Description**: This stylesheet provides the visual styling for the module’s configuration interface, ensuring the drag-and-drop elements and column lists are presented clearly. It may also include minor styling adjustments for the new columns introduced in the actual order list to ensure proper alignment and readability within the PrestaShop Back Office theme.
  - **Key CSS class selectors**: Likely targets specific IDs or classes within the module’s `getContent()` template, and potentially new column classes injected into the grid.

### 4.6 Smarty Template Structure (`views/templates/`)

The module information indicates no explicit `.tpl` files were found in `views/templates/`. This suggests that the module’s configuration interface is likely rendered directly within the `getContent()` method of the main module file (`index.php`) using PHP to generate the HTML, or it dynamically injects content into existing PrestaShop grid templates via hooks.

If templates were present, they would typically be:

- **Hook templates (`views/templates/hook/`)**: For rendering new column content within the grid cells.
- **Admin templates (`views/templates/admin/`)**: For the module’s configuration form.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create custom SQL tables.
  - Configuration settings (e.g., the JSON string representing the column order and visibility) are stored in the `ps_configuration` table using keys like `MYORDERGRIDPRO_CONFIG` or similar.
- **Registered Hooks Table**:
  The module primarily relies on PrestaShop’s Symfony grid hooks for its functionality.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionGet and actionSet` (for grid definitions) | When the order grid is being defined and rendered in the Back Office. | These are the primary hooks used to inject new column definitions and data providers into the existing PrestaShop order grid. `actionGet` allows the module to retrieve the current grid definition, and `actionSet` allows it to modify or add new columns before the grid is rendered. |
| `displayBackOfficeHeader` | Executed in the `<head>` section of every Back Office page. | Used to include CSS and JavaScript assets (`order_grid_admin.css`, `grid_pro.js`, `order_grid_admin.js`, `order_list_live_status.js`) specifically for the Back Office, ensuring they are loaded when needed. |
| `displayAdminOrderListToolbar` (or similar) | Renders content in the toolbar area of the order list. | Potentially used to add quick action buttons or filters related to the module’s functionality. |
| `actionAdminOrdersListingFieldsModifier` (or similar) | Modifies the fields/columns available in the order listing query. | Allows the module to add new fields to the SQL query that fetches order data, enabling the display of custom column data. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for “Order Grid Pro - columns & layout of list of orders,” please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our team is dedicated to ensuring your module functions perfectly and helps you maximize your PrestaShop store’s efficiency.
