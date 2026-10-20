---
title: "Simple password recovery - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Simple password recovery PrestaShop module by MyPresta.eu."
sidebar:
  label: "Simple password recovery - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Simple password recovery Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/simple-password-recovery.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/simple-password-recovery/)
>
> ---


# Simple password recovery

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No unusual server configurations are required.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

The “Simple password recovery” module is designed to be largely plug-and-play, replacing the default PrestaShop password recovery flow with minimal configuration required.

When you navigate to **Modules > Module Manager** and click “Configure” next to “Simple password recovery”, you will typically find a straightforward configuration interface.

**What this setting does:** This screen allows you to enable or disable the module’s core functionality and potentially adjust minor behavioral settings. The primary purpose is to activate the simplified password recovery process.

**Effect of changing this setting:**

- **When enabled:** The module takes over the default PrestaShop password recovery mechanism. When a customer requests a password reset, they will receive an email with a unique, secure link that directs them to a dedicated page to set their new password. This simplifies the user experience significantly.
- **When disabled:** The module’s functionality is deactivated. Your PrestaShop store will revert to its default, standard password recovery process, which may involve more steps or different verification methods for the customer.

**Recommended value:** **Enabled (YES)**. The core benefit of this module is to simplify the password recovery process. Keeping it enabled ensures your customers benefit from this improved experience.

**Merchant scenario / example:**
You’ve noticed customers frequently contact support because they struggle with the default password recovery. By enabling this module, you provide a direct, one-click link in the email, allowing them to instantly set a new password. This reduces confusion and gets them back to shopping faster.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Module Status (Enable/Disable) | Enabled | Activates or deactivates the simplified password recovery process. When enabled, customers receive a direct link to set a new password. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My customers are not receiving the password reset emails.**
A:

- **Check Spam Folders:** Advise customers to check their spam or junk mail folders.
- **Email Configuration:** Verify your PrestaShop email settings under **Advanced Parameters > E-mail**. Ensure your SMTP settings are correct or that the PHP `mail()` function is working.
- **Module Conflicts:** Temporarily disable other modules that might interfere with email sending or customer account management to rule out conflicts.
- **Server Logs:** Check your server’s mail logs for any errors related to outgoing emails.

**Q: The password reset link takes customers to a blank page or an error.**
A:

- **Clear Cache:** Go to **Advanced Parameters > Performance** and clear your Smarty cache, browser cache, and module cache.
- **URL Rewriting:** Ensure URL rewriting is enabled in PrestaShop (**Shop Parameters > SEO & URLs**) and that your `.htaccess` file is correctly configured.
- **Module Integrity:** Re-upload the module files via FTP to ensure no files are corrupted or missing.
- **Theme Compatibility:** While rare, a highly customized theme might have JavaScript conflicts. Check your browser’s developer console for any JavaScript errors.

**Q: Can I customize the appearance of the new password page?**
A: Yes, the module uses standard PrestaShop templating. The appearance is primarily controlled by your active PrestaShop theme’s CSS and the module’s own CSS (`spreset/views/css/spreset.css`). Developers can override these styles in your theme’s custom CSS or by modifying the module’s template files (`views/templates/front/password-change-form.tpl`, `views/templates/front/simple-reset-page.tpl`, `views/templates/front/simple-reset.tpl`).

**Q: Does this module work with multi-language stores?**
A: Yes, like most PrestaShop modules, the text strings are translatable. You can translate the module’s phrases via **International > Translations** in your Back Office, selecting “Installed modules translations” and then finding “Simple password recovery”.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters working with the “Simple password recovery” module.

### 4.1 Architecture Overview

The “Simple password recovery” module overrides the default PrestaShop password recovery mechanism by introducing custom front controllers to handle the token generation, email sending, and the new password setting process. It leverages PrestaShop’s MVC pattern, with dedicated controllers for different stages of the recovery. The module’s main file (`index.php`) handles installation, uninstallation, and the primary configuration form.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `controllers/front/changepass.php`
    - **Class Name**: `SpresetChangepassModuleFrontController` (extends `ModuleFrontController`)
    - **Responsibility**: This controller is responsible for displaying the form where a customer can set their new password after clicking the secure reset link. It validates the token provided in the URL and handles the submission of the new password.
  - `controllers/front/index.php`
    - **Class Name**: `SpresetIndexModuleFrontController` (extends `ModuleFrontController`)
    - **Responsibility**: This controller likely serves as a fallback or a general entry point for the module’s front-office functionality, potentially redirecting or handling initial requests related to the password reset process. In many cases, it might be a placeholder or used for specific routing.
  - `controllers/front/simplereset.php`
    - **Class Name**: `SpresetSimpleresetModuleFrontController` (extends `ModuleFrontController`)
    - **Responsibility**: This controller is the core of the simplified reset process. It receives the initial password reset request (e.g., from the standard PrestaShop “Forgot password” form), generates the secure token, sends the email with the unique reset link, and handles the initial validation of the customer’s email address.
- **Back-Office Admin Controllers**: None. The module’s configuration is handled directly within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

The module does not appear to define custom classes extending `ObjectModel` or other core PrestaShop classes within a dedicated `classes/` directory. Its logic is primarily encapsulated within the main module file and its front controllers.

### 4.4 JavaScript Assets (`views/js/`)

- `views/js/spreset.js`
  - **Scope**: Front-office.
  - **Details**: This script likely handles client-side validation for the new password form (e.g., checking if passwords match, minimum length requirements) and potentially AJAX submissions for the password change. It might also include UI enhancements or interactions specific to the password reset page. Developers should inspect this file for specific event listeners (e.g., `submit` on the password form) and any custom functions.

### 4.5 CSS Stylesheets (`views/css/`)

- `views/css/spreset.css`
  - **Scope**: Front-office customer styling.
  - **Details**: This stylesheet provides specific styling for the module’s front-office components, primarily the new password entry form and the associated pages. It ensures that the password recovery interface looks presentable and integrates reasonably well with various themes. Developers can inspect this file to identify key CSS class selectors (e.g., `.spreset-form`, `.spreset-input`, `.spreset-button`) that can be overridden in their theme’s custom CSS file to match the store’s branding.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Front-office templates (`views/templates/front/`)**:

  - `views/templates/front/password-change-form.tpl`
    - **Purpose**: This template likely renders the actual form where the customer inputs and confirms their new password. It would contain input fields for “New Password” and “Confirm New Password,” along with a submit button.
  - `views/templates/front/simple-reset-page.tpl`
    - **Purpose**: This template might serve as the main wrapper or layout for the simplified password reset process, potentially including messages, instructions, and embedding other partial templates like `password-change-form.tpl`.
  - `views/templates/front/simple-reset.tpl`
    - **Purpose**: Similar to `simple-reset-page.tpl`, this template is part of the front-office display for the password reset flow. It could be used for the initial “enter your email” form or for displaying success/error messages related to the reset request.
- **Module-specific templates (`views/templates/`)**:

  - `views/templates/spreset.tpl`
    - **Purpose**: This template is likely used for the main module configuration in the Back Office (if `getContent()` renders a template) or for a generic display hook if the module has a simple output for a hook. Given the module’s nature, it’s more probable for the Back Office configuration.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: The module does not appear to create custom SQL tables. It likely utilizes existing PrestaShop tables (e.g., `ps_customer` for customer data, `ps_configuration` for module settings) and generates temporary tokens without persistent storage in a dedicated table. Tokens are typically stored in the session or passed via URL parameters with a short expiry.
- **Registered Hooks Table**:
  The module does not explicitly list registered hooks in the provided information, but based on its functionality, it would implicitly interact with the standard PrestaShop password recovery flow, which is often triggered by the `displayCustomerAccountForm` or `actionAuthenticationBefore` hooks, or by overriding core PrestaShop controllers.
  The module’s main file (`index.php`) would register its front controllers to handle specific routes, effectively “hooking” into the URL routing system rather than traditional `display` or `action` hooks for visual output.

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the “Simple password recovery” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to ensuring the optimal performance and compatibility of our modules with the latest PrestaShop versions.
