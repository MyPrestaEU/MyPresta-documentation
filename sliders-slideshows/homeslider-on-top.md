---
title: "Homeslider on top - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Homeslider on top PrestaShop module by MyPresta.eu."
sidebar:
  label: "Homeslider on top - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Homeslider on top Module on MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/homeslider-on-top.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/sliders-slideshows/homeslider-on-top/)
>
> ---


# Homeslider on top

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for a PrestaShop installation and will support this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

This module is designed to be extremely simple, primarily acting as a “bridge” to allow the *default PrestaShop Image slider* to be displayed in a new location. Therefore, its own configuration screen is minimal. The actual slider images, links, and settings (like speed, pause on hover, etc.) are managed through the standard PrestaShop “Image slider” module.

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installing “Homeslider on top,” navigate to **Modules > Module Manager**, search for “Homeslider on top,” and click “Configure.”

You will typically find a very simple configuration interface, primarily focused on enabling or disabling the module’s core functionality.

- **What this setting does:** This setting controls whether the “Homeslider on top” module is active and attempting to display your image slider in the designated top position.
- **Effect of changing this setting:**
  - *When enabled:* The module will register its hooks and attempt to render the default PrestaShop image slider at the top of your store.
  - *When disabled:* The module will cease to function, and the image slider will not appear in the top position (it will revert to its default placement if the standard Image slider module is still active and hooked elsewhere).
- **Recommended value:** **YES** (Enabled) if you want your slider to appear at the top.
- **Merchant scenario / example:** You’ve just launched a new collection and want to feature it prominently with a large banner at the very top of your site. You would enable this module. If you later decide you prefer the slider in a different location (e.g., below the header), you might disable this module and re-hook the standard Image slider module elsewhere.

**Important Note:** This module *does not* manage the images or settings of the slider itself. To add, edit, or remove slides, or to change slider behavior (like transition speed, auto-play, etc.), you must go to the configuration of the **“Image slider”** module (often found under **Modules > Module Manager**, search for “Image slider” or “ps\_imageslider”).

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Module Enabled/Disabled | Enabled | Controls whether the module actively displays the image slider at the top of the store. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My slider isn’t showing up at all, even after enabling the module.**
A:

1. **Check the “Image slider” module:** Ensure the *default PrestaShop “Image slider” module* (often named `ps_imageslider`) is installed, enabled, and has slides configured. This “Homeslider on top” module only changes the *position* of that existing slider.
2. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes, PrestaShop needs a cache refresh to recognize new module placements.
3. **Theme Compatibility:** While designed for broad compatibility, some heavily customized themes might override default hook behaviors. If issues persist, contact your theme developer or MyPresta.eu support.

**Q: The slider is showing, but it looks strange or misaligned.**
A:

1. **Check “Image slider” settings:** Ensure the images you’ve uploaded to the *default PrestaShop “Image slider” module* are of consistent dimensions and high quality.
2. **Theme Styling:** Your theme’s CSS might be conflicting. This module primarily handles placement. If the styling is off, it’s likely a CSS issue with your theme interacting with the slider’s default styles. You might need a web developer to inspect the CSS.

**Q: How do I change the images or the speed of the slider?**
A: This module only controls the *placement*. To manage the actual content (images, links, descriptions) and behavior (speed, auto-play, pause on hover) of the slider, you need to go to the configuration of the **“Image slider”** module (the standard PrestaShop module, usually found by searching “Image slider” in **Modules > Module Manager**).

**Q: Can I have two sliders, one at the top and one in the default position?**
A: This module specifically moves the *default* PrestaShop image slider to the top. If you want a second, independent slider, you would need a different module designed for that purpose.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a technical overview for developers and webmasters looking to understand, customize, or troubleshoot the “Homeslider on top” module.

### 4.1 Architecture Overview

The “Homeslider on top” module is a lightweight PrestaShop module primarily designed to alter the display location of the core `ps_imageslider` module. It achieves this by unregistering `ps_imageslider` from its default hooks (like `displayHome`) and re-registering it to a more prominent hook, typically `displayHeader`. It does not introduce new database tables, complex classes, or extensive front-office assets, making it a simple yet effective “hook manager” for the existing slider functionality.

### 4.2 Controllers (`controllers/`)

This module does not introduce any custom Front-Office or Back-Office controllers. All configuration is handled directly within the `getContent()` method of the main module file.

### 4.3 Core Classes & Models (`classes/`)

This module does not introduce any custom classes or models. It operates by interacting with PrestaShop’s core module management functions.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include any custom JavaScript files. The JavaScript for the slider functionality is provided by the `ps_imageslider` module itself.

### 4.5 CSS Stylesheets (`views/css/`)

This module does not include any custom CSS files. The styling for the slider is provided by the `ps_imageslider` module and/or the active PrestaShop theme.

### 4.6 Smarty Template Structure (`views/templates/`)

This module does not include any custom Smarty template files. It relies on the templates provided by the `ps_imageslider` module.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: This module does not create any custom database tables. Its configuration is stored in `ps_configuration` using standard PrestaShop configuration keys.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `install()` | During module installation | Registers the module to `displayHeader` and potentially unregisters `ps_imageslider` from `displayHome` or other default hooks. |
| `uninstall()` | During module uninstallation | Unregisters the module from `displayHeader` and potentially re-registers `ps_imageslider` to its default hooks. |
| `displayHeader` | Renders content within the `<head>` section or at the very top of the `<body>` | This is the primary hook where the module attempts to render the `ps_imageslider` content. |
| `hookDisplayHeader` | When `displayHeader` is called | The module’s method that executes when `displayHeader` is called. It typically calls `Module::hookDisplayHome()` of the `ps_imageslider` module to render its content. |

The core logic resides in the `homeslider-on-top.php` file, specifically within the `install()`, `uninstall()`, and `hookDisplayHeader()` methods. The `hookDisplayHeader()` method is crucial as it’s responsible for fetching and rendering the content of the `ps_imageslider` module when this module is active.

**Key Logic within `homeslider-on-top.php`:**

- **`__construct()`**: Sets up basic module information.
- **`install()`**:
  - Calls `parent::install()`.
  - Registers the module to `displayHeader`.
  - Crucially, it often attempts to unregister the `ps_imageslider` module from `displayHome` to prevent duplicate display, and then registers `ps_imageslider` to `displayHeader` if it’s not already there, or ensures its content is rendered via this module’s `hookDisplayHeader`.
- **`uninstall()`**:
  - Calls `parent::uninstall()`.
  - Unregisters the module from `displayHeader`.
  - Re-registers `ps_imageslider` to `displayHome` to restore default behavior.
- **`getContent()`**: Handles the module’s back-office configuration form (which is usually very simple, often just an enable/disable switch).
- **`hookDisplayHeader()`**:
  - This method is executed when the `displayHeader` hook is called by PrestaShop.
  - It typically checks if the `ps_imageslider` module is installed and enabled.
  - If so, it directly calls the `hookDisplayHome()` method of the `ps_imageslider` module to retrieve its rendered content and return it, effectively “moving” the slider’s output to the `displayHeader` position.

Developers looking to customize this module would primarily focus on the `hookDisplayHeader()` method if they wanted to alter how the `ps_imageslider` content is retrieved or wrapped, or the `install()`/`uninstall()` methods if they needed to change the specific hooks involved.

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Homeslider on top” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
