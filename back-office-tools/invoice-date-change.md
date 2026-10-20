---
title: "Invoice date change - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Invoice date change PrestaShop module by MyPresta.eu."
sidebar:
  label: "Invoice date change - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Invoice date change Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/invoice-date-change.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/invoice-date-change/)
>
> ---


# Invoice date change

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are required beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Invoice date change” module. This will take you to the main configuration screen.

On this screen, you will find the core functionality of the module, which allows you to set the desired invoice date for an order.

**How to use it:**

1. **Navigate to an Order:**
   - Go to **Orders > Orders** in your PrestaShop Back Office.
   - Click on an existing order to view its details.
2. **Locate the Invoice Date Section:**
   - On the order detail page, scroll down. You will find a new section or block related to “Invoice Date Change”.
   - This section will typically appear within the “Documents” block or a similar area where invoices are managed.
3. **Select the Desired Date:**
   - You will see a date picker field. Click on this field to open a calendar.
   - Choose the exact date you want to appear on the invoice. This can be a past date or a future date.
4. **Save Your Changes:**
   - After selecting the date, there will be a “Save” or “Update” button within this section. Click it to apply the new invoice date to the order.
5. **Generate or Regenerate the Invoice:**
   - Once the date is saved, if you generate a new invoice for this order (or regenerate an existing one), the PDF will reflect the date you just set.

**What this setting does:** This module doesn’t have a global “on/off” switch or complex settings. Its primary function is to inject a date picker directly into your order detail pages in the Back Office. This date picker allows you to manually override the default invoice generation date for individual orders.

**Effect of changing this setting:**

- *When you select a date and save:* The chosen date is stored for that specific order. Any invoice generated for this order *after* you’ve set this date will use your selected date instead of the current system date.
- *When you don’t use the module’s date picker:* PrestaShop will continue to generate invoices with the current date, as it does by default.

**Recommended value:** Use the date picker to select the exact date required for each specific invoice. There is no global “recommended value” as the date will vary per order.

**Merchant scenario / example:**
Imagine a customer placed an order on January 15th, but due to a stock delay, the product was only shipped and invoiced on January 25th. However, for accounting purposes, you need the invoice date to reflect the original order date of January 15th.

1. You go to the order details page for this specific order.
2. In the “Invoice Date Change” section, you open the calendar and select January 15th.
3. You click “Save”.
4. Now, when you generate the PDF invoice for this order, it will display “January 15th” as the invoice date, even though you generated it on January 25th.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Order Detail Page (Back Office) | Date Picker (within “Invoice Date Change” section) | Varies per order | Allows manual selection of the invoice issue date for a specific order. The selected date will appear on the generated PDF invoice, overriding the default current date. |
| Order Detail Page (Back Office) | Save/Update Button | N/A | Applies the selected invoice date to the current order. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I changed the date, but the invoice still shows the old date. What’s wrong?**
A: Make sure you clicked the “Save” or “Update” button after selecting the new date on the order detail page. Also, ensure you are generating a *new* invoice or *regenerating* the existing one *after* saving the new date. If you’re looking at an already downloaded PDF, it won’t magically update. You need to download it again.

**Q: The date picker isn’t showing up on my order page.**
A:

1. **Check Module Installation:** Go to **Modules > Module Manager** and ensure “Invoice date change” is installed and enabled.
2. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes PrestaShop needs a cache refresh to display new module elements.
3. **Theme Compatibility:** While the module is designed to integrate seamlessly, very heavily customized themes might occasionally interfere. If clearing cache doesn’t help, temporarily switch to the default PrestaShop theme to see if the date picker appears. If it does, your theme might require a small adjustment.

**Q: Can I change the date for multiple invoices at once?**
A: No, this module is designed for individual order invoice date changes. You need to go into each order’s detail page to set its specific invoice date. There is no bulk editing feature.

**Q: Does this module affect other dates in PrestaShop, like order date or payment date?**
A: No, this module *only* changes the issue date that appears on the generated PDF invoice. It does not alter the order creation date, payment date, or any other timestamps associated with the order in your database.

**Q: Will this module work with my custom invoice template?**
A: Yes, the module injects the chosen date into the standard PrestaShop invoice generation process. As long as your custom invoice template correctly uses the standard variables for the invoice date, it should display the date set by the module.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Invoice date change” module is a lightweight PrestaShop module primarily designed to extend the Back Office order management functionality. It leverages PrestaShop’s hook system to inject a custom date input field into the order detail page. When a new date is selected and saved, it updates the `invoice_date` field of the `OrderInvoice` object, ensuring that subsequent PDF invoice generations reflect the user-defined date. It follows a simple, direct approach without complex MVC structures or custom database tables, relying on existing PrestaShop core functionalities.

### 4.2 Controllers (`controllers/`)

This module does not introduce any custom front-office or back-office controllers. All logic is handled within the main module file (`invoicedate/index.php`) and through PrestaShop’s hook system.

### 4.3 Core Classes & Models (`classes/`)

This module does not introduce any custom classes or models in the `classes/` directory. It directly interacts with the core `OrderInvoice` object and its properties.

### 4.4 JavaScript Assets (`views/js/`)

No custom JavaScript files are included in this module. The date picker functionality is typically provided by PrestaShop’s core JavaScript libraries (e.g., jQuery UI Datepicker) which are already loaded in the Back Office.

### 4.5 CSS Stylesheets (`views/css/`)

No custom CSS files are included in this module. The styling for the date picker and surrounding elements relies on PrestaShop’s default Back Office CSS.

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses two specific templates to display the date input field on the order detail page, depending on the PrestaShop version.

- **Hook templates (`views/templates/hook/`)**:
  - `invoicedate/views/templates/hook/displayAdminOrder16.tpl`
    - **Hook**: This template is rendered in the `displayAdminOrder` hook, specifically for PrestaShop 1.6.x versions.
    - **Purpose**: It outputs the HTML structure for the invoice date input field (a date picker) and a submit button within the order details page in the PrestaShop 1.6 Back Office. It allows the administrator to select and save a custom invoice date for the current order.
  - `invoicedate/views/templates/hook/displayAdminOrder17.tpl`
    - **Hook**: This template is rendered in the `displayAdminOrder` hook, specifically for PrestaShop 1.7.x and newer versions.
    - **Purpose**: Similar to the 1.6 version, this template provides the HTML for the invoice date input field and submit button, adapted for the structural and styling differences of the PrestaShop 1.7+ Back Office order page.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  This module does not create any new custom database tables. It modifies the `invoice_date` field of the existing `ps_order_invoice` table (or `_order_invoice` depending on your prefix) when an invoice date is updated via the module’s interface.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayAdminOrder` | Executed on the PrestaShop Back Office order detail page. | This hook is used to inject the module’s custom HTML (the date picker and save button) into the order details view, allowing the merchant to interact with the invoice date setting. The module uses version-specific templates (`displayAdminOrder16.tpl` or `displayAdminOrder17.tpl`) for this hook. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Invoice date change” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist you with any issues or questions regarding the module’s functionality and compatibility.
