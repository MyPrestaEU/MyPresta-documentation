---
title: "Before & after - pictures diff tool - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Before & after - pictures diff tool PrestaShop module by MyPresta.eu."
sidebar:
  label: "Before & after - pictures diff tool - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Before & after - pictures diff tool Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/before-after-pictures-diff-tool.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/before-after-pictures-diff-tool/)
>
> ---


# Before & after - pictures diff tool

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Before & after - pictures diff tool” module to access its main settings.

#### General Settings

- **What this setting does:** This section controls the overall activation and operational mode of the module.
- **Effect of changing this setting:**
  - *Enabled:* The module will be active across your store. The “Before & After” image comparison tool will be available on product pages where you have configured images.
  - *Disabled:* The module will be inactive. The “Before & After” image comparison tool will not appear on any product pages, even if you have configured images for them.
  - *Test mode:* This option is typically used for development or staging environments. When enabled, the module might display additional debugging information or operate under specific conditions that are not suitable for a live production store. It’s generally not recommended for live stores unless explicitly instructed by support.
- **Recommended value:** “Enabled” for a live store. “Disabled” if you want to temporarily hide the feature without uninstalling the module.
- **Merchant scenario / example:** If you’re launching a new product line that heavily relies on visual transformations (e.g., custom-painted shoes), you’d set this to “Enabled” to showcase the work. If you’re performing maintenance or don’t want the feature active for a period, you’d set it to “Disabled”.

#### Language Settings (Implicit)

While not explicitly listed as a setting, the module will respect your PrestaShop’s default language settings for the Back Office.

- **`PS_LANG_DEFAULT`**: This PrestaShop core setting determines the default language for your store.
- **`PS_BO_ALLOW_EMPLOYEE_FORM_LANG`**: This PrestaShop core setting allows employees to choose their preferred language for forms.
- **Effect of changing this setting:** These core PrestaShop settings ensure that any text or labels provided by the module in the Back Office (e.g., on the product editing page for adding before/after images) are displayed in the correct language for the administrator.
- **Recommended value:** Ensure your `PS_LANG_DEFAULT` is set to your primary store language. If you have a multi-lingual team, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` should be enabled.

#### Update Settings (Implicit)

The module also includes internal settings related to updates from MyPresta.eu. These are usually managed automatically.

- **`mypresta_updates`, `update_`, `updatev_`**: These are internal configuration keys used by MyPresta.eu modules to check for and manage updates. You generally do not need to interact with these.
- **Effect of changing this setting:** Modifying these directly could interfere with the module’s ability to receive important updates and bug fixes.
- **Recommended value:** Leave these untouched.

### 2.2 Dedicated Admin Screens & Controller Views

#### Product Editing Page (Back Office > Catalog > Products > Edit Product)

This module integrates directly into the standard PrestaShop product editing interface.

- **Screen Name & Menu Location:** To access this, navigate to **Catalog > Products**, then click “Edit” on any product.
- **Available Actions & Settings:** Within the product editing page, you will find a new section or tab specifically for “Before & after - pictures diff tool”. Here, you will be able to:
  - **Upload “Before” Image:** Select and upload the initial state image for your product.
  - **Upload “After” Image:** Select and upload the final state image for your product.
  - **Save:** After uploading, remember to save the product to apply the changes.
- **Effect of changes:**
  - *Adding images:* Once you upload both a “Before” and an “After” image for a specific product and save, the interactive comparison slider will automatically appear on that product’s front-office page.
  - *Removing images:* If you remove one or both images, the comparison slider will no longer be displayed for that product.
  - *Updating images:* Replacing images will update the slider on the front office.
- **Recommended workflow for daily store management:**
  1. When adding a new product that benefits from a before/after comparison, first create the product as usual.
  2. Navigate to its editing page.
  3. Locate the “Before & after” section.
  4. Upload your “before” and “after” images. Ensure they are of similar dimensions for the best visual effect.
  5. Save the product.
  6. Check the product page on the front office to confirm the slider is working as expected.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Module Status | Enabled | Activates/deactivates the entire module functionality. |
| Product Editing Page | Upload “Before” Image | N/A | Defines the initial state image for the comparison. |
| Product Editing Page | Upload “After” Image | N/A | Defines the final state image for the comparison. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The “Before & After” slider isn’t showing on my product page.**
A1:

- **Check Module Status:** Go to **Modules > Module Manager** and ensure “Before & after - pictures diff tool” is “Enabled”.
- **Check Product Images:** Edit the specific product (**Catalog > Products > Edit**) and verify that both a “Before” and an “After” image have been uploaded and saved in the module’s section.
- **Clear Cache:** Sometimes, PrestaShop’s cache can prevent new content from appearing. Go to **Advanced Parameters > Performance** and click “Clear cache”.
- **Theme Compatibility:** While the module is designed to be compatible, some highly customized themes might require minor CSS adjustments. If the above steps don’t work, contact MyPresta.eu support.

**Q2: The images look distorted or misaligned in the slider.**
A2:

- **Image Dimensions:** For the best results, ensure your “Before” and “After” images have the exact same dimensions (width and height). If they differ significantly, the slider might struggle to align them perfectly.
- **Image Quality:** Use high-quality images. Low-resolution images might appear pixelated when scaled.

**Q3: Can I use this module for products with multiple variations (combinations)?**
A3: The module currently allows you to set one “Before” and one “After” image per product, not per combination. If your variations have different before/after states, you might need to create separate products or use the main product images for the comparison.

**Q4: How do I translate the module’s text (if any) into other languages?**
A4: Any text labels introduced by the module in the Back Office (e.g., “Upload Before Image”) can typically be translated through PrestaShop’s built-in translation system. Go to **International > Translations**, select “Installed modules translations”, choose your theme, and then find the “Before & after - pictures diff tool” module to edit its translations.

**Q5: The slider works, but it doesn’t look quite right with my theme’s design.**
A5: This often comes down to CSS styling. Your theme might have conflicting styles. You can try to inspect the element using your browser’s developer tools to identify the conflicting CSS. For more advanced customization, you might need a web developer or contact MyPresta.eu support for guidance on overriding the module’s default styles.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Before & after - pictures diff tool” module is a standard PrestaShop module following an MVC-like pattern. It primarily extends the `Module` class, integrates with the product administration page via hooks, and injects its front-office assets and templates into the product page footer. It leverages external jQuery plugins (`jquery.event.move.js`, `jquery.twentytwenty.js`) for the interactive slider functionality.

### 4.2 Controllers (`controllers/`)

This module does not use dedicated front-office or back-office controllers. All logic is handled within the main module class and via hooks.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or `ObjectModel`s. It stores its configuration directly in `ps_configuration` and product-specific image paths as product attributes or configuration values, managed through the `displayAdminProductsExtra` hook.

### 4.4 JavaScript Assets (`views/js/`)

The module includes several JavaScript files, primarily for the “TwentyTwenty” image comparison slider. These are loaded in the front office.

- **`beforeafter/js/jquery.event.move.js`**
  - **Scope:** Front-office.
  - **Purpose:** A lightweight jQuery plugin that provides touch and mouse event handling for dragging elements. It’s a dependency for `jquery.twentytwenty.js`.
  - **Details:** Binds events like `move`, `movestart`, `moveend` to enable drag functionality.
- **`beforeafter/js/jquery.twentytwenty.js`**
  - **Scope:** Front-office.
  - **Purpose:** The core jQuery plugin that implements the “TwentyTwenty” image comparison slider.
  - **Details:** Initializes the slider on specified elements, handles the visual rendering of the before/after images, and manages the interactive divider based on `jquery.event.move.js`. It typically targets a container with two `img` tags inside.
- **`beforeafter/js/twentytwenty.js`**
  - **Scope:** Front-office.
  - **Purpose:** This file likely contains the module’s specific initialization logic for the `jquery.twentytwenty.js` plugin, applying it to the correct elements on the product page.
  - **Details:** It will contain jQuery selectors to identify the `div` element wrapping the before/after images and call the `.twentytwenty()` method on it, potentially with configuration options.

### 4.5 CSS Stylesheets (`views/css/`)

The module includes CSS files to style the image comparison slider and its components.

- **`beforeafter/css/foundation.css`**
  - **Scope:** Front-office.
  - **Purpose:** This file likely contains basic reset or foundational styles, possibly a subset of the Zurb Foundation framework, to ensure consistent rendering of the slider elements. It might define basic grid, typography, or form styles that the module uses.
  - **Key Selectors:** May include general `div`, `img`, `button` styles, or specific classes like `.row`, `.column`.
- **`beforeafter/css/twentytwenty.css`**
  - **Scope:** Front-office.
  - **Purpose:** Contains the specific styling required for the “TwentyTwenty” image comparison slider itself.
  - **Key Selectors:** Will define the appearance of the slider container, the divider handle, the overlay, and the positioning of the “before” and “after” images. Examples: `.twentytwenty-container`, `.twentytwenty-overlay`, `.twentytwenty-handle`, `.twentytwenty-before`, `.twentytwenty-after`. Developers can override these classes in their theme’s `custom.css` or `theme.css` to match their store’s design.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `beforeafter/views/templates/front/hook/displayFooter.tpl`
    - **Hook:** `displayFooter` (or potentially `displayFooterProduct` depending on internal logic).
    - **Purpose:** This template is responsible for rendering the actual HTML structure for the “Before & After” image comparison slider on the front office. It will contain the `div` elements that the JavaScript will target to initialize the `twentytwenty` plugin, including the `img` tags for the “before” and “after” images. It also likely includes the necessary JavaScript and CSS asset loading.
  - `beforeafter/views/templates/front/hook/displayFooterCms.tpl`
    - **Hook:** Likely `displayFooter` or `displayFooterProduct` but potentially with conditional logic for CMS pages.
    - **Purpose:** This template might be a fallback or an alternative for rendering the slider on CMS pages, although the module description focuses on product pages. Its content would be similar to `displayFooter.tpl`.
- **Admin templates (`views/templates/admin/`)**:
  - `beforeafter/views/templates/admin/displayAdminProductsExtra.tpl`
    - **Hook:** `displayAdminProductsExtra`
    - **Purpose:** This template renders the custom input fields and upload forms within the PrestaShop product editing page in the Back Office. It provides the interface for administrators to upload and manage the “Before” and “After” images for each product. It will contain form elements (e.g., `input type="file"`) and potentially display thumbnails of already uploaded images.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create custom SQL tables.
  - It stores its configuration settings (like `BA_TEST`) in the `ps_configuration` table.
  - Product-specific “before” and “after” image paths are likely stored as product-specific configuration values or attributes, managed through the `displayAdminProductsExtra` hook and the module’s `install()` and `uninstall()` methods.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionProductUpdate` | After a product is updated in the Back Office. | Used to save the paths of the “before” and “after” images uploaded via the product editing page. |
| `displayFooterProduct` | Renders content in the footer section of the product page. | Used to display the “Before & After” image comparison slider on the front-office product page. |
| `displayAdminProductsExtra` | Renders additional content on the product editing page in the Back Office. | Used to inject the custom form fields for uploading “before” and “after” images into the product administration interface. |
| `actionAdminControllerSetMedia` | Before an admin controller renders its view, allowing modules to add JS/CSS. | Used to load the necessary JavaScript (`jquery.event.move.js`, `jquery.twentytwenty.js`, `twentytwenty.js`) and CSS (`foundation.css`, `twentytwenty.css`) files for the module in the Back Office (if needed for the admin product page) and potentially the front office. |
| `displayHeader` | Renders content in the `<head>` section of the front-office pages. | Used to load the necessary JavaScript and CSS files for the “Before & After” slider on the front office, ensuring they are available before the `displayFooterProduct` hook renders the slider’s HTML. |

## 5. Official Support & Updates

For official support, updates, and any further assistance with the “Before & after - pictures diff tool” module, please refer to your MyPresta.eu customer account. You can find the latest module versions, documentation, and contact our support team directly through the MyPresta.eu website.
