---
title: "Deffered Payment - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Deffered Payment PrestaShop module by MyPresta.eu."
sidebar:
  label: "Deffered Payment - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Deffered Payment Module on MyPresta.eu](https://mypresta.eu/modules/payment-process/deffered-payment.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/payment/deffered-payment/)
>
> ---


# Deffered Payment

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and generally sufficient for this module. No unusual extensions are needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Deffered Payment)

This is the main configuration screen where you define the core behavior of the Deffered Payment module.

- **Menu Location:** Back Office > Modules > Module Manager > Search for “Deffered Payment” > Click “Configure”

#### General Settings

| Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- |
| **Enable Deffered Payment** | YES | **What this setting does:** This is the master switch for the module.   **Effect of changing this setting:**   *When enabled:* The Deffered Payment option will be available at checkout for eligible customers.   *When disabled:* The Deffered Payment option will be hidden from all customers, regardless of other settings.   **Recommended value:** YES (to use the module).   **Merchant scenario:** Enable this when you’re ready to offer this payment method. |
| **Allowed Customer Groups** | (Select relevant groups) | **What this setting does:** Determines which customer groups can see and use the Deffered Payment option.   **Effect of changing this setting:**   *When selected:* Only customers belonging to the chosen groups will see Deffered Payment at checkout.   *When not selected:* Customers in unselected groups will not see this option.   **Recommended value:** Select specific groups (e.g., “Wholesalers”, “VIP Customers”). Avoid “All customers” unless you intend to offer deferred payment to everyone.   **Merchant scenario:** You have a “B2B Clients” group. Select only this group so only your business clients can use deferred payment. |
| **Payment Due Days** | 30 | **What this setting does:** Defines the number of days after an order is placed that the payment is due.   **Effect of changing this setting:** This value will be used to calculate the payment due date displayed to the customer and for internal tracking.   **Recommended value:** 30 (common for net-30 terms), 7, 14, 60, etc., depending on your business policy.   **Merchant scenario:** Set to 30 for “Net 30” payment terms. |
| **Minimum Order Total for Deffered Payment** | 0.00 | **What this setting does:** Sets a minimum order value (in your default currency) that an order must meet to qualify for deferred payment.   **Effect of changing this setting:**   *If order total is below this value:* Deffered Payment will not be available, even for eligible customer groups.   *If order total is above or equal to this value:* Deffered Payment will be available (if other conditions met).   **Recommended value:** 0.00 (no minimum) or a specific value (e.g., 100.00 for B2B).   **Merchant scenario:** You only want to offer deferred payment for large orders, so you set it to 500.00. |
| **Order Status for Deffered Payment** | Awaiting deferred payment | **What this setting does:** Specifies the initial order status that will be assigned to orders placed using the Deffered Payment method.   **Effect of changing this setting:** This status will be visible in your Back Office order list and to the customer in their order history. It helps you quickly identify orders awaiting payment.   **Recommended value:** Create a specific status like “Awaiting Deferred Payment” or “Payment Due” in **Order Statuses** (Back Office > Shop Parameters > Order Settings > Statuses) and select it here.   **Merchant scenario:** You want a clear status to differentiate these orders from “Awaiting bank wire payment” or “Payment accepted”. |
| **Cron Job URL** | (Displayed URL) | **What this setting does:** This URL is used to trigger automated tasks related to deferred payments (e.g., checking due dates, sending reminders, if such features are implemented or extended).   **Effect of changing this setting:** This is a read-only field. You should set up a cron job on your server to visit this URL regularly (e.g., once a day).   **Recommended value:** Copy this URL and add it to your server’s cron job scheduler.   **Merchant scenario:** You want to automate any background processes the module might have, such as updating order statuses or sending notifications. |

#### Target Products (Specific Product Eligibility)

This section allows you to restrict deferred payment to specific products or categories.

| Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- |
| **Apply to specific products only** | NO | **What this setting does:** Determines if the deferred payment option is limited to orders containing only specific products.   **Effect of changing this setting:**   *When enabled:* The “Deffered Payment” option will only appear at checkout if *all* products in the cart are on your approved list.   *When disabled:* The module will apply based on customer groups and minimum order total, regardless of specific products.   **Recommended value:** NO (for general use) or YES (for highly specific scenarios).   **Merchant scenario:** You only offer deferred payment for your high-value “Premium Services” products. You enable this and add those products below. |
| **Products allowed for deferred payment** | (Empty) | **What this setting does:** If “Apply to specific products only” is enabled, this field allows you to search for and add specific products.   **Effect of changing this setting:** Only orders containing these products (and no others) will be eligible for deferred payment.   **Recommended value:** Add relevant products if “Apply to specific products only” is YES.   **Merchant scenario:** You add “Product A” and “Product B”. If a customer’s cart contains “Product A” and “Product C”, deferred payment will not be available. If it contains only “Product A”, it will be. |

### 2.2 Dedicated Admin Screens & Controller Views

The module adds several new sections to your PrestaShop Back Office menu to manage deferred payments.

#### 2.2.1 Deferred Payment Users (Back Office > Deffered Payment > Deferred Payment Users)

This screen allows you to manage individual customer permissions for deferred payment, overriding or supplementing the customer group settings.

- **Screen Name & Menu Location:** Back Office > Deffered Payment > Deferred Payment Users
- **Available Actions & Settings:**
  - **Listing Table:** Displays a list of customers who have been specifically granted or denied deferred payment access.
  - **Add New / Edit User:**
    - **Customer Search:** Find a specific customer by name or email.
    - **Enable Deferred Payment:** YES/NO switch to grant or revoke deferred payment access for this individual customer.
    - **Payment Due Days (Override):** Optionally set a custom number of payment due days for this specific customer, overriding the global setting.
    - **Credit Limit:** Set a maximum outstanding amount (in your default currency, based on `PS_CURRENCY_DEFAULT`) that this customer can have on deferred payment orders.
  - **Effect of changes:**
    - Adding a customer and enabling deferred payment grants them access, even if their group isn’t selected in the main module config.
    - Disabling for a customer revokes their access, even if their group is selected.
    - Custom due days and credit limits apply only to that specific customer.
- **Recommended workflow for daily store management:**
  1. Use this section to grant special deferred payment terms to individual VIP clients or to block problematic customers.
  2. Regularly review credit limits for high-volume deferred payment users.

#### 2.2.2 Deferred Payment Activity Log (Back Office > Deffered Payment > Activity Log)

This screen provides a historical record of actions and events related to deferred payments.

- **Screen Name & Menu Location:** Back Office > Deffered Payment > Activity Log
- **Available Actions & Settings:**
  - **Listing Table:** Displays a log of events, which might include:
    - When a deferred payment order was placed.
    - When a payment was marked as received.
    - Changes to deferred payment user settings.
    - Cron job executions.
  - **Columns:** Typically includes Date/Time, Event Type, Related Order/Customer, Description.
- **Effect of changes:** This is a read-only log. You cannot directly change entries here, but it provides valuable insights for auditing and troubleshooting.
- **Recommended workflow for daily store management:**
  1. Periodically check the log to monitor deferred payment activity and ensure everything is running smoothly.
  2. Use it to investigate any issues reported by customers regarding their deferred payment orders.

#### 2.2.3 Dashboard (Back Office > Deffered Payment > Dashboard)

This screen (likely represented by `defpay/controllers/admin/index.php`) would typically provide an overview or summary of deferred payment activities.

- **Screen Name & Menu Location:** Back Office > Deffered Payment > Dashboard (or main “Deffered Payment” menu item)
- **Available Actions & Settings:**
  - **Grid / Management View:** This screen likely presents key statistics, pending payments, overdue payments, or a quick summary of deferred payment orders. It might offer filters or search capabilities.
- **Effect of changes:** This is primarily an informational dashboard. Any actions taken (e.g., marking an order as paid) would typically redirect to the specific order page or another management screen.
- **Recommended workflow for daily store management:**
  1. Use this as your primary overview to quickly identify orders requiring attention (e.g., approaching due dates, overdue payments).
  2. Monitor the overall health of your deferred payment system.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|
| **Module Configuration** | Enable Deffered Payment | YES | Master switch for the payment method. |
| | Allowed Customer Groups | (Select relevant groups) | Restricts access to specific customer segments. |
| | Payment Due Days | 30 | Sets the default payment term in days. |
| | Minimum Order Total for Deffered Payment | 0.00 | Minimum cart value for deferred payment eligibility. |
| | Order Status for Deffered Payment | Awaiting deferred payment | Initial status for orders placed with this method. |
| | Cron Job URL | (Displayed URL) | URL for server-side automation tasks. |
| | Apply to specific products only | NO | Limits deferred payment to specific products. |
| | Products allowed for deferred payment | (Empty) | List of products eligible if “Apply to specific products only” is YES. |
| **Deferred Payment Users** | Customer Search | N/A | Find and manage individual customer access. |
| | Enable Deferred Payment (per user) | YES/NO | Individual override for deferred payment access. |
| | Payment Due Days (Override) | (Empty for global) | Custom payment terms for a specific customer. |
| | Credit Limit | (Empty for no limit) | Max outstanding amount for a specific customer. |
| **Activity Log** | N/A | N/A | Read-only log of deferred payment events. |
| **Dashboard** | N/A | N/A | Overview of deferred payment orders and statistics. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: Why isn’t Deffered Payment showing up for my customers at checkout?**
A:

1. **Is the module enabled?** Check “Enable Deffered Payment” in the module configuration.
2. **Are customer groups correct?** Ensure the customer is logged in and belongs to one of the “Allowed Customer Groups” selected in the module settings.
3. **Minimum Order Total:** Is the cart total above the “Minimum Order Total for Deffered Payment”?
4. **Specific Products:** If “Apply to specific products only” is enabled, does the cart *only* contain products from your approved list?
5. **Individual User Settings:** Check “Deferred Payment Users” to see if the customer has been individually disabled or has specific overrides.
6. **Cache:** Clear your PrestaShop cache (Advanced Parameters > Performance) and your browser cache.

**Q: How do I change the order status once a deferred payment is received?**
A: You will need to manually update the order status in the PrestaShop Back Office. Go to **Orders > Orders**, find the relevant order, and change its status from “Awaiting deferred payment” (or whatever you configured) to “Payment accepted” or “Delivered” as appropriate.

**Q: Can I set different payment due days for different customers?**
A: Yes! Use the “Deferred Payment Users” screen. You can search for a specific customer and set a custom “Payment Due Days (Override)” for them, which will take precedence over the global setting.

**Q: What is the Cron Job URL for and do I need to set it up?**
A: The Cron Job URL is for automated tasks the module might perform in the background (e.g., checking for overdue payments, sending notifications, if implemented). While the module might function without it for basic payment processing, it’s highly recommended to set it up on your server to ensure all automated features work correctly. Your web host or a developer can help you set up a cron job to visit this URL daily.

**Q: The module is installed, but I don’t see the “Deffered Payment” menu item in the Back Office.**
A:

1. **Permissions:** Check your employee permissions (Advanced Parameters > Team > Employees > Edit your profile > Permissions tab). Ensure you have access to the “Deffered Payment” module and its associated admin controllers.
2. **Cache:** Clear your PrestaShop cache (Advanced Parameters > Performance).

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the Deffered Payment module for developers and webmasters.

### 4.1 Architecture Overview

The Deffered Payment module follows PrestaShop’s standard MVC (Model-View-Controller) pattern. It integrates as a payment module, extending `PaymentModule` and providing custom admin controllers for managing deferred payment users and logs. It leverages PrestaShop’s configuration system for settings and hooks for front-office display and back-office order integration. The module introduces custom database tables (`defpay_log`, `defpayuser`) to store specific deferred payment data.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `defpay/controllers/front/cron.php`
  - **Class Name:** `DefPayCronModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** Handles the execution of cron job tasks. This controller is accessed via the `Cron Job URL` provided in the module configuration. It’s designed to be called periodically by a server-side cron scheduler to perform background operations like checking payment due dates, updating order statuses, or triggering notifications.
- `defpay/controllers/front/index.php`
  - **Class Name:** `DefPayIndexModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** A placeholder or default front controller. Often used for basic module routing or if the module needs a default front-office entry point that doesn’t directly correspond to a specific action. In this module, it might not have a direct user-facing function.
- `defpay/controllers/front/statement.php`
  - **Class Name:** `DefPayStatementModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** Likely handles the display or generation of deferred payment statements for customers. This could be a page in the customer account area showing pending payments or a link to download an invoice.
- `defpay/controllers/front/validation.php`
  - **Class Name:** `DefPayValidationModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** The core payment validation controller. When a customer selects “Deffered Payment” at checkout and confirms the order, this controller processes the order, sets the appropriate order status, and redirects the customer to the order confirmation page.

#### Back-Office Admin Controllers

- `defpay/controllers/admin/AdminDefPayActivityLog.php`
  - **Class Name:** `AdminDefPayActivityLogController` (extends `ModuleAdminController`)
  - **Tab Name:** `Deferred Payment Activity Log`
  - **Managed Entity:** `defpay_log` (custom database table)
  - **Responsibility:** Provides a list management interface for the `defpay_log` table. Displays a historical record of events related to deferred payments, such as order placements, status changes, or cron job actions.
- `defpay/controllers/admin/AdminDefPayUsers.php`
  - **Class Name:** `AdminDefPayUsersController` (extends `ModuleAdminController`)
  - **Tab Name:** `Deferred Payment Users`
  - **Managed Entity:** `defpayuser` (custom database table)
  - **Responsibility:** Manages individual customer settings for deferred payment. Allows administrators to enable/disable deferred payment for specific customers, set custom due days, and define credit limits. Interacts with the `ps_currency` table (via `PS_CURRENCY_DEFAULT`) for credit limit currency.
- `defpay/controllers/admin/index.php`
  - **Class Name:** `AdminDefPayDashboardController` (likely, extends `ModuleAdminController`)
  - **Tab Name:** `Deferred Payment Dashboard` (or main menu item)
  - **Managed Entity:** No direct single entity; aggregates data.
  - **Responsibility:** Serves as the main dashboard or overview for the Deffered Payment module in the Back Office. It likely displays key statistics, summaries of pending/overdue payments, and quick links to other management sections.

### 4.3 Core Classes & Models (`classes/`)

The provided module information indicates no custom classes in the `classes/` directory. This suggests that the module’s core logic, including `ObjectModel` definitions for `defpay_log` and `defpayuser`, might be directly embedded within the main `defpay/cronjob.php` file or within the admin controllers themselves. This is a less common but sometimes used approach for simpler modules.

If `defpay_log` and `defpayuser` are indeed custom tables, their `ObjectModel` definitions (e.g., `DefPayLog` and `DefPayUser` classes) would typically be found in `classes/`. If not, they are likely defined inline or managed directly via `Db` class calls.

### 4.4 JavaScript Assets (`views/js/`)

- `defpay/lib/emailTemplatesManager/js/emailTemplatesManager.js`
  - **Scope:** Back-office.
  - **Description:** Likely provides functionality for managing email templates within the module’s configuration or specific admin screens. This could include dynamic form fields, previewing templates, or saving template content.
- `defpay/lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Back-office (e.g., `AdminDefPayUsers` for customer search, or module config for product search).
  - **Description:** Implements an autocomplete feature for search inputs, such as finding customers or products. It listens for user input, makes AJAX calls to fetch suggestions, and displays them in a dropdown.
- `defpay/tools/browser-demo-simulator.js`
  - **Scope:** Potentially both, but more likely for development/testing.
  - **Description:** A utility script, possibly for simulating browser behavior or module interactions for testing purposes. Not typically used in a production environment.
- `defpay/views/js/adminDefPayActivityPreview.js`
  - **Scope:** Back-office (`AdminDefPayActivityLog`).
  - **Description:** Provides interactive features for the activity log, such as expanding log entries, filtering, or previewing details of an activity.
- `defpay/views/js/adminDefPayCollections.js`
  - **Scope:** Back-office (likely related to managing deferred payment collections).
  - **Description:** Implements JavaScript logic for a “collections” management interface, which could involve marking payments as received, sending reminders, or managing overdue accounts.
- `defpay/views/js/adminDefPayDashboard.js`
  - **Scope:** Back-office (Dashboard).
  - **Description:** Powers the interactive elements of the deferred payment dashboard, such as dynamic charts, data filtering, or AJAX updates for statistics.
- `defpay/views/js/adminDefPayPortfolio.js`
  - **Scope:** Back-office.
  - **Description:** Likely related to managing a “portfolio” of deferred payment accounts or orders, possibly offering advanced filtering, reporting, or bulk actions.
- `defpay/views/js/defpay_target_products.js`
  - **Scope:** Back-office (Module Configuration).
  - **Description:** Provides the JavaScript functionality for the “Target Products” section in the module configuration, enabling product search, selection, and removal for deferred payment eligibility.

### 4.5 CSS Stylesheets (`views/css/`)

- `defpay/lib/emailTemplatesManager/css/emailTemplatesManager.css`
  - **Scope:** Back-office.
  - **Description:** Styles for the email template management interface, ensuring a consistent look within the PrestaShop admin panel.
- `defpay/lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Back-office.
  - **Description:** Styles for the autocomplete search suggestions, ensuring they are visually distinct and user-friendly.
- `defpay/views/css/admin_defpay.css`
  - **Scope:** Back-office.
  - **Description:** General styling for the module’s custom admin screens (Dashboard, Users, Activity Log), ensuring a cohesive design within the PrestaShop Back Office.
- `defpay/views/css/defpay.css`
  - **Scope:** Front-office.
  - **Description:** General styling for the front-office components of the module, such as the payment option display on the checkout page or customer account sections.
- `defpay/views/css/statement-document.css`
  - **Scope:** Front-office (for print/PDF).
  - **Description:** Specific styles for the printable or PDF version of a deferred payment statement, optimized for document layout.
- `defpay/views/css/statement.css`
  - **Scope:** Front-office.
  - **Description:** Styles for the on-screen display of deferred payment statements in the customer account area.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `defpay/views/templates/hook/confirmation.tpl`
  - **Hook:** `displayOrderConfirmation` (or similar).
  - **Output:** Content displayed on the order confirmation page after a deferred payment order is placed, informing the customer about payment terms.
- `defpay/views/templates/hook/displayAdminOrder16.tpl`
  - **Hook:** `displayAdminOrder` (PrestaShop 1.6).
  - **Output:** Adds a block of information or actions related to deferred payment on the order detail page in the PrestaShop 1.6 Back Office.
- `defpay/views/templates/hook/displayAdminOrder17.tpl`
  - **Hook:** `displayAdminOrder` (PrestaShop 1.7+).
  - **Output:** Similar to `displayAdminOrder16.tpl`, but adapted for the PrestaShop 1.7+ Back Office order detail page, showing deferred payment status, due date, and possibly payment collection actions.
- `defpay/views/templates/hook/displayCustomerAccount.tpl`
  - **Hook:** `displayCustomerAccount` or `displayMyAccountBlock`.
  - **Output:** Adds a link or block to the customer’s “My Account” page, potentially linking to their deferred payment statement or history.
- `defpay/views/templates/hook/displayOrderDetail.tpl`
  - **Hook:** `displayOrderDetail` (front-office).
  - **Output:** Displays deferred payment specific information (e.g., due date, payment status) within the customer’s front-office order detail page.
- `defpay/views/templates/hook/payment.tpl`
  - **Hook:** `displayPayment` (or `paymentOptions` for PS 1.7+).
  - **Output:** Renders the “Deffered Payment” option on the checkout payment selection page.

#### Admin templates (`views/templates/admin/`)

- `defpay/views/templates/admin/cron_setup.tpl`
  - **Purpose:** Likely used within the module’s main configuration page (`getContent()`) to display the Cron Job URL and instructions.
- `defpay/views/templates/admin/defpay_target_products.tpl`
  - **Purpose:** Renders the interface for selecting specific products eligible for deferred payment within the module’s configuration.

#### Front-office templates (`views/templates/front/`)

- `defpay/views/templates/front/statement_preview.tpl`
  - **Purpose:** Displays a preview of a deferred payment statement to the customer in the front office.
- `defpay/views/templates/front/validation.tpl`
  - **Purpose:** The template rendered by the `validation.php` front controller, typically a confirmation message or a summary after a deferred payment order is successfully placed.

#### PDF templates (`views/templates/pdf/`)

- `defpay/views/templates/pdf/statement.tpl`
  - **Purpose:** Template used to generate a PDF version of a deferred payment statement or invoice.

#### Library Templates (`defpay/lib/emailTemplatesManager/views/` & `defpay/lib/searchTool/views/`)

These templates are part of embedded libraries within the module:

- `defpay/lib/emailTemplatesManager/views/buttonManager.tpl`
- `defpay/lib/emailTemplatesManager/views/createTemplateForm.tpl`
- `defpay/lib/emailTemplatesManager/views/editTemplateForm.tpl`
- `defpay/lib/emailTemplatesManager/views/mainForm.tpl`
- `defpay/lib/emailTemplatesManager/views/selectInput.tpl`
  - **Purpose:** These templates are used to render the various components of the email template management interface in the Back Office.
- `defpay/lib/searchTool/views/scripts.tpl`
  - **Purpose:** Likely includes JavaScript initialization or configuration for the autocomplete search tool.

### 4.7 Database Schema & Hooks Map

#### Database Tables

- `ps_defpay_log` (or `defpay_log`):
  - Stores activity log entries related to deferred payments.
  - Fields likely include: `id_defpay_log`, `id_order`, `id_customer`, `event_type`, `description`, `date_add`.
- `ps_defpayuser` (or `defpayuser`):
  - Stores individual deferred payment settings for customers.
  - Fields likely include: `id_defpayuser`, `id_customer`, `deferred_payment_enabled` (boolean), `payment_due_days_override` (int), `credit_limit` (decimal), `date_add`, `date_upd`.
- `ps_configuration`:
  - Module settings are stored here with keys like `DEFPAY_ENABLED`, `DEFPAY_GROUPS`, `DEFPAY_DUE_DAYS`, `DEFPAY_MIN_TOTAL`, `DEFPAY_ORDER_STATUS`, `DEFPAY_CRON_URL`, `DEFPAY_TARGET_PRODUCTS_ENABLED`, `DEFPAY_TARGET_PRODUCTS_LIST`.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayPayment` (PS 1.6) | On the payment selection step of checkout. | Renders the “Deffered Payment” option. |
| `paymentOptions` (PS 1.7+) | On the payment selection step of checkout. | Renders the “Deffered Payment” option (modern hook). |
| `displayOrderConfirmation` | After an order is successfully placed. | Displays deferred payment details on the confirmation page. |
| `displayCustomerAccount` / `displayMyAccountBlock` | On the customer’s “My Account” page. | Adds a link to deferred payment statements or history. |
| `displayOrderDetail` | On the customer’s front-office order detail page. | Shows deferred payment specific information for an order. |
| `displayAdminOrder` (PS 1.6) | On the order detail page in the Back Office (PS 1.6). | Injects deferred payment status and management tools. |
| `displayAdminOrder` (PS 1.7+) | On the order detail page in the Back Office (PS 1.7+). | Injects deferred payment status and management tools. |
| `actionValidateOrder` | After an order is successfully validated. | Used to perform actions like setting the initial deferred payment order status, logging the event, or creating a `defpayuser` entry if needed. |
| `actionOrderStatusUpdate` | When an order’s status is changed. | Can be used to trigger actions based on status changes (e.g., payment received, overdue). |
| `actionFrontControllerSetMedia` | Before a front controller renders its output. | Used to enqueue front-office CSS and JS assets. |
| `actionAdminControllerSetMedia` | Before an admin controller renders its output. | Used to enqueue back-office CSS and JS assets. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please log in to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). You will find your purchased modules and access to our support channels there.
