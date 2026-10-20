---
title: "Add order in back office + cod fee - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Add order in back office + cod fee PrestaShop module by MyPresta.eu."
sidebar:
  label: "Add order in back office + cod fee - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Add order in back office + cod fee Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/add-order-in-back-office-cod-fee.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/add-order-in-back-office-cod-fee/)
>
> ---


# Add order in back office + cod fee

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).
- **Prerequisite Module**: This module requires a “Cash on Delivery with Fee” payment module to be installed and configured on your store. This module *extends* the functionality of such a payment module within the Back Office.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This module has a very simple configuration page. Its primary function is to enable or disable the module’s core functionality.

**Access:** Back Office > Modules > Module Manager > Search for “Add order in back office + cod fee” > Click “Configure”

#### **Enable / Disable Module Functionality**

- **What this setting does:** This is a standard toggle switch that controls whether the module’s functionality is active or inactive. When enabled, the module will automatically add COD fees to manually created orders in the Back Office. When disabled, this functionality will cease.
- **Effect of changing this setting:**
  - *When enabled (YES):* The module will actively monitor the Back Office order creation process. If you select a “Cash on Delivery with Fee” payment method while creating an order, the associated fee will be automatically calculated and added to the order total.
  - *When disabled (NO):* The module will not interfere with the Back Office order creation process. If you select a “Cash on Delivery with Fee” payment method, the fee will *not* be automatically added, and you would have to manually adjust the order total if you wish to include it.
- **Recommended value:** **YES**. To benefit from the module’s core purpose of automating COD fee inclusion, it should be enabled.
- **Merchant scenario / example:** You’re taking a phone order from a customer who wants to pay by Cash on Delivery. You go to Back Office > Orders > Add new order. After adding products and selecting the customer, you choose your “Cash on Delivery with Fee” payment method. If this module is enabled, the COD fee will instantly appear in the order summary, ensuring the customer is charged correctly. If disabled, the fee would be missing, potentially leading to an incorrect order total.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable / Disable Module | YES | Controls whether the module automatically adds COD fees to manually created Back Office orders. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve installed the module, but the COD fee isn’t appearing when I create an order in the Back Office.**
A:

1. **Check Module Status:** Go to Modules > Module Manager and ensure “Add order in back office + cod fee” is installed and **enabled**.
2. **Check Prerequisite:** This module *requires* a separate “Cash on Delivery with Fee” payment module to be installed and configured. Make sure you have such a module, and it’s properly set up with its fees. This module *extends* that functionality, it doesn’t provide the COD fee mechanism itself.
3. **Clear Cache:** Sometimes PrestaShop’s cache can prevent new module functionality from appearing immediately. Go to Advanced Parameters > Performance, and click “Clear cache” in the top right.
4. **Verify Payment Method:** Ensure you are selecting the *specific* “Cash on Delivery with Fee” payment method that your other module provides, not a generic “Cash on Delivery” option without a fee.

**Q: Will this module affect orders placed by customers on the front-office of my store?**
A: No, this module only affects the process of creating orders *manually* in the PrestaShop Back Office. It does not alter how customers place orders or how fees are calculated on the front-end checkout process.

**Q: What if I have multiple “Cash on Delivery with Fee” modules?**
A: This module is designed to integrate with the standard way PrestaShop handles payment modules and their associated fees. It should work with any “Cash on Delivery with Fee” module that properly registers its fee calculation within PrestaShop’s payment framework. If you encounter issues, please contact MyPresta.eu support.

**Q: Does this module create the “Cash on Delivery with Fee” payment option itself?**
A: No, it does not. This module is an *enhancement* for an existing “Cash on Delivery with Fee” payment module. You must have a separate payment module installed that provides the actual COD payment method and its fee configuration.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Add order in back office + cod fee” module is a lightweight PrestaShop module primarily designed to extend the `AdminOrdersController` functionality. It achieves its purpose by hooking into specific actions within the Back Office order creation process, specifically when a payment method is selected or updated. Its core logic resides within the main module file, leveraging PrestaShop’s hook system to modify existing behavior without direct core file modification. It relies on the presence of a separate “Cash on Delivery with Fee” payment module to provide the actual fee calculation logic.

### 4.2 Controllers (`controllers/`)

This module does not introduce any custom Front-Office or Back-Office controllers. Its functionality is injected into the existing `AdminOrdersController` via hooks.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or `ObjectModel` instances. All logic is contained within the main module file.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include any custom JavaScript files. The functionality is handled server-side.

### 4.5 CSS Stylesheets (`views/css/`)

This module does not include any custom CSS files.

### 4.6 Smarty Template Structure (`views/templates/`)

This module does not include any custom Smarty template files. Its configuration is handled by the standard `getContent()` method, which typically uses PrestaShop’s helper forms.

### 4.7 Database Schema & Hooks Map

**Database Tables**:
This module does not create any custom database tables. It stores its configuration (e.g., enable/disable status) in the standard `ps_configuration` table, using a key like `ADDORDERINBACKOFFICECODFEE_ENABLED`.

**Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Executed when an Admin Controller sets its media assets. | Used to potentially inject JS/CSS if needed, though this module doesn’t use it for that. It’s a common hook for admin-side modifications. |
| `actionAdminOrdersControllerSaveAfter` | Executed after an order is saved in `AdminOrdersController`. | This is the primary hook used by the module. It allows the module to inspect the newly saved order, check the selected payment method, and if it’s a COD with fee, apply the fee. |
| `displayAdminOrder` | Executed on the order detail page in the Back Office. | Could be used to display additional information related to the COD fee on the order view, though the module’s core function is to *add* the fee, not just display it. |

**Key Logic within `add-order-in-back-office-cod-fee.php`:**

The module’s core functionality is likely implemented within the `hookActionAdminOrdersControllerSaveAfter` method. This method would:

1. Retrieve the `Order` object that was just saved.
2. Identify the `PaymentModule` used for the order.
3. Check if the selected payment module is a “Cash on Delivery with Fee” type (this typically involves checking the module’s name or a specific property/method it exposes).
4. If it is, it would then call a method on that payment module (or directly calculate based on its configuration) to get the COD fee.
5. Finally, it would update the order’s total, add a new `OrderInvoice` detail (or modify an existing one) to reflect the COD fee, and persist these changes to the database. This might involve creating a new `OrderPayment` entry or adjusting the `total_paid_tax_incl` and `total_paid_tax_excl` fields of the `Order` object.

Developers should be aware that this module relies heavily on the internal structure and behavior of the “Cash on Delivery with Fee” payment module it’s interacting with. Any custom COD payment modules might require adjustments or specific compatibility checks.

## 5. Official Support & Updates

For official support, updates, and further information regarding the “Add order in back office + cod fee” module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/) or contact MyPresta.eu support directly.
