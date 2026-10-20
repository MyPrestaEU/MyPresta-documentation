---
title: "Auto order status change - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Auto order status change PrestaShop module by MyPresta.eu."
sidebar:
  label: "Auto order status change - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Auto order status change Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/auto-order-status-change.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/auto-order-status-change/)
>
> ---


# Auto order status change

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No unusual server configurations are required.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Auto order status change)

This is the main and only configuration screen for the “Auto order status change” module. Here, you will define the rules for how order statuses automatically transition.

The configuration page will present you with a list of your current order statuses. For each status, you will be able to define what new status it should automatically change to.

**How to Configure a Rule:**

1. **Identify the “From” Status:** On the left side of the configuration table, you will see a list of all your existing order statuses (e.g., “Awaiting bank wire payment,” “Payment accepted,” “Shipped,” etc.). This is the *starting status* that triggers the automatic change.
2. **Select the “To” Status:** Next to each “From” status, you will find a dropdown menu. This menu contains all available order statuses in your store. Select the status you want the order to *automatically change to* when it enters the “From” status.
3. **Save Your Changes:** After setting up your desired transitions, make sure to click the **“Save”** button (usually at the bottom of the page) to apply your rules.

Let’s break down the typical settings you’ll encounter:

#### **Setting Group: Automatic Status Transitions**

This section will display a table or a series of dropdowns, allowing you to map “From” statuses to “To” statuses.

- **What this setting does:** This is the core functionality of the module. For each existing order status in your store, you can specify a *target status* that an order will automatically transition to *if* its status changes to the “From” status.
- **Effect of changing this setting:**
  - *When a “To” status is selected for a “From” status:* Whenever an order’s status is updated to the “From” status (either manually by an admin, by a payment gateway, or by another module), the module will immediately attempt to change it to the selected “To” status.
  - *When “No change” or similar is selected (or left blank):* If you don’t select a “To” status for a particular “From” status, no automatic change will occur for orders entering that specific “From” status. The order will simply remain in the “From” status until manually changed or acted upon by another rule/module.
- **Recommended value:** This depends entirely on your store’s workflow.
  - **Example 1 (Payment Accepted to Processing):**
    - **From Status:** `Payment accepted`
    - **To Status:** `Processing in progress` (or `Preparation in progress`)
    - **Purpose & Impact:** This is a very common and highly recommended setup. When a customer pays and the payment is confirmed (e.g., by PayPal, Stripe, credit card module), the order status automatically updates to “Payment accepted.” This rule then immediately moves it to “Processing,” signaling your warehouse or fulfillment team to start preparing the order without any manual intervention. This saves time and ensures prompt fulfillment.
  - **Example 2 (Shipped to Delivered):**
    - **From Status:** `Shipped`
    - **To Status:** `Delivered`
    - **Purpose & Impact:** While “Shipped” indicates the item has left your warehouse, “Delivered” confirms it has reached the customer. If your shipping carrier integration doesn’t automatically update to “Delivered,” you might set this rule. However, be cautious: this assumes all “Shipped” orders are eventually “Delivered.” It’s often better to rely on carrier tracking for “Delivered” status if possible. Use this if you want to quickly clear “Shipped” orders from your active list after a reasonable delivery time, but be aware it might not reflect actual delivery.
  - **Example 3 (Awaiting Bank Wire to Canceled - with caution):**
    - **From Status:** `Awaiting bank wire payment`
    - **To Status:** `Canceled`
    - **Purpose & Impact:** If you have a strict policy that bank wire payments must be received within a certain timeframe, and you manually change overdue orders to “Canceled,” this module could automate that. However, the module triggers *when the status changes to* “Awaiting bank wire payment.” If you want to cancel *after a delay*, this module alone won’t do it. You would need another mechanism (e.g., a cron job or another module) to change the status to “Awaiting bank wire payment” *after* the delay, which would then trigger this module to change it to “Canceled.” This specific use case is less direct for this module’s immediate trigger.
- **Merchant scenario / example:**
  - “I want all orders that successfully complete payment to automatically move to ‘Preparation in progress’ so my packing team knows to start working on them immediately.”
  - “When a customer requests a refund and I change the order status to ‘Refunded’, I want it to automatically move to ‘Closed’ so it’s no longer in my active order list.”

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | `From Status` (e.g., Payment accepted) | Varies by workflow | The initial status that triggers an automatic change. |
| Module Configuration | `To Status` (dropdown for each `From Status`) | `Processing in progress` (for `Payment accepted`) | The target status an order will automatically move to when it enters the `From Status`. Automates workflow, saves time. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My order statuses aren’t changing automatically. What should I check?**

- **A:** First, go to **Modules > Module Manager > Auto order status change > Configure** and ensure you have correctly set up the “From” and “To” statuses.
- **A:** Verify that the initial status change (the “From” status) is actually occurring. For example, if you expect “Payment accepted” to trigger a change, make sure the order actually reaches “Payment accepted” first.
- **A:** Clear your PrestaShop cache. Go to **Advanced Parameters > Performance** and click “Clear cache” in the top right. Sometimes, module configurations need a cache refresh to take effect.

**Q2: Can this module change statuses based on a time delay (e.g., cancel an order if not paid in 24 hours)?**

- **A:** No, this module triggers *immediately* when an order’s status *changes* to a specific “From” status. It does not have built-in functionality for time-based delays or cron jobs. For time-based actions, you would need a separate module or custom development that changes the order status after a delay, which would then trigger this module.

**Q3: Will this module interfere with my payment gateway’s status updates?**

- **A:** No, it works *with* them. Payment gateways typically update an order to a status like “Payment accepted” or “Awaiting payment.” This module then takes over *after* that initial update, applying your next rule. It doesn’t prevent the payment gateway from setting its initial status.

**Q4: I have a custom theme. Will this module work?**

- **A:** Yes, absolutely. This module operates entirely in the PrestaShop back-office and on the order processing logic. It has no front-office visual components or theme-specific styling, so it is fully compatible with any PrestaShop theme.

**Q5: How do I translate the module’s settings if my back-office is in another language?**

- **A:** PrestaShop automatically handles the translation of order statuses. The module uses the names of your existing order statuses. If you need to translate the module’s own interface elements (like “Save” button or section titles), you can do so via **International > Translations** in your PrestaShop back-office. Select “Installed modules translations,” choose your theme, your language, and then find the “schange” module.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters working with the “Auto order status change” module.

### 4.1 Architecture Overview

The “Auto order status change” module (`schange`) is a straightforward PrestaShop module primarily designed to hook into the `actionOrderStatusPostUpdate` event. It follows a standard PrestaShop module structure, leveraging the `Module` class for installation, uninstallation, and configuration. Its core logic resides within the main module file, processing status changes based on configurations stored in `ps_configuration`.

### 4.2 Controllers (`controllers/`)

This module does **not** contain any custom Front-Office or Back-Office Admin Controllers. All configuration is handled directly within the `getContent()` method of the main module file.

### 4.3 Core Classes & Models (`classes/`)

This module does **not** define any custom classes or `ObjectModel` instances in a `classes/` directory. All logic is encapsulated within the main `schange` class.

### 4.4 JavaScript Assets (`views/js/`)

This module does **not** include any custom JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)

This module does **not** include any custom CSS files. Styling for the configuration page is handled by PrestaShop’s default back-office CSS.

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses a single Smarty template for its configuration interface.

- **Admin templates (`views/templates/admin/`)**:
  - `schange/views/tpl/selectedProducts.tpl`: This template is used within the `getContent()` method to render the module’s configuration form. It typically displays the list of “From” order statuses and their corresponding “To” status dropdowns. Developers can inspect this file to understand the structure of the configuration form and how the status mapping is presented.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does **not** create any custom SQL tables.
  - All configuration settings (the “From” to “To” status mappings) are stored in the `ps_configuration` table. Each mapping is likely stored as a separate configuration key, or a serialized array under a single key, using the module’s name as a prefix (e.g., `SCHANGE_STATUS_FROM_X_TO_Y` or `SCHANGE_STATUS_MAP`).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionOrderStatusPostUpdate` | Triggered immediately after an order’s status has been successfully updated. | This is the primary hook used by the module. When an order’s status changes (e.g., from “Awaiting payment” to “Payment accepted”), this hook fires. The module then checks if the new status (the “From” status) has a configured “To” status. If a mapping exists, the module programmatically updates the order to the designated “To” status. |

### 4.8 Main Module File (`schange/index.php`)

- **Class Name**: `schange`
- **Parent Class**: `Module`
- **Key Methods**:
  - `__construct()`: Initializes module metadata (name, tab, version, author, etc.).
  - `install()`: Registers the `actionOrderStatusPostUpdate` hook and potentially sets default configuration values.
  - `uninstall()`: Unregisters the hook and cleans up configuration values from `ps_configuration`.
  - `getContent()`: Renders the module’s configuration page in the Back Office. This method handles form submission, saves settings to `ps_configuration`, and displays the status mapping interface using `selectedProducts.tpl`.
  - `hookActionOrderStatusPostUpdate($params)`: This is the core logic handler.
    - It receives `$params` containing the `newOrderStatus` and `id_order`.
    - It retrieves the configured status mappings from `ps_configuration`.
    - If the `newOrderStatus` matches a configured “From” status, it loads the `Order` object for `id_order`.
    - It then attempts to update the order’s status to the corresponding “To” status using `Order->setCurrentState()`.
    - It ensures that the status change is valid and handles potential errors.

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Auto order status change” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and integration.
