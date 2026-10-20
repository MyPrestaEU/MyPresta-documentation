---
title: "Duplicate CMS page - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Duplicate CMS page PrestaShop module by MyPresta.eu."
sidebar:
  label: "Duplicate CMS page - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Duplicate CMS page Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/duplicate-cms-page.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/duplicate-cms-page/)
>
> ---


# Duplicate CMS page

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and are sufficient for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Duplicate CMS page” module in the Module Manager. This will take you to the module’s main configuration screen.

#### General Settings

- **MyPresta.eu Updates (mypresta\_updates)**

  - **What this setting does:** This setting controls whether the module checks for updates from MyPresta.eu. Keeping this enabled ensures you are notified of new versions, bug fixes, and feature enhancements.
  - **Effect of changing this setting:**
    - *When enabled:* The module will periodically check for available updates. If an update is found, a notification might appear in your PrestaShop Back Office.
    - *When disabled:* The module will not check for updates, and you will not be notified of new versions automatically. You would need to manually check for updates on MyPresta.eu.
  - **Recommended value:** **YES** (Enabled).
  - **Merchant scenario / example:** You want to ensure your module is always up-to-date with the latest security patches and features without manually checking the MyPresta.eu website every week.
- **Update (update\_)**

  - **What this setting does:** This is usually a display field or a button related to the update check, showing the current status or allowing a manual check. It works in conjunction with the “MyPresta.eu Updates” setting.
  - **Effect of changing this setting:** Clicking a button here (if present) would initiate an immediate check for updates.
  - **Recommended value:** N/A (Interaction based).
  - **Merchant scenario / example:** After enabling “MyPresta.eu Updates,” you might click this to immediately see if a new version is available, rather than waiting for the next automatic check.
- **Update Version (updatev\_)**

  - **What this setting does:** This field typically displays the latest available version of the module as detected by the update checker.
  - **Effect of changing this setting:** This is a display-only field and cannot be changed directly. It provides information about the latest version.
  - **Recommended value:** N/A (Display only).
  - **Merchant scenario / example:** You see “1.2.3” here, indicating that a newer version than your current one (e.g., 1.2.2) is available.
- **Latest Version (dupcms\_LATEST)**

  - **What this setting does:** Similar to “Update Version,” this field displays the most recent version of the module available.
  - **Effect of changing this setting:** This is a display-only field.
  - **Recommended value:** N/A (Display only).
  - **Merchant scenario / example:** You can quickly verify if your installed module is the most current one by comparing this value to your installed version.
- **Miniatures (dupcms\_MINIATURES)**

  - **What this setting does:** This setting likely controls whether miniature images or icons are displayed in the module’s interface, possibly related to the update checker or other visual elements within the module’s admin panel.
  - **Effect of changing this setting:**
    - *When enabled:* You might see small icons or images in the module’s configuration or update notifications.
    - *When disabled:* These visual elements would be hidden, resulting in a more text-based interface.
  - **Recommended value:** **YES** (Enabled).
  - **Merchant scenario / example:** You prefer a more visually rich interface in your Back Office, so you keep this enabled to see any relevant icons.
- **ID CMS Category (dupcms\_ID\_CMSCAT)**

  - **What this setting does:** This setting is crucial for the module’s core functionality. It allows you to select a default CMS category where duplicated CMS pages will be placed.
  - **Effect of changing this setting:**
    - *When a specific category is selected:* All new duplicated CMS pages will automatically be assigned to this category. This helps in organizing your content.
    - *When no category is selected (or default):* The module might default to the same category as the original page, or a root category, depending on its internal logic. Setting a specific category gives you more control.
  - **Recommended value:** Select a logical default category, such as “Information” or a specific category you use for new pages.
  - **Merchant scenario / example:** You frequently duplicate “Legal Notice” pages for different regions. You can set this to your “Legal Pages” CMS category so all new duplicates automatically land there, making them easier to find and manage.

#### How to Use the Duplication Feature

The actual duplication action happens on the standard PrestaShop CMS page list:

1. Navigate to **Improve > Design > Pages** in your PrestaShop Back Office.
2. You will see a list of your existing CMS pages.
3. Locate the CMS page you wish to duplicate.
4. In the “Actions” column (usually represented by three dots or a dropdown menu) for that specific CMS page, you will find a new option added by this module: **“Duplicate”** (or a similar icon/text).
5. Click “Duplicate.”
6. The module will create an exact copy of the page, including its content, meta information, friendly URL, and active status. The new page will typically have a name like “Copy of [Original Page Name]” or similar, which you can then edit.
7. The duplicated page will be placed in the CMS category you selected in the module’s configuration (if `dupcms_ID_CMSCAT` is set) or in the same category as the original.
8. You can then edit the newly duplicated page to change its title, content, URL, and other settings as needed.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | MyPresta.eu Updates | YES | Enables automatic checks for module updates. |
| Module Configuration | Update | N/A (Button) | Initiates a manual check for module updates. |
| Module Configuration | Update Version | N/A (Display) | Shows the latest available module version. |
| Module Configuration | Latest Version | N/A (Display) | Displays the most recent module version detected. |
| Module Configuration | Miniatures | YES | Controls display of visual elements/icons in module interface. |
| Module Configuration | ID CMS Category | Select a category | Sets the default CMS category for duplicated pages. |
| CMS Pages List (Design > Pages) | Duplicate Action | N/A (Button) | Creates an exact copy of the selected CMS page. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I duplicated a page, but I can’t find it.**
A: Check the CMS category you selected in the module’s configuration (`dupcms_ID_CMSCAT`). If you didn’t set one, it might be in the same category as the original page or the root CMS category. Also, ensure you search for “Copy of [Original Page Name]” or similar, as the module adds a prefix to the duplicated page’s title.

**Q: The duplicated page has the same Friendly URL as the original. Is this an issue?**
A: Yes, this can cause conflicts and SEO problems. After duplicating a page, **always edit the new page immediately** and change its Friendly URL (also known as “URL Rewrite” or “Slug”) to something unique and descriptive for the new content. PrestaShop usually appends a number (e.g., `-1`) to the URL, but it’s best to customize it yourself.

**Q: I don’t see the “Duplicate” option in the CMS pages list.**
A:

1. Go to **Modules > Module Manager** and ensure the “Duplicate CMS page” module is installed and enabled.
2. Clear your PrestaShop cache: Go to **Advanced Parameters > Performance**, scroll down, and click “Clear cache.”
3. If it still doesn’t appear, try re-installing the module (after backing up your store). If the issue persists, contact MyPresta.eu support.

**Q: Does this module duplicate images and files linked within the CMS page content?**
A: Yes, the module duplicates the entire HTML content of the page. If your images are linked using relative paths within the content, they will continue to work. If they are uploaded directly through the rich text editor, the references will be copied. However, the module does not duplicate the actual image *files* on your server; it duplicates the *references* to them. This is generally desired behavior.

**Q: Can I duplicate a CMS category?**
A: No, this module is specifically designed to duplicate individual CMS *pages*, not entire CMS *categories*.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a technical overview for developers and webmasters looking to understand, debug, or extend the “Duplicate CMS page” module.

### 4.1 Architecture Overview

The “Duplicate CMS page” module is a lightweight PrestaShop module primarily focused on extending the functionality of the existing `AdminCmsController`. It leverages PrestaShop’s hook system (`actionAdminControllerSetMedia`) to inject JavaScript that modifies the default CMS page listing table, adding a “Duplicate” action. The core duplication logic is handled by the module’s `dupcms.php` file, which intercepts AJAX requests to perform the database operations required for copying CMS page data. It does not introduce new database tables or complex object models, relying instead on direct manipulation of existing `ps_cms` and `ps_cms_lang` tables.

### 4.2 Controllers (`controllers/`)

This module does not introduce any custom front-office or back-office controllers. Its functionality is integrated into the existing `AdminCmsController` via hooks and AJAX.

### 4.3 Core Classes & Models (`classes/`)

This module does not introduce any custom classes or `ObjectModel` definitions. It directly interacts with the `CMS` and `CMSCategory` PrestaShop core classes and their associated database tables.

### 4.4 JavaScript Assets (`views/js/`)

- **`dupcms/views/js/dupcms.js`**
  - **Scope:** Back-office (specifically, the `AdminCms` page).
  - **Responsibility:**
    - This script is injected into the `AdminCmsController` page (Improve > Design > Pages) via the `actionAdminControllerSetMedia` hook.
    - It waits for the DOM to be ready.
    - It identifies the “Actions” column in the CMS page listing table.
    - For each CMS page row, it dynamically adds a new “Duplicate” action button or link to the existing action dropdown.
    - It attaches an event listener (e.g., `click`) to these newly added “Duplicate” elements.
    - When a “Duplicate” action is clicked, it extracts the `id_cms` of the page to be duplicated.
    - It then sends an AJAX request to the module’s main PHP file (`dupcms/dupcms.php`) with the `id_cms` and an action parameter (e.g., `action=duplicateCms`).
    - It handles the AJAX response, typically displaying a success or error message and potentially refreshing the CMS page list to show the newly duplicated page.
    - It might also include logic for update notifications or other dynamic UI elements related to the module’s configuration.

### 4.5 CSS Stylesheets (`views/css/`)

- **`dupcms/views/css/dupcms.css`**
  - **Scope:** Back-office (specifically, the `AdminCms` page).
  - **Responsibility:**
    - Provides styling for the dynamically added “Duplicate” action link/button to ensure it integrates visually with the PrestaShop Back Office theme.
    - May include styles for any module-specific notifications or UI elements within the `AdminCms` context.
    - Key CSS class selectors developers can override: Look for classes like `.dupcms-duplicate-action` or similar within the injected HTML to customize its appearance.

### 4.6 Smarty Template Structure (`views/templates/`)

This module does not use any custom Smarty template files (`.tpl`). All its UI modifications in the Back Office are performed dynamically via JavaScript.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any new custom database tables.
  - It operates on existing PrestaShop tables:
    - `ps_cms`: Stores general CMS page information (active status, position, etc.).
    - `ps_cms_lang`: Stores language-specific CMS page content (title, meta description, content, friendly URL).
    - `ps_cms_shop`: Links CMS pages to specific shops in a multishop environment.
    - `ps_configuration`: Stores the module’s configuration settings (e.g., `dupcms_ID_CMSCAT`, `mypresta_updates`).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Executed when a Back Office controller is setting its media (JS/CSS). | This is the primary hook used by the module. It injects `dupcms.js` and `dupcms.css` into the `AdminCmsController` page, allowing the module to modify the CMS page list and add the “Duplicate” action. |

## 5. Official Support & Updates

For official support, updates, and to download the latest version of the “Duplicate CMS page” module, please log in to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality.
