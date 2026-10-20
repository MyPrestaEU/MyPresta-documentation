---
title: "Homepage tabs - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Homepage tabs PrestaShop module by MyPresta.eu."
sidebar:
  label: "Homepage tabs - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Homepage tabs Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-tabs.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/homepage-tabs/)
>
> ---


# Homepage tabs

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No unusual server configurations are required.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Homepage tabs” module in the Module Manager. This will take you to the main configuration screen.

The module’s configuration page is straightforward, primarily focusing on ensuring the module can receive updates.

- **What this setting does:** This section manages the module’s ability to check for and receive updates from MyPresta.eu. Keeping your modules updated is crucial for security, performance, and compatibility with new PrestaShop versions.
- **Effect of changing this setting:**
  - *When enabled (default):* The module will periodically check MyPresta.eu for new versions. If an update is available, you will be notified in your PrestaShop back office, allowing you to easily download and install the latest version. This ensures your module remains compatible and benefits from the latest features and bug fixes.
  - *When disabled:* The module will not check for updates. You will not be notified of new versions, potentially missing out on important improvements, security patches, or compatibility fixes. You would need to manually check for updates on MyPresta.eu.
- **Recommended value:** **YES (Enabled)**. It is highly recommended to keep this setting enabled to ensure your module is always up-to-date and secure.
- **Merchant scenario / example:** Imagine PrestaShop releases a new minor version (e.g., 8.1.5). An update to the “Homepage tabs” module might be released to ensure full compatibility. With updates enabled, you’d be notified and could easily update, preventing any potential issues. If disabled, your tabs might stop working correctly after the PrestaShop update, and you wouldn’t know why until you manually checked for module updates.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Update Checks (mypresta\_updates, update\_, updatev\_) | YES (Enabled) | Enables automatic checks for module updates from MyPresta.eu, ensuring compatibility, security, and access to new features. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My homepage tabs are not showing up after installation.**
A:

1. **Check Module Position:** Go to **Design > Positions** in your PrestaShop back office. Search for `displayHome`. Ensure that the “Homepage tabs” module is hooked to `displayHome`. If it’s not there, use the “Transplant a module” button to add it.
2. **Clear Cache:** Always clear your PrestaShop cache after installing or configuring modules. Go to **Advanced Parameters > Performance** and click “Clear cache” in the top right corner.
3. **Check for Theme Conflicts:** Some custom themes might override the `displayHome` hook or have specific styling that hides the module. Temporarily switch to the default PrestaShop theme (Classic) to see if the tabs appear. If they do, your theme requires custom CSS or template adjustments.

**Q: The products in the tabs don’t look right (e.g., wrong size, misaligned).**
A: This is typically a styling issue related to your store’s theme. The module itself provides the product data, but your theme dictates how product listings are displayed.

1. **Clear Cache:** Again, clear your PrestaShop cache.
2. **Theme CSS:** Your theme’s CSS might be conflicting with the module’s default styling. A web developer can inspect the elements using browser developer tools and apply custom CSS overrides in your theme’s `custom.css` file to correct the appearance.

**Q: Can I change the order of the tabs or which products appear in them?**
A: This module restores the *functionality* of homepage tabs (Popular, New, Bestsellers, On Sale). The specific product types displayed (e.g., “Popular Products”) are determined by PrestaShop’s core logic for those categories. This module does not offer options to manually select products for each tab or reorder the tabs themselves through its configuration. For advanced customization like custom product selections or tab ordering, you would typically need a more advanced module or custom development.

**Q: The module is installed, but I don’t see any configuration options beyond update settings.**
A: This module is designed to re-enable the core PrestaShop homepage tabs feature that was removed. Its primary function is to make the tabs appear again, using PrestaShop’s default logic for “Popular,” “New,” “Bestsellers,” and “On Sale” products. Therefore, it doesn’t have extensive configuration options for content management within the tabs themselves, as that logic is handled by PrestaShop’s core.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Homepage tabs” module (`homepagetabs`) is a lightweight PrestaShop module designed to re-enable a core front-office feature that was removed in newer PrestaShop versions. It primarily operates by hooking into `displayHome` to render the product tabs and `displayHeader` to include necessary assets. It leverages PrestaShop’s existing product fetching mechanisms for “Popular,” “New,” “Bestsellers,” and “On Sale” products, effectively acting as a bridge to restore the visual component. The module follows a standard PrestaShop MVC pattern, though its primary logic resides within the main module class (`homepagetabs.php`) for rendering.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. The module’s front-office display logic is entirely handled by the `homepagetabs.php` module file via hooks.
- **Back-Office Admin Controllers**: None. All configuration is handled directly within the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)

- None. The module does not define any custom classes or `ObjectModel` instances. It relies on PrestaShop’s core classes for product data retrieval.

### 4.4 JavaScript Assets (`views/js/`)

- `homepagetabs/views/js/homepagetabs.js`
  - **Scope**: Front-office.
  - **Responsibility**: This script is responsible for the interactive behavior of the homepage tabs. It likely handles:
    - Binding click event listeners to the tab headers.
    - Switching the visibility of product content blocks based on the active tab.
    - Adding/removing active CSS classes to tab headers and content.
    - Potentially handling AJAX requests if product content is loaded dynamically (though for this module, it’s more likely to be a simple show/hide mechanism for pre-rendered content).
    - Ensuring the tabs function correctly across different screen sizes and devices.

### 4.5 CSS Stylesheets (`views/css/`)

- `homepagetabs/views/css/homepagetabs.css`
  - **Scope**: Front-office customer styling.
  - **Responsibility**: This stylesheet provides the default visual presentation for the homepage tabs and their content. It defines styles for:
    - The tab container itself.
    - Individual tab headers (e.g., `ul.home-tabs li a`).
    - The active tab state (e.g., `ul.home-tabs li.active a`).
    - The product grid container for each tab (e.g., `.tab-content`).
    - Basic responsive adjustments for different screen sizes.
  - **Key CSS class selectors developers can override**: Developers can target classes like `.home-tabs`, `.home-tabs li`, `.home-tabs li.active`, `.tab-content`, and the product grid elements within `.tab-content` to integrate the module’s appearance seamlessly with their custom theme.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `homepagetabs/views/templates/hook/homepagetabs.tpl`
    - **Hook**: `displayHome`
    - **Purpose**: This is the primary front-office template responsible for rendering the entire homepage tabs block. It will contain the HTML structure for the tab headers (e.g., `<ul>` for tab titles) and the corresponding content areas (e.g., `<div>` for product lists). It iterates through the product data passed to it by the module’s `hookDisplayHome()` method, displaying “Popular,” “New,” “Bestsellers,” and “On Sale” products in their respective tab content areas. This template is where the product cards (images, names, prices, add-to-cart buttons) are rendered for each product type.
- **Admin templates (`views/templates/admin/`)**:
  - `homepagetabs/views/templates/admin/homepagetabs.tpl`
    - **Purpose**: This template renders the module’s configuration form in the PrestaShop back office. It displays the settings related to update checks (`mypresta_updates`, `update_`, `updatev_`) and any other standard module configuration elements.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: The module does not create any custom database tables. It stores its configuration settings (e.g., `mypresta_updates`) in the standard `ps_configuration` table.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHome` | Renders content on the store’s homepage. | This hook is used to output the entire HTML structure of the homepage tabs, including tab headers and product listings. |
| `displayHeader` | Executed in the `<head>` section of every front-office page. | This hook is used to include the module’s CSS (`homepagetabs.css`) and JavaScript (`homepagetabs.js`) files, ensuring proper styling and interactive functionality of the tabs. |

## 5. Official Support & Updates

For official updates, technical support, and further assistance with the “Homepage tabs” module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to help you with any questions or issues you may encounter.
