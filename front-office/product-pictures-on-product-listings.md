---
title: "Product pictures on product listings - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Product pictures on product listings PrestaShop module by MyPresta.eu."
sidebar:
  label: "Product pictures on product listings - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Product pictures on product listings Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-pictures-on-product-listings.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/product-pictures-on-product-listings/)
>
> ---


# Product pictures on product listings

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required for PrestaShop itself and generally available on all modern hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the “Product pictures on product listings” module. You can access it by navigating to **Modules > Module Manager** and clicking “Configure” next to the module name.

#### **Position of the module**

- **What this setting does:** This determines where the additional product images will appear relative to the main product image on listing pages.
- **Effect of changing this setting:**
  - *displayProductAdditionalInfo:* Images will appear in a common hook often used for extra product details.
  - *displayAfterProductThumbs:* Images will appear immediately after the main product image thumbnails (if your theme displays them).
  - *displayFooterProduct:* Images will appear in the footer section of the product block on the listing page.
  - *displayProductDeliveryTime:* Images will appear near the delivery time information (if your theme displays it).
  - *displayHeader:* This is a less common position for product images on listing pages and might require custom styling to look good.
  - *displayProductListReviews:* Images will appear near product review stars or count (if your theme displays them).
- **Recommended value:** Experiment with `displayProductAdditionalInfo` or `displayAfterProductThumbs` first, as these are typically good visual placements.
- **Merchant scenario / example:** If your theme has a clean layout and you want the images to be subtly integrated below the main image, `displayProductAdditionalInfo` might be best. If you want them to stand out more, `displayFooterProduct` could work.

#### **Design of the module**

- **What this setting does:** This allows you to choose between different visual styles for the module’s output, primarily affecting how the thumbnails are presented.
- **Effect of changing this setting:**
  - *Classic theme:* Applies styling that is often compatible with older PrestaShop themes or themes that mimic the classic look.
  - *Universal:* Applies a more modern, responsive design that aims to work well across a wider range of contemporary themes.
- **Recommended value:** `Universal` for most modern PrestaShop stores (1.7.x, 8.x, 9.x). Use `Classic theme` if you have an older or highly customized theme that doesn’t render `Universal` correctly.
- **Merchant scenario / example:** If your store uses a default PrestaShop 8 theme, `Universal` will likely integrate seamlessly. If you’re on PrestaShop 1.6 with a custom theme, `Classic theme` might be a safer bet.

#### **Display method**

- **What this setting does:** This controls which additional images are displayed for each product on the listing page.
- **Effect of changing this setting:**
  - *Pictures for color combinations:* Only displays images specifically linked to the color attributes of a product. Useful for fashion or products with distinct color variants.
  - *Pictures for each combination:* Displays images for all product combinations (e.g., size, color, material). This can lead to many images if you have many combinations.
  - *All product pictures:* Displays all images associated with the product, regardless of combination. This is the most comprehensive option.
- **Recommended value:** `All product pictures` for most general products. `Pictures for color combinations` if your products heavily rely on color variations and you want to keep the image count manageable.
- **Merchant scenario / example:** For a clothing store, selecting `Pictures for color combinations` would show all available colors for a specific t-shirt. For a furniture store, `All product pictures` would show different angles and close-ups of a sofa.

#### **In stock only**

- **What this setting does:** This option filters the displayed images based on product stock availability.
- **Effect of changing this setting:**
  - *Enabled:* Only displays images for product combinations that are currently in stock. If a specific color is out of stock, its associated images won’t appear.
  - *Disabled:* Displays all selected images, regardless of stock status.
- **Recommended value:** `Enabled` to avoid showing customers images of products they cannot immediately purchase, which can lead to frustration.
- **Merchant scenario / example:** If you sell shoes and a particular size/color combination is out of stock, enabling this prevents customers from seeing images of that specific variant, guiding them towards available options.

#### **Display color boxes instead pictures**

- **What this setting does:** Instead of showing small image thumbnails, this option displays color swatches (boxes) for product combinations.
- **Effect of changing this setting:**
  - *Enabled:* Replaces image thumbnails with small color boxes, typically using the color defined for the product attribute.
  - *Disabled:* Displays actual image thumbnails.
- **Recommended value:** `Disabled` if you want to show actual product images. `Enabled` if your products have clear color attributes and you prefer a cleaner, more compact look for color selection.
- **Merchant scenario / example:** For a paint store, enabling this would show small colored squares representing different paint colors, which is more efficient than showing a tiny picture of each color.

#### **Main product container on list of products**

- **What this setting does:** This is a technical setting to help the module identify the main container for each product on your listing pages. It requires a CSS selector.
- **Effect of changing this setting:** If set incorrectly, the module might not be able to find where to inject the additional images, or it might inject them in the wrong place.
- **Recommended value:** This depends entirely on your theme. Common values are `.product-miniature`, `.product-container`, or `.ajax_block_product`. You might need to inspect your theme’s HTML to find the correct selector.
- **Merchant scenario / example:** If your theme uses `<div class="product-item">` for each product, you would enter `.product-item` here.

#### **Product cover picture css**

- **What this setting does:** This is a technical setting to help the module identify the main product image element within each product container. It requires a CSS selector.
- **Effect of changing this setting:** If set incorrectly, the module won’t be able to switch the main product image when a thumbnail is clicked/hovered.
- **Recommended value:** This depends on your theme. Common values are `.product-thumbnail`, `.img-fluid`, or `img.replace-me`. You might need to inspect your theme’s HTML.
- **Merchant scenario / example:** If your theme’s main product image has the class `product-image-thumb`, you would enter `.product-image-thumb` here.

#### **Product cover picture anchor css**

- **What this setting does:** This is a technical setting to help the module identify the link (anchor tag) that wraps the main product image. This is important for ensuring the link still works correctly after image switching.
- **Effect of changing this setting:** If set incorrectly, clicking the main product image might not lead to the product page, or the image switching might fail.
- **Recommended value:** This depends on your theme. Common values are `.product-thumbnail a`, `.product-image a`, or `a.product-cover`. You might need to inspect your theme’s HTML.
- **Merchant scenario / example:** If your theme wraps the main product image in `<a class="product-link">`, you would enter `a.product-link` here.

#### **Product title anchor**

- **What this setting does:** This is a technical setting to identify the link (anchor tag) around the product title.
- **Effect of changing this setting:** This setting helps the module ensure that the product title link remains functional and correctly points to the product page.
- **Recommended value:** This depends on your theme. Common values are `.product-title a`, `.product-name a`, or `h3 a`. You might need to inspect your theme’s HTML.
- **Merchant scenario / example:** If your product titles are wrapped in `<h3 class="product-name"><a href="...">`, you would enter `h3.product-name a` here.

#### **Additional class for miniature anchor**

- **What this setting does:** This allows you to add an extra CSS class to the anchor tags of the miniature images displayed by the module. This is useful for custom styling.
- **Effect of changing this setting:** The specified class will be added to the HTML of the miniature image links, allowing you to target them with custom CSS rules in your theme.
- **Recommended value:** Leave empty unless you have specific custom styling requirements.
- **Merchant scenario / example:** If you want to add a special border to your miniature images, you could enter `my-custom-miniature-class` here, then add CSS like `.my-custom-miniature-class img { border: 1px solid blue; }` to your theme.

#### **Picture switch method**

- **What this setting does:** This controls how the main product image changes when a customer interacts with the additional thumbnails.
- **Effect of changing this setting:**
  - *On click:* The main image changes only when a customer clicks on a thumbnail.
  - *On hover:* The main image changes when a customer moves their mouse cursor over a thumbnail (without clicking).
  - *Slider:* The module displays a small slider with navigation arrows, allowing customers to scroll through images. This often implies “on click” behavior for the slider controls.
- **Recommended value:** `On hover` for a quick, interactive experience. `On click` if you prefer explicit user action. `Slider` if you have many images and want a more compact presentation.
- **Merchant scenario / example:** For a fashion store, `On hover` allows customers to quickly preview different looks. For a product with many detailed images, `Slider` can keep the listing page clean while still offering full access to all visuals.

#### **Pictures for color combinations (duplicate setting, likely a bug or legacy)**

- **What this setting does:** This appears to be a duplicate of the “Display method” setting, specifically related to showing images for color combinations.
- **Effect of changing this setting:** It’s best to rely on the “Display method” setting for this functionality. If this is a separate control, it might override or conflict with the “Display method” setting.
- **Recommended value:** Ensure consistency with the “Display method” setting.
- **Merchant scenario / example:** If “Display method” is set to “Pictures for color combinations”, this setting should also be enabled or consistent.

#### **Pictures for each combination (duplicate setting, likely a bug or legacy)**

- **What this setting does:** Similar to the above, this appears to be a duplicate of the “Display method” setting, specifically related to showing images for all combinations.
- **Effect of changing this setting:** Best to rely on the “Display method” setting.
- **Recommended value:** Ensure consistency with the “Display method” setting.
- **Merchant scenario / example:** If “Display method” is set to “Pictures for each combination”, this setting should also be enabled or consistent.

#### **All product pictures (duplicate setting, likely a bug or legacy)**

- **What this setting does:** Similar to the above, this appears to be a duplicate of the “Display method” setting, specifically related to showing all product pictures.
- **Effect of changing this setting:** Best to rely on the “Display method” setting.
- **Recommended value:** Ensure consistency with the “Display method” setting.
- **Merchant scenario / example:** If “Display method” is set to “All product pictures”, this setting should also be enabled or consistent.

#### **Configuration Quick Reference Table**

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Position of the module | `displayProductAdditionalInfo` | Determines where additional images appear on product listings. |
| Module Configuration | Design of the module | `Universal` | Sets the visual style for the image thumbnails (Classic vs. Modern). |
| Module Configuration | Display method | `All product pictures` | Controls which images are shown (color combos, all combos, or all product images). |
| Module Configuration | In stock only | `Enabled` | Filters images to show only for in-stock product combinations. |
| Module Configuration | Display color boxes instead pictures | `Disabled` | Replaces image thumbnails with color swatches if enabled. |
| Module Configuration | Main product container on list of products | `.product-miniature` (or theme-specific) | CSS selector for the main product block on listing pages. |
| Module Configuration | Product cover picture css | `.product-thumbnail` (or theme-specific) | CSS selector for the main product image element. |
| Module Configuration | Product cover picture anchor css | `.product-thumbnail a` (or theme-specific) | CSS selector for the link wrapping the main product image. |
| Module Configuration | Product title anchor | `h3 a` (or theme-specific) | CSS selector for the link wrapping the product title. |
| Module Configuration | Additional class for miniature anchor | Leave empty | Adds a custom CSS class to miniature image links for styling. |
| Module Configuration | Picture switch method | `On hover` | Defines how the main image changes (click, hover, or slider). |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The additional images are not showing up on my product listings.**

- **A:** First, check your module configuration:
  - Ensure “Position of the module” is set to a hook that your theme actually renders (e.g., `displayProductAdditionalInfo`). If your theme is heavily customized, you might need to try different positions or consult a developer.
  - Verify the “Main product container on list of products”, “Product cover picture css”, “Product cover picture anchor css”, and “Product title anchor” settings. These are crucial CSS selectors that must match your theme’s HTML structure. Use your browser’s developer tools (F12) to inspect the elements on your category page and find the correct classes/IDs.
  - Make sure the products actually have multiple images uploaded in their product settings in the Back Office.
- **A:** Clear your PrestaShop cache: Go to **Advanced Parameters > Performance**, and click “Clear cache” in the top right. Also, clear your browser’s cache.

**Q2: The images appear, but they don’t switch when I hover/click.**

- **A:** This usually indicates an issue with the CSS selectors for the main product image or its container.
  - Double-check “Product cover picture css” and “Product cover picture anchor css”. These must accurately target the main image and its wrapping link.
  - Ensure there are no JavaScript errors on your page that might be preventing the module’s script from running. Check your browser’s developer console (F12 > Console tab).
  - If you have other modules that modify product listings, there might be a conflict. Try temporarily disabling other front-office modules to isolate the issue.

**Q3: The images look distorted or the styling is off.**

- **A:**
  - Try switching the “Design of the module” setting between `Classic theme` and `Universal` to see if one integrates better with your theme.
  - Your theme might have conflicting CSS rules. You can use the “Additional class for miniature anchor” setting to add a custom class, then use custom CSS in your theme to override conflicting styles.
  - Ensure your uploaded product images are of consistent quality and aspect ratio.

**Q4: I’m using a custom theme, and the module doesn’t seem to work at all.**

- **A:** Custom themes often use different HTML structures and CSS classes than default PrestaShop themes.
  - You will almost certainly need to adjust the CSS selectors for “Main product container on list of products”, “Product cover picture css”, “Product cover picture anchor css”, and “Product title anchor” to match your theme’s specific markup. This usually requires basic knowledge of HTML/CSS inspection using browser developer tools.
  - Your custom theme might not be calling the standard PrestaShop hooks that the module uses. You might need to manually add the module’s hook calls to your theme’s `.tpl` files (consult your theme developer or a PrestaShop developer for this).

**Q5: The module slows down my page loading speed.**

- **A:** While the module is optimized, displaying many additional images can naturally increase page load time.
  - Ensure your product images are optimized for web (compressed, appropriate dimensions).
  - Consider using the “In stock only” option to reduce the number of images loaded for out-of-stock items.
  - If you have many images per product, consider using the `Slider` method, which often loads images more efficiently or lazily.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the “Product pictures on product listings” module, intended for developers, webmasters, and technical agencies.

### 4.1 Architecture Overview

The `productlistpics` module is primarily a front-office feature module designed to inject additional product image functionality into existing product listing templates. It leverages PrestaShop’s hook system to render its content and uses JavaScript to handle dynamic image switching (hover/click) or slider functionality. Configuration is managed through the standard `getContent()` method in the main module class, storing settings in `ps_configuration`. The module does not introduce custom database tables or complex `ObjectModel` entities.

### 4.2 Controllers (`controllers/`)

This module does **not** contain any custom Front-Office or Back-Office Admin Controllers. All logic is encapsulated within the main module class and its associated templates and assets.

### 4.3 Core Classes & Models (`classes/`)

This module does **not** contain any custom classes or `ObjectModel` entities in the `classes/` directory. All core logic resides within `productlistpics.php`.

### 4.4 JavaScript Assets (`views/js/`)

The module includes several JavaScript files, primarily for handling image switching and slider functionality.

- `productlistpics/js/owl-carousel/owl.carousel.js`:
  - **Scope:** Front-office.
  - **Description:** This is the core Owl Carousel library, a popular touch-enabled jQuery plugin for responsive carousels. It provides the fundamental functionality for creating image sliders.
- `productlistpics/js/owl-carousel/owl.run.js`:
  - **Scope:** Front-office.
  - **Description:** This script likely contains the initialization and configuration code for Owl Carousel instances used by the module. It sets up the slider behavior, responsiveness, and navigation options based on module settings.
- `productlistpics/js/plp-replacement.js`:
  - **Scope:** Front-office.
  - **Description:** This script is likely responsible for the core logic of replacing the main product image when a thumbnail is interacted with. It listens for events (click/hover) on the generated thumbnails and updates the `src` and `srcset` attributes of the main product image, potentially also updating the `href` of the main image’s anchor tag.
- `productlistpics/js/productlistpics-mouseover.js`:
  - **Scope:** Front-office.
  - **Description:** This script specifically implements the “On hover” picture switch method. It attaches `mouseover` and `mouseout` event listeners to the miniature image anchors to trigger the main image replacement.
- `productlistpics/js/productlistpics.js`:
  - **Scope:** Front-office.
  - **Description:** This is likely the main module’s front-office JavaScript entry point. It might handle the “On click” picture switch method, general DOM manipulation related to injecting the thumbnails, and potentially orchestrating the loading of other scripts based on configuration.
- `productlistpics/js/slider-productlistpics-mouseover.js`:
  - **Scope:** Front-office.
  - **Description:** This script combines slider functionality with hover-based image switching. It would likely initialize the Owl Carousel and then add hover listeners to the slider items to update the main product image.
- `productlistpics/js/slider-productlistpics.js`:
  - **Scope:** Front-office.
  - **Description:** This script integrates the Owl Carousel slider with click-based image switching. It initializes the slider and handles clicks on slider items to update the main product image.

### 4.5 CSS Stylesheets (`views/css/`)

The module includes several CSS files for styling the injected elements and the Owl Carousel.

- `productlistpics/css.css`:
  - **Scope:** Front-office.
  - **Description:** General styling for the module’s elements, such as the container for additional pictures, thumbnail sizing, and basic layout.
- `productlistpics/js/owl-carousel/owl.carousel.css`:
  - **Scope:** Front-office.
  - **Description:** Base styles for the Owl Carousel plugin, defining the structure and default appearance of the slider.
- `productlistpics/js/owl-carousel/owl.theme.css`:
  - **Scope:** Front-office.
  - **Description:** Default theme for Owl Carousel, providing visual styling for navigation buttons, dots, and overall slider aesthetics.
- `productlistpics/js/owl-carousel/owl.transitions.css`:
  - **Scope:** Front-office.
  - **Description:** CSS for various transition effects used by Owl Carousel (e.g., fade, slide).
- `productlistpics/productlistpics-classic.css`:
  - **Scope:** Front-office.
  - **Description:** Specific styling rules applied when the “Classic theme” design option is selected in the module configuration. This targets older PrestaShop themes or themes mimicking the classic look.
- `productlistpics/productlistpics.css`:
  - **Scope:** Front-office.
  - **Description:** Main styling for the module, likely containing rules for the “Universal” design option and general overrides or enhancements.

**Key CSS class selectors developers can override:**

- `.productlistpics-container`: The main wrapper for the additional images.
- `.productlistpics-thumb`: Individual thumbnail containers.
- `.productlistpics-thumb img`: The actual image within the thumbnail.
- `.owl-carousel`, `.owl-item`, `.owl-nav`, `.owl-dots`: Standard Owl Carousel selectors for slider customization.

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses Smarty templates to render its content within various PrestaShop hooks.

- **Hook templates (`views/templates/hook/`)**:
  - `productlistpics/header.tpl`:
    - **Hook:** `displayHeader` (or similar, typically registered in `install()`).
    - **Output:** This template is responsible for including the necessary CSS and JavaScript assets for the module to function on the front-office. It conditionally loads scripts based on the chosen “Picture switch method” (e.g., `owl.carousel.js`, `productlistpics-mouseover.js`, `slider-productlistpics.js`).
  - `productlistpics/html.tpl`:
    - **Hook:** This is a generic template that might be included by other templates or used for specific content blocks. Its exact usage depends on how the module’s main PHP file renders content.
    - **Output:** Contains the HTML structure for displaying the additional product images, including loops for iterating through images and conditional logic for displaying color boxes or image thumbnails.
  - `productlistpics/productFooter.tpl`:
    - **Hook:** `displayFooterProduct` (as configured in “Position of the module”).
    - **Output:** Renders the additional product images in the footer section of a product block on listing pages. It likely includes `html.tpl` or similar logic.
  - `productlistpics/productPage.tpl`:
    - **Hook:** This template is likely used for hooks like `displayProductAdditionalInfo`, `displayAfterProductThumbs`, `displayProductDeliveryTime`, `displayProductListReviews` (as configured in “Position of the module”).
    - **Output:** Renders the additional product images within the specified product listing hook. It contains the core logic for generating the image thumbnails or color boxes and setting up the necessary data attributes for JavaScript interaction.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  The module does **not** create any custom database tables. All its configuration settings are stored in the `ps_configuration` table using keys like `PLP_TYPE`, `PLP_INSTOCK`, `PLP_METHOD`, `PLP_SWITCH`, `PLP_DESIGN`, `PLP_POSITION`, and various CSS selector keys (`pls_product_miniature`, `pls_product_miniature_img`, etc.).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Injects CSS and JavaScript assets required by the module. |
| `displayProductAdditionalInfo` | Within the product miniature block, often below the main image or title. | Renders the additional product image thumbnails/slider. |
| `displayAfterProductThumbs` | After the main product image thumbnails (if present). | Renders the additional product image thumbnails/slider. |
| `displayFooterProduct` | In the footer area of each product miniature block. | Renders the additional product image thumbnails/slider. |
| `displayProductDeliveryTime` | Near the product delivery time information in the product miniature. | Renders the additional product image thumbnails/slider. |
| `displayProductListReviews` | Near product review stars/count in the product miniature. | Renders the additional product image thumbnails/slider. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Product pictures on product listings” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
