---
title: "HomeFeatured Pro Rollover - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the HomeFeatured Pro Rollover PrestaShop module by MyPresta.eu."
sidebar:
  label: "HomeFeatured Pro Rollover"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy HomeFeatured Pro Rollover Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/homefeatured-pro-rollover.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/homefeatured-pro-rollover/)
>
> ---


# HomeFeatured Pro Rollover

## 1. Requirements & Compatibility
- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient and usually pre-installed on most web hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)
After installation, click "Configure" next to "HomeFeatured Pro Rollover" in the Module Manager to access its settings.

#### 2.1.1 Number of products to be displayed
-   **What this setting does:** This controls how many featured products will be shown in the "Featured Products" section on your homepage.
-   **Effect of changing this setting:**
    -   *When set to a specific number (e.g., 8):* Your homepage will display exactly that many products from your "Home" category (or whichever category you've designated for featured products).
    -   *When set to a different number:* The number of products displayed will change accordingly. If you set it too high, it might make your homepage very long; if too low, you might not showcase enough products.
-   **Recommended value:** A number that fits well within your homepage layout, typically between 8 and 12 for a standard grid.
-   **Merchant scenario / example:** If you want to highlight your top 8 best-sellers on the homepage, you would set this to "8". If you have a wider layout and want to show more variety, you might increase it to "12".

#### 2.1.2 Display attributes on product page
-   **What this setting does:** This is a standard PrestaShop setting that controls whether product attributes (like size, color) are displayed on the product page itself. While this module primarily affects the homepage, this setting is often included in modules that interact with product displays.
-   **Effect of changing this setting:**
    -   *When enabled (Yes):* Product attributes will be visible and selectable on individual product pages.
    -   *When disabled (No):* Product attributes will not be shown on product pages, potentially simplifying the page but removing important selection options for customers.
-   **Recommended value:** **Yes**. Most stores need to display attributes for products with variations.
-   **Merchant scenario / example:** For a clothing store, customers need to select size and color. Enabling this ensures those options appear on the product page. Disabling it would make it impossible for customers to choose variations.

#### 2.1.3 Default language
-   **What this setting does:** This setting specifies the default language for your store. It's a core PrestaShop setting often referenced by modules to ensure proper language handling.
-   **Effect of changing this setting:**
    -   *When set to your primary language (e.g., English):* The module will use this language for any language-dependent data or fallbacks if translations are missing.
-   **Recommended value:** **Your store's primary language.** This should match the default language you've set in PrestaShop's localization settings.
-   **Merchant scenario / example:** If your store's main audience is in France, you would set this to "French" to ensure all default text and product information is correctly displayed in French.

#### 2.1.4 Number of products to be displayed (Duplicate of 4.1.1)
-   **What this setting does:** This is a duplicate of the "Number of products to be displayed" setting (HOME\_FEATURED\_PRO\_NBR). It controls the same aspect: how many featured products appear on your homepage.
-   **Effect of changing this setting:** Changing this will directly alter the count of products shown in the featured section.
-   **Recommended value:** Refer to section 4.1.1.
-   **Merchant scenario / example:** Refer to section 4.1.1.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|---|
| Module Configuration | Number of products to be displayed (HOME\_FEATURED\_PRO\_NBR) | 8-12 (depends on layout) | Sets the count of featured products on the homepage. |
| Module Configuration | Display attributes on product page (PS\_ATTRIBUTE\_CATEGORY\_DISPLAY) | Yes | Controls visibility of product attributes on product pages. |
| Module Configuration | Default language (PS\_LANG\_DEFAULT) | Your store's primary language | Specifies the default language for the store. |
| Module Configuration | Number of products to be displayed (HOME\_FEATURED\_NBR) | Same as HOME\_FEATURED\_PRO\_NBR | Duplicate setting for the count of featured products. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: The rollover effect isn't working on my homepage.**
A:
1.  **Check Module Status:** Ensure the "HomeFeatured Pro Rollover" module is installed and enabled in **Modules > Module Manager**.
2.  **Clear Cache:** Go to **Advanced Parameters > Performance** and click "Clear cache" (or "Clear Smarty cache" in older versions). Sometimes, old cache prevents new module changes from appearing.
3.  **Product Images:** Verify that the featured products actually have *at least two* images uploaded in their product settings (**Catalog > Products > [Edit Product] > Images tab**). The module needs a second image to display on hover.
4.  **Theme Compatibility:** While the module is designed for broad compatibility, very heavily customized themes might require minor CSS adjustments. If the issue persists, contact MyPresta.eu support.

**Q: My homepage looks broken after installation.**
A:
1.  **Immediate Action:** If your store becomes unusable, disable the module immediately from **Modules > Module Manager**.
2.  **Check PrestaShop Version:** Ensure you downloaded the correct module version for your PrestaShop installation (e.g., PS 8.x version for PrestaShop 8.x).
3.  **Theme Conflicts:** Some themes might have their own "featured products" logic that conflicts. Try temporarily switching to the default PrestaShop theme (Classic) to see if the issue resolves. If it does, the problem is theme-related.
4.  **Contact Support:** Provide MyPresta.eu support with details about your PrestaShop version, theme, and any error messages you see.

**Q: How do I change which products are "featured"?**
A: The module uses PrestaShop's standard "Featured Products" mechanism. To change which products appear:
1.  Go to **Catalog > Categories**.
2.  Find the category named "Home" (or the category you've designated as your homepage category).
3.  Edit this category and go to the "Products" tab.
4.  You can add or remove products from this category to control what appears in your featured section.

**Q: The images are not perfectly aligned or sized during rollover.**
A: This usually indicates a CSS conflict with your theme.
1.  **Image Dimensions:** Ensure all product images (especially the first and second ones) are uploaded with consistent aspect ratios and similar dimensions. PrestaShop automatically resizes them, but large differences can cause layout shifts.
2.  **Theme Customization:** Your theme's CSS might be overriding the module's styling. A webmaster can inspect the element using browser developer tools to identify conflicting CSS rules and apply a fix in your theme's custom CSS file.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview
The HomeFeatured Pro Rollover module (`homefeaturedpro`) is a straightforward PrestaShop module designed to override and enhance the default `homefeatured` module's functionality. It primarily focuses on front-office display, specifically injecting JavaScript and CSS to enable the image rollover effect on the homepage's featured products. It leverages PrestaShop's hook system to integrate its logic and templates. The module does not introduce new database tables or complex ObjectModels, instead relying on existing PrestaShop product data.

### 4.2 Controllers (`controllers/`)
This module does not introduce any custom Front-Office or Back-Office Admin Controllers. All configuration is handled via the main module file's `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)
This module does not introduce any custom classes or ObjectModels. It operates by extending existing PrestaShop functionality and rendering its own templates.

### 4.4 JavaScript Assets (`views/js/`)
This module does not include any custom JavaScript files. The rollover effect is achieved purely through CSS.

### 4.5 CSS Stylesheets (`views/css/`)
-   **`homefeaturedpro/homefeatured.css`**
    *   **Scope:** Front-office customer styling.
    *   **Main UI components and containers it styles:** This stylesheet contains the core CSS rules responsible for the image rollover effect. It targets product image containers within the featured products section, likely using selectors like `.product-container .product-image`, `.product-image-container`, or similar, to hide the second image by default and display it on hover.
    *   **Key CSS class selectors developers can override in their theme:**
        *   `.product-image-container .img-hover`: Likely controls the visibility and positioning of the second image.
        *   `.product-image-container .img-primary`: Controls the primary image.
        *   Styles related to `transition` properties for smooth image changes.
        *   `overflow: hidden` on the image container to manage image swapping.

### 4.6 Smarty Template Structure (`views/templates/`)

-   **`homefeaturedpro/homefeatured.tpl`**
    *   **Scope:** Front-office.
    *   **Hook:** Primarily rendered in `displayHome` or `Home` (depending on PrestaShop version and theme configuration).
    *   **Purpose:** This is the main template responsible for rendering the featured products grid on the homepage. It iterates through the `$products` variable (passed from the module's `hookDisplayHome` method) and for each product, it generates the HTML structure including the primary and secondary images, product name, price, and other details. It's designed to work with PrestaShop 1.7.x and newer. The logic within this template is crucial for displaying both images and applying the necessary CSS classes for the rollover effect.

-   **`homefeaturedpro/homefeatured14.tpl`**
    *   **Scope:** Front-office.
    *   **Hook:** Likely intended for older PrestaShop versions (e.g., 1.4.x, 1.5.x, 1.6.x) if the module supports them, or as an alternative for specific theme structures.
    *   **Purpose:** This template serves the same purpose as `homefeatured.tpl` but is structured to be compatible with older PrestaShop template syntaxes and HTML structures. It would also iterate through products and render the necessary image elements for the rollover effect. For modern PrestaShop versions (1.7+), `homefeatured.tpl` is the primary template used.

### 4.7 Database Schema & Hooks Map

-   **Database Tables**:
    *   The module does not create any custom database tables.
    *   It stores its configuration settings in the `ps_configuration` table using the following keys:
        *   `HOME_FEATURED_PRO_NBR`: Stores the number of featured products to display.
        *   `PS_ATTRIBUTE_CATEGORY_DISPLAY`: (Standard PrestaShop config, potentially referenced or set by the module).
        *   `PS_LANG_DEFAULT`: (Standard PrestaShop config, potentially referenced or set by the module).
        *   `HOME_FEATURED_NBR`: (Duplicate of `HOME_FEATURED_PRO_NBR`, likely for backward compatibility or internal consistency).

-   **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
|---|---|---|
| `displayHeader` | In the `<head>` section of every front-office page. | Used to include the module's CSS stylesheet (`homefeatured.css`) to ensure the rollover styles are loaded before the page content. |
| `header` | Alias for `displayHeader`. | Same as `displayHeader`. |
| `Home` | On the homepage, typically in the main content area. | Renders the module's featured products template (`homefeatured.tpl` or `homefeatured14.tpl`) and passes the product data to it. |
| `displayHome` | Alias for `Home` in modern PrestaShop versions. | Same as `Home`. |

## 5. Official Support & Updates
For official updates, technical support, and further assistance with the HomeFeatured Pro Rollover module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to help with any issues or questions you may have.
