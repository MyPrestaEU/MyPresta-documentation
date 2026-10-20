---
title: "Quick Order Preview - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Quick Order Preview PrestaShop module by MyPresta.eu."
sidebar:
  label: "Quick Order Preview - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Quick Order Preview Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/quick-order-preview.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/quick-order-preview/)
>
> ---


# Quick Order Preview

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 9.x, 8.x, 1.7.7.x - 1.7.8.x, 1.7.0.0 - 1.7.6.x, 1.6.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Quick Order Preview” module. This will take you to its main configuration screen.

There are no specific configuration options on this screen for the “Quick Order Preview” module. The module works out-of-the-box by enhancing the existing “Orders” page functionality. Its primary function is to inject the necessary JavaScript and templates to enable the quick preview feature directly into your order list.

### 2.2 Dedicated Admin Screens & Controller Views

#### AdminPreviewOrderController (Back Office > Orders > Orders List)

This module does not add a new menu item to your PrestaShop back office. Instead, it enhances the existing **“Orders”** list page (found under **Back Office > Orders > Orders**).

- **Screen Name & Menu Location:** You access this enhanced functionality by navigating to **Orders > Orders** in your PrestaShop back office.
- **Available Actions & Settings:**
  - **Quick Preview Functionality:** When you are on the “Orders” list page, simply click on any order row. Instead of being redirected to the full order details page, the module will expand the order row to display key information directly below it. This includes:
    - **Customer Address:** Billing and shipping addresses.
    - **Products Ordered:** A list of items purchased, including quantities and prices.
    - **Customer Note:** If the customer left a note during checkout, it will be visible here.
  - **“View Order” Button:** Within the expanded preview, you will still find a “View Order” button (or similar link) that allows you to navigate to the full, traditional order details page if you need to perform actions like changing order status, adding products, or generating invoices.
  - **Customer Note Saving:** The module also includes functionality to save customer notes directly from this quick preview. This is managed by the `save-customer-note.js` script.
- **Effect of changes:**
  - Clicking an order row now toggles the display of its detailed information directly on the orders list page.
  - You can quickly review essential order data without leaving the main list, significantly speeding up your order processing workflow.
  - The ability to save customer notes directly from the preview streamlines communication and record-keeping.
- **Recommended workflow for daily store management:**
  1. Go to **Orders > Orders**.
  2. To quickly check what a customer ordered or their shipping address, simply click on the order row in the list.
  3. The details will expand below the order. Review the information.
  4. If you need to change the order status, print an invoice, or perform other advanced actions, click the “View Order” button within the expanded preview to go to the full order details page.
  5. If you need to add a quick note about the customer or order, use the customer note field within the preview and save it.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Orders List | Click Order Row | N/A | Expands order details (products, addresses, notes) directly on the list page, saving navigation time. |
| Orders List | Customer Note Field | N/A | Allows saving notes directly from the quick preview. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: The order details don’t expand when I click on an order row. What’s wrong?**
A:

1. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” in the top right. Sometimes, old cache files prevent new module scripts from loading.
2. **Module Enabled:** Ensure the “Quick Order Preview” module is enabled in **Modules > Module Manager**.
3. **Theme Compatibility:** While the module is designed to be compatible, very heavily customized themes might sometimes interfere. Check your browser’s developer console (F12) for JavaScript errors. If you see errors related to the module, contact MyPresta.eu support.
4. **PrestaShop Version:** Ensure you downloaded and installed the correct module version for your specific PrestaShop installation.

**Q: Can I customize what information is shown in the quick preview?**
A: The module displays essential information like products and addresses. Customizing the displayed fields would require direct modification of the module’s template files (`address.tpl`, `products.tpl`). This is a developer-level task.

**Q: Does this module affect my store’s performance?**
A: No, the module is designed to be lightweight. It only loads additional content when you explicitly click on an order row in the back office. It does not add any overhead to your front office or general back office browsing.

**Q: I’m using an older PrestaShop 1.6 version, will this work?**
A: Yes, the module is compatible with PrestaShop 1.6.x. Ensure you download the correct package for your PrestaShop version from your MyPresta.eu account.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Quick Order Preview” module (`qov`) is primarily a Back Office enhancement module. It leverages PrestaShop’s `AdminController` override mechanism and Smarty templating to inject dynamic content into the existing “Orders” list. It uses JavaScript to handle the AJAX requests and DOM manipulation for expanding/collapsing order details. The module does not introduce new database tables or complex `ObjectModel` structures, focusing instead on augmenting existing PrestaShop functionality.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. This module is purely a Back Office tool.
- **Back-Office Admin Controllers**:

  - `qov/controllers/admin/AdminPreviewOrder.php`
    - **Class Name & Parent Class**: `AdminPreviewOrderController` extends `AdminOrdersController`.
    - **Responsibility**: This controller overrides the default `AdminOrdersController` to inject the necessary JavaScript and potentially modify the `renderList()` method to include the quick preview functionality. It’s responsible for handling the AJAX requests that fetch the order details (products, addresses) when an order row is clicked, and rendering the `address.tpl` and `products.tpl` templates with the retrieved data. It also manages the `QOV_TRACKING_EMAIL` configuration key, although its direct use is not evident from the provided information.

### 4.3 Core Classes & Models (`classes/`)

None. The module does not define custom `ObjectModel` classes or complex business logic classes. It primarily interacts with existing PrestaShop core classes like `Order`, `Address`, `Product`, etc., through its controller.

### 4.4 JavaScript Assets (`views/js/`)

- `qov/views/js/177-expand-all-imm.js`

  - **Scope**: Back-office (Orders list, PrestaShop 1.7.7+).
  - **Description**: This script likely handles the immediate expansion of all order details on the orders list page, possibly for a specific view or action. It would bind click events to order rows and trigger AJAX calls to fetch and display details for multiple orders simultaneously.
- `qov/views/js/177-expand-all.js`

  - **Scope**: Back-office (Orders list, PrestaShop 1.7.7+).
  - **Description**: Similar to `177-expand-all-imm.js`, this script is responsible for the “expand all” functionality. It would listen for a specific trigger (e.g., a button click) to expand all visible order details on the current page, making AJAX requests for each order.
- `qov/views/js/177orders-multiple.js`

  - **Scope**: Back-office (Orders list, PrestaShop 1.7.7+).
  - **Description**: This is the core script enabling the quick preview functionality. It binds click events to individual order rows in the `AdminOrders` list. When an order row is clicked, it prevents the default navigation to the full order page. Instead, it makes an AJAX request to the `AdminPreviewOrderController` (or a similar endpoint) to fetch the order’s products, addresses, and other details. It then dynamically injects the rendered HTML (from `address.tpl` and `products.tpl`) into a new row or an expanded section below the clicked order row. It also handles the collapsing of the details when the row is clicked again.
- `qov/views/js/save-customer-note.js`

  - **Scope**: Back-office (Orders list, specifically within the quick preview).
  - **Description**: This script handles the functionality for saving customer notes directly from the quick order preview. It binds to input fields or buttons within the expanded order details. When a note is entered or updated, it sends an AJAX request to a back-office endpoint (likely the `AdminPreviewOrderController` or the default `AdminOrdersController` with a specific action) to persist the note in the database, typically in the `ps_order_note` table or similar.

### 4.5 CSS Stylesheets (`views/css/`)

None. The module does not include custom CSS files. It likely relies on existing PrestaShop back-office styling or inline styles for the expanded order details. Developers looking to style the preview should target the dynamically injected HTML elements.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Admin templates (`views/templates/admin/`)**:
  - `qov/views/templates/admin/address.tpl`
    - **Description**: This template is used to render the customer’s billing and shipping address details within the quick order preview. It receives address data from the `AdminPreviewOrderController` and formats it for display.
  - `qov/views/templates/admin/products.tpl`
    - **Description**: This template is responsible for rendering the list of products ordered by the customer within the quick order preview. It receives product data (name, quantity, price, etc.) and displays it in a clear, tabular, or list format.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any custom database tables. It reads from and potentially writes to (for customer notes) standard PrestaShop tables such as `ps_orders`, `ps_order_detail`, `ps_address`, `ps_customer`, and `ps_order_note`.
  - Configuration values are stored in `ps_configuration`, specifically `QOV_TRACKING_EMAIL`.
- **Registered Hooks Table**:
  The module does not explicitly register any front-office hooks (like `displayHeader`, `displayRightColumn`, `displayProduct`, `displayFooter`) as it is a back-office module. Its functionality is primarily injected by overriding the `AdminOrdersController` and adding JavaScript and templates to the existing Back Office “Orders” page.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Executed when an Admin Controller sets its media assets. | Used by `AdminPreviewOrderController` to enqueue its JavaScript files (`177-expand-all-imm.js`, `177-expand-all.js`, `177orders-multiple.js`, `save-customer-note.js`) for the `AdminOrders` page. |
| `displayAdminOrder` | Executed on the Admin Order page. | While not explicitly listed as a hook, the module’s core functionality is achieved by overriding `AdminOrdersController` and modifying its `renderList()` method or by injecting content via JavaScript into the existing order list. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the “Quick Order Preview” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist you with any questions or issues you may encounter.
