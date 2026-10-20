---
title: "Credit slip number change - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Credit slip number change PrestaShop module by MyPresta.eu."
sidebar:
  label: "Credit slip number change - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Credit slip number change Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/credit-slip-number-change.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/credit-slip-number-change/)
>
> ---


# Credit slip number change

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required by PrestaShop itself and are sufficient for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This module has a very simple configuration page, primarily for internal MyPresta.eu updates. The core functionality of changing credit slip numbers is accessed directly from the order details page.

- **Menu Location:** Back Office > Modules > Module Manager > Search for “Credit slip number change” > Click “Configure”.

| Setting / Option | What this setting does | Effect of changing this setting | Recommended value | Merchant scenario / example |
| --- | --- | --- | --- | --- |
| **MyPresta.eu updates** | This setting controls whether the module checks for updates from MyPresta.eu. | *When enabled:* The module will periodically check for new versions and notify you in the back office. *When disabled:* The module will not check for updates automatically. | YES | Keeping this enabled ensures you are always aware of new versions, bug fixes, and feature enhancements for the module. |

### 2.2 Dedicated Admin Screens & Controller Views

The primary functionality of this module is integrated directly into the **Order Details page** in your PrestaShop back office. There are no separate dedicated admin screens.

- **Screen Name & Menu Location:** Back Office > Orders > Orders > Click on any order to view its details.
- **Available Actions & Settings:**
  - On the Order Details page, scroll down to the “Credit Slips” section.
  - For each credit slip listed, you will see a new input field next to its current number.
  - You can type a new number into this field.
  - After entering the new number, click the “Save” button (or similar icon, usually a floppy disk or checkmark) next to the input field to apply the change.
- **Effect of changes:**
  - When you change a credit slip number and save it, the new number is immediately updated in your PrestaShop database.
  - This new number will then be reflected on the credit slip PDF generated for that specific credit slip. Both you and your customer will see the updated number on the document.
- **Recommended workflow for daily store management:**
  1. Go to **Orders > Orders** in your PrestaShop back office.
  2. Select the order for which you need to modify a credit slip number.
  3. On the Order Details page, locate the “Credit Slips” block.
  4. Find the specific credit slip you wish to change.
  5. Enter the desired new number in the provided input field.
  6. Click the save icon next to the input field.
  7. Verify the change by downloading the credit slip PDF; it should now display the new number.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | MyPresta.eu updates | YES | Controls automatic update checks for the module. |
| Order Details Page (Credit Slips section) | Credit Slip Number Input Field | N/A (User-defined) | Allows direct modification of individual credit slip numbers. Changes reflected on PDF. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I changed the credit slip number, but it’s not showing on the PDF.**
A: After changing the number, ensure you clicked the “Save” button next to the input field. Then, regenerate or re-download the credit slip PDF. If it still doesn’t show, try clearing your browser cache or PrestaShop’s Smarty cache (Advanced Parameters > Performance > Clear cache).

**Q: Can I change the number of an already validated or sent credit slip?**
A: Yes, the module allows you to change the number of any existing credit slip. The change will only affect the number displayed on the PDF, not the underlying financial transaction itself.

**Q: Is there a way to bulk edit credit slip numbers?**
A: No, this module is designed for individual credit slip number changes directly on the order details page. It does not offer a bulk editing feature. For bulk operations, custom development might be required.

**Q: What happens if I enter a duplicate credit slip number?**
A: PrestaShop’s core system might not prevent duplicate credit slip numbers, as the module directly updates the number. It is your responsibility to ensure uniqueness if your accounting practices require it. The module facilitates the change but does not enforce uniqueness constraints beyond PrestaShop’s default behavior.

**Q: The input field to change the number isn’t appearing on my order page.**
A:

1. **Check Module Installation:** Ensure the module is correctly installed and enabled in **Modules > Module Manager**.
2. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache”.
3. **Theme Compatibility:** While the module uses standard PrestaShop hooks, very heavily customized themes might sometimes interfere. If the issue persists, temporarily switch to the default PrestaShop theme to see if the field appears. If it does, your theme might require a small adjustment.
4. **PrestaShop Version:** Ensure you downloaded the correct module version for your PrestaShop installation.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Credit slip number change” module (`creditnb`) is a lightweight PrestaShop module that extends the back-office functionality by injecting a custom input field into the `displayAdminOrder` hook. This allows administrators to modify credit slip numbers directly on the order details page. The module primarily interacts with PrestaShop’s `OrderSlip` object and its associated database table to update the `number` field. It leverages standard PrestaShop module structure and templating.

### 4.2 Controllers (`controllers/`)

This module does not introduce any custom front-office or back-office controllers. All interactions are handled via the main module file (`creditnb.php`) and standard PrestaShop AJAX mechanisms for form submissions within the admin order page.

### 4.3 Core Classes & Models (`classes/`)

This module does not introduce any custom classes or models in the `classes/` directory. It directly interacts with PrestaShop’s native `OrderSlip` object.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include any custom JavaScript files. The functionality for saving the new credit slip number is handled by the form submission within the `displayAdminOrder` hook template, likely leveraging existing PrestaShop AJAX or form handling.

### 4.5 CSS Stylesheets (`views/css/`)

This module does not include any custom CSS files. The styling of the input field is expected to inherit from the PrestaShop back-office theme.

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses hook templates to inject its functionality into the PrestaShop back office.

- **Hook templates (`views/templates/hook/`)**:
  - `creditnb/views/templates/hook/displayAdminOrder16.tpl`
    - **Purpose:** This template is designed for PrestaShop 1.6.x (though the module lists 1.7.x, 8.x, 9.x compatibility, this file might be a legacy inclusion or for broader compatibility). It renders the input field and save button for changing credit slip numbers within the “Credit Slips” section of the order details page.
    - **Hook:** `displayAdminOrder`
    - **Output:** An HTML block containing a form element with an input field for each credit slip’s number and a mechanism to save the updated value.
  - `creditnb/views/templates/hook/displayAdminOrder17.tpl`
    - **Purpose:** This template is designed for PrestaShop 1.7.x, 8.x, and 9.x. It renders the input field and save button for changing credit slip numbers within the “Credit Slips” section of the order details page, adapted for the newer back-office UI.
    - **Hook:** `displayAdminOrder`
    - **Output:** An HTML block containing a form element with an input field for each credit slip’s number and a mechanism to save the updated value.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any new custom database tables.
  - It modifies the `number` column in the `ps_order_slip` (or `_order_slip`) table, which is part of PrestaShop’s core database schema.
  - Configuration settings (`mypresta_updates`, `update_`, `updatev_`) are stored in the `ps_configuration` table.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayAdminOrder` | Renders content on the PrestaShop back-office order details page. | Injects the custom input field and save mechanism for modifying credit slip numbers directly into the “Credit Slips” section of the order view. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the “Credit slip number change” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to ensuring the smooth operation and continuous improvement of our modules.
