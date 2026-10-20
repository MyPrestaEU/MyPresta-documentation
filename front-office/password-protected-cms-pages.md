---
title: "Password protected CMS pages - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Password protected CMS pages PrestaShop module by MyPresta.eu."
sidebar:
  label: "Password protected CMS pages - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Password protected CMS pages Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/password-protected-cms-pages.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/password-protected-cms-pages/)
>
> ---


# Password protected CMS pages

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” on the module will take you to its main configuration screen. This screen primarily serves as an entry point to the dedicated management area for your protected CMS pages.

- **What this screen does:** This page typically provides a brief overview or a direct link to the main management interface where you will actually set up and manage your password-protected CMS pages. It might also contain general settings if the module had any, but for this module, the core functionality is managed in a separate section.
- **Effect of changing settings:** Any settings here would directly impact the module’s global behavior or appearance.
- **Recommended value:** Follow the on-screen instructions, usually clicking a button to proceed to the CMS page management.
- **Merchant scenario / example:** You’ve just installed the module. You’ll likely see a button like “Manage Protected CMS Pages” or “Configure CMS Passwords.” Clicking this will take you to the dedicated screen to start protecting your pages.

### 2.2 Dedicated Admin Screen: Manage Protected CMS Pages (Back Office > Modules > Password protected CMS pages > Configure > [Link to Management])

This is the primary screen where you will manage which CMS pages are protected and what their passwords are. You access this screen usually by clicking a link or button from the main module configuration page.

- **Screen Name & Menu Location:** You will typically find a new menu item under **Modules > Module Manager > Password protected CMS pages > Configure**, which then directs you to the management interface. The URL might look something like `admin/index.php?controller=AdminPcmsController`.
- **Available Actions & Settings:**
  - **Listing Table:** This screen will display a table listing all your existing CMS pages. For each page, you’ll see its name, ID, and whether it’s currently protected.
  - **Add/Edit Protection:** For each CMS page in the list, you will typically find an “Edit” or “Configure” button/icon. Clicking this will open a form where you can:
    - **Enable/Disable Protection:** A simple switch (Yes/No) to turn password protection on or off for that specific CMS page.
      - *When enabled:* The page will require a password to view its content on the front office.
      - *When disabled:* The page will be publicly accessible as a standard CMS page.
      - *Recommended value:* “Yes” for pages you want to protect, “No” for public pages.
      - *Merchant scenario:* You want to protect your “VIP Offers” page, so you enable protection.
    - **Set Password:** An input field where you define the password for that specific CMS page.
      - *Effect of changing:* This is the exact password customers will need to enter to view the page.
      - *Recommended value:* Choose a strong, unique password for each protected page.
      - *Merchant scenario:* You set “MYSECRETDEAL” as the password for your “VIP Offers” page.
  - **Bulk Actions:** Depending on the module version, there might be options to enable/disable protection for multiple pages at once, though individual page management is more common for password settings.
- **Effect of changes:**
  - When you enable protection and set a password for a CMS page, that page immediately becomes password-protected on your front office. Customers visiting its URL will see the password prompt.
  - Disabling protection makes the page publicly visible again.
- **Recommended workflow for daily store management:**
  1. Decide which CMS pages need to be private or exclusive.
  2. Navigate to this “Manage Protected CMS Pages” screen.
  3. Find the desired CMS page in the list.
  4. Click “Edit” or the equivalent action for that page.
  5. Enable the password protection switch.
  6. Enter a strong, unique password.
  7. Save your changes.
  8. Communicate the password to your intended audience.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Manage Protected CMS Pages** | Enable/Disable Protection | No / Yes (as needed) | Controls whether a specific CMS page requires a password to be viewed. |
|  | Password for CMS Page | (Empty) / Strong, unique password | The exact string customers must enter to access the protected content. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve set a password, but the page is still visible without it. What’s wrong?**
A:

1. **Check if protection is enabled:** Go to the “Manage Protected CMS Pages” screen and ensure the “Enable Protection” switch for that specific CMS page is set to “Yes”.
2. **Clear your browser cache:** Your browser might be showing you a cached version of the page. Try clearing your browser’s cache or opening the page in an incognito/private window.
3. **Clear PrestaShop cache:** Go to **Advanced Parameters > Performance** in your Back Office and click “Clear cache” in the top right corner. This ensures PrestaShop is serving the latest configuration.

**Q: Can I have different passwords for different CMS pages?**
A: Yes! This module is designed for exactly that. Each CMS page can have its own unique password, allowing you to create multiple tiers of protected content.

**Q: What happens if a customer enters the wrong password?**
A: The module will display an error message (e.g., “Incorrect password. Please try again.”) and the password input form will reappear, allowing the customer to re-enter the password.

**Q: Can I customize the look of the password input form?**
A: The module uses a basic styling for the password form. For advanced customization, you would need a webmaster or developer to modify the module’s CSS file (`css.css`) or override its template (`cms.tpl`).

**Q: I’ve updated my PrestaShop theme, and now the password form looks strange. What should I do?**
A: Custom themes sometimes have their own styling that can conflict with module displays.

1. **Clear PrestaShop cache:** Always try this first (**Advanced Parameters > Performance > Clear cache**).
2. **Contact your theme developer:** They might have specific instructions for module compatibility.
3. **Consult a webmaster:** A developer can inspect the CSS and HTML to identify and resolve styling conflicts.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Password protected CMS pages” module (`passcms`) primarily works by overriding the core `CmsController` to intercept requests for CMS pages. When a protected CMS page is requested, it checks for a valid password in the session. If no valid password is found, it renders a password input form instead of the actual CMS content. The module uses a dedicated Admin Controller (`AdminPcmsController`) for managing the password settings for each CMS page.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `passcms/override/controllers/front/CmsController.php`
    - **Class name & parent class**: `CmsController` (overrides core `CmsController`)
    - **Responsibility**: This is the core of the front-office functionality. It intercepts the `initContent()` method of the original `CmsController`. It checks if the requested CMS page (identified by `id_cms`) is configured as password-protected. If it is, and no valid password is in the session, it renders the `cms.tpl` template with the password input form. It also handles the POST request for password submission, validating it against the stored password and setting a session variable upon success.
  - `passcms/override/controllers/front/index.php`
    - **Class name & parent class**: Not a class, typically an empty file or a basic security measure to prevent direct directory listing.
    - **Responsibility**: Standard PrestaShop practice for `override` directories.
- **Back-Office Admin Controllers**:

  - `passcms/controllers/admin/AdminPcmsController.php`
    - **Tab name and managed entity**: Manages the password protection settings for individual CMS pages. This controller extends `ModuleAdminController` and provides the interface for listing CMS pages and configuring their passwords. It handles the CRUD operations for the `pcms` entity (though no explicit `ObjectModel` is listed, it likely interacts directly with `ps_configuration` or a custom table for password storage). It renders the grid view of CMS pages and the form for editing password settings.
  - `passcms/controllers/admin/index.php`
    - **Class name & parent class**: Not a class, typically an empty file or a basic security measure to prevent direct directory listing.
    - **Responsibility**: Standard PrestaShop practice for controller directories.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes in the `classes/` directory. This suggests that the module likely stores its configuration directly in `ps_configuration` table, using keys like `PCMS_PASSWORD_ID_CMS_X` where `X` is the `id_cms`, or it might use a custom table that is managed directly by the `AdminPcmsController` without a dedicated `ObjectModel`.

### 4.4 JavaScript Assets (`views/js/`)

The module dossier indicates no custom JavaScript files. The password submission is likely handled via a standard HTML form POST or simple inline JS if any dynamic behavior is present.

### 4.5 CSS Stylesheets (`views/css/`)

- `passcms/css.css`
  - **Scope**: Front-office customer styling.
  - **Main UI components and containers it styles**: This file contains the basic styling for the password input form displayed on protected CMS pages. It likely targets elements like the form container, input field, and submit button.
  - **Key CSS class selectors developers can override**: Developers can inspect the rendered HTML of the password form to identify specific classes (e.g., `.passcms-form`, `.passcms-input`, `.passcms-button`, `.passcms-error`) and override them in their theme’s `custom.css` or `theme.css` to match the store’s branding.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Admin templates (`views/templates/admin/`)**:

  - `passcms/admin.tpl`
    - **Purpose**: This template is likely used for the main configuration page of the module, providing the entry point or general information, potentially linking to the `AdminPcmsController` management interface.
  - `passcms/views/templates/admin/script.tpl`
    - **Purpose**: This template might contain inline JavaScript or Smarty variables that are rendered within the Back Office for the `AdminPcmsController` to handle dynamic behavior or data passing.
- **Front-office templates (`views/templates/front/`)**:

  - `passcms/views/templates/front/cms.tpl`
    - **Purpose**: This is the crucial template rendered by the overridden `CmsController` when a protected CMS page is accessed without a valid password. It contains the HTML structure for the password input form, including the input field, submit button, and any error messages.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not explicitly create a custom SQL table based on the dossier. It is highly probable that the password settings for each CMS page are stored in the `ps_configuration` table using unique configuration keys, e.g., `PCMS_PASSWORD_ID_CMS_X` where `X` is the `id_cms`.
  - `ps_configuration`: Stores module configuration values, including potentially the passwords for each CMS page.
- **Registered Hooks Table**:
  The module primarily operates via controller override rather than traditional hooks for its core functionality. However, it might register some standard hooks for general module integration or display.

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `displayBackOfficeHeader` | Renders in the `<head>` section of Back Office pages. | Used to include CSS (`css.css`) or JS for the `AdminPcmsController` interface. |
  | `displayHeader` | Renders in the `<head>` section of front-office pages. | Could be used to include front-office CSS (`css.css`) or JS if needed globally, though it’s more likely loaded conditionally by the `CmsController` override. |
  | `actionFrontControllerSetMedia` | Executed when a front controller sets its media assets. | Alternative to `displayHeader` for conditionally loading assets based on the current controller. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Password protected CMS pages” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
