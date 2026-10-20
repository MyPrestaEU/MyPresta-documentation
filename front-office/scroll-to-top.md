---
title: "Scroll to top - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Scroll to top PrestaShop module by MyPresta.eu."
sidebar:
  label: "Scroll to top - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Scroll to top Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/scroll-to-top.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/scroll-to-top/)
>
> ---


# Scroll to top

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installing the module, navigate to **Modules > Module Manager** and click “Configure” next to “Scroll to top”. This page allows you to customize the appearance and positioning of the scroll-to-top button.

#### **Visual Positioning**

- **What this setting does:** This is a visual representation of where the button will appear on your store. It’s not a direct setting but rather a visual aid that changes based on your “Position X” and “Position Y” settings.
- **Effect of changing this setting:** As you adjust “Position X” and “Position Y”, the button’s preview on this configuration page will move, helping you visualize its final location on your front office.
- **Recommended value:** This is dynamic.
- **Merchant scenario / example:** If you want the button to be closer to the bottom-right, you’ll see the preview move there as you adjust the X and Y values.

#### **Color Scheme**

- **What this setting does:** This controls the background color of the scroll-to-top button.
- **Effect of changing this setting:**
  - *When set to a specific color (e.g., #007bff for blue):* The button will display with that background color on your front office.
  - *When set to a different color:* The button’s background will change accordingly.
- **Recommended value:** Choose a color that complements your store’s branding and is clearly visible against your website’s background, but not too distracting.
- **Merchant scenario / example:** If your brand colors are blue and white, you might set this to a shade of blue to match your theme.

#### **Opacity**

- **What this setting does:** This determines how transparent or opaque the scroll-to-top button is. A lower opacity makes it more transparent, allowing background content to show through.
- **Effect of changing this setting:**
  - *When set to a high value (e.g., 1.0 or 100%):* The button will be fully opaque, with no transparency.
  - *When set to a lower value (e.g., 0.7 or 70%):* The button will be semi-transparent, subtly blending with your store’s background.
- **Recommended value:** A value between 0.8 and 1.0 (80%-100%) is usually good. Too low, and it might be hard to see; too high, and it might feel too prominent.
- **Merchant scenario / example:** If you want the button to be present but not overly dominant, setting opacity to 0.8 might be a good choice.

#### **Position X (from right)**

- **What this setting does:** This controls the horizontal position of the button, specifically its distance from the right edge of the browser window.
- **Effect of changing this setting:**
  - *Increasing the value (e.g., from 20px to 50px):* Moves the button further to the left, away from the right edge.
  - *Decreasing the value (e.g., from 50px to 20px):* Moves the button closer to the right edge.
- **Recommended value:** Start with a value like `20px` or `30px` to keep it comfortably away from the edge without being too far into the content area.
- **Merchant scenario / example:** If you have a chat widget or another fixed element on the right side of your store, you might increase this value to `60px` to prevent the scroll-to-top button from overlapping it.

#### **Position Y (from bottom)**

- **What this setting does:** This controls the vertical position of the button, specifically its distance from the bottom edge of the browser window.
- **Effect of changing this setting:**
  - *Increasing the value (e.g., from 20px to 50px):* Moves the button further upwards, away from the bottom edge.
  - *Decreasing the value (e.g., from 50px to 20px):* Moves the button closer to the bottom edge.
- **Recommended value:** Start with a value like `20px` or `30px` to keep it comfortably away from the bottom edge, above the footer.
- **Merchant scenario / example:** If your store has a sticky footer or a cookie consent bar at the very bottom, you might increase this value to `70px` to ensure the scroll-to-top button is always visible above those elements.

#### **Configuration Quick Reference Table**

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Visual Positioning | Dynamic | Visual aid for button placement based on X/Y settings. |
| Module Configuration | Color Scheme | Varies (e.g., #007bff) | Sets the background color of the scroll-to-top button. |
| Module Configuration | Opacity | 0.8 - 1.0 | Controls the transparency of the button (0.0 = fully transparent, 1.0 = fully opaque). |
| Module Configuration | Position X (from right) | 20px - 30px | Defines the button’s horizontal distance from the right edge of the screen. |
| Module Configuration | Position Y (from bottom) | 20px - 30px | Defines the button’s vertical distance from the bottom edge of the screen. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: The scroll-to-top button isn’t appearing on my store. What should I do?**
A:

1. **Check Module Status:** Go to **Modules > Module Manager** and ensure the “Scroll to top” module is installed and enabled.
2. **Clear Cache:** PrestaShop uses caching. Go to **Advanced Parameters > Performance**, scroll down to “Clear cache” and click “Clear cache”. Then refresh your front office.
3. **Scroll Down:** Remember, the button only appears when you scroll down the page. Make sure you’ve scrolled sufficiently for it to become visible.
4. **Check Positions:** Ensure “Position X” and “Position Y” are not set to extremely high values that might push the button off-screen. Try setting them to `20px` each as a test.
5. **Theme Compatibility:** While rare, some highly customized themes might have CSS conflicts. If the above steps don’t work, temporarily switch to the default PrestaShop theme (Classic) to see if the button appears. If it does, your theme’s developer might need to assist.

**Q: The button is visible but doesn’t scroll to the top when clicked.**
A:

1. **Check JavaScript:** This usually indicates a JavaScript conflict or error. Open your browser’s developer console (usually F12, then go to the “Console” tab) and look for any red error messages.
2. **Module Order:** Ensure no other module is interfering with core JavaScript functionality.
3. **Reinstall:** Try uninstalling and reinstalling the module. This can sometimes resolve corrupted files.

**Q: How can I change the icon of the button (e.g., from an arrow to something else)?**
A: The module uses a standard arrow icon. Changing this requires direct modification of the module’s CSS or template files, which falls under developer customization. It’s not an option available in the module’s configuration.

**Q: The button looks fine on desktop but is too big/small/misplaced on mobile.**
A:

1. **Adjust X & Y:** Use the “Position X” and “Position Y” settings to fine-tune its placement specifically for mobile. You might need different values to avoid conflicts with mobile-specific UI elements.
2. **Theme Responsiveness:** The module’s CSS is designed to be responsive, but your theme’s overall responsiveness can influence how it appears. Test on actual devices or use your browser’s developer tools to simulate different screen sizes.
3. **Custom CSS (Developer Task):** For advanced sizing or styling changes specific to mobile, a webmaster would need to add custom CSS rules to your theme, targeting the button only on smaller screens.

**Q: Will this module slow down my website?**
A: No, the “Scroll to top” module is very lightweight. It adds minimal CSS and JavaScript, which are loaded efficiently. Any performance impact would be negligible.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers, webmasters, and agencies looking to understand, debug, or extend the “Scroll to top” module.

### 4.1 Architecture Overview

The “Scroll to top” module is a straightforward PrestaShop module primarily focused on front-office UI enhancement. It follows a classic PrestaShop module structure, leveraging hooks to inject its HTML, CSS, and JavaScript assets into the front office. It does not introduce custom controllers or complex data models, relying instead on PrestaShop’s configuration system for its settings. The core functionality is handled client-side via JavaScript.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. The module’s front-office functionality is entirely handled by injecting assets and a template via hooks.
- **Back-Office Admin Controllers**: None. All configuration is managed through the main module’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

- No custom classes or `ObjectModel` definitions are present in this module. All logic resides within the main `scrolltop.php` file.

### 4.4 JavaScript Assets (`views/js/`)

- **`scrolltop/scrolltop.js`**
  - **Scope:** Front-office.
  - **Responsibility:** This script handles the core client-side logic for the scroll-to-top button.
  - **Details:**
    - It waits for the DOM to be fully loaded (`$(document).ready()`).
    - It attaches an event listener to the `$(window).scroll()` event.
    - Inside the scroll event handler, it checks `$(this).scrollTop()`. If the scroll position is greater than a certain threshold (e.g., 100px), it shows the scroll-to-top button; otherwise, it hides it.
    - It attaches a click event listener to the scroll-to-top button element.
    - When clicked, it uses `$('html, body').animate({scrollTop: 0}, 'slow');` to smoothly animate the page scroll back to the top.
    - It prevents the default link behavior (`return false;`).
  - **Dependencies:** jQuery (which is typically available in PrestaShop front office).

### 4.5 CSS Stylesheets (`views/css/`)

- **`scrolltop/scrolltop.css`**
  - **Scope:** Front-office customer styling.
  - **Responsibility:** Defines the visual appearance and fixed positioning of the scroll-to-top button.
  - **Details:**
    - Targets the `#scroll-to-top` element.
    - Uses `position: fixed;` to keep the button in a static position relative to the viewport.
    - Applies `bottom` and `right` properties, dynamically set by the module’s configuration, to control its exact placement.
    - Defines `z-index` to ensure the button appears above other content.
    - Sets `display: none;` initially, as the JavaScript controls its visibility.
    - Styles for `background-color`, `border-radius`, `padding`, `width`, `height`, `line-height`, `text-align`, `color` (for the arrow icon), `font-size`, and `cursor`.
    - Includes a `transition` property for smooth visual changes (e.g., on hover or when appearing/disappearing).
    - May include responsive adjustments using media queries to optimize appearance on different screen sizes.
  - **Key CSS class selectors developers can override:** `#scroll-to-top`, `#scroll-to-top i` (for the icon).

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - **`scrolltop/footer.tpl`**
    - **Hook:** `displayFooter` (or `displayHeader` for asset loading).
    - **Purpose:** This template renders the HTML structure for the scroll-to-top button.
    - **Content:** Typically contains an `<a>` tag or `<div>` with an ID like `#scroll-to-top`, and an `<i>` tag (often using Font Awesome or a similar icon font) for the arrow icon.
    - It also includes inline style attributes or data attributes to pass the configured `color`, `opacity`, `position X`, and `position Y` values from the module’s settings to the front-end CSS or JavaScript for dynamic styling.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create any custom SQL tables.
  - Configuration settings (`st_color`, `st_x`, `st_y`, `st_o`, `mypresta_updates`, `update_`, `updatev_`) are stored in PrestaShop’s `ps_configuration` table.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Used to register and load the module’s CSS (`scrolltop.css`) and JavaScript (`scrolltop.js`) assets. |
| `displayFooter` | At the end of the `<body>` section of every front-office page, just before the closing `</body>` tag. | Used to render the HTML structure of the scroll-to-top button (`footer.tpl`). This ensures the button’s HTML is present in the DOM for the JavaScript to manipulate. |

## 5. Official Support & Updates

For official updates, technical support, and the latest versions of the “Scroll to top” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions regarding the module’s functionality and compatibility.
