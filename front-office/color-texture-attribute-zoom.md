---
title: "Color / texture attribute zoom - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Color / texture attribute zoom PrestaShop module by MyPresta.eu."
sidebar:
  label: "Color / texture attribute zoom - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Color / texture attribute zoom Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/color-texture-attribute-zoom.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/color-texture-attribute-zoom/)
>
> ---


# Color / texture attribute zoom

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required by PrestaShop itself and are sufficient for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the “Color / texture attribute zoom” module, accessible after installation by clicking the “Configure” button.

#### **Enable / Disable Module**

- **What this setting does:** This is the master switch to turn the module’s functionality on or off across your entire store.
- **Effect of changing this setting:**
  - *When enabled:* The color/texture zoom feature will be active on your product pages and quick view pop-ups, according to the other settings you’ve chosen.
  - *When disabled:* The zoom feature will be completely deactivated, and no enlarged previews will appear.
- **Recommended value:** **Enabled** (to utilize the module’s features).
- **Merchant scenario / example:** If you want to temporarily disable the zoom feature for maintenance or testing, you can switch this off without uninstalling the module.

#### **Show color / texture name (value)**

- **What this setting does:** Determines whether the text name of the color or texture (e.g., “Red”, “Leather”) appears alongside the zoomed preview window.
- **Effect of changing this setting:**
  - *When enabled:* The name of the attribute will be displayed next to the zoomed image, providing additional context to the customer.
  - *When disabled:* Only the zoomed image will appear, without the text label.
- **Recommended value:** **Enabled**. This provides clearer information to the customer, especially if colors are similar or textures are subtle.
- **Merchant scenario / example:** If you have many shades of blue (e.g., “Sky Blue”, “Navy Blue”), showing the name helps customers differentiate them clearly.

#### **Disable switch attribute on tap**

- **What this setting does:** Controls the behavior of the module on touch devices (like smartphones and tablets) when a customer taps on a color/texture swatch.
- **Effect of changing this setting:**
  - *When enabled:* Tapping a color/texture swatch will only show the zoom preview. The main product image on the page will NOT change to reflect the tapped attribute.
  - *When disabled:* Tapping a color/texture swatch will show the zoom preview AND also update the main product image to show the product in that selected color/texture.
- **Recommended value:** **Disabled**. Most customers expect the main product image to update when they select a color/texture, even on mobile. Enable this only if you have a specific reason not to change the main image on tap.
- **Merchant scenario / example:** If your product images are generic and don’t change based on color attributes, or if you want to prevent accidental main image changes on mobile, you might enable this. Otherwise, keep it disabled for standard behavior.

#### **Color preview window width**

- **What this setting does:** Sets the width (in pixels) of the pop-up window that displays the zoomed color preview.
- **Effect of changing this setting:**
  - *Increasing the value:* Makes the preview window wider, showing more detail.
  - *Decreasing the value:* Makes the preview window narrower.
- **Recommended value:** A value between **200px and 300px** is usually a good balance. Start with `280` and adjust based on your product images and theme design.
- **Merchant scenario / example:** If your color swatches are very small and you want to show a significant enlargement, increase this value. If your product page layout is very narrow, you might need to reduce it.

#### **Color preview window height**

- **What this setting does:** Sets the height (in pixels) of the pop-up window that displays the zoomed color preview.
- **Effect of changing this setting:**
  - *Increasing the value:* Makes the preview window taller, showing more detail.
  - *Decreasing the value:* Makes the preview window shorter.
- **Recommended value:** A value between **200px and 300px** is usually a good balance. Start with `280` and adjust based on your product images and theme design.
- **Merchant scenario / example:** Similar to width, adjust this to ensure the zoomed color is clearly visible without being excessively large or small for your product page.

#### **Activate zoom in combinations table**

- **What this setting does:** Determines if the zoom feature should also apply to color/texture attributes displayed within a product combinations table (if your theme uses one).
- **Effect of changing this setting:**
  - *When enabled:* Customers can hover/tap on color/texture swatches inside a combinations table to see the zoomed preview.
  - *When disabled:* The zoom feature will only work for color/texture attributes outside of any combination tables.
- **Recommended value:** **Enabled**. This provides a consistent and helpful experience across all areas where color/texture attributes are displayed.
- **Merchant scenario / example:** If you sell t-shirts with a table showing sizes and available colors, enabling this allows customers to zoom in on colors directly from that table.

#### **Texture preview window width**

- **What this setting does:** Sets the width (in pixels) of the pop-up window that displays the zoomed texture preview. This is separate from the color preview width, allowing you to optimize for different types of attribute images.
- **Effect of changing this setting:**
  - *Increasing the value:* Makes the texture preview wider.
  - *Decreasing the value:* Makes the texture preview narrower.
- **Recommended value:** Similar to color, a value between **200px and 300px** is often suitable. Start with `280`.
- **Merchant scenario / example:** If your texture images are highly detailed and require a larger view to appreciate, you might set a higher width here than for simple color swatches.

#### **Exclude some color attribute groups from ZOOM**

- **What this setting does:** Allows you to specify certain attribute groups (e.g., “Size”, “Material”) for which the zoom feature should NOT be applied, even if they use color or texture images.
- **Effect of changing this setting:**
  - *When attribute group IDs are entered:* The zoom feature will be disabled for any attributes belonging to the specified groups.
  - *When left empty:* The zoom feature will apply to all color/texture attribute groups.
- **Recommended value:** Leave **empty** unless you have a specific reason to exclude groups. If you need to exclude, enter the numeric IDs of the attribute groups, separated by commas (e.g., `1, 5, 12`). You can find attribute group IDs in your PrestaShop Back Office under **Catalog > Attributes & Features > Attribute Groups**.
- **Merchant scenario / example:** You might have an “Availability” attribute group that uses color swatches (e.g., green for in stock, red for out of stock), but you don’t want these to trigger a zoom. In this case, you would find the ID of the “Availability” attribute group and enter it here.

#### **Animation type**

- **What this setting does:** Selects the visual effect used when the zoom preview window appears.
- **Effect of changing this setting:** Changes the way the preview window animates into view (e.g., fading in, sliding).
- **Recommended value:** **Fade**. This is generally the most subtle and professional-looking animation. Experiment with others if you prefer a different effect.
- **Merchant scenario / example:** You can choose an animation that best fits your store’s overall design aesthetic.

#### **Update animation type**

- **What this setting does:** Selects the visual effect used when the content of the zoom preview window changes (e.g., when switching between different colors/textures while the preview is already open).
- **Effect of changing this setting:** Changes the animation for content updates within the preview.
- **Recommended value:** **Fade**. Similar to the initial animation, a fade is usually smooth and non-distracting.
- **Merchant scenario / example:** If a customer quickly hovers over multiple color swatches, this animation dictates how smoothly the preview content transitions.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable / Disable Module | Enabled | Master switch for module functionality. |
| Module Configuration | Show color / texture name (value) | Enabled | Displays attribute name with zoom preview. |
| Module Configuration | Disable switch attribute on tap | Disabled | Prevents main image change on mobile tap (if enabled). |
| Module Configuration | Color preview window width | 280 | Width of the color zoom pop-up in pixels. |
| Module Configuration | Color preview window height | 280 | Height of the color zoom pop-up in pixels. |
| Module Configuration | Activate zoom in combinations table | Enabled | Extends zoom to attributes within combination tables. |
| Module Configuration | Texture preview window width | 280 | Width of the texture zoom pop-up in pixels. |
| Module Configuration | Exclude some color attribute groups from ZOOM | Empty | Comma-separated IDs of attribute groups to ignore for zoom. |
| Module Configuration | Animation type | Fade | Animation for the zoom preview appearance. |
| Module Configuration | Update animation type | Fade | Animation for content changes within the zoom preview. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: The zoom isn’t appearing on my product page. What should I check?**
A:

1. **Module Enabled:** Go to **Modules > Module Manager** and ensure “Color / texture attribute zoom” is enabled.
2. **Attribute Setup:** Verify that your product attributes are correctly set up as “Color” or “Texture” type in **Catalog > Attributes & Features > Attributes**. Make sure you have uploaded actual images for these attributes, not just color codes.
3. **Cache:** Clear your PrestaShop cache. Go to **Advanced Parameters > Performance**, scroll down to “Clear cache” and click “Clear cache”. Also, clear your browser’s cache.
4. **Theme Compatibility:** While the module is designed for broad compatibility, very heavily customized themes might sometimes interfere. If the above steps don’t work, temporarily switch to the default PrestaShop theme to see if the zoom appears. If it does, your theme might require a small adjustment.

**Q: The zoom preview window is too small/large.**
A: Adjust the “Color preview window width”, “Color preview window height”, and “Texture preview window width” settings in the module’s configuration page. Increase the values to make the window larger, decrease them to make it smaller. Remember to save changes and clear cache.

**Q: The color/texture name isn’t showing up with the zoom.**
A: Check the “Show color / texture name (value)” setting in the module configuration. Ensure it is set to “Enabled”.

**Q: On mobile, when I tap a color, the main product image doesn’t change, but I want it to.**
A: Go to the module configuration and ensure “Disable switch attribute on tap” is set to “Disabled”. This will allow the main product image to update when a color/texture is tapped.

**Q: I want to exclude a specific attribute group from having the zoom feature.**
A: Navigate to **Catalog > Attributes & Features > Attribute Groups** in your PrestaShop Back Office. Find the attribute group you wish to exclude and note its ID (usually visible in the URL when you edit it, or in the table itself). Then, go to the module configuration, find “Exclude some color attribute groups from ZOOM”, and enter the ID(s) separated by commas (e.g., `1,5,12`).

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Color / texture attribute zoom” module (`colorzoom`) is a front-office feature module designed to enhance product attribute visualization. It primarily leverages PrestaShop’s hook system to inject its JavaScript and CSS assets into the front-office header and to render its specific zoom template on product pages. It uses the `tooltipster` library for the actual zoom/tooltip functionality, dynamically attaching it to color and texture attribute elements. Configuration is managed via the standard `getContent()` method in the main module file, storing settings in `ps_configuration`.

### 4.2 Controllers (`controllers/`)

The module includes two front-office controllers, though their primary function in this module is often minimal or for specific AJAX needs, with much of the logic handled client-side via JavaScript.

- **Front-Office Controllers**:

  - `controllers/front/index.php`
    - Class name: `ColorzoomIndexModuleFrontController` (extends `ModuleFrontController`)
    - Responsibility: This controller likely serves as a fallback or a generic entry point. Given the module’s primary function is UI enhancement via JS/CSS, this controller might not have extensive logic or might be used for simple data retrieval if needed by the front-end.
  - `controllers/front/loader.php`
    - Class name: `ColorzoomLoaderModuleFrontController` (extends `ModuleFrontController`)
    - Responsibility: This controller could be used for loading specific resources or data dynamically, potentially for AJAX requests related to the zoom functionality, though the core zoom logic is client-side.
- **Back-Office Admin Controllers**: None. All configuration is handled via the main module’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

The module does not define any custom `ObjectModel` classes or dedicated business logic classes in the `classes/` directory. Its core functionality is implemented within the main `colorzoom.php` file and through its JavaScript assets.

### 4.4 JavaScript Assets (`views/js/`)

The module relies heavily on JavaScript for its interactive zoom functionality, particularly the `tooltipster` library.

- `colorzoom/lib/tooltipster/dist/js/plugins/tooltipster/SVG/tooltipster-SVG.js`
  - Scope: Front-office.
  - Details: A plugin for the `tooltipster` library, specifically for handling SVG elements within tooltips. This might be used if attribute images are SVG-based or if the module needs to interact with SVG elements on the page.
- `colorzoom/lib/tooltipster/dist/js/tooltipster.bundle.js`
  - Scope: Front-office.
  - Details: The full bundled version of the `tooltipster` library, providing the core functionality for creating flexible and customizable tooltips. This is the primary library responsible for the zoom pop-ups.
- `colorzoom/lib/tooltipster/dist/js/tooltipster.core.js`
  - Scope: Front-office.
  - Details: The core JavaScript file for the `tooltipster` library. It’s possible that `tooltipster.bundle.js` already includes this, but it’s listed separately, indicating a modular inclusion.
- `colorzoom/views/js/colorzoom-combinationstable.js`
  - Scope: Front-office.
  - Details: This script specifically targets product combination tables. It likely contains logic to identify color/texture attributes within these tables and initialize the `tooltipster` zoom functionality on them, respecting the `cz_ctab` configuration setting. It binds event listeners to elements within these tables.
- `colorzoom/views/js/colorzoom.js`
  - Scope: Front-office.
  - Details: This is the main custom JavaScript for the module. It’s responsible for:
    - Identifying color/texture attribute elements on the product page (outside of combination tables).
    - Initializing `tooltipster` on these elements with module-specific configurations (width, height, animation type, showing name).
    - Handling the “Disable switch attribute on tap” logic for mobile devices.
    - Potentially listening for `prestashop.on` events like `updateProduct` to re-initialize tooltips if product content changes via AJAX.

### 4.5 CSS Stylesheets (`views/css/`)

The module includes CSS for styling the zoom previews and the `tooltipster` library.

- `colorzoom/lib/tooltipster/dist/css/tooltipster.bundle.css`
  - Scope: Front-office customer styling.
  - Details: The bundled CSS for the `tooltipster` library, providing default styling for the tooltips (the zoom preview windows).
- `colorzoom/lib/tooltipster/dist/css/tooltipster.core.css`
  - Scope: Front-office customer styling.
  - Details: The core CSS for `tooltipster`, defining fundamental styles.
- `colorzoom/views/css/colorszoom.css`
  - Scope: Front-office customer styling.
  - Details: Custom CSS specific to the “Color / texture attribute zoom” module. This file likely contains overrides or additional styles to integrate the `tooltipster` tooltips seamlessly into PrestaShop’s product page, ensuring correct positioning, font sizes for attribute names, and responsiveness. Developers can inspect this file for key selectors to override in their theme’s custom CSS.

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses Smarty templates to inject its JavaScript and CSS, and to render the content of the zoom preview.

- **Hook templates (`views/templates/hook/`)**:
  - `colorzoom/views/header.tpl`
    - Hook: `displayHeader`
    - Purpose: This template is responsible for including the module’s CSS and JavaScript files into the `<head>` section of the front-office pages. It also passes configuration variables from the back office (like `cz_width`, `cz_height`, `cz_animation`, `cz_name`, `cz_disableclick`, `cz_ctab`, `cz_exclusions`) to the front-end JavaScript, making them accessible for dynamic initialization.
- **Front-office templates (`views/templates/front/`)**:
  - `colorzoom/views/quickview.tpl`
    - Purpose: This template is likely designed to be rendered within a product quick view pop-up. It contains the necessary markup or logic to ensure the zoom functionality is correctly initialized for attributes displayed in quick view modals.
  - `colorzoom/views/zoom.tpl`
    - Purpose: This is the core template for the content displayed inside the zoom preview (tooltip). It dynamically receives the attribute image URL and the attribute name, rendering them within the tooltip structure. It’s the visual component that the `tooltipster` library will display.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  The module does not create any custom SQL tables. All its configuration settings are stored in the `ps_configuration` table using keys prefixed with `cz_` (e.g., `cz_width`, `cz_height`, `cz_animation`, `cz_name`, `cz_disableclick`, `cz_exclusions`, `cz_ctab`) and `mypresta_updates`, `update_`, `updatev_` for update management.
- **Registered Hooks Table**:

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `displayHeader` | In the `<head>` section of every front-office page. | Injects the module’s CSS and JavaScript files, and passes configuration variables to the front-end. |
  | `displayProductAdditionalInfo` | Within the product information block on the product page. | This hook is used to render the necessary JavaScript initialization or specific markup for the zoom feature on the product page, ensuring it’s active for color/texture attributes. |

## 5. Official Support & Updates

For official support, module updates, and any further assistance, please refer to your customer account at MyPresta.eu. Our team is dedicated to providing timely support and ensuring your module functions optimally.
