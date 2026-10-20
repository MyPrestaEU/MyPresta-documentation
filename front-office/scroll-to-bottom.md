---
title: "Scroll to bottom - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Scroll to bottom PrestaShop module by MyPresta.eu."
sidebar:
  label: "Scroll to bottom - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Scroll to bottom Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/scroll-to-bottom.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/scroll-to-bottom/)
>
> ---


# Scroll to bottom

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main and only configuration screen for the “Scroll to bottom” module. You can access it by navigating to **Modules > Module Manager** and searching for “Scroll to bottom”, then clicking the “Configure” button.

#### Settings & Options

- **Color of the button (st\_color)**

  - **What this setting does:** This allows you to define the color of the “Scroll to bottom” button. You can use standard HTML color names (like `red`, `blue`, `green`) or hexadecimal color codes (like `#FF0000` for red, `#0000FF` for blue).
  - **Effect of changing this setting:**
    - *When set to a specific color (e.g., `#007bff`):* The button will display in that exact color on your front office.
    - *When left empty or invalid:* The button will likely revert to a default color defined by the module’s CSS, which might not match your brand.
  - **Recommended value:** Choose a color that complements your store’s design and is clearly visible against your background, but not overly distracting. Use your brand’s primary or secondary color.
  - **Merchant scenario / example:** If your brand uses a lot of deep blue, setting this to `#000080` (navy blue) would make the button blend nicely while remaining functional.
- **X position of the button (st\_x)**

  - **What this setting does:** This controls the horizontal position of the button on the screen. It determines how far from the right edge of the browser window the button will appear. The value is typically in pixels.
  - **Effect of changing this setting:**
    - *When set to a lower value (e.g., `20`):* The button will be closer to the right edge of the screen.
    - *When set to a higher value (e.g., `80`):* The button will be further away from the right edge, moving towards the center of the screen.
  - **Recommended value:** `20` or `30` pixels is a common and unobtrusive placement. This keeps it out of the main content area but still easily accessible.
  - **Merchant scenario / example:** If you have other fixed elements on the right side of your screen (like a chat widget), you might need to increase this value to `50px` to prevent the “Scroll to bottom” button from overlapping.
- **Y position of the button (st\_y)**

  - **What this setting does:** This controls the vertical position of the button on the screen. It determines how far from the top edge of the browser window the button will appear. The value is typically in pixels.
  - **Effect of changing this setting:**
    - *When set to a lower value (e.g., `20`):* The button will be closer to the top edge of the screen.
    - *When set to a higher value (e.g., `80`):* The button will be further down from the top edge.
  - **Recommended value:** `20` or `30` pixels is a good starting point. This places it in the top-right corner without being too high or too low.
  - **Merchant scenario / example:** If your store’s header is very tall or you have a “Scroll to Top” button also in the top-right, you might adjust this to `60px` or `70px` to ensure both buttons have enough space and don’t overlap.
- **Opacity of the button (st\_o)**

  - **What this setting does:** This controls the transparency of the button. Opacity values range from `0` (completely transparent/invisible) to `1` (completely opaque/solid). You can use decimal values like `0.5` for 50% transparency.
  - **Effect of changing this setting:**
    - *When set to `1`:* The button will be fully visible and solid.
    - *When set to `0.5`:* The button will be semi-transparent, allowing background content to show through.
    - *When set to `0`:* The button will be invisible (though still clickable if you know where it is).
  - **Recommended value:** `0.8` or `0.9` is often a good balance. It makes the button slightly less intrusive while still being clearly visible. `1` is also perfectly fine if you want it to stand out more.
  - **Merchant scenario / example:** If you find the button too prominent or distracting, reducing its opacity to `0.7` can make it blend more subtly into your store’s design without losing its functionality.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Color of the button (st\_color) | `#007bff` (example) | Sets the button’s color. Affects visibility and brand consistency. |
| Module Configuration | X position of the button (st\_x) | `20` | Horizontal distance from the right edge. Prevents overlap with other elements. |
| Module Configuration | Y position of the button (st\_y) | `20` | Vertical distance from the top edge. Positions the button clearly. |
| Module Configuration | Opacity of the button (st\_o) | `0.8` | Transparency of the button. Controls how intrusive or subtle it appears. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

- **Q: The button isn’t showing up on my store.**
  - **A:** First, ensure the module is installed and enabled in **Modules > Module Manager**. Then, check the module’s configuration page to make sure all settings are saved. If it’s still not appearing, try clearing your PrestaShop cache (**Advanced Parameters > Performance > Clear cache**). Sometimes, custom themes might also interfere; temporarily switch to the default PrestaShop theme to rule this out.
- **Q: The button is showing, but it’s in the wrong place or looks strange.**
  - **A:** Go to the module’s configuration page. Adjust the “X position” and “Y position” settings to move the button horizontally and vertically. Experiment with different values until it’s in a satisfactory location. For appearance issues, check the “Color” and “Opacity” settings. If it still looks off, your theme’s CSS might be overriding the module’s styles.
- **Q: The scroll animation isn’t smooth or doesn’t work.**
  - **A:** This module uses JavaScript for the smooth scrolling effect. Ensure there are no JavaScript errors on your site (you can check your browser’s developer console for errors). Conflicts with other modules or custom theme JavaScript can sometimes prevent the animation from working correctly. Clearing cache is a good first step.
- **Q: Can I change the icon of the button?**
  - **A:** The module’s current version does not offer a direct setting to change the icon from the back office. This would require custom CSS or template modifications (see the Developer Guide for more technical details).
- **Q: Does this module affect my store’s performance or SEO?**
  - **A:** This module is very lightweight, adding minimal CSS and JavaScript. It should have negligible impact on your store’s loading speed or SEO. The functionality is purely for user experience and does not alter content in a way that would affect search engine indexing.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Scroll to bottom” module is a straightforward front-office feature implemented as a standard PrestaShop module. It primarily leverages PrestaShop’s hook system to inject its CSS, JavaScript, and the button’s HTML structure into the front office. Configuration is handled via the `getContent()` method in the main module file, storing settings in `ps_configuration`. There are no custom controllers, ObjectModels, or complex database interactions.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. The module’s front-office functionality is injected directly via hooks.
- **Back-Office Admin Controllers**: None. Configuration is handled within the main module file.

### 4.3 Core Classes & Models (`classes/`)

- None. The module does not define any custom classes or ObjectModels. All logic is contained within `scrollbottom.php`.

### 4.4 JavaScript Assets (`views/js/`)

- `scrollbottom/scrollbottom.js`
  - **Scope:** Front-office.
  - **Responsibility:** This script is responsible for the core functionality of the “Scroll to bottom” button.
    - It likely listens for the DOM to be ready.
    - It attaches a click event listener to the “Scroll to bottom” button element.
    - When clicked, it uses JavaScript’s `window.scrollTo()` or `element.scrollIntoView()` method, often with `behavior: 'smooth'`, to animate the scroll to the bottom of the page (specifically, the `body` or `html` element’s maximum scroll height).
    - It might also handle the button’s visibility, making it appear or disappear based on the user’s scroll position (e.g., only show when the user has scrolled down a certain amount).

### 4.5 CSS Stylesheets (`views/css/`)

- `scrollbottom/scrollbottom.css`
  - **Scope:** Front-office customer styling.
  - **Main UI components and containers it styles:** This stylesheet defines the visual appearance and positioning of the “Scroll to bottom” button.
    - It will likely target a specific ID or class for the button (e.g., `#scrollbottom_button`).
    - It defines properties such as `position: fixed`, `right`, `top`, `z-index`, `background-color`, `color`, `padding`, `border-radius`, `cursor`, and potentially `display: none` initially, with JavaScript controlling its visibility.
    - It may also include styles for the arrow icon within the button (e.g., using a font icon or a background image).
  - **Key CSS class selectors developers can override in their theme:** Developers can inspect the generated HTML to find the exact ID/class of the button (e.g., `#scrollbottom_button`) and override its styles in their theme’s `custom.css` or equivalent file to achieve a custom look.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - `scrollbottom/adv.tpl`: This template is likely used for displaying an advertisement or promotional content related to MyPresta.eu, often injected into a hook like `displayAdminHome` or similar, but not directly related to the front-office button functionality.
  - `scrollbottom/footer.tpl`: This is the primary template for the front-office button.
    - **Hooked into:** `displayFooter` or `footer` (depending on PrestaShop version and theme).
    - **Outputs:** The HTML structure for the “Scroll to bottom” button, including its ID/class, the arrow icon, and potentially inline styles or data attributes derived from the module’s configuration settings (color, position, opacity).
- **Admin templates (`views/templates/admin/`)**: None.
- **Front-office templates (`views/templates/front/`)**: None.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any custom SQL tables.
  - Configuration settings are stored in the `ps_configuration` table using keys like `ST_COLOR`, `ST_X`, `ST_Y`, `ST_O`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of the front office. | Used to register and include the module’s CSS (`scrollbottom.css`) and JavaScript (`scrollbottom.js`) files, ensuring they are loaded before the page content. |
| `header` | Alias for `displayHeader` in some contexts. | Same as `displayHeader`. |
| `displayFooter` | At the end of the `<body>` section, before the closing `</body>` tag. | Used to render the `footer.tpl` template, which contains the HTML structure for the “Scroll to bottom” button. |
| `footer` | Alias for `displayFooter` in some contexts. | Same as `displayFooter`. |

## 5. Official Support & Updates

For official updates, technical support, and to access the latest versions of the “Scroll to bottom” module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
