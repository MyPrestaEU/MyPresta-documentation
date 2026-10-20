---
title: "Show tags on product page - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Show tags on product page PrestaShop module by MyPresta.eu."
sidebar:
  label: "Show tags on product page - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Show tags on product page Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/show-tags-on-product-page.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/show-tags-on-product-page/)
>
> ---


# Show tags on product page

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) typically found on any modern PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This module features a straightforward configuration page, allowing you to quickly enable or disable its functionality and choose where the tags will appear on your product pages.

**Access:** Navigate to **Modules > Module Manager**, search for “Show tags on product page”, and click “Configure”.

#### **Enable / Disable Module**

- **What this setting does:** This is the master switch for the module’s functionality.
- **Effect of changing this setting:**
  - *When enabled:* The module will start displaying product tags on your front office product pages according to your chosen hook.
  - *When disabled:* The module will cease to display product tags. All other settings will be saved but inactive.
- **Recommended value:** YES
- **Merchant scenario / example:** You want to test the module or temporarily hide tags during a site redesign. You would disable it and then re-enable when ready.

#### **Select Hook to Display Tags**

- **What this setting does:** This crucial setting determines *where* on your product page the tags will be displayed. PrestaShop uses “hooks” as specific points in the page’s code where modules can insert their content.
- **Effect of changing this setting:**
  - *When set to `displayProductButtons` (PrestaShop 1.7+):* Tags will typically appear near the “Add to Cart” button or other product action buttons. This is often a prominent and effective location.
  - *When set to `displayProductExtraContent` (PrestaShop 1.7+):* Tags will appear in a dedicated section for extra product content, often below the main product information or within a tab.
  - *When set to `displayFooterProduct` (PrestaShop 1.7+):* Tags will appear at the bottom of the product page, often above the footer of the entire website.
  - *When set to `displayLeftColumnProduct` (PrestaShop 1.7+):* Tags will appear in the left column specifically on the product page.
  - *When set to `displayRightColumnProduct` (PrestaShop 1.7+):* Tags will appear in the right column specifically on the product page.
  - *Other hooks (e.g., `displayProductTab`, `displayProductTabContent`, `displayFooter`):* The exact placement will depend on your theme’s implementation of these hooks. `displayFooter` would place tags in the general website footer, which is usually not product-specific.
- **Recommended value:** `displayProductButtons` or `displayProductExtraContent` are generally the most effective for visibility and context. Experiment to see what looks best with your theme.
- **Merchant scenario / example:** You want tags to be highly visible to encourage immediate discovery of similar products, so you choose `displayProductButtons`. If you prefer them to be less intrusive and part of supplementary information, `displayProductExtraContent` might be better.

#### **Title for Tags Block**

- **What this setting does:** This allows you to set a custom title that will appear above the list of tags on the product page.
- **Effect of changing this setting:**
  - *When a title is entered (e.g., “Product Tags”, “Related Keywords”):* This title will be displayed above the list of tags, providing a clear heading for your customers.
  - *When left empty:* No title will be displayed, and only the list of tags will appear.
- **Recommended value:** “Product Tags” or “Keywords”
- **Merchant scenario / example:** You want to clearly label the section so customers understand its purpose. Setting the title to “Related Tags” helps guide their interaction.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable Module | YES | Activates/deactivates the module’s tag display functionality. |
| Module Configuration | Select Hook to Display Tags | `displayProductButtons` or `displayProductExtraContent` | Determines the exact position of the tags on the product page. |
| Module Configuration | Title for Tags Block | “Product Tags” | Sets a heading for the displayed tags, improving clarity for customers. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve installed and configured the module, but the tags aren’t showing on my product pages. What’s wrong?**
**A1:**

- **Check Module Status:** Ensure the module is “Enabled” in its configuration.
- **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). PrestaShop often caches content, and new module output might not appear until the cache is cleared.
- **Verify Product Tags:** Make sure the specific product you are viewing actually has tags assigned to it. Edit the product in the Back Office and check the “SEO” or “Tags” tab.
- **Theme Compatibility:** Some highly customized themes might override standard PrestaShop hooks or have unique layouts. Try switching to the default PrestaShop theme (e.g., Classic) temporarily to see if the tags appear. If they do, your custom theme might require a small adjustment (see Q3).
- **Hook Selection:** Double-check that you’ve selected an appropriate hook in the module’s configuration. Some hooks might not be rendered by your theme in a visible location.

**Q2: The tags are showing, but they look plain or don’t match my theme’s style.**
**A2:**

- The module provides basic styling. If you want them to perfectly match your theme, you’ll need to add custom CSS.
- **How to do it:**
  1. Inspect the tags on your product page using your browser’s developer tools (right-click, then “Inspect”).
  2. Identify the CSS classes used by the tags (e.g., `ptags_block`, `ptags_item`).
  3. Add custom CSS rules to your theme’s `custom.css` file (if it has one) or directly in the module’s `ptags.css` file (though modifying module files directly is not recommended as updates will overwrite them).
  - **Example CSS:**

    ```
    .ptags\_block { margin-top: 20px; padding: 15px; border: 1px solid #eee; background-color: #f9f9f9;}.ptags\_block h3 { font-size: 18px; color: #333; margin-bottom: 10px;}.ptags\_item { display: inline-block; margin-right: 8px; margin-bottom: 8px;}.ptags\_item a { background-color: #007bff; color: white; padding: 5px 10px; border-radius: 3px; text-decoration: none; font-size: 14px;}.ptags\_item a:hover { background-color: #0056b3;}
    ```

**Q3: The tags appear, but they are in an awkward position, or I want them in a very specific spot not listed in the hook options.**
**A3:**

- The module relies on standard PrestaShop hooks. If you need a highly specific, non-standard placement, it usually requires theme modification.
- **Solution:** You or your web developer would need to manually insert the module’s display function into your theme’s product page template (`product.tpl` or `product-details.tpl` in your theme folder).
  - Find the exact location in your theme’s `.tpl` file where you want the tags to appear.
  - Insert the following Smarty code: `{hook h='displayProductTags' product=$product}` (Note: `displayProductTags` is a custom hook name you’d register in the module, or you can use `displayProductButtons` if that’s what you configured).
  - Alternatively, you can call the module directly: `{Module::getInstanceByName('ptags')->hookDisplayProductTags(['product' => $product])}`. This is more direct but less flexible than using a hook.
- **Important:** This requires basic knowledge of PrestaShop theme development.

**Q4: Will this module slow down my store?**
**A4:**

- No, this module is very lightweight. It performs a simple database query to fetch tags associated with the current product. This operation is highly optimized by PrestaShop’s core and will not noticeably impact your page load times.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Show tags on product page” module (`ptags`) is a straightforward PrestaShop module designed to extend front-office functionality. It follows a classic PrestaShop module architecture, primarily leveraging the `Module` class and its `install()`, `uninstall()`, and `hook` methods. It does not introduce custom controllers, models, or complex JavaScript. Its core function is to fetch product tags and render them via a Smarty template in a chosen front-office hook.

### 4.2 Controllers (`controllers/`)

This module does **not** contain any custom Front-Office or Back-Office controllers. All logic is encapsulated within the main module class (`ptags/index.php`) and executed via PrestaShop’s hook system.

### 4.3 Core Classes & Models (`classes/`)

This module does **not** introduce any custom classes or `ObjectModel` definitions. It directly utilizes PrestaShop’s core `Tag` and `Product` classes to retrieve necessary data.

### 4.4 JavaScript Assets (`views/js/`)

This module does **not** contain any custom JavaScript files. Its functionality is purely server-side rendering of HTML.

### 4.5 CSS Stylesheets (`views/css/`)

- **File Path**: `ptags/views/css/ptags.css`
- **Scope**: Front-office customer styling.
- **Main UI components and containers it styles**: This stylesheet provides basic styling for the block containing the product tags and the individual tag links.
- **Key CSS class selectors developers can override in their theme**:
  - `.ptags_block`: Styles the main container block for the tags.
  - `.ptags_block h3`: Styles the title of the tags block.
  - `.ptags_item`: Styles each individual tag item (e.g., `display: inline-block`, margins).
  - `.ptags_item a`: Styles the clickable tag links (e.g., background, color, padding, border-radius).

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - **File Path**: `ptags/views/front/ptags.tpl`
  - **Rendered in hook**: This template is rendered by the module’s `hook` methods (e.g., `hookDisplayProductButtons`, `hookDisplayProductExtraContent`, etc., depending on configuration).
  - **Visual block output**: This template is responsible for outputting the HTML structure for the tags block, including the optional title and the list of clickable tag links. It iterates through the `$tags` variable (an array of tag objects) passed from the module’s hook method.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: This module does not create any custom database tables. It relies on existing PrestaShop tables, primarily `ps_tag`, `ps_product_tag`, and `ps_lang` for tag data.

  - Configuration settings are stored in `ps_configuration` with keys like `PTAGS_ENABLED`, `PTAGS_HOOK`, `PTAGS_TITLE`.
- **Registered Hooks Table**:

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `displayHeader` | In the `<head>` section of every page. | Used to load the module’s CSS stylesheet (`ptags.css`). |
  | `displayProductButtons` | On the product page, typically near the “Add to Cart” button. | Displays the product tags block. (PrestaShop 1.7+) |
  | `displayProductExtraContent` | On the product page, in a dedicated section for extra content. | Displays the product tags block. (PrestaShop 1.7+) |
  | `displayFooterProduct` | At the bottom of the product page content. | Displays the product tags block. (PrestaShop 1.7+) |
  | `displayLeftColumnProduct` | In the left column specifically on the product page. | Displays the product tags block. (PrestaShop 1.7+) |
  | `displayRightColumnProduct` | In the right column specifically on the product page. | Displays the product tags block. (PrestaShop 1.7+) |
  | `displayProductTab` | Adds a new tab to the product page. | (If configured) Displays the product tags within a tab. |
  | `displayProductTabContent` | Content for a product page tab. | (If configured) Displays the product tags as content for a tab. |
  | `displayFooter` | In the general website footer. | (If configured) Displays the product tags block in the global footer. |
  | `displayLeftColumn` | In the left column of pages (not product-specific). | (If configured) Displays the product tags block in the global left column. |
  | `displayRightColumn` | In the right column of pages (not product-specific). | (If configured) Displays the product tags block in the global right column. |

  The module dynamically registers itself to the hook selected in its configuration. The `index.php` file contains the `hook[HookName]` methods that fetch the product ID, retrieve associated tags, and pass them to `ptags.tpl` for rendering.

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Show tags on product page” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist merchants and developers with any issues or questions related to the module’s functionality and integration.
