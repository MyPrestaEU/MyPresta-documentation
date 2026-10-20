---
title: "Invoice number change - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Invoice number change PrestaShop module by MyPresta.eu."
sidebar:
  label: "Invoice number change - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Invoice number change Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/invoice-number-change.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/invoice-number-change/)
>
> ---


# Invoice number change

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are required beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, navigate to **Modules > Module Manager** and search for “Invoice number change”. Click on the “Configure” button.

This module does not have a separate configuration screen with multiple settings. Its functionality is integrated directly into the order details page in your Back Office. The “Configure” button will simply confirm the module is installed and ready to use.

The core functionality of this module is to add a new field or modify an existing display on the order details page, allowing you to edit the invoice number directly.

**How to use the module:**

1. **Navigate to an Order:** In your PrestaShop Back Office, go to **Orders > Orders**.
2. **Select an Order:** Click on any order to view its details.
3. **Locate the Invoice Section:** Scroll down the order details page until you find the “Documents” or “Invoices” section.
4. **Edit Invoice Number:** You will now see an editable field or a button next to the invoice number that allows you to change it.
   - **What this setting does:** This feature allows you to directly type in a new invoice number for a specific invoice associated with the current order.
   - **Effect of changing this setting:**
     - *When you enter a new number and save:* The invoice number for that specific order invoice will be updated in your database and reflected on the invoice document itself (if regenerated or viewed). This change is permanent and affects your financial records.
   - **Recommended value:** Only change invoice numbers when absolutely necessary and always double-check for accuracy. Ensure the new number follows your internal numbering scheme or legal requirements.
   - **Merchant scenario / example:** An order was initially invoiced as INV00123. Due to a data migration, you need this invoice to be INV2024-005. You would navigate to the order, find INV00123, click to edit, enter INV2024-005, and save.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Order Details Page (Documents/Invoices section) | Invoice Number (editable field) | N/A (depends on existing invoice) | Allows direct modification of an invoice number for a specific order. Crucial for corrections, compliance, or integration with external systems. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve installed the module, but I don’t see any new settings page. Is it working?**
A1: Yes, the module is working as intended. This module does not add a separate configuration page. Its functionality is integrated directly into the order details page. Navigate to **Orders > Orders**, select an order, and you should find an editable field or option to change the invoice number within the “Documents” or “Invoices” section.

**Q2: I changed an invoice number, but the old number still appears on the PDF invoice.**
A2: After changing the invoice number in the Back Office, you might need to regenerate the PDF invoice for that order to reflect the new number. PrestaShop often caches PDF content. Download the invoice again from the order details page, and it should display the updated number.

**Q3: Can I revert an invoice number change?**
A3: The module allows you to change the number to anything you desire. If you need to revert, you would simply edit the field again and enter the original number (if you remember it or have it logged). The module does not keep a history of changes itself, so careful logging on your part is recommended.

**Q4: Will changing an invoice number affect my accounting reports in PrestaShop?**
A4: Yes, changing an invoice number will update the `invoice_number` field in your database for that specific invoice. Any PrestaShop reports that pull invoice numbers directly from the database will reflect the new number. Ensure your changes are consistent with your accounting practices.

**Q5: The module doesn’t seem to be active on my custom theme. What should I do?**
A5: This module uses PrestaShop’s override system to modify core behavior and hooks into standard admin templates. It should work with most custom themes without issues, as it only affects the Back Office. If you encounter problems, first clear your PrestaShop cache (**Advanced Parameters > Performance > Clear cache**). If the issue persists, it might be a conflict with another module or a highly customized admin template. Contact MyPresta.eu support with details of your theme and any other relevant modules.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Invoice number change” module (`invoicenb`) is designed to extend PrestaShop’s core invoice management functionality without altering the database schema. It achieves this primarily through an `override` of the `OrderInvoice` class and by hooking into the Back Office order detail page to provide an editable interface for the invoice number. This approach ensures minimal impact on the core system while providing the desired feature.

### 4.2 Controllers (`controllers/`)

This module does not introduce any custom front-office or back-office controllers. All functionality is integrated via the main module file, overrides, and template hooks.

### 4.3 Core Classes & Models (`classes/`)

- **`invoicenb/override/classes/order/OrderInvoice.php`**
  - **Class Name**: `OrderInvoice` (overrides the core `OrderInvoice` class)
  - **Parent Class**: `OrderInvoiceCore`
  - **Responsibility**: This override is the core of the module’s functionality. It modifies the behavior of the `OrderInvoice` class, specifically how invoice numbers are handled and potentially saved. The override is responsible for allowing the invoice number to be updated from the Back Office. It likely adds or modifies a method to facilitate the saving of a new invoice number when submitted via the admin interface.
  - **Database Table**: `ps_order_invoice` (or your table prefix)
  - **`$definition` fields**: This override works with the existing `$definition` of `OrderInvoiceCore`, particularly the `number` field.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include any custom JavaScript files. The interactive editing functionality is handled directly within the Smarty templates and potentially through standard PrestaShop AJAX mechanisms if a form submission is involved.

### 4.5 CSS Stylesheets (`views/css/`)

This module does not include any custom CSS files. The styling for the editable field or button on the order page will rely on PrestaShop’s default Back Office CSS.

### 4.6 Smarty Template Structure (`views/templates/`)

This module uses templates to inject the editable invoice number field into the Back Office order details page.

- **Hook templates (`views/templates/hook/`)**:
  - **`invoicenb/views/templates/hook/displayAdminOrder16.tpl`**
    - **Hook**: `displayAdminOrder` (for PrestaShop 1.6.x)
    - **Purpose**: This template is rendered on the order details page in PrestaShop 1.6.x. It injects the HTML form elements (e.g., an input field and a save button) that allow the administrator to view and modify the invoice number for a specific order. It likely includes logic to display the current invoice number and handle the submission of a new one.
  - **`invoicenb/views/templates/hook/displayAdminOrder17.tpl`**
    - **Hook**: `displayAdminOrder` (for PrestaShop 1.7.x, 8.x, 9.x)
    - **Purpose**: Similar to `displayAdminOrder16.tpl`, but adapted for the template structure and potentially different hook parameters of PrestaShop 1.7.x and newer versions. It provides the same functionality: displaying an editable invoice number field on the order details page.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any new custom database tables. It interacts with the existing `ps_order_invoice` table (or your table prefix) to update the `number` column.
  - Configuration records are stored in `ps_configuration` for the module’s internal settings (if any, though this module appears to have minimal explicit settings).
- **Registered Hooks Table**:

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `displayAdminOrder` | Renders content on the Back Office order details page. | Used to inject the HTML form for editing the invoice number directly into the order view. The module provides separate templates for PrestaShop 1.6 and 1.7+ for this hook. |
  | `actionObjectOrderInvoiceUpdateAfter` | Executed after an `OrderInvoice` object has been updated. | (Implicit, if the override uses this) Could be used to trigger additional actions or logging after an invoice number has been successfully changed. |
  | `actionObjectOrderInvoiceAddAfter` | Executed after an `OrderInvoice` object has been added. | (Implicit, if the override uses this) Could be used to modify the initial invoice number upon creation, though the primary focus is on changing existing ones. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Invoice number change” module, please refer to your MyPresta.eu customer account. You can download the newest versions from your order history and access our dedicated support channels for any technical assistance or inquiries.
