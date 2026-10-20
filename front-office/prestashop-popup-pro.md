---
title: "Prestashop Popup Pro - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Prestashop Popup Pro PrestaShop module by MyPresta.eu."
sidebar:
  label: "Prestashop Popup Pro - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Prestashop Popup Pro Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/prestashop-popup-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/prestashop-popup-pro/)
>
> ---


# Prestashop Popup Pro

## 1. Requirements & Compatibility

To ensure the Prestashop Popup Pro module runs smoothly on your store, please check the following requirements:

- **Supported PrestaShop Versions**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for general PrestaShop operation and should be available on any modern hosting environment. No special or unusual extensions are needed for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

The main configuration page for Prestashop Popup Pro is where you define everything about your popup: its content, appearance, and behavior.

**General Settings Tab**

- **Enable Popup Pro:**

  - **What this setting does:** This is the master switch for the entire module.
  - **Effect of changing this setting:**
    - *When enabled:* The module will start displaying popups according to your other settings.
    - *When disabled:* No popups will appear on your store, regardless of other configurations.
  - **Recommended value:** YES (when you want to use popups).
  - **Merchant scenario / example:** You’re running a campaign and want to activate your popup. You enable it. After the campaign, you disable it without losing your settings.
- **Popup Content (HTML Editor):**

  - **What this setting does:** This is the core of your popup. It’s a powerful HTML editor where you design what appears inside the popup window. You can add text, images, links, videos, and even embed forms (e.g., newsletter signup).
  - **Effect of changing this setting:** Any changes here directly update the visual content displayed to your customers in the popup.
  - **Recommended value:** Your desired promotional message, image, or call to action.
  - **Merchant scenario / example:** You want to announce a 15% discount. You’d type “Get 15% off your first order! Use code: SAVE15” and perhaps add an image of popular products.
- **Popup Width (px):**

  - **What this setting does:** Defines the width of your popup window in pixels.
  - **Effect of changing this setting:**
    - *Increasing the value:* Makes the popup wider.
    - *Decreasing the value:* Makes the popup narrower.
  - **Recommended value:** Start with `600px` to `800px` for desktop, then adjust based on your content and design.
  - **Merchant scenario / example:** You have a large banner image in your popup. You might set the width to `800px` to ensure the image displays well. For a simple text message, `400px` might be sufficient.
- **Popup Height (px):**

  - **What this setting does:** Defines the height of your popup window in pixels.
  - **Effect of changing this setting:**
    - *Increasing the value:* Makes the popup taller.
    - *Decreasing the value:* Makes the popup shorter.
  - **Recommended value:** `auto` (leave empty) or a specific pixel value if your content has a fixed height.
  - **Merchant scenario / example:** If your popup content is dynamic or short, leaving it empty (`auto`) allows the popup to adjust its height to fit the content. If you have a video that requires a specific aspect ratio, you might set a fixed height.
- **Display Popup On:**

  - **What this setting does:** Determines *when* the popup appears.
  - **Effect of changing this setting:**
    - *Page Load:* Popup appears after the page loads.
    - *Exit Intent:* Popup appears when the user’s mouse moves outside the browser window (indicating they might leave).
    - *Scroll:* Popup appears after the user scrolls down a certain percentage of the page.
    - *Time Delay:* Popup appears after a specified number of seconds.
  - **Recommended value:** Depends on your goal. “Exit Intent” is often effective for capturing abandoning visitors. “Page Load” with a short delay (e.g., 3-5 seconds) is good for general announcements.
  - **Merchant scenario / example:** To reduce cart abandonment, you’d choose “Exit Intent” and offer a discount code. To announce a new product line, you might use “Page Load” with a 3-second delay.
- **Delay Before Popup Appears (seconds):**

  - **What this setting does:** If “Display Popup On” is set to “Page Load” or “Time Delay”, this specifies how many seconds to wait before the popup shows.
  - **Effect of changing this setting:** A higher value means the popup appears later, giving the customer more time to browse. A lower value means it appears sooner.
  - **Recommended value:** `3` to `5` seconds. Too fast can be intrusive, too slow might miss the customer.
  - **Merchant scenario / example:** You want to give customers a moment to see your homepage before showing a newsletter signup. You set this to `5` seconds.
- **Popup Frequency (days):**

  - **What this setting does:** Controls how often a *returning* customer sees the popup. Once a customer closes the popup, this setting determines how many days pass before they see it again.
  - **Effect of changing this setting:**
    - *0:* Popup appears on every visit (can be annoying).
    - *Higher value:* Popup appears less frequently for returning visitors.
  - **Recommended value:** `7` to `30` days. Avoid annoying your loyal customers.
  - **Merchant scenario / example:** You’re running a month-long sale. You set this to `7` days so customers are reminded weekly, but not on every single visit.
- **Show Popup On Mobile Devices:**

  - **What this setting does:** Toggles whether the popup should display on smartphones and tablets.
  - **Effect of changing this setting:**
    - *Enabled:* Popup appears on mobile devices, adjusting responsively.
    - *Disabled:* Popup will only appear on desktop computers.
  - **Recommended value:** YES, but ensure your popup content is mobile-friendly.
  - **Merchant scenario / example:** You have a simple, text-based popup that looks good on mobile. You enable this to reach all your customers. If your popup has complex imagery or forms that break on mobile, you might disable it.
- **Popup Background Color:**

  - **What this setting does:** Sets the background color of the popup window itself.
  - **Effect of changing this setting:** Changes the visual color behind your content.
  - **Recommended value:** A color that complements your brand and makes your content stand out. Often white (`#FFFFFF`) or a light neutral color.
  - **Merchant scenario / example:** Your brand uses a lot of blue. You might choose a light blue background for the popup to match.
- **Popup Border Color:**

  - **What this setting does:** Sets the color of the border around the popup window.
  - **Effect of changing this setting:** Changes the visual color of the popup’s edge.
  - **Recommended value:** Often a subtle color, or transparent if you prefer no border.
  - **Merchant scenario / example:** You want a clean look, so you set this to a very light grey or transparent.
- **Popup Border Width (px):**

  - **What this setting does:** Sets the thickness of the border around the popup window.
  - **Effect of changing this setting:** A higher value makes the border thicker.
  - **Recommended value:** `0` to `2` pixels for a subtle effect.
  - **Merchant scenario / example:** You want a very defined popup, so you set a `2px` border. For a minimalist design, you set it to `0`.
- **Popup Border Radius (px):**

  - **What this setting does:** Controls the roundness of the popup’s corners.
  - **Effect of changing this setting:**
    - *0:* Sharp, square corners.
    - *Higher value:* More rounded corners.
  - **Recommended value:** `0` to `10` pixels for a modern look.
  - **Merchant scenario / example:** You want your popup to have soft, modern edges, so you set this to `8px`.
- **Overlay Background Color:**

  - **What this setting does:** Sets the color of the semi-transparent layer that appears *behind* the popup, darkening the rest of your store content.
  - **Effect of changing this setting:** Changes the color of the overlay. Often a dark color with transparency.
  - **Recommended value:** Black (`#000000`) with some transparency (e.g., `rgba(0,0,0,0.7)` if you can input RGBA).
  - **Merchant scenario / example:** You want the popup to be the absolute focus, so you choose a dark, almost opaque overlay.
- **Overlay Opacity (0-100):**

  - **What this setting does:** Controls how transparent or opaque the overlay background is. `0` is fully transparent (invisible), `100` is fully opaque (solid color).
  - **Effect of changing this setting:**
    - *Higher value:* More opaque, darker background, more focus on the popup.
    - *Lower value:* More transparent, lighter background, more of your store content visible.
  - **Recommended value:** `50` to `80`.
  - **Merchant scenario / example:** You want to slightly dim the background but still allow customers to see your store behind the popup. You set this to `60`.
- **Show Close Button:**

  - **What this setting does:** Toggles the visibility of the standard “X” close button on the popup.
  - **Effect of changing this setting:**
    - *Enabled:* A close button appears, allowing customers to easily dismiss the popup.
    - *Disabled:* No “X” button. Customers will need to click outside the popup or press ESC (if enabled) to close it.
  - **Recommended value:** YES, for good user experience.
  - **Merchant scenario / example:** You want to make it easy for customers to close the popup, so you enable the close button.
- **Allow Closing by Clicking Outside:**

  - **What this setting does:** Determines if clicking anywhere on the overlay (outside the popup content) will close the popup.
  - **Effect of changing this setting:**
    - *Enabled:* Clicking the overlay closes the popup.
    - *Disabled:* Only the close button or ESC key will dismiss the popup.
  - **Recommended value:** YES, for good user experience.
  - **Merchant scenario / example:** You want to provide multiple ways for customers to dismiss the popup, so you enable this.
- **Allow Closing by ESC Key:**

  - **What this setting does:** Determines if pressing the ESC key on the keyboard will close the popup.
  - **Effect of changing this setting:**
    - *Enabled:* ESC key closes the popup.
    - *Disabled:* ESC key has no effect on the popup.
  - **Recommended value:** YES, for good user experience.
  - **Merchant scenario / example:** You want to provide an accessible way for customers to dismiss the popup, so you enable this.
- **Custom CSS:**

  - **What this setting does:** Allows you to add your own custom CSS rules to further style the popup or its content. This is for advanced users or developers.
  - **Effect of changing this setting:** Any valid CSS rules you add here will be applied to the popup, potentially overriding default styles.
  - **Recommended value:** Leave empty unless you have specific styling needs.
  - **Merchant scenario / example:** You want to change the font size of a specific paragraph inside your popup, or add a unique shadow effect not available in other settings. You would add the CSS here.

**Advanced Settings Tab (or similar grouping if available)**

- **Popup Animation (Entry Effect):**

  - **What this setting does:** Selects an animation effect for when the popup appears on screen.
  - **Effect of changing this setting:** The popup will animate into view using the chosen effect (e.g., fade in, slide down, zoom).
  - **Recommended value:** “Fade In” or “Slide Down” are generally subtle and professional.
  - **Merchant scenario / example:** You want your popup to smoothly appear rather than just popping up instantly, so you choose “Fade In”.
- **Popup Animation (Exit Effect):**

  - **What this setting does:** Selects an animation effect for when the popup disappears from screen.
  - **Effect of changing this setting:** The popup will animate out of view using the chosen effect.
  - **Recommended value:** “Fade Out” or “Slide Up” to match the entry effect.
  - **Merchant scenario / example:** To maintain a consistent and smooth user experience, you choose “Fade Out” as the exit animation.
- **Display Popup on Specific Pages (URLs):**

  - **What this setting does:** Allows you to specify exact URLs or URL patterns where the popup should (or should not) appear.
  - **Effect of changing this setting:** The popup will only show on the pages matching your criteria, or be hidden from them.
  - **Recommended value:** Use this to target your popups effectively.
  - **Merchant scenario / example:** You have a special offer for a specific product category. You would enter the URL of that category page here to ensure the popup only appears for relevant visitors.
- **Do Not Display Popup on Specific Pages (URLs):**

  - **What this setting does:** Allows you to specify exact URLs or URL patterns where the popup should *not* appear.
  - **Effect of changing this setting:** The popup will be hidden from the pages matching your criteria.
  - **Recommended value:** Use this to avoid showing popups on sensitive pages like checkout or login.
  - **Merchant scenario / example:** You don’t want the popup to interrupt the checkout process. You would add your checkout page URL (e.g., `/order`) here.
- **Display Popup for Specific Customer Groups:**

  - **What this setting does:** Restricts the popup’s visibility to certain customer groups (e.g., Visitors, Customers, Guests, Wholesalers).
  - **Effect of changing this setting:** Only customers belonging to the selected groups will see the popup.
  - **Recommended value:** Depends on your target audience. “Visitors” and “Guests” are common for lead generation.
  - **Merchant scenario / example:** You have a special offer exclusively for your registered customers. You would select “Customers” here.
- **Display Popup for Specific Languages:**

  - **What this setting does:** Restricts the popup’s visibility to customers browsing in specific languages.
  - **Effect of changing this setting:** Only customers using the selected language will see the popup.
  - **Recommended value:** All languages, or specific ones if your popup content is language-dependent.
  - **Merchant scenario / example:** You have a popup with content only translated into English and French. You would select “English” and “French” here.
- **Display Popup for Specific Currencies:**

  - **What this setting does:** Restricts the popup’s visibility to customers browsing with specific currencies.
  - **Effect of changing this setting:** Only customers using the selected currency will see the popup.
  - **Recommended value:** All currencies, or specific ones if your popup content is currency-dependent.
  - **Merchant scenario / example:** You have a special offer only valid for customers paying in USD. You would select “USD” here.
- **Display Popup for Specific Countries:**

  - **What this setting does:** Restricts the popup’s visibility to customers from specific countries.
  - **Effect of changing this setting:** Only customers detected as being from the selected countries will see the popup.
  - **Recommended value:** All countries, or specific ones for geo-targeted campaigns.
  - **Merchant scenario / example:** You’re running a promotion exclusively for customers in France. You would select “France” here.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration Page** | Enable Popup Pro | YES | Master switch for activating/deactivating the popup. |
|  | Popup Content (HTML Editor) | (Empty) | Design what appears inside the popup (text, images, links). |
|  | Popup Width (px) | 600-800px | Sets the horizontal size of the popup. |
|  | Popup Height (px) | auto (empty) | Sets the vertical size of the popup, or auto-adjusts. |
|  | Display Popup On | Exit Intent / Page Load (3-5s delay) | Determines the trigger for the popup appearance. |
|  | Delay Before Popup Appears (seconds) | 3-5 | Time delay before popup shows (if “Page Load” selected). |
|  | Popup Frequency (days) | 7-30 | How often a returning customer sees the popup. |
|  | Show Popup On Mobile Devices | YES | Controls popup visibility on phones/tablets. |
|  | Popup Background Color | #FFFFFF (White) | Color of the popup window’s background. |
|  | Popup Border Color | Transparent / Light Grey | Color of the popup’s border. |
|  | Popup Border Width (px) | 0-2 | Thickness of the popup’s border. |
|  | Popup Border Radius (px) | 0-10 | Roundness of the popup’s corners. |
|  | Overlay Background Color | #000000 (Black) | Color of the semi-transparent background behind the popup. |
|  | Overlay Opacity (0-100) | 50-80 | Transparency level of the overlay. |
|  | Show Close Button | YES | Displays the ‘X’ button to close the popup. |
|  | Allow Closing by Clicking Outside | YES | Allows closing by clicking on the overlay. |
|  | Allow Closing by ESC Key | YES | Allows closing by pressing the ESC key. |
|  | Custom CSS | (Empty) | Add custom CSS for advanced styling. |
|  | Popup Animation (Entry Effect) | Fade In / Slide Down | Visual effect when the popup appears. |
|  | Popup Animation (Exit Effect) | Fade Out / Slide Up | Visual effect when the popup disappears. |
|  | Display Popup on Specific Pages (URLs) | (Empty) | Show popup only on specified URLs. |
|  | Do Not Display Popup on Specific Pages (URLs) | (Empty) | Hide popup from specified URLs (e.g., checkout). |
|  | Display Popup for Specific Customer Groups | All | Target popup to specific customer types. |
|  | Display Popup for Specific Languages | All | Target popup to specific languages. |
|  | Display Popup for Specific Currencies | All | Target popup to specific currencies. |
|  | Display Popup for Specific Countries | All | Target popup to specific countries. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My popup isn’t showing up at all. What should I check first?**
**A1:**

1. **Is the module enabled?** Go to **Modules > Module Manager** and ensure “Prestashop Popup Pro” is installed and enabled.
2. **Is “Enable Popup Pro” set to YES in the module configuration?** This is the master switch.
3. **Check your “Display Popup On” settings:** If it’s set to “Time Delay,” ensure the delay isn’t too long. If “Exit Intent,” make sure you’re actually triggering it correctly (moving mouse out of browser window).
4. **Clear your PrestaShop cache:** Go to **Advanced Parameters > Performance**, scroll down, and click “Clear cache.” Sometimes old cached files prevent new module settings from taking effect.
5. **Check for conflicts:** Temporarily disable other popup or overlay modules to see if there’s a conflict.

**Q2: My popup looks strange or broken on mobile devices.**
**A2:**

1. **Is “Show Popup On Mobile Devices” enabled?** If not, it won’t show at all.
2. **Review your “Popup Content”:** Complex HTML, very large images, or content not designed for small screens can break. Try simplifying the content or using smaller, optimized images.
3. **Check “Popup Width” and “Popup Height”:** While the module is responsive, sometimes fixed pixel values can cause issues on very small screens. Consider leaving “Popup Height” empty for `auto`.
4. **Custom CSS:** If you’ve added custom CSS, it might not be mobile-friendly. Test your CSS using browser developer tools (inspect element) on different screen sizes.

**Q3: The popup appears too often for my customers. How can I control this?**
**A3:**

1. **Adjust “Popup Frequency (days)”:** This is the key setting. A higher number means customers will see the popup less often. For example, setting it to `30` means they’ll only see it once a month after closing it.
2. **Consider your “Display Popup On” setting:** If it’s “Page Load” with a short delay, it might feel more intrusive than “Exit Intent.”

**Q4: I want to translate my popup content into multiple languages. How do I do that?**
**A4:** The “Popup Content” HTML editor should support PrestaShop’s multi-language input. When editing the content, look for language tabs or dropdowns (usually at the top right of the editor) to switch between languages and provide different content for each. Ensure you have the desired languages installed in PrestaShop. If the editor doesn’t show language tabs, you might need to input the content for each language manually by switching your back office language.

**Q5: The popup content is too small/large, or the font is wrong.**
**A5:**

1. **Use the HTML editor:** The built-in HTML editor usually provides options to change font size, color, and other styling for your text.
2. **Custom CSS:** For more precise control, use the “Custom CSS” field. For example, to change the font size of all text in the popup, you might add:

   ```
   .popuppro-content p { font-size: 16px !important;}
   ```

   (You might need to inspect the popup in your browser to find the correct CSS selectors like `.popuppro-content`).

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview of the Prestashop Popup Pro module, intended for developers, webmasters, and technical agencies.

### 4.1 Architecture Overview

The Prestashop Popup Pro module follows a standard PrestaShop module architecture, primarily leveraging the `Module` class for its core functionality and `ModuleFrontController` for AJAX interactions. It heavily relies on JavaScript for front-office display logic, animations, and event handling (like exit intent). Configuration is managed through the `getContent()` method in the main module file, storing settings in `ps_configuration`. The module integrates a Smarty Templates Manager for flexible content creation and a color picker for UI customization.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `popuppro/controllers/front/index.php`
    - **Class Name:** `PopupproIndexModuleFrontController` (likely, based on file naming convention)
    - **Parent Class:** `ModuleFrontController`
    - **Responsibility:** This controller might serve as a general entry point or a fallback for module-related front-office requests. It could be responsible for initial data loading or rendering a basic module view if no specific action is requested.
  - `popuppro/controllers/front/popuploader.php`
    - **Class Name:** `PopupproPopuploaderModuleFrontController`
    - **Parent Class:** `ModuleFrontController`
    - **Responsibility:** This controller is highly likely responsible for loading the popup content and configuration dynamically via AJAX. When a user visits a page, a JavaScript script would send an AJAX request to this controller to fetch the popup’s HTML, styling, and behavioral settings based on the module’s configuration. It would return a JSON or HTML payload.
  - `popuppro/controllers/front/popupstat.php`
    - **Class Name:** `PopupproPopupstatModuleFrontController`
    - **Parent Class:** `ModuleFrontController`
    - **Responsibility:** This controller is designed to handle statistical data related to the popup. It would receive AJAX requests from the front-office JavaScript to record popup impressions, clicks on the close button, or other interactions, allowing the module to track performance (though a dedicated stats view is not explicitly listed in admin controllers, this data might be stored for future use or internal logging).
- **Back-Office Admin Controllers**: None explicitly listed, indicating that all administration is handled via the `getContent()` method of the main module file.

### 4.3 Core Classes & Models (`classes/`)

No custom classes or `ObjectModel` definitions are listed in the `classes/` directory. This suggests that the module primarily stores its configuration directly in the `ps_configuration` table using `Configuration::updateValue()` and `Configuration::get()`, and does not manage complex custom data entities requiring dedicated database tables or `ObjectModel` mapping.

### 4.4 JavaScript Assets (`views/js/`)

- `popuppro/js/popup-engine.js`:
  - **Scope:** Front-office.
  - **Detail:** This is likely the core JavaScript file responsible for the fundamental mechanics of the popup. It would handle creating the popup DOM elements (the overlay, the popup container, the close button), injecting the content, managing animations (entry/exit effects), and positioning the popup on the screen. It probably defines the main `PopupPro` object or similar.
- `popuppro/js/popup-events.js`:
  - **Scope:** Front-office.
  - **Detail:** This script would manage all the event listeners that trigger the popup. This includes:
    - `DOMContentLoaded` or `window.load` for initial setup.
    - `setTimeout` for time-delayed popups.
    - Scroll event listeners for scroll-triggered popups.
    - `mouseleave` or similar events on `document.body` for exit-intent detection.
    - Click listeners for the close button and outside-click closing.
    - `keyup` listener for the ESC key.
    - AJAX calls to `popuploader.php` to fetch content and `popupstat.php` to record events.
- `popuppro/js/popup-scripts.js`:
  - **Scope:** Front-office.
  - **Detail:** This file might contain additional, perhaps more specific, scripts related to popup behavior or interactions, possibly handling form submissions within the popup, dynamic content updates, or integration with other front-office elements.
- `popuppro/js/script.js`:
  - **Scope:** Front-office/Back-office (generic name, could be either).
  - **Detail:** Given its generic name, this could be a general utility script, or it might contain initialization logic for the popup on the front-office, or even some minor back-office scripting if it’s loaded there. It’s common for modules to have a `script.js` for general purpose code.
- `popuppro/js/tinymce16-force-urls.inc.js`, `popuppro/js/tinymce16.inc.js`:
  - **Scope:** Back-office.
  - **Detail:** These files are related to the TinyMCE rich text editor, specifically version 1.6. They are included to provide the HTML editor functionality for the “Popup Content” field in the module’s back-office configuration. `tinymce16-force-urls.inc.js` likely handles ensuring URLs are correctly formatted within the editor.
- `popuppro/jscolor/jscolor.js`:
  - **Scope:** Back-office.
  - **Detail:** This is the JavaScript library for the color picker functionality used in the back-office configuration (e.g., for Popup Background Color, Border Color, Overlay Color). It provides the interactive color selection interface.
- `popuppro/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`:
  - **Scope:** Back-office.
  - **Detail:** This script is part of an internal library for managing Smarty templates within the module’s configuration. It likely provides functionality for previewing templates, selecting them, or dynamically inserting template-based content into the HTML editor.

### 4.5 CSS Stylesheets (`views/css/`)

- `popuppro/css.css`:
  - **Scope:** Front-office.
  - **Detail:** This is likely the primary stylesheet for the front-office popup, defining its default appearance: positioning, sizing, border, shadow, close button styling, and potentially responsive adjustments.
  - **Key Selectors:** `.popuppro-overlay`, `.popuppro-popup`, `.popuppro-close-btn`, `.popuppro-content`.
- `popuppro/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`:
  - **Scope:** Back-office.
  - **Detail:** Stylesheets for the Smarty Templates Manager interface within the module’s back-office configuration. It would style the template selection, preview areas, and related UI elements.
- `popuppro/popuppro.css`:
  - **Scope:** Front-office.
  - **Detail:** Similar to `css.css`, this might contain additional or specific styles for the popup, potentially for different animation states or specific content elements. There might be some overlap or separation of concerns between `css.css` and `popuppro.css`.
  - **Key Selectors:** Likely similar to `css.css`, focusing on the main popup components.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**: (None explicitly listed in `views/templates/hook/`, but `views/header.tpl` is likely hooked)

  - `popuppro/views/header.tpl`:
    - **Hook:** `displayHeader`
    - **Output:** This template is almost certainly hooked into `displayHeader`. It would be responsible for injecting the necessary JavaScript and CSS files into the `<head>` section of the front-office, and potentially some initial HTML structure or configuration data for the JavaScript to use.
  - `popuppro/views/header_address.tpl`, `popuppro/views/header_carrier.tpl`:
    - **Hook:** Potentially `displayHeader` or other specific hooks related to address/carrier information.
    - **Output:** These seem like specialized header templates, possibly for displaying dynamic content related to customer address or carrier information *within* a popup, or for specific popup scenarios. Their exact use would depend on module logic.
  - `popuppro/views/popup.tpl`:
    - **Hook:** Not directly hooked, but rendered by JavaScript.
    - **Output:** This is the main template for the front-office popup structure. It defines the HTML for the overlay, the popup container, the close button, and a placeholder for the dynamic content loaded via AJAX.
- **Admin templates (`views/templates/admin/`)**:

  - `popuppro/views/admin/admin.tpl`:
    - **Purpose:** The main template for the module’s configuration page in the back office. It would contain the overall layout, tabs, and structure for the settings forms.
  - `popuppro/views/admin/boscript.tpl`:
    - **Purpose:** Back-office JavaScript template. This likely injects specific JavaScript code needed for the admin configuration page, such as initializing TinyMCE, the color picker, or custom form validation.
  - `popuppro/views/admin/popup_preview.tpl`:
    - **Purpose:** Template for displaying a live or simulated preview of the popup within the back-office configuration, allowing merchants to see changes as they make them.
  - `popuppro/views/admin/presets.tpl`:
    - **Purpose:** Template for managing or displaying predefined popup templates or styles.
  - `popuppro/views/admin/shadow_editor.tpl`:
    - **Purpose:** A specialized template for configuring shadow effects for the popup, potentially offering advanced controls beyond simple color/opacity.
  - `popuppro/views/admin/stats.tpl`:
    - **Purpose:** If the module collects statistics (as suggested by `popupstat.php`), this template would be used to display those statistics in the back office.
  - `popuppro/views/templates/admin/_configure/helpers/form/form.tpl`:
    - **Purpose:** This is a standard PrestaShop override template for the `HelperForm` class, specifically for the module’s configuration form. It allows the module to customize how its settings form is rendered, potentially adding custom fields or layout.
- **SmartyTemplatesManager Library Templates (`popuppro/lib/smartyTemplatesManager/tpl/` and `views/`)**:

  - `popuppro/lib/smartyTemplatesManager/tpl/cartMini.tpl`, `example.tpl`, `freeShippingBar.tpl`, `helloCustomer.tpl`, `lastOrder.tpl`, `productHighlight.tpl`, `showReachedQtyInCart.tpl`:
    - **Purpose:** These are predefined content templates that the merchant can select or use as a starting point for their popup content. They offer common use cases like mini-cart displays, free shipping announcements, welcome messages, last order details, product highlights, or quantity reached in cart messages. These would be rendered dynamically into the main popup content area.
  - `popuppro/lib/smartyTemplatesManager/views/buttonManager.tpl`, `buttonManagerNoJs.tpl`, `createTemplateForm.tpl`, `editTemplateForm.tpl`, `mainForm.tpl`, `selectInput.tpl`:
    - **Purpose:** These templates are part of the internal Smarty Templates Manager library, used within the back-office configuration to manage and interact with the content templates. They provide UI for creating, editing, and selecting these predefined content blocks.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not appear to create custom SQL tables.
  - All configuration settings are stored in the `ps_configuration` table. Key configuration names would typically follow the pattern `POPUPPRO_SETTING_NAME`. Examples include:
    - `POPUPPRO_ENABLED`
    - `POPUPPRO_CONTENT` (likely multi-language)
    - `POPUPPRO_WIDTH`
    - `POPUPPRO_DISPLAY_ON`
    - `POPUPPRO_FREQUENCY`
    - `POPUPPRO_BG_COLOR`
    - …and so on for all configuration options.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Executed in the `<head>` section of every front-office page. | Injects necessary CSS and JavaScript files for the popup to function, and potentially initializes global JavaScript variables or configuration data. |
| `displayRightColumn` | Executed in the right column of pages (if enabled by theme). | While the module description mentions “Columns,” it’s less likely for a full-screen popup. If used, it might render a trigger for the popup or a smaller, non-overlay element. |
| `displayLeftColumn` | Executed in the left column of pages (if enabled by theme). | Similar to `displayRightColumn`, less likely for the main popup, but could be used for a trigger. |
| `displayFooter` | Executed at the bottom of every front-office page, before the closing `</body>` tag. | Could be used to inject JavaScript that needs to run after the DOM is fully loaded, or to place the popup HTML structure at the very end of the document. |
| `displayProductAdditionalInfo` (or similar product page hook) | Executed on the product page, typically below the main product details. | If the module supports product-specific popups, it might use this hook to inject a trigger or specific popup logic relevant to the product. |
| `actionFrontControllerSetMedia` | Executed when a front controller sets its media (CSS/JS). | A common hook for modules to register their assets (CSS/JS) efficiently, ensuring they are loaded only when needed. |

## 5. Official Support & Updates

For official support, module updates, and any further assistance with your Prestashop Popup Pro module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our dedicated support team is ready to help you maximize the potential of your module.
