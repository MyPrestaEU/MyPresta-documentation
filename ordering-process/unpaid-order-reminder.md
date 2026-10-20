---
title: "Unpaid order reminder - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Unpaid order reminder PrestaShop module by MyPresta.eu."
sidebar:
  label: "Unpaid order reminder - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Unpaid order reminder Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/unpaid-order-reminder.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/unpaid-order-reminder/)
>
> ---


# Unpaid order reminder

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. Ensure your server’s cron job functionality is enabled and correctly configured for the module’s automated reminders to work.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The “Unpaid order reminder” module offers several configuration screens to manage your reminder settings, view history, and handle unsubscribed customers.

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Unpaid order reminder)

This is the main configuration screen where you set up the core behavior of the module.

- **What this setting does:** This section allows you to enable or disable the module, configure the cron job, and manage the general settings for your reminder emails.
- **Effect of changing this setting:** Controls the overall functionality and automation of the reminder system.

#### General Settings

- **Enable Module:**

  - **What this setting does:** Turns the entire “Unpaid order reminder” module on or off.
  - **Effect of changing this setting:**
    - *When enabled:* The module will start sending reminders according to your defined rules and cron job.
    - *When disabled:* No reminders will be sent, and the module will be inactive.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Enable this after you’ve set up your reminder rules to start recovering unpaid orders. Disable it if you need to temporarily stop all reminders for maintenance or a specific campaign.
- **Cron Job URL:**

  - **What this setting does:** Displays the unique URL that your server’s cron job needs to execute periodically. This URL triggers the module to check for unpaid orders and send reminders.
  - **Effect of changing this setting:** This URL is crucial for the module’s automation. Without it being called by a cron job, no reminders will be sent automatically.
  - **Recommended value:** Copy this URL and set it up in your hosting control panel’s cron job manager.
  - **Merchant scenario / example:** You’ll typically set this up once during initial configuration. For example, you might configure your server to call this URL every hour to ensure timely reminders.
- **Unsubscribe Link in Email:**

  - **What this setting does:** Determines whether an unsubscribe link is included in the reminder emails.
  - **Effect of changing this setting:**
    - *When enabled:* Customers can click a link in the email to opt out of future unpaid order reminders.
    - *When disabled:* Customers cannot easily opt out, which might lead to frustration or mark your emails as spam.
  - **Recommended value:** YES (Highly recommended for compliance and customer satisfaction).
  - **Merchant scenario / example:** Always include this to give customers control and maintain a good sender reputation.
- **Order Statuses to Remind:**

  - **What this setting does:** Allows you to select which specific order statuses should trigger a reminder. Typically, these are statuses indicating an order is awaiting payment (e.g., “Awaiting bank wire payment,” “Awaiting check payment”).
  - **Effect of changing this setting:** Only orders with the selected statuses will be considered for reminders.
  - **Recommended value:** Select all statuses that represent an order awaiting payment.
  - **Merchant scenario / example:** If you use “Awaiting bank wire payment” and “Awaiting check payment,” select both. If you have a custom status like “Pending payment gateway,” include that too.
- **Order Statuses to Stop Reminders:**

  - **What this setting does:** Defines which order statuses, if reached, should stop any further reminders for that specific order. This usually includes statuses like “Payment accepted,” “Shipped,” or “Canceled.”
  - **Effect of changing this setting:** Once an order reaches one of these statuses, the module will no longer send reminders for it, preventing unnecessary or confusing emails.
  - **Recommended value:** Select all statuses that indicate payment has been received, the order is processed, or the order is no longer valid (e.g., “Payment accepted,” “Canceled,” “Refunded”).
  - **Merchant scenario / example:** If a customer pays for an order, you don’t want them to receive another reminder. Selecting “Payment accepted” here ensures this.

#### Reminder Rules

This section is where you define the actual reminder emails. You can create multiple rules, each with different timing and email content.

- **Add New Reminder Rule:**
  - **What this setting does:** Allows you to create a new set of reminder parameters.
  - **Effect of changing this setting:** Opens a form to define a new reminder email.
  - **Recommended value:** Create at least one rule.
  - **Merchant scenario / example:** You might want to send a first reminder after 24 hours and a second, more urgent one after 72 hours.

When adding/editing a rule, you’ll configure:

- **Days after order creation:**

  - **What this setting does:** Specifies how many days after the order was placed this particular reminder email should be sent.
  - **Effect of changing this setting:** Controls the timing of the reminder.
  - **Recommended value:** Start with 1 or 2 days for the first reminder.
  - **Merchant scenario / example:** Set to “1” for a first reminder 24 hours after the order. Set to “3” for a second reminder 3 days after the order.
- **Email Subject:**

  - **What this setting does:** The subject line of the reminder email.
  - **Effect of changing this setting:** This is what customers see in their inbox. A clear, concise subject increases open rates.
  - **Recommended value:** Something like “Reminder: Your Unpaid Order on [Shop Name]” or “Action Required: Complete Your Order #[Order ID]”.
  - **Merchant scenario / example:** “Don’t Forget Your Order from MyPresta.eu!”
- **Email Content:**

  - **What this setting does:** The main body of the reminder email. You can use variables (like `{customer_name}`, `{order_id}`, `{shop_name}`) to personalize the message.
  - **Effect of changing this setting:** This is the core message to your customer. A friendly, helpful tone is best.
  - **Recommended value:** Include a greeting, mention the unpaid order, provide instructions on how to pay or where to find payment details, and offer help.
  - **Merchant scenario / example:** “Dear {customer\_name}, This is a friendly reminder about your recent order #{order\_id} on {shop\_name}. It appears the payment for this order is still pending. Please complete your payment at your earliest convenience to ensure your order is processed. You can view your order details here: [Link to order history]. If you have any questions, please contact us.”
- **Active:**

  - **What this setting does:** Enables or disables this specific reminder rule.
  - **Effect of changing this setting:**
    - *When enabled:* This reminder will be sent according to its timing.
    - *When disabled:* This reminder will not be sent, even if the module is active.
  - **Recommended value:** YES for active rules.
  - **Merchant scenario / example:** You might disable a rule if you’re testing new content or want to temporarily pause a specific reminder.

### 2.2 Order Reminders Management (Back Office > Modules > Unpaid order reminder > Order Reminders)

This dedicated screen, accessible via the module’s menu in the Back Office, allows you to view and manage the orders that are currently eligible for reminders.

- **Screen Name & Menu Location:** **Order Reminders** (under the “Unpaid order reminder” menu item).
- **Available Actions & Settings:** This screen displays a list of orders that currently match your “Order Statuses to Remind” criteria.
  - **Grid / Management View:** You’ll see a table with columns like Order ID, Customer Name, Order Date, Current Status, and potentially the next reminder date.
  - **Actions:** You might have actions to manually send a reminder for a specific order, or to exclude an order from future reminders.
- **Effect of changes:**
  - **Manually sending a reminder:** Immediately dispatches the next scheduled reminder email for that order.
  - **Excluding an order:** Prevents the module from sending any further reminders for that specific order, even if its status still matches the reminder criteria.
- **Recommended workflow for daily store management:** Periodically check this list to get an overview of pending unpaid orders. Use the manual send option if a customer calls and you want to immediately send them the payment details again. Exclude orders if you’ve made a special arrangement with a customer or if an order is problematic.

### 2.3 Order Reminders History (Back Office > Modules > Unpaid order reminder > History)

This screen provides a log of all reminder emails that have been sent by the module.

- **Screen Name & Menu Location:** **History** (under the “Unpaid order reminder” menu item).
- **Available Actions & Settings:** This screen displays a table with details about each sent reminder:
  - Columns typically include: Order ID, Customer Name, Email Address, Reminder Rule (which rule triggered it), Date Sent, and potentially the email subject.
- **Effect of changes:** This is a read-only log. No direct changes are made here, but it provides valuable insights.
- **Recommended workflow for daily store management:** Use this screen to verify that reminders are being sent correctly. If a customer claims they didn’t receive a reminder, you can check this history to confirm if it was dispatched.

### 2.4 Unsubscribed Customers (Back Office > Modules > Unpaid order reminder > Unsubscribed Customers)

This screen lists customers who have opted out of receiving unpaid order reminders.

- **Screen Name & Menu Location:** **Unsubscribed Customers** (under the “Unpaid order reminder” menu item).
- **Available Actions & Settings:** This screen displays a table with:
  - Columns typically include: Customer ID, Customer Name, Email Address, and Date Unsubscribed.
  - **Actions:** You might have an option to manually remove a customer from this list, effectively re-subscribing them to reminders (use with caution and only if requested by the customer).
- **Effect of changes:**
  - **Removing from list:** The customer will once again be eligible to receive reminders if their order status matches.
- **Recommended workflow for daily store management:** Monitor this list to understand customer preferences. Only re-subscribe a customer if they explicitly request it.

### 2.5 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Enable Module | YES | Turns module functionality on/off. |
|  | Cron Job URL | Copy & Configure | Essential for automated reminder sending. |
|  | Unsubscribe Link in Email | YES | Allows customers to opt out, improves sender reputation. |
|  | Order Statuses to Remind | Awaiting bank wire, Awaiting check, etc. | Defines which order statuses trigger reminders. |
|  | Order Statuses to Stop Reminders | Payment accepted, Canceled, etc. | Prevents reminders for paid or invalid orders. |
|  | **Reminder Rules** |  |  |
|  | Days after order creation | 1, 3, 7 (example) | Sets timing for each reminder email. |
|  | Email Subject | “Reminder: Your Unpaid Order…” | Subject line of the reminder email. |
|  | Email Content | Personalized message with variables | Body of the reminder email. |
|  | Active (for each rule) | YES | Enables/disables individual reminder rules. |
| **Order Reminders** | (List of eligible orders) | N/A | Overview of orders awaiting payment. |
|  | Manual Send Reminder | N/A | Immediately sends next reminder for selected order. |
|  | Exclude Order | N/A | Prevents future reminders for selected order. |
| **History** | (Log of sent reminders) | N/A | Audit trail of all dispatched reminder emails. |
| **Unsubscribed Customers** | (List of unsubscribed customers) | N/A | Shows customers who opted out of reminders. |
|  | Remove from Unsubscribe List | N/A | Re-subscribes customer to reminders (use with caution). |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My reminders aren’t being sent. What should I check first?**
**A1:**

- **Module Enabled:** Go to **Modules > Module Manager > Unpaid order reminder** and ensure the “Enable Module” setting is set to YES.
- **Cron Job:** The most common issue. You *must* set up the cron job on your hosting server. Copy the “Cron Job URL” from the module’s configuration page and add it to your hosting control panel’s cron job manager. Ensure it’s set to run frequently (e.g., every hour). If you’re unsure how to do this, contact your hosting provider.
- **Order Statuses:** Double-check “Order Statuses to Remind” and “Order Statuses to Stop Reminders” in the module configuration. Make sure the orders you expect reminders for have a status selected in the “to Remind” list, and haven’t reached a status in the “to Stop” list.
- **Reminder Rules Active:** Ensure the individual reminder rules you’ve created are marked as “Active.”

**Q2: Customers are receiving too many reminders, or reminders after they’ve paid. How do I fix this?**
**A2:**

- **“Order Statuses to Stop Reminders”:** This is crucial. Make sure all statuses that indicate a paid or completed order (e.g., “Payment accepted,” “Shipped,” “Canceled,” “Refunded”) are selected in this setting. This tells the module to stop sending reminders once the order reaches one of these states.
- **Reminder Rule Timing:** Review the “Days after order creation” for each reminder rule. Ensure they are spaced appropriately and not overlapping in a way that sends too many emails too quickly.

**Q3: Can I customize the email templates?**
**A3:** Yes, the module allows you to customize the email subject and content directly within the reminder rule settings. You can use specific variables (like `{customer_name}`, `{order_id}`, `{shop_name}`) to personalize the message. For more advanced visual customization, a developer would need to modify the underlying email template files (located in `mails/` within your PrestaShop installation, using the module’s template structure as a guide).

**Q4: The unsubscribe link isn’t working, or customers are still getting emails after unsubscribing.**
**A4:**

- **Unsubscribe Link Enabled:** Ensure “Unsubscribe Link in Email” is set to YES in the module’s main configuration.
- **Check “Unsubscribed Customers” list:** Go to **Modules > Unpaid order reminder > Unsubscribed Customers**. Verify that the customer’s email address appears on this list. If it doesn’t, they might not have successfully unsubscribed.
- **Cache:** Clear your PrestaShop cache (**Advanced Parameters > Performance > Clear Cache**) after making any configuration changes.

**Q5: What happens if a customer has multiple unpaid orders?**
**A5:** The module will treat each unpaid order individually. If a customer has two separate unpaid orders, they will receive reminders for each order according to your defined rules, as long as those orders meet the criteria.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the “Unpaid order reminder” module, intended for developers and webmasters.

### 4.1 Architecture Overview

The “Unpaid order reminder” module (`oreminders`) follows a standard PrestaShop module architecture, leveraging MVC principles. It primarily focuses on back-office administration for configuration and a front-office cron job for automated processing. It extends `Module` for its core functionality and utilizes custom `AdminController` classes for managing reminders, history, and unsubscribed customers. Email templating is handled through a custom manager, and configuration is stored in `ps_configuration`.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `controllers/front/CronJob.php`
  - **Class name & parent class:** `OremindersCronJobModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** This controller is designed to be called by a server-side cron job. It’s the entry point for the module’s automated logic. When executed, it iterates through unpaid orders, checks against defined reminder rules, and dispatches reminder emails. It typically returns a simple success/failure message or log output.
- `controllers/front/index.php`
  - **Class name & parent class:** `OremindersIndexModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** This is likely a placeholder or a fallback controller. In many modules, `index.php` in `controllers/front` serves as a default or a simple entry point if no specific action is requested. It might handle basic module display or redirection if the module had a front-office presence. Given the module’s nature, its primary front-office interaction is via `CronJob.php`.

#### Back-Office Admin Controllers

- `controllers/admin/AdminOrderReminders.php`
  - **Class name & parent class:** `AdminOrderRemindersController` extends `ModuleAdminController`.
  - **Tab name and managed entity:** Manages the “Order Reminders” list. This controller is responsible for displaying a list of orders that are currently eligible for reminders based on the module’s configuration. It provides actions to manually send reminders or exclude specific orders.
- `controllers/admin/AdminOrderRemindersHistory.php`
  - **Class name & parent class:** `AdminOrderRemindersHistoryController` extends `ModuleAdminController`.
  - **Tab name and managed entity:** Manages the “History” log. This controller displays a read-only list of all reminder emails that have been successfully sent by the module, including details like order ID, customer, and send date.
- `controllers/admin/AdminOrderRemindersUnsub.php`
  - **Class name & parent class:** `AdminOrderRemindersUnsubController` extends `ModuleAdminController`.
  - **Tab name and managed entity:** Manages the “Unsubscribed Customers” list. This controller displays customers who have opted out of receiving reminders and allows for their re-subscription (if needed).
- `controllers/admin/index.php`
  - **Class name & parent class:** `AdminOremindersIndexController` extends `ModuleAdminController`.
  - **Tab name and managed entity:** Similar to the front-office `index.php`, this might serve as a default or fallback admin controller. It could potentially handle the main module configuration if `getContent()` in the main module file redirects to it, or if it’s used for a specific, simple admin action.

### 4.3 Core Classes & Models (`classes/`)

The provided inventory indicates no custom classes in the `classes/` directory. This suggests that the module might be using `ObjectModel` directly within its main module file or admin controllers, or it’s managing data through direct database queries or by extending existing PrestaShop core models (e.g., `Order`, `Customer`).

If custom data is stored, it’s likely managed via `ps_configuration` for settings and potentially custom database tables created during installation (though no SQL files were listed, so table creation would be inline in `install()`).

### 4.4 JavaScript Assets (`views/js/`)

- `oreminders/lib/emailTemplatesManager/js/emailTemplatesManager.js`
  - **Scope:** Back-office.
  - **Details:** This script likely provides dynamic functionality for the email template management interface within the module’s configuration. This could include:
    - Adding/removing reminder rules dynamically.
    - Handling AJAX requests for saving/loading email templates.
    - Implementing a rich text editor (e.g., TinyMCE integration) for email content.
    - Managing variables insertion into email templates.
    - Client-side validation for form fields related to email rules.

### 4.5 CSS Stylesheets (`views/css/`)

- `oreminders/lib/emailTemplatesManager/css/emailTemplatesManager.css`
  - **Scope:** Back-office admin form styling.
  - **Details:** This stylesheet provides specific styling for the email template manager interface in the module’s Back Office configuration. It would define styles for:
    - Layout of reminder rule forms.
    - Styling of input fields, buttons, and text areas within the template editor.
    - Ensuring a consistent look and feel with the PrestaShop Back Office theme.
  - **Key CSS class selectors developers can override:** Look for specific classes prefixed with `oreminders-` or `email-templates-manager-` within the module’s admin templates to identify customizable elements.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `oreminders/views/templates/hook/form.tpl`
  - **Hook:** Potentially `displayAdminModuleConfigure` or similar, if used for a small form within a hook context. More likely, it’s a generic form template used internally.
  - **Output:** Renders a generic form structure.
- `oreminders/views/templates/hook/header.tpl`
  - **Hook:** `displayHeader` (Front-office).
  - **Output:** Used to include necessary CSS or JavaScript files in the `<head>` section of the front-office, if the module had any front-end components (e.g., for the unsubscribe page).
- `oreminders/views/templates/hook/identity.tpl`
  - **Hook:** Unclear from name, but `displayCustomerAccount` or similar for displaying customer-specific information, or perhaps related to the unsubscribe process.
  - **Output:** Could render a message or a form related to customer identity or preferences.

#### Admin templates (`views/templates/admin/`)

- `oreminders/lib/emailTemplatesManager/views/buttonManager.tpl`
  - **Context:** Used within the email template manager.
  - **Output:** Renders buttons for managing email templates (e.g., “Add New Rule,” “Save,” “Delete”).
- `oreminders/lib/emailTemplatesManager/views/createTemplateForm.tpl`
  - **Context:** Used within the email template manager.
  - **Output:** Renders the form for creating a new reminder email template/rule.
- `oreminders/lib/emailTemplatesManager/views/editTemplateForm.tpl`
  - **Context:** Used within the email template manager.
  - **Output:** Renders the form for editing an existing reminder email template/rule.
- `oreminders/lib/emailTemplatesManager/views/mainForm.tpl`
  - **Context:** Used within the email template manager.
  - **Output:** The main wrapper template for the email template management interface, likely combining `buttonManager`, `createTemplateForm`, and `editTemplateForm`.
- `oreminders/lib/emailTemplatesManager/views/selectInput.tpl`
  - **Context:** Used within the email template manager.
  - **Output:** A reusable template for rendering a `<select>` dropdown input, likely for choosing order statuses or other options.
- `oreminders/views/templates/admin/order_reminders/helpers/form/form.tpl`
  - **Context:** Used by `AdminOrderRemindersController` for its form views (e.g., if there’s an add/edit form for an order reminder entry, though it’s primarily a list controller).
  - **Output:** Renders a standard PrestaShop admin form.
- `oreminders/views/templates/admin/order_reminders/helpers/list/list_action_email.tpl`
  - **Context:** Used by `AdminOrderRemindersController` in its list view.
  - **Output:** Renders a specific action button or link within the list of order reminders, likely for “Send Email” or “View Email.”
- `oreminders/views/templates/admin/script.tpl`
  - **Context:** Admin Back Office.
  - **Output:** Likely includes inline JavaScript code or configuration variables needed by the Back Office interface, possibly for AJAX calls or dynamic UI elements.

### 4.7 Database Schema & Hooks Map

#### Database Tables

The module description and file inventory do not explicitly list SQL files for custom table creation. However, based on the admin controllers, the module likely interacts with the following (either custom tables or `ps_configuration` for settings):

- `ps_configuration`: Stores all module settings (e.g., `OREMINDERS_ENABLED`, `OREMINDERS_CRON_URL`, `OREMINDERS_UNSUB_LINK`, `OREMINDERS_STATUSES_REMIND`, `OREMINDERS_STATUSES_STOP`, and serialized data for individual reminder rules).
- `ps_or` (or similar, managed by `AdminOrderRemindersController`): Likely a custom table to store information about orders currently being reminded, or to mark orders as excluded.
- `ps_or_history` (or similar, managed by `AdminOrderRemindersHistoryController`): A custom table to log every reminder email sent, including `id_order`, `id_customer`, `email`, `id_reminder_rule`, `date_sent`.
- `ps_or_ounsub` (or similar, managed by `AdminOrderRemindersUnsubController`): A custom table to store customer IDs or email addresses of those who have unsubscribed from reminders.

#### Registered Hooks Table

| Hook Name | Scope | Execution Timing | Technical Purpose |
| --- | --- | --- | --- |
| `displayHeader` | Front-Office | In the `<head>` section of all front-office pages. | To include module-specific CSS/JS for front-office components (e.g., unsubscribe page). |
| `displayAdminModuleConfigure` | Back-Office | When viewing the module’s main configuration page. | To render the module’s main configuration form (`getContent()` method). |
| `actionValidateOrder` | Back-Office | After an order has been successfully validated. | Potentially used to initialize reminder tracking for new orders, though the cron job is the primary trigger. |
| `actionOrderStatusUpdate` | Back-Office | When an order’s status is changed. | To check if an order’s new status should stop reminders (e.g., if it becomes “Payment accepted”). |
| `actionCronJob` | Back-Office (via Front Controller) | Executed by the server’s cron job. | The core hook that triggers the module’s logic to find unpaid orders and send reminders. |
| (Implicit Hooks for Admin Tabs) | Back-Office | When rendering the Back Office menu. | To add the module’s custom menu items (Order Reminders, History, Unsubscribed Customers). |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Unpaid order reminder” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and configuration.
