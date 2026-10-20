---
title: "MyQuill - Quill editor - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the MyQuill - Quill editor PrestaShop module by MyPresta.eu."
sidebar:
  label: "MyQuill - Quill editor"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy MyQuill - Quill editor Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/myquill-quill-editor.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/myquill-quill-editor/)
>
> ---


# MyQuill - Quill editor

## 1. Requirements & Compatibility
- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient and usually enabled by default on most hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)
After installation, clicking "Configure" will take you to the main configuration screen for MyQuill. This is where you control how the Quill editor behaves in your Back Office.

#### **General Settings Tab**

**1. Enable MyQuill Editor**
-   **What this setting does:** This is the master switch to activate or deactivate the MyQuill editor.
-   **Effect of changing this setting:**
    -   *When enabled (YES):* The Quill editor will replace the default TinyMCE editor in all supported areas of your PrestaShop Back Office (e.g., product descriptions, CMS pages, category descriptions).
    -   *When disabled (NO):* The default TinyMCE editor will be restored, and MyQuill's features will not be available.
-   **Recommended value:** **YES** (to use the module's features).
-   **Merchant scenario / example:** If you want to temporarily revert to TinyMCE for compatibility testing with another module, you would disable MyQuill here. Otherwise, keep it enabled to enjoy the advanced editor.

**2. Load Quill Editor on Front Office**
-   **What this setting does:** Determines if the necessary Quill editor assets (CSS, JS) are loaded on your store's front office. This is usually only needed if you have a custom theme or another module that uses Quill on the front end.
-   **Effect of changing this setting:**
    -   *When enabled (YES):* Quill's core files will be included in your store's public pages. This might slightly increase page load time but is necessary if you display Quill-generated content that requires its specific styling or functionality on the front end.
    -   *When disabled (NO):* Quill's core files will *not* be loaded on the front office, saving bandwidth and potentially improving page load speed.
-   **Recommended value:** **NO** (unless you have a specific reason to load it, like a custom theme feature).
-   **Merchant scenario / example:** If you're using a custom theme that displays interactive content (like accordions or tabs) created with MyQuill, and these elements aren't rendering correctly, enabling this might resolve the issue. For most stores, it's not needed.

**3. Load Quill Editor on Back Office**
-   **What this setting does:** Controls whether the Quill editor assets are loaded in your PrestaShop Back Office. This is essential for the module to function.
-   **Effect of changing this setting:**
    -   *When enabled (YES):* The Quill editor will load and function correctly in your Back Office.
    -   *When disabled (NO):* The Quill editor will not load, and you will likely see a blank editor area or the default TinyMCE. This effectively disables the module's core functionality in the Back Office.
-   **Recommended value:** **YES** (This must be enabled for the module to work).
-   **Merchant scenario / example:** You should always keep this enabled. Disabling it would prevent you from using MyQuill's features in the admin panel.

**4. Editor Height (in pixels)**
-   **What this setting does:** Sets the default height of the Quill editor input area in pixels.
-   **Effect of changing this setting:**
    -   *When set to a higher value (e.g., 500px):* The editor will appear taller, giving you more vertical space to view and edit your content without scrolling.
    -   *When set to a lower value (e.g., 200px):* The editor will be shorter, which might be useful for shorter content sections but could require more scrolling for longer descriptions.
-   **Recommended value:** **300px** (or adjust based on your preference for typical content length).
-   **Merchant scenario / example:** If you frequently write very long product descriptions, increasing this to 400px or 500px might make your editing experience more comfortable. For short CMS page titles, a smaller height might be fine.

**5. Editor Toolbar Options**
-   **What this setting does:** This allows you to customize which tools appear in the Quill editor's toolbar. You can select or deselect various buttons and features.
-   **Effect of changing this setting:**
    -   *When options are selected:* The corresponding buttons (e.g., bold, italic, image, video, table) will appear in the editor's toolbar, making those functions available to you.
    -   *When options are deselected:* The corresponding buttons will be hidden from the toolbar, preventing their use.
-   **Recommended value:** Enable all options initially, then deselect any tools you are certain you will never use to simplify the toolbar.
-   **Merchant scenario / example:** If you never plan to embed videos, you could deselect the "YouTube/Vimeo" option to reduce clutter in the toolbar. If you want to ensure your team only uses basic formatting, you could limit the options significantly.

**6. Image Upload Folder**
-   **What this setting does:** Specifies the default folder on your server where images uploaded through the Quill editor will be stored.
-   **Effect of changing this setting:**
    -   *When set to a specific path (e.g., `/img/cms/`):* All images uploaded via the editor will go into that folder.
    -   *When left as default (usually `/img/cms/` or similar):* Images will be stored in the standard PrestaShop CMS image directory.
-   **Recommended value:** Leave as default (`/img/cms/`) unless you have a specific organizational need to change it.
-   **Merchant scenario / example:** If you want to keep product-specific images separate from CMS page images, you could create a new folder (e.g., `/img/products_quill/`) and set this option accordingly. Ensure the folder exists and has write permissions.

**7. Enable SEO Link Generation**
-   **What this setting does:** Activates a feature that helps you create SEO-friendly links within your content.
-   **Effect of changing this setting:**
    -   *When enabled (YES):* The link tool in Quill will offer options to generate clean, descriptive links, potentially using product or category names as link text.
    -   *When disabled (NO):* The link tool will behave as a standard link inserter without specific SEO enhancements.
-   **Recommended value:** **YES** (to benefit from improved internal linking for SEO).
-   **Merchant scenario / example:** When linking to a product, instead of just pasting the URL, this feature might help you automatically generate a link with the product's name as the anchor text, which is better for SEO.

**8. Enable YouTube/Vimeo Embedding**
-   **What this setting does:** Allows you to embed videos from YouTube and Vimeo directly into your content using the Quill editor.
-   **Effect of changing this setting:**
    -   *When enabled (YES):* A dedicated button or option will appear in the toolbar to easily paste video URLs and embed them.
    -   *When disabled (NO):* You will not be able to use the dedicated video embedding tool.
-   **Recommended value:** **YES** (if you plan to use videos in your content).
-   **Merchant scenario / example:** You can easily add a product demonstration video to a product description or a brand story video to your "About Us" page.

**9. Enable Tables**
-   **What this setting does:** Adds functionality to create and edit HTML tables within the Quill editor.
-   **Effect of changing this setting:**
    -   *When enabled (YES):* A table creation tool will be available in the toolbar, allowing you to insert and manage tables (add rows/columns, merge cells, etc.).
    -   *When disabled (NO):* The table tool will be hidden.
-   **Recommended value:** **YES** (tables are useful for displaying structured data like specifications or comparisons).
-   **Merchant scenario / example:** Use tables to display product specifications, comparison charts, or shipping rate information on a CMS page.

**10. Enable Bootstrap Buttons**
-   **What this setting does:** Provides a tool to easily insert Bootstrap-styled buttons into your content, which can be used for calls to action.
-   **Effect of changing this setting:**
    -   *When enabled (YES):* A button tool will appear, allowing you to choose button styles (primary, secondary, success, etc.) and link them.
    -   *When disabled (NO):* The button tool will be hidden.
-   **Recommended value:** **YES** (for clear calls to action).
-   **Merchant scenario / example:** Add a "Shop Now" button to a promotional banner on a CMS page or a "Download PDF" button to a product's technical specifications.

**11. Enable Tabs**
-   **What this setting does:** Allows you to create tabbed content sections, useful for organizing large amounts of information in a compact way.
-   **Effect of changing this setting:**
    -   *When enabled (YES):* A tab creation tool will be available, letting you define tab titles and content for each tab.
    -   *When disabled (NO):* The tab tool will be hidden.
-   **Recommended value:** **YES** (for better content organization).
-   **Merchant scenario / example:** On a product page, use tabs for "Description," "Specifications," "Reviews," and "Shipping Information" to keep the page clean.

**12. Enable Galleries**
-   **What this setting does:** Integrates a feature to create simple image galleries within your content.
-   **Effect of changing this setting:**
    -   *When enabled (YES):* A gallery tool will appear, allowing you to select multiple images and arrange them into a gallery.
    -   *When disabled (NO):* The gallery tool will be hidden.
-   **Recommended value:** **YES** (for visually appealing image displays).
-   **Merchant scenario / example:** Showcase multiple angles of a product or a collection of lifestyle images on a CMS page.

**13. Enable FAQ (Accordion)**
-   **What this setting does:** Adds a tool to create interactive FAQ sections using an accordion (expandable/collapsible) format.
-   **Effect of changing this setting:**
    -   *When enabled (YES):* An FAQ tool will be available, letting you add question-and-answer pairs that users can expand or collapse.
    -   *When disabled (NO):* The FAQ tool will be hidden.
-   **Recommended value:** **YES** (excellent for support pages or product FAQs).
-   **Merchant scenario / example:** Create a dedicated "Frequently Asked Questions" CMS page or add a small FAQ section to a product page to address common customer queries.

#### **Save Button**
-   **What this does:** After making any changes to the settings on this page, you **must** click the "Save" button to apply them.
-   **Effect of clicking:** Your changes will be stored in the database, and the Quill editor will reflect these new settings the next time you open it in the Back Office.
-   **Recommended action:** Always click "Save" after modifying any setting.

### 2.2 Dedicated Admin Screens & Controller Views

MyQuill primarily integrates directly into existing PrestaShop content editing screens (like product, category, and CMS page edit forms). It does not introduce new top-level menu items or dedicated data management screens for its own content. The "AdminMyquillAjaxController" and "index.php" controllers are internal components handling the module's background operations, such as image uploads or dynamic content loading for the editor features.

Therefore, there is no separate "AdminMyquill" screen for you to manage. All interaction happens directly within the content editing forms where Quill replaces TinyMCE.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|---|
| **Module Configuration Page** | Enable MyQuill Editor | YES | Activates/deactivates the Quill editor in the BO. |
| | Load Quill Editor on Front Office | NO | Loads Quill assets on FO (only if needed by theme/module). |
| | Load Quill Editor on Back Office | YES | Loads Quill assets in BO (essential for module function). |
| | Editor Height (in pixels) | 300px | Sets the vertical size of the editor window. |
| | Editor Toolbar Options | All enabled | Customizes which tools appear in the editor toolbar. |
| | Image Upload Folder | `/img/cms/` | Specifies where uploaded images are stored. |
| | Enable SEO Link Generation | YES | Adds features for creating SEO-friendly links. |
| | Enable YouTube/Vimeo Embedding | YES | Allows embedding videos from YouTube/Vimeo. |
| | Enable Tables | YES | Adds functionality to create and edit HTML tables. |
| | Enable Bootstrap Buttons | YES | Provides a tool to insert Bootstrap-styled buttons. |
| | Enable Tabs | YES | Allows creating tabbed content sections. |
| | Enable Galleries | YES | Integrates a feature to create image galleries. |
| | Enable FAQ (Accordion) | YES | Adds a tool to create interactive FAQ sections. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: After installing MyQuill, the editor area is blank or still shows TinyMCE.**
*   **A:** First, ensure "Enable MyQuill Editor" and "Load Quill Editor on Back Office" are both set to **YES** in the module's configuration. Second, clear your PrestaShop cache: Go to **Advanced Parameters > Performance**, then click "Clear cache" in the top right. Also, clear your browser's cache.

**Q2: My images are not uploading, or I can't see them after upload.**
*   **A:** Check the "Image Upload Folder" setting in MyQuill's configuration. Ensure the specified folder exists on your server (e.g., `/img/cms/`) and has the correct write permissions (usually 755 or 775). If the folder doesn't exist, create it via FTP/SFTP.

**Q3: Some toolbar buttons (e.g., Tables, Videos) are missing from the editor.**
*   **A:** Go to MyQuill's configuration page and check the "Editor Toolbar Options" section. Make sure the specific features you want to use (e.g., "Enable Tables," "Enable YouTube/Vimeo Embedding") are set to **YES**. Save your changes and clear cache.

**Q4: Content created with MyQuill (like tabs or accordions) isn't displaying correctly on my front office.**
*   **A:** This often happens if your theme doesn't include the necessary CSS or JavaScript for these interactive elements. Try enabling "Load Quill Editor on Front Office" in MyQuill's configuration. If the issue persists, your theme might require specific Bootstrap or JavaScript libraries that are not loaded by default or are conflicting. In this case, you might need a webmaster to investigate.

**Q5: How do I revert to the default TinyMCE editor?**
*   **A:** Simply go to **Modules > Module Manager**, find "MyQuill - Quill editor," and click the "Disable" button. All content previously created with MyQuill will still be there, but the editing interface will revert to TinyMCE. You can re-enable MyQuill at any time.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)
This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview
The MyQuill module integrates the Quill.js rich text editor into the PrestaShop Back Office, replacing the default TinyMCE. It achieves this by hooking into the `displayBackOfficeHeader` to inject its assets and then using JavaScript to target and initialize Quill instances on relevant textarea elements. The module provides enhanced features like image uploads, video embedding, and custom content blocks (tables, tabs, galleries, FAQs) by extending Quill's functionality and providing AJAX endpoints for server-side operations. It avoids core overrides, ensuring compatibility and easy uninstallation.

### 4.2 Controllers (`controllers/`)

-   **Front-Office Controllers**:
    The module does not include any dedicated front-office controllers. All front-office functionality related to displaying Quill-generated content is handled by the theme's rendering of standard PrestaShop content (product descriptions, CMS pages, etc.) and the optional loading of MyQuill's front-office assets via hooks.

-   **Back-Office Admin Controllers**:
    *   `controllers/admin/AdminMyquillAjaxController.php`
        *   **Class name & parent class**: `AdminMyquillAjaxController` extends `ModuleAdminController`.
        *   **Responsibility**: This controller handles AJAX requests originating from the Quill editor in the Back Office. Its primary role is to manage server-side operations such as image uploads, ensuring they are correctly stored in the designated directory and returning the URL for insertion into the editor. It might also handle other dynamic data requests for specific Quill plugins (e.g., fetching product data for SEO links).
    *   `controllers/admin/index.php`
        *   **Class name & parent class**: This file typically contains a simple `die('Access Denied');` statement or similar security measure.
        *   **Responsibility**: It's a standard PrestaShop practice to include an `index.php` file in every directory to prevent directory listing and direct access. It does not contain any functional controller logic for the module.

### 4.3 Core Classes & Models (`classes/`)
The MyQuill module does not introduce any custom `ObjectModel` classes or database tables. It primarily operates by replacing the editor interface and storing its configuration in `ps_configuration`. Content created with Quill is stored directly in PrestaShop's existing content fields (e.g., `ps_product_lang.description`, `ps_cms_lang.content`) as standard HTML.

### 4.4 JavaScript Assets (`views/js/`)

-   `views/js/myquill-admin.js`
    *   **Scope**: Back-office.
    *   **Detail**: This is the main administrative JavaScript file. It is responsible for initializing the Quill editor on all relevant textarea elements within the PrestaShop Back Office. It reads the module's configuration settings (editor height, toolbar options, enabled features) and dynamically constructs the Quill instance with the appropriate modules and handlers. It also contains logic for integrating custom toolbar buttons and handling their actions (e.g., opening image upload dialogs, inserting video embeds).
-   `views/js/myquill-editor.js`
    *   **Scope**: Back-office.
    *   **Detail**: This file likely contains the core Quill.js library itself or specific customizations/extensions to the base Quill editor. It defines the editor's fundamental behavior, rendering, and API.
-   `views/js/myquill-front.js`
    *   **Scope**: Front-office.
    *   **Detail**: This script is conditionally loaded on the front office if the "Load Quill Editor on Front Office" setting is enabled. It contains JavaScript necessary to make interactive elements created with Quill (like tabs, accordions, galleries) functional on the customer-facing side of the store. It might include listeners for click events on tab headers or accordion titles to toggle content visibility.
-   `views/js/myquill-plugins.js`
    *   **Scope**: Back-office.
    *   **Detail**: This file encapsulates the JavaScript logic for various custom plugins and extensions added to Quill by MyQuill. This includes the implementation for features like image upload handling, video embedding, table creation, Bootstrap buttons, tabs, galleries, and FAQ accordions. It defines how these custom "blots" (Quill's term for custom content blocks) are rendered and how their associated toolbar actions behave.
-   `views/js/myquill-pro.js`
    *   **Scope**: Back-office.
    *   **Detail**: This file likely contains advanced or "pro" features and enhancements for the Quill editor, potentially building upon the `myquill-plugins.js`. It could include more sophisticated UI elements, additional formatting options, or further integrations specific to the MyPresta.eu version of the module.

### 4.5 CSS Stylesheets (`views/css/`)

-   `views/css/myquill-admin.css`
    *   **Scope**: Back-office admin form styling.
    *   **Detail**: Contains styles specific to the Quill editor's appearance within the PrestaShop Back Office. This includes styling for the toolbar, editor container, custom dialogs, and ensuring the editor integrates visually with the PrestaShop admin theme.
-   `views/css/myquill-editor.css`
    *   **Scope**: Back-office admin form styling.
    *   **Detail**: This file likely contains core CSS for the Quill editor itself, defining base styles for text formatting, blockquotes, lists, and other standard Quill elements. It might also include styles for custom blots (e.g., tables, buttons) when rendered within the editor.
-   `views/css/myquill-front.css`
    *   **Scope**: Front-office customer styling.
    *   **Detail**: This stylesheet is conditionally loaded on the front office if the corresponding setting is enabled. It provides the necessary CSS to correctly render interactive elements created with MyQuill (like tabs, accordions, galleries) on the customer-facing store. Developers can override these styles in their theme's `custom.css` or `theme.css` to match their brand.
-   `views/css/quill.snow.css`
    *   **Scope**: Back-office admin form styling.
    *   **Detail**: This is the standard "Snow" theme stylesheet for Quill.js. It provides the default visual appearance for the Quill editor's toolbar and content area, including icons, button styles, and basic formatting. This is a core Quill component.

### 4.6 Smarty Template Structure (`views/templates/`)

-   **Hook templates (`views/templates/hook/`)**:
    *   `bo-header.tpl`
        *   **Hook**: `displayBackOfficeHeader`
        *   **Output**: This template is responsible for injecting the necessary CSS and JavaScript assets (Quill core, module-specific JS/CSS) into the `<head>` section of the Back Office pages where the editor is needed. It dynamically includes files based on module configuration.
-   **Admin templates (`views/templates/admin/`)**:
    *   `configure.tpl`
        *   **Output**: This template renders the main configuration form for the MyQuill module, accessible via **Modules > Module Manager > Configure**. It displays all the settings described in Section 4.1, including switches, input fields, and the "Save" button.
    *   `preview.tpl`
        *   **Output**: This template might be used for a preview feature within the Back Office, potentially showing how Quill-generated content would look on the front end. Its exact usage would depend on the module's internal implementation for previewing content.

-   **Front-office templates (`views/templates/front/`)**:
    The module does not include any dedicated front-office templates. All Quill-generated content is rendered within existing PrestaShop theme templates (e.g., `product.tpl`, `cms.tpl`) by inserting the raw HTML output from the editor.

### 4.7 Database Schema & Hooks Map

-   **Database Tables**:
    The MyQuill module does not create any custom database tables. All its configuration settings are stored in the `ps_configuration` table using keys typically prefixed with `MYQUILL_`. Content created with the editor is stored in standard PrestaShop content tables (e.g., `ps_product_lang`, `ps_cms_lang`).

-   **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
|---|---|---|
| `displayBackOfficeHeader` | Executed in the `<head>` of Back Office pages. | Injects MyQuill's CSS and JavaScript assets (Quill editor, plugins, admin styles) into the Back Office to initialize the editor. |
| `displayHeader` | Executed in the `<head>` of Front Office pages. | Conditionally injects MyQuill's front-office CSS and JavaScript assets if "Load Quill Editor on Front Office" is enabled, to ensure interactive elements (tabs, accordions) function correctly. |
| `displayFooter` | Executed at the end of the `<body>` of Front Office pages. | Potentially used for injecting late-loading scripts or additional resources for front-office interactive elements, if not handled by `displayHeader`. |
| `displayProductExtraContent` | Executed on the product page. | Allows for injecting additional content blocks on the product page, potentially useful for custom Quill-generated content if the module were extended to manage such blocks directly. (Less likely to be directly used by MyQuill's core editor replacement function, but available for extensions). |
| `displayLeftColumn` | Executed in the left column of Front Office pages. | Similar to `displayProductExtraContent`, provides a hook for injecting content into the left column. |
| `displayRightColumn` | Executed in the right column of Front Office pages. | Similar to `displayProductExtraContent`, provides a hook for injecting content into the right column. |

## 5. Official Support & Updates
For the latest updates, bug fixes, and official support for the MyQuill - Quill editor module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). You can download the newest versions from your order history and access support resources directly from the MyPresta.eu website.
