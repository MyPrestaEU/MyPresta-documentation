---
title: "Accessories on list of products - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Accessories on list of products PrestaShop module by MyPresta.eu."
sidebar:
  label: "Accessories on list of products - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Accessories on list of products Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/accessories-on-list-of-products.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/accessories-on-list-of-products/)
>
> ---


# Accessories on list of products

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required by PrestaShop itself and are sufficient for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click the “Configure” button next to the “Accessories on list of products” module in the Module Manager. This will take you to the main configuration screen.

| Setting / Option | What this setting does | Effect of changing this setting | Recommended value | Merchant scenario / example |
| --- | --- | --- | --- | --- |
| **Fix classic theme bug** | This setting addresses a specific display issue that can occur with the default PrestaShop Classic theme or themes based on it, where accessories might not render correctly. | *When enabled:* The module applies a fix to ensure accessories display properly on product lists, especially with the Classic theme. *When disabled:* The fix is not applied. If you’re using the Classic theme or a derivative, accessories might not show up correctly or might have layout issues. | **YES** (If you use the Classic theme or a theme based on it) / **NO** (If you use a completely custom theme and don’t experience issues) | If you’ve installed the module and accessories aren’t appearing or look broken on your category pages, enabling this setting is the first step to troubleshoot, especially if you’re on the Classic theme. If your theme is heavily customized and doesn’t show this bug, you might keep it disabled to avoid any potential conflicts, though it’s generally safe to enable. |
| **Enabled / Disabled** | This is the main switch to activate or deactivate the module’s functionality across your entire store. | *When enabled:* The module will actively display accessories on product listing pages as described. *When disabled:* The module’s functionality is completely turned off, and no accessories will appear on product lists. | **Enabled** | You’ve finished setting up your accessories for products and want them to appear on your live store. You would enable this. If you need to temporarily hide accessories for maintenance or a special campaign, you would disable it. |

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Fix classic theme bug | YES (for Classic theme users) | Resolves display issues for accessories on product lists with the Classic theme. |
| Module Configuration Page | Enabled / Disabled | Enabled | Toggles the module’s core functionality on or off. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: Accessories are not showing up on my product list pages.**
A:

1. **Check Module Status**: Ensure the module is “Enabled” in its configuration.
2. **Check Accessory Assignment**: Verify that the main products actually have accessories assigned to them in the PrestaShop product editing page (under the “Accessories” tab).
3. **Theme Compatibility**: If you’re using a custom theme, it might override the standard product list template in a way that prevents the module from hooking correctly. Try enabling the “Fix classic theme bug” setting, even if you’re not on the Classic theme, as it might resolve some general display issues.
4. **Clear Cache**: Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes, PrestaShop’s cache needs to be refreshed to reflect new module changes.

**Q: The accessories look strange or are misaligned on my store.**
A:

1. **“Fix classic theme bug”**: Try enabling this setting in the module configuration. It specifically addresses layout issues.
2. **Theme CSS Conflict**: Your theme’s CSS might be conflicting with the module’s styling. This often requires a webmaster or developer to inspect the CSS and make adjustments.
3. **Clear Cache**: Always clear your PrestaShop cache after making configuration changes.

**Q: Can I control which accessories appear for specific products?**
A: Yes, the module uses PrestaShop’s native accessory assignment feature. To add or remove accessories for a product, go to **Catalog > Products**, edit the desired product, and navigate to the “Accessories” tab. Here you can search for and add/remove associated products.

**Q: Does this module slow down my store?**
A: The module is designed to be efficient. It leverages PrestaShop’s existing accessory data. However, if you have thousands of products each with dozens of accessories, and your server resources are limited, any additional data loading can have a minor impact. For most stores, the performance impact is negligible.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Accessories on list of products” module (`accol`) is a standard PrestaShop module primarily focused on front-office display. It extends `Module` and leverages PrestaShop’s hook system to inject accessory data and rendering into existing product list templates. It does not introduce new database tables or complex custom controllers, making it lightweight and focused on its display purpose. The module’s logic is contained within its main PHP file, with associated JS and CSS for styling and interaction.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. The module injects its content directly into existing product list templates via hooks.
- **Back-Office Admin Controllers**: None. Configuration is handled directly via the `getContent()` method in the main module file.

### 4.3 Core Classes & Models (`classes/`)

- The module does not define any custom classes in the `classes/` directory. All core logic resides within the `accol.php` main module file.
- It interacts with standard PrestaShop `Product` and `Product::getAccessories()` methods to retrieve accessory data.

### 4.4 JavaScript Assets (`views/js/`)

- **`accol/js/accol.js`**
  - **Scope**: Front-office.
  - **Purpose**: This script is responsible for handling the dynamic display and potential interactions with the accessory lists. It might include logic for responsive carousels (if implemented), showing/hiding accessory blocks, or AJAX calls for adding accessories to the cart (though the module’s primary function is display, not direct AJAX add-to-cart). It is likely loaded via `displayHeader` or `header` hook.
  - **Details**: It may bind event listeners to accessory elements, manage their visibility, or initialize any third-party libraries used for carousels or sliders if the module implements such features for accessory display.

### 4.5 CSS Stylesheets (`views/css/`)

- **`accol/css/accol.css`**
  - **Scope**: Front-office customer styling.
  - **Purpose**: This stylesheet provides the necessary visual styling for the accessory lists displayed on product pages.
  - **Main UI components and containers**: It styles the container for accessories, individual accessory items (images, names, prices), and potentially any navigation elements (like arrows for carousels).
  - **Key CSS class selectors**: Developers can expect selectors like `.accol-accessories-list`, `.accol-accessory-item`, `.accol-accessory-image`, `.accol-accessory-name`, etc., which can be overridden in a custom theme’s `custom.css` or `theme.css` to match the theme’s aesthetic.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `accol/accol.tpl`: This is the primary front-office template responsible for rendering the list of accessories for a given product. It is likely hooked into `displayProductListReviews` or a similar hook that allows injecting content into the product list item loop. It receives an array of accessory products and iterates through them to display their images, names, and potentially prices.
- **Admin templates (`views/templates/admin/`)**:
  - `accol/admin.tpl`: This template is used for the module’s configuration page in the PrestaShop Back Office. It contains the HTML form elements for the “Fix classic theme bug” and “Enabled/Disabled” settings, along with any informational messages or save buttons.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: The module does not create any custom database tables. It relies on PrestaShop’s native `ps_product_accessory` table (which links products to their accessories) and `ps_configuration` for its own settings (`ACCOL_FIX`).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Used to load CSS (`accol.css`) and JavaScript (`accol.js`) assets for the front-office display. |
| `displayProductListReviews` | Within the product list item loop, typically below the product’s main information. | The primary hook used to inject the `accol.tpl` template, rendering the accessories for each product in the list. This hook is often available in `product-list.tpl` or similar templates. |
| `header` | (Alias for `displayHeader` in many contexts, especially older PrestaShop versions). | Same purpose as `displayHeader` – loading assets. |
| `actionFrontControllerSetMedia` | Executed when a front controller is setting its media assets. | Can be used to conditionally add CSS/JS based on the current page context, ensuring assets are loaded only when needed. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Accessories on list of products” module, please refer to your customer account at MyPresta.eu. Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
