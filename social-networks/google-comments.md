---
title: "Google+ Comments - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Google+ Comments PrestaShop module by MyPresta.eu."
sidebar:
  label: "Google+ Comments - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Google+ Comments Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/google-comments.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/google-comments/)
>
> ---


# Google+ Comments

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the Google+ Comments module. You’ll find all the settings here to control how the comments appear and function on your store.

**Access:** Navigate to **Modules > Module Manager**, search for “Google+ Comments”, and click **“Configure”**.

#### Settings & Options

1. **Display Google+ Comments on Product Page**

   - **What this setting does:** This switch controls whether the Google+ comment section is shown on your product pages.
   - **Effect of changing this setting:**
     - *When enabled (YES):* The Google+ comment section will appear on all your product pages, allowing customers to view and add comments.
     - *When disabled (NO):* The Google+ comment section will be hidden from all product pages.
   - **Recommended value:** YES (if you want to use the commenting feature).
   - **Merchant scenario / example:** If you want to encourage customer interaction and leverage user-generated content, enable this. If you prefer a different commenting system or no comments at all, disable it.
2. **Choose Hook for Google+ Comments**

   - **What this setting does:** This dropdown allows you to select where on the product page (or other pages) the Google+ comment block will be displayed. Hooks are specific locations in your PrestaShop theme where modules can inject content.
   - **Effect of changing this setting:**
     - *Selecting `displayProductExtraContent` (or similar product page hook):* The comments will appear within the main content area of the product page, typically below the product description or tabs. This is the most common and recommended placement.
     - *Selecting `displayLeftColumn` or `displayRightColumn`:* The comments block will appear in the left or right sidebar of your store (if your theme has them and they are active on product pages). This is generally not ideal for a full comment section.
     - *Selecting `displayFooter`:* The comments block will appear in the footer section of your store. Again, not ideal for product-specific comments.
   - **Recommended value:** `displayProductExtraContent` or a similar hook that places the comments directly on the product page content area. The exact hook name might vary slightly between PrestaShop versions or themes, but aim for one that integrates well with product details.
   - **Merchant scenario / example:** You want the comments to be easily visible when a customer is reviewing a product. Choosing `displayProductExtraContent` ensures it’s part of the product’s main information flow.
3. **Width of Google+ Comments Block (in pixels)**

   - **What this setting does:** This input field allows you to define the fixed width of the Google+ comment section in pixels.
   - **Effect of changing this setting:**
     - *Setting a specific pixel value (e.g., `600`):* The comment block will always try to render at that exact width. If the screen is smaller, it might overflow or cause layout issues.
     - *Leaving empty or setting to `100%` (if allowed by the module, though typically expects pixels):* The module might try to auto-adjust, but for Google+ comments, a fixed pixel width is often expected.
   - **Recommended value:** A value that fits well within your product page’s main content area, typically `600` to `800` pixels, depending on your theme’s layout. You may need to experiment to find the best fit.
   - **Merchant scenario / example:** Your product page content area is 700px wide. Setting this to `650`px ensures the comment block fits nicely without breaking the layout.
4. **Number of Comments to Display**

   - **What this setting does:** This input field controls how many comments are initially loaded and displayed in the Google+ comment section. More comments can usually be loaded by the user clicking a “Load More” button provided by Google.
   - **Effect of changing this setting:**
     - *Setting a low number (e.g., `5`):* Only a few comments will show initially, making the page load faster and appear less cluttered. Users will need to click to see more.
     - *Setting a high number (e.g., `20`):* More comments will be visible immediately, which can be good for highly commented products but might make the page longer.
   - **Recommended value:** `5` to `10`. This provides a good balance between showing engagement and keeping the page concise.
   - **Merchant scenario / example:** You have many comments on popular products. Setting this to `7` shows enough engagement without overwhelming the customer with a very long scroll.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Display Google+ Comments on Product Page | YES | Enables/disables the comment section on product pages. |
| Module Configuration | Choose Hook for Google+ Comments | `displayProductExtraContent` | Determines where the comment block appears on the page. |
| Module Configuration | Width of Google+ Comments Block (in pixels) | `600` - `800` | Sets the fixed width of the comment section. Adjust to fit your theme. |
| Module Configuration | Number of Comments to Display | `5` - `10` | Controls how many comments are initially visible. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: The comments section isn’t showing up on my product pages after installation.**
A:

1. **Check Module Configuration:** Go to **Modules > Module Manager > Google+ Comments > Configure**. Ensure “Display Google+ Comments on Product Page” is set to YES.
2. **Verify Hook Selection:** Make sure the “Choose Hook for Google+ Comments” is set to a relevant product page hook like `displayProductExtraContent`. If your theme uses a custom hook for product content, you might need to select that or consult your theme developer.
3. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache”). Sometimes, PrestaShop’s cache prevents new module content from appearing immediately.
4. **Theme Compatibility:** Some highly customized themes might override standard PrestaShop hooks. If the issue persists, contact your theme developer or MyPresta.eu support.

**Q: The comments section looks too wide/narrow or breaks my layout.**
A:

1. **Adjust Width Setting:** In the module configuration, modify the “Width of Google+ Comments Block (in pixels)” setting. Experiment with different values (e.g., 600, 700, 800) until it fits your product page layout.
2. **Check Theme CSS:** If adjusting the width doesn’t help, your theme’s CSS might be interfering. You may need a webmaster to inspect the element and add custom CSS to your theme to ensure proper display.

**Q: Can I moderate the comments before they appear?**
A: The Google+ Comments module uses Google’s own commenting system. Moderation capabilities are typically handled within the Google platform itself, not directly within PrestaShop. You would need to check Google’s policies and tools for comment moderation related to embedded widgets.

**Q: My customers are having trouble posting comments.**
A:

1. **Google Account Requirement:** Remind customers that they need to be logged into a Google account to post comments.
2. **Browser Issues:** Advise customers to try a different browser or clear their browser’s cache and cookies.
3. **Google Service Status:** Occasionally, Google services might experience temporary outages. Check Google’s status pages if many users report issues simultaneously.

**Q: Does this module still work since Google+ was shut down?**
A: While Google+ as a social network has been deprecated, Google still provides embedded commenting widgets that leverage Google accounts. This module integrates with that underlying Google commenting infrastructure. It may not provide the direct “SEO boost” from “+1s” as it once did, but it still functions as a Google-powered commenting system.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a technical overview for developers and webmasters working with the Google+ Comments module.

### 4.1 Architecture Overview

The `Google+ Comments` module is a straightforward PrestaShop module primarily implemented within its main PHP file (`google-comments.php`). It leverages PrestaShop’s `Module` class and `Configuration` class to manage settings. Its core functionality involves injecting a Google-provided JavaScript snippet into the front-office, which then renders the comment widget. There are no custom controllers, models, or complex AJAX interactions within the module itself; it relies heavily on Google’s external script for its front-end functionality.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. The module’s front-office display is handled by hooking into standard PrestaShop display hooks and rendering a Smarty template containing the Google comment embed code.
- **Back-Office Admin Controllers**: None. All configuration is handled via the `getContent()` method in the main module file.

### 4.3 Core Classes & Models (`classes/`)

- No custom classes or `ObjectModel` definitions are present in this module. All data is stored directly in PrestaShop’s `ps_configuration` table.

### 4.4 JavaScript Assets (`views/js/`)

- No custom JavaScript files are included in this module. The module’s functionality relies entirely on the external Google JavaScript library that it embeds.

### 4.5 CSS Stylesheets (`views/css/`)

- No custom CSS files are included in this module. The styling of the Google comment widget is controlled by Google’s own embedded styles. Any custom styling would need to target the generated Google iframe/elements via theme overrides (which can be challenging due to cross-domain iframe restrictions).

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses a single Smarty template to render the Google comment widget.

- **Hook templates (`views/templates/hook/`)**:
  - `googlecomments.tpl`: This template is rendered when the module is hooked. It contains the HTML structure for the Google comment widget, including the `<div>` element with the `data-href`, `data-width`, and `data-num-comments` attributes, and the `script` tag to load the Google Platform JavaScript SDK.
    - **Purpose:** To embed the Google comment widget on the front-office.
    - **Variables used:**
      - `{$link->getModuleLink('googlecomments', 'ajax', array(), true)|escape:'htmlall':'UTF-8'}`: This is likely a remnant or placeholder as the module doesn’t use an AJAX controller. The `data-href` attribute for Google comments typically points to the canonical URL of the page where comments are being displayed (e.g., the product page URL).
      - `{Configuration::get('GOOGLE_COMMENTS_WIDTH')}`: Retrieves the configured width for the comment block.
      - `{Configuration::get('GOOGLE_COMMENTS_NUM')}`: Retrieves the configured number of comments to display.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  The module does not create any custom database tables. All its configuration settings are stored in the `ps_configuration` table:

  - `GOOGLE_COMMENTS_ENABLED`: Stores `1` (enabled) or `0` (disabled) for displaying comments.
  - `GOOGLE_COMMENTS_HOOK`: Stores the name of the selected hook (e.g., `displayProductExtraContent`).
  - `GOOGLE_COMMENTS_WIDTH`: Stores the width of the comment block in pixels.
  - `GOOGLE_COMMENTS_NUM`: Stores the number of comments to display.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Used to register assets (though this module doesn’t use it for that, it’s a common hook). |
| `displayProductExtraContent` | Within the main content area of a product page, often in a tab or below description. | **Primary hook for displaying the comment block on product pages.** |
| `displayLeftColumn` | In the left sidebar of the store. | Optional hook for displaying the comment block (less common for full comments). |
| `displayRightColumn` | In the right sidebar of the store. | Optional hook for displaying the comment block (less common for full comments). |
| `displayFooter` | In the footer section of the store. | Optional hook for displaying the comment block (less common for full comments). |
| `actionFrontControllerSetMedia` | Before the front controller renders the page, allowing modules to add JS/CSS. | Used to add the Google Platform JavaScript SDK to the page. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the Google+ Comments module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to providing assistance and ensuring the smooth operation of your modules.
