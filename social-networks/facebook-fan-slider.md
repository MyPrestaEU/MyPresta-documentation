---
title: "Facebook Fan Slider - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Facebook Fan Slider PrestaShop module by MyPresta.eu."
sidebar:
  label: "Facebook Fan Slider - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Facebook Fan Slider Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-fan-slider.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/facebook-fan-slider/)
>
> ---


# Facebook Fan Slider

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required for PrestaShop itself and generally available on all modern hosting environments. No special server configurations are needed beyond a standard PrestaShop setup.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

To access the module’s settings, go to **Modules > Module Manager**, search for “Facebook Fan Slider”, and click the “Configure” button.

Here’s a detailed breakdown of each setting:

- **Facebook Page URL (fs\_url)**

  - **What this setting does:** This is the most crucial setting. It tells the module which specific Facebook Page to display in the sliding box.
  - **Effect of changing this setting:**
    - *When set to your Facebook Page URL:* The module will fetch and display the Like Box/Page Plugin for that exact page.
    - *When left empty or set incorrectly:* The module will either not display the Facebook content, or it will show an error, as it won’t know which page to connect to.
  - **Recommended value:** Enter the full URL of your Facebook Page (e.g., `https://www.facebook.com/MyPresta.eu`).
  - **Merchant scenario / example:** If your business page is `https://www.facebook.com/MyAwesomeShop`, you would enter that URL here.
- **Width (fs\_width)**

  - **What this setting does:** Controls the width of the Facebook Like Box/Page Plugin *inside* the sliding panel, in pixels.
  - **Effect of changing this setting:**
    - *When set to a specific pixel value (e.g., 280):* The Facebook content will be exactly that wide.
    - *When set to a smaller value:* The content might appear cramped or some elements might be cut off.
    - *When set to a larger value:* The content will expand, but ensure it doesn’t exceed the screen width or look disproportionate.
  - **Recommended value:** Start with `280` or `300` pixels. Adjust based on how much content you display (e.g., if showing posts, you might need more width).
  - **Merchant scenario / example:** You want the sliding box to be wide enough to clearly show your page’s cover photo and the “Like” button without being too bulky.
- **Height (fs\_height)**

  - **What this setting does:** Controls the height of the Facebook Like Box/Page Plugin *inside* the sliding panel, in pixels.
  - **Effect of changing this setting:**
    - *When set to a specific pixel value (e.g., 400):* The Facebook content will be exactly that tall.
    - *When set to a smaller value:* Content might be cut off, requiring users to scroll within the box.
    - *When set to a larger value:* The box will be taller, potentially taking up more screen space.
  - **Recommended value:** Start with `400` or `500` pixels. If you enable “Show Posts”, you’ll likely need more height (e.g., `600-700px`) to display a few posts without excessive scrolling.
  - **Merchant scenario / example:** You want to show a few recent posts from your Facebook page, so you increase the height to `600px` to make them visible.
- **Hide Cover Photo (fs\_hide\_cover)**

  - **What this setting does:** Determines whether your Facebook Page’s large cover photo is displayed at the top of the Like Box/Page Plugin.
  - **Effect of changing this setting:**
    - *When enabled (checked):* The cover photo will not be shown, making the Like Box more compact.
    - *When disabled (unchecked):* The cover photo will be displayed, making the Like Box visually richer but also taller.
  - **Recommended value:** *Disabled* (unchecked) if you want a more visually appealing box. *Enabled* (checked) if you need to save vertical space.
  - **Merchant scenario / example:** You have a beautiful cover photo on Facebook and want to showcase it, so you leave this unchecked. If you’re tight on space, you might check it.
- **Show Friends’ Faces (fs\_show\_facepile)**

  - **What this setting does:** Controls whether the profile pictures of friends who already like your page are displayed below the “Like” button.
  - **Effect of changing this setting:**
    - *When enabled (checked):* A row of profile pictures of mutual friends who like your page will appear, adding social proof.
    - *When disabled (unchecked):* These profile pictures will not be shown.
  - **Recommended value:** *Enabled* (checked). Social proof can encourage others to like your page.
  - **Merchant scenario / example:** You want to leverage social proof to encourage new likes, so you enable this to show friends who already like your page.
- **Show Posts (fs\_show\_posts)**

  - **What this setting does:** Determines whether recent posts from your Facebook Page’s timeline are displayed within the Like Box/Page Plugin.
  - **Effect of changing this setting:**
    - *When enabled (checked):* Your latest Facebook posts will appear, making the box more dynamic and engaging. You’ll likely need to increase the `Height` setting.
    - *When disabled (unchecked):* Only the basic “Like Page” functionality and friend faces (if enabled) will be shown.
  - **Recommended value:** *Enabled* (checked) if you regularly post engaging content and want to showcase it. Remember to adjust `Height`.
  - **Merchant scenario / example:** You frequently post about new products and promotions on Facebook. Enabling this allows customers to see your latest updates directly from your store.
- **Hide Call To Action (fs\_hide\_cta)**

  - **What this setting does:** Controls the visibility of the “Call To Action” button (e.g., “Send Message”, “Shop Now”) that you might have configured on your Facebook Page.
  - **Effect of changing this setting:**
    - *When enabled (checked):* The CTA button will not be displayed in the Like Box.
    - *When disabled (unchecked):* The CTA button (if configured on your Facebook Page) will be visible.
  - **Recommended value:** *Disabled* (unchecked) if your CTA is relevant to your store visitors. *Enabled* (checked) if you prefer to only focus on getting likes.
  - **Merchant scenario / example:** Your Facebook page has a “Shop Now” button. You want customers to use it, so you leave this unchecked.
- **Small Header (fs\_small\_header)**

  - **What this setting does:** Uses a smaller version of the header for the Facebook Like Box/Page Plugin.
  - **Effect of changing this setting:**
    - *When enabled (checked):* The header area of the Like Box will be more compact, saving vertical space.
    - *When disabled (unchecked):* The standard, larger header will be used.
  - **Recommended value:** *Enabled* (checked) if you want a more streamlined look or need to save space.
  - **Merchant scenario / example:** You want the sliding box to be as compact as possible without hiding essential information, so you enable the small header.
- **Slide on (fanslider\_slideon)**

  - **What this setting does:** Determines the interaction method that makes the Facebook box slide out.
  - **Effect of changing this setting:**
    - *When set to “Click”:* The box will only slide out when the customer explicitly clicks the tab.
    - *When set to “Hover”:* The box will slide out when the customer moves their mouse cursor over the tab.
  - **Recommended value:** “Click” is generally less intrusive and prevents accidental pop-outs. “Hover” can be more immediate but might annoy some users.
  - **Merchant scenario / example:** You want to ensure the slider only appears when a customer actively chooses to see it, so you set it to “Click”.
- **Position (fs\_pos)**

  - **What this setting does:** Controls where the sliding tab appears on your website.
  - **Effect of changing this setting:**
    - *When set to “Left”:* The tab will appear on the left side of the browser window.
    - *When set to “Right”:* The tab will appear on the right side of the browser window.
  - **Recommended value:** “Left” or “Right”, depending on your theme’s layout and where it causes the least interference with other elements.
  - **Merchant scenario / example:** Your theme has a live chat widget on the right, so you set the Facebook Fan Slider to “Left” to avoid conflicts.
- **Background Color (fs\_bg\_color)**

  - **What this setting does:** Sets the background color of the sliding panel itself (not the Facebook content, but the container it slides in).
  - **Effect of changing this setting:**
    - *When set to a specific color (e.g., #FFFFFF for white, #0000FF for blue):* The background of the sliding box will change to that color.
  - **Recommended value:** A color that matches your store’s branding or a neutral color like white (`#FFFFFF`) or light gray (`#F0F0F0`).
  - **Merchant scenario / example:** Your brand uses a specific shade of blue. You enter the hex code for that blue to ensure the slider matches your brand identity.
- **Border Color (fs\_br\_color)**

  - **What this setting does:** Sets the color of the border around the sliding panel.
  - **Effect of changing this setting:**
    - *When set to a specific color (e.g., #CCCCCC for light gray):* The border of the sliding box will change to that color.
  - **Recommended value:** A subtle color that complements your background color, or a color that matches your brand.
  - **Merchant scenario / example:** You want a subtle border around the slider, so you choose a light gray color (`#DDDDDD`).
- **Language (fs\_langarray)**

  - **What this setting does:** Allows you to select the language for the Facebook Like Box/Page Plugin. This ensures the “Like Page” button and other Facebook-generated text are in the correct language for your audience.
  - **Effect of changing this setting:**
    - *When set to a specific language (e.g., “en\_US” for English, “fr\_FR” for French):* The Facebook plugin will render in that language.
  - **Recommended value:** Select the primary language of your store or your target audience.
  - **Merchant scenario / example:** Your store primarily serves customers in France, so you select “fr\_FR” to display the Facebook content in French.
- **Adapt Container Width (fs\_adapt\_container\_width)**

  - **What this setting does:** Tells the Facebook Page Plugin to adapt its width to the width of its parent container (the sliding box).
  - **Effect of changing this setting:**
    - *When enabled (checked):* The Facebook content will try to fill the `Width` you specified for the sliding box, making it responsive within that container.
    - *When disabled (unchecked):* The Facebook content might use its default width, potentially leading to overflow or empty space if it doesn’t match your `Width` setting.
  - **Recommended value:** *Enabled* (checked) for better responsiveness and to ensure the Facebook content fits well within your specified `Width`.
  - **Merchant scenario / example:** You want the Facebook content to automatically adjust to the width of your slider, so you enable this for a cleaner look.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Facebook Page URL (fs\_url) | Your Facebook Page URL | Specifies which Facebook page to display. **CRITICAL!** |
| Module Configuration | Width (fs\_width) | 280-300px | Sets the width of the Facebook content inside the slider. |
| Module Configuration | Height (fs\_height) | 400-500px (more if showing posts) | Sets the height of the Facebook content inside the slider. |
| Module Configuration | Hide Cover Photo (fs\_hide\_cover) | Disabled (unchecked) | Shows/hides the large cover photo from your Facebook page. |
| Module Configuration | Show Friends’ Faces (fs\_show\_facepile) | Enabled (checked) | Displays profile pictures of friends who like your page (social proof). |
| Module Configuration | Show Posts (fs\_show\_posts) | Enabled (checked) | Displays recent posts from your Facebook timeline. Requires more height. |
| Module Configuration | Hide Call To Action (fs\_hide\_cta) | Disabled (unchecked) | Shows/hides the CTA button configured on your Facebook page. |
| Module Configuration | Small Header (fs\_small\_header) | Enabled (checked) | Uses a more compact header for the Facebook plugin. |
| Module Configuration | Slide on (fanslider\_slideon) | Click | Determines if the box slides out on “Click” or “Hover”. “Click” is less intrusive. |
| Module Configuration | Position (fs\_pos) | Left / Right | Sets the side of the screen where the tab appears. |
| Module Configuration | Background Color (fs\_bg\_color) | Matches theme / White (#FFFFFF) | Sets the background color of the sliding panel. |
| Module Configuration | Border Color (fs\_br\_color) | Subtle gray (#DDDDDD) | Sets the border color of the sliding panel. |
| Module Configuration | Language (fs\_langarray) | Your store’s primary language | Sets the language for the Facebook plugin text. |
| Module Configuration | Adapt Container Width (fs\_adapt\_container\_width) | Enabled (checked) | Makes the Facebook content responsive to the slider’s width. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The Facebook slider isn’t appearing on my store. What should I check first?**
A1:

- **Module Enabled:** Go to **Modules > Module Manager** and ensure the “Facebook Fan Slider” module is installed and enabled.
- **Facebook Page URL:** Double-check the `Facebook Page URL (fs_url)` in the module configuration. Make sure it’s the *exact* URL of your Facebook page (e.g., `https://www.facebook.com/MyPresta.eu`) and not just your profile or a group.
- **Cache:** Clear your PrestaShop cache (Go to **Advanced Parameters > Performance**, then click “Clear cache” in the top right). Also, clear your browser’s cache.
- **Theme Conflicts:** Temporarily switch to the default PrestaShop theme to see if the slider appears. If it does, your custom theme might have CSS or JavaScript conflicts.

**Q2: The Facebook content inside the slider looks cut off or too small/large.**
A2:

- **Width & Height:** Adjust the `Width (fs_width)` and `Height (fs_height)` settings in the module configuration. If you’re showing posts, you’ll definitely need more height.
- **Adapt Container Width:** Ensure `Adapt Container Width (fs_adapt_container_width)` is enabled (checked). This helps the Facebook content fit responsively within the slider.
- **Small Header:** If you’re trying to save vertical space, try enabling `Small Header (fs_small_header)`.

**Q3: The language of the Facebook Like Box is incorrect.**
A3:

- **Language Setting:** Go to the module configuration and verify the `Language (fs_langarray)` setting. Select the correct language code for your target audience (e.g., `en_US` for US English, `fr_FR` for French).

**Q4: I changed settings, but nothing is happening on the front office.**
A4:

- **Save Changes:** Always click the “Save” button after making any changes in the module configuration.
- **Clear Cache:** PrestaShop heavily relies on caching. After saving, always clear your PrestaShop cache (**Advanced Parameters > Performance > Clear cache**) and your browser’s cache. This is the most common reason for changes not appearing immediately.

**Q5: The slider is overlapping with another element on my site.**
A5:

- **Position:** Adjust the `Position (fs_pos)` setting (Left or Right) to see if moving the slider to the other side resolves the conflict.
- **CSS Adjustments (Developer needed):** If the issue persists, it might require custom CSS adjustments to either the slider or the conflicting element. This would typically involve a webmaster or developer.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The Facebook Fan Slider module (`fanslider`) is a standard PrestaShop module implementing the `Module` class. It primarily leverages PrestaShop’s hook system to inject its HTML, CSS, and JavaScript into the front-office. The core functionality revolves around displaying the official Facebook Page Plugin within a custom sliding UI element. Configuration is managed via the `getContent()` method, storing settings in `ps_configuration`. The module does not use custom database tables or `ObjectModel` classes.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. All front-office rendering and logic are handled directly within the main module file (`fanslider.php`) via hooks and injected JavaScript.
- **Back-Office Admin Controllers**: None. Configuration is handled by the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)

- No custom classes or `ObjectModel` definitions are present in the `classes/` directory. The module’s logic is self-contained within `fanslider/fanslider.php`.

### 4.4 JavaScript Assets (`views/js/`)

The module includes several JavaScript files, primarily for the sliding animation and color picker functionality.

- `fanslider/jscolor/jscolor.js`

  - **Scope:** Back-office (used in `getContent()` for color picker inputs).
  - **Responsibility:** Provides a JavaScript color picker utility, allowing administrators to visually select colors for the slider’s background and border. It attaches to input fields with the class `jscolor`.
- `fanslider/js/fanslider-click.js`

  - **Scope:** Front-office.
  - **Responsibility:** This script handles the “click” interaction for the slider. It listens for click events on the slider tab and toggles the visibility and position of the main slider container (`#fanslider`). It also manages the `fanslider_open` class to control the open/closed state.
- `fanslider/js/fanslider.js`

  - **Scope:** Front-office.
  - **Responsibility:** This is likely the main script for the slider’s animation and initial setup. It handles the “hover” interaction if configured, and potentially calculates initial positions or applies CSS transformations for the sliding effect. It interacts with the `#fanslider` and `#fanslider_tab` elements.
- `fanslider/script.js`

  - **Scope:** Front-office.
  - **Responsibility:** This script likely contains the core logic for initializing the Facebook Page Plugin (FB.init and FB.XFBML.parse) and potentially other general setup or event binding related to the slider’s behavior. It ensures the Facebook SDK is loaded and the plugin is rendered correctly.

### 4.5 CSS Stylesheets (`views/css/`)

The module does not explicitly list CSS files in `views/css/`. Styling for the slider is likely embedded directly within the `fanslider.php` file’s `hookDisplayHeader` method or within the `rightcolumn.tpl` template, or dynamically generated based on configuration. Developers should inspect the generated HTML and the main module file for inline styles or `<style>` blocks.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `fanslider/views/templates/hook/rightcolumn.tpl`
    - **Hook:** This template is primarily designed to be rendered in a hook that allows for content injection into the page, such as `displayFooter` or `displayHeader` (even though its name suggests `displayRightColumn`, the module’s implementation places it as a fixed element).
    - **Visual Block:** This template outputs the main HTML structure for the Facebook Fan Slider. It typically includes:
      - The main container for the slider (`#fanslider`).
      - The clickable tab (`#fanslider_tab`).
      - The container for the Facebook Page Plugin (`<div class="fb-page">`).
      - It receives configuration variables from the module to dynamically set attributes for the Facebook Page Plugin (e.g., `data-href`, `data-width`, `data-height`, `data-hide-cover`, `data-show-facepile`, `data-show-posts`, `data-hide-cta`, `data-small-header`, `data-adapt-container-width`).
      - It also includes the necessary `div` for the Facebook SDK to render the plugin.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any custom database tables.
  - All configuration settings are stored in the `ps_configuration` table using keys prefixed with `FS_` or `FANSIDER_` (e.g., `FS_WIDTH`, `FANSIDER_SLIDEON`).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Executed in the `<head>` section of every page. | Injects necessary CSS and JavaScript files, and potentially the Facebook SDK initialization script. Also, may output inline styles based on configuration. |
| `displayFooter` | Executed at the bottom of every page, before the closing `</body>` tag. | Renders the main HTML structure of the Facebook Fan Slider (from `rightcolumn.tpl`) and ensures the Facebook SDK is loaded and the Page Plugin is initialized after the DOM is ready. This is where the visual component is added to the page. |

## 5. Official Support & Updates

For the latest versions, updates, and professional support for the Facebook Fan Slider module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have.
