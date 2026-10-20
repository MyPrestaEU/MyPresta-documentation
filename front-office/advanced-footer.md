---
title: "Advanced Footer - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Advanced Footer PrestaShop module by MyPresta.eu."
sidebar:
  label: "Advanced Footer - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Advanced Footer Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/advanced-footer.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/advanced-footer/)
>
> ---


# Advanced Footer

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No unusual server requirements.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main screen where you will define the look and feel of your advanced footer.

- **Menu Location:** Back Office > Modules > Module Manager > Search for “Advanced Footer” > Click “Configure”.

#### **Settings & Options:**

1. **Footer Width (`advf_f_width`)**

   - **What this setting does:** This controls the overall width of your custom footer area. You can set it to a fixed pixel value or a percentage.
   - **Effect of changing this setting:**
     - *When set to a fixed pixel value (e.g., `1200px`):* The footer will always be that exact width, centered on the page. On very wide screens, there might be empty space on the sides. On narrower screens, it might introduce horizontal scrollbars if the value is too large.
     - *When set to a percentage (e.g., `100%`):* The footer will stretch to fill the available width of the screen, adapting dynamically. This is generally recommended for responsive designs.
   - **Recommended value:** `100%` for a full-width, responsive footer, or `1200px` if your main store content area has a fixed width and you want the footer to match.
   - **Merchant scenario / example:** If your store’s main content area is 1200px wide, setting the footer width to `1200px` will make it align perfectly, creating a cohesive design. If you want the footer to always span the entire browser window, `100%` is the way to go.
2. **Footer Height (`advf_f_height`)**

   - **What this setting does:** This defines the minimum height of your footer area. If your content is taller than this, the footer will expand automatically.
   - **Effect of changing this setting:**
     - *When set to a specific pixel value (e.g., `280px`):* The footer will always be at least this tall. This can be useful for maintaining a consistent visual presence even if some pages have less footer content.
     - *When left empty or set to `auto` (if available):* The footer’s height will be determined solely by its content.
   - **Recommended value:** `280px` or `300px` is a good starting point to give your footer a substantial presence. You can adjust this based on the amount of content you plan to put inside.
   - **Merchant scenario / example:** You want your footer to always occupy a noticeable space at the bottom of the page, even if you only have a few links. Setting a minimum height ensures it doesn’t look too thin.
3. **Footer Background Color (`advf_f_bg`)**

   - **What this setting does:** This allows you to choose a solid background color for your entire footer area.
   - **Effect of changing this setting:**
     - *When set to a color (e.g., `#333333` for dark grey):* The footer background will display this color.
     - *When left empty:* The footer might inherit a background from your theme or be transparent.
   - **Recommended value:** A color that complements your store’s branding. Darker colors (like dark grey or black) are common for footers, but a lighter color can also work depending on your design.
   - **Merchant scenario / example:** Your brand uses a specific shade of blue. You can set the footer background to this blue to reinforce your brand identity.
4. **Footer Text Color (`advf_f_color`)**

   - **What this setting does:** This sets the default color for all text within your footer, including links.
   - **Effect of changing this setting:**
     - *When set to a color (e.g., `#ffffff` for white):* All text in the footer will appear in this color.
     - *When left empty:* Text color might inherit from your theme’s default settings, which might not be legible against your chosen footer background.
   - **Recommended value:** A color that provides good contrast with your chosen `Footer Background Color`. If your background is dark, choose a light text color (e.g., white, light grey). If your background is light, choose a dark text color.
   - **Merchant scenario / example:** You have a dark grey footer background. Setting the text color to white (`#ffffff`) ensures all your links and information are easily readable.
5. **Footer Link Hover Color (`advf_f_color_hover`)**

   - **What this setting does:** This defines the color that links in your footer will change to when a customer hovers their mouse over them.
   - **Effect of changing this setting:**
     - *When set to a color (e.g., `#cccccc` for light grey):* Links will visually change to this color on hover, providing feedback to the user that the element is interactive.
     - *When left empty:* Links might not have a hover effect, or they might inherit a default hover color from your theme, which may not match your footer design.
   - **Recommended value:** A slightly different shade of your `Footer Text Color` or an accent color from your brand palette. It should be noticeable but not jarring.
   - **Merchant scenario / example:** Your footer links are white. Setting the hover color to a light blue (`#ADD8E6`) provides a subtle, branded interaction when customers move their mouse over them.
6. **Footer Background Image URL (`advf_f_bg_url`)**

   - **What this setting does:** Allows you to use an image as the background for your footer instead of or in addition to a solid color. You need to provide the full URL to the image.
   - **Effect of changing this setting:**
     - *When a valid URL is provided:* The image will appear as the footer’s background. The `Footer Background Color` will show through if the image is transparent or if the image doesn’t cover the entire footer.
     - *When left empty:* No background image will be used.
   - **Recommended value:** Leave empty unless you have a specific, optimized background image. If used, ensure the image is lightweight and relevant.
   - **Merchant scenario / example:** You have a subtle texture image that you want to use as a background for your footer to add visual depth. You would upload this image to your server and paste its URL here.
7. **Footer Background Image Position (`advf_f_bg_pos`)**

   - **What this setting does:** Controls how a background image (if set) is positioned within the footer area. Common values include `center center`, `top left`, `bottom right`, etc.
   - **Effect of changing this setting:**
     - *When set to `center center`:* The image will be centered horizontally and vertically.
     - *When set to `top left`:* The image will start from the top-left corner.
   - **Recommended value:** `center center` for most images, or `top left` if your image is a pattern meant to start from the corner.
   - **Merchant scenario / example:** Your background image is a small logo you want to appear once in the center of the footer. You’d set this to `center center`.
8. **Footer Background Image Repeat (`advf_f_bg_repeat`)**

   - **What this setting does:** Determines if and how a background image (if set) should repeat to fill the footer area.
   - **Effect of changing this setting:**
     - *When set to `repeat`:* The image will tile horizontally and vertically.
     - *When set to `no-repeat`:* The image will appear only once.
     - *When set to `repeat-x`:* The image will tile horizontally only.
     - *When set to `repeat-y`:* The image will tile vertically only.
   - **Recommended value:** `no-repeat` for single images (like a logo), or `repeat` if your image is a small pattern designed to tile.
   - **Merchant scenario / example:** You have a tiny, seamless pattern image. Setting this to `repeat` will make it cover the entire footer area with that pattern. If it’s a single decorative element, `no-repeat` is better.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Footer Width (`advf_f_width`) | `100%` | Sets the overall width of the footer. `100%` for responsive full-width, `1200px` for fixed width. |
| Module Configuration | Footer Height (`advf_f_height`) | `280px` | Defines the minimum height of the footer. Ensures a consistent visual presence. |
| Module Configuration | Footer Background Color (`advf_f_bg`) | (Your Brand Color) | Sets the solid background color for the footer. Crucial for branding and contrast. |
| Module Configuration | Footer Text Color (`advf_f_color`) | (Contrasting Color) | Sets the default text color in the footer. Ensures readability against the background. |
| Module Configuration | Footer Link Hover Color (`advf_f_color_hover`) | (Subtle Accent) | Defines the color of links when hovered over. Improves user interaction feedback. |
| Module Configuration | Footer Background Image URL (`advf_f_bg_url`) | Leave empty | URL to an image to use as the footer background. Adds visual texture or branding. |
| Module Configuration | Footer Background Image Position (`advf_f_bg_pos`) | `center center` | How the background image is positioned. `center center` for most single images. |
| Module Configuration | Footer Background Image Repeat (`advf_f_bg_repeat`) | `no-repeat` | How the background image tiles. `no-repeat` for single images, `repeat` for patterns. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My footer changes aren’t showing up on the front office.**
**A1:** This is usually a caching issue.
\* Go to **Advanced Parameters > Performance** in your PrestaShop Back Office.
\* Click “Clear cache” (or “Clear Smarty cache” in older versions).
\* If you use a third-party caching module or server-level caching (like Varnish), clear those caches as well.
\* Also, try clearing your browser’s cache (Ctrl+F5 or Cmd+Shift+R).

**Q2: The footer looks different on mobile devices than on desktop.**
**A2:** This is expected and usually a good thing! Modern PrestaShop themes are responsive, meaning they adapt the layout for different screen sizes. The module’s settings (like `Footer Width: 100%`) are designed to work with this. If specific elements look broken, it might be a conflict with your theme’s CSS.
\* **Troubleshooting:** Check your theme’s mobile-specific CSS. If you’ve added custom HTML content to the footer, ensure that content is also responsive. You might need a webmaster to inspect the CSS.

**Q3: How do I add actual content (links, text, images) into this advanced footer?**
**A3:** This module primarily provides the *styling* framework (background, colors, dimensions) for your footer. The *content* of the footer is typically managed by your PrestaShop theme’s footer hooks (like `displayFooter`) or by other modules designed for content blocks (e.g., a custom HTML block module, or PrestaShop’s built-in Link List module).
\* **Solution:** After configuring the Advanced Footer’s style, you’ll need to use your theme’s options or other content modules to populate the `displayFooter` hook with your desired links, text, and images. The Advanced Footer module will then apply its styling to that content.

**Q4: The colors I set don’t seem to be applied to all elements in my footer.**
**A4:** This can happen if your theme has very specific CSS rules that override the module’s styles.
\* **Troubleshooting:** The module applies general footer styling. If your theme has more specific rules (e.g., for `ul li a` inside the footer), those might take precedence. You might need to consult a webmaster to add custom CSS to your theme to override specific elements, or adjust your theme’s settings if it has a dedicated footer customization section.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The Advanced Footer module is a standard PrestaShop module primarily focused on front-office styling. It leverages PrestaShop’s configuration system (`Configuration::updateValue`) to store its settings and hooks into `displayFooter` to inject its custom CSS and JavaScript. It does not introduce new database tables or complex ObjectModels, making it lightweight and focused on its core task: footer customization. The module uses a `getContent()` method for its back-office configuration, rendering a standard PrestaShop form.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. The module directly hooks into `displayFooter` and `footer` to render its content and apply styles.
- **Back-Office Admin Controllers**: None. All configuration is handled within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

- No custom classes or ObjectModels are defined in the `classes/` directory. All logic is contained within the `advfooter.php` main module file.

### 4.4 JavaScript Assets (`views/js/`)

- `advfooter/js/advajax.js`:
  - **Scope:** Back-office.
  - **Responsibility:** Likely handles AJAX requests related to saving module configuration settings without a full page reload, or provides dynamic feedback within the configuration form.
- `advfooter/js/foscript.js`:
  - **Scope:** Front-office.
  - **Responsibility:** This script would contain any client-side logic or dynamic behavior specific to the advanced footer on the customer-facing side. This could include responsive adjustments, specific hover effects not handled by CSS, or interactions with embedded content.
- `advfooter/js/jscolor/jscolor.js`:
  - **Scope:** Back-office.
  - **Responsibility:** This is a third-party JavaScript library for providing a color picker widget in the Back Office. It’s used to allow merchants to visually select colors for background, text, and hover effects.
- `advfooter/js/script.js`:
  - **Scope:** Back-office.
  - **Responsibility:** General-purpose script for the module’s Back Office configuration page. It might initialize the `jscolor` picker, handle form validation, or other UI enhancements for the admin interface.

### 4.5 CSS Stylesheets (`views/css/`)

- `advfooter/css/fancybox.css`:
  - **Scope:** Front-office (potentially, if the module uses Fancybox for any embedded content or images).
  - **Responsibility:** Provides styling for the Fancybox lightbox library, which is commonly used for displaying images, videos, or other content in a modal overlay. Its presence suggests the module might support such functionality, or it’s included as a general utility.
  - **Key CSS class selectors:** `.fancybox-overlay`, `.fancybox-wrap`, `.fancybox-inner`, etc. Developers can override these to customize the lightbox appearance.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - `advfooter/footer.tpl`:
    - **Hook:** `displayFooter` (and potentially `footer` for older themes).
    - **Output:** This template is responsible for rendering the main structure of the advanced footer. It will likely contain a `div` or `footer` HTML element with dynamic inline styles or class attributes populated by the module’s configuration settings (e.g., `width`, `height`, `background-color`, `background-image`, `color`). It acts as the container for any content that other modules or the theme place into the `displayFooter` hook.
- **Admin templates (`views/templates/admin/`)**: None. The configuration form is likely rendered directly within `getContent()` using PrestaShop’s `HelperForm` or similar.
- **Front-office templates (`views/templates/front/`)**: None.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any custom SQL tables.
  - Configuration settings are stored in the `ps_configuration` table using the keys: `ADVF_F_WIDTH`, `ADVF_F_HEIGHT`, `ADVF_F_BG`, `ADVF_F_COLOR`, `ADVF_F_COLOR_HOVER`, `ADVF_F_BG_URL`, `ADVF_F_BG_POS`, `ADVF_F_BG_REPEAT`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Executed in the `<head>` section of every page. | Used to register CSS and JavaScript assets (`foscript.js`, `fancybox.css`) for the front-office, and potentially inject inline styles based on module configuration. |
| `displayBackOfficeHeader` | Executed in the `<head>` section of every Back Office page. | Used to register CSS and JavaScript assets (`advajax.js`, `jscolor.js`, `script.js`) for the module’s configuration page. |
| `displayFooter` | Executed at the bottom of the page, typically before the closing `</body>` tag. | Renders the `footer.tpl` template, which applies the custom styling and acts as the container for the footer content. |
| `footer` | (PrestaShop 1.6 and older, or for specific theme compatibility) | Similar to `displayFooter`, used to render footer content. The module likely registers to both for broader compatibility. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please log in to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). You will find your purchased modules and direct access to support resources there.
