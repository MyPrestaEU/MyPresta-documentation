---
title: "Zoom images on product list in back office - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Zoom images on product list in back office PrestaShop module by MyPresta.eu."
sidebar:
  label: "Zoom images on product list in back office - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Zoom images on product list in back office Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/zoom-images-on-product-list-in-back-office.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/zoom-images-on-product-list-in-back-office/)
>
> ---


# Zoom images on product list in back office

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the module name. You will be taken to its main configuration screen.

This module has a very simple configuration, typically consisting of a single switch to enable or disable its functionality.

- **Enable Zoom on Product List:**
  - **What this setting does:** This is the master switch for the module. It controls whether the image zoom feature is active or inactive in your Back Office product list.
  - **Effect of changing this setting:**
    - *When enabled (YES):* When you navigate to **Catalog > Products** in your Back Office, hovering over any product image thumbnail in the list will display a larger, zoomed version of that image.
    - *When disabled (NO):* The zoom functionality will be turned off. Hovering over product images will have no special effect, and you will see the standard small thumbnails.
  - **Recommended value:** YES
  - **Merchant scenario / example:** If you want to use the convenient zoom feature to quickly check product images, ensure this is set to “YES”. If you find it interferes with another Back Office customization or simply prefer not to use it, set it to “NO”.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable Zoom on Product List | YES | Activates or deactivates the image zoom feature on the Back Office product list. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve enabled the module, but the zoom isn’t working on my product list. What should I do?**
A:

1. **Clear Cache:** Go to **Advanced Parameters > Performance** in your Back Office and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes, PrestaShop’s cache can prevent new JavaScript from loading.
2. **Check Browser Console:** Open your browser’s developer tools (usually F12) and look for any errors in the “Console” tab. This might indicate a conflict with another module or theme.
3. **Module Conflicts:** Temporarily disable other modules that modify the Back Office product list (if any) to see if there’s a conflict.
4. **Theme Overrides:** If you are using a heavily customized Back Office theme, it might be overriding the standard product list structure, preventing the module from injecting its JavaScript. Contact your theme developer or MyPresta.eu support.

**Q: The zoomed image appears, but it looks blurry or pixelated.**
A: The module displays the image that PrestaShop provides for the product list. If the original image uploaded for that product is low resolution, the zoomed version will also appear blurry. Ensure you upload high-resolution images for your products.

**Q: Does this module slow down my Back Office?**
A: No, the module is very lightweight. It only loads a small JavaScript library and applies it when you hover over an image. It does not perform heavy operations or database queries that would impact performance.

**Q: Can I customize the size of the zoom box or the zoom level?**
A: The module uses a standard “elevateZoom” tool, which has some default behaviors. While the module itself doesn’t offer configuration options for these specific visual aspects, a developer could potentially modify the `zplb.js` file to adjust these parameters. This would require custom coding.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Zoom images on product list in back office” module (`zplb`) is a simple, yet effective, PrestaShop module primarily designed to inject client-side JavaScript into the Back Office product list. It leverages PrestaShop’s hook system to load its assets and relies on a third-party JavaScript library (elevateZoom, though integrated into `zplb.js`) to provide the zoom functionality. It does not introduce new database tables or complex business logic.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. This module is exclusively for the Back Office.
- **Back-Office Admin Controllers**: None. The module’s configuration is handled directly within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

- None. The module does not define any custom classes or `ObjectModel` instances. All logic is contained within the main `zplb/index.php` file.

### 4.4 JavaScript Assets (`views/js/`)

- `zplb/lib/js/zplb.js`
  - **Scope:** Back-office. This script is loaded specifically on the Back Office product list page.
  - **Functionality:** This file contains the core JavaScript logic for the zoom feature. It likely includes or integrates the “elevateZoom” library. It targets the product image elements within the Back Office product list table (e.g., `img.img-thumbnail` or similar selectors used by PrestaShop’s product list). It binds mouseover/hover events to these images and initializes the zoom functionality, creating the magnified view.

### 4.5 CSS Stylesheets (`views/css/`)

- None. The module does not include any custom CSS files. The styling for the zoom box is typically handled by the JavaScript library itself, often injecting inline styles or using minimal default styling that integrates well with PrestaShop’s Back Office.

### 4.6 Smarty Template Structure (`views/templates/`)

- None. The module does not use any `.tpl` files. Its functionality is injected directly via JavaScript into the existing Back Office product list HTML structure.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  - The module does not create any custom database tables.
  - It stores its configuration (e.g., the “Enable Zoom” setting) in the `ps_configuration` table, using a key like `ZPLB_ENABLED`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayBackOfficeHeader` | Executed in the `<head>` section of every Back Office page. | Used to conditionally load the `zplb.js` script only when the current Back Office page is the product list (`AdminProducts`). This ensures the script is not loaded unnecessarily on other admin pages, optimizing performance. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Zoom images on product list in back office” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
