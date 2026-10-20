---
title: "Product page CMS tab - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Product page CMS tab PrestaShop module by MyPresta.eu."
sidebar:
  label: "Product page CMS tab - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Product page CMS tab Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-cms-tab.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/product-page-cms-tab/)
>
> ---


# Product page CMS tab

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and are usually available by default on most hosting environments. No special or unusual extensions are needed for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Product page CMS tab” module in your Module Manager. This will take you to the main configuration screen.

#### **Select CMS page to display as a tab**

This is the core setting of the module. It determines which of your existing CMS pages will be displayed as a new tab on all product pages.

- **What this setting does:** This dropdown menu lists all the CMS pages you have created in your PrestaShop store (found under **Design > Pages** or **Design > CMS** in older versions). You need to select one of these pages.
- **Effect of changing this setting:**
  - *When a CMS page is selected:* A new tab will appear on every product page in your store. The title of this tab will be the title of the selected CMS page, and the content displayed when the tab is clicked will be the content of that CMS page.
  - *When ”--- Select ---” is chosen:* No new tab will appear on product pages. The module will effectively be inactive in terms of front-office display.
- **Recommended value:** Select the CMS page that contains information you want to share universally across all your product pages (e.g., a “Shipping Information” page, “Size Guide,” or “Warranty Details”).
- **Merchant scenario / example:** You want to provide a detailed “Size Guide” for all clothing products. You would first create a CMS page titled “Size Guide” with all the relevant information. Then, in this module’s configuration, you would select “Size Guide” from the dropdown. Now, every product page will have a “Size Guide” tab.

#### **Tab Type**

This setting controls how the module integrates with PrestaShop’s tab system, especially for different PrestaShop versions.

- **What this setting does:** This dropdown allows you to choose the method the module uses to display the tab. It’s primarily a compatibility setting for different PrestaShop versions.
- **Effect of changing this setting:**
  - *When “PrestaShop 1.7 / 8.x / 9.x” is selected:* The module will use the `displayProductExtraContent` hook, which is the standard and recommended way to add new tabs in modern PrestaShop versions. This ensures native look and feel.
  - *When “PrestaShop 1.6” is selected:* The module will use older hooks like `productTab` and `productTabContent`, which were standard in PrestaShop 1.6. This option is for backward compatibility if you are running an older, unsupported PrestaShop 1.6 store (though the module is officially for 1.7+).
- **Recommended value:** For PrestaShop 1.7, 8.x, and 9.x stores, always select **“PrestaShop 1.7 / 8.x / 9.x”**.
- **Merchant scenario / example:** If you are running PrestaShop 8.1, you would select “PrestaShop 1.7 / 8.x / 9.x” to ensure the tab displays correctly and integrates seamlessly with your theme’s design. If you were, for some reason, using this module on an old PrestaShop 1.6 store, you would select “PrestaShop 1.6”.

#### **MyPresta.eu Live Updates**

This section is common across MyPresta.eu modules and helps you manage module updates.

- **What this setting does:** This feature checks for new versions of the module directly from MyPresta.eu.
- **Effect of changing this setting:**
  - *When enabled:* The module will periodically check for updates. If a new version is available, you will see a notification in your module list or on the module’s configuration page. This helps you stay up-to-date with bug fixes and new features.
  - *When disabled:* The module will not check for updates automatically. You would need to manually check your MyPresta.eu account for new versions.
- **Recommended value:** **YES**. Keeping modules updated is crucial for security, compatibility, and accessing the latest features.
- **Merchant scenario / example:** You want to ensure your module always has the latest security patches. By enabling this, you’ll be notified when an update is available, prompting you to download and install it.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | **Select CMS page to display as a tab** | --- Select --- / Your chosen CMS page | Determines which CMS page content appears as a new tab on all product pages. |
| Module Configuration Page | **Tab Type** | PrestaShop 1.7 / 8.x / 9.x | Ensures correct tab display and integration with your PrestaShop version’s architecture. |
| Module Configuration Page | **MyPresta.eu Live Updates** | YES | Enables automatic checks for module updates from MyPresta.eu. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: The new tab isn’t showing up on my product pages. What should I do?**
A:

1. **Check Module Configuration:** Go to **Modules > Module Manager**, find “Product page CMS tab”, and click “Configure”. Ensure you have selected a valid CMS page from the “Select CMS page to display as a tab” dropdown. If ”--- Select ---” is chosen, no tab will appear.
2. **Check Tab Type:** Make sure “Tab Type” is set to “PrestaShop 1.7 / 8.x / 9.x” for modern PrestaShop versions.
3. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes, PrestaShop’s cache prevents changes from appearing immediately.
4. **Check CMS Page Status:** Ensure the selected CMS page is active and publicly visible (not disabled or set to private). You can check this under **Design > Pages**.
5. **Theme Compatibility:** While the module uses standard PrestaShop hooks, very heavily customized themes might sometimes interfere. If the above steps don’t work, temporarily switch to the default PrestaShop theme to see if the tab appears. If it does, your theme might require a small adjustment.

**Q: Can I have different CMS tabs for different products?**
A: This module is designed to display *one specific CMS page* as a tab on *all* product pages. It does not support assigning different CMS pages to individual products. If you need product-specific tabs, you would typically need a more advanced module or custom development.

**Q: The content in the tab looks strange or unstyled.**
A: The module simply pulls the content from your CMS page. The styling of this content is usually handled by your PrestaShop theme’s CSS.

1. **Check CMS Page Content:** Ensure the content on your original CMS page (under **Design > Pages**) is formatted correctly and doesn’t contain broken HTML.
2. **Theme CSS:** Your theme’s CSS might not have specific styles for content within product tabs, or it might be overriding default styles. If you have a web developer, they can inspect the page to identify and fix any styling conflicts.

**Q: I updated my CMS page, but the tab content on product pages hasn’t changed.**
A: After updating a CMS page, always clear your PrestaShop cache (**Advanced Parameters > Performance > Clear cache**). Your store might be serving an older cached version of the content.

**Q: How do I translate the tab title if my store is multi-language?**
A: The tab title is automatically taken from the title of the selected CMS page. To translate it, you need to edit the CMS page itself (**Design > Pages**) and provide translations for its title and content for each language you support. The module will then display the correct translated title based on the customer’s selected language.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Product page CMS tab” module (`cmstab`) is a lightweight PrestaShop module designed to inject existing CMS page content into product pages as a new tab. It primarily leverages PrestaShop’s hook system to achieve this. The module’s core logic resides in its main PHP file, `cmstab.php`, which handles installation, uninstallation, configuration, and hook registration. It does not introduce custom database tables or complex ObjectModels, relying instead on PrestaShop’s native `CMS` class for content retrieval. The module provides two sets of templates to ensure compatibility with both PrestaShop 1.6 and 1.7+ tab rendering mechanisms, selectable via the back-office configuration.

### 4.2 Controllers (`controllers/`)

This module does not introduce any custom Front-Office or Back-Office Admin Controllers. All functionality is managed through the main module class and PrestaShop’s hook system.

### 4.3 Core Classes & Models (`classes/`)

This module does not introduce any custom classes or ObjectModels in the `classes/` directory. It directly utilizes PrestaShop’s core `CMS` class to fetch content based on the configured CMS page ID.

### 4.4 JavaScript Assets (`views/js/`)

- **`cmstab/trusted.js`**
  - **Scope:** Back-office (module configuration page).
  - **Purpose:** This script is typically included in MyPresta.eu modules to handle the “MyPresta.eu Live Updates” functionality. It communicates with the MyPresta.eu API to check for new module versions and display update notifications within the PrestaShop back office. It does not affect the front-office display or customer interaction.

### 4.5 CSS Stylesheets (`views/css/`)

This module does not include any custom CSS files. The styling of the tab and its content is inherited from the active PrestaShop theme. Developers wishing to style the tab should target the appropriate selectors provided by the theme or PrestaShop’s core tab system.

### 4.6 Smarty Template Structure (`views/templates/`)

The module provides two sets of templates to accommodate different PrestaShop versions’ tab rendering approaches. The specific set used is determined by the “Tab Type” setting in the module’s configuration.

- **Hook templates (`views/templates/hook/`)**: This directory is not explicitly used for direct hook rendering in this module. Templates are directly referenced from `views/front/`.
- **Front-office templates (`views/templates/front/`)**:

  - **`cmstab/views/front/tab.tpl`**

    - **Purpose:** This template is designed for PrestaShop 1.6 compatibility. It’s rendered when the “Tab Type” is set to “PrestaShop 1.6”. It outputs the HTML for the tab *header* (the clickable part of the tab) using the CMS page title.
    - **Hook:** `productTab` (PrestaShop 1.6 specific)
    - **Variables:** `$cmstab_title` (the title of the selected CMS page).
  - **`cmstab/views/front/tab16.tpl`**

    - **Purpose:** This template is also for PrestaShop 1.6 compatibility. It outputs the HTML for the tab *content* area, displaying the actual content of the selected CMS page.
    - **Hook:** `productTabContent` (PrestaShop 1.6 specific)
    - **Variables:** `$cmstab_content` (the HTML content of the selected CMS page).
  - **`cmstab/views/front/tabcontents.tpl`**

    - **Purpose:** This template is for PrestaShop 1.7, 8.x, and 9.x compatibility. It’s rendered when the “Tab Type” is set to “PrestaShop 1.7 / 8.x / 9.x”. It outputs the entire tab structure, including both the tab header and its content, as expected by the `displayProductExtraContent` hook.
    - **Hook:** `displayProductExtraContent` (PrestaShop 1.7+ standard)
    - **Variables:**
      - `$cmstab_title`: The title of the selected CMS page.
      - `$cmstab_content`: The HTML content of the selected CMS page.
      - `$cmstab_id`: A unique ID for the tab, derived from the CMS page ID.
  - **`cmstab/views/front/tabcontents16.tpl`**

    - **Purpose:** This template appears to be a redundant or alternative version of `tab16.tpl` or `tabcontents.tpl`, likely for specific 1.6 scenarios or an older implementation. Given the module’s current logic, `tabcontents.tpl` is used for 1.7+ and `tab.tpl`/`tab16.tpl` for 1.6. Developers should primarily focus on `tabcontents.tpl` for modern PrestaShop versions.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create any custom database tables.
  - It stores its configuration settings in PrestaShop’s `ps_configuration` table:
    - `CMSTAB_ID`: Stores the ID of the selected CMS page.
    - `CMSTAB_TYPE`: Stores the selected tab type (e.g., ‘17’ for PrestaShop 1.7+, ‘16’ for PrestaShop 1.6).
    - `MYPRESTA_UPDATES`: Stores the setting for live updates.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Used by the module to register its JavaScript for live updates in the back office. |
| `displayBackOfficeHeader` | In the `<head>` section of every back-office page. | Used by the module to register its JavaScript for live updates in the back office. |
| `displayProductExtraContent` | On product pages, for adding new tabs (PrestaShop 1.7+). | Main hook for rendering the CMS tab and its content on modern PrestaShop versions. |
| `productTab` | On product pages, for adding new tab headers (PrestaShop 1.6). | Used for backward compatibility to render the tab header on PrestaShop 1.6. |
| `productTabContent` | On product pages, for adding new tab content (PrestaShop 1.6). | Used for backward compatibility to render the tab content on PrestaShop 1.6. |
| `actionAdminControllerSetMedia` | When an admin controller sets its media assets. | Used by the module to register its JavaScript for live updates in the back office. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and professional support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to providing timely assistance and ensuring the optimal performance of your modules.
