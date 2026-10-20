---
title: "Home new products block - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Home new products block PrestaShop module by MyPresta.eu."
sidebar:
  label: "Home new products block - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Home new products block Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/home-new-products-block.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/home-new-products-block/)
>
> ---


# Home new products block

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are needed beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Home new products block” module to access its settings.

#### Setting: Number of products to display

- **What this setting does:** This field allows you to control how many of your newest products will be shown in the block on your homepage.
- **Effect of changing this setting:**
  - *When set to a higher number (e.g., 10):* More new products will be visible in the block, giving customers a broader selection of your latest items. This might make the block longer or require more scrolling.
  - *When set to a lower number (e.g., 4):* Fewer new products will be displayed, making the block more compact. This can be useful if you have limited space or want to highlight only the absolute freshest items.
- **Recommended value:** A good starting point is `8` or `12` products. This provides a decent selection without overwhelming the page.
- **Merchant scenario / example:** If you run a fashion store and add 20 new items every week, setting this to `12` ensures a good variety is always visible. If you only add a few new artisanal products each month, `4` or `6` might be more appropriate to keep the block concise.

#### Setting: Display on homepage

- **What this setting does:** This is a simple ON/OFF switch that controls whether the “Home new products block” is visible on your store’s homepage.
- **Effect of changing this setting:**
  - *When enabled (YES):* The block with your new products will appear on your homepage, as described in Section 2.
  - *When disabled (NO):* The block will be hidden from your homepage. This might be useful if you temporarily want to remove it without uninstalling the module, or if you prefer to use other methods to showcase new products.
- **Recommended value:** `YES` (Enabled). The primary purpose of this module is to display new products on the homepage.
- **Merchant scenario / example:** You might temporarily disable it if you’re running a special seasonal campaign that requires all homepage space for promotional banners, and then re-enable it once the campaign is over.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Number of products to display | 8-12 | Controls how many new products appear in the block. Higher number shows more, lower number makes it more compact. |
| Module Configuration Page | Display on homepage | YES | Toggles the visibility of the new products block on your homepage. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My new products block isn’t showing up on the homepage after installation.**
A:

1. **Check Module Configuration:** Go to **Modules > Module Manager**, find “Home new products block,” and click “Configure.” Ensure “Display on homepage” is set to `YES`.
2. **Clear Cache:** Sometimes PrestaShop’s cache prevents changes from appearing immediately. Go to **Advanced Parameters > Performance**, and click “Clear cache” in the top right corner.
3. **Check Hook Position:** While the module is designed to hook automatically, sometimes theme conflicts or other modules can interfere. Go to **Design > Positions**. Search for `displayHome` (or `displayHomeTabContent` if your theme uses tabs). Ensure `home-new-products-block` is listed and enabled within one of these hooks. If not, you might need to “Transplant a module” to `displayHome`.

**Q: The block is showing old products, not new ones.**
A: The module displays products based on their “date added” in PrestaShop. Ensure that when you add new products, their creation date is correctly set to the current date. If you imported products with old dates, they might not appear as “new.” You might need to manually update the `date_add` field for those products in your database (advanced task, consult a developer) or re-add them.

**Q: I want to change where the block appears on my homepage (e.g., higher up, or in a column).**
A: You can adjust the position of the module using PrestaShop’s built-in “Live Edit” feature.

1. Go to **Design > Positions**.
2. Click the “Run Live Edit” button (usually in the top right).
3. Navigate to your homepage.
4. You should see outlines around various module blocks. Find the “Home new products block” and drag it to your desired position. You can also use the “Transplant a module” button to move it to a different hook (e.g., `displayLeftColumn`, `displayRightColumn`, `displayFooter`).

**Q: The block looks strange or doesn’t match my theme’s styling.**
A: This module uses standard PrestaShop product display templates, which should inherit most of your theme’s styling. If it looks off:

1. **Clear Cache:** As above, clear your PrestaShop cache.
2. **Theme Overrides:** Your theme might have specific CSS that conflicts. This usually requires a web developer to inspect your site’s CSS and potentially add custom styles to your theme’s `custom.css` file to override the default.
3. **Module Update:** Ensure you have the latest version of the module from MyPresta.eu.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Home new products block” module is a straightforward PrestaShop module following the standard module structure. It primarily uses the `Module` class to manage its lifecycle (installation, uninstallation) and `hook` methods to render content in the front office. It retrieves product data directly from PrestaShop’s core database tables, leveraging existing `Product` and `Category` functionalities. There are no custom controllers or complex ObjectModels, making it lightweight and easy to integrate.

### 4.2 Controllers (`controllers/`)

- This module does **not** contain any custom Front-Office or Back-Office controllers. All logic is encapsulated within the main module file and executed via hooks.

### 4.3 Core Classes & Models (`classes/`)

- This module does **not** contain any custom classes or ObjectModels in a `classes/` directory. It relies on PrestaShop’s core `Product` and `Category` classes for data retrieval.

### 4.4 JavaScript Assets (`views/js/`)

- This module does **not** include any custom JavaScript files. Any dynamic behavior (e.g., carousels) would typically be handled by the theme’s existing JS or a separate module.

### 4.5 CSS Stylesheets (`views/css/`)

- This module does **not** include any custom CSS files. It relies on the theme’s default styling for product lists and grids. Developers wishing to style this block specifically should target its HTML structure (e.g., `div#home_new_products`) in their theme’s `custom.css` or equivalent.

### 4.6 Smarty Template Structure (`views/templates/`)

- This module primarily uses a single template file for rendering its content.

  - **Hook templates (`views/templates/hook/`)**:
    - `views/templates/hook/home-new-products-block.tpl`: This is the main template file responsible for rendering the block of new products on the homepage.
      - **Hook:** Primarily intended for `displayHome` (or `displayHomeTabContent` in some themes).
      - **Purpose:** It iterates through the `$products` variable (an array of `Product` objects) passed from the `hookDisplayHome` method and displays each product’s image, name, price, and “Add to Cart” button, typically using a loop and including a standard product-list item template (e.g., `product-miniature.tpl` or similar, depending on the PrestaShop version and theme).

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does **not** create any custom database tables.
  - It stores its configuration settings (e.g., `HOME_NEW_PRODUCTS_NBR`, `HOME_NEW_PRODUCTS_DISPLAY`) in the standard `ps_configuration` table.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHome` | Renders content in the main homepage area. | Displays the block of new products on the store’s homepage. |
| `displayHeader` | Executed in the `<head>` section of every page. | Used to register assets (CSS/JS) if any were present, though this module doesn’t use it for that. Could be used for meta tags or other global elements. |
| `displayLeftColumn` | Renders content in the left sidebar. | Allows the new products block to be moved to the left column via “Design > Positions.” |
| `displayRightColumn` | Renders content in the right sidebar. | Allows the new products block to be moved to the right column via “Design > Positions.” |
| `displayFooter` | Renders content in the store’s footer. | Allows the new products block to be moved to the footer via “Design > Positions.” |
| `actionProductAdd` | Executed after a new product is added. | Could be used to clear cache or re-index, though not explicitly used by this module. |
| `actionProductUpdate` | Executed after a product is updated. | Could be used to clear cache or re-index, though not explicitly used by this module. |
| `actionProductDelete` | Executed after a product is deleted. | Could be used to clear cache or re-index, though not explicitly used by this module. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Home new products block” module, please refer to your MyPresta.eu customer account. You can download the newest versions and access support resources directly from [MyPresta.eu](https://mypresta.eu).
