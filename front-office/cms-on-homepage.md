---
title: "CMS on homepage - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the CMS on homepage PrestaShop module by MyPresta.eu."
sidebar:
  label: "CMS on homepage - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy CMS on homepage Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/cms-on-homepage.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/cms-on-homepage/)
>
> ---


# CMS on homepage

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5 (Always extending to PHP 8.5)
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself, and this module has no additional special requirements.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “CMS on homepage” module. You will be taken to its main configuration screen.

#### Select CMS Page

This is the primary setting for the module. It allows you to choose which of your existing CMS pages will have its content displayed on the homepage.

- **What this setting does:** This dropdown menu lists all the CMS pages you have created in your PrestaShop store (found under **Shop Parameters > Pages**). You select one of these pages.
- **Effect of changing this setting:**
  - *When a CMS page is selected:* The content of the chosen CMS page will be fetched and displayed on your store’s homepage.
  - *When no CMS page is selected (or if you change your mind):* The module will not display any content, or it will display the content of the newly selected page.
- **Recommended value:** Choose the CMS page whose content you wish to feature prominently on your homepage. This could be your “About Us,” “Shipping Information,” “Privacy Policy” (if you want it very visible), or a custom page with promotional content.
- **Merchant scenario / example:** You have a CMS page titled “Our Story” that details your brand’s history and values. By selecting “Our Story” here, every visitor to your homepage will immediately see this content, helping to build brand connection and trust.

After making your selection, remember to click the **“Save”** button to apply your changes.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Select CMS Page | (None selected initially) | Choose which CMS page’s content appears on the homepage. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve selected a CMS page, but nothing is showing on my homepage. What’s wrong?**
A:

1. **Clear Cache:** Go to **Advanced Parameters > Performance** in your Back Office and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes PrestaShop needs a cache refresh to display new content.
2. **Check CMS Page Status:** Ensure the selected CMS page itself is active and visible in your store (go to **Shop Parameters > Pages** and check its status).
3. **Theme Compatibility:** While the module uses standard PrestaShop hooks, some highly customized themes might override these hooks or have specific layout requirements. If clearing cache doesn’t help, contact your theme developer or MyPresta.eu support.

**Q: The CMS content is showing, but it doesn’t look right (e.g., wrong fonts, colors, layout).**
A: The module simply injects the content of your CMS page. The styling (fonts, colors, spacing) is typically controlled by your PrestaShop theme’s CSS.

1. **Check CMS Page Content:** Ensure there’s no custom, conflicting HTML or inline styling within the CMS page content itself that might be causing issues.
2. **Theme Customization:** You might need to add custom CSS to your theme to better integrate the CMS content visually. A web developer can help with this.

**Q: Can I display multiple CMS pages on the homepage?**
A: This specific module is designed to display *one* selected CMS page. If you need to display multiple distinct blocks of CMS content, you would either need to combine them into a single CMS page or look for a more advanced content management module.

**Q: How do I translate the CMS content for different languages?**
A: The content of your CMS page is managed directly within PrestaShop’s core CMS functionality. When you edit a CMS page (**Shop Parameters > Pages**), you can select the language to edit its content. The module will automatically display the content in the language currently selected by the customer on your storefront.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “CMS on homepage” module is a lightweight PrestaShop module primarily designed to inject existing CMS page content into various homepage hooks. It follows a standard PrestaShop module structure, leveraging the `Module` class and its `install()` and `uninstall()` methods for setup and cleanup, and `getContent()` for back-office configuration. Front-office display is handled entirely through hook registration and Smarty templates. It does not introduce custom controllers, models, or complex JavaScript.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. All front-office content rendering is handled directly via registered hooks within the main module file.
- **Back-Office Admin Controllers**: None. The module’s configuration is managed through the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)

- None. The module relies on PrestaShop’s core `CMS` and `Configuration` classes.

### 4.4 JavaScript Assets (`views/js/`)

- None. The module does not include any custom JavaScript.

### 4.5 CSS Stylesheets (`views/css/`)

- None. The module does not include any custom CSS. The displayed CMS content inherits styling from the active PrestaShop theme.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`cmshomepage/views/templates/hook/cmshomepage.tpl`**

  - **Purpose:** This is the primary template responsible for rendering the actual content of the selected CMS page. It’s designed to be hooked into `displayHome` or `displayHomeTabContent` for direct content output.
  - **Variables:**
    - `{$cms_content}`: The HTML content of the selected CMS page, fetched and assigned by the module.
  - **Output:** Renders the raw HTML content of the CMS page.
- **`cmshomepage/views/templates/hook/tab.tpl`**

  - **Purpose:** This template is used when the module is hooked into `displayHomeTab`. It generates the HTML for a tab header that, when clicked, reveals the CMS content.
  - **Variables:**
    - `{$tab_name}`: The title of the tab, typically derived from the CMS page title.
    - `{$tab_id}`: A unique ID for the tab, used to link it to its corresponding content panel.
  - **Output:** An `<li>` element containing an `<a>` tag, suitable for inclusion in a tab navigation structure.
- **`cmshomepage/views/templates/hook/tabContents.tpl`**

  - **Purpose:** This template is used when the module is hooked into `displayHomeTabContent`. It generates the HTML for the content panel associated with a tab.
  - **Variables:**
    - `{$tab_id}`: The unique ID matching the `tab.tpl`’s ID.
    - `{$cms_content}`: The HTML content of the selected CMS page.
  - **Output:** A `<div>` element with the tab content, typically hidden by default and revealed via JavaScript when its corresponding tab is clicked.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any custom database tables.
  - It stores its configuration in the `ps_configuration` table using the key `CMSHOMEPAGE_ID_CMS` to store the ID of the selected CMS page.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHomeTabContent` | Renders content within a homepage tab. | Outputs the `cmshomepage.tpl` or `tabContents.tpl` with the CMS content. |
| `displayHomeTab` | Renders a tab header on the homepage. | Outputs the `tab.tpl` with the CMS page title as the tab name. |
| `displayHome` | Renders content directly in the main homepage area. | Outputs the `cmshomepage.tpl` with the CMS content. |

The module’s `install()` method registers these hooks. The `hookDisplayHome()`, `hookDisplayHomeTab()`, and `hookDisplayHomeTabContent()` methods in `cmshomepage.php` are responsible for fetching the selected CMS page content and rendering the appropriate template.

### 4.8 Configuration Keys

The module uses the following configuration keys in `ps_configuration`:

- `CMSHOMEPAGE_ID_CMS`: Stores the `id_cms` of the CMS page selected by the merchant to be displayed on the homepage.

## 5. Official Support & Updates

For official updates, bug fixes, and dedicated developer support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Ensure you are using the latest version of the module for optimal performance and compatibility with your PrestaShop store.
