---
title: "Export Customers with address - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Export Customers with address PrestaShop module by MyPresta.eu."
sidebar:
  label: "Export Customers with address - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Export Customers with address Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/export-customers-with-address.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/export-customers-with-address/)
>
> ---


# Export Customers with address

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient for PrestaShop modules. No special hosting requirements beyond a standard PrestaShop environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” on the module will take you to its main configuration page. This screen primarily handles internal module settings related to updates.

- **What this setting does:** This section typically manages internal module update checks and version information. These settings are usually for the module’s internal use to ensure you’re running the latest version and to provide update notifications.
- **Effect of changing this setting:**
  - *`mypresta_updates`*: This is likely an internal flag to enable or disable update checks from MyPresta.eu.
  - *`update_`*: This might store the last time an update check was performed.
  - *`updatev_`*: This could store the latest available version detected.
- **Recommended value:** It’s generally recommended to leave these settings at their default values to ensure you receive important update notifications.
- **Merchant scenario / example:** You don’t typically interact with these settings directly. They work in the background to inform you if a new version of the module is available, ensuring you have access to the latest features and bug fixes.

### 2.2 Dedicated Admin Screens & Controller Views

#### 2.2.1 Export Customers with Address (Back Office > Advanced Parameters > Export Customers with address)

This is the primary screen where you will perform the customer export. You can find it under the “Advanced Parameters” menu in your PrestaShop back office.

- **Screen Name & Menu Location:** **Advanced Parameters > Export Customers with address**
- **Available Actions & Settings:**
  - When you navigate to this screen, you will see a button or a link to initiate the export process. The module automatically prepares a CSV file containing all customer data and their associated addresses.
  - The exported file will include the following columns, formatted for PrestaShop’s import tool:
    - **Customer ID**: Unique identifier for the customer.
    - **Active (0/1)**: Whether the customer account is active (1) or inactive (0).
    - **Titles ID (Mr = 1, Ms = 2, else 0)**: The ID corresponding to the customer’s title (e.g., Mr., Ms.).
    - \*\*Email \*\*\*: The customer’s email address (mandatory).
    - \*\*Password \*\*\*: The customer’s password (mandatory, usually hashed).
    - **Birthday (yyyy-mm-dd)**: The customer’s birth date.
    - \*\*Last Name \*\*\*: The customer’s last name (mandatory).
    - \*\*First Name \*\*\*: The customer’s first name (mandatory).
    - **Newsletter (0/1)**: Whether the customer is subscribed to the newsletter (1) or not (0).
    - **Opt-in (0/1)**: Whether the customer has opted in for partner offers (1) or not (0).
    - **Register date**: The date the customer registered their account.
    - **Groups (x,y,z…)**: A comma-separated list of IDs of the customer groups the customer belongs to.
    - **Default group ID**: The ID of the customer’s default group.
    - **ID / Name of shop**: The ID or name of the shop the customer is associated with (useful in multi-store environments).
    - **Address ID**: Unique identifier for the customer’s address.
    - \*\*Alias \*\*\*: An alias for the address (e.g., “My Home Address”).
    - \*\*Customer email \*\*\*: The email associated with this address (should match the customer’s email).
    - **Manufacturer**: (If applicable)
    - **Supplier**: (If applicable)
    - **Company**: The company name associated with the address.
    - … and other standard address fields like `Address1`, `Address2`, `Postcode`, `City`, `Country`, `Phone`, `Mobile Phone`, `VAT Number`, etc.
- **Effect of changes:** Clicking the export button will generate and download a CSV file to your computer. This action does not modify any data in your PrestaShop store; it only extracts it.
- **Recommended workflow for daily store management:**
  1. **Regular Backups:** Periodically export your customer data as a backup, especially before major store updates or migrations.
  2. **Marketing List Generation:** Export customer data to create lists for email marketing campaigns, segmenting by groups or registration dates.
  3. **CRM Updates:** If you use an external CRM, export data to keep it synchronized with your PrestaShop customer base.

#### 2.2.2 AdminExportCustomersController (index.php)

This file likely serves as the entry point or a helper for the `AdminExportCustomersController`, ensuring the module’s administrative interface functions correctly within the PrestaShop back office. It doesn’t present a separate configurable screen but rather facilitates the display and functionality of the main export screen.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | `mypresta_updates` | Enabled | Internal flag for MyPresta.eu update checks. Keep enabled for notifications. |
| Module Configuration Page | `update_` | (Internal) | Stores last update check timestamp. |
| Module Configuration Page | `updatev_` | (Internal) | Stores latest available module version. |
| Advanced Parameters > Export Customers with address | Export Button | N/A | Initiates download of a CSV file containing all customer and address data. |
| Advanced Parameters > Export Customers with address | Exported CSV Columns | N/A | Includes Customer ID, Active, Titles ID, Email, Password, Birthday, Last Name, First Name, Newsletter, Opt-in, Register date, Groups, Default group ID, Shop ID/Name, Address ID, Alias, Customer email, Company, and all standard address fields. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I clicked the export button, but nothing happened or the file is empty.**
**A1:**

- **Check for browser pop-up blockers:** Your browser might be blocking the file download. Look for a notification or icon in your browser’s address bar and allow downloads from your PrestaShop admin.
- **Module permissions:** Ensure the module has the necessary file system permissions to create and serve the CSV file. While rare, incorrect permissions can prevent file generation.
- **Server memory limits:** If you have a very large number of customers, the export process might hit PHP memory limits on your server. Check your server’s PHP error logs (often found in `var/logs` or your hosting control panel) for memory-related errors. You might need to temporarily increase `memory_limit` in your `php.ini` file.
- **Empty customer database:** Double-check that you actually have customers registered in your store.

**Q2: The exported CSV file looks garbled or has strange characters.**
**A2:** This is often an encoding issue.

- **Open with correct encoding:** When opening the CSV file in a spreadsheet program (like Excel), ensure you select **UTF-8** as the file origin or encoding. Most modern systems use UTF-8, and PrestaShop exports are typically in this format.
- **Check PrestaShop language settings:** Ensure your PrestaShop store’s default language and character set are correctly configured in **International > Localization**.

**Q3: Can I choose which fields to export?**
**A3:** This module exports a predefined set of customer and address fields that are compatible with PrestaShop’s native import tool. It does not offer options to select or deselect individual fields. If you need a highly customized export, you might need a more advanced export module or custom development.

**Q4: Will exporting customers affect my store’s performance?**
**A4:** For most stores, a one-time export will have a negligible impact. For stores with hundreds of thousands of customers, the export process might take a few moments and consume some server resources. It’s generally recommended to perform large exports during off-peak hours if you anticipate a very long processing time. The module is designed to be efficient, but server resources are always a factor.

**Q5: I want to re-import the customers after making changes. How do I do that?**
**A5:** This module only handles the export. To re-import, you would use PrestaShop’s native import tool:

1. Go to **Advanced Parameters > Import**.
2. Select “Customers” or “Addresses” as the entity to import.
3. Upload your modified CSV file.
4. Carefully map the columns from your CSV to the PrestaShop database fields.

Always test imports on a development or staging environment first, and ensure you have a full database backup before performing any large-scale imports on your live store. Incorrect imports can lead to data loss or corruption.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Export Customers with address” module (`exportcustomers`) is a straightforward PrestaShop module primarily focused on back-office functionality. It follows a standard PrestaShop MVC pattern for its administrative interface. The core logic resides within the main module file and a dedicated Admin Controller. It does not introduce new database tables but leverages existing PrestaShop `Customer` and `Address` `ObjectModel` structures to retrieve and format data for export. The module’s simplicity means it has no front-office components, custom classes, or complex JavaScript/CSS assets.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. This module has no front-office functionality.
- **Back-Office Admin Controllers**:

  - `exportcustomers/controllers/admin/AdminExportCustomers.php`
    - **Class name & parent class**: `AdminExportCustomersController` extending `ModuleAdminController`.
    - **Responsibility**: This is the primary controller responsible for handling the customer and address export logic. When accessed via the PrestaShop back office menu, it initiates the process of fetching customer and address data from the database, formatting it into a CSV string, and sending it as a downloadable file to the browser. It constructs the CSV header row with all the specified fields (Customer ID, Email, Address ID, Alias, etc.) and then iterates through `Customer` and `Address` objects to populate the data rows.
  - `exportcustomers/controllers/admin/index.php`
    - **Responsibility**: This is a common placeholder file in PrestaShop module admin controller directories. It typically contains a simple `header('Location: ../../index.php?controller=AdminHome')` or similar redirect to prevent direct directory listing or access, ensuring security and proper routing within the PrestaShop back office. It does not contain any functional logic for the module itself.

### 4.3 Core Classes & Models (`classes/`)

This module does not introduce any custom classes or models in the `classes/` directory. It directly utilizes PrestaShop’s core `Customer` and `Address` `ObjectModel` classes to retrieve data from the database.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include any custom JavaScript files. The export process is typically initiated by a simple form submission or a direct link, handled entirely by the PHP controller.

### 4.5 CSS Stylesheets (`views/css/`)

This module does not include any custom CSS files. Its back-office interface relies entirely on the default PrestaShop back-office styling.

### 4.6 Smarty Template Structure (`views/templates/`)

This module does not include any custom Smarty template files. The `AdminExportCustomersController` likely renders a very simple view, possibly just a button or a message, directly within its `renderForm()` or `initContent()` method, or it directly triggers a file download without rendering a complex template.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: This module does not create any custom database tables. It reads data from existing PrestaShop tables, primarily `ps_customer` and `ps_address`.

  - `ps_configuration`: The module stores its internal configuration settings (`mypresta_updates`, `update_`, `updatev_`) in the `ps_configuration` table.
- **Registered Hooks Table**:
  This module does not register any front-office hooks. Its functionality is entirely confined to the back office.
  It likely uses the `actionAdminControllerSetMedia` hook (implicitly or explicitly) for its admin controller, and potentially `displayAdminProductsExtra` or similar for its back-office menu item.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Executed when an admin controller is initialized. | Used by `ModuleAdminController` to add CSS/JS assets (though this module has none). |
| `displayAdminAdvancedParameters` | Renders content in the “Advanced Parameters” section of the back office. | Likely used to add the module’s link/entry point to the “Advanced Parameters” menu. |

## 5. Official Support & Updates

For official updates, technical support, and the latest versions of the “Export Customers with address” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu). Our support team is available to assist with any issues or questions regarding module functionality and compatibility.
