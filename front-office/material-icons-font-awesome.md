---
title: "Material Icons + Font Awesome - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Material Icons + Font Awesome PrestaShop module by MyPresta.eu."
sidebar:
  label: "Material Icons + Font Awesome - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Material Icons + Font Awesome Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/material-icons-font-awesome.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/material-icons-font-awesome/)
>
> ---


# Material Icons + Font Awesome

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special requirements beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main and only configuration screen for the “Material Icons + Font Awesome” module. You’ll find it by navigating to **Modules > Module Manager**, searching for “Material Icons + Font Awesome”, and clicking “Configure”.

#### **Add Font Awesome**

- **What this setting does:** This switch controls whether the Font Awesome icon library is loaded into your store’s front-office (what customers see) and back-office (your admin panel).
- **Effect of changing this setting:**
  - *When enabled:* The Font Awesome CSS file will be added to the `<head>` section of your website, making all Font Awesome icons available for use. This will fix any missing Font Awesome icons.
  - *When disabled:* The Font Awesome CSS file will NOT be loaded by this module. If your theme or another module already loads Font Awesome, or if you don’t need it, you can disable this to avoid loading it twice.
- **Recommended value:**
  - **Enabled** if you notice missing Font Awesome icons on your storefront or in the back-office, or if you plan to use Font Awesome icons in your content.
  - **Disabled** if all Font Awesome icons already display correctly (meaning your theme or another module is already loading it) to prevent redundant loading.
- **Merchant scenario / example:** You’ve installed a new payment module, and its payment method icons (e.g., a credit card symbol) are showing as empty boxes. If these icons are based on Font Awesome, enabling this setting will make them appear correctly.

#### **Add Material Icons**

- **What this setting does:** This switch controls whether the Material Icons library (from Google) is loaded into your store’s front-office and back-office.
- **Effect of changing this setting:**
  - *When enabled:* The Material Icons CSS file will be added to the `<head>` section of your website, making all Material Icons available for use. This will fix any missing Material Icons.
  - *When disabled:* The Material Icons CSS file will NOT be loaded by this module. If your theme or another module already loads Material Icons, or if you don’t need them, you can disable this.
- **Recommended value:**
  - **Enabled** if you notice missing Material Icons on your storefront or in the back-office.
  - **Disabled** if all Material Icons already display correctly (meaning your theme or another module is already loading it) to prevent redundant loading.
- **Merchant scenario / example:** Your theme uses Material Icons for its navigation arrows or some product page elements, but after a theme update, they’ve disappeared. Enabling this setting will likely bring them back.

#### **Configuration Quick Reference Table**

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Add Font Awesome | Enabled (if needed) | Loads Font Awesome icon library for front and back office. Fixes missing Font Awesome icons. |
| Module Configuration | Add Material Icons | Enabled (if needed) | Loads Material Icons library for front and back office. Fixes missing Material Icons. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve enabled the settings, but icons are still missing. What should I do?**
A: First, clear your PrestaShop cache. Go to **Advanced Parameters > Performance**, and click “Clear cache” in the top right. Also, clear your browser’s cache (Ctrl+F5 or Cmd+Shift+R). If icons are still missing, it’s possible the icons you’re looking for belong to a different icon library not covered by this module, or there’s a CSS conflict in your theme.

**Q: Will this module slow down my website?**
A: The module loads standard CSS files for the icon libraries. If you only enable the libraries you need, and they aren’t already loaded by your theme, the performance impact is minimal and necessary for correct display. If you enable a library that’s already loaded by your theme, you’ll be loading it twice, which can cause a slight slowdown. Always check if your theme already includes these libraries before enabling them here.

**Q: My custom theme has its own icon set. Will this module interfere?**
A: It shouldn’t interfere directly. This module adds the specified icon libraries. If your theme uses a different icon set (e.g., custom SVGs or another font icon library), this module will simply add Font Awesome and/or Material Icons alongside it. If you experience conflicts, you can try disabling one or both options in the module to see if it resolves the issue.

**Q: How do I know if my theme already loads Font Awesome or Material Icons?**
A: The easiest way is to right-click on your store’s page (front-office) and select “View Page Source” or “Inspect Element.” Then search for “font-awesome.css” or “material-icons.css” within the `<head>` section. If you find them, your theme is likely already loading them. Alternatively, if all icons display correctly without this module, then your theme or another module is already handling it.

**Q: Can I use both Font Awesome and Material Icons at the same time?**
A: Yes, absolutely. You can enable both options in the module configuration. This is often necessary if different parts of your store (e.g., your theme and a third-party module) rely on different icon libraries.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Material Icons + Font Awesome” module is a lightweight PrestaShop module primarily designed to inject external CSS stylesheets for icon libraries. It follows a standard PrestaShop module structure, leveraging hooks to integrate its functionality into the front-office and back-office. It does not introduce custom controllers, models, or database tables, focusing solely on asset management.

### 4.2 Controllers (`controllers/`)

This module does not contain any custom front-office or back-office controllers. All logic is handled within the main module file (`fonticons.php`) via hooks.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or extend `ObjectModel`. All configuration is stored directly in `ps_configuration` using the keys defined below.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include any custom JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)

The module’s core functionality relies on these CSS files:

- **`fonticons/views/css/font-awesome.css`**:

  - **Scope**: Front-office and Back-office.
  - **Purpose**: Contains the CSS rules and `@font-face` declarations for the Font Awesome icon library. This file is responsible for making Font Awesome icons available throughout the store.
  - **Key CSS class selectors**: `fa`, `fas`, `far`, `fal`, `fab` (for different Font Awesome styles), followed by specific icon classes like `fa-shopping-cart`, `fa-user`, etc. Developers can override these by targeting these classes in their theme’s CSS.
- **`fonticons/views/css/material-icons.css`**:

  - **Scope**: Front-office and Back-office.
  - **Purpose**: Contains the CSS rules and `@font-face` declarations for the Material Icons library from Google. This file makes Material Icons available.
  - **Key CSS class selectors**: `material-icons`. Icons are typically rendered by placing the icon’s ligature name within an element with this class (e.g., `<i class="material-icons">shopping_cart</i>`). Developers can override styling for this class.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`fonticons/views/advert.tpl`**:
  - **Scope**: Back-office (module configuration page).
  - **Purpose**: This template is used to display an advertisement or promotional message within the module’s configuration page in the PrestaShop back-office. It is rendered by the `getContent()` method.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  This module does not create any custom database tables. It stores its configuration settings in the standard `ps_configuration` table.

  - `ps_configuration` entries:
    - `fonticons_FA`: Stores the status (1 for enabled, 0 for disabled) of Font Awesome inclusion for the front-office.
    - `fonticons_MI`: Stores the status (1 for enabled, 0 for disabled) of Material Icons inclusion for the front-office.
    - `BO_fonticons_FA`: Stores the status (1 for enabled, 0 for disabled) of Font Awesome inclusion for the back-office.
    - `BO_fonticons_MI`: Stores the status (1 for enabled, 0 for disabled) of Material Icons inclusion for the back-office.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Executed in the `<head>` section of every front-office page. | Used to load the Font Awesome and/or Material Icons CSS files for the customer-facing part of the store, based on `fonticons_FA` and `fonticons_MI` configuration. |
| `actionAdminControllerSetMedia` | Executed when an AdminController is setting its media assets (CSS/JS). | Used to load the Font Awesome and/or Material Icons CSS files for the PrestaShop back-office, based on `BO_fonticons_FA` and `BO_fonticons_MI` configuration. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please log in to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). You will find your purchased modules and download links there. For technical assistance or any questions, please use the support channels provided on MyPresta.eu.
