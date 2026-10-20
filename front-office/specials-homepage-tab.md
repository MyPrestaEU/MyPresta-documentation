---
title: "Specials Homepage Tab - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Specials Homepage Tab PrestaShop module by MyPresta.eu."
sidebar:
  label: "Specials Homepage Tab - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Specials Homepage Tab Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/specials-homepage-tab.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/specials-homepage-tab/)
>
> ---


# Specials Homepage Tab

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for a PrestaShop installation and are sufficient for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Specials Homepage Tab” module to access its settings.

#### Settings & Options:

- **Number of products**

  - **What this setting does:** This controls how many special offer products will be displayed within the “Specials” tab on your homepage.
  - **Effect of changing this setting:**
    - *When set to a higher number (e.g., 12):* More products will be visible in the tab, giving customers a wider selection of deals. This might require more scrolling or pagination depending on your theme.
    - *When set to a lower number (e.g., 4):* Fewer products will be shown, creating a more concise display. This can be useful if you want to highlight only your very best deals or keep the homepage clean.
  - **Recommended value:** Start with a number that fits well within your theme’s design (e.g., 8 or 12) and adjust based on how many special offers you typically have and how much space you want them to occupy.
  - **Merchant scenario / example:** If you have many products on sale and want to showcase variety, set it to 12. If you prefer a minimalist homepage and only want to highlight a few star deals, set it to 4.
- **Random products**

  - **What this setting does:** This determines whether the special offer products displayed in the tab are shown in a fixed order (e.g., by ID, date added) or in a random order each time the page is loaded.
  - **Effect of changing this setting:**
    - *When enabled (YES):* Each time a customer visits your homepage, the order of products in the “Specials” tab will be randomized. This ensures that different products get visibility and prevents the same few items from always being at the top.
    - *When disabled (NO):* Products will be displayed in a consistent, non-random order (typically by product ID or creation date, depending on PrestaShop’s default sorting for specials). This means the same products will always appear first.
  - **Recommended value:** **YES**. Randomizing products is generally recommended to give all your special offers a fair chance of being seen and to keep the homepage fresh for returning customers.
  - **Merchant scenario / example:** If you have 20 products on sale but only display 8, enabling “Random products” ensures that over time, all 20 products will eventually appear in the tab, rather than just the first 8.

#### Other Configuration Keys (Internal PrestaShop Settings):

The module also interacts with several core PrestaShop configuration keys. While these are not directly configurable within the module itself, understanding their purpose helps in troubleshooting or advanced customization:

- `PS_CATALOG_MODE`: If your store is in catalog mode (no prices, no add to cart), special prices won’t be relevant.
- `PS_LANG_DEFAULT`: The default language of your store, used for retrieving product names and descriptions.
- `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Determines if employees can change the language of forms in the back office.
- `PS_TAX_ADDRESS_TYPE`: How taxes are calculated (e.g., based on delivery or invoice address).
- `PS_COUNTRY_DEFAULT`: The default country for your store, impacting tax and shipping calculations.
- `PS_NB_DAYS_NEW_PRODUCT`: The number of days a product is considered “new.” (Not directly related to specials, but often found in modules that list products).

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Number of products | 8-12 (Adjust to theme) | Sets how many special offer products are shown in the tab. |
| Module Configuration | Random products | YES | Randomizes the order of products in the tab for fresh display. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My “Specials” tab is empty or not showing any products, but I have products on sale.**

- **A:** First, ensure that your products are correctly marked as “on sale” in their product settings in the PrestaShop back office (under the “Pricing” tab, make sure “Specific prices” are configured and active). Also, check the “Number of products” setting in the module configuration; if it’s set to 0, no products will display. Finally, clear your PrestaShop cache (**Advanced Parameters > Performance > Clear cache**).

**Q2: The “Specials” tab is not appearing on my homepage at all.**

- **A:**
  1. **Module Enabled:** Go to **Modules > Module Manager** and ensure the “Specials Homepage Tab” module is enabled.
  2. **Hooked Correctly:** The module uses `displayHomeTab` and `displayHomeTabContent`. Your theme must support these hooks for the tab to appear. Most standard PrestaShop themes do. If you’re using a heavily customized theme, it might not be calling these hooks.
  3. **Cache:** Always clear your PrestaShop cache (**Advanced Parameters > Performance > Clear cache**) after installing or configuring modules.
  4. **Theme Compatibility:** While the module is designed to be compatible, very old or highly customized themes might require minor adjustments. If issues persist, contact MyPresta.eu support.

**Q3: The products in the “Specials” tab don’t look good or don’t match my theme’s design.**

- **A:** The module uses your theme’s existing styling for product listings. If the products look off, it’s usually a CSS issue with your theme rather than the module itself.
  - **Check Theme CSS:** Inspect your theme’s CSS for product listing styles.
  - **Custom CSS:** You might need to add custom CSS to your theme’s `custom.css` file (if available) or directly edit your theme’s stylesheet to adjust the appearance.
  - **Mobile Responsiveness:** Test on different devices. If it looks fine on desktop but not mobile, it’s a responsiveness issue with your theme’s CSS.

**Q4: Can I change the title of the “Specials” tab (e.g., to “Deals” or “Promotions”)?**

- **A:** The module uses the default PrestaShop translation for “Specials.” To change it, you would typically go to **International > Translations**, select “Installed modules translations,” choose your theme, and then find the “Specials Homepage Tab” module. You can then edit the translation for the tab title.

**Q5: Why are some products that are on sale not showing up in the tab?**

- **A:**
  1. **Number of Products Limit:** Check the “Number of products” setting in the module configuration. If you have more specials than this limit, only the first (or random, if enabled) set will display.
  2. **Product Visibility:** Ensure the product is active, visible, and has an actual specific price configured (not just a regular price reduction).
  3. **Cache:** Clear your PrestaShop cache.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Specials Homepage Tab” module (`blockspecialstab`) is a lightweight PrestaShop module primarily focused on front-office display. It adheres to the standard PrestaShop module architecture, leveraging hooks to inject content into the homepage. It does not introduce custom controllers, models, or complex JavaScript/CSS beyond what’s necessary for basic templating. Its core functionality revolves around fetching products with specific prices and rendering them within a tab structure.

### 4.2 Controllers (`controllers/`)

This module does **not** include any custom Front-Office or Back-Office Admin Controllers. All logic is encapsulated within the main module class (`blockspecialstab.php`).

### 4.3 Core Classes & Models (`classes/`)

This module does **not** introduce any custom classes or `ObjectModel` definitions. It relies on PrestaShop’s core `Product` and `SpecificPrice` classes to retrieve product data.

### 4.4 JavaScript Assets (`views/js/`)

This module does **not** include any custom JavaScript files. The tab switching functionality and product display are handled by the theme’s existing JavaScript (e.g., jQuery, Bootstrap JS) which typically manages `displayHomeTab` and `displayHomeTabContent` interactions.

### 4.5 CSS Stylesheets (`views/css/`)

This module does **not** include any custom CSS files. It is designed to inherit the styling of the active PrestaShop theme for product listings, ensuring seamless integration. Developers should refer to their theme’s CSS for styling product grids and tabs.

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses two primary Smarty templates, both located in the `views/templates/hook/` directory, to render the tab and its content.

- **`blockspecialstab/views/templates/hook/blockspecialstab.tpl`**

  - **Purpose:** This template is responsible for rendering the actual “Specials” tab *header* that appears alongside other tabs (e.g., “New Arrivals”).
  - **Hook:** Primarily rendered via `displayHomeTab`.
  - **Output:** Typically outputs an `<li>` element containing an `<a>` tag with a link to the tab’s content (e.g., `#blockspecialstab`).
  - **Key elements for developers:**
    - `id="home-page-tabs"`: The container for all homepage tabs (usually in the theme).
    - `id="blockspecialstab"`: The ID for the tab itself, used for linking to its content.
    - `{l s='Specials' mod='blockspecialstab'}`: The translatable text for the tab title.
- **`blockspecialstab/views/templates/hook/blockspecialstabcontents.tpl`**

  - **Purpose:** This template renders the *content* that appears when the “Specials” tab is clicked. It contains the actual list of special offer products.
  - **Hook:** Primarily rendered via `displayHomeTabContent`.
  - **Output:** Typically outputs a `<div>` element containing a loop that iterates through the `$products` variable (passed from the module) and displays each product using a common product-list partial from the theme (e.g., `product-list.tpl` or a similar snippet).
  - **Key elements for developers:**
    - `id="blockspecialstab"`: The ID for the content block, matching the tab header.
    - `{$products}`: An array of `Product` objects (or associative arrays representing products) passed from the module, containing details like ID, name, price, image, etc.
    - `{include file='catalog/_partials/miniatures/product.tpl' product=$product}` (example for PS 1.7/8): The module typically uses a standard theme partial to render each product, ensuring consistent styling. Developers should check their theme’s `_partials/miniatures/product.tpl` or `product-list.tpl` for how individual products are rendered.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create any custom SQL tables.
  - It stores its configuration settings in the `ps_configuration` table using keys like `BLOCKSTAB_NB_CACHES` (legacy), `BLOCKSTABS_NB_CACHES` (current), and `BLOCKSTABS_RAND`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHomeTab` | Renders in the homepage tab navigation area. | Injects the “Specials” tab header (`blockspecialstab.tpl`) into the main homepage tab list. |
| `displayHomeTabContent` | Renders in the homepage content area, corresponding to the tab. | Injects the list of special offer products (`blockspecialstabcontents.tpl`) when the “Specials” tab is active. |
| `addproduct` | After a product is added. | Clears the module’s internal cache to ensure new products are considered for specials. |
| `updateproduct` | After a product is updated. | Clears the module’s internal cache to reflect changes in product prices or status. |
| `deleteproduct` | After a product is deleted. | Clears the module’s internal cache to remove deleted products from specials. |
| `displayAddProduct` | (Legacy hook, often used for admin forms) | Clears the module’s internal cache. |
| `displayUpdateProduct` | (Legacy hook, often used for admin forms) | Clears the module’s internal cache. |
| `displayDeleteProduct` | (Legacy hook, often used for admin forms) | Clears the module’s internal cache. |

The `addproduct`, `updateproduct`, `deleteproduct`, `displayAddProduct`, `displayUpdateProduct`, and `displayDeleteProduct` hooks are primarily used to trigger a cache clear within the module. This ensures that the list of special products displayed on the homepage is always up-to-date when product information (especially pricing or status) changes.

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Specials Homepage Tab” module, please refer to your customer account at MyPresta.eu. Our support team is available to assist with any technical issues or questions regarding the module’s functionality.
