---
title: "Google product plus button + coupon - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Google product plus button + coupon PrestaShop module by MyPresta.eu."
sidebar:
  label: "Google product plus button + coupon - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Google product plus button + coupon Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/google-product-plus-button-coupon.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/google-product-plus-button-coupon/)
>
> ---


# Google product plus button + coupon

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and any module that interacts with external APIs.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the “Google product plus button + coupon” module. You’ll find all the settings here to control how the Google +1 button appears and how the coupons are generated.

#### **General Settings**

- **Update\_ / Updatev\_ (Internal Settings)**

  - **What this setting does:** These are internal module settings used for tracking updates and versioning. They are not meant for direct merchant interaction.
  - **Effect of changing this setting:** You should **never** manually change these values. Doing so could interfere with module updates or internal processes.
  - **Recommended value:** Leave as is.
  - **Merchant scenario / example:** These settings ensure your module can be updated correctly when new versions are released by MyPresta.eu.
- **Voucher Code (gc\_voucher)**

  - **What this setting does:** This is the **discount percentage** that will be applied to the coupon generated for customers who click the +1 button.
  - **Effect of changing this setting:**
    - *When set to `10` (for 10%):* Customers who +1 a product will receive a coupon for 10% off their next purchase.
    - *When set to `0` or left empty:* No discount will be applied, essentially making the coupon worthless.
  - **Recommended value:** A reasonable discount percentage, e.g., `5`, `10`, or `15`.
  - **Merchant scenario / example:** You want to offer a 10% discount to encourage social sharing. You would enter `10` here.
- **Show Prices (gc\_show\_prices)**

  - **What this setting does:** Determines whether the original and discounted prices are displayed alongside the coupon offer.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* The customer will see the original price and the price after the discount is applied, making the value of the coupon clearer.
    - *When disabled (No):* Only the coupon code will be shown, without explicit price comparisons.
  - **Recommended value:** `Yes`. Showing the price difference often increases the perceived value of the coupon.
  - **Merchant scenario / example:** A customer sees a product for $100. If “Show Prices” is enabled and the coupon is 10%, they’ll see “$100 -> $90 with coupon”, which is more compelling.
- **Show Total (gc\_show\_total)**

  - **What this setting does:** Controls whether the total order value (after discount) is displayed with the coupon. This is usually relevant if the coupon applies to the entire cart.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* The customer might see an estimated total order value with the discount applied.
    - *When disabled (No):* The focus remains on the product price or the coupon code itself.
  - **Recommended value:** `Yes`, especially if the coupon is cart-wide, as it helps the customer visualize their savings.
  - **Merchant scenario / example:** If the coupon applies to the whole cart, showing a potential total saving can encourage a larger purchase.
- **Show Products (gc\_show\_products)**

  - **What this setting does:** Determines if the specific product(s) to which the coupon applies are listed when the coupon is displayed.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* The coupon message might explicitly state “This coupon applies to [Product Name]”.
    - *When disabled (No):* The coupon is presented more generally, or it might be assumed to apply to the product just +1’d.
  - **Recommended value:** `Yes`, for clarity, unless your coupon is always store-wide.
  - **Merchant scenario / example:** If your coupon is only for the product the customer +1’d, showing the product name clarifies its usage.
- **Show Product URL (gc\_show\_product\_url)**

  - **What this setting does:** Controls whether the URL of the product that was +1’d is included in the coupon display.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* The customer sees a direct link back to the product page, which can be useful if they navigate away.
    - *When disabled (No):* The URL is omitted.
  - **Recommended value:** `Yes`, for better user experience and navigation.
  - **Merchant scenario / example:** A customer gets a coupon, then closes the pop-up. Having the product URL helps them quickly return to the product they were interested in.
- **Last Tab (gc\_lasttab)**

  - **What this setting does:** This setting likely controls which tab or section of the product page the Google +1 button and coupon information will appear in, if your theme uses a tabbed product description area.
  - **Effect of changing this setting:**
    - *When set to `1` (or similar value):* The module content will appear in the last tab of the product page.
    - *When set to `0` (or similar value):* The module content will appear in the first tab or a default location.
  - **Recommended value:** Experiment with `1` to see if it fits your theme’s layout. If your theme doesn’t use tabs, this setting might have no visible effect.
  - **Merchant scenario / example:** Your product page has “Description,” “Data Sheet,” and “Reviews” tabs. Setting this to `1` might place the +1 button and coupon in a new “Social Share” tab or at the end of the “Description” tab.
- **Position (gc\_position)**

  - **What this setting does:** Determines the general area on the product page where the Google +1 button and coupon offer will be displayed. This maps to PrestaShop’s hook system.
  - **Effect of changing this setting:**
    - *Changing the value:* Moves the module’s content to different locations on the product page (e.g., above “Add to Cart”, below description, in a side column).
  - **Recommended value:** `displayproductActions` or `displayproductFooter` are common and effective places. Test different positions to see what integrates best with your theme and is most visible to customers.
  - **Merchant scenario / example:** You want the +1 button to be very prominent, so you choose `displayproductActions` to place it near the “Add to Cart” button.
- **Number of Likes (gc\_nblikes)**

  - **What this setting does:** This setting likely controls the minimum number of +1s required before a coupon is issued, or it might be a display setting for the +1 count. Given the module’s core functionality, it’s more likely related to the coupon trigger.
  - **Effect of changing this setting:**
    - *When set to `1` (or `0`):* A coupon is issued immediately upon a single +1.
    - *When set to `5`:* A coupon might only be issued after 5 unique +1s (less likely given the instant reward nature, but possible for a “group coupon” feature). More likely, it controls the display of the +1 count.
  - **Recommended value:** `1` (or `0` if it means “always show”). The module’s strength is instant gratification.
  - **Merchant scenario / example:** You want every customer who +1s to get a coupon, so you set this to `1`.
- **Button Style (gc\_button\_style)**

  - **What this setting does:** Allows you to choose the visual style or size of the Google +1 button.
  - **Effect of changing this setting:**
    - *Changing the value:* Alters the appearance of the +1 button (e.g., small, medium, large, tall, with or without count).
  - **Recommended value:** Choose a style that is visible but doesn’t disrupt your product page design. “Medium” or “Standard” are usually good starting points.
  - **Merchant scenario / example:** Your product page has limited space, so you choose a “small” button style.
- **Share Mode (gcshare\_mode)**

  - **What this setting does:** This setting likely controls how the sharing functionality works, possibly offering different ways for the customer to share or interact with the Google+ platform.
  - **Effect of changing this setting:**
    - *Changing the value:* Could alter the pop-up behavior or the specific Google+ sharing dialog that appears.
  - **Recommended value:** Leave at the default unless you have a specific reason to change it and understand the implications for Google+ integration.
  - **Merchant scenario / example:** You might experiment with different modes if you find the default sharing experience is not optimal for your customers.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Voucher Code (gc\_voucher) | 10 | Discount percentage for the generated coupon. |
| Module Configuration | Show Prices (gc\_show\_prices) | Yes | Display original and discounted prices with coupon. |
| Module Configuration | Show Total (gc\_show\_total) | Yes | Display estimated total order value with discount. |
| Module Configuration | Show Products (gc\_show\_products) | Yes | List specific product(s) the coupon applies to. |
| Module Configuration | Show Product URL (gc\_show\_product\_url) | Yes | Include the product URL in the coupon display. |
| Module Configuration | Last Tab (gc\_lasttab) | 1 (or theme-dependent) | Position in product page tabs (if applicable). |
| Module Configuration | Position (gc\_position) | displayproductActions / displayproductFooter | General placement of the button and coupon on product page. |
| Module Configuration | Number of Likes (gc\_nblikes) | 1 | Minimum +1s for coupon (likely 1 for instant reward). |
| Module Configuration | Button Style (gc\_button\_style) | Standard / Medium | Visual size and style of the Google +1 button. |
| Module Configuration | Share Mode (gcshare\_mode) | Default | Controls the Google+ sharing interaction. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

- **Q: The Google +1 button isn’t showing up on my product pages.**

  - **A:** First, check the “Position (gc\_position)” setting in the module configuration. Ensure you’ve selected a hook that is actually rendered by your theme on the product page. Some custom themes might not implement all standard PrestaShop hooks.
  - **A:** Clear your PrestaShop cache (Advanced Parameters > Performance > Clear cache).
  - **A:** Check for JavaScript errors in your browser’s developer console (F12). Conflicts with other modules or theme scripts can sometimes prevent buttons from loading.
  - **A:** Ensure the module is enabled in the Module Manager.
- **Q: Customers are clicking +1 but not receiving a coupon.**

  - **A:** Verify that the “Voucher Code (gc\_voucher)” setting has a valid discount percentage (e.g., `10` for 10%). If it’s `0` or empty, no effective coupon will be generated.
  - **A:** Check the “Number of Likes (gc\_nblikes)” setting. If it’s set to a value greater than 1, the coupon won’t be issued until that threshold is met. For instant coupons, it should be 1.
  - **A:** Ensure there are no server-side errors preventing coupon generation. Check your PrestaShop error logs (Advanced Parameters > Logs).
- **Q: The button looks strange or is misaligned on my mobile site.**

  - **A:** This is often a CSS conflict with your theme. The module includes its own CSS, but your theme’s styles might override or conflict with it. You may need a web developer to inspect the CSS and make minor adjustments.
  - **A:** Try different “Button Style (gc\_button\_style)” options to see if a different size renders better.
- **Q: Can I customize the coupon message or validity?**

  - **A:** The module’s configuration primarily controls the discount percentage and display options. For advanced coupon rules (e.g., minimum purchase, specific categories, validity period), you would typically manage these within PrestaShop’s native “Catalog Price Rules” or “Cart Rules” (Discounts) section, and the module would generate a code that adheres to those rules if applicable, or you might need to manually create a specific rule that matches the module’s generated coupon. The module itself generates a basic percentage discount.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a technical deep dive into the “Google product plus button + coupon” module for developers and webmasters.

### 4.1 Architecture Overview

The module follows a standard PrestaShop module architecture, primarily leveraging the `Module` class and its `install()`, `uninstall()`, and `getContent()` methods. It integrates with the front-office via various display hooks to inject the Google +1 button and associated coupon logic. The coupon generation and display are handled dynamically using JavaScript and Smarty templates. There are no custom `ObjectModel` classes or dedicated Admin Controllers beyond the main module configuration.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. All front-office functionality is handled via module hooks and direct template rendering.
- **Back-Office Admin Controllers**: None. Configuration is entirely within the main module’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

- No custom classes or `ObjectModel` definitions are present in the `classes/` directory. All core logic resides within `googlecoupon/googlecoupon.php`.

### 4.4 JavaScript Assets (`views/js/`)

- `googlecoupon/lib/voucherengine/script.js`
  - **Scope:** Front-office.
  - **Responsibility:** This script is likely responsible for the core logic of the coupon generation and display. It would listen for the Google +1 button click event, trigger the coupon generation process (possibly via an AJAX call to the module’s main file or a direct JavaScript function), and then display the coupon code to the user. It might also handle the interaction with the Google+ API (though Google+ APIs have largely been deprecated or integrated into other services).
- `googlecoupon/trusted.js`
  - **Scope:** Front-office.
  - **Responsibility:** This script’s purpose is less clear from the name alone, but it could be related to ensuring the integrity of the +1 action, tracking, or integration with other trusted services. It might also be a remnant of older Google+ API integrations.

### 4.5 CSS Stylesheets (`views/css/`)

- `googlecoupon/css.css`
  - **Scope:** Front-office.
  - **Responsibility:** Provides the primary styling for the Google +1 button, the coupon display area, and any associated pop-ups or notifications.
  - **Key CSS class selectors:** Developers should inspect this file to identify specific classes (e.g., `.googlecoupon-button-container`, `.googlecoupon-voucher-display`, `.googlecoupon-modal`) that can be overridden in a custom theme’s `custom.css` or `theme.css` to match the store’s branding.
- `googlecoupon/css/css.css`
  - **Scope:** Front-office.
  - **Responsibility:** This appears to be a duplicate or an alternative stylesheet. It’s important to check if both are loaded or if one is a fallback. It would likely contain similar styling rules as `googlecoupon/css.css`.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**: None explicitly listed, but the `share.tpl` likely serves this purpose.
- **Admin templates (`views/templates/admin/`)**: None.
- **Front-office templates (`views/templates/front/`)**: None explicitly listed, but `share.tpl` is the key front-office template.
  - `googlecoupon/share.tpl`
    - **Scope:** Front-office.
    - **Purpose:** This template is responsible for rendering the Google +1 button and the container where the coupon information will be displayed. It will be injected into the various front-office hooks configured in the module. It likely contains placeholders for the Google+ script and the dynamically generated coupon code.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not appear to create custom SQL tables.
  - Configuration settings are stored in the `ps_configuration` table using keys such as `GC_VOUCHER`, `GC_SHOW_PRICES`, `GC_SHOW_TOTAL`, `GC_SHOW_PRODUCTS`, `GC_SHOW_PRODUCT_URL`, `GC_LASTTAB`, `GC_POSITION`, `GC_NBLIKES`, `GC_BUTTON_STYLE`, `GCSHARE_MODE`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayproductActions` | On product page, typically near the “Add to Cart” button. | Injects the Google +1 button and coupon display in a prominent area. |
| `displayproductFooter` | On product page, at the bottom of the product information block. | Injects the Google +1 button and coupon display after the main product details. |
| `productFooter` | On product page, similar to `displayproductFooter`, often used for additional content. | Alternative placement for the Google +1 button and coupon display. |
| `extraLeft` | On product page, in the left column (if enabled by theme). | Places the module content in the left sidebar. |
| `productActions` | On product page, specifically around the “Add to Cart” and quantity selectors. | Alternative placement for the Google +1 button and coupon display, often very prominent. |
| `displayextraleft` | On product page, in the left column. | Similar to `extraLeft`, for injecting content into the left sidebar. |
| `extraRight` | On product page, in the right column (if enabled by theme). | Places the module content in the right sidebar. |
| `displayextraright` | On product page, in the right column. | Similar to `extraRight`, for injecting content into the right sidebar. |
| `displayHeader` | In the `<head>` section of every page. | Used to include necessary CSS and JavaScript files for the module. |
| `header` | In the `<head>` section of every page (older PrestaShop versions). | Similar to `displayHeader`, for including assets. |

## 5. Official Support & Updates

For official updates, technical support, and to download the latest versions of the “Google product plus button + coupon” module, please log in to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have.
