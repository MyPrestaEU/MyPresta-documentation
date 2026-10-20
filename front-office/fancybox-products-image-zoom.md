---
title: "Fancybox products image zoom - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Fancybox products image zoom PrestaShop module by MyPresta.eu."
sidebar:
  label: "Fancybox products image zoom - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Fancybox products image zoom Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/fancybox-products-image-zoom.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/fancybox-products-image-zoom/)
>
> ---


# Fancybox products image zoom

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the Fancybox products image zoom module. You’ll find it by navigating to **Modules > Module Manager**, searching for “Fancybox products image zoom”, and clicking “Configure”.

#### Theme Support & Selector Settings

These settings help the module identify the correct elements on your product page to apply the Fancybox zoom, especially important for custom themes.

- **Theme support**

  - **What this setting does:** This is a crucial setting that tells the module which theme structure it should expect. It helps the module correctly identify the main product image and its thumbnails on your product pages.
  - **Effect of changing this setting:**
    - *When set to “Classic”:* The module will use predefined selectors that work perfectly with PrestaShop’s default “Classic” theme. This is the most common and recommended setting if you are using the Classic theme or a theme based very closely on it.
    - *When set to “Hummingbird”:* The module will use predefined selectors for the “Hummingbird” theme, which is the default theme for PrestaShop 8.1 and newer.
    - *When set to “Custom”:* This option allows you to manually specify the CSS selectors for your main product image and thumbnails. This is essential if you are using a heavily customized theme or a third-party theme that doesn’t follow the “Classic” or “Hummingbird” structure.
  - **Recommended value:** “Classic” if you are on PrestaShop 1.7.x to 8.0.x with the Classic theme. “Hummingbird” if you are on PrestaShop 8.1+ with the Hummingbird theme. “Custom” if you have a unique theme.
  - **Merchant scenario / example:** If your product images aren’t zooming correctly after installation, and you’re using a custom theme, switching this to “Custom” and then adjusting the selectors below is the next step.
- **Detected theme profile**

  - **What this setting does:** This field displays the theme profile the module has automatically detected based on your “Theme support” selection. It’s an informational field, not directly configurable.
  - **Effect of changing this setting:** No direct effect, as it’s a display-only field. It simply confirms which set of selectors the module is currently using.
  - **Recommended value:** N/A (informational).
  - **Merchant scenario / example:** You’ve set “Theme support” to “Classic”, and this field confirms “Classic” is detected.
- **Hummingbird cover selector** (Only visible if “Theme support” is “Hummingbird”)

  - **What this setting does:** Specifies the CSS selector for the main product cover image container when using the Hummingbird theme. This helps the module target the correct area for the zoom.
  - **Effect of changing this setting:** If incorrect, the Fancybox zoom might not activate on the main product image, or it might target the wrong element.
  - **Recommended value:** Leave as default unless your Hummingbird-based theme has significantly altered its structure.
  - **Merchant scenario / example:** Your Hummingbird theme has a unique structure for the main image. You might need to inspect your theme’s code to find the correct CSS class or ID for the main image container and enter it here.
- **Hummingbird image selector** (Only visible if “Theme support” is “Hummingbird”)

  - **What this setting does:** Specifies the CSS selector for the actual `<img>` tag of the main product cover image within the Hummingbird theme.
  - **Effect of changing this setting:** Similar to the cover selector, an incorrect value will prevent the zoom from working on the main image.
  - **Recommended value:** Leave as default.
  - **Merchant scenario / example:** If the zoom isn’t working on the main image, and you’re on Hummingbird, check this selector.
- **Hummingbird thumbnails selector** (Only visible if “Theme support” is “Hummingbird”)

  - **What this setting does:** Specifies the CSS selector for the product thumbnail images container when using the Hummingbird theme. This is important for creating a gallery from your thumbnails.
  - **Effect of changing this setting:** If incorrect, the module might not be able to create a Fancybox gallery from your thumbnails, or clicking thumbnails might not open the Fancybox.
  - **Recommended value:** Leave as default.
  - **Merchant scenario / example:** If clicking on thumbnails doesn’t open the Fancybox gallery, verify this selector.
- **Main cover picture selector** (Only visible if “Theme support” is “Custom”)

  - **What this setting does:** When “Custom” theme support is selected, this field allows you to manually enter the CSS selector for the container element that holds your main product image on the product page.
  - **Effect of changing this setting:** If this selector is incorrect, the Fancybox zoom will not activate on your main product image.
  - **Recommended value:** You’ll need to use your browser’s developer tools (F12) to inspect your product page and find the unique CSS class or ID of the `<div>` or other container element that wraps your main product image.
  - **Merchant scenario / example:** Your custom theme uses `<div id="my-custom-main-image-wrapper">` for the main image. You would enter `#my-custom-main-image-wrapper` here.
- **Main cover image** (Only visible if “Theme support” is “Custom”)

  - **What this setting does:** When “Custom” theme support is selected, this field allows you to manually enter the CSS selector for the actual `<img>` tag of your main product image.
  - **Effect of changing this setting:** If this selector is incorrect, the Fancybox zoom will not activate on your main product image.
  - **Recommended value:** Use your browser’s developer tools to find the unique CSS class or ID of the `<img>` tag itself.
  - **Merchant scenario / example:** Your custom theme uses `<img class="product-main-image-src">` for the main image. You would enter `.product-main-image-src` here.
- **Thumbs pictures selector** (Only visible if “Theme support” is “Custom”)

  - **What this setting does:** When “Custom” theme support is selected, this field allows you to manually enter the CSS selector for the container element that holds your product thumbnail images.
  - **Effect of changing this setting:** If this selector is incorrect, the module will not be able to create a Fancybox gallery from your thumbnails, or clicking thumbnails might not open the Fancybox.
  - **Recommended value:** Use your browser’s developer tools to find the unique CSS class or ID of the `<div>` or other container element that wraps your product thumbnails.
  - **Merchant scenario / example:** Your custom theme uses `<ul id="product-thumbnails-list">` for the thumbnails. You would enter `#product-thumbnails-list` here.

#### Fancybox Behavior Settings

These settings control how the Fancybox zoom behaves and interacts with your customers.

- **Create gallery**

  - **What this setting does:** Determines whether all product images (main image and thumbnails) are grouped into a single Fancybox gallery. When enabled, clicking any image will open Fancybox, and customers can then navigate through all product images using arrows.
  - **Effect of changing this setting:**
    - *When enabled (“On”):* Customers can browse through all product images in a full-screen Fancybox overlay, using navigation arrows. This provides a comprehensive view of the product.
    - *When disabled (“Off”):* Clicking an image will only open that specific image in Fancybox. Customers cannot navigate to other product images from within the Fancybox view.
  - **Recommended value:** “On” for a better user experience and to encourage customers to view all product angles.
  - **Merchant scenario / example:** You want customers to easily flip through all product images without closing and re-opening the zoom for each one. Enable this.
- **Swipe**

  - **What this setting does:** Enables or disables swipe gestures for navigating the Fancybox gallery on touch-enabled devices (smartphones, tablets).
  - **Effect of changing this setting:**
    - *When enabled (“On”):* Customers can swipe left or right on their touch devices to move between images in the Fancybox gallery.
    - *When disabled (“Off”):* Swipe gestures will not work. Customers will need to use the navigation arrows (if “Create gallery” is enabled).
  - **Recommended value:** “On” for a modern, intuitive mobile experience.
  - **Merchant scenario / example:** You want your mobile users to have a seamless, natural way to browse product images. Keep this enabled.
- **Avoid doubled cover image in gallery**

  - **What this setting does:** When “Create gallery” is enabled, sometimes the main product image might appear twice in the gallery (once as the main image, and again if it’s also listed as a thumbnail). This setting prevents that duplication.
  - **Effect of changing this setting:**
    - *When enabled (“On”):* The module will try to detect and remove any duplicate main product image from the Fancybox gallery, ensuring each image appears only once.
    - *When disabled (“Off”):* If the main product image is also part of the thumbnail list, it might appear twice in the Fancybox gallery.
  - **Recommended value:** “On” for a cleaner, more professional gallery experience.
  - **Merchant scenario / example:** You notice that when customers open the Fancybox gallery, the first image is identical to the second. Enabling this will fix that.
- **Display captions (image titles)**

  - **What this setting does:** Controls whether the title/caption associated with each product image is displayed within the Fancybox overlay. These titles are usually set in your PrestaShop product image management.
  - **Effect of changing this setting:**
    - *When enabled (“On”):* The image title will appear as a caption below or above the image in the Fancybox overlay.
    - *When disabled (“Off”):* No caption will be displayed, providing a cleaner, image-only view.
  - **Recommended value:** “On” if your image titles provide useful information (e.g., “Front View”, “Detail Shot”, “Model Wearing Product”). “Off” if your image titles are generic or you prefer a minimalist look.
  - **Merchant scenario / example:** You use descriptive titles for your product images and want customers to see them when zooming. Enable this.
- **Switch main picture on thumb mouse over**

  - **What this setting does:** Determines if hovering your mouse over a product thumbnail automatically changes the main product image displayed on the product page, *before* clicking to open Fancybox.
  - **Effect of changing this setting:**
    - *When enabled (“On”):* Moving your mouse cursor over a thumbnail will instantly swap the main product image to show the hovered thumbnail. This is a common and convenient feature for shoppers.
    - *When disabled (“Off”):* The main product image will only change when a thumbnail is clicked, not just hovered over.
  - **Recommended value:** “On” for a more interactive and user-friendly browsing experience.
  - **Merchant scenario / example:** You want customers to quickly preview different product images by just moving their mouse, without needing to click. Enable this.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | **Theme support** | Classic / Hummingbird | Selects predefined CSS selectors for your theme (Classic, Hummingbird, or Custom). Crucial for module functionality. |
| Module Configuration | **Detected theme profile** | N/A (Informational) | Shows which theme profile is currently active. |
| Module Configuration | **Hummingbird cover selector** | Default | CSS selector for main image container (Hummingbird theme). |
| Module Configuration | **Hummingbird image selector** | Default | CSS selector for main `<img>` tag (Hummingbird theme). |
| Module Configuration | **Hummingbird thumbnails selector** | Default | CSS selector for thumbnail container (Hummingbird theme). |
| Module Configuration | **Main cover picture selector** | Custom (Inspect theme) | CSS selector for main image container (Custom theme). |
| Module Configuration | **Main cover image** | Custom (Inspect theme) | CSS selector for main `<img>` tag (Custom theme). |
| Module Configuration | **Thumbs pictures selector** | Custom (Inspect theme) | CSS selector for thumbnail container (Custom theme). |
| Module Configuration | **Create gallery** | On | Groups all product images into a browsable Fancybox gallery. |
| Module Configuration | **Swipe** | On | Enables swipe gestures for gallery navigation on touch devices. |
| Module Configuration | **Avoid doubled cover image in gallery** | On | Prevents the main image from appearing twice in the gallery. |
| Module Configuration | **Display captions (image titles)** | On / Off (Merchant preference) | Shows image titles as captions in the Fancybox overlay. |
| Module Configuration | **Switch main picture on thumb mouse over** | On | Changes main product image on thumbnail hover. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: The Fancybox zoom isn’t appearing at all on my product pages.**
A:

1. **Check Module Status:** Ensure the module is installed and enabled in **Modules > Module Manager**.
2. **Theme Support Setting:** Go to the module’s configuration page. If you’re using the “Classic” theme, ensure “Theme support” is set to “Classic”. If you’re on PrestaShop 8.1+ with the Hummingbird theme, set it to “Hummingbird”. If you have a custom theme, set it to “Custom” and carefully review the CSS selectors you’ve entered (see next point).
3. **Custom Theme Selectors:** If “Theme support” is “Custom”, the most common issue is incorrect CSS selectors. Use your browser’s developer tools (F12) to inspect your product page. Find the exact CSS classes or IDs for your main product image container, the `<img>` tag, and your thumbnail container. Update these in the module settings.

**Q: The Fancybox opens, but it’s showing the wrong image or only one image.**
A:

1. **“Create gallery” Setting:** Ensure “Create gallery” is set to “On” in the module configuration if you want to browse multiple images.
2. **Thumbnail Selectors:** If “Create gallery” is on but only one image appears, check your “Thumbs pictures selector” (especially if “Theme support” is “Custom”). The module needs to correctly identify all your thumbnails to build the gallery.
3. **Image Titles/Captions:** If captions aren’t showing, ensure “Display captions (image titles)” is “On” and that your product images actually have titles defined in the PrestaShop back office.

**Q: Swipe gestures aren’t working on my mobile device.**
A:

1. **“Swipe” Setting:** Make sure the “Swipe” option is set to “On” in the module configuration.
2. **Gallery Enabled:** Swipe only works if “Create gallery” is also “On”, as it’s for navigating between multiple images.
3. **Browser/Device Compatibility:** While widely supported, very old browsers or specific device configurations might have issues. Test on a modern mobile browser.

**Q: My product page layout looks a bit off after installing the module.**
A:

1. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache”. Sometimes, old cached files can interfere with new module styling.
2. **Theme Conflicts:** While the module tries to be compatible, very specific custom theme CSS might conflict. If clearing cache doesn’t help, temporarily disable the module to see if the issue disappears. If it does, you might need a web developer to adjust your theme’s CSS or the module’s custom selectors.

**Q: How do I find the correct CSS selectors for my custom theme?**
A:

1. Open your product page in a web browser (Chrome, Firefox, Edge).
2. Right-click on your main product image and select “Inspect” or “Inspect Element”.
3. This will open the browser’s developer tools. Look for the `<img>` tag of your main image and its parent `<div>` or other container. Note down any unique `id` attributes (e.g., `id="my-image"`) or `class` attributes (e.g., `class="product-image-wrapper"`).
4. Repeat this for your product thumbnails.
5. Use these IDs (prefixed with `#`, e.g., `#my-image`) or classes (prefixed with `.`, e.g., `.product-image-wrapper`) in the module’s “Custom” theme settings. You might need to experiment a bit to find the most specific and reliable selectors.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The `fancyzoom` module is a lightweight PrestaShop module primarily designed to replace the default product image zoom functionality with Fancybox. It achieves this by hooking into `displayHeader` to inject its custom JavaScript and CSS, and by using JavaScript to identify and re-initialize image elements with Fancybox. The module’s configuration is handled via the standard `getContent()` method in the main module file, storing settings in `ps_configuration`. It does not introduce custom database tables, `ObjectModel` classes, or dedicated front/admin controllers beyond the main module configuration.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. All front-office functionality is injected via hooks and handled by JavaScript.
- **Back-Office Admin Controllers**: None. All back-office configuration is handled by the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)

- No custom classes or `ObjectModel` definitions are present in the `classes/` directory. All core logic resides within the main `fancyzoom.php` module file.

### 4.4 JavaScript Assets (`views/js/`)

The module includes two JavaScript files, primarily for front-office functionality. They are registered via `displayHeader` hook.

- `fancyzoom/views/templates/js/fancyzoom.js`

  - **Scope:** Front-office.
  - **Responsibility:** This is the core script that initializes Fancybox. It dynamically identifies the main product image and thumbnails based on the configured CSS selectors (or default Classic/Hummingbird selectors). It then binds click events to these images to open them in a Fancybox gallery. It also handles the “switch main picture on thumb mouse over” functionality. It’s responsible for disabling the default PrestaShop zoom.
  - **Key functionalities:**
    - Disables default PrestaShop image zoom.
    - Detects theme profile (Classic, Hummingbird, Custom) and applies appropriate selectors.
    - Initializes Fancybox on product images.
    - Manages Fancybox gallery creation and options (swipe, captions, doubled images).
    - Handles thumbnail hover effect to change the main image.
    - Listens for `updateProduct` event (PrestaShop 1.7+ product page updates) to re-initialize Fancybox.
- `fancyzoom/views/templates/js/touchswipe.js`

  - **Scope:** Front-office.
  - **Responsibility:** This is a third-party library that provides robust touch swipe event detection. It’s used by `fancyzoom.js` to enable swipe navigation within the Fancybox gallery on touch devices.
  - **Key functionalities:** Provides a jQuery plugin for detecting swipe gestures (left, right, up, down) and other touch events.

### 4.5 CSS Stylesheets (`views/css/`)

The module includes one CSS file for front-office styling.

- `fancyzoom/views/templates/css/fancyzoom.css`
  - **Scope:** Front-office customer styling.
  - **Responsibility:** Contains the necessary CSS for the Fancybox overlay itself, including styling for the navigation arrows, close button, captions, and general appearance. It ensures the Fancybox modal is properly positioned and styled.
  - **Key CSS class selectors developers can override:**
    - `.fancybox-container`: Main container for the Fancybox overlay.
    - `.fancybox-bg`: Background overlay.
    - `.fancybox-toolbar`: Toolbar with close button, etc.
    - `.fancybox-caption`: Caption area.
    - `.fancybox-button`: Buttons (close, navigation).
    - `.fancybox-image`: The image itself within Fancybox.
      Developers can override these classes in their theme’s `custom.css` or similar file to match their store’s branding.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - `fancyzoom/views/templates/hook/fancyzoom.tpl`
    - **Hook:** `displayHeader`
    - **Purpose:** This template is responsible for injecting the necessary JavaScript variables and the module’s JS and CSS files into the `<head>` section of the front-office. It passes configuration variables from the back office (like selectors, gallery options) to the `fancyzoom.js` script.
- **Admin templates (`views/templates/admin/`)**:

  - `fancyzoom/views/templates/admin/admin.tpl`
    - **Purpose:** This template renders the module’s configuration form in the PrestaShop back office. It displays all the settings described in Section 4.1, including input fields for selectors, checkboxes for gallery options, and the theme profile detection.
- **Front-office templates (`views/templates/front/`)**: None.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  The module does not create any custom database tables. All its configuration settings are stored in the `ps_configuration` table using keys prefixed with `FZ_` (e.g., `FZ_THEME`, `FZ_COVER_DIV`, `FZ_GALLERY`).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Injects the module’s CSS and JavaScript files, and passes configuration variables to the front-end scripts. This is where the Fancybox library and its initialization logic are loaded. |

## 5. Official Support & Updates

For official updates, technical support, and to download the latest versions of the “Fancybox products image zoom” module, please log in to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and integration.
