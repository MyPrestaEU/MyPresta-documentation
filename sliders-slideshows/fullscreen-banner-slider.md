---
title: "Fullscreen Banner Slider - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Fullscreen Banner Slider PrestaShop module by MyPresta.eu."
sidebar:
  label: "Fullscreen Banner Slider - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Fullscreen Banner Slider Module on MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/fullscreen-banner-slider.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/sliders-slideshows/fullscreen-banner-slider/)
>
> ---


# Fullscreen Banner Slider

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Fullscreen Banner Slider” module in your Module Manager. This will take you to the main configuration screen where you can manage all aspects of your slider.

The module’s configuration is handled through the `getContent()` method in the main module file, presenting a standard PrestaShop configuration form.

#### **General Settings**

- **What this setting does:** These settings control the overall behavior and appearance of your fullscreen slider.
- **Effect of changing this setting:** Adjusting these values will directly impact how the slider is displayed to your customers, its size, speed, and whether it’s active.

| Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- |
| **Enable Fullscreen Slider** | YES | **Purpose:** Turns the entire slider feature on or off.   **Effect:**   *When enabled:* The fullscreen slider will appear to new visitors.   *When disabled:* The slider will not be displayed on your store.   **Recommended:** YES, to activate the feature. |
| **Slider Width** | 100% | **Purpose:** Defines the width of the slider.   **Effect:**   *Set to 100% (recommended):* The slider will span the entire width of the browser window.   *Set to a fixed pixel value (e.g., 1200px):* The slider will have a fixed width, potentially leaving empty space on very wide screens.   **Recommended:** 100% for a true fullscreen experience. |
| **Slider Height** | 100% | **Purpose:** Defines the height of the slider.   **Effect:**   *Set to 100% (recommended):* The slider will span the entire height of the browser window.   *Set to a fixed pixel value (e.g., 800px):* The slider will have a fixed height, potentially leaving empty space on very tall or short screens.   **Recommended:** 100% for a true fullscreen experience. |
| **Animation Type** | (Dropdown with various options) | **Purpose:** Selects the visual transition effect between banners.   **Effect:** Each option provides a different animation style (e.g., fade, slide, cube, etc.). Experiment to find one that matches your brand.   **Recommended:** Choose an animation that is smooth and not too distracting. “Fade” or “Slide” are often good starting points. |
| **Animation Speed (ms)** | 800 | **Purpose:** Controls how fast the transition between banners occurs, in milliseconds (1000ms = 1 second).   **Effect:**   *Higher value (e.g., 1500):* Slower, more gradual transitions.   *Lower value (e.g., 400):* Faster, snappier transitions.   **Recommended:** 800-1000ms for a balanced, professional feel. |
| **Interval between slides (ms)** | 3000 | **Purpose:** Sets the duration each banner is displayed before transitioning to the next, in milliseconds.   **Effect:**   *Higher value (e.g., 5000):* Banners stay on screen longer, giving visitors more time to read/view.   *Lower value (e.g., 2000):* Banners change more quickly, creating a dynamic feel.   **Recommended:** 3000-5000ms, depending on the complexity of your banner content. |
| **Show Navigation Arrows** | YES | **Purpose:** Determines if “next” and “previous” arrows are visible for manual slide navigation.   **Effect:**   *When enabled:* Arrows appear on the sides of the slider, allowing users to click through banners.   *When disabled:* Banners only change automatically based on the interval.   **Recommended:** YES, for better user control. |
| **Show Pagination Dots** | YES | **Purpose:** Determines if small dots (or thumbnails) representing each slide are visible, usually at the bottom of the slider.   **Effect:**   *When enabled:* Dots appear, allowing users to see how many slides there are and jump to a specific one.   *When disabled:* No visual indicator of slide count or direct navigation.   **Recommended:** YES, for better user orientation and navigation. |
| **Autoplay Slider** | YES | **Purpose:** Controls whether the slider automatically cycles through banners.   **Effect:**   *When enabled:* Banners will automatically change after the set interval.   *When disabled:* Banners will only change if the user clicks navigation arrows or pagination dots.   **Recommended:** YES, to ensure all your messages are seen. |
| **Close Button Text** | Close | **Purpose:** Allows you to customize the text displayed on the button that closes the fullscreen slider.   **Effect:** Changes the text on the button.   **Recommended:** “Close”, “Skip”, or “Continue to Store”. |
| **Cookie Expiration (days)** | 7 | **Purpose:** Sets how long the module remembers that a user has seen the slider, preventing it from showing again.   **Effect:**   *Set to 7 days:* The slider will reappear for the same user after 7 days.   *Set to 0:* The slider will appear on every visit (not recommended for user experience).   *Set to a high number (e.g., 365):* The slider will appear only once a year for returning visitors.   **Recommended:** 7 days is a good balance, allowing you to re-engage returning visitors with new offers periodically without being intrusive. |

#### **Banner Management**

This section allows you to add, edit, and remove the individual banners that will be displayed in your slider.

- **What this setting does:** Each entry here represents one image (banner) in your slider. You can upload the image, link it to a specific page, and set its display order.
- **Effect of changing this setting:**
  - *Adding a new banner:* Introduces a new slide into your rotation.
  - *Editing a banner:* Updates its image, link, or position.
  - *Deleting a banner:* Removes it from the slider.

For each banner, you will typically find fields like:

- **Banner Image:** Upload the image file for your slide. Ensure images are high-resolution and optimized for web to maintain fast loading times.
- **Banner Link (URL):** The web address (URL) where customers will be directed if they click on this banner. Leave empty if the banner is purely informational.
- **Display Order:** A numerical value that determines the sequence of the banners. Banners with lower numbers appear first.

#### **Configuration Quick Reference Table**

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|
| Module Configuration | Enable Fullscreen Slider | YES | Activates/deactivates the entire slider feature. |
| Module Configuration | Slider Width | 100% | Sets the width of the slider (e.g., 100% for full width). |
| Module Configuration | Slider Height | 100% | Sets the height of the slider (e.g., 100% for full height). |
| Module Configuration | Animation Type | (Various) | Chooses the visual transition effect between slides. |
| Module Configuration | Animation Speed (ms) | 800 | Controls the speed of slide transitions. |
| Module Configuration | Interval between slides (ms) | 3000 | Sets how long each banner is displayed. |
| Module Configuration | Show Navigation Arrows | YES | Displays/hides arrows for manual slide navigation. |
| Module Configuration | Show Pagination Dots | YES | Displays/hides dots/thumbnails for direct slide access. |
| Module Configuration | Autoplay Slider | YES | Enables/disables automatic slide progression. |
| Module Configuration | Close Button Text | Close | Customizes the text on the slider close button. |
| Module Configuration | Cookie Expiration (days) | 7 | Determines how long a user won’t see the slider after closing it. |
| Module Configuration | Banner Image | (Upload) | Uploads the image for an individual slide. |
| Module Configuration | Banner Link (URL) | (Empty) | Sets the destination URL when a banner is clicked. |
| Module Configuration | Display Order | (Number) | Defines the sequence in which banners appear. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: The slider isn’t appearing on my store. What should I do?**
A:

1. **Check Module Status:** Go to **Modules > Module Manager** and ensure “Fullscreen Banner Slider” is installed and enabled.
2. **Configuration:** Verify that “Enable Fullscreen Slider” is set to YES in the module’s configuration.
3. **Cookie Expiration:** If you’ve seen the slider before, it might be due to the cookie. Try clearing your browser’s cookies or opening your store in an incognito/private browsing window to simulate a first-time visitor.
4. **Cache:** Clear your PrestaShop cache under **Advanced Parameters > Performance**. Also, clear your browser cache.
5. **Theme Compatibility:** While the module is designed to be compatible, sometimes custom themes can interfere. Temporarily switch to the default PrestaShop theme to see if the slider appears. If it does, your theme might require a small adjustment (contact your theme developer or a webmaster).

**Q: My banner images look blurry or stretched. How can I fix this?**
A: This usually happens if your uploaded images are not high enough resolution or have incorrect aspect ratios for a fullscreen display.

1. **Image Quality:** Always use high-resolution images.
2. **Aspect Ratio:** While the module scales, try to use images that are wide and relatively short, suitable for a fullscreen banner (e.g., 1920x1080 pixels or similar wide formats). Avoid very tall or narrow images.
3. **Optimization:** Ensure your images are optimized for web (compressed) to prevent slow loading times, even if they are high resolution.

**Q: Can I have different sliders for different pages or customer groups?**
A: This specific version of the Fullscreen Banner Slider module is designed for a single, site-wide fullscreen display that appears once per visitor session/cookie. It does not offer advanced targeting options for specific pages or customer groups. If you need such functionality, you might need a more advanced banner management module or custom development.

**Q: How do I translate the “Close” button text into other languages?**
A:

1. Go to **International > Translations** in your PrestaShop Back Office.
2. Select “Installed modules translations” as the Type of translation.
3. Choose your theme.
4. Select the language you want to translate.
5. Find the “Fullscreen Banner Slider” module in the list. You should see the “Close Button Text” field there to translate. Save your changes.

**Q: The slider appears, but the animations are not working, or the layout is off.**
A:

1. **JavaScript Conflicts:** This is often due to conflicts with other modules’ JavaScript or your theme’s JavaScript. Check your browser’s developer console (F12 key) for any JavaScript errors.
2. **CSS Conflicts:** Similar to JS, your theme’s CSS might be overriding the module’s styles.
3. **Module Reinstallation:** Sometimes a fresh reinstallation can resolve unexpected issues. Uninstall the module (without deleting data if prompted), then reinstall it.
   If errors persist, consult a webmaster or contact MyPresta.eu support with details from your browser’s developer console.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The Fullscreen Banner Slider module (`fullscreenslider`) is a standard PrestaShop module primarily implemented within its main PHP file, `ajax_fullscreenslider.php`. It leverages PrestaShop’s `Module` class for installation, uninstallation, and configuration (`getContent()`). The front-office display is managed by hooking into `displayHeader` and rendering a Smarty template. The slider functionality itself relies on external jQuery plugins (`jquery.skitter.js`, `jquery.easing.1.3.js`) for animations and `noconflict.js` to ensure jQuery compatibility. Configuration values are stored in `ps_configuration`.

### 4.2 Controllers (`controllers/`)

This module does not utilize dedicated Front-Office or Back-Office Admin Controllers. All configuration is handled within the `getContent()` method of the main module file.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or `ObjectModel` instances in the `classes/` directory. All data (banner images, links, order) is managed directly through the module’s configuration settings, typically serialized and stored in `ps_configuration`.

### 4.4 JavaScript Assets (`views/js/`)

The module includes several JavaScript files, primarily for the slider’s core functionality and animations. These are typically loaded in the front-office.

- `fullscreenslider/js/jquery.easing.1.3.js`
  - **Scope:** Front-office.
  - **Responsibility:** Provides additional easing functions for jQuery animations, allowing for more diverse and smooth transition effects beyond the default linear or swing. This is a dependency for `jquery.skitter.js`.
- `fullscreenslider/js/jquery.skitter.js`
  - **Scope:** Front-office.
  - **Responsibility:** This is the main jQuery plugin responsible for the slider’s functionality. It handles image loading, animation transitions, navigation (arrows, pagination), autoplay, and event binding for user interaction. It initializes the slider based on the configuration settings passed from the module.
- `fullscreenslider/js/noconflict.js`
  - **Scope:** Front-office.
  - **Responsibility:** This script is crucial for ensuring compatibility when multiple JavaScript libraries (especially different versions of jQuery) are loaded on the same page. It typically wraps jQuery code in an immediately invoked function expression (IIFE) that passes `jQuery` as an argument, allowing it to be aliased as `$` locally without conflicting with other libraries that might also use `$`.

### 4.5 CSS Stylesheets (`views/css/`)

The module includes one primary CSS file for styling the slider.

- `fullscreenslider/css/skitter.styles.css`
  - **Scope:** Front-office customer styling.
  - **Responsibility:** Contains all the necessary CSS rules to style the fullscreen slider, including its container, navigation arrows, pagination dots, and the visual effects of the chosen animation type. It defines the default look and feel of the slider.
  - **Key CSS class selectors developers can override:**
    - `.box_skitter` (main slider container)
    - `.box_skitter ul` (list of slides)
    - `.box_skitter ul li` (individual slide)
    - `.box_skitter .info_slide` (slide captions/info, if used)
    - `.box_skitter .prev_button`, `.box_skitter .next_button` (navigation arrows)
    - `.box_skitter .info_slide_dots`, `.box_skitter .info_slide_thumb` (pagination elements)
    - Specific classes for animation types (e.g., `.cube`, `.fade`, etc.)

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses Smarty templates to render its front-office content.

- **Hook templates (`views/templates/hook/`)**:

  - `fullscreenslider/header.tpl`
    - **Hook:** `displayHeader` (or similar, depending on module’s `hook` method implementation).
    - **Purpose:** This template is likely responsible for injecting the necessary CSS and JavaScript files into the `<head>` section of the HTML, and potentially the initial HTML structure for the slider container, which will then be populated and animated by the JavaScript. It might also contain the logic to check for the cookie that determines if the slider should be shown.
  - `fullscreenslider/top.tpl`
    - **Hook:** This template is likely rendered within the `displayTop` hook or directly included by `header.tpl` to output the main HTML structure of the fullscreen slider itself.
    - **Purpose:** It contains the `div` elements and `ul/li` structure that `jquery.skitter.js` expects to find to initialize the slider. It iterates through the configured banners, outputting each image with its associated link. It also includes the HTML for the close button.
- **Admin templates (`views/templates/admin/`)**: This module does not appear to use dedicated admin templates, as configuration is handled directly within `getContent()`.
- **Front-office templates (`views/templates/front/`)**: This module does not appear to use dedicated standalone front-office page templates.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create custom SQL tables.
  - Configuration settings (including serialized data for banners like image paths, links, and order) are stored in the `ps_configuration` table. Keys typically follow the pattern `FULLSCREENSLIDER_SETTING_NAME`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Executed in the `<head>` section of every front-office page. | Injects module’s CSS and JavaScript files, and potentially the initial HTML structure for the slider, along with cookie-checking logic. |
| `displayTop` (or similar) | Executed in the top section of the front-office page, often just below the header. | Renders the main HTML structure of the fullscreen slider, including the banner images and navigation elements. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the Fullscreen Banner Slider module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist merchants and developers with any issues or questions regarding the module’s functionality and compatibility.
