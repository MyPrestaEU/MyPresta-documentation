---
title: "Related Products Free - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Related Products Free PrestaShop module by MyPresta.eu."
sidebar:
  label: "Related Products Free - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Related Products Free Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/related-products-free.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/related-products-free/)
>
> ---


# Related Products Free

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL), which are typically available on most PrestaShop-compatible hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Related Products Free)

This is the main and only configuration screen for the “Related Products Free” module. Here you will define how the related products block behaves and what products it displays.

#### **Display related products from category**

- **What this setting does:** This crucial setting determines *which* products will be shown as “related.” Instead of manually picking products for each item, this module simplifies things by letting you select a specific category. All products belonging to this chosen category will then be displayed as related products on *every* product page in your store.
- **Effect of changing this setting:**
  - *When a category is selected (e.g., “Accessories”):* On every product page in your store, a block will appear showing products that belong to the “Accessories” category.
  - *When “None” or no category is selected:* The module will not display any related products, as it doesn’t know which products to show.
- **Recommended value:** Choose a category that contains general, complementary, or best-selling items that could be relevant to a wide range of your main products. For example, if you sell clothing, “Accessories” or “Sale Items” could be good choices.
- **Merchant scenario / example:** You sell various types of electronics. You create a category called “Must-Have Gadget Accessories” and add items like universal chargers, screen protectors, and headphones to it. By selecting this category here, every product page (e.g., for a smartphone, a laptop, or a tablet) will show these “Must-Have Gadget Accessories” as related products, encouraging cross-sales.

#### **Number of products to display**

- **What this setting does:** This controls how many related products will be shown in the block on your product pages.
- **Effect of changing this setting:**
  - *When set to ‘4’:* The module will display four products from your chosen category.
  - *When set to ‘8’:* The module will display eight products.
- **Recommended value:** 4 or 5. Too many products can overwhelm the customer or make the page look cluttered, especially on mobile. A smaller, curated selection is often more effective.
- **Merchant scenario / example:** You want to show a concise selection of related items without making the product page too long. Setting this to ‘4’ ensures a clean layout while still offering good cross-selling opportunities.

#### **Display products from selected category only**

- **What this setting does:** This setting determines whether the related products shown are *only* from the category you selected above, or if it can also include products from the *current product’s own category*.
- **Effect of changing this setting:**
  - *When enabled (YES):* Only products from the category chosen in “Display related products from category” will be shown.
  - *When disabled (NO):* The module will show products from the selected category *and* potentially products from the category of the product the customer is currently viewing. This can lead to more relevant suggestions if the current product’s category also contains good cross-sell items.
- **Recommended value:** “YES” if your chosen “related products” category is very general (like “Accessories”). “NO” if you want to mix in more specific related items from the current product’s category. Test both to see what works best for your store.
- **Merchant scenario / example:** You’ve selected “Accessories” as your related category. If you set this to “YES,” only accessories will show. If you set it to “NO,” and a customer is viewing a “T-shirt” (which is in the “Tops” category), the module might show both “Accessories” and other “Tops” as related.

#### **Hook to display related products**

- **What this setting does:** This is where you decide *where* on the product page the related products block will appear. PrestaShop uses “hooks” as specific points in the page’s code where modules can insert their content.
- **Effect of changing this setting:**
  - *When set to `displayFooterProduct` (Recommended):* The related products block will appear at the bottom of the product information section, usually above the footer of the entire page. This is a common and effective placement.
  - *When set to `displayProductExtraContent` (PrestaShop 1.7+):* The block might appear within a tab or a specific section of the product page’s main content area, depending on your theme.
  - *Other hooks (e.g., `displayLeftColumnProduct`, `displayRightColumnProduct`):* The block will appear in the left or right sidebar of the product page, if your theme supports sidebars on product pages.
- **Recommended value:** `displayFooterProduct`. This hook is widely supported by themes and provides a clear, unobtrusive placement for related items. Experiment with others if you have a specific design in mind.
- **Merchant scenario / example:** You want the related products to be visible but not interfere with the main product description and “Add to Cart” button. Choosing `displayFooterProduct` places it neatly below the primary content, allowing customers to scroll down and discover more.

#### **Display products in carousel**

- **What this setting does:** This determines if the related products are shown in a static grid (all visible at once) or in a dynamic, scrollable carousel (where customers can click arrows or swipe to see more).
- **Effect of changing this setting:**
  - *When enabled (YES):* The related products will appear in a carousel format, allowing you to display more products in a compact space.
  - *When disabled (NO):* The products will be displayed in a static grid, showing all selected products at once (up to the “Number of products to display” limit).
- **Recommended value:** “YES” if you want to save space or display more products than can fit comfortably in a single row. “NO” if you prefer all products to be immediately visible without interaction.
- **Merchant scenario / example:** You want to show 8 related products, but displaying them all in a grid makes the page too long. Enabling the carousel allows you to show 8 products while only taking up the space of 4, with customers scrolling to see the rest.

#### **Display products in random order**

- **What this setting does:** This controls the order in which the related products from your chosen category are displayed.
- **Effect of changing this setting:**
  - *When enabled (YES):* Each time a customer visits a product page, the related products will appear in a different, random order.
  - *When disabled (NO):* The products will appear in a consistent order, usually based on their ID or position within the selected category.
- **Recommended value:** “YES”. Randomizing the order ensures that all products in your chosen category get a chance to be seen over time, preventing the same few products from always being at the top.
- **Merchant scenario / example:** You have 20 products in your “Accessories” category, but you only display 5. If the order is always the same, only the first 5 will ever be seen. By enabling random order, different accessories will appear each time, increasing exposure for all of them.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Display related products from category | Select a relevant category | Defines the source category for related products. |
| Module Configuration | Number of products to display | 4-5 | Controls how many related products are shown. |
| Module Configuration | Display products from selected category only | YES / NO (Test both) | Determines if only the selected category’s products are shown, or if the current product’s category can also contribute. |
| Module Configuration | Hook to display related products | `displayFooterProduct` | Specifies the location of the related products block on the product page. |
| Module Configuration | Display products in carousel | YES | Shows related products in a scrollable carousel for compact display. |
| Module Configuration | Display products in random order | YES | Randomizes the order of displayed related products for varied exposure. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve configured the module, but I don’t see any related products on my product pages.**
A:

1. **Check Category Selection:** Ensure you have selected a valid category in the “Display related products from category” setting and that this category actually contains products.
2. **Check Product Status:** Make sure the products within your selected category are active, in stock, and visible in your store.
3. **Clear Cache:** Go to **Advanced Parameters > Performance** in your PrestaShop Back Office and click “Clear cache” (or “Clear Smarty cache”). Sometimes, PrestaShop needs a cache refresh to display new module content.
4. **Theme Compatibility:** While the module uses standard PrestaShop hooks, some highly customized themes might have specific overrides. Try switching to the default PrestaShop theme temporarily to see if the block appears. If it does, your theme might require minor adjustments.

**Q: The related products block looks strange or unstyled on my site.**
A: This is usually a CSS (styling) conflict with your theme.

1. **Clear Cache:** Always start by clearing your PrestaShop cache.
2. **Theme Overrides:** Your theme might have its own styling for product lists or carousels that conflict. You might need a web developer to inspect the CSS and apply custom styles to make it fit your theme’s design. The module provides basic styling, but your theme’s styles often take precedence.

**Q: Can I have different related products for different main products?**
A: The “Related Products Free” module is designed for simplicity, displaying products from a *single chosen category* across all product pages. For more advanced, product-specific related product assignments, you would need a more comprehensive (paid) module.

**Q: The carousel isn’t working or displaying correctly.**
A:

1. **Check JavaScript Conflicts:** Another module or your theme might have conflicting JavaScript that prevents the carousel from initializing. Check your browser’s developer console for JavaScript errors.
2. **Clear Cache:** Again, clear your PrestaShop cache.
3. **Disable & Re-enable:** Try disabling the “Display products in carousel” setting, saving, then re-enabling it and saving again.

**Q: How do I translate the module’s title (e.g., “Related Products”) into other languages?**
A:

1. Go to **International > Translations** in your PrestaShop Back Office.
2. Select “Installed modules translations” for the “Type of translation.”
3. Choose your theme (or “Core” if your theme isn’t listed).
4. Select the language you want to translate.
5. Find the “relatedfree” module in the list and translate the relevant strings.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a technical overview for developers and webmasters working with the “Related Products Free” module.

### 4.1 Architecture Overview

The “Related Products Free” module is a straightforward PrestaShop module following a basic MVC-like pattern within the module’s scope. It primarily uses the `Module` class’s `getContent()` method for its Back Office configuration and registers a single hook (`displayFooterProduct` by default, but configurable) to inject its front-office template. It does not introduce custom controllers, ObjectModels, or complex JavaScript/CSS assets beyond its core functionality.

### 4.2 Controllers (`controllers/`)

- This module does **not** contain any custom Front-Office or Back-Office controllers. All configuration is handled within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

- This module does **not** contain any custom classes or ObjectModels in the `classes/` directory. All logic is encapsulated within the main `RelatedFree` class (defined in `index.php`).

### 4.4 JavaScript Assets (`views/js/`)

- This module does **not** contain any custom JavaScript files. If the carousel option is enabled, it relies on PrestaShop’s core JavaScript libraries (e.g., Owl Carousel if available in the theme, or a simple custom implementation within the TPL if not).

### 4.5 CSS Stylesheets (`views/css/`)

- This module does **not** contain any custom CSS files. Styling is expected to be handled by the theme or relies on basic inline styles/structure that themes typically style. Developers should apply custom CSS to match their theme’s aesthetic.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Admin templates (`views/templates/admin/`)**:

  - `views/templates/admin/tabs.tpl`: This template is used to render the module’s configuration form in the Back Office. It defines the structure of the settings, including input fields for category selection, number of products, hook selection, and toggle switches for carousel and random order. It’s rendered by `getContent()` in `index.php`.
- **Hook templates (`views/templates/hook/`)**:

  - `views/templates/hook/productFooter.tpl`: This is the primary front-office template. It’s rendered when the module is hooked (e.g., `displayFooterProduct`). This template contains the HTML structure for the related products block, including the title, and iterates through the `$products` variable (passed from the module) to display each related product’s image, name, and price. It also contains the logic for rendering a carousel if the corresponding configuration option is enabled.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  The module does not create any custom database tables. All configuration settings are stored in the `ps_configuration` table using standard PrestaShop configuration keys.

  - `PS_RELATEDFREE_CATEGORY`: Stores the ID of the selected category for related products.
  - `PS_RELATEDFREE_NUMBER`: Stores the number of products to display.
  - `PS_RELATEDFREE_ONLY_SELECTED`: Stores a boolean (0/1) for displaying only products from the selected category.
  - `PS_RELATEDFREE_HOOK`: Stores the name of the hook where the module is displayed.
  - `PS_RELATEDFREE_CAROUSEL`: Stores a boolean (0/1) for enabling the carousel.
  - `PS_RELATEDFREE_RANDOM`: Stores a boolean (0/1) for displaying products in random order.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Used for registering assets (though this module doesn’t use it for assets). |
| `displayLeftColumn` | In the left sidebar of pages that have one. | Alternative placement for the related products block. |
| `displayRightColumn` | In the right sidebar of pages that have one. | Alternative placement for the related products block. |
| `displayFooter` | At the bottom of every page, before the closing `</body>` tag. | Alternative placement for the related products block. |
| `displayProductExtraContent` | Within the main product content area, often in tabs (PrestaShop 1.7+). | Alternative placement for the related products block. |
| `displayFooterProduct` | At the bottom of the product information section on product pages. | **Primary hook used by the module** for displaying related products. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Related Products Free” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality.
