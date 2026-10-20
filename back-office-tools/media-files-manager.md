---
title: "Media / Files Manager - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Media / Files Manager PrestaShop module by MyPresta.eu."
sidebar:
  label: "Media / Files Manager - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Media / Files Manager Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/media-files-manager.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/media-files-manager/)
>
> ---


# Media / Files Manager

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. The module requires write permissions to the directories it manages, which is standard for PrestaShop installations.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, you’ll be directed to the module’s configuration page. This page primarily serves to integrate the file manager into your PrestaShop back office and manage its core settings.

The main configuration screen will display the file manager interface directly. This interface is a fully-featured file browser, similar to what you’d see on your computer, but operating on your server files.

**Key Areas & Functionality within the File Manager Interface:**

1. **Navigation Panel (Left Sidebar):**

   - **What this does:** Shows a tree-like structure of your server’s directories, typically starting from your PrestaShop root folder. You can click on folders to navigate through them.
   - **Effect of using this:** Allows you to quickly jump between different parts of your PrestaShop installation (e.g., `img/p` for product images, `themes/yourtheme/css` for stylesheets).
   - **Recommended value:** Use this to navigate to the specific folder where you want to manage files.
2. **File Listing Area (Main Panel):**

   - **What this does:** Displays the contents (files and subfolders) of the currently selected folder. You’ll see file names, sizes, types, and modification dates.
   - **Effect of using this:** This is where you’ll perform most of your file operations.
   - **Recommended value:** Familiarize yourself with the icons and information presented for each file.
3. **Toolbar (Top of the File Listing Area):**

   - **What this does:** Contains various buttons and tools for file operations. Common tools include:
     - **Upload:** Upload files from your computer to the current server folder.
     - **New Folder:** Create a new directory.
     - **New File:** Create a new empty file (e.g., a `.txt`, `.html`, or `.css` file).
     - **Copy, Cut, Paste:** Standard file manipulation.
     - **Rename:** Change the name of a file or folder.
     - **Delete:** Remove files or folders (use with extreme caution!).
     - **Edit:** Open a text editor for selected text files (e.g., `.php`, `.css`, `.js`, `.html`).
     - **Preview:** View images or other supported file types directly.
     - **Search:** Find files within the current directory or recursively.
     - **View Options:** Change how files are displayed (list, icons, etc.).
   - **Effect of using these tools:** Directly manipulates files and folders on your server.
   - **Recommended value:** Always double-check your selections before performing actions like “Delete” or “Rename.”
4. **Context Menu (Right-Click):**

   - **What this does:** Right-clicking on a file or folder often brings up a context-sensitive menu with quick access to common operations like “Open,” “Edit,” “Rename,” “Delete,” “Download,” “Get Info,” etc.
   - **Effect of using this:** Provides a faster way to perform actions on individual items.
   - **Recommended value:** Explore the right-click options for different file types.

**Specific Settings (if any, based on `mypresta_updates`, `update_`, `updatev_`):**

The module’s `getContent()` method primarily renders the file manager interface itself. The configuration keys `mypresta_updates`, `update_`, and `updatev_` are standard internal keys used by MyPresta.eu modules to manage update notifications and version checks. These are not settings you typically interact with directly as a merchant.

- **What these settings do:** These are internal flags that help the module communicate with MyPresta.eu’s update server to check for new versions and display notifications in your PrestaShop back office if an update is available.
- **Effect of changing these settings:** You cannot directly change these. They are managed automatically by the module. If they were to be manually altered (which is not recommended), it might affect the module’s ability to notify you about new versions.
- **Recommended value:** Leave them as they are. They are for internal module management.
- **Merchant scenario / example:** You don’t need to worry about these. The module will automatically inform you if a new version is released, prompting you to download and install it from your MyPresta.eu account.

### 2.2 Dedicated Admin Screens & Controller Views

This module does not introduce any additional dedicated admin screens or custom controllers beyond its main configuration page. The entire file management functionality is embedded directly within the module’s configuration interface.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | **Navigation Panel** | N/A | Browse server directories. |
| Module Configuration Page | **File Listing Area** | N/A | View and interact with files/folders. |
| Module Configuration Page | **Toolbar (Upload, New Folder, Edit, Delete, etc.)** | N/A | Perform file operations (upload, create, modify, delete). |
| Module Configuration Page | **Context Menu (Right-click)** | N/A | Quick access to file operations. |
| Module Configuration Page | `mypresta_updates` | Internal | Internal flag for update notifications. |
| Module Configuration Page | `update_` | Internal | Internal flag for update notifications. |
| Module Configuration Page | `updatev_` | Internal | Internal flag for update notifications. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I uploaded an image, but it’s not showing on my product page.**
A:

- **Check the path:** Ensure you uploaded the image to the correct directory that PrestaShop expects (usually `img/p/` followed by subfolders).
- **Clear Cache:** Sometimes PrestaShop’s cache (or your browser cache) might prevent new images from showing immediately. Go to **Advanced Parameters > Performance** in your back office and click “Clear cache.” Also, try clearing your browser’s cache.
- **Permissions:** Ensure the folder where you uploaded the image has correct write permissions (usually 755 or 775). While the module usually handles this, sometimes server configurations can be strict.

**Q: I edited a CSS file, but my store’s design hasn’t changed.**
A:

- **Clear Cache:** This is the most common reason. Go to **Advanced Parameters > Performance** and clear PrestaShop’s cache. Also, clear your browser’s cache (Ctrl+F5 or Cmd+R usually forces a hard refresh).
- **Correct File:** Double-check that you edited the correct CSS file that your theme is actually loading. Some themes use compiled CSS or multiple stylesheets.
- **Syntax Errors:** If you introduced a syntax error in your CSS, it might prevent the stylesheet from loading correctly. Use your browser’s developer tools (F12) to check for CSS errors.

**Q: I accidentally deleted a file/folder. Can I recover it?**
A:

- **Immediately Restore from Backup:** This is why regular backups are crucial. If you have a recent backup of your server files, restore the deleted item from there.
- **Contact Hosting Provider:** Some hosting providers maintain daily backups and might be able to restore individual files for you.
- **Caution:** The module itself does not have a “trash” or “undo” feature. Deletion is permanent.

**Q: The file manager looks broken or doesn’t load correctly.**
A:

- **Check Browser Console:** Open your browser’s developer tools (F12) and look for any errors in the “Console” tab. This can indicate JavaScript conflicts or server-side issues.
- **Module Conflicts:** Try disabling other recently installed modules to see if there’s a conflict.
- **Server Error Logs:** Check your server’s PHP error logs for any related errors.
- **Permissions:** Ensure the module’s own files and folders have correct read/write permissions.

**Q: Can I restrict access to certain folders for different admin users?**
A:

- This module, in its current version, provides a single, full-access file manager interface. PrestaShop’s native permissions system for modules typically grants either full access or no access to the module’s configuration. Granular folder-level permissions for different back-office users are not a built-in feature of this specific module. You would need custom development to implement such a feature.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Media / Files Manager” module (`fmpro`) is built around the popular open-source **elFinder** file manager. It integrates elFinder directly into the PrestaShop back office, primarily through the module’s `getContent()` method. This means the core file management logic and UI are handled by elFinder’s robust JavaScript and PHP backend, with the PrestaShop module acting as a wrapper and entry point.

The module itself is a standard PrestaShop module, extending `Module`. It does not introduce custom database tables (beyond `ps_configuration` for its own internal settings) or complex `ObjectModel` structures. Its primary function is to instantiate and configure the elFinder library within the PrestaShop admin context.

### 4.2 Controllers (`controllers/`)

This module does not utilize custom front-office or back-office controllers in the traditional PrestaShop sense (i.e., files in `controllers/front/` or `controllers/admin/`).
The elFinder library itself has its own backend connector (typically a PHP script) that handles file operations. This connector is likely integrated or called directly from within the main `fmpro.php` module file or a separate PHP script within the `fmpro/php/` directory, acting as the server-side handler for elFinder’s AJAX requests.

### 4.3 Core Classes & Models (`classes/`)

The module does not define any custom classes or models within a `classes/` directory. The core logic for file management is handled by the integrated elFinder library.

### 4.4 JavaScript Assets (`views/js/`)

The module heavily relies on JavaScript for its front-end interface, primarily the elFinder library. All JS files are located in `fmpro/js/`.

- `fmpro/js/elfinder.full.js`: This is the main elFinder library file, containing all the core functionality for the file manager UI, interactions, and AJAX communication with the backend. It’s a comprehensive script that powers the entire interface.
- `fmpro/js/extras/editors.default.js`: Provides default text editor functionality within elFinder, allowing users to edit text-based files directly.
- `fmpro/js/extras/quicklook.googledocs.js`: Enhances the “quick look” feature by integrating with Google Docs for previewing certain document types.
- `fmpro/js/i18n/elfinder.*.js`: A large collection of internationalization (i18n) files, providing translations for the elFinder interface into various languages (e.g., `elfinder.fr.js` for French, `elfinder.es.js` for Spanish). These are loaded based on the user’s language setting.
- `fmpro/js/i18n/help/*.html.js`: Contains localized help content for the elFinder interface, embedded as JavaScript strings.
- `fmpro/js/proxy/elFinderSupportVer1.js`: Likely a compatibility layer or proxy script for older elFinder versions or specific server configurations.
- `fmpro/js/worker/calcfilehash.js`: A web worker script for calculating file hashes, potentially used for integrity checks or caching.
- `fmpro/js/worker/quicklook.tiff.js`: A web worker script specifically for handling TIFF image previews.
- `fmpro/js/worker/quicklook.unzip.js`: A web worker script for handling ZIP file previews or content listing.

**Developer Notes:**

- The elFinder library is self-contained. Developers extending the module would primarily interact with elFinder’s API if they needed to customize its behavior or integrate it with other components.
- For styling, custom CSS is generally preferred over modifying these core JS files.
- For localization, ensure the correct `elfinder.LANG.js` file is loaded based on the PrestaShop back office language.

### 4.5 CSS Stylesheets (`views/css/`)

The module includes CSS files to style the elFinder interface. These are located in `fmpro/css/`.

- `fmpro/css/elfinder.full.css`: This is the main stylesheet for the elFinder interface, defining the layout, icons, colors, and overall visual appearance of the file manager.
- `fmpro/css/theme.css`: This file likely contains additional styling or overrides to integrate elFinder more seamlessly with the PrestaShop back office theme, or to provide specific theme adjustments for elFinder itself.

**Developer Notes:**

- To customize the appearance of the file manager, developers should create their own CSS file and load it *after* `elfinder.full.css` and `theme.css` to override specific styles.
- Key CSS class selectors are typically prefixed with `elfinder-` (e.g., `.elfinder-navbar`, `.elfinder-cwd-wrapper`).

### 4.6 Smarty Template Structure (`views/templates/`)

The module does not explicitly list any `.tpl` files in a `views/templates/` directory in the provided inventory. This suggests that the elFinder interface is rendered directly via JavaScript and HTML generated within the `getContent()` method of the main `fmpro.php` file, or that elFinder’s own templating mechanism is used internally, without exposing `.tpl` files in the module’s `views/templates/` structure.

The `getContent()` method will likely output the necessary HTML container (`<div>`) where the elFinder JavaScript will initialize and render the file manager.

### 4.7 Database Schema & Hooks Map

**Database Tables**:
The module does not create any custom database tables. It stores its internal configuration settings (like `mypresta_updates`, `update_`, `updatev_`) in PrestaShop’s standard `ps_configuration` table.

- `ps_configuration`:
  - `name`: `MYPRESTA_UPDATES_FMPRO` (or similar, for update checks)
  - `name`: `UPDATE_FMPRO` (or similar, for update checks)
  - `name`: `UPDATEV_FMPRO` (or similar, for update checks)

**Registered Hooks Table**:
The module’s primary function is to provide an administrative tool, so it does not typically register many front-office hooks. The module description mentions “Front-Office Hooks: Header, Columns, Product, or Footer” but this is likely a generic statement for MyPresta.eu modules and not specific to this module’s actual implementation, as it’s an admin tool.

Based on its nature as an admin tool, the module would primarily interact with back-office hooks, if any, to add menu items or integrate into existing admin pages. However, the provided information does not explicitly list any registered hooks. The most common integration point for such a module is directly through its `getContent()` method, which is accessed when clicking “Configure” in the Module Manager.

If it were to register any hooks, common ones for admin tools might include:

- `displayBackOfficeHeader`: To include its CSS/JS assets in the back office.
- `displayAdminProductsExtra`: (Less likely for a general file manager, but possible for specific product-related file uploads).
- `actionAdminControllerSetMedia`: To load assets for its configuration page.

Given the module’s design, its main entry point is its configuration page, where the elFinder instance is initialized.

## 5. Official Support & Updates

For official updates, technical support, and the latest versions of the “Media / Files Manager” module, please refer to your customer account at MyPresta.eu. Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and integration with your PrestaShop store.
