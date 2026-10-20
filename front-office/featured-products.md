---
title: "Featured Products - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Featured Products PrestaShop module by MyPresta.eu."
sidebar:
  label: "Featured Products - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Featured Products Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/featured-products.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/featured-products/)
>
> ---


# Featured Products

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are required.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

To access the configuration, navigate to **Modules > Module Manager**, search for “Featured Products,” and click “Configure.”

This screen allows you to define which products are displayed and how they appear on your homepage.

#### Settings & Options:

1. **Source Category ID**

   - **What this setting does:** This is the most crucial setting. It determines *which* category’s products will be displayed as “featured” on your homepage. You need to enter the numerical ID of the category you wish to showcase.
   - **Effect of changing this setting:**
     - *When set to a valid Category ID (e.g., `3` for “Clothes”):* The module will fetch and display products belonging to the category with that ID.
     - *When set to an invalid or non-existent ID:* No products will be displayed, or an error might occur if the ID is malformed.
   - **Recommended value:** The ID of the category you want to promote.
   - **Merchant scenario / example:** If you want to feature your “New Arrivals” category (which has an ID of, say, `12`), you would enter `12` here. To find a category ID, go to **Catalog > Categories** in your Back Office, click “Edit” on a category, and look at the URL in your browser (e.g., `id_category=12`).
2. **Number of Products**

   - **What this setting does:** This controls how many products from your selected “Source Category” will be displayed on the homepage.
   - **Effect of changing this setting:**
     - *When set to `5`:* Only the first 5 products from the chosen category will be shown.
     - *When set to `10`:* Up to 10 products will be displayed.
   - **Recommended value:** A reasonable number like `8` or `12` to avoid overwhelming the homepage, but enough to showcase variety. Consider your theme’s layout.
   - **Merchant scenario / example:** If your “New Arrivals” category has 50 products, but you only want to show the latest 8 on the homepage, you would set this to `8`.
3. **Placement Position**

   - **What this setting does:** This determines *how* the featured products are displayed on your homepage: either directly in the main content area (`displayHome`) or within a tab (`displayHomeTabContent`).
   - **Effect of changing this setting:**
     - *When set to `Homepage Tab`:* The products will appear under a new tab on your homepage (e.g., “Featured Products”). This requires your theme to support homepage tabs.
     - *When set to `Homepage`:* The products will be displayed as a standalone section directly on your homepage, without being hidden behind a tab.
   - **Recommended value:**
     - Choose `Homepage Tab` if your theme uses tabs for product listings (like default PrestaShop themes often do) and you want to keep your homepage clean.
     - Choose `Homepage` if you want maximum visibility for these products and your theme has ample space in the main content area.
   - **Merchant scenario / example:** If you’re running a special promotion and want the products to be immediately visible without customers needing to click a tab, you’d select `Homepage`. If you have many product types featured on your homepage and want to organize them neatly, `Homepage Tab` is a better choice.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Source Category ID | (Your Category ID) | Specifies which category’s products are displayed. |
| Module Configuration | Number of Products | 8-12 | Limits the number of products shown from the selected category. |
| Module Configuration | Placement Position | Homepage Tab / Homepage | Determines if products appear in a tab or directly on the homepage. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My featured products aren’t showing up on the homepage.**
A:

1. **Check “Source Category ID”:** Ensure you’ve entered a correct, existing category ID. Go to **Catalog > Categories**, edit the desired category, and find its ID in the browser URL (e.g., `id_category=X`).
2. **Check “Number of Products”:** Make sure it’s set to a value greater than 0.
3. **Check “Placement Position”:** If set to “Homepage Tab,” ensure your theme actually supports and displays homepage tabs. Some custom themes might not. Try switching to “Homepage” to see if they appear as a direct section.
4. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache.” Sometimes, PrestaShop’s cache prevents changes from appearing immediately.

**Q: The products are showing, but they look misaligned or have incorrect styling.**
A: This is usually a theme-related issue.

1. **Theme Compatibility:** While the module is compatible with PrestaShop versions, its visual output might conflict with highly customized themes.
2. **CSS Conflict:** Your theme’s CSS might be overriding or conflicting with the module’s default styling. You might need a web developer to inspect the CSS and apply custom styles to `featuredcategory.css` or your theme’s custom CSS file.

**Q: Can I feature products from multiple categories?**
A: Not directly with this module. The “Featured Products” module is designed to display products from *one* selected category at a time. If you need to feature products from multiple categories simultaneously, you would need to either:
a) Create a new “Master Featured” category and add products from various categories into it.
b) Install multiple instances of this module (if your theme allows) or use a different module designed for multi-category displays.

**Q: How do I translate the “Featured Products” tab title?**
A: If you’re using the “Homepage Tab” placement, the tab title is usually generated by the module.

1. Go to **International > Translations**.
2. Select “Installed modules translations,” your theme, and your language.
3. Search for the “Featured Products” module. You should find the text string for the tab title there and can translate it.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The `Featured Products` module is a straightforward PrestaShop module primarily designed to display a list of products from a specified category on the homepage. It leverages PrestaShop’s hook system (`displayHome`, `displayHomeTab`, `displayHomeTabContent`) to inject its content. The module’s logic is contained within its main PHP file, `featuredcategory.php`, which handles configuration, installation, and content rendering. It does not introduce custom controllers, models, or complex JavaScript, making it a lightweight and easily maintainable solution.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. All front-office content rendering is handled directly via hooks in the main `featuredcategory.php` file and associated Smarty templates.
- **Back-Office Admin Controllers**: None. Module configuration is managed through the standard `getContent()` method in the main module file.

### 4.3 Core Classes & Models (`classes/`)

- No custom classes or `ObjectModel` definitions are present in this module. All data retrieval (products, categories) is done using PrestaShop’s core `Product` and `Category` classes.

### 4.4 JavaScript Assets (`views/js/`)

- No custom JavaScript files are included with this module.

### 4.5 CSS Stylesheets (`views/css/`)

- `featuredcategory/css/featuredcategory.css`
  - **Scope:** Front-office customer styling.
  - **Main UI components and containers it styles:** This stylesheet provides basic styling for the product list generated by the module, ensuring it looks presentable within the homepage context. It likely targets generic product list containers and individual product elements.
  - **Key CSS class selectors developers can override in their theme:** Developers can inspect the HTML output of the module to identify specific classes (e.g., `.featuredcategory-products`, `.product-item`, `.product-name`) and override them in their theme’s custom CSS file to match the overall store design.

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses Smarty templates to render its content, primarily for the homepage hooks.

- **Hook templates (`views/templates/hook/`)**:
  - `featuredcategory/views/templates/hook/featuredcategory17-tabContents.tpl`
    - **Hook:** `displayHomeTabContent`
    - **Purpose:** This template is responsible for rendering the actual list of featured products when the “Placement Position” is set to “Homepage Tab.” It typically contains the loop to iterate through products and display their details (image, name, price, add to cart button).
  - `featuredcategory/views/templates/hook/featuredcategory17.tpl`
    - **Hook:** `displayHome`
    - **Purpose:** This template renders the list of featured products when the “Placement Position” is set to “Homepage” (i.e., not in a tab). It will output the same product list structure as `featuredcategory17-tabContents.tpl` but directly into the main `displayHome` hook.
  - `featuredcategory/views/templates/hook/tab.tpl`
    - **Hook:** `displayHomeTab`
    - **Purpose:** This template renders the actual tab title (e.g., “Featured Products”) that appears on the homepage when the “Placement Position” is set to “Homepage Tab.” It provides the clickable element that reveals the content from `featuredcategory17-tabContents.tpl`.
- **Admin templates (`views/templates/admin/`)**: None.
- **Front-office templates (`views/templates/front/`)**: None.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: This module does not create any custom database tables. It stores its configuration settings in PrestaShop’s `ps_configuration` table.

  - `ps_configuration` entries:
    - `CFEATURED_NBR`: Stores the “Number of Products” setting.
    - `CFEATURED_ID`: Stores the “Source Category ID” setting.
    - `CFEATURED_WHERE`: Stores the “Placement Position” setting (e.g., ‘tab’ or ‘home’).
    - `mypresta_updates`: Used for module update checks by MyPresta.eu.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHomeTab` | Renders content for a new tab on the homepage. | Outputs the HTML for the “Featured Products” tab title. |
| `displayHomeTabContent` | Renders content for the selected tab on the homepage. | Outputs the HTML for the list of featured products when the tab is active. |
| `displayHome` | Renders content directly in the main homepage area. | Outputs the HTML for the list of featured products when not using tabs. |
| `displayHeader` | Executed in the `<head>` section of every page. | Used to include the module’s CSS stylesheet (`featuredcategory.css`) for front-office display. |
| `actionProductDelete` | Triggered after a product is deleted. | Potentially used to clear cache or re-evaluate featured products if the deleted product was in the featured category. |
| `actionProductUpdate` | Triggered after a product is updated. | Potentially used to clear cache or re-evaluate featured products if the updated product is in the featured category. |
| `actionProductAdd` | Triggered after a new product is added. | Potentially used to clear cache or re-evaluate featured products if the new product is in the featured category. |
| `actionCategoryUpdate` | Triggered after a category is updated. | Potentially used to clear cache or re-evaluate featured products if the featured category itself is updated. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions regarding the “Featured Products” module.
