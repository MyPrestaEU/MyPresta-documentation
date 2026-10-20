---
title: "Order List Invoice Column & Search - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Order List Invoice Column & Search PrestaShop module by MyPresta.eu."
sidebar:
  label: "Order List Invoice Column & Search - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Order List Invoice Column & Search Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-list-invoice-column-search.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/order-list-invoice-column-search/)
>
> ---


# Order List Invoice Column & Search

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special hosting requirements beyond a standard PrestaShop setup.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the module name “Order List Invoice Column & Search”. This module has a very simple and direct configuration, as its core functionality is to enhance the existing order list.

The configuration page for “Order List Invoice Column & Search” is straightforward. It primarily serves to enable or disable the module’s functionality.

- **Setting Name:** Enable Invoice Column & Search
- **What this setting does:** This is the main switch to activate or deactivate the module’s features. When enabled, the module will add the “Invoice Number” column to your order list and integrate the search functionality. When disabled, your order list will revert to its default PrestaShop appearance.
- **Effect of changing this setting:**
  - *When enabled (YES):* A new column titled “Invoice Number” will appear in your Back Office under **Orders > Orders**. This column will display the invoice number for each order (if an invoice has been generated). Additionally, the search bar on the Orders page will now allow you to search by invoice number.
  - *When disabled (NO):* The “Invoice Number” column will be removed from the order list, and the ability to search by invoice number will be deactivated. Your order list will look exactly as it did before installing this module.
- **Recommended value:** **YES**. To benefit from the module’s features, you should enable it.
- **Merchant scenario / example:** If you want to quickly find all orders related to a specific invoice (e.g., “INV00123”), you would enable this setting. Then, you’d navigate to **Orders > Orders**, type “INV00123” into the search bar, and the system would filter the list to show only that order. If you disable it, you would have to manually click into each order to check its invoice number, which is very time-consuming.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable Invoice Column & Search | YES | Activates/deactivates the invoice column and search functionality on the Orders list in the Back Office. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve enabled the module, but I don’t see the “Invoice Number” column or the search isn’t working.**
A:

1. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” in the top right corner. Sometimes PrestaShop needs a cache refresh to display new elements.
2. **Check Module Status:** Double-check that the module is indeed “Enabled” on its configuration page.
3. **PrestaShop Version:** Ensure your PrestaShop version is compatible with the module (1.7.x, 8.x, 9.x).
4. **Browser Cache:** Try clearing your browser’s cache or using an incognito window to rule out browser-specific issues.

**Q: The invoice numbers are showing “N/A” or are empty for some orders.**
A: This typically means an invoice has not yet been generated for those specific orders in PrestaShop. The module only displays the invoice number if it exists in PrestaShop’s database. You will need to manually generate the invoice for those orders through the standard PrestaShop order management process.

**Q: Will this module slow down my Back Office?**
A: No, the module is designed to be lightweight and efficient. It primarily extends an existing PrestaShop feature (the order list) rather than adding heavy new processes. Its impact on performance should be negligible.

**Q: Can I customize the position of the “Invoice Number” column?**
A: The module places the column in a logical position within the order list. Direct customization of column order is not a built-in feature of this module. For advanced layout changes, you would typically need custom theme development or another specialized module.

**Q: Does this module create new invoices?**
A: No, this module does not generate invoices. It only displays and allows searching by invoice numbers that have already been generated by PrestaShop’s core functionality.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Order List Invoice Column & Search” module (`olistinv`) is a classic PrestaShop module that extends core functionality by hooking into existing display and action points within the Back Office. It primarily modifies the `AdminOrders` controller’s list view to add a new column and enhances the search capabilities without introducing new database tables or complex front-office interactions. Its simplicity lies in leveraging PrestaShop’s hook system and overriding template logic where necessary.

### 4.2 Controllers (`controllers/`)

This module does not introduce any custom front-office or back-office controllers. All its logic is contained within the main module file, `olistinv/index.php`, and executed via hooks.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or `ObjectModel`s. It directly interacts with existing PrestaShop core classes and database structures.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include any custom JavaScript files. The search functionality is integrated by modifying the existing search form’s behavior, which is handled by PrestaShop’s core JS.

### 4.5 CSS Stylesheets (`views/css/`)

This module does not include any custom CSS files. The new column will inherit the styling of the existing PrestaShop Back Office tables.

### 4.6 Smarty Template Structure (`views/templates/`)

This module does not include any custom Smarty template files. It achieves its functionality by dynamically injecting content into existing PrestaShop templates via hooks, specifically by modifying the `AdminOrders` list display.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: This module does not create any new database tables. It reads from the `ps_orders` table (specifically the `invoice_number` field) and potentially `ps_order_invoice` for invoice details, and stores its configuration in `ps_configuration`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayAdminOrderListHeader` | Renders before the header of the order list table in the Back Office. | Used to add the “Invoice Number” column header to the order list. |
| `displayAdminOrderList` | Renders for each row (order) in the order list table in the Back Office. | Used to display the actual invoice number for each order in the newly added column. |
| `actionAdminOrdersListingFieldsModifier` | Modifies the fields array used to build the order list query and display. | Used to add the `invoice_number` field to the list of searchable and displayable fields for the `AdminOrders` controller. This is crucial for both displaying the column and enabling search. |
| `actionAdminOrdersFilterModifier` | Modifies the filter query for the order list. | Used to extend the search functionality to include the `invoice_number` field when a search query is submitted. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Order List Invoice Column & Search” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist you with any issues or questions regarding the module’s functionality.
