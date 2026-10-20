---
title: "Loading effect on attribute change - preloader - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Loading effect on attribute change - preloader PrestaShop module by MyPresta.eu."
sidebar:
  label: "Loading effect on attribute change - preloader - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Loading effect on attribute change - preloader Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/loading-effect-on-attribute-change-preloader.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/loading-effect-on-attribute-change-preloader/)
>
> ---


# Loading effect on attribute change - preloader

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the module name to access its settings. This module has a straightforward configuration page.

#### **Enable / Disable Preloader**

- **What this setting does:** This is the main switch to turn the loading effect on or off across your entire store.
- **Effect of changing this setting:**
  - *When enabled (YES):* The loading animation will appear on product pages whenever a customer changes product attributes.
  - *When disabled (NO):* The loading animation will not appear, and your product pages will behave as they did before installing the module (i.e., no visual feedback during attribute changes).
- **Recommended value:** YES
- **Merchant scenario / example:** You’ve just installed the module and want to activate it. Set this to YES. If you need to temporarily disable it for testing or during a major theme update, you can switch it to NO.

#### **Preloader Type**

- **What this setting does:** This option allows you to choose the style or type of loading animation that will be displayed. The module typically comes with a selection of pre-defined spinner animations.
- **Effect of changing this setting:**
  - *When set to “Spinner 1”:* A specific type of animated spinner (e.g., a simple rotating circle) will be shown.
  - *When set to “Spinner 2”:* A different animated spinner (e.g., a pulsing dot, a fading bar) will be shown.
  - *When set to “Custom Image”:* If available, this option would allow you to upload your own GIF or image to use as the preloader. (Based on the module description, this might be a future enhancement or a more advanced option not directly mentioned, but it’s a common feature for “preloader type” settings).
- **Recommended value:** Experiment with the available options to see which one best matches your store’s design and branding. A simple, clean spinner is often best.
- **Merchant scenario / example:** Your store has a minimalist design, so you might choose “Spinner 1” if it’s a clean, unobtrusive animation. If your brand is more playful, you might pick a more dynamic “Spinner 2” or even upload a custom branded GIF if the option is available.

#### **Preloader Color**

- **What this setting does:** This allows you to define the color of the loading animation. This is crucial for matching the preloader to your store’s color scheme.
- **Effect of changing this setting:**
  - *When set to `#007bff` (blue):* The spinner will appear in a blue color.
  - *When set to `#ff0000` (red):* The spinner will appear in a red color.
- **Recommended value:** A color that complements your store’s primary or accent colors. Often, a neutral gray, white, or your brand’s main action color works well.
- **Merchant scenario / example:** Your store’s main call-to-action buttons are green. Setting the preloader color to green will make it feel like an integrated part of your store’s design, rather than a generic element.

#### **Preloader Size (in pixels)**

- **What this setting does:** This controls the physical dimensions (width and height) of the loading animation.
- **Effect of changing this setting:**
  - *When set to `32px`:* The spinner will be small and subtle.
  - *When set to `64px`:* The spinner will be larger and more prominent.
- **Recommended value:** Start with a moderate size like `40px` or `48px`. Test on desktop and mobile to ensure it’s visible but not overly intrusive.
- **Merchant scenario / example:** On a product page with large images, a `32px` spinner might get lost. Increasing it to `48px` or `56px` would make it more noticeable without being distracting. Conversely, if your product images are small, a smaller spinner might be more appropriate.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable / Disable Preloader | YES | Activates or deactivates the loading animation on product attribute changes. |
| Module Configuration | Preloader Type | (Choose based on preference) | Selects the visual style of the loading spinner. |
| Module Configuration | Preloader Color | (Match your brand) | Sets the color of the loading animation to integrate with your store’s design. |
| Module Configuration | Preloader Size (in pixels) | 40px - 56px | Adjusts the physical size of the spinner for visibility and aesthetics. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve enabled the module, but I don’t see any loading effect on my product page.**
A:

1. **Clear Cache:** The most common reason. Go to **Advanced Parameters > Performance** in your PrestaShop Back Office and click “Clear cache” (or “Clear Smarty cache” in older versions).
2. **Module Position:** Ensure the module is hooked correctly. While the module automatically handles this, sometimes theme conflicts can prevent it. The module typically injects its CSS/JS into the `displayHeader` hook.
3. **Theme Overrides:** If you’re using a heavily customized theme, it might be overriding default PrestaShop JavaScript behavior for attribute changes, preventing the module from detecting the event. Contact your theme developer or a PrestaShop expert.
4. **Browser Cache:** Try clearing your browser’s cache or testing in an incognito/private browsing window.

**Q: The preloader appears, but it looks out of place or doesn’t match my store’s design.**
A:

1. **Adjust Color & Size:** Go to the module’s configuration page and experiment with the “Preloader Color” and “Preloader Size” settings. Try to match your brand’s primary or accent colors.
2. **Change Preloader Type:** If available, try different “Preloader Type” options to find one that visually fits your theme better.
3. **Custom CSS:** For advanced customization, a webmaster can use custom CSS to fine-tune its appearance (see Developer Guide).

**Q: The preloader appears, but it stays on the screen too long, even after the product attributes have updated.**
A: This usually indicates a JavaScript conflict or an issue with your theme’s attribute update mechanism. The module relies on standard PrestaShop events to know when to hide the preloader.

1. **Check for JavaScript Errors:** Open your browser’s developer console (F12) and look for any red error messages in the “Console” tab when changing attributes.
2. **Module Conflicts:** Temporarily disable other front-office modules that modify product page behavior (e.g., quick view modules, custom attribute modules) to see if one is causing a conflict.
3. **Theme Compatibility:** Ensure your theme is fully compatible with your PrestaShop version and doesn’t have outdated JavaScript.

**Q: Does this module slow down my website?**
A: No, the module itself is very lightweight. It adds a small amount of CSS and JavaScript to your page. Its purpose is to *visually manage* the perception of loading time, not to cause it. If your page is slow, the problem lies elsewhere (e.g., large images, unoptimized server, other heavy modules).

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Loading effect on attribute change - preloader” module (`ppreloader`) is a lightweight, front-office focused module designed to enhance user experience during AJAX-driven product attribute updates. It primarily leverages PrestaShop’s `displayHeader` hook to inject its CSS and JavaScript, which then listens for specific DOM changes or events on the product page to trigger and hide the loading animation. It does not introduce new database tables or complex backend logic, focusing solely on front-end presentation.

### 4.2 Controllers (`controllers/`)

This module does not utilize any custom Front-Office or Back-Office Admin Controllers. All configuration is handled directly within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

This module does not introduce any custom classes or `ObjectModel` definitions. It operates entirely through its main module file and front-end assets.

### 4.4 JavaScript Assets (`views/js/`)

- **`ppreloader/views/js/ppreloader.js`**
  - **Scope:** Front-office (Product Page).
  - **Responsibility:** This script is the core of the module’s functionality.
    - It waits for the DOM to be ready.
    - It listens for changes on product attribute selectors (e.g., `select[name="group[X]"]`, radio buttons, color pickers, etc., depending on the theme’s structure).
    - It also likely listens for AJAX events related to product combination updates (e.g., `updateProduct` event or `ajaxComplete` calls targeting specific URLs).
    - When an attribute change is detected and an AJAX call is initiated, it dynamically inserts the preloader HTML structure (defined in `header.tpl` or generated on the fly) into a relevant container on the product page (e.g., `$('#product_images')` or `$('#product-details')`).
    - It applies the chosen `Preloader Type`, `Preloader Color`, and `Preloader Size` from the module’s configuration.
    - Once the AJAX call completes and the product information is updated, it removes the preloader HTML from the DOM.
    - It ensures mobile responsiveness of the preloader.

### 4.5 CSS Stylesheets (`views/css/`)

- **`ppreloader/views/css/ppreloader.css`**
  - **Scope:** Front-office customer styling.
  - **Responsibility:** This stylesheet defines the visual appearance and animation of the loading preloader.
    - It includes styles for the overlay that might cover the product area during loading.
    - It defines the CSS for various preloader types (spinners, dots, etc.), including their animation keyframes.
    - It ensures the preloader is centered and positioned correctly within its container.
    - It handles basic responsiveness for different screen sizes.
  - **Key CSS class selectors developers can override:**
    - `.ppreloader-overlay`: The main overlay container.
    - `.ppreloader-spinner`: The container for the actual spinner animation.
    - Specific classes for different spinner types (e.g., `.ppreloader-spinner-type1`, `.ppreloader-spinner-type2`).
    - `@keyframes` rules for the animations.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`ppreloader/views/header.tpl`**
  - **Scope:** Front-office.
  - **Hook:** `displayHeader`
  - **Responsibility:** This template is primarily responsible for including the module’s CSS and JavaScript files into the `<head>` section of the front-office pages.
    - It uses `{$css_dir}ppreloader.css` to link the stylesheet.
    - It uses `{$js_dir}ppreloader.js` to link the JavaScript file.
    - It also likely contains inline JavaScript to pass the module’s configuration settings (enabled status, type, color, size) from the Back Office to the `ppreloader.js` script, making them available for dynamic use. This is crucial for the JS to know how to render the preloader.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: This module does not create any custom SQL tables. All configuration settings are stored in the `ps_configuration` table using standard PrestaShop configuration keys (e.g., `PPRELOADER_ENABLED`, `PPRELOADER_TYPE`, `PPRELOADER_COLOR`, `PPRELOADER_SIZE`).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Executed in the `<head>` section of every front-office page. | Injects the module’s CSS (`ppreloader.css`) and JavaScript (`ppreloader.js`) files, along with passing configuration variables to the JS. |

## 5. Official Support & Updates

For official updates, technical support, and to download the latest versions of the “Loading effect on attribute change - preloader” module, please log in to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have.
