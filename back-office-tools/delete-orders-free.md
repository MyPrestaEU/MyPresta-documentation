---
title: "Delete Orders Free - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Delete Orders Free PrestaShop module by MyPresta.eu."
sidebar:
  label: "Delete Orders Free - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Delete Orders Free Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/delete-orders-free.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/delete-orders-free/)
>
> ---


# Delete Orders Free

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient and usually enabled by default on most hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” will take you to the module’s main configuration page. This page primarily handles update notifications for the module itself.

- **What this setting does:** This section manages the module’s ability to check for updates and display notifications.
- **Effect of changing this setting:**
  - *When enabled:* The module will periodically check MyPresta.eu for newer versions. If an update is available, a notification might appear in your PrestaShop back office, prompting you to download and install the latest version. This ensures you always have the most secure and feature-rich version of the module.
  - *When disabled:* The module will not check for updates automatically. You would need to manually visit MyPresta.eu to check for new versions. While this might slightly reduce server requests, it means you could miss important updates or bug fixes.
- **Recommended value:** **Enabled (YES)**. Keeping this enabled ensures you are always informed about the latest improvements and security patches for the module.
- **Merchant scenario / example:** You want to be notified if a new version of “Delete Orders Free” is released that fixes a bug or adds a new feature. Keeping this enabled ensures you’ll see a notification in your PrestaShop admin panel.

### 2.2 Dedicated Admin Screens & Controller Views

#### 2.2.1 Delete Orders Tab (Back Office > Orders > Delete Orders)

This is the primary interface for the module’s functionality.

- **Screen Name & Menu Location:** You can access this screen by navigating to **Orders > Delete Orders** in your PrestaShop back office menu.
- **Available Actions & Settings:**
  - Upon entering this tab, you will see a list of all orders in your PrestaShop store, similar to the standard “Orders” list.
  - Each order in the list will have a dedicated **“Delete”** button or icon (often a trash can icon) next to it.
  - **Deleting an order:** Clicking the “Delete” button next to any order will immediately and permanently remove that order from your database. This action is irreversible.
- **Effect of changes:**
  - When you click “Delete” for an order, the order record, along with all associated data (such as order details, customer messages related to that order, invoices, and potentially stock movements if the order status was configured to affect stock) will be removed from your PrestaShop database.
  - The order will no longer appear in your “Orders” list, nor will it be included in any sales reports or statistics.
- **Recommended workflow for daily store management:**
  1. Regularly review your “Orders” list for test orders, fraudulent orders, or orders that were completely canceled and no longer need to be tracked.
  2. Navigate to **Orders > Delete Orders**.
  3. Carefully identify the orders you wish to remove.
  4. Click the “Delete” button next to each specific order you want to remove.
  5. Confirm the deletion if prompted.
  6. **Important:** Exercise extreme caution as this action is permanent and cannot be undone. It is highly recommended to perform a database backup before deleting a large number of orders.

#### 2.2.2 Index.php (deleteordersfree/controllers/admin/index.php)

This file is a standard PrestaShop controller placeholder and typically doesn’t present a direct, configurable screen to the merchant. Its purpose is usually to redirect to the main module configuration or a specific admin tab. In this module’s context, it likely ensures that navigating to the module’s base admin path correctly directs you to the `deleteorderstab` controller.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration Page** | Update Check (mypresta\_updates) | Enabled (YES) | Controls whether the module checks for new versions and notifies you. Keep enabled for updates. |
| **Orders > Delete Orders** | Delete Button (per order) | N/A | Permanently removes a selected order and its associated data from the database. **Irreversible action.** |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I deleted an order by mistake! Can I get it back?**
A: Unfortunately, no. The “Delete Orders Free” module performs a permanent deletion. This is why we emphasize caution. Always have a recent backup of your database, especially before performing bulk deletions. If you have a backup, you might be able to restore your entire database to a previous state, but this would also revert all other changes made since the backup.

**Q: I don’t see the “Delete Orders” tab under the “Orders” menu.**
A:

1. **Check Module Installation:** Go to **Modules > Module Manager** and search for “Delete Orders Free”. Ensure it is installed and enabled.
2. **Clear Cache:** Sometimes, PrestaShop’s menu cache needs to be refreshed. Go to **Advanced Parameters > Performance**, scroll down to “Clear cache” and click “Clear cache”.
3. **Check Permissions:** Ensure your user profile has the necessary permissions to access and manage modules and orders. Go to **Advanced Parameters > Team > Profiles**, select your profile, then go to **Permissions > Modules** and **Permissions > Orders** to verify.

**Q: Will deleting an order also refund the customer or cancel the payment?**
A: No. This module only removes the order record from your PrestaShop database. It does NOT interact with payment gateways (like PayPal, Stripe, etc.) to issue refunds or cancel transactions. You must handle any payment reversals or refunds directly through your payment gateway’s interface.

**Q: Does deleting an order affect product stock?**
A: If your PrestaShop configuration for order statuses is set to decrement stock when an order is placed, and you delete an order, the stock will NOT be automatically re-incremented. You would need to manually adjust the stock for the affected products if you wish to put them back into inventory. This is a critical point to remember for inventory management.

**Q: The module is installed, but I don’t see any “Delete” buttons on the order list.**
A: Ensure you are on the dedicated **Orders > Delete Orders** tab, not the standard **Orders > Orders** list. The delete functionality is specifically added to the module’s custom tab.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Delete Orders Free” module is a straightforward PrestaShop module primarily focused on extending the Back Office functionality. It follows a standard PrestaShop MVC pattern for its administrative interface. The core logic resides in the main module file for installation/uninstallation and in a dedicated AdminController for managing the order deletion process. It does not introduce new database tables or complex front-office interactions.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. This module has no front-office presence.
- **Back-Office Admin Controllers**:

  - `deleteordersfree/controllers/admin/deleteorderstab.php`
    - **Class name & parent class**: `DeleteOrdersTabController` extends `ModuleAdminController`.
    - **Responsibility**: This is the main controller for the module’s functionality. It renders the list of orders in the Back Office, providing the “Delete” action for each order. It handles the logic for receiving the delete request (e.g., via GET parameter or POST submission) and then executing the database deletion for the specified order ID. This controller likely overrides or extends methods from `AdminController` to display the order list and add the custom action.
  - `deleteordersfree/controllers/admin/index.php`
    - **Class name & parent class**: This is typically a placeholder file that ensures proper routing within the admin section. It usually contains a simple `header('Location: ...')` redirect or an empty file to prevent directory listing. In PrestaShop, `index.php` files in subdirectories of `controllers/admin` are often used to define the entry point for a specific section or to prevent direct access. For this module, it likely ensures that accessing the base `admin/deleteordersfree` path correctly directs to the `deleteorderstab` controller.

### 4.3 Core Classes & Models (`classes/`)

This module does not introduce any custom classes or `ObjectModel` definitions. It directly interacts with PrestaShop’s core `Order` and related `ObjectModel` classes (e.g., `OrderInvoice`, `OrderPayment`, `OrderHistory`, `Message`, `Cart`, `CustomerThread`, `SpecificPrice`, `StockAvailable`) to perform deletions.

### 4.4 JavaScript Assets (`views/js/`)

No custom JavaScript files are included in this module. The deletion action is likely handled via a standard form submission or a simple GET request with a confirmation prompt.

### 4.5 CSS Stylesheets (`views/css/`)

No custom CSS files are included in this module. The module relies on PrestaShop’s default Back Office styling for its interface.

### 4.6 Smarty Template Structure (`views/templates/`)

No custom Smarty template files are explicitly listed in the module inventory. The `deleteorderstab` controller likely uses PrestaShop’s default `list.tpl` or similar templates for rendering the order grid, injecting the “Delete” action through controller logic (e.g., `renderList()` method).

### 4.7 Database Schema & Hooks Map

- **Database Tables**: This module does not create any new custom database tables. It operates directly on existing PrestaShop core tables related to orders, such as:

  - `ps_orders`
  - `ps_order_detail`
  - `ps_order_history`
  - `ps_order_invoice`
  - `ps_order_payment`
  - `ps_message` (for messages related to the order)
  - `ps_cart` (the cart associated with the order)
  - `ps_customer_thread` (customer service threads related to the order)
  - `ps_specific_price` (if specific prices were applied via the order)
  - `ps_stock_available` (if stock was decremented by the order)
  - And potentially other related tables (e.g., `ps_order_carrier`, `ps_order_slip`).
    It also stores its configuration settings (like `mypresta_updates`) in the `ps_configuration` table.
- **Registered Hooks Table**:
  The module description mentions “Front-Office Hooks: Header, Columns, Product, or Footer” but the module’s functionality is purely back-office. This suggests that these hooks are either not actively used by the module’s core logic or are remnants from a generic module template. Based on the module’s stated purpose and file inventory, it’s highly unlikely to render anything in these front-office hooks.

  The primary hook usage for this module is likely:

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `actionAdminControllerSetMedia` | Executed when an AdminController is initialized and before its content is rendered. | Potentially used to add custom JS/CSS (though none are listed) or to register specific module-related assets for the admin page. |
  | `displayBackOfficeHeader` | Executed in the header of every Back Office page. | Could be used for update notifications or to inject minor admin-specific scripts/styles. |
  | `actionModuleInstall` | Executed when the module is installed. | Creates the “Delete Orders” tab in the Back Office menu and sets default configuration values. |
  | `actionModuleUninstall` | Executed when the module is uninstalled. | Removes the “Delete Orders” tab and cleans up configuration values. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Delete Orders Free” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist merchants and developers with any issues or questions related to the module’s functionality.
