---
title: "Additional checkboxes during register - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Additional checkboxes during register PrestaShop module by MyPresta.eu."
sidebar:
  label: "Additional checkboxes during register - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Additional checkboxes during register Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/additional-checkboxes-during-register.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/additional-checkboxes-during-register/)
>
> ---


# Additional checkboxes during register

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required, which are typically available on most PrestaShop-compatible hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the module, accessed by clicking “Configure” after installation.

- **What this setting does:** This screen primarily handles the general module settings and allows you to manage updates.
- **Effect of changing this setting:**
  - `mypresta_updates`: This is a general setting for MyPresta.eu modules to check for updates.
    - *When enabled:* The module will periodically check MyPresta.eu for new versions, notifying you in the Back Office if an update is available. This helps you keep your module secure and up-to-date with the latest features and bug fixes.
    - *When disabled:* The module will not automatically check for updates. You would need to manually check your MyPresta.eu account for new versions.
  - `update_`: This setting is related to the update check functionality.
  - `updatev_`: This setting is related to the update check functionality.
- **Recommended value:** For `mypresta_updates`, it is generally **recommended to keep it enabled** to ensure you are always informed about the latest module versions. The other two settings are internal and should generally be left as they are.
- **Merchant scenario / example:** You want to ensure your store is always running the most secure and feature-rich version of the module. Enabling update checks means you’ll be notified directly in your PrestaShop admin when a new version is released, making it easy to stay current.

### 2.2 Dedicated Admin Screens & Controller Views

#### AdminAddTosListController (Back Office > Modules > Additional Checkboxes > Checkboxes List)

This screen is where you define and manage all the individual checkboxes that will appear during customer registration.

- **Screen Name & Menu Location:** You can find this screen by navigating to **Modules > Additional Checkboxes > Checkboxes List** in your PrestaShop Back Office menu.
- **Available Actions & Settings:**
  - **List of Checkboxes:** This page displays a table of all the custom checkboxes you have created. Each row shows the checkbox’s name, whether it’s required, its status (enabled/disabled), and its position.
  - **Add New Checkbox:** There will be a button (e.g., “Add new checkbox” or a plus icon) to create a brand new checkbox. When adding/editing a checkbox, you will typically configure:
    - **Name/Label:** The text that appears next to the checkbox (e.g., “I agree to the Privacy Policy”). This should be clear and concise.
    - **Link (Optional):** A URL to a page (e.g., your Privacy Policy page, a specific terms page) that customers can click to read the full details. This is crucial for transparency.
    - **Required:** A toggle switch (Yes/No) to determine if the customer *must* check this box to complete registration.
      - *When enabled (Yes):* Customers cannot register without checking this box. This is ideal for essential legal agreements.
      - *When disabled (No):* Customers can register even if they don’t check this box. This is suitable for optional consents like newsletter subscriptions.
    - **Active:** A toggle switch (Yes/No) to enable or disable the checkbox’s display on the front office.
      - *When enabled (Yes):* The checkbox will be visible on the registration form.
      - *When disabled (No):* The checkbox will be hidden from the registration form but retained in the Back Office for future use.
    - **Position:** An integer to control the order in which checkboxes appear on the registration form. Lower numbers appear higher up.
  - **Edit/Delete:** Each checkbox in the list will have actions to edit its details or delete it entirely.
- **Effect of changes:**
  - **Adding a new checkbox:** The new checkbox will immediately appear on your customer registration form (if active) and on the customer’s “My Personal Information” page.
  - **Editing a checkbox:** Changes to the label, link, required status, or active status will be reflected instantly on the front office.
  - **Deleting a checkbox:** The checkbox will be removed from the front office. Existing customer consents for this specific checkbox will remain recorded in the history but no new consents can be given.
- **Recommended workflow for daily store management:**
  1. **Identify Consent Needs:** Before adding, determine what specific consents you need (e.g., Privacy Policy, Newsletter, Age Verification, specific service terms).
  2. **Create Content Pages:** Ensure you have dedicated CMS pages (or external links) for each policy or term you want to link to.
  3. **Add Checkboxes:** Go to “Checkboxes List” and click “Add new checkbox.” Fill in the label, link, set it as required/optional, and activate it.
  4. **Order Checkboxes:** Use the “Position” field to arrange them logically.
  5. **Review Front Office:** Always test the registration process on your store’s front office after making changes to ensure everything displays and functions as expected.

#### AdminAddTosHistoryController (Back Office > Modules > Additional Checkboxes > History)

This screen provides a historical record of customer consents for each checkbox.

- **Screen Name & Menu Location:** You can find this screen by navigating to **Modules > Additional Checkboxes > History** in your PrestaShop Back Office menu.
- **Available Actions & Settings:**
  - **Consent History Table:** This page displays a detailed log of when each customer agreed (or disagreed) to a specific checkbox.
  - **Columns typically include:**
    - **Customer Name:** The name of the customer.
    - **Checkbox Name:** The label of the checkbox they interacted with.
    - **Consent Status:** Whether they accepted (checked) or declined (unchecked) the box.
    - **Date:** The timestamp of when the consent was recorded.
    - **IP Address:** The IP address from which the consent was given (important for legal compliance).
  - **Filtering/Searching:** You can usually filter this list by customer, checkbox, or date range to find specific consent records.
- **Effect of changes:** This screen is primarily for viewing and auditing. You cannot directly modify consent records here, as they represent historical facts.
- **Recommended workflow for daily store management:**
  - **Auditing & Compliance:** Use this screen to verify customer consents if there are any disputes or for internal compliance audits.
  - **Data Privacy Requests:** If a customer requests to know what data you hold or what they’ve consented to, this history provides a clear record.

#### index.php (addtos/controllers/admin/index.php)

This file is a placeholder and typically contains a simple `header('Location: ../../../index.php?controller=AdminHome');` or similar redirect to prevent direct access to the directory. It does not represent a configurable screen for the merchant.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | MyPresta.eu Updates Check | Enabled | Notifies you of new module versions for security and features. |
| **Checkboxes List** | Checkbox Name/Label | N/A (User Defined) | The visible text next to the checkbox on the registration form. |
| **Checkboxes List** | Link (URL) | N/A (User Defined) | URL to a policy page; provides details for the checkbox. |
| **Checkboxes List** | Required | No (Optional) | If Yes, customer *must* check to register. If No, it’s optional. |
| **Checkboxes List** | Active | Yes | If Yes, checkbox is visible on front office. If No, it’s hidden. |
| **Checkboxes List** | Position | N/A (User Defined) | Determines the display order of checkboxes on the form. |
| **History** | Customer Name | N/A (View Only) | Displays which customer gave consent. |
| **History** | Checkbox Name | N/A (View Only) | Displays which checkbox was interacted with. |
| **History** | Consent Status | N/A (View Only) | Shows if the customer accepted or declined. |
| **History** | Date | N/A (View Only) | Timestamp of the consent record. |
| **History** | IP Address | N/A (View Only) | IP address from which consent was given. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve added a new checkbox, but it’s not showing up on the registration page.**
**A1:**

- **Check “Active” status:** Go to **Modules > Additional Checkboxes > Checkboxes List** and ensure the “Active” switch for your checkbox is set to “Yes.”
- **Clear Cache:** Sometimes PrestaShop’s cache can prevent new content from appearing immediately. Go to **Advanced Parameters > Performance**, scroll down to “Clear cache” and click “Clear cache.”
- **Module Position:** Ensure the module is hooked correctly. While the module usually handles this automatically, if you’ve made theme modifications, it might be worth checking the module’s hooks in **Design > Positions** (or **Modules > Positions** in older versions). The module typically uses `displayAdditionalCustomerFormFields` or similar hooks.

**Q2: My checkbox text is too long and looks bad on mobile.**
**A2:**

- **Keep it concise:** Try to shorten the checkbox label to its essence (e.g., “Agree to Privacy Policy” instead of “I have read and agree to the terms and conditions of the privacy policy of this website”).
- **Use links:** Put the detailed information on a separate CMS page and link to it from the checkbox label. This keeps the form clean while providing full transparency.
- **Theme Customization:** If the issue persists, your theme’s CSS might be limiting the display. A webmaster can adjust the CSS for the `.addtos-checkbox` or similar classes to improve responsiveness.

**Q3: Can I translate the checkbox labels into different languages?**
**A3:** Yes! When you edit a checkbox in **Modules > Additional Checkboxes > Checkboxes List**, you should see a language selector next to the “Name/Label” field (often a flag icon). Click on the flag to switch to another language and enter the translated text for that language. Remember to save your changes for each language.

**Q4: What happens if I delete a checkbox? Does it delete the customer’s consent history?**
**A4:** No, deleting a checkbox from the “Checkboxes List” will remove it from the front-office registration form, but it **will not delete the historical consent records** that customers previously gave for that checkbox. Those records remain in the “History” section for auditing and compliance purposes. New customers simply won’t see that checkbox anymore.

**Q5: I want to change the order of the checkboxes on the registration page.**
**A5:** Go to **Modules > Additional Checkboxes > Checkboxes List**. In the table, you should see a “Position” column. You can usually drag and drop the rows to reorder them, or there might be up/down arrows or an editable number field to change the position. Remember to save your changes if required.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Additional checkboxes during register” module follows a standard PrestaShop MVC (Model-View-Controller) pattern, primarily extending `Module` for its core functionality and `AdminController` for Back Office management. It leverages PrestaShop’s hook system to inject custom fields into the customer registration and identity forms and to record consent data. The module introduces custom database tables to store checkbox definitions and customer consent history.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: This module does not use dedicated front controllers. All front-office interactions (displaying checkboxes, processing consent) are handled directly via PrestaShop’s core customer controllers by leveraging specific hooks.
- **Back-Office Admin Controllers**:

  - `addtos/controllers/admin/AdminAddTosHistory.php`
    - **Class name & parent class**: `AdminAddTosHistoryController` extends `ModuleAdminController`.
    - **Tab name and managed entity**: Manages the historical records of customer consents. It’s accessible via the “History” tab under the module’s main menu. This controller displays a `list` view of the `TosHistory` objects, showing customer, checkbox, consent status, date, and IP. It does not allow editing or adding records, as it’s a historical log.
  - `addtos/controllers/admin/AdminAddTosList.php`
    - **Class name & parent class**: `AdminAddTosListController` extends `ModuleAdminController`.
    - **Tab name and managed entity**: Manages the definition of the custom checkboxes. It’s accessible via the “Checkboxes List” tab. This controller provides `list`, `add`, and `edit` views for `Tos` objects, allowing administrators to define the checkbox label, link, required status, active status, and position.
  - `addtos/controllers/admin/index.php`
    - This is a standard placeholder file to prevent directory listing. It typically contains `header('Location: ../../../index.php?controller=AdminHome');` or similar. It has no functional role in the module’s logic.

### 4.3 Core Classes & Models (`classes/`)

The module’s core classes are likely defined within the main `addtos.php` file or directly within the `classes/` directory if present (though the inventory suggests they might be in the main file).

- `Tos` (Likely defined within `addtos.php` or `classes/Tos.php`):

  - **Database table**: `ps_addtos_tos` (or similar, based on `tos` entity name).
  - **Extends `ObjectModel`**: Yes.
  - **`$definition` fields**:
    - `id_tos`: Primary key.
    - `name`: `HTML` field, `isLang` (multilingual) - the checkbox label.
    - `link`: `HTML` field, `isLang` (multilingual) - the URL for more information.
    - `required`: `BOOL` - whether the checkbox is mandatory.
    - `active`: `BOOL` - whether the checkbox is currently displayed.
    - `position`: `INT` - display order.
  - **Key public methods**: Standard `ObjectModel` methods for CRUD operations.
- `TosHistory` (Likely defined within `addtos.php` or `classes/TosHistory.php`):

  - **Database table**: `ps_addtos_toshistory` (or similar, based on `toshistory` entity name).
  - **Extends `ObjectModel`**: Yes.
  - **`$definition` fields**:
    - `id_toshistory`: Primary key.
    - `id_customer`: `INT` - ID of the customer who gave consent.
    - `id_tos`: `INT` - ID of the checkbox.
    - `accepted`: `BOOL` - `1` if accepted, `0` if declined (or `NULL` if optional and not checked).
    - `date_add`: `DATE` - timestamp of consent.
    - `ip_address`: `STRING` - IP address of the customer at the time of consent.
  - **Key public methods**: Primarily for `add` and `read` operations, as history records are immutable.

### 4.4 JavaScript Assets (`views/js/`)

The inventory indicates no specific JavaScript files are present. This suggests that any client-side validation or dynamic behavior for the checkboxes is handled either by PrestaShop’s core JS, the theme’s JS, or is not a primary feature of this module (relying on server-side validation).

### 4.5 CSS Stylesheets (`views/css/`)

The inventory indicates no specific CSS files are present. This implies that the module relies on the default PrestaShop styling for form elements or the active theme’s CSS to style the checkboxes. Developers looking to customize the appearance would target standard form input selectors or potentially classes added by the module in its templates.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `addtos/views/templates/hook/addtos_bo.tpl`: This template is likely used in the Back Office, possibly for displaying a module block or information within an admin page, or for rendering content within the module’s configuration page (e.g., update notifications).
- **Admin templates (`views/templates/admin/`)**: No dedicated admin templates are listed, suggesting that the `AdminAddTosListController` and `AdminAddTosHistoryController` rely on PrestaShop’s default `list.tpl` and `form.tpl` templates for rendering their views.
- **Front-office templates (`views/templates/front/`)**:
  - `addtos/views/templates/front/identity.tpl`: This template is likely hooked into the customer’s “My Personal Information” (Identity) page. It would display the list of checkboxes and the customer’s current consent status, potentially allowing them to update their preferences.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - `ps_addtos_tos`: Stores the definitions of each custom checkbox (label, link, required status, active status, position).
  - `ps_addtos_tos_lang`: Stores the multilingual content for `name` and `link` fields of the `ps_addtos_tos` table.
  - `ps_addtos_toshistory`: Stores the historical records of customer consents (customer ID, checkbox ID, accepted status, timestamp, IP address).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionValidateOrder` | After an order is validated. | Potentially used for recording consent related to order-specific terms, though less common for registration checkboxes. |
| `validateCustomerFormFields` | During customer registration form submission validation. | Crucial for server-side validation of required checkboxes. If a required checkbox is not checked, this hook would prevent registration. |
| `displayAdditionalCustomerFormFields` | Renders additional fields on the customer registration form. | Primary hook for displaying the custom checkboxes on the front-office registration page. |
| `displaytermsAndConditions` | Renders terms and conditions content. | Could be used to display checkboxes near the standard T&C, or as an alternative. |
| `displayvalidateCustomerFormFields` | Renders validation messages for customer form fields. | Used to display error messages if a required checkbox is not checked. |
| `additionalCustomerFormFields` | Similar to `displayAdditionalCustomerFormFields`, potentially for different contexts or versions. | Another hook for injecting custom fields into customer forms. |
| `termsAndConditions` | Similar to `displaytermsAndConditions`. | Another hook for injecting terms and conditions. |
| `actionCustomerAccountAdd` | After a new customer account is successfully created. | Used to record the customer’s consent choices for all active checkboxes into the `ps_addtos_toshistory` table. |
| `displayAdminCustomers` | Renders content on the Admin Customers list/edit page. | Could be used to display a summary of a customer’s consents directly in their Back Office profile. |
| `displayCustomerAccountForm` | Renders content on the customer’s “My Personal Information” (Identity) page. | Used to display the checkboxes and allow customers to view/update their consent preferences post-registration. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Additional checkboxes during register” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and configuration.
