---
title: "Facebook join to group widget - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Facebook join to group widget PrestaShop module by MyPresta.eu."
sidebar:
  label: "Facebook join to group widget - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Facebook join to group widget Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-join-to-group-widget.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/facebook-join-to-group-widget/)
>
> ---


# Facebook join to group widget

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main screen where you will set up all the options for your Facebook Join Group widget.

- **Screen Name & Menu Location:** Back Office > Modules > Module Manager > “Facebook join to group widget” > Configure

#### Settings & Options:

1. **Group URL** (Configuration Key: `fbg_href`)

   - **What this setting does:** This is the most crucial setting. It defines the direct link to your Facebook Group. When customers click the “Join Group” button, they will be taken to this URL.
   - **Effect of changing this setting:**
     - *When set to a valid Facebook Group URL:* The “Join Group” button will correctly redirect users to your specified group.
     - *When left empty or set to an invalid URL:* The button might not work, or it might lead to an error page, frustrating your customers.
   - **Recommended value:** Always provide the full and correct URL to your Facebook Group (e.g., `https://www.facebook.com/groups/yourgroupname/`).
   - **Merchant scenario / example:** You want customers to join your “My Awesome Store Community” group. You would paste `https://www.facebook.com/groups/myawesomestorecommunity/` here.
2. **Box width** (Configuration Key: `fbg_width`)

   - **What this setting does:** Controls the width of the Facebook Join Group widget box on your store. You can specify this in pixels.
   - **Effect of changing this setting:**
     - *When set to a specific pixel value (e.g., `280`):* The box will attempt to render at that exact width.
     - *When left empty or set to `0`:* The module will try to auto-adjust its width based on the available space in the hook it’s displayed in, or use a default value.
   - **Recommended value:** Start with `280` or `300` pixels. Test on different devices. If you want it to fill the available space in a column, you might leave it empty, but be aware it might stretch too wide in some hooks.
   - **Merchant scenario / example:** You want the widget to fit neatly into your left column, which is 250px wide. You would set this to `250`.
3. **Where do you want to display the box?** (Configuration Key: `fbg_hook`)

   - **What this setting does:** This dropdown allows you to select the specific location (PrestaShop hook) where the widget will appear on your store.
   - **Effect of changing this setting:**
     - *Selecting `DisplayFooter`:* The widget will appear at the bottom of every page.
     - *Selecting `DisplayHome`:* The widget will appear only on your homepage.
     - *Selecting `DisplayRightColumn`:* The widget will appear in the right sidebar on pages that have one.
     - *Selecting any other hook:* The widget will appear in that specific location.
   - **Recommended value:** This depends entirely on your theme and marketing strategy. `DisplayRightColumn` or `DisplayLeftColumn` are common for side widgets. `DisplayFooter` is good for less intrusive placement. `DisplayHome` is great for high visibility.
   - **Merchant scenario / example:** You want the widget to be visible on most pages but not interfere with your main content. You choose `DisplayRightColumn`.
4. **Header** (Configuration Key: `fbg_header`)

   - **What this setting does:** This is the main title text displayed at the top of your Facebook Join Group widget.
   - **Effect of changing this setting:**
     - *When set to “Join Our Community”:* This text will be prominently displayed.
     - *When left empty:* No header text will be shown, making the widget less clear to customers.
   - **Recommended value:** A clear, inviting title like “Join Our Facebook Group”, “Our Community”, or “Connect With Us”.
   - **Merchant scenario / example:** You want to clearly tell customers what the box is about. You set it to “Join Our Exclusive Facebook Group!”.
5. **Description** (Configuration Key: `fbg_desc`)

   - **What this setting does:** This provides a short explanatory text below the header, giving customers more context about your Facebook Group.
   - **Effect of changing this setting:**
     - *When set to “Get exclusive deals and updates!”:* This message will appear below the header.
     - *When left empty:* The widget will only show the header and button, potentially missing an opportunity to entice users.
   - **Recommended value:** A brief, compelling sentence or two explaining the benefits of joining (e.g., “Be the first to know about new products and special offers!”).
   - **Merchant scenario / example:** You want to encourage sign-ups by highlighting benefits. You set it to “Access member-only discounts, sneak peeks, and connect with fellow enthusiasts!”.
6. **Button text** (Configuration Key: `fbg_btn_text`)

   - **What this setting does:** This is the text displayed on the button that customers click to join your group.
   - **Effect of changing this setting:**
     - *When set to “Join Group”:* This text will appear on the button.
     - *When left empty:* The button might appear blank or use a default, which is less effective.
   - **Recommended value:** A clear call to action like “Join Group”, “Join Now”, or “Connect on Facebook”.
   - **Merchant scenario / example:** You want a direct call to action. You set it to “Join Our Group”.
7. **Text color** (Configuration Key: `fbg_text_color`)

   - **What this setting does:** Allows you to set the color of the header and description text within the widget.
   - **Effect of changing this setting:**
     - *When set to `#000000` (black):* The text will appear black.
     - *When set to `#FFFFFF` (white):* The text will appear white.
   - **Recommended value:** Choose a color that contrasts well with your chosen background color and matches your brand’s color palette. Use a hex code (e.g., `#333333`).
   - **Merchant scenario / example:** Your widget has a dark background. You set the text color to `#FFFFFF` for readability.
8. **Border style** (Configuration Key: `fbg_border_style`)

   - **What this setting does:** Defines the visual style of the border around the widget box.
   - **Effect of changing this setting:**
     - *`solid`:* A single, continuous line.
     - *`dashed`:* A series of short lines.
     - *`dotted`:* A series of dots.
     - *`none`:* No border will be displayed.
   - **Recommended value:** `solid` or `none` are most common. `solid` provides a clear boundary.
   - **Merchant scenario / example:** You want a subtle outline for the box. You choose `solid`.
9. **Border color** (Configuration Key: `fbg_border_color`)

   - **What this setting does:** Sets the color of the border around the widget box.
   - **Effect of changing this setting:**
     - *When set to `#CCCCCC` (light grey):* The border will be light grey.
     - *When set to `#FF0000` (red):* The border will be red.
   - **Recommended value:** A color that complements your store’s design, often a subtle grey or a brand accent color. Use a hex code.
   - **Merchant scenario / example:** Your brand uses a specific shade of blue. You set the border color to `#007bff`.
10. **Border size** (Configuration Key: `fbg_border_size`)

    - **What this setting does:** Determines the thickness of the border in pixels.
    - **Effect of changing this setting:**
      - *When set to `1`:* A thin border will appear.
      - *When set to `5`:* A thicker, more prominent border will appear.
    - **Recommended value:** `1` or `2` pixels for a subtle border.
    - **Merchant scenario / example:** You want a very thin border. You set the size to `1`.
11. **Border radius** (Configuration Key: `fbg_border_radius`)

    - **What this setting does:** Controls the roundness of the corners of the widget box. A higher value creates more rounded corners.
    - **Effect of changing this setting:**
      - *When set to `0`:* The box will have sharp, square corners.
      - *When set to `10`:* The corners will be noticeably rounded.
    - **Recommended value:** `0` for sharp corners, `3` to `5` for slightly rounded, or `10+` for very rounded, depending on your theme’s aesthetic.
    - **Merchant scenario / example:** Your theme uses slightly rounded elements. You set the border radius to `5`.
12. **Background color** (Configuration Key: `fbg_bg_color`)

    - **What this setting does:** Sets the primary background color of the widget box.
    - **Effect of changing this setting:**
      - *When set to `#F0F2F5` (light grey, similar to Facebook’s background):* The box background will be light grey.
      - *When set to `#FFFFFF` (white):* The box background will be white.
    - **Recommended value:** A color that makes the text readable and fits your store’s design. Use a hex code.
    - **Merchant scenario / example:** You want the widget to stand out slightly from a white page background. You set the background color to `#F8F8F8`.
13. **Background gradient** (Configuration Key: `fbg_bg_gradient`)

    - **What this setting does:** Allows you to add a CSS gradient to the background of the widget box, creating a smooth transition between two or more colors. This overrides the single “Background color” if used.
    - **Effect of changing this setting:**
      - *When set to `linear-gradient(to right, #FFD700, #FFA500)`:* The background will transition from gold to orange.
      - *When left empty:* The “Background color” setting will be used instead.
    - **Recommended value:** Use a CSS gradient string if you want a more dynamic background. If you’re unsure, leave this empty and use a single “Background color”.
    - **Merchant scenario / example:** You want a subtle, modern look. You use a gradient like `linear-gradient(to bottom, #e0eafc, #cfdef3)`.

#### Hidden/Internal Settings (for developer reference, not directly configurable by merchant):

- `mypresta_updates`, `update_`, `updatev_`: Internal keys for module updates and version checks.
- `fbg_app`, `fbg_appid`: These keys suggest potential for Facebook App integration, but are not exposed in the current configuration.
- `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: PrestaShop core settings related to language handling in the back office.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | **Group URL** | Your Facebook Group URL | Direct link to your Facebook Group for the “Join Group” button. **CRITICAL!** |
| Module Configuration | **Box width** | `280` or `300`px | Sets the width of the widget box. Leave empty for auto-adjust. |
| Module Configuration | **Where do you want to display the box?** | `DisplayRightColumn` or `DisplayFooter` | Selects the PrestaShop hook where the widget appears. |
| Module Configuration | **Header** | “Join Our Facebook Group” | Main title text for the widget. |
| Module Configuration | **Description** | “Get exclusive deals and updates!” | Short explanatory text below the header. |
| Module Configuration | **Button text** | “Join Group” | Text displayed on the action button. |
| Module Configuration | **Text color** | `#333333` (dark grey) | Color of the header and description text. Use hex code. |
| Module Configuration | **Border style** | `solid` or `none` | Visual style of the box border (solid, dashed, dotted, none). |
| Module Configuration | **Border color** | `#CCCCCC` (light grey) | Color of the box border. Use hex code. |
| Module Configuration | **Border size** | `1` or `2`px | Thickness of the box border. |
| Module Configuration | **Border radius** | `0` or `5`px | Roundness of the box corners. |
| Module Configuration | **Background color** | `#F0F2F5` (light grey) | Primary background color of the widget box. Use hex code. |
| Module Configuration | **Background gradient** | Leave empty | CSS gradient for the background. Overrides `Background color` if set. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

1. **The widget isn’t showing up on my store.**

   - **Check 1:** Go to **Modules > Module Manager**, search for “Facebook join to group widget”, and ensure it is installed and enabled.
   - **Check 2:** In the module’s configuration, verify that you have selected a “Where do you want to display the box?” (hook). Make sure the selected hook actually exists and is active in your current theme. Some themes might not use all standard PrestaShop hooks.
   - **Check 3:** Clear your PrestaShop cache (**Advanced Parameters > Performance > Clear cache**). Sometimes, changes don’t appear until the cache is refreshed.
   - **Check 4:** If you have a custom theme, it might override standard hook displays. Contact your theme developer or a webmaster.
2. **The “Join Group” button doesn’t work or leads to an error.**

   - **Check:** Go to the module’s configuration and carefully re-enter your “Group URL”. Ensure it’s the complete and correct URL to your Facebook Group (e.g., `https://www.facebook.com/groups/yourgroupname/`). Test the URL directly in your browser to confirm it works.
3. **The widget looks strange or doesn’t fit my theme’s design.**

   - **Check 1:** Adjust the “Box width” setting. If it’s too wide for a column, it might break the layout. Try a smaller pixel value.
   - **Check 2:** Use the “Text color”, “Border style”, “Border color”, “Border size”, “Border radius”, “Background color”, and “Background gradient” settings to match your theme’s colors and styles.
   - **Check 3:** Clear your PrestaShop cache after making style changes.
   - **Check 4:** If the issue persists, it might be a CSS conflict with your theme. A webmaster can inspect your site’s CSS to identify and resolve conflicts.
4. **Can I display the widget in multiple locations?**

   - The current version of the module allows you to select only one hook from the dropdown. If you need to display it in multiple places, you would need to duplicate the module (which requires developer intervention) or use a custom solution.
5. **My text isn’t showing up in the correct language.**

   - The “Header”, “Description”, and “Button text” fields are typically translatable if your PrestaShop installation supports multiple languages for module configurations. Ensure you are editing the module’s configuration in the correct language context in the Back Office (check the language dropdown at the top right of your admin panel).

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Facebook join to group widget” module is a straightforward PrestaShop module following a basic MVC-like pattern inherent to PrestaShop’s module structure. It primarily uses the `Module` class for its core functionality, configuration management, and hook registration. All configuration is handled via the `getContent()` method in the main module file, storing settings in `ps_configuration`. Front-office display is managed through Smarty templates rendered via registered hooks. There are no custom controllers or ObjectModels.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. All front-office rendering is handled directly via `hook` methods within the main `fbgroup.php` module file, which then render Smarty templates.
- **Back-Office Admin Controllers**: None. All administration is handled via the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)

- **`fbgroup/fbgroup.php` (Main Module Class)**
  - **Class Name:** `Fbgroup`
  - **Parent Class:** `Module`
  - **Responsibility:**
    - Module installation (`install()`) and uninstallation (`uninstall()`).
    - Registration of all specified hooks (`registerHook()`).
    - Management of module configuration settings via `getContent()` method, which handles form submission and updates `ps_configuration` table.
    - Implementation of various `hook` methods (e.g., `hookDisplayHeader`, `hookDisplayFooter`, `hookDisplayHome`, etc.) to render the widget in the front office.
    - Retrieval of configuration values from `ps_configuration` for template rendering.
    - `_clearCache()` method for clearing module-specific cache.
    - `_displayForm()` method for rendering the configuration form in the back office.

### 4.4 JavaScript Assets (`views/js/`)

- No custom JavaScript files are included in this module. All functionality is handled server-side or via standard HTML/CSS.

### 4.5 CSS Stylesheets (`views/css/`)

- No custom CSS files are included in this module. All styling is applied inline within the `displayHeader.tpl` template or directly via the `hookDisplayHeader` method, using the configuration values. This means developers wishing to override styles will need to target the generated HTML directly or use the `displayHeader` hook to inject their own CSS.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - `fbgroup/views/displayHeader.tpl`:
    - **Hook:** Primarily intended for `displayHeader` (though the module’s `hookDisplayHeader` method is used to inject CSS, not render the widget itself). This template is NOT used for the main widget display. It’s likely a remnant or used for meta/CSS injection.
    - **Purpose:** If it were used, it would output HTML within the `<head>` section. In this module’s context, the `hookDisplayHeader` method is used to *inject CSS styles* dynamically based on configuration settings, rather than rendering a visible template.
  - `fbgroup/views/displayWidget.tpl`:
    - **Hook:** This is the primary template used for rendering the Facebook Join Group widget in all selected front-office hooks (e.g., `displayFooter`, `displayHome`, `displayRightColumn`, etc.).
    - **Purpose:** Outputs the HTML structure for the widget, including the header, description, and the “Join Group” button. It receives variables like `fbg_href`, `fbg_header`, `fbg_desc`, `fbg_btn_text`, and dynamic CSS styles from the module’s hook methods.
- **Admin templates (`views/templates/admin/`)**: None. The configuration form is built programmatically within `getContent()` using PrestaShop’s `HelperForm`.
- **Front-office templates (`views/templates/front/`)**: None.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any custom database tables.
  - All configuration settings are stored in the `ps_configuration` table (or `_configuration` prefix, depending on your setup) using the configuration keys listed in section 4.1 (e.g., `FBG_HREF`, `FBG_WIDTH`, `FBG_HEADER`, etc.).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Used by the module to inject dynamic CSS styles for the widget based on configuration. |
| `displayFooter` | At the bottom of every page, before `</body>`. | Renders the `displayWidget.tpl` template, showing the Facebook widget. |
| `displayHome` | On the homepage, usually in the main content area. | Renders the `displayWidget.tpl` template, showing the Facebook widget. |
| `displayNav1` | In the navigation bar, often top-left. | Renders the `displayWidget.tpl` template, showing the Facebook widget. |
| `displayNav2` | In the navigation bar, often top-right. | Renders the `displayWidget.tpl` template, showing the Facebook widget. |
| `displayNav` | Generic navigation hook, theme dependent. | Renders the `displayWidget.tpl` template, showing the Facebook widget. |
| `displayFbgroup` | Custom hook, requires theme integration. | Renders the `displayWidget.tpl` template, showing the Facebook widget. |
| `displayTop` | In the header section, often above the logo. | Renders the `displayWidget.tpl` template, showing the Facebook widget. |
| `displayTopColumn` | In the main content area of the header. | Renders the `displayWidget.tpl` template, showing the Facebook widget. |
| `displayLeftColumn` | In the left sidebar of pages that have one. | Renders the `displayWidget.tpl` template, showing the Facebook widget. |
| `displayRightColumn` | In the right sidebar of pages that have one. | Renders the `displayWidget.tpl` template, showing the Facebook widget. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Facebook join to group widget” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
