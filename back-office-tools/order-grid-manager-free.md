---
title: "Order Grid Manager Free - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Order Grid Manager Free PrestaShop module by MyPresta.eu."
sidebar:
  label: "Order Grid Manager Free - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Order Grid Manager Free Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-grid-manager-free.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/order-grid-manager-free/)
>
> ---


# Order Grid Manager Free

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) typically included with any modern web hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” will take you to the module’s main settings page. Here, you’ll find a list of all the columns that appear on your PrestaShop Back Office orders list. Each column has a simple ON/OFF switch.

**Screen Name & Menu Location:**

- **Menu Path:** Back Office > Modules > Module Manager > Order Grid Manager Free > Configure

**Available Settings:**
You will see a list of checkboxes or switches, each corresponding to a column in your Back Office Orders list. The exact list of columns may vary slightly depending on your PrestaShop version and other installed modules, but common examples include:

- **ID:** The unique identifier for each order.

  - **What this setting does:** Controls whether the “ID” column is visible in your orders list.
  - **Effect of changing this setting:**
    - *When enabled:* The “ID” column will be displayed.
    - *When disabled:* The “ID” column will be hidden.
  - **Recommended value:** YES (Often useful for quick reference and support).
  - **Merchant scenario / example:** If you frequently reference orders by their unique ID when communicating with customers or your warehouse, keep this enabled. If you primarily use other identifiers like customer name or reference, you might hide it.
- **Reference:** The internal reference number for the order.

  - **What this setting does:** Controls the visibility of the “Reference” column.
  - **Effect of changing this setting:**
    - *When enabled:* The “Reference” column will be displayed.
    - *When disabled:* The “Reference” column will be hidden.
  - **Recommended value:** YES (Crucial for tracking and internal communication).
  - **Merchant scenario / example:** Most merchants use the order reference for packaging slips, invoices, and customer service. Keep this visible unless you have a very specific workflow that doesn’t use it.
- **New client:** Indicates if the order is from a new customer.

  - **What this setting does:** Controls the visibility of the “New client” column.
  - **Effect of changing this setting:**
    - *When enabled:* The “New client” column will be displayed.
    - *When disabled:* The “New client” column will be hidden.
  - **Recommended value:** NO (Unless you specifically target new customer data in your daily workflow).
  - **Merchant scenario / example:** If your marketing team frequently reviews orders to identify new customer acquisition trends, you might keep this visible. Otherwise, it’s often a good candidate to hide for a cleaner view.
- **Customer:** The name of the customer who placed the order.

  - **What this setting does:** Controls the visibility of the “Customer” column.
  - **Effect of changing this setting:**
    - *When enabled:* The “Customer” column will be displayed.
    - *When disabled:* The “Customer” column will be hidden.
  - **Recommended value:** YES (Almost always essential for order identification).
  - **Merchant scenario / example:** You almost certainly need to see who placed the order. Keep this enabled.
- **Total:** The total amount of the order.

  - **What this setting does:** Controls the visibility of the “Total” column.
  - **Effect of changing this setting:**
    - *When enabled:* The “Total” column will be displayed.
    - *When disabled:* The “Total” column will be hidden.
  - **Recommended value:** YES (Important for financial overview).
  - **Merchant scenario / example:** Essential for quickly seeing the value of each order. Keep this enabled.
- **Payment:** The payment method used for the order.

  - **What this setting does:** Controls the visibility of the “Payment” column.
  - **Effect of changing this setting:**
    - *When enabled:* The “Payment” column will be displayed.
    - *When disabled:* The “Payment” column will be hidden.
  - **Recommended value:** YES (Useful for payment reconciliation).
  - **Merchant scenario / example:** If you need to quickly see if an order was paid via credit card, PayPal, or bank transfer, keep this enabled.
- **Status:** The current status of the order (e.g., Payment accepted, Shipped, Delivered).

  - **What this setting does:** Controls the visibility of the “Status” column.
  - **Effect of changing this setting:**
    - *When enabled:* The “Status” column will be displayed.
    - *When disabled:* The “Status” column will be hidden.
  - **Recommended value:** YES (Critical for tracking order progress).
  - **Merchant scenario / example:** Absolutely essential for managing order fulfillment. Keep this enabled.
- **Date:** The date and time the order was placed.

  - **What this setting does:** Controls the visibility of the “Date” column.
  - **Effect of changing this setting:**
    - *When enabled:* The “Date” column will be displayed.
    - *When disabled:* The “Date” column will be hidden.
  - **Recommended value:** YES (Important for chronological order and aging).
  - **Merchant scenario / example:** Useful for sorting orders by when they were placed or identifying older orders that need attention. Keep this enabled.
- **Invoice:** Link to view/download the invoice.

  - **What this setting does:** Controls the visibility of the “Invoice” column.
  - **Effect of changing this setting:**
    - *When enabled:* The “Invoice” column will be displayed.
    - *When disabled:* The “Invoice” column will be hidden.
  - **Recommended value:** YES (Convenient for quick access to invoices).
  - **Merchant scenario / example:** If your team frequently needs to download or view invoices directly from the orders list, keep this enabled.
- **Delivery:** Link to view/download the delivery slip.

  - **What this setting does:** Controls the visibility of the “Delivery” column.
  - **Effect of changing this setting:**
    - *When enabled:* The “Delivery” column will be displayed.
    - *When disabled:* The “Delivery” column will be hidden.
  - **Recommended value:** YES (Convenient for quick access to delivery slips).
  - **Merchant scenario / example:** If your warehouse or shipping team uses delivery slips, keeping this visible provides quick access.
- **Actions:** Buttons for viewing, editing, or deleting the order.

  - **What this setting does:** Controls the visibility of the “Actions” column.
  - **Effect of changing this setting:**
    - *When enabled:* The “Actions” column will be displayed.
    - *When disabled:* The “Actions” column will be hidden.
  - **Recommended value:** YES (Essential for managing individual orders).
  - **Merchant scenario / example:** You will almost always need to view or edit an order. Keep this enabled.

**Saving Your Changes:**
After you’ve made your selections, remember to click the **“Save”** button (usually at the bottom of the configuration page) to apply your changes. Once saved, navigate to **Orders > Orders** in your Back Office to see the updated column layout.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | ID | YES | Shows/hides the unique order ID. |
| Module Configuration | Reference | YES | Shows/hides the internal order reference. |
| Module Configuration | New client | NO | Shows/hides indicator for new customers. |
| Module Configuration | Customer | YES | Shows/hides the customer’s name. |
| Module Configuration | Total | YES | Shows/hides the total order amount. |
| Module Configuration | Payment | YES | Shows/hides the payment method used. |
| Module Configuration | Status | YES | Shows/hides the current order status. |
| Module Configuration | Date | YES | Shows/hides the order placement date. |
| Module Configuration | Invoice | YES | Shows/hides the invoice download link. |
| Module Configuration | Delivery | YES | Shows/hides the delivery slip download link. |
| Module Configuration | Actions | YES | Shows/hides the action buttons (view, edit, delete). |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve configured the module, but the order grid hasn’t changed.**
A: After saving your changes in the module configuration, you might need to clear your PrestaShop cache. Go to **Advanced Parameters > Performance**, and click “Clear cache” in the top right corner. Also, try refreshing your browser page (Ctrl+F5 or Cmd+R) to ensure you’re not seeing a cached version of the Back Office.

**Q: Can I have different column views for different admin users?**
A: The “Order Grid Manager Free” module applies a single, universal setting for all administrators. It does not support individual user preferences for column visibility. If you need this advanced functionality, you might need to look for a premium module or custom development.

**Q: Will this module affect my store’s performance?**
A: No, this module has a negligible impact on performance. It only changes which columns are displayed in the Back Office orders list, which is a client-side (browser) rendering adjustment based on a simple configuration. It does not alter database queries or front-office loading times.

**Q: What if I accidentally hide a column I need?**
A: No problem! Simply go back to **Modules > Module Manager > Order Grid Manager Free > Configure**, re-enable the desired column by checking its box, and save your changes. Then clear your cache and refresh your browser.

**Q: Does this module support multi-language translations for column names?**
A: The module itself does not introduce new translatable strings for column names. It simply controls the visibility of existing PrestaShop column names, which are already handled by PrestaShop’s core translation system.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a technical overview for developers and webmasters looking to understand, debug, or extend the “Order Grid Manager Free” module.

### 4.1 Architecture Overview

The `Order Grid Manager Free` module is a straightforward PrestaShop module primarily designed to modify the display of the `AdminOrders` list. It leverages PrestaShop’s configuration system to store user preferences for column visibility and injects JavaScript to dynamically hide/show columns based on these settings. It follows a basic PrestaShop module structure, with its core logic residing in the main module file.

### 4.2 Controllers (`controllers/`)

This module does not utilize custom Front-Office or Back-Office controllers. All configuration and logic are handled within the main module class and its `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or `ObjectModel` instances. It operates directly on PrestaShop’s core configuration and existing Back Office structures.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include any dedicated JavaScript files in `views/js/`. The logic for hiding/showing columns is likely injected directly into the Back Office via a hook or within the `getContent()` method’s template, using inline JavaScript or a simple CSS injection. Given the module’s simplicity and “Free” designation, it’s highly probable that the column hiding is achieved by adding CSS `display: none;` rules or by manipulating the DOM directly after the page loads, based on the stored configuration.

### 4.5 CSS Stylesheets (`views/css/`)

This module does not include any dedicated CSS files in `views/css/`. Similar to JavaScript, any styling (primarily `display: none;` for columns) is likely injected inline or dynamically generated based on configuration.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`myordergridfree/views/templates/admin/advert.tpl`**:
  - **Scope:** Back-office (Admin configuration page).
  - **Purpose:** This template is likely used to display an advertisement or promotional message within the module’s configuration page in the Back Office. It’s a common practice for free modules to include such elements. It does not directly control the order grid functionality but is part of the module’s `getContent()` output.

The actual configuration form for column visibility is likely rendered directly within the `getContent()` method of the main module file, possibly using PrestaShop’s `HelperForm` or custom HTML, and then the `advert.tpl` is included for promotional content.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create any custom SQL tables.
  - It stores its configuration settings in the standard PrestaShop `ps_configuration` table. Each setting (e.g., `MYORDERGRIDFREE_HIDE_ID_COLUMN`) will correspond to a row in this table, storing a boolean value (0 or 1) for visibility.
- **Registered Hooks Table**:
  This module’s primary functionality relies on modifying the Back Office display. Given the “Free” version’s simplicity, it likely uses one or more of the following approaches:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayBackOfficeHeader` | Executed in the `<head>` section of Back Office pages. | Most probable hook for injecting inline CSS or JavaScript to hide columns on the `AdminOrders` page. This allows the module to apply `display: none;` to specific `<th>` and `<td>` elements based on the saved configuration. |
| `actionAdminControllerSetMedia` | Executed when an Admin controller sets its media assets. | Could be used to register a small JS file or inline script that runs specifically on the `AdminOrders` controller to manipulate the DOM. |
| `displayAdminOrderListBefore` / `displayAdminOrderListAfter` | Before/After the order list table is rendered. | Less likely for this module, as it modifies the list itself, not just adds content around it. |

The module’s `install()` method would register these hooks, and the `hookDisplayBackOfficeHeader()` (or similar) method would contain the logic to retrieve the stored configuration and output the necessary CSS/JS to hide the selected columns when the `AdminOrders` page is loaded.

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Order Grid Manager Free” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality.
