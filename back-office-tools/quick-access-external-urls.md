---
title: "Quick Access - external urls - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Quick Access - external urls PrestaShop module by MyPresta.eu."
sidebar:
  label: "Quick Access - external urls - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Quick Access - external urls Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/quick-access-external-urls.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/quick-access-external-urls/)
>
> ---


# Quick Access - external urls

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

This module integrates directly with PrestaShop’s existing Quick Access management system. There is no separate configuration screen for the module itself. Instead, it modifies the behavior of the default “Quick Access” feature in your Back Office.

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

When you click “Configure” for the “Quick Access - external urls” module, you will typically see a simple confirmation that the module is installed and active. There are no specific settings to adjust on this page, as the module works by overriding core PrestaShop behavior.

### 2.2 Dedicated Admin Screens & Controller Views

The module’s functionality is managed through the standard PrestaShop Quick Access menu.

**Screen Name & Menu Location:**

- **Back Office > Administration > Quick Access** (or **Configure > Advanced Parameters > Quick Access** in older PrestaShop 1.7.x versions).
- You can also access it directly from the Quick Access menu itself (the small clock icon at the top of your Back Office), by clicking “Manage Quick Access”.

**Available Actions & Settings:**
On this screen, you will see a list of your existing Quick Access links.

- **Adding a new Quick Access link:**

  1. Click the **“Add new quick access”** button (or similar, usually a plus icon).
  2. You will see a form with fields like:
     - **Name:** The text that will appear in your Quick Access menu (e.g., “DHL Shipping Portal”, “Stripe Dashboard”, “Google Analytics”).
     - **URL:** This is the crucial field. **With this module installed, you can now enter ANY valid URL here, including external websites.** For example:
       - `https://www.dhl.com/global-en/home/tracking.html`
       - `https://dashboard.stripe.com/`
       - `https://analytics.google.com/`
       - `https://mypresta.eu/`
     - **Open in new window:** (Recommended: YES) This option determines if the link opens in a new browser tab/window.
       - *When enabled:* The external link will open in a new tab, keeping your PrestaShop Back Office open in the current tab. This is generally recommended for external links to avoid navigating away from your admin panel.
       - *When disabled:* The link will open in the same tab, replacing your PrestaShop Back Office view.
  3. Click **“Save”**.
- **Editing an existing Quick Access link:**

  1. Find the link in the list and click the “Edit” icon (pencil).
  2. Modify the Name or URL as needed.
  3. Click “Save”.
- **Deleting a Quick Access link:**

  1. Find the link in the list and click the “Delete” icon (trash can).
  2. Confirm the deletion.

**Effect of changes:**

- Any Quick Access links you add, edit, or delete on this screen will immediately reflect in the Quick Access menu (the clock icon) at the top of your PrestaShop Back Office.
- When you click on a Quick Access link that points to an external URL, your browser will navigate to that external site (either in the same tab or a new one, depending on your “Open in new window” setting).

**Recommended workflow for daily store management:**

1. **Identify frequently used external tools:** Think about the websites you visit daily or weekly to manage your store (e.g., shipping, payment, marketing, support, supplier portals).
2. **Add them to Quick Access:** Go to **Administration > Quick Access** and add each external URL with a clear, descriptive name.
3. **Enable “Open in new window”:** For all external links, set “Open in new window” to YES. This ensures your PrestaShop Back Office remains open and accessible.
4. **Organize for your team:** If you have multiple admin users, consider what quick links would be most beneficial for each role.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Back Office > Administration > Quick Access** | **Name** | User-defined | Text displayed in the Quick Access menu. |
|  | **URL** | User-defined (External URL) | The web address the link points to. **This module enables external URLs here.** |
|  | **Open in new window** | YES (for external links) | Determines if the link opens in a new browser tab/window. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve installed the module, but I still can’t add external URLs to Quick Access. What’s wrong?**
A1:

- **Clear Cache:** After installation, always clear your PrestaShop cache. Go to **Advanced Parameters > Performance**, and click “Clear cache” in the top right.
- **Check Module Status:** Ensure the module is enabled. Go to **Modules > Module Manager**, search for “Quick Access - external urls”, and verify it’s active.
- **Verify Installation:** Sometimes, an installation can fail silently. Try uninstalling and reinstalling the module.
- **Browser Cache:** Clear your browser’s cache and cookies, or try accessing the Back Office in an incognito/private window.

**Q2: My Quick Access links are opening in the same tab, even for external sites. How do I fix this?**
A2:

- When adding or editing a Quick Access link, make sure the **“Open in new window”** option is set to **YES**. This setting controls whether the link opens in a new tab or the current one.

**Q3: Will this module affect my store’s performance or SEO?**
A3:

- No. This module operates entirely within the PrestaShop Back Office. It does not add any code, styling, or functionality to your store’s front office (what customers see). Therefore, it has no impact on your store’s loading speed, SEO, or customer experience.

**Q4: I’ve added many Quick Access links. Can I organize them?**
A4:

- PrestaShop’s default Quick Access feature doesn’t offer advanced organization like folders or categories. However, you can control the order of the links by dragging and dropping them on the **Administration > Quick Access** page. You can also use descriptive names to make them easy to identify.

**Q5: What if I uninstall this module? Will my external Quick Access links disappear?**
A5:

- If you uninstall this module, the ability to add *new* external URLs will be removed. Existing external URLs that you added while the module was active *might* continue to work, but PrestaShop’s core validation might prevent them from being edited or could cause issues. It’s best to keep the module installed if you rely on external Quick Access links.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Quick Access - external urls” module (`qae`) achieves its functionality by overriding core PrestaShop classes and controllers. Specifically, it targets the `QuickAccess` `ObjectModel` and the `AdminQuickAccessesController` to remove the validation that restricts Quick Access URLs to internal Back Office paths. This is a common PrestaShop override pattern.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: This module does not include any front-office controllers as its functionality is exclusively for the Back Office.
- **Back-Office Admin Controllers**:

  - **`qae/override/controllers/admin/AdminQuickAccessesController.php`**
    - **Class Name**: `AdminQuickAccessesController` (overrides the core `AdminQuickAccessesController`)
    - **Parent Class**: `AdminController`
    - **Responsibility**: This override is crucial. The original `AdminQuickAccessesController` contains logic to validate the `url` field of a Quick Access entry, ensuring it’s an internal PrestaShop Back Office path. This override modifies or removes that validation, allowing external URLs to be saved. Developers should inspect the `postProcess()` or `renderForm()` methods for the specific changes related to URL validation.

### 4.3 Core Classes & Models (`classes/`)

- **`qae/override/classes/index.php`**

  - This is typically an empty file or a file containing only `<?php exit; ?>` to prevent direct directory listing. It’s a security measure and not part of the module’s core logic.
- **`qae/override/classes/Link.php`**

  - **Class Name**: `Link` (overrides the core `Link` class)
  - **Parent Class**: `LinkCore`
  - **Responsibility**: The `Link` class is responsible for generating URLs in PrestaShop. While the primary change for external URLs is in `QuickAccess` and `AdminQuickAccessesController`, an override of `Link` might be present to ensure that any internal URL generation or validation methods that `QuickAccess` relies on are compatible with the new external URL allowance, or to prevent unintended side effects. Developers should look for modifications in methods related to URL validation or sanitization.
- **`qae/override/classes/QuickAccess.php`**

  - **Class Name**: `QuickAccess` (overrides the core `QuickAccess` `ObjectModel`)
  - **Parent Class**: `ObjectModel`
  - **Database Table**: `ps_quick_access`
  - **`$definition` fields**: This class defines the structure of a Quick Access entry, including `id_quick_access`, `name`, `url`, and `new_window`.
  - **Key Public Methods & Business Logic**: This override is fundamental. The original `QuickAccess` `ObjectModel` likely includes validation rules for the `url` field within its `validateFields()` or `add()`/`update()` methods. This override removes or relaxes those validation rules, allowing the `url` field to store any string, including external URLs, without triggering validation errors.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include any custom JavaScript files. The changes are purely server-side (PHP overrides).

### 4.5 CSS Stylesheets (`views/css/`)

This module does not include any custom CSS files. The visual presentation of the Quick Access menu is handled by the default PrestaShop Back Office theme.

### 4.6 Smarty Template Structure (`views/templates/`)

This module does not include any custom Smarty template files. It leverages the existing templates of the PrestaShop Back Office for rendering the Quick Access management page and the Quick Access menu itself.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create any new database tables. It modifies the behavior of how data is stored and validated for the existing `ps_quick_access` table.
  - Configuration records are not stored in `ps_configuration` by this module, as it primarily relies on class/controller overrides.
- **Registered Hooks Table**:
  This module does not register any specific hooks in the traditional sense (e.g., `displayHeader`, `actionValidateOrder`). Its functionality is implemented through PrestaShop’s override system, which directly modifies core classes and controllers rather than injecting code via hooks.

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Quick Access - external urls” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any technical issues or questions you may have.
