---
title: "Responsive Facebook Like Box - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Responsive Facebook Like Box PrestaShop module by MyPresta.eu."
sidebar:
  label: "Responsive Facebook Like Box - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Responsive Facebook Like Box Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/responsive-facebook-like-box.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/responsive-facebook-like-box/)
>
> ---


# Responsive Facebook Like Box

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and are usually available on any modern hosting environment. No special hosting requirements beyond a standard PrestaShop setup.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for your “Responsive Facebook Like Box” module. Here you will define how your Facebook Like Box looks and behaves on your store.

- **Menu Location:** Back Office > Modules > Module Manager > Search for “Responsive Facebook Like Box” > Click “Configure”.

#### Settings & Options:

1. **Facebook Fanpage URL:**

   - **What this setting does:** This is the most critical setting. It tells the module which specific Facebook page to display in the Like Box.
   - **Effect of changing this setting:**
     - *When set to your Facebook page URL (e.g., `https://www.facebook.com/MyPresta.eu`):* The module will display the Like Box for that specific page.
     - *When left empty or set to an invalid URL:* The Like Box will not display correctly or at all.
   - **Recommended value:** Your official Facebook Fanpage URL.
   - **Merchant scenario / example:** If your store’s Facebook page is `https://www.facebook.com/MyAwesomeStore`, you would enter that URL here.
2. **Width of the Like Box (in pixels):**

   - **What this setting does:** Controls the horizontal size of the Facebook Like Box.
   - **Effect of changing this setting:**
     - *When set to a specific pixel value (e.g., `340`):* The Like Box will attempt to render at that exact width.
     - *When set to a smaller value:* The box will be narrower, potentially hiding some content or making text smaller.
     - *When set to a larger value:* The box will be wider, taking up more horizontal space.
   - **Recommended value:** `340` (This is a common default for Facebook’s Page Plugin and often works well in side columns). For full-width sections, you might use a larger value or leave it to auto-adjust if the theme allows.
   - **Merchant scenario / example:** If your right column is 300px wide, setting this to 280-300px would ensure it fits perfectly without overflowing.
3. **Height of the Like Box (in pixels):**

   - **What this setting does:** Controls the vertical size of the Facebook Like Box.
   - **Effect of changing this setting:**
     - *When set to a specific pixel value (e.g., `500`):* The Like Box will render at that exact height.
     - *When set to a smaller value:* The box will be shorter, potentially requiring scrolling to see all content (like recent posts or friend faces).
     - *When set to a larger value:* The box will be taller, taking up more vertical space.
   - **Recommended value:** `500` (A good balance to show some content without being excessively long). Adjust based on how much content you want to display (e.g., more posts = more height).
   - **Merchant scenario / example:** If you want to show 3-4 recent posts from your Facebook page, you might need a height of 500px or more. If you only want to show the “Like” button and cover photo, a smaller height like 200px might suffice.
4. **Show Faces of Friends:**

   - **What this setting does:** Determines whether the Like Box displays profile pictures of people who have liked your page and are also friends with the current viewer.
   - **Effect of changing this setting:**
     - *When enabled (YES):* The Like Box will show faces, adding a social proof element, as visitors see their friends connected to your brand.
     - *When disabled (NO):* Faces will not be displayed, resulting in a cleaner, more compact look.
   - **Recommended value:** YES (Leverages social proof to encourage more likes).
   - **Merchant scenario / example:** Enabling this can increase trust and engagement, as shoppers are more likely to follow a brand their friends already like.
5. **Show Stream (Posts from your Page):**

   - **What this setting does:** Controls whether recent posts from your Facebook page are displayed within the Like Box.
   - **Effect of changing this setting:**
     - *When enabled (YES):* Your latest Facebook posts will appear in the box, providing fresh content and encouraging interaction.
     - *When disabled (NO):* Only the cover photo, page name, and “Like” button will be visible, making the box more compact.
   - **Recommended value:** YES (Keeps the content fresh and shows visitors what kind of content they can expect if they follow you).
   - **Merchant scenario / example:** If you regularly post updates, promotions, or interesting content on Facebook, showing the stream keeps your website visitors engaged with your social media activity.
6. **Show Header:**

   - **What this setting does:** Determines whether a small “Facebook” header is displayed at the top of the Like Box.
   - **Effect of changing this setting:**
     - *When enabled (YES):* A small header with the Facebook logo and text will appear.
     - *When disabled (NO):* The header will be removed, giving a slightly more integrated look, but potentially less clear that it’s a Facebook widget.
   - **Recommended value:** YES (Provides clear branding and context).
   - **Merchant scenario / example:** Keeping the header helps users immediately recognize it as a Facebook widget.
7. **Use Small Header:**

   - **What this setting does:** If “Show Header” is enabled, this option controls whether a smaller version of the header is used.
   - **Effect of changing this setting:**
     - *When enabled (YES):* The header will be more compact.
     - *When disabled (NO):* The standard-sized header will be used.
   - **Recommended value:** YES (Often looks better in side columns or smaller spaces).
   - **Merchant scenario / example:** Useful if you’re placing the Like Box in a narrow column where space is limited.
8. **Adapt to Container Width:**

   - **What this setting does:** This is a crucial responsiveness setting. It tells the Facebook Like Box to automatically adjust its width to fit the width of the container it’s placed in (e.g., your theme’s column).
   - **Effect of changing this setting:**
     - *When enabled (YES):* The Like Box will dynamically resize, making it truly responsive and preventing overflow issues on different screen sizes. The “Width of the Like Box” setting might be overridden or used as a maximum.
     - *When disabled (NO):* The Like Box will try to maintain the “Width of the Like Box” setting, potentially leading to layout issues on smaller screens if the set width is too large.
   - **Recommended value:** YES (Essential for a responsive design and good user experience on mobile).
   - **Merchant scenario / example:** If you place the Like Box in a responsive sidebar, enabling this ensures it always fits perfectly, regardless of the device your customer is using.
9. **Background Color (Hex Code):**

   - **What this setting does:** Allows you to set a custom background color for the Like Box using a hexadecimal color code (e.g., `#FFFFFF` for white).
   - **Effect of changing this setting:**
     - *When set to a specific hex code:* The background of the Like Box will change to that color.
     - *When left empty or set to an invalid code:* The default Facebook background color (usually light grey or white) will be used.
   - **Recommended value:** Match your theme’s background color or leave empty for default.
   - **Merchant scenario / example:** If your store has a dark theme, you might set this to a dark grey to blend in better.
10. **Placement Hook:**

    - **What this setting does:** Determines where on your PrestaShop store the Facebook Like Box will be displayed.
    - **Effect of changing this setting:**
      - *When set to `displayHeader`:* The Like Box will appear in the header section of your store.
      - *When set to `displayLeftColumn` or `displayRightColumn`:* The Like Box will appear in the respective sidebar.
      - *When set to `displayFooter`:* The Like Box will appear in the footer section.
      - *When set to `displayProductButtons` or similar product page hook:* The Like Box will appear on product pages.
    - **Recommended value:** `displayRightColumn` or `displayLeftColumn` (Common and effective for visibility without being intrusive).
    - **Merchant scenario / example:** If you want the Like Box to be visible on most pages without taking up prime header space, placing it in a column is a good choice. If you want it to be very prominent, the header might be preferred.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Facebook Fanpage URL | Your Facebook Page URL | Links the module to your specific Facebook page. |
| Module Configuration | Width of the Like Box (px) | 340 | Sets the horizontal size. |
| Module Configuration | Height of the Like Box (px) | 500 | Sets the vertical size. |
| Module Configuration | Show Faces of Friends | YES | Displays profile pictures of friends for social proof. |
| Module Configuration | Show Stream (Posts) | YES | Displays recent posts from your Facebook page. |
| Module Configuration | Show Header | YES | Displays the “Facebook” header. |
| Module Configuration | Use Small Header | YES | Uses a compact header if “Show Header” is enabled. |
| Module Configuration | Adapt to Container Width | YES | Makes the Like Box responsive to its parent container. |
| Module Configuration | Background Color (Hex) | (Leave empty for default) | Customizes the background color of the box. |
| Module Configuration | Placement Hook | displayRightColumn / displayLeftColumn | Determines where the box appears on your store. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The Facebook Like Box isn’t showing up on my store. What should I do?**

- **A:** First, double-check that you have entered the correct and complete **“Facebook Fanpage URL”** in the module configuration. Make sure it starts with `https://`.
- **A:** Verify that the **“Placement Hook”** you selected is actually active and displayed by your theme. Some themes might not display certain hooks (e.g., left column) on all pages. Try switching to a different hook like `displayFooter` to see if it appears there.
- **A:** Clear your PrestaShop cache. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Also, clear your browser’s cache.
- **A:** Ensure the module is enabled. In **Modules > Module Manager**, search for the module and confirm it’s not disabled.

**Q2: The Like Box looks too wide/narrow or too tall/short.**

- **A:** Adjust the **“Width of the Like Box”** and **“Height of the Like Box”** settings in the module configuration.
- **A:** If you want it to automatically adjust to your theme’s column, make sure **“Adapt to Container Width”** is set to YES. This is especially important for responsive themes.

**Q3: Why aren’t recent posts or friends’ faces showing up in the Like Box?**

- **A:** Check the module configuration settings:
  - Ensure **“Show Stream (Posts from your Page)”** is set to YES to display posts.
  - Ensure **“Show Faces of Friends”** is set to YES to display friend faces.
- **A:** Facebook’s API sometimes has limitations or delays. Ensure your Facebook page has recent public posts.

**Q4: The background color I set isn’t appearing.**

- **A:** Make sure you’ve entered a valid hexadecimal color code (e.g., `#RRGGBB`). If you’re using a custom theme, there might be conflicting CSS styles. You might need a web developer to inspect the element and apply a more specific CSS rule if the module’s setting is being overridden.

**Q5: The module works on desktop but looks strange on mobile.**

- **A:** This is almost always due to the **“Adapt to Container Width”** setting. Ensure it is set to YES. This tells the Facebook widget to be responsive. Also, check your theme’s responsiveness; if the container the module is in isn’t responsive, the module can’t adapt perfectly.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview of the “Responsive Facebook Like Box” module for developers and webmasters.

### 4.1 Architecture Overview

The `Responsive Facebook Like Box` module (`likebox/ar.php`) is a standard PrestaShop module following the MVC pattern where applicable for its configuration. It primarily leverages PrestaShop’s hook system to inject the Facebook Page Plugin (Like Box) into various front-office locations. The core functionality relies on the Facebook Page Plugin’s JavaScript SDK, which is dynamically loaded and configured based on the module’s settings. Configuration is managed via `Configuration::get()` and `Configuration::updateValue()` within the main module class.

### 4.2 Controllers (`controllers/`)

This module does not utilize custom Front-Office or Back-Office Admin Controllers. All configuration is handled directly within the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or extend `ObjectModel`. All logic is encapsulated within the main module file `ar.php`.

### 4.4 JavaScript Assets (`views/js/`)

- **`likebox/jscolor/jscolor.js`**

  - **Scope:** Back-office (Admin Configuration Page).
  - **Purpose:** This is a third-party JavaScript library for a color picker. It’s used on the module’s configuration page to provide a user-friendly interface for selecting the “Background Color” setting.
  - **Functionality:** It transforms a standard text input field into an interactive color picker, allowing the admin to visually select a hexadecimal color code.
- **`likebox/script.js`**

  - **Scope:** Front-office.
  - **Purpose:** This script is responsible for dynamically loading the Facebook JavaScript SDK and initializing the Facebook Page Plugin (Like Box) on the front-office.
  - **Functionality:**
    - It typically checks for the existence of the Facebook SDK (`FB`) and loads it if not already present.
    - It then calls `FB.XFBML.parse()` or similar methods to render the `div` element with the `fb-page` class, applying the attributes (data-href, data-width, etc.) based on the module’s configuration.
    - It ensures the Like Box is rendered correctly after the DOM is ready.

### 4.5 CSS Stylesheets (`views/css/`)

- **`likebox/css/css.css`**

  - **Scope:** Front-office.
  - **Purpose:** Contains general styling rules for the Facebook Like Box container and potentially some responsive adjustments.
  - **Key Selectors:** Likely targets the main container `div` that wraps the Facebook Page Plugin, ensuring it fits within the theme’s layout and handles basic responsiveness. Developers can override these styles in their theme’s `custom.css` or `theme.css` if needed.
- **`likebox/css.css`**

  - **Scope:** Front-office.
  - **Purpose:** Similar to `likebox/css/css.css`, this file likely contains additional or alternative styling rules for the front-office display of the Like Box. It might include rules for specific placements or minor visual tweaks.
  - **Key Selectors:** Targets the Facebook Like Box container and related elements.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`likebox/header.tpl`**

  - **Scope:** Front-office.
  - **Hook:** `displayHeader` (or similar header-related hook).
  - **Purpose:** This template is responsible for outputting the HTML structure for the Facebook Like Box when the module is configured to display in the header. It contains the `div` element with the `fb-page` class and `data-*` attributes that the Facebook SDK uses to render the plugin.
  - **Variables:** Accesses configuration variables (e.g., `{$facebook_page_url}`, `{$width}`, `{$height}`, `{$show_faces}`, etc.) passed from the module’s PHP logic.
- **`likebox/rightcolumn.tpl`**

  - **Scope:** Front-office.
  - **Hook:** `displayRightColumn` (or `displayLeftColumn`, `displayFooter`, `displayProductButtons`, etc., depending on the chosen hook).
  - **Purpose:** This template is responsible for outputting the HTML structure for the Facebook Like Box when the module is configured to display in a column or other content areas. It contains the `div` element with the `fb-page` class and `data-*` attributes.
  - **Variables:** Similar to `header.tpl`, it accesses configuration variables to dynamically set the plugin’s attributes.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create any custom SQL tables.
  - All configuration settings are stored in the `ps_configuration` table (or `_configuration` prefix) using keys like `RESPONSIVE_FB_LIKEBOX_URL`, `RESPONSIVE_FB_LIKEBOX_WIDTH`, etc.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Renders in the `<head>` section of the page, or at the top of the `<body>`. | Injects the Facebook Like Box HTML and potentially the Facebook SDK initialization script. |
| `displayLeftColumn` | Renders content in the left sidebar of the store. | Injects the Facebook Like Box HTML into the left column. |
| `displayRightColumn` | Renders content in the right sidebar of the store. | Injects the Facebook Like Box HTML into the right column. |
| `displayFooter` | Renders content in the footer section of the store. | Injects the Facebook Like Box HTML into the footer. |
| `displayProductButtons` (or similar product page hook) | Renders content on the product page, often near the add-to-cart button or description. | Injects the Facebook Like Box HTML onto product pages. |
| `actionFrontControllerSetMedia` | Executed when a front controller is setting its media (JS/CSS). | Registers the module’s CSS and JavaScript files for front-office display. |
| `actionAdminControllerSetMedia` | Executed when an admin controller is setting its media (JS/CSS). | Registers the `jscolor.js` script and potentially admin-specific CSS for the module’s configuration page. |

## 5. Official Support & Updates

For the latest updates, new versions, and official support for the “Responsive Facebook Like Box” module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist you with any questions or issues you may encounter.
