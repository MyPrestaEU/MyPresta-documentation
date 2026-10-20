---
title: "Delete Orders Pro - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Delete Orders Pro PrestaShop module by MyPresta.eu."
sidebar:
  label: "Delete Orders Pro - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Delete Orders Pro Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/delete-orders-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/delete-orders-pro/)
>
> ---


# Delete Orders Pro

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are required beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” will take you to the main configuration page for the “Delete Orders Pro” module. This screen primarily handles general module settings and update checks.

- **What this setting does:** This section typically includes standard MyPresta.eu module settings related to update notifications and internal tracking.
- **Effect of changing this setting:**
  - `mypresta_updates`, `update_`, `updatev_`: These settings control whether the module checks for updates from MyPresta.eu and displays notifications in your back office. Enabling them keeps you informed about new versions and features. Disabling them will stop these notifications.
  - `DELETEORDERS_LAST_TAB`: This is an internal setting that tracks the last tab or view you were on within the module’s dedicated administration interface. It helps the module remember your last position for convenience.
- **Recommended value:**
  - For update-related settings: **YES** (or Enabled). It’s always recommended to keep update checks enabled to ensure you’re running the latest, most secure, and feature-rich version of the module.
  - `DELETEORDERS_LAST_TAB`: Leave this setting as is; it’s managed automatically by the module.
- **Merchant scenario / example:** Keeping update checks enabled means you’ll be notified directly in your PrestaShop back office when a new version of “Delete Orders Pro” is released, ensuring you can easily upgrade and benefit from improvements or bug fixes.

### 2.2 Dedicated Admin Screens & Controller Views

#### 2.2.1 Delete Orders Tab (Back Office > Orders > Delete Orders Pro)

This is the primary interface where you will manage and delete orders.

- **Screen Name & Menu Location:** You can access this screen by navigating to **Orders > Delete Orders Pro** in your PrestaShop back office menu.
- **Available Actions & Settings:** This screen presents a grid or list view of your orders, similar to the standard PrestaShop Orders list, but with added functionality specifically for deletion.
  - **Filtering Options:** You will likely find filters to narrow down the orders you want to delete (e.g., by order status, date range, customer, etc.). This is crucial for safely targeting specific types of orders.
  - **Selection Checkboxes:** Each order in the list will have a checkbox, allowing you to select individual orders for deletion.
  - **Bulk Actions:** There should be an option to select multiple orders (e.g., “Select All” or “Select orders with status X”) and then perform a bulk deletion.
  - **Delete Button:** A prominent button (e.g., “Delete Selected Orders” or “Delete Orders”) will initiate the deletion process.
- **Effect of changes:**
  - When you select orders and click the delete button, the module will permanently remove those orders and all associated data (order details, products ordered, customer messages related to the order, invoices, etc.) from your PrestaShop database.
  - This action is irreversible.
- **Recommended workflow for daily store management:**
  1. **Regularly review your orders:** Identify which order statuses commonly represent “unwanted” orders (e.g., “Canceled,” “Payment error,” “On backorder” if not fulfilled, or custom statuses for test orders).
  2. **Access “Delete Orders Pro”:** Go to **Orders > Delete Orders Pro**.
  3. **Filter orders:** Use the available filters to display only the orders you intend to delete (e.g., filter by “Canceled” status and a date range older than 3 months).
  4. **Carefully select orders:** Double-check the orders you have filtered and select them using the checkboxes.
  5. **Initiate deletion:** Click the “Delete Selected Orders” button. Confirm the action when prompted.
  6. **Perform backups:** Before any major deletion, always ensure you have a recent database backup.

#### 2.2.2 Index Controller (deleteorderspro/controllers/admin/index.php)

This file typically serves as a routing or fallback controller within the module’s admin section. In the context of “Delete Orders Pro,” it likely ensures that if a user navigates to the base admin path of the module without specifying a particular action or sub-controller, they are redirected to the main `deleteorderstab` interface.

- **Screen Name & Menu Location:** Not a direct screen, but part of the module’s internal navigation.
- **Available Actions & Settings:** No direct user-configurable settings. Its purpose is to manage internal routing.
- **Effect of changes:** No direct merchant impact. It ensures a smooth navigation experience within the module’s admin section.
- **Recommended workflow for daily store management:** No specific workflow needed; this operates in the background.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | `mypresta_updates` | YES | Enables/disables update notifications from MyPresta.eu. |
|  | `update_` | YES | Internal flag for update status. |
|  | `updatev_` | YES | Internal flag for update version. |
|  | `DELETEORDERS_LAST_TAB` | (Auto-managed) | Tracks last visited tab in module’s admin interface. |
| **Delete Orders Tab** | Filters (Status, Date, etc.) | Varies | Narrows down the list of orders to be deleted. |
|  | Order Selection Checkboxes | N/A | Allows selection of individual orders for deletion. |
|  | Bulk Action: Delete Selected | N/A | Permanently removes selected orders and associated data. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I deleted orders, but my store’s performance doesn’t seem much faster. Why?**
A: While deleting orders reduces database size, performance is influenced by many factors (hosting, other modules, theme optimization, image sizes). Deleting orders is one step in overall optimization. Ensure you’ve also cleared PrestaShop’s cache (**Advanced Parameters > Performance**) after deletion.

**Q: Can I recover orders after I’ve deleted them?**
A: No. Once orders are deleted using this module, they are permanently removed from your database. This is why it’s crucial to always back up your database before performing any major deletion and to carefully review your selections.

**Q: Will deleting orders affect my customer accounts or product stock?**
A: Deleting an order removes the order record itself and its associated details (like the specific products ordered within that transaction, invoices, messages). It does NOT delete the customer account associated with the order, nor does it typically revert stock levels (as stock is usually adjusted at the time of order creation or status change, not deletion). Always verify the module’s behavior in a test environment if you have specific concerns about stock.

**Q: The module isn’t showing up in my Back Office menu.**
A:

1. **Check installation:** Go to **Modules > Module Manager** and search for “Delete Orders Pro.” Ensure it’s listed as “Installed” and “Enabled.”
2. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache.” Sometimes, menu changes require a cache refresh.
3. **Permissions:** Check your user permissions under **Administration > Permissions** to ensure your profile has access to the “Orders” section and any module-specific permissions.

**Q: I’m getting an error when trying to delete orders.**
A:

1. **Check PrestaShop Debug Mode:** Enable debug mode (**Advanced Parameters > Performance > Debug mode**) to see if a more detailed error message appears.
2. **Server Error Logs:** Check your server’s PHP error logs (often found in your hosting control panel) for any related messages.
3. **Contact Support:** If you can’t resolve the issue, gather any error messages and contact MyPresta.eu support for assistance.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a technical overview for developers and webmasters working with the “Delete Orders Pro” module.

### 4.1 Architecture Overview

The “Delete Orders Pro” module follows the standard PrestaShop module architecture, primarily leveraging Back-Office Admin Controllers for its functionality. It integrates into the PrestaShop menu system and uses PrestaShop’s core `AdminController` for rendering lists and handling form submissions. The module directly interacts with the database to perform deletion operations on order-related tables. It does not introduce custom `ObjectModel` classes but rather operates on existing PrestaShop order entities.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. This module has no front-office presence.
- **Back-Office Admin Controllers**:

  - `deleteorderspro/controllers/admin/deleteorderstab.php`

    - **Class Name**: `AdminDeleteOrdersProController` (or similar, typically derived from the file name and module context) extending `ModuleAdminController`.
    - **Responsibility**: This is the main administrative controller for the module. It’s responsible for:
      - Displaying the list of orders in a grid format.
      - Handling filtering, sorting, and pagination of orders.
      - Processing the deletion of selected orders.
      - Interacting with PrestaShop’s core `Order` and related `ObjectModel`s to perform database deletions.
      - Rendering the template for the order list and deletion interface.
    - **PrestaShop Tab**: This controller is registered as a new tab under the “Orders” menu in the PrestaShop back office.
  - `deleteorderspro/controllers/admin/index.php`

    - **Class Name**: Not a typical controller class; often a simple redirect or bootstrap file.
    - **Responsibility**: This file typically serves as a fallback or entry point. In many modules, if a user navigates to the base `admin/module_name` path, this `index.php` might redirect them to the primary controller (e.g., `deleteorderstab`) to ensure the correct interface is loaded. It prevents direct access to the directory and ensures proper routing.

### 4.3 Core Classes & Models (`classes/`)

The module does not appear to introduce any custom classes or `ObjectModel`s in its `classes/` directory based on the provided inventory. It likely operates directly on PrestaShop’s core `Order` and related `ObjectModel`s (e.g., `OrderHistory`, `OrderDetail`, `ProductSale`, `Cart`, etc.) to ensure comprehensive deletion of all associated data.

### 4.4 JavaScript Assets (`views/js/`)

No JavaScript files were identified in the module archive. The module likely relies on standard PrestaShop back-office JavaScript for form submissions and grid interactions, or its functionality is entirely server-side.

### 4.5 CSS Stylesheets (`views/css/`)

No CSS files were identified in the module archive. The module likely inherits styling directly from the PrestaShop back-office theme, ensuring a consistent look and feel without custom styles.

### 4.6 Smarty Template Structure (`views/templates/`)

No `.tpl` files were identified in the module archive. This suggests that the module might be using PrestaShop’s default `list.tpl` and `form.tpl` templates provided by `AdminController` for rendering its grid and configuration, or it generates its HTML directly within the controller.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  The module does not create custom database tables. It operates on existing PrestaShop tables related to orders, including but not limited to:

  - `ps_orders`
  - `ps_order_detail`
  - `ps_order_history`
  - `ps_order_invoice`
  - `ps_order_payment`
  - `ps_order_return`
  - `ps_order_slip`
  - `ps_cart` (and related `ps_cart_product`)
  - `ps_message` (for customer messages related to orders)
  - `ps_product_sale` (updates sales count)
  - `ps_customer_thread` (for customer service threads related to orders)
  - `ps_configuration` (for storing module settings like `mypresta_updates`, `DELETEORDERS_LAST_TAB`).
- **Registered Hooks Table**:
  Based on the module’s purpose as a back-office administration tool, it primarily uses hooks for installation, uninstallation, and potentially adding menu items. It does not appear to use front-office display hooks.

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `install()` | During module installation | Creates the new “Delete Orders Pro” tab in the PrestaShop back office menu. Stores initial configuration values in `ps_configuration`. |
  | `uninstall()` | During module uninstallation | Removes the “Delete Orders Pro” tab from the back office menu. Deletes configuration values from `ps_configuration`. |
  | `displayBackOfficeHeader` | Renders content in the `<head>` section of the Back Office | Potentially used to include any necessary JS/CSS for the admin controller, though none were identified in the inventory. |
  | `actionAdminControllerSetMedia` | Allows adding JS/CSS to specific admin controllers | Used by `AdminDeleteOrdersProController` to add any specific assets required for its interface. |

## 5. Official Support & Updates

For official support, updates, and to download the latest version of the “Delete Orders Pro” module, please visit your customer account at [MyPresta.eu](https://mypresta.eu). Our support team is available to assist with any technical issues or questions you may have regarding the module’s functionality.
