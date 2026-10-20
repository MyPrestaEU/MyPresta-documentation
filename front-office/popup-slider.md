---
title: "Popup Slider - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Popup Slider PrestaShop module by MyPresta.eu."
sidebar:
  label: "Popup Slider - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Popup Slider Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/popup-slider.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/popup-slider/)
>
> ---


# Popup Slider

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.4.x, 1.5.x, 1.6.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the Popup Slider module, where you’ll define how your popup looks and behaves.

#### General Settings

- **Popup Width (px):**

  - **What this setting does:** Defines the width of the popup window in pixels.
  - **Effect of changing this setting:**
    - *When set to a specific value (e.g., 800):* The popup will appear exactly 800 pixels wide on desktop screens.
    - *When set to a different value:* The popup will resize accordingly.
  - **Recommended value:** 800px (or adjust based on your image sizes and design).
  - **Merchant scenario / example:** If your slider images are 800px wide, setting this to 800px ensures they fit perfectly without scaling issues.
- **Popup Height (px):**

  - **What this setting does:** Defines the height of the popup window in pixels.
  - **Effect of changing this setting:**
    - *When set to a specific value (e.g., 500):* The popup will appear exactly 500 pixels tall.
    - *When set to a different value:* The popup will resize accordingly.
  - **Recommended value:** 500px (or adjust based on your image sizes and design).
  - **Merchant scenario / example:** If your slider images are 500px tall, setting this to 500px ensures they fit perfectly.
- **Popup Background Color:**

  - **What this setting does:** Sets the background color of the popup window itself (the area behind your slider images). You can use a color picker to select.
  - **Effect of changing this setting:**
    - *When set to a specific color (e.g., #FFFFFF for white):* The popup’s background will display that color.
    - *When set to a different color:* The background color changes.
  - **Recommended value:** #FFFFFF (white) or a color that complements your store’s design.
  - **Merchant scenario / example:** If your store has a dark theme, you might choose a light grey (#F5F5F5) for the popup background to make the content stand out.
- **Popup Border Color:**

  - **What this setting does:** Sets the color of the border around the popup window.
  - **Effect of changing this setting:**
    - *When set to a specific color (e.g., #CCCCCC for light grey):* The popup will have a border of that color.
    - *When set to a different color:* The border color changes.
  - **Recommended value:** #CCCCCC (light grey) or a color that matches your brand.
  - **Merchant scenario / example:** A subtle border can help define the popup against a busy background.
- **Popup Border Width (px):**

  - **What this setting does:** Defines the thickness of the popup border in pixels.
  - **Effect of changing this setting:**
    - *When set to 1:* The border will be 1 pixel thick.
    - *When set to 0:* No border will be visible.
  - **Recommended value:** 1px or 0px.
  - **Merchant scenario / example:** A 0px border can create a more seamless, modern look if your design doesn’t require a visible border.
- **Popup Border Radius (px):**

  - **What this setting does:** Controls the roundness of the popup’s corners. A higher value means rounder corners.
  - **Effect of changing this setting:**
    - *When set to 0:* The popup will have sharp, square corners.
    - *When set to 10:* The corners will be slightly rounded.
  - **Recommended value:** 5px or 0px.
  - **Merchant scenario / example:** Rounded corners can give your popup a softer, more modern aesthetic.
- **Popup Shadow:**

  - **What this setting does:** Adds a shadow effect around the popup, making it appear to float above the page.
  - **Effect of changing this setting:**
    - *When enabled (YES):* A subtle shadow will appear around the popup.
    - *When disabled (NO):* The popup will have no shadow.
  - **Recommended value:** YES.
  - **Merchant scenario / example:** A shadow helps the popup stand out from the background content, improving visibility and perceived depth.
- **Popup Overlay Color:**

  - **What this setting does:** Sets the color of the semi-transparent overlay that covers the rest of your store content when the popup is active.
  - **Effect of changing this setting:**
    - *When set to a specific color (e.g., #000000 for black):* The overlay will be that color.
  - **Recommended value:** #000000 (black).
  - **Merchant scenario / example:** A dark overlay helps focus the visitor’s attention solely on the popup content.
- **Popup Overlay Opacity (0-1):**

  - **What this setting does:** Controls the transparency of the overlay. 0 is fully transparent, 1 is fully opaque.
  - **Effect of changing this setting:**
    - *When set to 0.5:* The overlay will be 50% transparent, allowing some of the background store content to be seen.
    - *When set to 0.8:* The overlay will be 80% opaque, making the background content very dim.
  - **Recommended value:** 0.7 or 0.8.
  - **Merchant scenario / example:** A higher opacity ensures the popup is the primary focus, while a lower opacity might be used if you want to subtly hint at the content behind the popup.
- **Popup Re-display Time (hours):**

  - **What this setting does:** Determines how many hours must pass before the popup is shown again to the same visitor after they have closed it.
  - **Effect of changing this setting:**
    - *When set to 0:* The popup will appear every time the visitor loads a page (not recommended for user experience).
    - *When set to 24:* The popup will reappear after 24 hours.
    - *When set to a very high number (e.g., 8760 for 1 year):* The popup will effectively only show once per visitor.
  - **Recommended value:** 24 (for daily promotions) or 168 (for weekly promotions) or a very high number like 8760 (for once-per-year or effectively once-ever).
  - **Merchant scenario / example:** If you run daily deals, setting this to 24 hours ensures visitors see the new deal each day. If you only want to show a welcome message once, set it to a very high number.
- **Show Close Button:**

  - **What this setting does:** Toggles the visibility of the ‘X’ close button on the popup.
  - **Effect of changing this setting:**
    - *When enabled (YES):* A close button will be visible, allowing visitors to easily dismiss the popup.
    - *When disabled (NO):* No close button will be shown. Visitors will have to click outside the popup or navigate away to close it.
  - **Recommended value:** YES.
  - **Merchant scenario / example:** Always provide a clear way for users to close the popup to avoid frustration and improve user experience.
- **Close on Overlay Click:**

  - **What this setting does:** Determines if clicking on the semi-transparent overlay (outside the popup content) will close the popup.
  - **Effect of changing this setting:**
    - *When enabled (YES):* Clicking the overlay will close the popup.
    - *When disabled (NO):* Only the close button (if enabled) or navigating away will close the popup.
  - **Recommended value:** YES.
  - **Merchant scenario / example:** This provides an intuitive and common way for users to dismiss popups, enhancing usability.

#### Slider Images Configuration

This section allows you to add, edit, and manage the images that will appear in your popup slider. You can add an unlimited number of images.

For each image slot, you will typically find:

- **Image Upload Field:**

  - **What this setting does:** Allows you to upload an image file from your computer to be displayed in the slider.
  - **Effect of changing this setting:**
    - *When an image is uploaded:* It replaces any existing image in that slot or adds a new one to the slider.
  - **Recommended value:** Use high-quality, optimized images that match the aspect ratio of your popup width/height.
  - **Merchant scenario / example:** Upload your latest product photo, a banner for a sale, or a graphic promoting a new feature.
- **Image Link (URL):**

  - **What this setting does:** Specifies the URL that visitors will be redirected to when they click on this specific slider image.
  - **Effect of changing this setting:**
    - *When a URL is entered:* Clicking the image will take the visitor to that page.
    - *When left empty:* The image will not be clickable.
  - **Recommended value:** Always link to relevant pages (product, category, blog post, contact page).
  - **Merchant scenario / example:** Link a “New Arrivals” banner to your new products category page, or a “Summer Sale” banner to your sale landing page.
- **Image Title/Alt Text:**

  - **What this setting does:** Provides a text description for the image. This text is important for SEO (search engines) and accessibility (screen readers for visually impaired users).
  - **Effect of changing this setting:**
    - *When text is entered:* This text will be used by search engines to understand the image content and by screen readers to describe the image.
  - **Recommended value:** A concise, descriptive phrase that accurately describes the image content and includes relevant keywords.
  - **Merchant scenario / example:** For an image of a new dress, use “New Summer Collection Dress - Shop Now”.
- **Delete Image Button:**

  - **What this setting does:** Removes the selected image from the slider.
  - **Effect of changing this setting:**
    - *When clicked:* The image and its associated settings are removed from the slider configuration.
  - **Recommended value:** Use this to remove outdated promotions or images.
  - **Merchant scenario / example:** After a sale ends, delete the banner image promoting that sale.
- **Add New Image Button:**

  - **What this setting does:** Adds a new empty slot for you to upload another image to the slider.
  - **Effect of changing this setting:**
    - *When clicked:* A new set of image upload, link, and title fields appears.
  - **Recommended value:** Use this to expand your slider content.
  - **Merchant scenario / example:** Add a new slide for an upcoming holiday promotion.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Popup Width (px) | 800 | Sets the width of the popup window. |
| Module Configuration | Popup Height (px) | 500 | Sets the height of the popup window. |
| Module Configuration | Popup Background Color | #FFFFFF | Background color of the popup content area. |
| Module Configuration | Popup Border Color | #CCCCCC | Color of the border around the popup. |
| Module Configuration | Popup Border Width (px) | 1 | Thickness of the popup border. |
| Module Configuration | Popup Border Radius (px) | 5 | Roundness of the popup corners. |
| Module Configuration | Popup Shadow | YES | Adds a shadow effect for depth. |
| Module Configuration | Popup Overlay Color | #000000 | Color of the semi-transparent background overlay. |
| Module Configuration | Popup Overlay Opacity (0-1) | 0.7 | Transparency level of the overlay. |
| Module Configuration | Popup Re-display Time (hours) | 24 | How long before the popup shows again to a visitor. |
| Module Configuration | Show Close Button | YES | Displays an ‘X’ button to close the popup. |
| Module Configuration | Close on Overlay Click | YES | Allows closing the popup by clicking outside it. |
| Module Configuration | Image Upload Field | N/A | Uploads an image for a slide. |
| Module Configuration | Image Link (URL) | N/A | URL to navigate to when clicking the slide image. |
| Module Configuration | Image Title/Alt Text | N/A | Descriptive text for SEO and accessibility. |
| Module Configuration | Delete Image Button | N/A | Removes a slide from the slider. |
| Module Configuration | Add New Image Button | N/A | Adds a new empty slide slot. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My popup isn’t showing up at all. What should I check?**
A1:

- **Module Enabled:** First, ensure the module is enabled in **Modules > Module Manager**.
- **Configuration Saved:** Make sure you’ve saved your configuration settings after making changes.
- **Images Added:** Have you uploaded at least one image to the slider configuration? The slider won’t appear if there are no images.
- **Cache:** Clear your PrestaShop cache (**Advanced Parameters > Performance > Clear Cache**) and your browser cache. Sometimes old cached files prevent new module content from loading.
- **Re-display Time:** If you’ve visited your site before, the “Popup Re-display Time” might be preventing it from showing again. Try opening your store in an incognito/private browser window to simulate a first-time visitor.

**Q2: My popup looks strange or is not centered correctly on my custom theme.**
A2:

- **Theme Conflicts:** Custom themes sometimes have conflicting CSS styles.
- **Width/Height Settings:** Double-check your “Popup Width” and “Popup Height” settings in the module configuration. Ensure they are appropriate for your images and screen sizes.
- **Developer Assistance:** If the issue persists, it might require a small CSS adjustment by a web developer familiar with your theme. They can inspect the elements and apply custom styles to resolve conflicts.

**Q3: The images in my slider are blurry or distorted.**
A3:

- **Image Quality:** Ensure the images you are uploading are high-resolution and not pixelated.
- **Aspect Ratio:** The images should ideally match the aspect ratio (width to height ratio) you’ve set for your “Popup Width” and “Popup Height”. If your images have a different ratio, they might be stretched or squeezed to fit.
- **Image Optimization:** While high-res is good, excessively large file sizes can slow down your site. Optimize your images for web use (e.g., compress them) before uploading.

**Q4: Can I have different popups for different pages or customer groups?**
A4: The Popup Slider module, in its current version, displays a single, global popup to all visitors based on the re-display logic. It does not natively support different popups for specific pages or customer groups. For such advanced functionality, you would typically need a more complex module or custom development.

**Q5: How do I translate the module’s text (e.g., the close button text, if any)?**
A5: While this module primarily uses images, any default text elements would be translatable through PrestaShop’s translation system:

- Navigate to **International > Translations**.
- Select “Installed modules translations”.
- Choose your theme, your language, and then find “Popup Slider” in the module list.
- You can then edit any translatable strings.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a technical deep dive into the Popup Slider module’s architecture, intended for developers and webmasters.

### 4.1 Architecture Overview

The Popup Slider module (`popupslider/cz.php`) is a classic PrestaShop 1.4-1.6 module, primarily leveraging the `Module` class for its core functionality. It integrates into the front-office via a hook (typically `displayHeader` or `displayFooter` implicitly, though the documentation mentions `Header, Columns, Product, or Footer` as potential display areas, the provided template `header.tpl` suggests `displayHeader` is the primary integration point). Configuration is managed through the `getContent()` method, storing settings in `ps_configuration`. Front-office interaction is handled by injecting JavaScript and CSS, which then renders the slider using the bxSlider library.

### 4.2 Controllers (`controllers/`)

This module does not contain any custom Front-Office or Back-Office Admin Controllers. All configuration is handled within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or `ObjectModel` instances. All configuration data is stored directly in the `ps_configuration` table using standard `Configuration::get()` and `Configuration::updateValue()` methods.

### 4.4 JavaScript Assets (`views/js/`)

The module relies heavily on JavaScript for its front-office functionality, specifically for the popup and slider behavior.

- **`popupslider/jscolor/jscolor.js`**:

  - **Scope:** Back-office (used within the module’s configuration page).
  - **Responsibility:** Provides a JavaScript color picker functionality for the module’s configuration form, allowing merchants to easily select colors for the popup background, border, and overlay.
  - **Details:** This is a third-party library integrated for UI enhancement in the admin panel.
- **`popupslider/js/bxslider.js`**:

  - **Scope:** Front-office.
  - **Responsibility:** This is the core library for the animated image slider within the popup. It handles the transitions, navigation controls (arrows, dots), and responsive behavior of the slideshow.
  - **Details:** A widely used jQuery content slider. The module initializes this slider on the images within the popup.
- **`popupslider/js/script.js`**:

  - **Scope:** Front-office.
  - **Responsibility:** This custom script orchestrates the popup’s appearance and behavior.
    - **Cookie Management:** Checks for a cookie to determine if the user is a first-time visitor or if the re-display time has elapsed.
    - **Popup Display:** Triggers the display of the popup overlay and the slider content.
    - **Event Handling:** Binds events for closing the popup (e.g., clicking the close button, clicking the overlay).
    - **bxSlider Initialization:** Initializes the `bxslider.js` on the appropriate DOM element containing the slider images.
  - **Details:** This script is crucial for the module’s “smart” display logic and user interaction.

### 4.5 CSS Stylesheets (`views/css/`)

The module does not explicitly list custom CSS files in the provided inventory. However, it is highly probable that the `bxslider.js` library includes its own CSS (e.g., `jquery.bxslider.css` or similar) which would be loaded, and the module’s `header.tpl` or `cz.php` might inject inline styles based on configuration settings (colors, dimensions).

If any CSS files were present, they would typically:

- **Scope:** Front-office (for popup and slider styling).
- **Main UI components:** Style the popup container, overlay, close button, slider navigation (arrows, dots), and individual slide images.
- **Key CSS class selectors:** Developers should look for classes like `.popupslider-overlay`, `.popupslider-container`, `.popupslider-close`, `.bx-wrapper`, `.bx-viewport`, `.bx-controls`, etc., to override in their theme’s `custom.css` or child theme.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - **`popupslider/header.tpl`**:
    - **Hook:** Likely `displayHeader` (or similar, given the name). This template is responsible for rendering the HTML structure of the popup overlay, the popup container, and the image slider itself.
    - **Output:** It generates the necessary `div` elements for the overlay, the main popup box, the close button, and the `ul` list that `bxslider.js` will transform into an interactive slideshow. It also likely includes inline styles derived from the module’s configuration settings (width, height, colors, etc.) and includes the necessary JavaScript and CSS assets.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create custom database tables. All configuration settings are stored in the standard PrestaShop `ps_configuration` table.
  - **Configuration Keys (Examples):**
    - `POPUP_SLIDER_WIDTH`
    - `POPUP_SLIDER_HEIGHT`
    - `POPUP_SLIDER_BG_COLOR`
    - `POPUP_SLIDER_BORDER_COLOR`
    - `POPUP_SLIDER_BORDER_WIDTH`
    - `POPUP_SLIDER_BORDER_RADIUS`
    - `POPUP_SLIDER_SHADOW`
    - `POPUP_SLIDER_OVERLAY_COLOR`
    - `POPUP_SLIDER_OVERLAY_OPACITY`
    - `POPUP_SLIDER_REDISPLAY_TIME`
    - `POPUP_SLIDER_SHOW_CLOSE_BTN`
    - `POPUP_SLIDER_CLOSE_ON_OVERLAY_CLICK`
    - `POPUP_SLIDER_IMAGE_X` (where X is an incrementing ID for each image, storing URL, link, alt text).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Executed in the `<head>` section of every front-office page. | Used to inject the module’s CSS and JavaScript files, and potentially the initial HTML structure for the popup (though the popup itself is usually hidden until triggered by JS). |
| `displayFooter` (Potential) | Executed at the end of the `<body>` section of every front-office page. | Could be used as an alternative to `displayHeader` for injecting the popup HTML and JS, often preferred for performance as it doesn’t block page rendering. |
| `displayRightColumn` (Potential) | Executed in the right column of the front-office. | While mentioned in the merchant description, it’s unlikely a full-page popup would be rendered here. More likely for a small banner or trigger. |
| `displayLeftColumn` (Potential) | Executed in the left column of the front-office. | Similar to `displayRightColumn`, unlikely for a full-page popup. |
| `displayProductButtons` (Potential) | Executed on the product page, near the add-to-cart button. | Unlikely for a global popup, but could be used for a product-specific popup if the module had such advanced features. |

Given the `header.tpl` file, `displayHeader` is the most probable hook for injecting the module’s assets and initial popup structure.

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the Popup Slider module, please refer to your customer account at MyPresta.eu. Our team is dedicated to providing assistance and ensuring your module functions optimally.

- **MyPresta.eu Order History & Downloads:** <https://mypresta.eu/my-account/orders/>
- **MyPresta.eu Support Contact:** <https://mypresta.eu/contact>
