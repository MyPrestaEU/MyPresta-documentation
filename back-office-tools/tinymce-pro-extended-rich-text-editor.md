---
title: "tinyMCE pro - extended rich text editor - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the tinyMCE pro - extended rich text editor PrestaShop module by MyPresta.eu."
sidebar:
  label: "tinyMCE pro - extended rich text editor - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy tinyMCE pro - extended rich text editor Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/tinymce-pro-extended-rich-text-editor.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/tinymce-pro-extended-rich-text-editor/)
>
> ---


# tinyMCE pro - extended rich text editor

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” to access the module’s main settings. This screen allows you to enable or disable the enhanced editor and manage its core functionalities.

The configuration page for “tinyMCE pro” is designed to be simple, as the module primarily works by replacing and enhancing the existing editor without extensive user-facing settings beyond its activation.

- **What this setting does:** This module primarily works by replacing the default PrestaShop editor with an enhanced version of tinyMCE. The configuration page will typically contain an “Enable/Disable” switch for the module itself, and potentially options to control which specific areas of the back office the enhanced editor should apply to.
- **Effect of changing this setting:**

  - *When enabled:* The standard, often limited, text editor in areas like product descriptions, CMS pages, and category descriptions will be replaced with the “tinyMCE pro” editor. This new editor will feature a richer toolbar with options for Font Awesome icons, YouTube video embedding, advanced HTML/JavaScript code acceptance, and more.
  - *When disabled:* The module will cease to function, and PrestaShop will revert to its default text editor. All the advanced features provided by “tinyMCE pro” will no longer be available.
- **Recommended value:** **Enabled**. To benefit from the module’s features, it should always be enabled.
- **Merchant scenario / example:** You’re editing a product description for a new item. With “tinyMCE pro” enabled, you can easily add a YouTube video showcasing the product, include Font Awesome icons for features (e.g., a checkmark icon for “In Stock”), and use advanced formatting to create a visually appealing layout, all directly within the editor. If disabled, you’d be limited to basic text formatting.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | **Module Status (Enable/Disable)** | Enabled | Controls whether the enhanced tinyMCE editor replaces the default PrestaShop editor in the back office. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve enabled the module, but the editor still looks the same. What should I do?**
**A1:** After enabling any module that modifies the back office, it’s a good practice to clear your browser’s cache and PrestaShop’s Smarty cache.
- **Browser Cache:** Hard refresh your browser (Ctrl+F5 or Cmd+Shift+R).
- **PrestaShop Cache:** Go to **Advanced Parameters > Performance** in your PrestaShop back office. Click the “Clear cache” button in the top right corner.

**Q2: Some of the new editor features (like Font Awesome icons) aren’t displaying correctly on my front office.**
**A2:** This usually indicates a conflict with your custom theme’s CSS or JavaScript.
- **Check for Conflicts:** Temporarily switch to the default PrestaShop theme (Classic or Hummingbird) and check if the features display correctly. If they do, the issue is with your custom theme.
- **Theme Customization:** Your theme might be overriding or not including necessary CSS/JS for these elements. You may need to consult your theme developer or a webmaster to integrate the module’s front-office assets correctly into your theme.

**Q3: Can I use this editor for all languages in my store?**
**A3:** Yes, the tinyMCE editor is designed to work seamlessly with PrestaShop’s multi-language capabilities. When you switch languages in the back office, the editor will still be available for you to input content in the selected language. The module also includes language files for many of its plugins (e.g., Font Awesome, PowerPaste), ensuring a localized experience where available.

**Q4: I’m seeing an error after installing the module, or my back office is slow.**
**A4:**
- **Check Server Error Logs:** The first step is always to check your server’s PHP error logs. These logs often provide specific details about what went wrong.
- **Disable Other Modules:** Temporarily disable other recently installed or complex modules to rule out conflicts.
- **PHP Version:** Ensure your PHP version is within the supported range (PHP 7.1 - 8.5). An incompatible PHP version can cause various issues.
- **Contact Support:** If the issue persists, gather any error messages and contact MyPresta.eu support for assistance.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The `tinyMCE pro` module primarily functions by overriding PrestaShop’s default `Validate` class to ensure compatibility with the extended HTML content generated by the enhanced tinyMCE editor. It injects its own version of the tinyMCE library and a multitude of plugins into the back office, effectively replacing the standard editor. The module’s core logic resides in `index.php`, which handles installation, uninstallation, and the configuration form. It leverages PrestaShop’s hook system to load its assets and initialize the editor where needed.

### 4.2 Controllers (`controllers/`)

This module does not introduce any custom front-office or back-office controllers. Its functionality is primarily integrated through the main module file (`index.php`) and by overriding core PrestaShop classes.

### 4.3 Core Classes & Models (`classes/`)

- **`tinymcepro/override/classes/index.php`**: This file is typically an empty placeholder to prevent directory listing, a common security practice. It does not contain any functional class definitions.
- **`tinymcepro/override/classes/Validate.php`**:
  - **Purpose**: This is a crucial override. PrestaShop’s `Validate` class is responsible for sanitizing and validating various inputs, including HTML content. The default `isCleanHtml()` method can be overly restrictive for rich content, stripping out valid HTML5 elements, attributes, or JavaScript that the extended tinyMCE editor might generate.
  - **Override Logic**: This override likely modifies or extends the `isCleanHtml()` method (or related validation methods) to allow a broader range of HTML, attributes, and potentially embedded scripts/styles, ensuring that the content generated by tinyMCE pro is not stripped or deemed invalid by PrestaShop’s core validation.
  - **Impact**: Developers should be aware that this override changes core validation behavior. If custom validation rules are in place or other modules rely on strict `isCleanHtml()`, conflicts might arise.

### 4.4 JavaScript Assets (`views/js/`)

The module includes a vast array of JavaScript files, primarily for the tinyMCE core library and its numerous plugins.

- **`tinymcepro/js/accordion.js`**: Likely a custom script to handle accordion functionality on the front-office, possibly related to the `bootstrapaccordion` tinyMCE plugin.
- **`tinymcepro/js/alerts.js`**: Custom script for handling alert messages, potentially tied to a Bootstrap alert plugin.
- **`tinymcepro/js/fancybox.js`**: Integration of the Fancybox library for lightboxes, likely used for image or media display within the editor’s output.
- **`tinymcepro/js/readmore.js`**: Script for implementing “read more” functionality, collapsing long content sections.
- **`tinymcepro/js/tinymce-cmscategory.js`**: Specific initialization or configuration script for tinyMCE when used in CMS or category description fields.
- **`tinymcepro/lib/htmlTemplatesManager/js/htmlTemplatesManager.js`**: Core JavaScript for the HTML Templates Manager plugin, enabling creation, editing, and insertion of predefined HTML snippets.
- **`tinymcepro/lib/plugins/bootstrapaccordion/plugin.js`**: tinyMCE plugin for inserting and managing Bootstrap-style accordions.
- **`tinymcepro/lib/plugins/codesample/plugin.js`**: tinyMCE plugin for inserting and syntax-highlighting code samples. Includes `prism.css` for styling.
- **`tinymcepro/lib/plugins/editattributes/plugin.js`**: tinyMCE plugin to easily edit HTML attributes of selected elements.
- **`tinymcepro/lib/plugins/fontawesome/langs/*.js`**: Language files for the Font Awesome tinyMCE plugin.
- **`tinymcepro/lib/plugins/lineheight/index.js`, `langs/de.js`, `plugin.js`**: tinyMCE plugin for controlling line height of text.
- **`tinymcepro/lib/plugins/paragraph/*.js`**: A complex plugin for managing paragraph styles and potentially showing block elements. Includes several internal utility scripts.
- **`tinymcepro/lib/plugins/powerpaste/*.js`**: Advanced tinyMCE plugin for cleaning and sanitizing content pasted from Microsoft Word, Google Docs, etc. Includes many language files.
- **`tinymcepro/lib/plugins/smileys/plugin.js`**: tinyMCE plugin for inserting emoji/smileys.
- **`tinymcepro/lib/plugins/youtube/includes/youtube.js`, `plugin.js`**: tinyMCE plugin for embedding YouTube videos.
- **`tinymcepro/lib/tinymce.inc.js`**: Likely the main tinyMCE core library file, or a custom build/configuration file for the editor.
- **`tinymcepro/lib/tinymce_loader.js`**: Script responsible for loading and initializing the tinyMCE editor instances across the PrestaShop back office.

### 4.5 CSS Stylesheets (`views/css/`)

- **`tinymcepro/css/tinymcepro.css`**: General custom styles for the module, potentially for its configuration page or front-office elements.
- **`tinymcepro/css.css`**: Another general stylesheet, possibly for older PrestaShop versions or specific UI elements.
- **`tinymcepro/lib/editor.css`**: Core CSS for the tinyMCE editor itself, defining its appearance within the back office.
- **`tinymcepro/lib/htmlTemplatesManager/css/htmlTemplatesManager.css`**: Styles for the HTML Templates Manager interface.
- **`tinymcepro/lib/iconset.css`**: Likely contains styles for custom icons used within the editor or module.
- **`tinymcepro/lib/plugins/bs_alert/assets/css/bootstrap.css`, `plugin.css`**: Bootstrap CSS and specific plugin styles for the Bootstrap Alert tinyMCE plugin.
- **`tinymcepro/lib/plugins/bs_images/assets/css/bootstrap.css`, `plugin.css`**: Bootstrap CSS and specific plugin styles for the Bootstrap Images tinyMCE plugin.
- **`tinymcepro/lib/plugins/codesample/css/prism.css`**: Stylesheet for syntax highlighting used by the `codesample` plugin.
- **`tinymcepro/lib/plugins/powerpaste/css/editorcss.css`**: Styles specifically for the PowerPaste plugin, potentially for visual feedback during pasting.
- **`tinymcepro/lib/plugins/tinyplusBootstrapTools/flat-blue.css`, `res-show-blocks-style.css`**: Additional Bootstrap-related or block display styles, possibly for specific editor themes or tools.
- **`tinymcepro/lib/plugins/youtube/includes/youtube.css`**: Styles for the YouTube video embedding functionality.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`tinymcepro/header.tpl`**: This template is likely hooked into `displayHeader` to load necessary CSS and JavaScript assets for the module, both in the back office (for the editor itself) and potentially the front office (for rendered content like accordions or fancybox).
- **`tinymcepro/lib/htmlTemplatesManager/views/buttonManager.tpl`**: Template for the button or interface that opens the HTML Templates Manager.
- **`tinymcepro/lib/htmlTemplatesManager/views/createTemplateForm.tpl`**: Form template for creating new HTML templates.
- **`tinymcepro/lib/htmlTemplatesManager/views/editTemplateForm.tpl`**: Form template for editing existing HTML templates.
- **`tinymcepro/lib/htmlTemplatesManager/views/mainForm.tpl`**: The main interface template for the HTML Templates Manager.
- **`tinymcepro/lib/htmlTemplatesManager/views/selectInput.tpl`**: A reusable template for a select dropdown input within the template manager.
- **`tinymcepro/views/admin/fonts.tpl`**: Template related to font selection or display, possibly for custom font integration within the editor.
- **`tinymcepro/views/admin/form.tpl`**: The main configuration form template for the module, rendered via `getContent()` in `index.php`.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: This module does not appear to create custom SQL tables. Its configuration settings are stored in `ps_configuration` (e.g., `PS_TINYMCEPRO_ENABLED`). HTML templates created via the `htmlTemplatesManager` might be stored in a custom table or serialized in `ps_configuration` as well, though no explicit SQL file is present, suggesting dynamic creation or configuration storage.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayBackOfficeHeader` | Renders in the `<head>` section of the PrestaShop back office. | Injects necessary CSS and JavaScript files for the tinyMCE editor and its plugins to function. This is where the core tinyMCE library and its initialization scripts are loaded. |
| `actionAdminControllerSetMedia` | Executed when an admin controller sets its media assets. | Allows the module to add its specific JS/CSS files to the current admin page, ensuring the tinyMCE editor is loaded only on pages where it’s needed (e.g., Product edit, CMS page edit). |
| `actionGetContentEditor` | (If custom hook) | This hook would be used to replace the default editor instance with the module’s enhanced tinyMCE editor. |
| `displayHeader` | Renders in the `<head>` section of the front office. | Potentially loads front-office specific assets (like `accordion.js`, `fancybox.js`, `tinymcepro.css`) if the content generated by the editor requires special styling or JavaScript to display correctly (e.g., accordions, lightboxes). |
| `displayRightColumn` | Renders in the right column of the front office. | (Unlikely to be used directly for editor functionality, but could be used to display content *created* by the editor if the module had a front-office widget). |
| `displayLeftColumn` | Renders in the left column of the front office. | (Similar to `displayRightColumn`). |
| `displayFooter` | Renders in the footer of the front office. | Could be used to load non-critical JavaScript or CSS for front-office display. |

## 5. Official Support & Updates

For official updates, technical support, and any further assistance with the “tinyMCE pro - extended rich text editor” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to help you with installation, configuration, and troubleshooting.
