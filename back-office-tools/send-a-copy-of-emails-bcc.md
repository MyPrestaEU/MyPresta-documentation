---
title: "Send a copy of emails (BCC) - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Send a copy of emails (BCC) PrestaShop module by MyPresta.eu."
sidebar:
  label: "Send a copy of emails (BCC)"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Send a copy of emails (BCC) Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/send-a-copy-of-emails-bcc.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/send-a-copy-of-emails-bcc/)
>
> ---


# Send a copy of emails (BCC)

## 1. Requirements & Compatibility
- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)
After installation, clicking "Configure" will take you to the main configuration page for the module.

#### **MyPresta.eu Updates & Version Check**
At the top of the configuration page, you will typically see settings related to MyPresta.eu updates. These are standard for MyPresta.eu modules and help you keep your module up-to-date.

-   **What this setting does:** These fields (often labeled `mypresta_updates`, `update_`, `updatev_`) are used by the module to check for new versions available from MyPresta.eu and inform you if an update is needed. They are usually pre-filled or automatically managed.
-   **Effect of changing this setting:**
    -   *If enabled/active:* The module can periodically check for updates, notifying you in the PrestaShop back office if a new version is available.
    -   *If disabled/inactive:* You might not receive automatic notifications about module updates, requiring manual checks.
-   **Recommended value:** Leave these settings as they are, usually enabled or automatically managed, to ensure you are always informed about the latest module versions and security fixes.
-   **Merchant scenario / example:** You want to be notified when a new version of the module is released that includes new features or bug fixes, so you keep these update checks active.

#### **Main Module Settings**
Below the update settings, you will find the core configuration options for the BCC email functionality.

-   **Email Address for BCC:**
    -   **What this setting does:** This is the most crucial setting. It defines the email address where all selected BCC copies will be sent.
    -   **Effect of changing this setting:**
        -   *When set to a valid email address:* All emails selected in the list below will have a blind carbon copy sent to this address.
        -   *When left empty or set to an invalid address:* No BCC copies will be sent, even if emails are selected in the list.
    -   **Recommended value:** A dedicated email address for archiving (e.g., `archive@yourstore.com`, `support@yourstore.com`, or your personal admin email).
    -   **Merchant scenario / example:** You want all order confirmations to be copied to your customer service team's inbox, `support@yourstore.com`, so you enter this address here.

-   **Select Emails to BCC:**
    -   **What this setting does:** This section presents a list of all email templates (types of emails) that your PrestaShop store can send. You can select which specific email types you want to BCC.
    -   **Effect of changing this setting:**
        -   *When an email type is checked:* A BCC copy of that specific email type will be sent to the "Email Address for BCC" whenever your store sends it.
        -   *When an email type is unchecked:* No BCC copy will be sent for that specific email type.
    -   **Recommended value:** Select only the email types that are critical for your record-keeping or operational needs. Over-BCCing can flood an inbox. Common choices include:
        -   `order_conf` (Order confirmation)
        -   `shipped` (Order shipped)
        -   `contact_form` (Contact form submission)
        -   `password` (Password reset)
        -   `account` (New account creation)
    -   **Merchant scenario / example:** You want to keep a record of all new orders and customer inquiries. You would check `order_conf` and `contact_form` from the list.

### 2.2 Dedicated Admin Screens & Controller Views

#### **Mail BCC Management (Back Office > Advanced Parameters > Mail BCC)**
This module creates a dedicated menu item in your PrestaShop back office under "Advanced Parameters" (or similar, depending on PrestaShop version) named "Mail BCC". This screen is managed by `AdminMailBccController`.

-   **Screen Name & Menu Location:** **Advanced Parameters > Mail BCC**
-   **Available Actions & Settings:** This screen typically presents a grid (list) of all the email types you have configured to be BCC'd, along with the BCC email address. It acts as a summary and management interface for your BCC settings.
    -   You might see columns like:
        -   **ID:** Internal identifier for the BCC rule.
        -   **Email Template:** The name of the email template (e.g., `order_conf`).
        -   **BCC Email:** The email address where the copy is sent.
        -   **Enabled:** A toggle to quickly enable or disable BCC for that specific email type.
        -   **Actions:** Buttons to edit or delete the BCC rule (though often, the main module configuration page is used for bulk selection).
-   **Effect of changes:**
    -   *Enabling/Disabling a rule:* Directly controls whether a BCC copy is sent for that specific email type.
    -   *Editing a rule:* Allows you to change the BCC email address for a specific email type (if the module supports per-email BCC addresses, otherwise it will reflect the global setting).
    -   *Deleting a rule:* Removes the BCC setting for that email type.
-   **Recommended workflow for daily store management:** Use this screen to quickly review which emails are being BCC'd and to make quick enable/disable changes without going back to the main module configuration. For adding new email types or changing the primary BCC address, the main module configuration page is usually more efficient.

#### **index.php (bccmail/controllers/admin/index.php)**
This file is a standard PrestaShop practice for securing admin controller directories and typically does not present a user-facing screen or configuration options directly. It usually contains a simple `header('Location: ../../index.php?controller=AdminHome');` or similar to redirect unauthorized access, preventing direct browsing of the directory. Merchants will not interact with this file.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|---|
| **Module Configuration Page** | MyPresta.eu Updates | Enabled | Keeps you informed about module updates. |
| | **Email Address for BCC** | Your Admin Email / `archive@yourstore.com` | The destination email for all BCC copies. Critical for archiving. |
| | **Select Emails to BCC** | `order_conf`, `contact_form`, `shipped` | Choose which specific email types to copy. Prevents inbox flooding. |
| **Advanced Parameters > Mail BCC** | Email Template List | Varies by selection | Overview and quick toggle for configured BCC email types. |
| | Enabled Toggle | Enabled | Quickly activate/deactivate BCC for a specific email type. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I've configured the module, but I'm not receiving any BCC emails. What should I check?**
A:
1.  **Double-check the BCC Email Address:** Go to **Modules > Module Manager > Configure** for "Send a copy of emails (BCC)" and ensure the "Email Address for BCC" is correctly spelled and valid.
2.  **Verify Selected Email Types:** Make sure the specific email types you expect to be copied (e.g., `order_conf`) are actually checked in the module's configuration.
3.  **Check Spam Folder:** The BCC emails might be landing in the spam or junk folder of the BCC recipient's inbox.
4.  **PrestaShop Email Settings:** Ensure your PrestaShop store's general email settings (**Advanced Parameters > E-mail**) are correctly configured and that your store can send emails in general. Test by sending a test email from PrestaShop.
5.  **Clear Cache:** Sometimes, PrestaShop's cache can prevent changes from taking effect immediately. Go to **Advanced Parameters > Performance** and click "Clear cache" (or "Clear Smarty cache" in older versions).

**Q: Can I send BCC copies to multiple email addresses?**
A: The module's primary configuration allows for one main BCC email address. If you need to send copies to multiple addresses, you have two options:
1.  Set the BCC email address to a distribution list or group email address that forwards to multiple recipients.
2.  Configure an email rule in the BCC recipient's inbox to automatically forward copies to other addresses based on sender or subject.

**Q: Will this module slow down my store or email sending?**
A: The impact on performance is generally negligible. Sending an additional BCC copy is a very minor operation for the mail server. The module uses PrestaShop's standard email sending mechanism, simply adding an extra recipient.

**Q: My custom theme has custom email templates. Will this module still work?**
A: Yes, the module hooks into PrestaShop's core `Mail` class, which is responsible for sending all emails, regardless of whether they use default or custom templates. As long as PrestaShop is sending the email, this module can BCC it.

**Q: How do I translate the module's interface into another language?**
A: Go to **International > Translations** in your PrestaShop back office. Select "Installed modules translations", choose your theme, and then select "Send a copy of emails (BCC)". You can then translate any strings displayed by the module in the back office.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical implementation of the "Send a copy of emails (BCC)" module for developers and webmasters.

### 4.1 Architecture Overview
The "Send a copy of emails (BCC)" module (`bccmail`) primarily functions by overriding PrestaShop's core `Mail` class. This is a common and powerful technique in PrestaShop to modify core behavior without directly editing core files. By overriding `Mail.php`, the module intercepts all email sending operations and injects the BCC functionality based on its configuration. It follows a standard PrestaShop module structure with a main module file, admin controllers for configuration, and an override class.

### 4.2 Controllers (`controllers/`)

-   **Front-Office Controllers**: This module does not have any dedicated front-office controllers as its functionality is entirely back-office and server-side.

-   **Back-Office Admin Controllers**:
    *   `bccmail/controllers/admin/AdminMailBcc.php`
        *   **Class name & parent class:** `AdminMailBccController` extends `ModuleAdminController`.
        *   **Tab name and managed entity:** This controller manages the "Mail BCC" tab under "Advanced Parameters". It's responsible for displaying and managing the list of configured BCC email types. It likely uses PrestaShop's `HelperList` or `HelperView` to render a grid of `MailBcc` objects (or a representation of the module's configuration).
        *   **Responsibility:** Handles the display of the BCC configuration summary, potentially allowing for individual rule activation/deactivation or deletion. It interacts with the module's configuration data (likely stored in `ps_configuration` or a custom table if more complex data is needed per BCC rule).
    *   `bccmail/controllers/admin/index.php`
        *   **Class name & parent class:** Not a class, but a security file.
        *   **Responsibility:** This file is a standard PrestaShop security measure. It typically contains `header('Location: ../../index.php?controller=AdminHome');` or similar to prevent direct directory listing and unauthorized access to the `controllers/admin` directory. It does not provide any functional logic for the module itself.

### 4.3 Core Classes & Models (`classes/`)

-   `bccmail/override/classes/Mail.php`
    *   **What database table it interacts with:** Indirectly interacts with `ps_configuration` to retrieve the module's settings (BCC email address and selected email templates).
    *   **Whether it extends `ObjectModel`:** No, it overrides the core `Mail` class.
    *   **Key public methods and business logic encapsulated:**
        *   This file contains the core logic for intercepting email sending. It overrides the `send()` method (or a similar method) of the original `Mail` class.
        *   Inside the overridden `send()` method, it will:
            1.  Retrieve the module's configuration: the global BCC email address and the list of email templates selected for BCC.
            2.  Check if the current email being sent (identified by its template name, e.g., `order_conf`) is in the list of selected BCC templates.
            3.  If a match is found, it modifies the email headers or parameters to include the configured BCC email address before calling the parent `Mail::send()` method to dispatch the email.
        *   This ensures that the BCC recipient is added to the email's blind carbon copy list, making them invisible to the primary recipients.

-   `bccmail/override/classes/index.php`
    *   **Responsibility:** Similar to `controllers/admin/index.php`, this is a security file to prevent direct directory listing of the `override/classes` directory. It typically contains a blank PHP tag or a redirect.

### 4.4 JavaScript Assets (`views/js/`)

-   `bccmail/views/templates/admin/js/bccmail.js`
    *   **Scope:** Back-office.
    *   **What event listeners it binds:** This script is likely used on the module's configuration page or the `AdminMailBccController` screen. It could bind listeners for:
        *   Form submission events to handle saving configuration.
        *   Checkbox changes for selecting email templates to BCC.
        *   Input field validation for the BCC email address.
        *   AJAX calls to update settings dynamically without a full page reload.
    *   **What DOM manipulation, modal popups, animation, or external third-party SDK calls it executes:** Might perform simple DOM manipulations like showing/hiding elements based on selections, displaying success/error messages, or basic form validation. It's unlikely to involve complex animations or third-party SDKs for this module's functionality.

### 4.5 CSS Stylesheets (`views/css/`)
The module does not appear to include any custom CSS files in its archive. It likely relies on PrestaShop's default back-office styling for its configuration forms and lists, or inline styles if absolutely necessary.

### 4.6 Smarty Template Structure (`views/templates/`)

-   **Hook templates (`views/templates/hook/`)**: None explicitly listed, but the module's main configuration form (`getContent()`) would render its settings using a Smarty template, typically located in `views/templates/admin/configure.tpl` or similar, even if not explicitly listed in the inventory as a separate file.
-   **Admin templates (`views/templates/admin/`)**:
    *   `bccmail/lib/searchTool/views/scripts.tpl`
        *   **Purpose:** This template is likely part of a helper or utility library within the module (e.g., a search tool for email templates). It would contain JavaScript or Smarty logic to render search inputs, filter lists, or handle dynamic content loading within the admin interface. It's not a standalone page but a component.
-   **Front-office templates (`views/templates/front/`)**: None. The module has no front-office presence.

### 4.7 Database Schema & Hooks Map

-   **Database Tables**:
    *   The module primarily stores its configuration in PrestaShop's `ps_configuration` table.
        *   `PS_CONFIGURATION` keys would include:
            *   `BCCMAIL_EMAIL_ADDRESS`: Stores the main email address for BCC.
            *   `BCCMAIL_SELECTED_TEMPLATES`: Stores a serialized array or comma-separated string of the email template names selected for BCC.
            *   `MYPRESTA_UPDATES`, `UPDATE_`, `UPDATEV_`: For module update checks.
    *   No custom SQL tables are explicitly created by this module based on the provided inventory.

-   **Registered Hooks Table**:
    The module does not register any standard display hooks (like `displayHeader`, `displayRightColumn`, `displayFooter`) as it has no front-office presence. Its core functionality relies on overriding the `Mail` class rather than using traditional PrestaShop hooks for email sending.

    However, it implicitly "hooks" into the email sending process via its override.
    *   **`actionEmailSend` (Implicit via override)**: While not a formally registered hook, the module's `override/classes/Mail.php` effectively intercepts the `Mail::send()` method, which is the core action of sending an email. This is where the BCC logic is injected.
        *   **Execution Timing:** Every time `Mail::send()` is called by PrestaShop (e.g., on order confirmation, customer registration, contact form submission).
        *   **Technical Purpose:** To add the configured BCC recipient to the email before it is dispatched by PrestaShop's mailer.

## 5. Official Support & Updates
For the latest module updates, technical support, and additional resources, please visit your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the "Send a copy of emails (BCC)" module.
