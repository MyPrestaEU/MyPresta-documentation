---
title: "Order created by employee - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Order created by employee PrestaShop module by MyPresta.eu."
sidebar:
  label: "Order created by employee - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Order created by employee Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-created-by-employee.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/order-created-by-employee/)
>
> ---


# Order created by employee

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) typically available on any PrestaShop-compatible hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking the “Configure” button will take you to the module’s main configuration page.

This module is designed to be extremely simple and effective, requiring minimal configuration. Upon installation, it automatically begins collecting the necessary data.

**What this screen does:**
This page serves as a confirmation that the module is installed and active. It doesn’t present any configurable settings because the module’s core functionality (logging employee-created orders) is enabled by default upon installation.

**Effect of changing this setting:**
There are no settings to change on this screen. The module’s functionality is “always on” once installed.

**Recommended value:**
No values to set. Simply ensure the module is installed and enabled.

**Merchant scenario / example:**
You’ve just installed the module. You navigate to its configuration page and see a simple message confirming its status. From this point forward, every new order created by an employee through the PrestaShop Back Office will be marked as such. When you view an order’s details, you will see a new section indicating if it was created by an employee and which employee did it.

### 2.2 Dedicated Admin Screens & Controller Views

This module does not add new dedicated menu items or complex admin screens. Its functionality integrates directly into the existing PrestaShop order detail page.

**Screen Name & Menu Location:**
The information provided by this module is displayed directly on the **Order Details Page**.
To access it:

1. Navigate to **Orders > Orders** in your PrestaShop Back Office.
2. Click on any order from the list to view its details.

**Available Actions & Settings:**
On the Order Details Page, you will find a new section (typically near the top or in a dedicated block) that displays whether the order was created by an employee. If it was, it will also show the name of the employee who created it.

**Effect of changes:**
There are no actions or settings to change on this view. This section is purely informational, providing you with the data collected by the module.

**Recommended workflow for daily store management:**
When reviewing orders, especially those that seem unusual, or when performing internal audits, always check the “Order created by employee” section on the order details page. This quick check can provide immediate context about the origin of the order, helping you understand if it was a customer’s direct purchase or an internal entry.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | *(No configurable settings)* | N/A | Confirms module installation and activation. Module functionality is always on. |
| Order Details Page (Back Office) | “Order created by employee” information block | N/A | Displays if the order was created by an employee and their name. Purely informational. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve installed the module, but I don’t see any changes on old orders.**
A: This module starts collecting data from the moment it’s installed. It cannot retroactively determine if past orders were created by an employee. You will only see the “Order created by employee” information on orders placed *after* the module was successfully installed and active.

**Q: I created an order in the Back Office, but I don’t see the employee information on the order details page.**
A: First, ensure the module is installed and enabled (check **Modules > Module Manager**). If it is, clear your PrestaShop cache (**Advanced Parameters > Performance**). If the issue persists, ensure you are viewing an order that was *actually created by an employee* in the Back Office *after* the module’s installation.

**Q: Does this module affect my store’s performance?**
A: No, the module is very lightweight. It only adds a small piece of data during the order creation process in the Back Office and displays that data on the order details page. It has no impact on your front office performance or customer experience.

**Q: Can I disable the module’s functionality without uninstalling it?**
A: This module does not have an on/off switch in its configuration. To stop its functionality, you would need to disable or uninstall the module via the Module Manager. However, given its beneficial nature for internal tracking, it’s generally recommended to keep it active.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Order created by employee” module (`logoe`) is a straightforward PrestaShop module designed to extend the core `Order` functionality. It primarily operates by hooking into the order creation process within the Back Office to record the `id_employee` responsible for the order. This information is then displayed on the existing order detail page in the Back Office. It follows a simple event-driven pattern using PrestaShop hooks.

### 4.2 Controllers (`controllers/`)

This module does not introduce any custom front-office or back-office controllers. All its logic is handled within the main module file and through hooks.

### 4.3 Core Classes & Models (`classes/`)

This module does not introduce any custom classes or `ObjectModel` definitions. It directly interacts with the `Order` object and `Configuration` for its settings.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include any custom JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)

This module does not include any custom CSS files. Styling for the displayed information is typically minimal and relies on existing PrestaShop Back Office styles.

### 4.6 Smarty Template Structure (`views/templates/`)

This module uses a single template file for displaying information in the Back Office.

- **Admin templates (`views/templates/admin/`)**:
  - `logoe/views/templates/admin/logoelog.tpl`: This template is responsible for rendering the “Order created by employee” information block on the PrestaShop Back Office order detail page. It typically displays the employee’s name if the order was created by an employee. It’s likely rendered via a hook like `displayAdminOrder` or `displayAdminOrderTabContent`.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  The module does not create a new dedicated database table. Instead, it extends the existing `ps_orders` table by adding a new column during installation.

  - `ps_orders`: A new column, likely `id_employee_created`, is added to this table to store the ID of the employee who created the order. This column would be `INT(10) UNSIGNED` and nullable, with a default value of `NULL`.
- **Registered Hooks Table**:

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `actionOrderAdd` | After a new order is successfully added to the database. | This hook is crucial. It’s used to capture the `id_employee` from the current Back Office session and update the newly created order’s `id_employee_created` column in `ps_orders`. |
  | `displayAdminOrder` (or similar, e.g., `displayAdminOrderTabContent`, `displayAdminOrderMain`) | When the Back Office order detail page is rendered. | This hook is used to inject the `logoelog.tpl` template into the order detail page, displaying the `id_employee_created` information (e.g., employee name). |

## 5. Official Support & Updates

For official support, module updates, and any further assistance, please visit your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to providing timely support and ensuring your module functions perfectly.
