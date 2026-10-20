---
title: "Facebook Like Box Free - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Facebook Like Box Free PrestaShop module by MyPresta.eu."
sidebar:
  label: "Facebook Like Box Free - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Facebook Like Box Free Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-like-box-free.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/facebook-like-box-free/)
>
> ---


# Facebook Like Box Free

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required by PrestaShop itself and are sufficient for this module. No special hosting requirements beyond a standard PrestaShop setup.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main and only configuration screen for the Facebook Like Box Free module. You’ll find all settings here to control its appearance and behavior.

| Setting / Option | What this setting does | Effect of changing this setting | Recommended value | Merchant scenario / example |
| --- | --- | --- | --- | --- |
| **Enabled** / **Disabled** | Controls whether the Facebook Like Box is active and visible on your store. | *When Enabled:* The Like Box will appear on your store in the chosen position. *When Disabled:* The Like Box will be hidden from your store. | **Enabled** | You want to start promoting your Facebook page. |
| **Position** | Determines where the Like Box will be displayed on your store. | *When set to Left column:* The Like Box appears in the left sidebar. *When set to Right column:* The Like Box appears in the right sidebar. *When set to Homepage:* The Like Box appears in the main content area of your homepage. *When set to Footer:* The Like Box appears at the bottom of every page. | **Right column** or **Homepage** | You want the Like Box to be prominently visible without interfering with product viewing. |
| **Facebook Page URL** | This is the direct link to your official Facebook Page. | *When set to your page URL (e.g., `https://www.facebook.com/MyPrestaEU`):* The Like Box will display content and a “Like” button for *your* specific Facebook Page. *When left empty or incorrect:* The Like Box may not display correctly or will show an error. | Your actual Facebook Page URL | You want to connect your store visitors to your brand’s Facebook presence. |
| **Width** | Sets the width of the Like Box in pixels. | *When set to a specific pixel value (e.g., `280`):* The Like Box will be exactly that wide. *When left empty:* The module will try to auto-adjust the width, but it’s often better to set a specific value for consistent design. | `280` (or adjust to fit your column/layout) | Your right column is 300px wide, so you set the Like Box width to 280px to fit nicely with some padding. |
| **Height** | Sets the height of the Like Box in pixels. | *When set to a specific pixel value (e.g., `500`):* The Like Box will be exactly that tall. *When left empty:* The module will try to auto-adjust the height. | `500` (or adjust based on content you want to show) | You want to show a few recent posts, so you set the height to 500px to allow enough space. |
| **Hide cover** | Controls whether the large cover photo of your Facebook Page is displayed at the top of the Like Box. | *When enabled:* The cover photo will be hidden, making the Like Box more compact. *When disabled:* The cover photo will be visible. | **Enabled** (for a cleaner look) | You prefer a minimalist design and want the Like Box to take up less vertical space. |
| **Profile pictures** (Show Facepile) | Determines if the profile pictures of people who like your page are shown below the “Like” button. | *When enabled:* A row of small profile pictures will appear, showing social proof. *When disabled:* These profile pictures will not be shown. | **Enabled** (for social proof) | You want to show visitors that many others already like your page, encouraging them to do the same. |
| **Show posts** (Show Stream) | Controls whether recent posts from your Facebook Page are displayed within the Like Box. | *When enabled:* Your latest Facebook posts will be visible, making the Like Box more dynamic. *When disabled:* Only the “Like” button and facepile (if enabled) will be shown. | **Enabled** | You actively post on Facebook and want to showcase your latest content directly on your store. |
| **Call to action button** (Hide CTA) | Controls whether the “Call to Action” button (e.g., “Send Message”, “Shop Now”) from your Facebook Page is hidden. | *When enabled:* The CTA button will be hidden. *When disabled:* The CTA button will be visible if configured on your Facebook Page. | **Enabled** (often for a cleaner look) | You want to focus solely on getting a “Like” and don’t want another button distracting visitors. |
| **Small header** | Makes the header of the Like Box smaller. | *When enabled:* The header (containing your page name and “Like” button) will be more compact. *When disabled:* The header will be standard size. | **Enabled** (for a more compact design) | You want the Like Box to be less intrusive and blend more seamlessly into your store’s design. |
| **Facebook library** (Include App) | This setting controls whether the necessary Facebook JavaScript SDK is loaded. | *When enabled:* The module will load the Facebook SDK, which is essential for the Like Box to function correctly. *When disabled:* The Like Box will likely not display or function properly. | **Enabled** | This is crucial for the Like Box to work. |

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enabled/Disabled | Enabled | Activates/Deactivates the Like Box on your store. |
| Module Configuration | Position | Right column / Homepage | Determines where the Like Box appears (Left/Right Column, Homepage, Footer). |
| Module Configuration | Facebook Page URL | Your Facebook Page URL | Links the Like Box to your specific Facebook Page. |
| Module Configuration | Width | 280 | Sets the width of the Like Box in pixels. |
| Module Configuration | Height | 500 | Sets the height of the Like Box in pixels. |
| Module Configuration | Hide cover | Enabled | Hides the large cover photo for a more compact look. |
| Module Configuration | Profile pictures (Show Facepile) | Enabled | Shows profile pictures of people who like your page (social proof). |
| Module Configuration | Show posts (Show Stream) | Enabled | Displays recent posts from your Facebook Page. |
| Module Configuration | Call to action button (Hide CTA) | Enabled | Hides the Facebook Page’s Call to Action button. |
| Module Configuration | Small header | Enabled | Makes the Like Box header more compact. |
| Module Configuration | Facebook library (Include App) | Enabled | Loads the necessary Facebook JavaScript SDK for functionality. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: The Facebook Like Box isn’t showing up on my store. What should I do?**
A:

1. **Check Module Status:** Go to **Modules > Module Manager** and ensure “Facebook Like Box Free” is installed and enabled.
2. **Verify Configuration:** Go to the module’s configuration page.
   - Make sure “Enabled” is set to YES.
   - Double-check that the “Facebook Page URL” is correct and complete (e.g., `https://www.facebook.com/MyPrestaEU`).
   - Ensure “Facebook library” (Include App) is enabled.
3. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes old cached files prevent new modules from appearing.
4. **Check Hook Position:** Ensure the “Position” you selected (e.g., Right column, Homepage) is actually active in your theme. Some themes might not display certain columns. You can check **Design > Positions** to see if the module is hooked correctly.

**Q: The Like Box looks too wide/narrow or too tall/short.**
A: Adjust the “Width” and “Height” settings on the module’s configuration page. Experiment with different pixel values until it fits your theme’s layout perfectly. Remember to clear your browser cache after making changes to see the update.

**Q: I changed settings, but nothing happened on my store.**
A: After saving changes in the module configuration, always clear your PrestaShop cache (**Advanced Parameters > Performance > Clear cache**) and then clear your browser’s cache (Ctrl+F5 or Cmd+R) to ensure you’re seeing the latest version of your store.

**Q: The Like Box is showing an error message or not loading content.**
A:

1. **Incorrect URL:** The most common reason is an incorrect “Facebook Page URL.” Double-check it for typos.
2. **Facebook API Issues:** Occasionally, there might be temporary issues with Facebook’s API. Wait a bit and check again.
3. **Theme Conflicts:** Rarely, your theme’s JavaScript or CSS might conflict. If the above steps don’t work, try temporarily switching to the default PrestaShop theme to rule out a theme conflict.

**Q: Can I translate the “Like Page” text into other languages?**
A: The text within the Facebook Like Box itself (like “Like Page” or post content) is controlled by Facebook and will automatically adapt to the user’s Facebook language settings. The module’s back-office settings are translatable via **International > Translations** in PrestaShop.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a technical overview for developers and webmasters working with the Facebook Like Box Free module.

### 4.1 Architecture Overview

The `Facebook Like Box Free` module is a straightforward PrestaShop module primarily designed to embed the Facebook Page Plugin (formerly Like Box) using the official Facebook JavaScript SDK. It follows a basic PrestaShop module structure, leveraging the `Module` class for installation, uninstallation, and configuration. Its core functionality revolves around displaying the Facebook widget via a Smarty template hooked into various front-office positions. There are no custom database tables or complex ObjectModels involved; all configuration is stored in `ps_configuration`.

### 4.2 Controllers (`controllers/`)

This module does **not** contain any custom Front-Office or Back-Office Admin Controllers. All logic is encapsulated within the main module file (`likeboxfree.php`).

### 4.3 Core Classes & Models (`classes/`)

This module does **not** define any custom classes or ObjectModels in the `classes/` directory. All module logic resides in the main `likeboxfree.php` file.

### 4.4 JavaScript Assets (`views/js/`)

This module does **not** include any custom JavaScript files in `views/js/`.
The Facebook JavaScript SDK is dynamically loaded by the module’s template if the `lbf_includeapp` setting is enabled. This is handled by Facebook’s own script, not a custom module script.

### 4.5 CSS Stylesheets (`views/css/`)

- **`likeboxfree/css.css`**
  - **Scope:** Front-office customer styling.
  - **Main UI components and containers it styles:** This file provides basic styling for the wrapper around the Facebook Like Box to ensure it integrates cleanly into the PrestaShop layout, particularly for column hooks. It might contain rules for padding, margins, or basic responsiveness.
  - **Key CSS class selectors developers can override:** Developers can inspect the generated HTML to find the wrapper element (e.g., a `div` with a specific ID or class generated by the module) and override its styles in their theme’s `custom.css` or `theme.css`.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - **`likeboxfree/rightcolumn.tpl`**
    - **Hooked into:** `displayHome`, `displayFooter`, `displayRightColumn`, `displayLeftColumn` (depending on the `likeboxfree_position` configuration).
    - **Visual block output:** This template is responsible for rendering the HTML structure that embeds the Facebook Page Plugin. It dynamically generates the `div` element with the `fb-page` class and data attributes (`data-href`, `data-width`, `data-height`, etc.) based on the module’s configuration settings. It also includes the necessary JavaScript snippet to initialize the Facebook SDK and parse the plugin.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  This module does not create any custom database tables. All configuration settings are stored in the `ps_configuration` table using keys prefixed with `likeboxfree_` or `lbf_`.

  - `ps_configuration` entries:
    - `likeboxfree_position`: Stores the chosen hook position (e.g., `displayRightColumn`).
    - `lbf_width`: Width of the Like Box.
    - `lbf_height`: Height of the Like Box.
    - `lbf_hide_cover`: Boolean (0/1) for hiding the cover photo.
    - `lbf_show_facepile`: Boolean (0/1) for showing profile pictures.
    - `lbf_show_posts`: Boolean (0/1) for showing posts.
    - `lbf_hide_cta`: Boolean (0/1) for hiding the call to action button.
    - `lbf_small_header`: Boolean (0/1) for a small header.
    - `lbf_url`: The Facebook Page URL.
    - `lbf_includeapp`: Boolean (0/1) for including the Facebook SDK.
    - (Legacy/unused keys might also exist from older versions, but the above are active).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHome` | Renders content on the homepage. | Displays the Facebook Like Box on the main homepage content area if configured. |
| `displayFooter` | Renders content in the store’s footer. | Displays the Facebook Like Box at the bottom of every page if configured. |
| `displayRightColumn` | Renders content in the right sidebar. | Displays the Facebook Like Box in the right column of pages if configured. |
| `displayLeftColumn` | Renders content in the left sidebar. | Displays the Facebook Like Box in the left column of pages if configured. |

The module’s `hookDisplay*` methods check the `likeboxfree_position` configuration value and only render the `rightcolumn.tpl` template if the current hook matches the configured position.

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Facebook Like Box Free” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and integration.
