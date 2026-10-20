---
title: "Password protected category pages - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Password protected category pages PrestaShop module by MyPresta.eu."
sidebar:
  label: "Password protected category pages - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Password protected category pages Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/password-protected-category-pages.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/password-protected-category-pages/)
>
> ---


# Password protected category pages

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installing the module, click “Configure” to access its main settings. This screen provides general module management options.

- **What this setting does:** This section typically includes standard MyPresta.eu module settings related to updates and licensing. It ensures your module is up-to-date and properly licensed.
- **Effect of changing this setting:**
  - *`mypresta_updates`*: This setting controls whether the module checks for updates automatically. Keeping it enabled ensures you’re notified of new versions.
  - *`update_` and `updatev_`*: These are internal settings used by the module to manage update checks and version information. You generally do not need to interact with these directly.
- **Recommended value:** Keep `mypresta_updates` enabled to receive important updates and bug fixes.
- **Merchant scenario / example:** If you want to ensure your module always has the latest features and security patches, keep the update check enabled. If you are on a highly customized store and prefer to manually control updates after thorough testing, you might disable it, but this is generally not recommended for most merchants.

### 2.2 Dedicated Admin Screen: Category Passwords (Back Office > Catalog > Category Passwords)

This is the core management screen for setting up and managing passwords for your categories.

- **Screen Name & Menu Location:** You can find this screen by navigating to **Catalog > Category Passwords** in your PrestaShop Back Office menu.
- **Available Actions & Settings:**
  - **Category List:** This screen displays a list of all your categories. For each category, you will see if it is currently password protected and how many passwords are assigned to it.
  - **Add/Edit Passwords:** For each category, you can click an “Edit” or “Manage Passwords” button (or similar icon) to open a dedicated interface. Here, you can:
    - **Select a Category:** Choose the specific category you want to protect.
    - **Add New Password:** Enter a new password for the selected category. You can add multiple passwords for a single category. This is useful if you want to give different access codes to different groups of customers (e.g., “VIP123” for premium customers, “WHOLESALE456” for B2B partners).
    - **Delete Password:** Remove existing passwords.
    - **Enable/Disable Protection:** A toggle or checkbox might be available to quickly enable or disable password protection for a category without deleting all its passwords.
- **Effect of changes:**
  - **Adding a password:** The selected category will immediately become password protected in the front office. Customers will need to enter one of the assigned passwords to view its products.
  - **Deleting a password:** That specific password will no longer grant access. If it was the only password for a category, the category might become unprotected (depending on the module’s exact logic, it’s safer to explicitly disable protection if you want it open).
  - **Disabling protection:** The category will become publicly accessible again, and customers will see its products without needing a password.
- **Recommended workflow for daily store management:**
  1. Go to **Catalog > Category Passwords**.
  2. Identify the category you wish to protect.
  3. Click the “Manage Passwords” or “Edit” icon next to it.
  4. In the new screen, add one or more passwords. Remember that each password you add will grant access.
  5. Save your changes.
  6. To remove protection, either delete all passwords for that category or use an “Enable/Disable” toggle if available.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | `mypresta_updates` | Enabled | Controls automatic update checks for the module. Keep enabled for latest features and security. |
| Module Configuration Page | `update_`, `updatev_` | (Internal) | Internal settings for update management. No merchant interaction needed. |
| Category Passwords (Catalog > Category Passwords) | Category List | N/A | Overview of all categories and their password protection status. |
| Category Passwords (Catalog > Category Passwords) | Add/Edit Passwords | N/A | Allows adding, editing, or deleting passwords for specific categories. Multiple passwords per category are supported. |
| Category Passwords (Catalog > Category Passwords) | Enable/Disable Protection | N/A | Toggles password protection for a category on or off. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve set a password, but the category is still visible without it. What’s wrong?**
A1:

- **Clear Cache:** The most common reason is caching. Go to **Advanced Parameters > Performance** in your PrestaShop Back Office and click “Clear cache” (or “Clear Smarty cache” and “Clear cache” for all caches).
- **Check Category Status:** Ensure the category itself is active and visible in your store.
- **Verify Password Entry:** Double-check that you’ve correctly entered and saved the password(s) in the **Catalog > Category Passwords** section.
- **Module Position:** Ensure the module is correctly hooked. While the module handles this automatically, if you have heavily customized themes, sometimes hooks can be overridden.

**Q2: Can I have multiple passwords for one category?**
A2: Yes! This module explicitly supports an unlimited number of passwords for a single category. This is useful for giving different access codes to different groups (e.g., “VIP” password, “Wholesale” password).

**Q3: What happens if a customer tries to access a product directly from a protected category via its URL?**
A3: If a product belongs to a password-protected category, accessing the product page directly will still require the category password to be entered first. The module ensures that the category context is respected, preventing direct access to products within a secured category without authentication.

**Q4: How do I remove password protection from a category?**
A4: Go to **Catalog > Category Passwords**. Find the category you want to unprotect. You can either delete all the passwords associated with that category, or if there’s an explicit “Enable/Disable” toggle for the category’s protection, use that. Once all passwords are removed or protection is disabled, the category will become publicly accessible again.

**Q5: The password form doesn’t look good on my custom theme. How can I fix it?**
A5: The module uses standard PrestaShop templating and CSS. If it doesn’t look right, it’s likely a CSS conflict with your custom theme.

- **Inspect Element:** Use your browser’s developer tools (F12) to inspect the password form elements. Look for conflicting CSS rules from your theme.
- **Custom CSS:** You can add custom CSS to your theme’s `custom.css` file (or similar) to override the module’s default styling and make it match your theme.
- **Contact Support:** If you’re not comfortable with CSS, contact your theme developer or MyPresta.eu support for assistance.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Password protected category pages” module integrates into PrestaShop’s MVC architecture primarily by overriding the core `CategoryController` to intercept requests to category pages. It uses a dedicated Admin Controller (`AdminCatPasswordController`) for managing category-password associations, storing these in a custom database table. Front-office display is handled via a custom Smarty template for the password entry form.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `catpswd/override/controllers/front/listing/CategoryController.php`
    - **Class Name:** `CategoryController` (overrides the core PrestaShop `CategoryController`)
    - **Parent Class:** `CategoryControllerCore`
    - **Responsibility:** This override is the core of the module’s front-office functionality. It intercepts requests to category pages. Before displaying the actual category content, it checks if the category is password protected. If it is, and the user has not yet entered the correct password (or the session has expired), it renders the password entry form (`category.tpl`) instead of the standard category page. It handles the submission of the password form, validates the entered password, and sets a session variable upon successful authentication.
  - `catpswd/override/controllers/front/listing/index.php`
    - **Responsibility:** This is a standard PrestaShop `index.php` file within an override directory, typically used to prevent direct directory listing and ensure proper module loading. It doesn’t contain active controller logic itself.
- **Back-Office Admin Controllers**:

  - `catpswd/controllers/admin/AdminCatPasswordController.php`
    - **Tab Name:** “Category Passwords” (under Catalog menu)
    - **Managed Entity:** `CatPassword` (though no `ObjectModel` is explicitly listed, this controller manages the category-password relationships, likely interacting directly with the database or a helper class).
    - **Responsibility:** This controller provides the interface in the PrestaShop Back Office for administrators to manage password protection for categories. It lists categories, allows adding multiple passwords to a category, and removing them. It handles the CRUD operations for the category-password data.
  - `catpswd/controllers/admin/index.php`
    - **Responsibility:** Similar to the front-office `index.php`, this file prevents direct directory listing for the admin controllers directory.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no explicit classes in the `classes/` directory. This suggests that the `AdminCatPasswordController` likely handles database interactions directly or uses a simple helper function within the main module file (`catpswd.php`) for data management, rather than a dedicated `ObjectModel`.

### 4.4 JavaScript Assets (`views/js/`)

The module dossier indicates no specific JavaScript files. The password submission and validation are likely handled via standard HTML form submission and server-side processing within the `CategoryController` override.

### 4.5 CSS Stylesheets (`views/css/`)

The module dossier indicates no specific CSS files. The styling for the password entry form is likely minimal and relies on the default PrestaShop theme’s base styling. Developers wishing to customize the appearance should target the form elements within the `category.tpl` template using their theme’s custom CSS.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `catpswd/lib/searchTool/views/scripts.tpl`
    - **Hook:** Likely used in `displayHeader` or `actionAdminControllerSetMedia` (if it contains JS/CSS includes for a search tool).
    - **Output:** This template likely contains JavaScript or CSS inclusions, possibly for a search utility used within the module’s admin interface or for front-office functionality.
- **Front-office templates (`views/templates/front/`)**:
  - `catpswd/views/templates/front/category.tpl`
    - **Purpose:** This is the template rendered by the overridden `CategoryController` when a password-protected category is accessed without authentication. It displays the password entry form to the customer. It typically includes fields for the password, a submit button, and messages for successful or failed attempts.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  - `ps_catpassword`: This custom table is created by the module during installation. It stores the associations between category IDs and their respective passwords.
    - **Columns (expected):** `id_catpassword` (primary key), `id_category` (foreign key to `ps_category`), `password` (the hashed or plain-text password string).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Potentially used for including global CSS or JS assets, or for setting meta tags related to the module’s functionality. |
| `actionAdminControllerSetMedia` | When an admin controller is loaded and its media (JS/CSS) are being set. | Used by the module to inject its specific JavaScript and CSS files into the Back Office for the `AdminCatPasswordController` or other admin pages where module assets are needed. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and professional support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to providing timely assistance and ensuring your module operates smoothly.
