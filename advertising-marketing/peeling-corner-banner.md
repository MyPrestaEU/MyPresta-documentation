---
title: "Peeling Corner Banner - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Peeling Corner Banner PrestaShop module by MyPresta.eu."
sidebar:
  label: "Peeling Corner Banner - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Peeling Corner Banner Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/peeling-corner-banner.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/peeling-corner-banner/)
>
> ---


# Peeling Corner Banner

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installing the module, click “Configure” to access its settings. This is where you’ll customize the appearance and behavior of your peeling banner.

#### **Image for the Corner (Small Image)**

- **What this setting does:** This is the small image that appears on the curled-back corner of your page. It’s the initial teaser that catches the customer’s eye.
- **Effect of changing this setting:**
  - *When an image is uploaded:* This image will be displayed on the small, curled corner.
  - *When no image is uploaded:* The corner might appear blank or use a default styling, which is less effective.
- **Recommended value:** Upload a small, attractive image (e.g., a small icon, a “Sale” tag, or a logo snippet) that hints at the promotion without giving everything away.
- **Merchant scenario / example:** You’re running a summer sale. You might upload a small image of a sun icon or a tiny “SALE” badge to this setting.

#### **Image for the Banner (Large Image)**

- **What this setting does:** This is the main banner image that is revealed when a customer hovers over the corner. This is where your primary message, product image, or call to action should be.
- **Effect of changing this setting:**
  - *When an image is uploaded:* This larger image will be displayed when the corner peels back.
  - *When no image is uploaded:* The peeled-back area will be empty, making the module ineffective.
- **Recommended value:** Upload a clear, compelling image that contains your full promotional message, a product photo, or a strong call to action. Ensure it’s sized appropriately for a banner (e.g., 200-300px wide, similar height).
- **Merchant scenario / example:** Following the summer sale example, this image would be a full banner announcing “Summer Sale! Up to 50% Off All Swimwear!” with attractive product photos.

#### **Link for the Banner**

- **What this setting does:** This is the URL (web address) that customers will be directed to when they click on the revealed banner.
- **Effect of changing this setting:**
  - *When a valid URL is entered:* Clicking the banner will take the customer to that page.
  - *When left empty or an invalid URL is entered:* Clicking the banner might do nothing or lead to an error page, frustrating customers.
- **Recommended value:** Always provide a full, valid URL (e.g., `https://yourstore.com/summer-sale-category`).
- **Merchant scenario / example:** You’d link this to your dedicated “Summer Sale” category page or a specific product page you want to highlight.

#### **Position of the Banner**

- **What this setting does:** This controls which corner of your website the peeling banner appears in.
- **Effect of changing this setting:**
  - *Left:* The banner will appear in the top-left corner of the browser window.
  - *Right:* The banner will appear in the top-right corner of the browser window.
- **Recommended value:** Choose the corner that best fits your website’s design and doesn’t obscure important elements. “Right” is often a good default as it’s less common for navigation or logos to be there.
- **Merchant scenario / example:** If your main logo and navigation are on the left, you’d choose “Right” to avoid visual clutter.

#### **Enable/Disable Module**

- **What this setting does:** This is a master switch to turn the entire peeling banner feature on or off without uninstalling the module.
- **Effect of changing this setting:**
  - *Enabled:* The peeling banner will be visible on your front office according to your other settings.
  - *Disabled:* The peeling banner will not appear on your front office.
- **Recommended value:** “Enabled” when you want to use the banner, “Disabled” if you need to temporarily hide it for maintenance or during specific periods.
- **Merchant scenario / example:** You’ve finished your holiday promotion and want to temporarily hide the banner until your next campaign. You would disable it here.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Image for the Corner | Upload small teaser image | Small image on the curled corner. Catches attention. |
| Module Configuration | Image for the Banner | Upload larger promotional image | Main banner image revealed on hover. Contains core message. |
| Module Configuration | Link for the Banner | Full URL (e.g., `https://yourstore.com/promo`) | Destination URL when banner is clicked. Directs traffic. |
| Module Configuration | Position of the Banner | Right | Which corner of the screen the banner appears (Left/Right). |
| Module Configuration | Enable/Disable Module | Enabled | Master switch to show or hide the banner on the store. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My banner isn’t showing up after configuration. What should I do?**
A:

1. **Check “Enable/Disable Module”:** Make sure the module is enabled in its configuration.
2. **Verify Image Uploads:** Ensure both “Image for the Corner” and “Image for the Banner” have been successfully uploaded.
3. **Clear Cache:** Go to **Advanced Parameters > Performance** in your PrestaShop back office and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes, old cached files prevent new module content from appearing.
4. **Module Hook:** The module should automatically hook into `displayHeader`. If it’s not showing, ensure it’s correctly hooked. You can check this under **Design > Positions** (or **Modules > Positions**). Search for `peelingcornerbanner` and confirm it’s associated with `displayHeader`.

**Q: The banner images look blurry or stretched.**
A: This usually means the images you uploaded are not optimized for the banner’s display size.

1. **Image Dimensions:** Check the actual size of the banner when it peels back (you might need to use your browser’s developer tools). Then, resize your “Image for the Banner” to match these dimensions or be slightly larger, ensuring good quality.
2. **File Size:** While quality is important, keep image file sizes as small as possible (under 100-200KB) to ensure fast page loading. Use tools like TinyPNG or online image optimizers.

**Q: The banner appears, but clicking it does nothing.**
A:

1. **Check “Link for the Banner”:** Go back to the module configuration and double-check the URL you entered for the banner link. Ensure it’s a complete and valid URL (e.g., `https://www.yourstore.com/category/product.html`).
2. **Test the Link:** Copy and paste the link directly into your browser to ensure it works correctly outside of the module.

**Q: The banner is overlapping with other elements on my page.**
A:

1. **Change Position:** Try switching the “Position of the Banner” from Left to Right (or vice-versa) in the module configuration.
2. **Theme Conflicts:** If changing the position doesn’t help, it might be a conflict with your specific PrestaShop theme’s CSS. This might require a webmaster to adjust the module’s or theme’s CSS (see Section 7 for developer details).

**Q: Can I have multiple peeling banners?**
A: No, this module is designed to display a single peeling banner at a time. If you need multiple, you would need to duplicate and modify the module, which requires developer expertise.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The Peeling Corner Banner module (`pcb`) is a straightforward PrestaShop module primarily designed to inject a JavaScript-driven visual effect into the front-office. It follows a basic PrestaShop module structure, utilizing the `Module` class for installation, uninstallation, and configuration (`getContent()`). The core functionality relies on a custom JavaScript file (`peelback.js`) that handles the DOM manipulation and animation, and a Smarty template (`header.tpl`) to render the initial HTML structure into the `displayHeader` hook. Configuration settings are stored in `ps_configuration`.

### 4.2 Controllers (`controllers/`)

- No custom Front-Office Controllers.
- No custom Back-Office Admin Controllers.
  The module’s configuration is handled directly within the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)

- No custom classes or `ObjectModel` definitions.
  All configuration is managed via `Configuration::get()` and `Configuration::updateValue()`.

### 4.4 JavaScript Assets (`views/js/`)

- `pcb/peelback.js`
  - **Scope:** Front-office.
  - **Description:** This is the core JavaScript file responsible for the peeling corner animation. It likely initializes a jQuery plugin or custom script that:
    - Detects the presence of the banner HTML structure (e.g., a `div` with a specific ID like `#peelback`).
    - Attaches event listeners, primarily `mouseover` and `mouseout`, to the corner element.
    - On `mouseover`, it animates the larger banner image to “peel back” into view (e.g., by changing CSS properties like `width`, `height`, `top`, `left`, `z-index`).
    - On `mouseout`, it animates the banner back to its initial curled state.
    - Handles the click event on the banner to redirect to the configured URL.
    - It likely uses jQuery’s `animate()` function for smooth transitions.

### 4.5 CSS Stylesheets (`views/css/`)

- No dedicated CSS files are found in the module archive.
  This implies that the styling for the banner (initial position, dimensions, z-index, etc.) is either:
  1. Injected directly via inline styles within the `header.tpl` template.
  2. Handled entirely by the JavaScript, which dynamically sets CSS properties.
  3. Relies on minimal default browser styling or expects the theme to provide basic resets.
     Developers looking to customize the appearance will need to inspect the generated HTML and JavaScript for inline styles or dynamically applied classes/styles.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `pcb/header.tpl`
    - **Hook:** `displayHeader` (or `displayTop` in older versions, but `displayHeader` is the standard for injecting global elements).
    - **Output:** This template renders the initial HTML structure for the peeling banner. It typically includes:
      - A container `div` for the entire banner.
      - An `img` tag for the small corner image.
      - An `img` tag for the larger banner image (initially hidden or partially hidden).
      - An `<a>` tag wrapping these images, linked to the configured URL.
      - It will likely use Smarty variables passed from the module’s `hookDisplayHeader()` method to output the image URLs, link URL, and banner position (left/right).
      - May contain inline `<style>` tags or rely on the `peelback.js` to dynamically apply styles.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create custom SQL tables.
  - Configuration settings are stored in the `ps_configuration` table (or `_configuration` prefix) with keys such as:
    - `PCB_CORNER_IMAGE` (path to the small corner image)
    - `PCB_BANNER_IMAGE` (path to the large banner image)
    - `PCB_BANNER_LINK` (the URL for the banner)
    - `PCB_BANNER_POSITION` (e.g., ‘left’ or ‘right’)
    - `PCB_ENABLED` (1 for enabled, 0 for disabled)
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Executed in the `<head>` section of every page. | Injects the necessary HTML structure for the banner and registers the `peelback.js` script. |
| `actionFrontControllerSetMedia` | Executed when media (JS/CSS) is set for a front controller. | (Implicitly used by `displayHeader` or `hookDisplayHeader` to register JS/CSS, though not explicitly listed as a separate hook in the module’s `install()` method, it’s how PrestaShop handles media registration). |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the Peeling Corner Banner module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to ensuring the smooth operation and continued improvement of our modules.
