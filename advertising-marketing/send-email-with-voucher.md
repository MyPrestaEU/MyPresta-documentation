---
title: "Send email with voucher - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Send email with voucher PrestaShop module by MyPresta.eu."
sidebar:
  label: "Send email with voucher - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Send email with voucher Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/send-email-with-voucher.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/send-email-with-voucher/)
>
> ---


# Send email with voucher

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and are usually available on any modern hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Send email with voucher)

This is the main configuration screen where you manage the settings for sending your voucher emails.

#### **Email Templates Manager Section**

This section is where you define the content and appearance of the emails that will carry your voucher codes.

- **What this section does:** This powerful tool allows you to create, edit, and manage different email templates. Each template can have its own subject line and body content, making it easy to send various types of voucher offers (e.g., “Welcome Discount,” “Birthday Gift,” “Abandoned Cart Offer”).
- **Effect of changing settings:**
  - *Creating a new template:* You define a new email design and subject line that you can later select when sending vouchers.
  - *Editing an existing template:* Changes to the subject or content will apply to all future emails sent using that specific template.
  - *Deleting a template:* The template will no longer be available for selection.
- **Recommended workflow:** Start by creating a few standard templates for your most common voucher campaigns. For example, a “Welcome” template for new customers, a “Loyalty” template for repeat buyers, and a “Special Offer” template for promotions.

#### **Voucher Engine Section**

This section is where you actually generate and send the voucher codes.

- **What this section does:** This is the core functionality for creating discount rules (vouchers) and sending them to specific email addresses. You can define the discount type (percentage, fixed amount), the value, conditions (minimum purchase, specific products), and the validity period.
- **Effect of changing settings:**
  - *Creating a new voucher:* A new discount rule is created in your PrestaShop catalog, and a unique code is generated.
  - *Sending a voucher:* An email containing the unique code and the selected template’s content is dispatched to the specified recipient(s).
  - *Associating with a customer:* The voucher can be linked to a specific customer’s account, meaning only that customer can use it.
- **Recommended workflow:**
  1. First, create or select an appropriate email template from the “Email Templates Manager” section.
  2. Then, use the “Voucher Engine” to define your discount parameters (e.g., 10% off, valid for 30 days, minimum purchase $50).
  3. Specify the recipient email address(es).
  4. Choose whether to associate the voucher with an existing customer account.
  5. Click “Send” to generate and dispatch the personalized voucher.

#### **Specific Settings within the Configuration Page**

While the module’s primary interface is through the “Email Templates Manager” and “Voucher Engine” sections, there are underlying configuration keys that control default behavior. These are often managed implicitly by the module’s interface, but it’s good to understand their purpose.

- **Mail title**

  - **What this setting does:** This is the default subject line for the emails sent with vouchers, if not overridden by a specific template.
  - **Effect of changing this setting:**
    - *When set to “Your Special Discount”:* Emails will default to this subject line.
    - *When changed to “Exclusive Offer from [Your Shop Name]”:* All new emails (without a specific template overriding it) will use this new subject.
  - **Recommended value:** Something clear and enticing, like “Your Exclusive Voucher from [Your Shop Name]”.
  - **Merchant scenario / example:** You want all your voucher emails to have a consistent brand message in the subject line.
- **Email template file**

  - **What this setting does:** This refers to the default email template file used for sending vouchers. The “Email Templates Manager” section provides a more user-friendly way to manage and select templates.
  - **Effect of changing this setting:**
    - *When set to `voucher_email.html`:* The module will use this specific file for the email body if no other template is selected.
  - **Recommended value:** Use the “Email Templates Manager” interface to create and select templates, as it’s more flexible and doesn’t require direct file manipulation.
  - **Merchant scenario / example:** You have a custom HTML email template file that you want to use as a base for all your voucher emails.

#### **Other Configuration Keys (Internal)**

These are internal PrestaShop configuration keys that the module might reference for its operations, but you typically won’t directly configure them within the module’s interface.

- `PS_SHOP_EMAIL`: Your store’s main contact email address. Used as the sender email for vouchers.
- `PS_SHOP_NAME`: Your store’s name. Used in email subjects or bodies.
- `PS_LANG_DEFAULT`: Your store’s default language.
- `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Setting related to employee language in the back office.
- `mypresta_updates`, `update_`, `updatev_`: Internal keys used by MyPresta.eu modules for update checks and version management.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | **Email Templates Manager** | N/A (create as needed) | Create and manage custom email templates for voucher emails. |
| Module Configuration Page | **Voucher Engine** | N/A (create as needed) | Generate unique voucher codes with specific rules and send them via email. |
| Module Configuration Page | Mail title | “Your Special Discount” (example) | Default subject line for voucher emails. |
| Module Configuration Page | Email template file | `voucher_email.html` (example) | Default HTML file used for email content. Use Email Templates Manager for better control. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My customers are not receiving the voucher emails. What should I check?**
A:

1. **Check your store’s email settings:** Go to **Advanced Parameters > E-mail** in your PrestaShop back office. Ensure your email configuration (SMTP or PHP mail) is correct and test sending a general email.
2. **Spam folders:** Ask your customers to check their spam or junk mail folders.
3. **Email template content:** Ensure your email templates are not too “spammy” (e.g., excessive use of capital letters, too many exclamation marks).
4. **Module logs:** Check if the module provides any logs or error messages during the sending process. (This might require developer assistance).

**Q: The voucher code was sent, but the customer says it doesn’t work.**
A:

1. **Check voucher validity:** In your PrestaShop back office, go to **Catalog > Discounts > Cart Rules**. Find the voucher code and check its validity dates, minimum amount, customer restrictions, and if it has already been used.
2. **Customer association:** If the voucher was associated with a specific customer, ensure the customer is logged into the correct account when trying to use it.
3. **Typos:** Ask the customer to double-check for any typos when entering the code.

**Q: Can I send the same voucher code to multiple customers?**
A: Yes, you can generate a single voucher code and send it to multiple email addresses. However, for better tracking and to prevent overuse, it’s generally recommended to generate unique codes for each recipient, especially for personalized offers. The module’s “Voucher Engine” is designed to generate unique codes.

**Q: How do I customize the look of the email templates?**
A: Use the “Email Templates Manager” section within the module’s configuration. It provides an interface to edit the subject and body of your email templates. For advanced HTML/CSS customization, you might need to edit the underlying template files (see Section 7 for developers).

**Q: The module is not displaying correctly after installation, or I see a blank page.**
A:

1. **Clear Smarty Cache:** Go to **Advanced Parameters > Performance** in your PrestaShop back office. Set “Template compilation” to “Recompile templates if the files have been updated” and “Cache” to “No”. Then, click “Clear cache” in the top right. After checking, you can revert “Cache” back to “Yes” and “Template compilation” to “Never recompile…” for performance.
2. **Check PHP version:** Ensure your PHP version is within the supported range (PHP 5.6 - 8.5).
3. **Server error logs:** Check your server’s PHP error logs for any specific error messages. This usually requires access to your hosting control panel.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Send email with voucher” module follows a standard PrestaShop module architecture, primarily leveraging the `Module` class for its core functionality and configuration. It integrates custom JavaScript and CSS for its back-office interface, particularly for the email template management and voucher generation tools. The module does not introduce custom front-office controllers or complex `ObjectModel` entities but rather interacts with PrestaShop’s built-in `CartRule` (discount) and `Mail` classes.

### 4.2 Controllers (`controllers/`)

This module does not contain any custom front-office or back-office controllers in the `controllers/` directory. All administrative logic and configuration are handled within the `getContent()` method of the main module file (`sendvouchers.php`).

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or models within a `classes/` directory. It relies on PrestaShop’s core classes, such as `CartRule` for discount management and `Mail` for sending emails.

### 4.4 JavaScript Assets (`views/js/`)

- **`sendvouchers/lib/emailTemplatesManager/js/emailTemplatesManager.js`**

  - **Scope:** Back-office (module configuration page).
  - **Responsibility:** Manages the interactive elements of the email template creation, editing, and deletion interface. This script likely handles AJAX calls to save/update template data, dynamically renders forms, and manages user interactions within the “Email Templates Manager” section. It might use jQuery for DOM manipulation and event binding.
- **`sendvouchers/lib/voucherengine/script.js`**

  - **Scope:** Back-office (module configuration page).
  - **Responsibility:** Powers the “Voucher Engine” section. This script is responsible for handling the generation of voucher codes, setting up discount rules (e.g., percentage, fixed amount, conditions), selecting email templates, and initiating the voucher sending process. It likely performs client-side validation and AJAX requests to the module’s `getContent()` method for server-side processing.

### 4.5 CSS Stylesheets (`views/css/`)

- **`sendvouchers/lib/emailTemplatesManager/css/emailTemplatesManager.css`**

  - **Scope:** Back-office admin form styling.
  - **Responsibility:** Provides styling for the “Email Templates Manager” interface, including forms for creating/editing templates, buttons, and potentially list views.
  - **Key CSS class selectors:** Developers can inspect the module’s HTML output in the back office to identify specific classes (e.g., `.email-template-form`, `.template-list-item`) for overriding in their custom admin themes or via `override.css`.
- **`sendvouchers/lib/voucherengine/ps16.css`**

  - **Scope:** Back-office admin form styling, specifically for PrestaShop 1.6 compatibility.
  - **Responsibility:** Provides styling for the “Voucher Engine” section, potentially including form layouts, input fields, and buttons, with adjustments to fit the PrestaShop 1.6 back-office theme. This file might also be loaded on newer PS versions for backward compatibility, but its primary purpose is for PS 1.6.
  - **Key CSS class selectors:** Similar to `emailTemplatesManager.css`, developers should inspect the generated HTML for specific selectors to target for overrides.

### 4.6 Smarty Template Structure (`views/templates/`)

All templates are located within the `sendvouchers/lib/emailTemplatesManager/views/` directory, indicating they are primarily used for rendering the back-office interface of the email template manager.

- **`sendvouchers/lib/emailTemplatesManager/views/buttonManager.tpl`**

  - **Scope:** Admin template.
  - **Purpose:** Likely renders buttons or controls related to managing email templates (e.g., “Add New Template,” “Manage Templates”).
- **`sendvouchers/lib/emailTemplatesManager/views/createTemplateForm.tpl`**

  - **Scope:** Admin template.
  - **Purpose:** Renders the HTML form for creating a new email template, including fields for subject, body, and potentially language selection.
- **`sendvouchers/lib/emailTemplatesManager/views/editTemplateForm.tpl`**

  - **Scope:** Admin template.
  - **Purpose:** Renders the HTML form for editing an existing email template, pre-populating fields with current template data.
- **`sendvouchers/lib/emailTemplatesManager/views/mainForm.tpl`**

  - **Scope:** Admin template.
  - **Purpose:** This is likely the main wrapper template for the “Email Templates Manager” section, orchestrating the display of the template list, creation form, and edit form.
- **`sendvouchers/lib/emailTemplatesManager/views/selectInput.tpl`**

  - **Scope:** Admin template.
  - **Purpose:** A reusable template snippet for rendering a `<select>` HTML input field, possibly for language selection or choosing an existing template.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not explicitly create custom SQL tables during `install()`.
  - It stores its configuration settings (like `sendvouchersTemplate`, `sendvouchersTitle`) in PrestaShop’s `ps_configuration` table.
  - It interacts with PrestaShop’s core `ps_cart_rule` and `ps_cart_rule_lang` tables when creating and managing discount vouchers.
- **Registered Hooks Table**:
  The module’s primary functionality is executed via its `getContent()` method in the back office. While the module description mentions “Front-Office Hooks: Header, Columns, Product, or Footer,” the provided codebase inventory does not show corresponding template files or explicit `hook` methods in `sendvouchers.php` that would render content in these front-office hooks. This suggests that if any front-office hooks are registered, they are either for internal processing (e.g., `actionFrontControllerSetMedia` for loading assets) or are remnants from previous versions and not actively used to display visual content.

  The core functionality of sending emails with vouchers is triggered by user action in the back office, not by front-office page loads.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayBackOfficeHeader` | On every back-office page load. | Potentially used to load module-specific CSS/JS for its configuration page. |
| `moduleRoutes` | During URL routing initialization. | (If implemented) To define custom friendly URLs for module pages. (Not explicitly detected in this module). |
| `actionAdminControllerSetMedia` | When an admin controller is loaded. | To add module-specific JavaScript and CSS files to the back-office configuration page. |

## 5. Official Support & Updates

For official updates, technical support, and to download the latest versions of the “Send email with voucher” module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
