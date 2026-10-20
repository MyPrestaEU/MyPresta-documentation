---
title: "Last product reviews - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Last product reviews PrestaShop module by MyPresta.eu."
sidebar:
  label: "Last product reviews - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Last product reviews Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/last-product-reviews.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/last-product-reviews/)
>
> ---


# Last product reviews

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the “Last product reviews” module. You’ll find all the settings here to control how and where your reviews are displayed.

#### **Display reviews in**

- **What this setting does:** This option determines where the “Last product reviews” block will appear on your website. You can choose from several standard PrestaShop hook positions.
- **Effect of changing this setting:**
  - *When set to “Header”:* The review block will appear at the very top of your store, often above or below your main navigation. This offers maximum visibility.
  - *When set to “Left Column”:* The review block will appear in the left sidebar of your store, if your theme has one.
  - *When set to “Right Column”:* The review block will appear in the right sidebar of your store, if your theme has one.
  - *When set to “Product page”:* The review block will appear on individual product pages. This is great for cross-selling or showing general social proof while a customer is considering a purchase.
  - *When set to “Footer”:* The review block will appear at the bottom of every page, typically above the copyright information.
- **Recommended value:** “Left Column” or “Right Column” for general visibility, or “Product page” if you want to emphasize reviews during the buying decision process. “Header” can be very impactful but might take up too much prime real estate depending on your theme.
- **Merchant scenario / example:** If you want customers to see recent reviews no matter where they browse, choose “Left Column”. If you want to encourage purchases on product pages, select “Product page”.

#### **Number of reviews to display**

- **What this setting does:** This controls how many individual product reviews will be shown in the “Last product reviews” block.
- **Effect of changing this setting:**
  - *When set to a low number (e.g., 3):* The block will be compact, showing only a few reviews. This is good for saving space but might not convey as much social proof.
  - *When set to a higher number (e.g., 10):* The block will be larger, displaying more reviews. This offers more social proof but requires more screen space.
- **Recommended value:** 3-5 for columns, 5-8 for header/footer, depending on your theme’s layout and available space.
- **Merchant scenario / example:** If your left column is narrow, set this to 3 to keep the block from becoming too long. If you have a wide footer, you might set it to 6 to showcase more feedback.

#### **Display customer name**

- **What this setting does:** This switch determines whether the name of the customer who left the review will be visible in the review block.
- **Effect of changing this setting:**
  - *When enabled (YES):* Each review will show the customer’s name (e.g., “Review by John D.”). This adds authenticity and personalization.
  - *When disabled (NO):* The customer’s name will be hidden, and only the review content and product will be shown. This might be preferred for privacy or a more minimalist design.
- **Recommended value:** YES. Displaying customer names adds credibility and makes the reviews feel more genuine.
- **Merchant scenario / example:** To maximize trust, enable this. If you’re concerned about customer privacy or prefer a very clean look, you might disable it.

#### **Display product name**

- **What this setting does:** This switch controls whether the name of the product being reviewed will be displayed alongside the review text.
- **Effect of changing this setting:**
  - *When enabled (YES):* Each review will clearly state which product it refers to (e.g., “Product: Super Widget”). This helps customers understand the context of the review.
  - *When disabled (NO):* Only the review text and customer name (if enabled) will be shown, without explicit mention of the product. This makes the block more generic.
- **Recommended value:** YES. It’s crucial for customers to know which product is being reviewed.
- **Merchant scenario / example:** If a customer sees a glowing review, they’ll want to know what product it’s for. Enabling this allows them to click through and potentially buy that specific item.

#### **Display review content**

- **What this setting does:** This switch determines whether the actual text of the customer’s review will be shown in the block.
- **Effect of changing this setting:**
  - *When enabled (YES):* The full or truncated text of the review will be displayed. This provides detailed feedback to potential buyers.
  - *When disabled (NO):* Only the rating (stars), customer name, and product name will be shown, without the written review. This creates a very compact block, focusing only on the star ratings.
- **Recommended value:** YES. The review content is the most valuable part of social proof.
- **Merchant scenario / example:** To give customers a quick overview of what others are saying, enable this. If you only want to show star ratings as a quick trust signal, you could disable it.

#### **Display review stars**

- **What this setting does:** This switch controls whether the star rating (e.g., 5 out of 5 stars) associated with each review will be visible.
- **Effect of changing this setting:**
  - *When enabled (YES):* The star rating will be prominently displayed for each review. This is a quick visual indicator of product quality.
  - *When disabled (NO):* The star rating will be hidden, and only the text content (if enabled) will be shown. This is generally not recommended as star ratings are a universal trust signal.
- **Recommended value:** YES. Star ratings are incredibly effective for quickly conveying product satisfaction.
- **Merchant scenario / example:** Always enable this to give customers an instant visual cue of product quality and customer satisfaction.

#### **Display product image**

- **What this setting does:** This switch determines if the main image of the product being reviewed will be shown next to its review.
- **Effect of changing this setting:**
  - *When enabled (YES):* A small thumbnail of the product image will appear with each review. This makes the block more visually appealing and helps customers quickly identify the product.
  - *When disabled (NO):* No product image will be shown, making the block more text-focused.
- **Recommended value:** YES. Product images significantly enhance the visual appeal and clarity of the review block.
- **Merchant scenario / example:** To make your review block more engaging and help customers quickly associate reviews with specific products, enable product images.

#### **Display product price**

- **What this setting does:** This switch controls whether the current price of the product being reviewed will be displayed in the review block.
- **Effect of changing this setting:**
  - *When enabled (YES):* The product’s price will be shown. This can be useful for customers who are price-sensitive or want to quickly see if a reviewed product fits their budget.
  - *When disabled (NO):* The price will not be displayed, keeping the focus solely on the review and product details.
- **Recommended value:** NO, unless you specifically want to highlight product prices in the review block. It can sometimes clutter the display.
- **Merchant scenario / example:** If you are running a sale and want to highlight reviewed products that are currently discounted, you might enable this. Otherwise, it’s often better to keep the focus on the review itself.

#### **Display product link**

- **What this setting does:** This switch determines if the product name (or image, if enabled) in the review block will be a clickable link that takes the customer directly to the product page.
- **Effect of changing this setting:**
  - *When enabled (YES):* Customers can click on the product name/image to navigate to the full product page, where they can learn more and potentially make a purchase. This is crucial for driving traffic to product pages.
  - *When disabled (NO):* The product name/image will be static text/image, and customers cannot click through. This reduces the module’s ability to drive conversions.
- **Recommended value:** YES. Always enable this to allow customers to easily explore reviewed products.
- **Merchant scenario / example:** A customer sees a great review for a “Bluetooth Speaker.” If the product name is clickable, they can immediately go to the speaker’s page to buy it.

#### **Display date of review**

- **What this setting does:** This switch controls whether the date when the review was submitted will be displayed.
- **Effect of changing this setting:**
  - *When enabled (YES):* The date (e.g., “Reviewed on 2023-10-26”) will be shown. This adds transparency and assures customers that the reviews are recent and relevant.
  - *When disabled (NO):* The date will be hidden.
- **Recommended value:** YES. Recent reviews are more impactful and trustworthy.
- **Merchant scenario / example:** Showing the date helps customers see that your store is active and constantly receiving new feedback, building confidence.

#### **Display review title**

- **What this setting does:** This switch determines if the title of the review (if customers provide one) will be displayed.
- **Effect of changing this setting:**
  - *When enabled (YES):* If a review has a title (e.g., “Amazing Product!”), it will be shown, often in bold, providing a quick summary of the review’s sentiment.
  - *When disabled (NO):* Only the main review content will be shown, without a separate title.
- **Recommended value:** YES. Review titles are excellent for quickly grabbing attention and summarizing the review’s essence.
- **Merchant scenario / example:** A customer quickly scanning reviews can get the gist from titles like “Great Value” or “Disappointed” before reading the full text.

#### **Minimum rating to display**

- **What this setting does:** This filter allows you to set a minimum star rating for reviews to be included in the “Last product reviews” block.
- **Effect of changing this setting:**
  - *When set to 1 star:* All reviews (1-5 stars) will be displayed.
  - *When set to 3 stars:* Only reviews with 3, 4, or 5 stars will be displayed. Reviews with 1 or 2 stars will be excluded.
  - *When set to 5 stars:* Only perfect 5-star reviews will be displayed.
- **Recommended value:** 3 or 4 stars. While transparency is good, you might want to highlight mostly positive feedback in this prominent block.
- **Merchant scenario / example:** To ensure your “Last product reviews” block always showcases positive feedback, set this to 4 stars. This helps maintain a positive image while still being authentic.

#### **Display only reviews from selected category**

- **What this setting does:** This option allows you to filter the reviews displayed to only those associated with products from a specific category.
- **Effect of changing this setting:**
  - *When “No” is selected:* Reviews from all categories will be considered for display.
  - *When a specific category (e.g., “Electronics”) is selected:* Only reviews for products within the “Electronics” category (and its subcategories) will be shown.
- **Recommended value:** “No” for general social proof. Select a category if the review block is placed in a context where only specific product types are relevant (e.g., on a category page).
- **Merchant scenario / example:** If you place the review block on your “T-Shirts” category page, you might select the “T-Shirts” category here to ensure only relevant reviews are shown, enhancing the customer experience.

#### **Display only reviews from selected product**

- **What this setting does:** This option allows you to filter the reviews displayed to only those associated with a specific product.
- **Effect of changing this setting:**
  - *When “No” is selected:* Reviews for all products will be considered for display.
  - *When a specific product (e.g., “My Awesome Gadget”) is selected:* Only reviews for “My Awesome Gadget” will be shown.
- **Recommended value:** “No” for general social proof. Select a product if the review block is placed in a context where only a single product’s reviews are relevant (e.g., on a custom landing page for that product).
- **Merchant scenario / example:** If you have a special promotional page for your “Best-Selling Coffee Maker,” you could configure this block to only show reviews for that specific coffee maker on that page.

#### **Display reviews as slider**

- **What this setting does:** This switch enables or disables a dynamic slider (carousel) for the reviews block.
- **Effect of changing this setting:**
  - *When enabled (YES):* The reviews will automatically scroll or allow customers to navigate through them using arrows/dots. This is great for displaying many reviews in a compact space.
  - *When disabled (NO):* The reviews will be displayed as a static list, one after another.
- **Recommended value:** YES, especially if you display more than 3-4 reviews or if the block is in a narrow column.
- **Merchant scenario / example:** If you want to show 8 reviews in your left column but don’t want the column to become excessively long, enabling the slider will make it compact and interactive.

#### **Slider auto play**

- **What this setting does:** If “Display reviews as slider” is enabled, this setting controls whether the slider automatically moves to the next review without user interaction.
- **Effect of changing this setting:**
  - *When enabled (YES):* The slider will automatically transition between reviews after a set delay.
  - *When disabled (NO):* The slider will only move when the customer clicks navigation arrows or dots.
- **Recommended value:** YES, but ensure the “Slider auto play speed” is set to a reasonable duration.
- **Merchant scenario / example:** To keep the review block dynamic and ensure all reviews get some visibility, enable auto-play.

#### **Slider auto play speed (in ms)**

- **What this setting does:** If “Slider auto play” is enabled, this setting determines how long (in milliseconds) each review is displayed before the slider automatically moves to the next one.
- **Effect of changing this setting:**
  - *A lower number (e.g., 2000ms = 2 seconds):* Reviews will change quickly.
  - *A higher number (e.g., 5000ms = 5 seconds):* Reviews will stay visible longer, giving customers more time to read.
- **Recommended value:** 4000-6000 (4-6 seconds) to give customers enough time to read a review without feeling rushed.
- **Merchant scenario / example:** Set this to 5000ms so customers have ample time to read each review as it slides by.

#### **Slider controls**

- **What this setting does:** If “Display reviews as slider” is enabled, this controls whether navigation arrows (left/right) are visible for customers to manually browse reviews.
- **Effect of changing this setting:**
  - *When enabled (YES):* Arrows will appear on the slider, allowing manual navigation.
  - *When disabled (NO):* No arrows will be shown. Customers can only rely on auto-play (if enabled) or touch/swipe gestures.
- **Recommended value:** YES. Providing controls improves user experience, even with auto-play.
- **Merchant scenario / example:** To give customers full control over browsing reviews, enable slider controls.

#### **Slider pager**

- **What this setting does:** If “Display reviews as slider” is enabled, this controls whether small dots (pagination) are visible, indicating the total number of reviews and the current review being displayed.
- **Effect of changing this setting:**
  - *When enabled (YES):* Dots will appear, showing progress and allowing direct jumps to specific reviews.
  - *When disabled (NO):* No dots will be shown.
- **Recommended value:** YES. Pagers provide a clear visual indication of how many reviews are available and where the customer is in the sequence.
- **Merchant scenario / example:** To help customers understand how many reviews are in the slider and easily jump to a specific one, enable the slider pager.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Display reviews in | Left Column / Right Column | Controls the position of the review block in your store. |
| Module Configuration | Number of reviews to display | 3-5 (columns), 5-8 (header/footer) | Sets how many reviews are visible in the block. |
| Module Configuration | Display customer name | YES | Shows the name of the reviewer for authenticity. |
| Module Configuration | Display product name | YES | Clearly links the review to its product. |
| Module Configuration | Display review content | YES | Shows the actual text of the review. |
| Module Configuration | Display review stars | YES | Visual indicator of product rating. |
| Module Configuration | Display product image | YES | Makes the block more visually appealing and identifiable. |
| Module Configuration | Display product price | NO | Shows product price (can clutter, usually not needed). |
| Module Configuration | Display product link | YES | Allows customers to click through to the product page. |
| Module Configuration | Display date of review | YES | Shows when the review was submitted, proving recency. |
| Module Configuration | Display review title | YES | Displays the review’s title for quick summaries. |
| Module Configuration | Minimum rating to display | 3 or 4 stars | Filters out lower-rated reviews for a positive display. |
| Module Configuration | Display only reviews from selected category | No | Filters reviews by product category. |
| Module Configuration | Display only reviews from selected product | No | Filters reviews by a specific product. |
| Module Configuration | Display reviews as slider | YES | Presents reviews in a dynamic, scrolling carousel. |
| Module Configuration | Slider auto play | YES | Automatically advances the slider. |
| Module Configuration | Slider auto play speed (in ms) | 4000-6000 | Sets the duration each review is shown in the slider. |
| Module Configuration | Slider controls | YES | Shows navigation arrows for manual slider control. |
| Module Configuration | Slider pager | YES | Shows dots for slider pagination. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve configured the module, but the review block isn’t showing up on my store.**
A:

1. **Check Module Position:** Go to **Design > Positions** (or **Modules > Positions** in older PrestaShop versions) in your Back Office. Search for `displayLastReviews` (or the hook you selected in the module configuration). Ensure the module “Last product reviews” is listed and enabled for that hook. If not, click “Transplant a module” and add it to the desired hook.
2. **Clear Cache:** PrestaShop often caches content. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” and “Clear cache” buttons).
3. **Check for Reviews:** Ensure you actually have approved product reviews in your store. The module can only display reviews that exist and are visible.
4. **Theme Compatibility:** While the module is designed to be compatible, some highly customized themes might require minor CSS adjustments. Check your browser’s developer console for any JavaScript errors.

**Q: The reviews are showing, but they don’t look right (e.g., bad styling, images too big).**
A:

1. **Theme Conflicts:** Your theme’s CSS might be overriding the module’s styles. You can try to add custom CSS to your theme’s `custom.css` file (if it has one) or directly edit `lastreviews/views/css/lastreviews.css` (though this is not update-safe).
2. **Image Sizes:** If product images are too large, check your theme’s image settings or the module’s CSS. The module uses a standard image size, but your theme might be rendering it differently.
3. **Slider Issues:** If the slider isn’t working, ensure “Display reviews as slider” is enabled. Check for JavaScript errors in your browser console, as other modules or theme scripts might be conflicting.

**Q: Can I display reviews from a specific product or category only?**
A: Yes! In the module configuration, you have options for “Display only reviews from selected category” and “Display only reviews from selected product.” Use these dropdowns to filter the reviews shown in the block.

**Q: My reviews are in multiple languages. Will the module display them correctly?**
A: The module relies on PrestaShop’s standard review system. If your reviews are correctly associated with languages in PrestaShop, the module should display the reviews in the active front-office language. Ensure your theme and PrestaShop are correctly configured for multi-language content.

**Q: How do I get more reviews to display?**
A: This module only *displays* existing reviews. To get more reviews, you need to encourage customers to leave them. Consider using a separate module for review reminders, offering incentives, or making the review submission process very easy on your product pages.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Last product reviews” module is a standard PrestaShop module following an MVC-like pattern. It primarily operates as a front-office feature, hooking into various display points to render a block of recent product reviews. It leverages PrestaShop’s core `ProductComment` (or similar) functionality to fetch review data. The module’s main logic resides in `index.php`, handling configuration and hook registration, while templates and assets manage the front-end display. It uses a third-party JavaScript library, `lightslider.js`, for carousel functionality.

### 4.2 Controllers (`controllers/`)

This module does not contain any custom Front-Office or Back-Office Admin Controllers. All configuration is handled directly within the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or `ObjectModel`s in a `classes/` directory. It relies on PrestaShop’s core `ProductComment` (or equivalent, depending on PrestaShop version and if the official Product Comments module is installed) to fetch review data.

### 4.4 JavaScript Assets (`views/js/`)

- **`lastreviews/lib/src/js/lightslider.js`**
  - **Scope:** Front-office.
  - **Purpose:** This is the core JavaScript library for creating responsive content sliders/carousels. It provides the functionality for the “Display reviews as slider” feature.
  - **Functionality:** Binds to a `<ul>` element (or similar container) to transform it into a responsive slider. It handles auto-play, navigation controls (arrows), pagination (dots), touch/swipe gestures, and responsive resizing.
  - **Dependencies:** Typically requires jQuery.

### 4.5 CSS Stylesheets (`views/css/`)

- **`lastreviews/lib/src/css/lightslider.css`**

  - **Scope:** Front-office customer styling.
  - **Purpose:** Provides the default styling for the `lightslider.js` library, including basic layout, navigation arrows, pager dots, and animation styles for the slider.
  - **Key Selectors:** `.lightSlider`, `.lSAction > .lSPrev`, `.lSAction > .lSNext`, `.lSPager`, etc. Developers can override these to match their theme’s aesthetic.
- **`lastreviews/views/css/lastreviews.css`**

  - **Scope:** Front-office customer styling.
  - **Purpose:** Contains custom styling specific to the “Last product reviews” module’s display block. This includes styling for the review container, individual review items, product images, star ratings, and text elements.
  - **Key Selectors:** `.last-reviews-block`, `.last-review-item`, `.review-product-image`, `.review-stars`, `.review-customer-name`, `.review-product-name`, etc. These selectors are designed to be easily overridden by a custom theme’s CSS for integration.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - **`lastreviews/views/templates/hook/admin-tips.tpl`**
    - **Purpose:** This template is likely used in the Back Office configuration page (`getContent()`) to display administrative tips or instructions to the merchant. It’s not rendered in the front office.
    - **Content:** Typically contains HTML for informational messages, links to documentation, or warnings.
  - **`lastreviews/views/templates/hook/last-reviews.tpl`**
    - **Purpose:** This is the main front-office template responsible for rendering the “Last product reviews” block. It’s hooked into various display points (e.g., `displayLeftColumn`, `displayFooter`).
    - **Data:** Receives an array of review data (customer name, product name, rating, content, date, image, link) from the module’s PHP logic.
    - **Structure:** Iterates through the provided reviews, conditionally displaying elements based on module configuration (e.g., customer name, product image, slider). It includes the necessary HTML structure for the `lightslider.js` to initialize if the slider option is enabled.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create its own custom database tables. It relies on PrestaShop’s core tables for product reviews, typically `ps_product_comment` and related tables (if the official Product Comments module is installed and active).
  - Configuration settings are stored in the `ps_configuration` table, with keys typically prefixed by `LASTREVIEWS_` (e.g., `LASTREVIEWS_DISPLAY_IN`, `LASTREVIEWS_NUM_REVIEWS`).
- **Registered Hooks Table**:

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `displayHeader` | In the `<head>` section of all front-office pages. | Used to include CSS/JS assets and potentially render the review block at the top of the page. |
  | `displayLeftColumn` | In the left sidebar of front-office pages. | Renders the review block in the left column. |
  | `displayRightColumn` | In the right sidebar of front-office pages. | Renders the review block in the right column. |
  | `displayFooter` | In the footer section of all front-office pages. | Renders the review block in the footer. |
  | `displayProductAdditionalInfo` (or similar product page hook) | On the product page, typically below the main product information. | Renders the review block on individual product pages. |
  | `actionFrontControllerSetMedia` | Executed when a front controller sets its media (CSS/JS). | Used to register the module’s CSS and JavaScript files (`lightslider.js`, `lastreviews.css`) to be loaded on the front office. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Last product reviews” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
