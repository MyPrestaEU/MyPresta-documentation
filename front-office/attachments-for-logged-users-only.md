---
title: "Attachments for logged users only - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Attachments for logged users only PrestaShop module by MyPresta.eu."
sidebar:
  label: "Attachments for logged users only - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Attachments for logged users only Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/attachments-for-logged-users-only.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/attachments-for-logged-users-only/)
>
> ---


# Attachments for logged users only

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installing the module, click “Configure” to access its settings. This is the main screen where you control the module’s behavior.

#### **Activate feature**

- **What this setting does:** This is the master switch for the module. It determines whether the attachment restriction feature is active or inactive on your store.
- **Effect of changing this setting:**
  - *When enabled (“Enabled”):* The module will actively restrict product attachment downloads to logged-in customers only. Non-logged-in users will not be able to download attachments.
  - *When disabled (“Disabled”):* The module will be inactive. Product attachments will behave as they do by default in PrestaShop, meaning anyone (logged-in or guest) can download them.
- **Recommended value:** “Enabled” if you want to restrict attachment downloads.
- **Merchant scenario / example:** If you want to start requiring customers to log in to download manuals, set this to “Enabled”. If you’re testing or want to temporarily revert to default PrestaShop behavior, set it to “Disabled”.

#### **Download for customers only**

- **What this setting does:** This setting refines the “Activate feature” by allowing you to specify *which* customers can download attachments based on their order history.
- **Effect of changing this setting:**
  - *When enabled:* Only customers who are logged in AND have at least one order with a selected status (see “Select order states” below) will be able to download attachments. This adds an extra layer of exclusivity.
  - *When disabled:* Any logged-in customer (regardless of their order history) will be able to download attachments, provided the “Activate feature” is enabled.
- **Recommended value:** “Disabled” for most cases, allowing any logged-in customer to download. “Enabled” if you want to offer attachments as a perk for *paying* customers.
- **Merchant scenario / example:** You sell software and want to provide updates or premium guides only to customers who have actually purchased the software. You would enable this setting and select “Payment accepted” in the “Select order states” option.

#### **Select order states**

- **What this setting does:** This option appears only if “Download for customers only” is enabled. It allows you to choose which order statuses qualify a customer to download attachments. A customer must have at least one order with one of the selected statuses to gain access.
- **Effect of changing this setting:**
  - *When one or more states are selected:* Only logged-in customers with an order matching one of these statuses can download attachments.
  - *When no states are selected (and “Download for customers only” is enabled):* This configuration might lead to no customers being able to download, as no qualifying order states are defined. It’s crucial to select at least one state if you enable “Download for customers only.”
- **Recommended value:** If “Download for customers only” is enabled, select relevant statuses like “Payment accepted,” “Delivered,” or “Shipped” to grant access to customers who have successfully completed an order.
- **Merchant scenario / example:** If you want to give access to attachments only to customers whose orders have been successfully paid for and processed, you would select “Payment accepted” and “Delivered.” This prevents customers with pending or cancelled orders from accessing the files.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Activate feature | Enabled | Master switch to enable/disable attachment restriction. |
| Module Configuration | Download for customers only | Disabled | If enabled, only logged-in customers with specific order states can download. |
| Module Configuration | Select order states | (None selected) | If “Download for customers only” is active, select order statuses that grant download access. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My attachments are still downloadable by everyone, even after enabling the module. What’s wrong?**
A:

1. **Check “Activate feature”:** Ensure the “Activate feature” setting on the module’s configuration page is set to “Enabled.”
2. **Clear Cache:** PrestaShop uses caching. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). This often resolves display issues after module configuration changes.
3. **Module Position:** Ensure the module is hooked correctly. While the module handles this automatically, sometimes theme conflicts can occur.

**Q: I’ve enabled “Download for customers only” and selected order states, but my logged-in customers still can’t download.**
A:

1. **Verify Order Status:** Double-check that the customer trying to download actually has an order with one of the *exact* statuses you selected in “Select order states.”
2. **Customer Login:** Confirm the customer is indeed logged into their account.
3. **Cache:** Clear your PrestaShop cache (Advanced Parameters > Performance).

**Q: How do I translate the messages shown to non-logged-in users?**
A: The module should integrate with PrestaShop’s translation system.

1. Go to **International > Translations**.
2. Select “Installed modules translations.”
3. Choose your theme, your language, and then the “Attachments for logged users only” module.
4. You should find the relevant text strings there to translate.

**Q: Will this module work with my custom theme?**
A: Yes, the module is designed to work with standard PrestaShop attachment mechanisms. It primarily intercepts the download request rather than heavily modifying the visual display of attachments. However, if your custom theme completely overrides the way attachments are displayed or linked, minor adjustments might be needed. Always test thoroughly after installation.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Attachments for logged users only” module primarily operates by overriding the default `AttachmentController` to intercept download requests. It leverages PrestaShop’s hook system (`displayHeader`, `header`) to inject necessary JavaScript and CSS, and its main logic resides in the `atlogged.php` file, handling configuration and the core override. The module uses a simple configuration structure stored in `ps_configuration` and includes front-office controllers for AJAX interactions and potential fallback logic.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `atlogged/controllers/front/index.php`

  - **Class Name:** `AtloggedIndexModuleFrontController` (likely, based on file naming convention)
  - **Parent Class:** `ModuleFrontController`
  - **Responsibility:** This controller might serve as a general entry point for module-specific front-office actions, potentially handling redirects or displaying messages when an attachment download is restricted. It could also be a placeholder or used for specific routing.
- `atlogged/controllers/front/popuploader.php`

  - **Class Name:** `AtloggedPopuploaderModuleFrontController`
  - **Parent Class:** `ModuleFrontController`
  - **Responsibility:** This controller likely handles AJAX requests related to displaying a login/registration prompt or a specific message when a user attempts to download a restricted attachment. It might render a small template (e.g., `atlogged-ajax.tpl`) with the appropriate content.
- `atlogged/override/controllers/front/AttachmentController.php`

  - **Class Name:** `AttachmentController` (overrides core class)
  - **Parent Class:** `AttachmentControllerCore`
  - **Responsibility:** This is the most critical part of the module’s front-office logic. It directly overrides PrestaShop’s core `AttachmentController`. Its primary function is to:
    1. Check if the module is enabled (`ATLOGGED_ON`).
    2. Verify if the current user is logged in.
    3. If `ATLOGGED_C_ON` (Download for customers only) is enabled, it further checks the user’s order history against the configured `atlogged_ostates`.
    4. If the user does not meet the criteria, it prevents the default attachment download process and instead redirects the user or triggers a module-specific action (e.g., showing a login prompt via AJAX).
- `atlogged/override/controllers/front/index.php`

  - **Class Name:** `IndexController` (overrides core class)
  - **Parent Class:** `IndexControllerCore`
  - **Responsibility:** Overriding the `IndexController` is less common for attachment-specific logic. This might be used for:
    1. Global checks or redirects related to the module on the homepage.
    2. Ensuring certain module-specific assets (JS/CSS) are loaded globally.
    3. Potentially handling a redirect to the login page if an attachment link is accessed directly without being logged in from the homepage context.

#### Back-Office Admin Controllers

- None identified. The module’s configuration is handled directly within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

- None identified. The module does not appear to define custom `ObjectModel` classes. It likely works directly with existing PrestaShop core objects (e.g., `Customer`, `Order`, `Attachment`) and configuration values.

### 4.4 JavaScript Assets (`views/js/`)

- `atlogged/views/js/atlogged.js`
  - **Scope:** Front-office.
  - **Details:** This script is likely responsible for:
    1. Intercepting clicks on attachment download links (`<a>` tags with specific classes or data attributes).
    2. Making AJAX calls to `popuploader.php` or `index.php` front controllers when a restricted download is attempted by a non-qualifying user.
    3. Displaying modal popups or messages (e.g., “Please log in to download”) based on the AJAX response.
    4. Potentially redirecting users to the login page if the AJAX response dictates it.
    5. Ensuring the user experience is smooth when access is denied.

### 4.5 CSS Stylesheets (`views/css/`)

- `atlogged/views/css/atlogged.css`
  - **Scope:** Front-office customer styling.
  - **Details:** This stylesheet provides the necessary styling for any custom elements introduced by the module, such as:
    1. Styling for the login/registration prompt modal or message box.
    2. Adjustments to attachment link appearance if they are disabled or visually altered when restricted.
  - **Key CSS class selectors developers can override:** Developers should inspect the HTML output generated by the module’s templates (e.g., `atlogged-ajax.tpl`) to identify specific classes (e.g., `.atlogged-modal`, `.atlogged-message`, `.atlogged-login-button`) for theme integration and customization.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Admin templates (`views/templates/admin/`)**:

  - `atlogged/views/templates/admin/orderstates.tpl`
    - **Purpose:** This template is used within the module’s `getContent()` method in the Back Office. It renders the list of order states (`atlogged_ostates`) for the “Select order states” configuration option, typically as a multi-select dropdown or a list of checkboxes.
- **Front-office templates (`views/templates/front/`)**:

  - `atlogged/views/templates/front/atlogged-ajax.tpl`
    - **Purpose:** This template is likely rendered by the `popuploader.php` front controller in response to an AJAX request. It contains the HTML content for the message displayed to users who cannot download an attachment (e.g., “Please log in to continue,” with links to login/registration).
  - `atlogged/views/templates/front/atlogged.tpl`
    - **Purpose:** This template might be included via a hook (e.g., `displayHeader`) or directly by a front controller. It could contain:
      1. Hidden elements or data attributes used by `atlogged.js`.
      2. Initial setup or configuration variables for the JavaScript.
      3. Fallback messages or elements that are always present but conditionally displayed by JS.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create custom SQL tables.
  - Configuration records are stored in the `ps_configuration` table:
    - `ATLOGGED_ON`: Stores the boolean value for the “Activate feature” setting.
    - `ATLOGGED_C_ON`: Stores the boolean value for the “Download for customers only” setting.
    - `atlogged_ostates`: Stores a serialized array or comma-separated string of selected order state IDs for the “Select order states” setting.
    - `mypresta_updates`, `update_`, `updatev_`: Used for module update checks by MyPresta.eu.
    - `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: A core PrestaShop configuration key, likely accessed for language context in the Back Office.
- **Registered Hooks Table**:

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `displayHeader` | In the `<head>` section of every front-office page. | Used to inject `atlogged.js` and `atlogged.css` into the page, ensuring the module’s client-side logic and styling are loaded. |
  | `header` | Alias for `displayHeader` in some PrestaShop versions/contexts. | Same purpose as `displayHeader`. |
  | `actionFrontControllerSetMedia` | When a front controller is setting its media assets. | Could be used to conditionally load JS/CSS only on specific pages (e.g., product pages) for performance optimization. |
  | `actionDispatcherBefore` | Before a front controller is dispatched. | Potentially used by the `AttachmentController` override to intercept the download request very early. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and dedicated technical support for the “Attachments for logged users only” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is ready to assist you with any questions or issues you may encounter.
