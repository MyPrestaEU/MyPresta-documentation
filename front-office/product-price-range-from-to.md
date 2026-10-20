---
title: "Product price range - from / to - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Product price range - from / to PrestaShop module by MyPresta.eu."
sidebar:
  label: "Product price range - from / to - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Product price range - from / to Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-price-range-from-to.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/product-price-range-from-to/)
>
> ---


# Product price range - from / to

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient for PrestaShop modules. No special hosting requirements beyond a standard PrestaShop-compatible environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installing the module, navigate to **Modules > Module Manager** and click “Configure” next to “Product price range - from / to”. You will be presented with the main configuration screen.

#### General Settings

This section controls the core behavior of the module.

- **Display price range on product list:**

  - **What this setting does:** This switch determines whether the “from [lowest price] to [highest price]” range is shown on pages that list multiple products, such as category pages, search results, or modules like “New Products” or “Featured Products.”
  - **Effect of changing this setting:**
    - *When enabled (YES):* Products with combinations and varying prices will display a price range on all product listing pages.
    - *When disabled (NO):* Only a single price (usually the base price or lowest combination price) will be shown on product listing pages, as per default PrestaShop behavior.
  - **Recommended value:** YES
  - **Merchant scenario / example:** If you sell T-shirts that cost €10 for small and €15 for large, enabling this will show “from €10.00 to €15.00” on your T-shirt category page, giving customers a quick overview of pricing options.
- **Display price range on product page:**

  - **What this setting does:** This switch controls whether the price range is displayed on the individual product page itself, typically near the main product price.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The product page will show the price range for products with combinations, informing the customer of the price variations before they select options.
    - *When disabled (NO):* The product page will only show a single price (usually the base price or lowest combination price), as per default PrestaShop behavior.
  - **Recommended value:** YES
  - **Merchant scenario / example:** On the product page for a custom-built computer, enabling this will show “from €800.00 to €2500.00” before the customer starts selecting CPU, RAM, and storage options, setting clear expectations.
- **Take quantity discounts into account:**

  - **What this setting does:** This crucial setting determines if the module should consider any quantity-based price reductions (specific prices for quantities) when calculating the *lowest* price in the range.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The module will calculate the absolute lowest possible price, including any quantity discounts, for the “from” part of the range. For example, if a product is €10, but €8 if you buy 10 units, the “from” price will be €8.
    - *When disabled (NO):* Quantity discounts will be ignored, and the “from” price will be based solely on the lowest combination price without considering bulk purchase savings.
  - **Recommended value:** YES (to ensure the most attractive and accurate lowest price is displayed).
  - **Merchant scenario / example:** If you sell pens for €1 each, but offer them at €0.80 if bought in packs of 100, enabling this will ensure the “from” price on your product list reflects €0.80, making the product appear even more affordable.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Display price range on product list | YES | Shows “from/to” price on category, search, and listing pages. |
| Module Configuration | Display price range on product page | YES | Shows “from/to” price on the individual product detail page. |
| Module Configuration | Take quantity discounts into account | YES | Includes quantity-based price reductions when calculating the lowest price in the range. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The price range isn’t showing up on my product pages/listings.**
A:

1. **Check Module Configuration:** Go to **Modules > Module Manager > Product price range - from / to > Configure**. Ensure “Display price range on product list” and “Display price range on product page” are both set to **YES**.
2. **Clear Cache:** PrestaShop uses caching. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions).
3. **Product Combinations:** Does the product actually have combinations with *different* prices? If all combinations have the same price, the module will likely display a single price as there’s no range to show.
4. **Theme Compatibility:** While the module is designed for broad compatibility, very heavily customized themes might require minor adjustments. If the issue persists after checking the above, contact MyPresta.eu support.

**Q2: The “from” price doesn’t seem to include my quantity discounts.**
A:

1. **Check Module Configuration:** Go to **Modules > Module Manager > Product price range - from / to > Configure**. Ensure “Take quantity discounts into account” is set to **YES**.
2. **Verify Quantity Discounts:** Double-check that your quantity discounts (specific prices) are correctly configured for the product and its combinations in the PrestaShop back office.
3. **Clear Cache:** Always clear your PrestaShop cache after making configuration changes.

**Q3: The price range looks a bit off or misaligned with my theme’s design.**
A:
The module tries to integrate seamlessly, but every theme is unique.

1. **Clear Cache:** Sometimes styling issues are due to old cached files.
2. **Custom CSS:** You might need to add some custom CSS to your theme to adjust the appearance. The module’s CSS classes are usually well-defined (see Section 7.5). A webmaster can help you target these classes to match your theme.
3. **Contact Support:** If you’re not comfortable with CSS, MyPresta.eu support can often provide guidance or small CSS snippets to help.

**Q4: Will this module slow down my store?**
A:
The module is optimized for performance. It calculates prices efficiently. While any module adds a tiny overhead, this one is designed to be lightweight. If you notice significant slowdowns, ensure your server meets PrestaShop’s recommended specifications and that other modules aren’t causing conflicts. Clearing cache regularly also helps.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters.

### 4.1 Architecture Overview

The “Product price range - from / to” module (`prange`) is a standard PrestaShop module following the MVC pattern. It primarily operates by hooking into various display points (`displayProductPriceBlock`, `displayProductListReviews`, etc.) to inject its calculated price range. The core logic resides within the main `index.php` file, which acts as the module’s entry point and handles configuration, installation, and hook registration. It leverages PrestaShop’s `Product` and `SpecificPrice` classes to calculate the price range, including quantity discounts.

### 4.2 Controllers (`controllers/`)

This module does not utilize custom front-office or back-office controllers. All logic is encapsulated within the main module class and executed via hooks.

### 4.3 Core Classes & Models (`classes/`)

This module does not define custom classes or extend `ObjectModel`. All necessary data manipulation and price calculations are performed using PrestaShop’s native `Product` and `SpecificPrice` classes within the main module file.

### 4.4 JavaScript Assets (`views/js/`)

- **`prange/views/js/prange-hide-p.js`**
  - **Scope:** Front-office (Product Page)
  - **Purpose:** This script likely contains logic to hide or modify the default product price display on the individual product page when the module’s price range is active. It might listen for DOM changes or page load events to ensure the module’s range is the primary price shown.
- **`prange/views/js/prange-hide-pl.js`**
  - **Scope:** Front-office (Product Listing Pages)
  - **Purpose:** Similar to `prange-hide-p.js`, but specifically targets product listing pages (categories, search results). It’s designed to hide or adjust the default single price display on these pages to make way for the module’s price range.
- **`prange/views/js/prange.js`**
  - **Scope:** Front-office
  - **Purpose:** This is likely the main JavaScript file for the module. It could contain:
    - Logic to dynamically update the price range if product attributes are changed via AJAX (e.g., selecting a combination).
    - Event listeners for `prestashop.on` events related to product data updates.
    - Any client-side rendering or manipulation required for the price range display.

### 4.5 CSS Stylesheets (`views/css/`)

- **`prange/views/css/prange.css`**
  - **Scope:** Front-office customer styling.
  - **Main UI components and containers it styles:** This stylesheet provides the default visual presentation for the price range text. It will define styles for the container holding the “from/to” text, font sizes, colors, margins, and potentially responsive adjustments.
  - **Key CSS class selectors developers can override:** Developers should inspect the rendered HTML to identify the specific classes (e.g., `.prange-price-range`, `.prange-from`, `.prange-to`) used by the module. These can then be targeted in a custom theme’s `custom.css` or `theme.css` to adjust the appearance.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**: This module does not explicitly define templates in a `hook/` subdirectory based on the provided inventory, but the templates listed below are effectively rendered via hooks.
- **Admin templates (`views/templates/admin/`)**: This module does not have custom admin templates beyond the standard `getContent()` form.
- **Front-office templates (`views/templates/front/`)**:
  - **`prange/views/templates/prange-oneprice.tpl`**
    - **Purpose:** This template is likely used when a product *does not* have combinations with varying prices, or when the module determines that only a single price should be displayed (e.g., if the “from” and “to” prices are identical). It ensures consistent formatting even for single-price products if the module is active.
    - **Rendered via:** Likely hooked into `displayProductPriceBlock` or similar.
  - **`prange/views/templates/prange.tpl`**
    - **Purpose:** This is the primary template for displaying the actual “from [lowest price] to [highest price]” range. It receives the calculated lowest and highest prices from the module’s PHP logic and formats them for display.
    - **Rendered via:** This template will be rendered when the module hooks into `displayProductPriceBlock` (for product page) and potentially other hooks for product listing pages (e.g., `displayProductListReviews`, `displayProductPriceBlock` in product list context, or by overriding core templates).

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create custom SQL tables.
  - It stores its configuration settings (e.g., `PRANGE_DISPLAY_LIST`, `PRANGE_DISPLAY_PRODUCT`, `PRANGE_QUANTITY_DISCOUNT`) in the standard `ps_configuration` table.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Used to include the module’s CSS (`prange.css`) and JavaScript files (`prange.js`, `prange-hide-p.js`, `prange-hide-pl.js`) for front-office styling and functionality. |
| `displayProductPriceBlock` | Renders content within the product price block on product pages and potentially product listings. | This is the primary hook for injecting the calculated price range into the product’s price display. The module likely checks the `type` parameter of this hook to determine context (product page vs. list). |
| `displayProductListReviews` | Renders content near product reviews on product listing pages. | While named for reviews, this hook is often used by modules to inject additional information (like price ranges) into product list items. |
| `displayProductExtraContent` | Renders extra content blocks on the product page. | Could be used as an alternative or supplementary location for the price range on the product page. |
| `displayAfterProductThumbs` | Renders content after product thumbnail images on the product page. | Another potential location for displaying the price range on the product page. |
| `displayProductButtons` | Renders content near product action buttons (e.g., Add to Cart). | Less likely for price range, but possible for contextual information. |
| `displayFooterProduct` | Renders content in the footer section of the product page. | A fallback or alternative location for the price range on the product page. |
| `displayProductAdditionalInfo` | Renders additional information on the product page. | A common hook for injecting custom product details. |
| `displayProductPrice` | Renders the product price itself. | This hook is often overridden or extended by modules that modify price display. |
| `actionProductUpdate` | Executed after a product is updated in the back office. | Could be used to clear module-specific caches or re-index price ranges if the module maintained its own cache. |
| `actionProductAdd` | Executed after a new product is added. | Similar to `actionProductUpdate`. |
| `actionProductDelete` | Executed after a product is deleted. | Similar to `actionProductUpdate`. |

*Note: The exact hooks used can vary slightly between module versions and PrestaShop versions. The above list represents common hooks for this module’s functionality based on its description.*

## 5. Official Support & Updates

For official updates, bug fixes, and dedicated developer support for the “Product price range - from / to” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Ensure you are running the latest version of the module for optimal performance and compatibility with your PrestaShop store.
