---
title: "Facebook Fan Coupons - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Facebook Fan Coupons PrestaShop module by MyPresta.eu."
sidebar:
  label: "Facebook Fan Coupons - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Facebook Fan Coupons Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-fan-coupons.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/facebook-fan-coupons/)
>
> ---


# Facebook Fan Coupons

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL). Your server must be able to communicate with Facebook’s API.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the Facebook Fan Coupons module, where you define how the coupons are generated and how the module behaves.

#### General Settings

- **What this setting does:** These settings control the overall behavior of the module, including updates and basic functionality.
- **Effect of changing this setting:**
  - `mypresta_updates`, `update_`, `updatev_`: These are internal settings related to module updates and version checks by MyPresta.eu. You generally do not need to change these.
- **Recommended value:** Leave these as their default values.
- **Merchant scenario / example:** These settings ensure your module is up-to-date and compatible with MyPresta.eu services.

#### Coupon Generation Settings

- **FANCOUPON\_FONTSTYLE**

  - **What this setting does:** Defines the font style used for the generated coupon code displayed to the customer on your Facebook tab. This is purely for visual presentation.
  - **Effect of changing this setting:**
    - *When set to a specific font:* The coupon code will be displayed in that font, making it more visually appealing or matching your brand.
    - *When left default:* A standard, readable font will be used.
  - **Recommended value:** Choose a clear, readable font that matches your brand’s aesthetic.
  - **Merchant scenario / example:** If your brand uses a specific stylish font, you can enter its name here (e.g., “Arial Black”, “Verdana”) to make the coupon look more integrated.
- **FANCOUPON\_VOUCHERCODE**

  - **What this setting does:** This is the *prefix* for the automatically generated voucher codes. Each code will start with this text, followed by random characters.
  - **Effect of changing this setting:**
    - *When set to “FANCOUPON”:* All generated codes will look like “FANCOUPONABCD123”.
    - *When set to “FBPROMO”:* All generated codes will look like “FBPROMOXYZ789”.
  - **Recommended value:** A short, memorable prefix related to Facebook or your promotion (e.g., “FBPROMO”, “FAN2024”, “MYFAN”).
  - **Merchant scenario / example:** Using “FBPROMO” helps you easily identify which orders came from this Facebook campaign in your PrestaShop order history.
- **FANCOUPON\_MODE**

  - **What this setting does:** Determines the type of discount the generated voucher code will provide (e.g., percentage, fixed amount, free shipping).
  - **Effect of changing this setting:**
    - *Percentage discount:* The coupon will reduce the order total by a percentage (e.g., 10% off).
    - *Fixed amount discount:* The coupon will reduce the order total by a fixed monetary value (e.g., $10 off).
    - *Free shipping:* The coupon will make shipping free for the order.
  - **Recommended value:** This depends on your marketing strategy. Percentage discounts are often popular for general promotions.
  - **Merchant scenario / example:** To offer 15% off for new Facebook fans, you would select “Percentage discount” here and then specify “15” in the corresponding value field (which appears after selecting the mode).
- **FANCOUPON\_CHARS**

  - **What this setting does:** Specifies the types of characters (letters, numbers) that will be used in the *random part* of the generated voucher code.
  - **Effect of changing this setting:**
    - *Letters and Numbers:* Codes will be a mix of alphanumeric characters (e.g., “ABC123”).
    - *Numbers only:* Codes will only contain digits (e.g., “123456”).
    - *Letters only:* Codes will only contain letters (e.g., “ABCDEF”).
  - **Recommended value:** “Letters and Numbers” for maximum uniqueness and security.
  - **Merchant scenario / example:** To make codes easier to read, you might choose “Letters only”, but this reduces the number of unique combinations possible for a given length.
- **FANCOUPON\_LENGTH**

  - **What this setting does:** Defines the length of the *random part* of the generated voucher code (excluding the prefix).
  - **Effect of changing this setting:**
    - *Shorter length (e.g., 4):* Codes are quicker to type but less unique (e.g., “FBPROMOABCD”).
    - *Longer length (e.g., 8):* Codes are more secure and unique but take longer to type (e.g., “FBPROMOABCD12345”).
  - **Recommended value:** 6-8 characters for a good balance of uniqueness and usability.
  - **Merchant scenario / example:** If you expect a very high volume of coupon generations, a longer length ensures each code is truly unique and prevents accidental duplicates.
- **FANCOUPON\_VOUCHER\_CAT**

  - **What this setting does:** Allows you to restrict the generated voucher code to apply only to products within specific categories in your store.
  - **Effect of changing this setting:**
    - *When specific categories are selected:* The coupon will only work if the customer has products from those categories in their cart.
    - *When no categories are selected:* The coupon will apply to all products in the store.
  - **Recommended value:** Leave empty if the coupon should apply store-wide. Select categories if you want to promote specific product lines.
  - **Merchant scenario / example:** If you’re running a promotion specifically for your “Summer Collection,” you would select that category here so the coupon only works on those items.
- **PS\_LANG\_DEFAULT**

  - **What this setting does:** This is the default language ID of your PrestaShop store. It’s used internally by the module to ensure coupon descriptions and other language-dependent elements are created correctly.
  - **Effect of changing this setting:** Incorrectly changing this could lead to issues with how coupons are created in your store’s default language.
  - **Recommended value:** Leave as the default value automatically detected by PrestaShop.
  - **Merchant scenario / example:** This ensures that when a coupon is generated, its internal description (e.g., “Facebook Fan Coupon”) is correctly set in your primary store language.

#### Advertising Blocks Settings (Optional)

- **FANCOUPON\_ADV\_POS1**

  - **What this setting does:** Controls the image/banner displayed in the **left column** of your PrestaShop store to promote the Facebook coupon offer.
  - **Effect of changing this setting:**
    - *When an image URL is entered:* The specified image will appear in the left column.
    - *When left empty:* No image will be displayed in the left column.
  - **Recommended value:** An attractive banner image (e.g., 200px wide) that clearly advertises the “Like us on Facebook, get a coupon!” offer.
  - **Merchant scenario / example:** You upload a custom banner image to your server (e.g., `img/cms/fb-coupon-left.jpg`) and enter its full URL here.
- **FANCOUPON\_ADV\_POS2**

  - **What this setting does:** Controls the image/banner displayed in the **right column** of your PrestaShop store to promote the Facebook coupon offer.
  - **Effect of changing this setting:**
    - *When an image URL is entered:* The specified image will appear in the right column.
    - *When left empty:* No image will be displayed in the right column.
  - **Recommended value:** Similar to `FANCOUPON_ADV_POS1`, an attractive banner image (e.g., 200px wide).
  - **Merchant scenario / example:** You might use a different design for the right column banner or simply duplicate the left column one.
- **FANCOUPON\_ADV\_POS3**

  - **What this setting does:** Controls the image/banner displayed in the **footer** of your PrestaShop store to promote the Facebook coupon offer.
  - **Effect of changing this setting:**
    - *When an image URL is entered:* The specified image will appear in the footer.
    - *When left empty:* No image will be displayed in the footer.
  - **Recommended value:** An attractive banner image suitable for the footer area.
  - **Merchant scenario / example:** A wider, shorter banner (e.g., 900px wide, 100px high) that fits well in the footer.
- **FANCOUPON\_ADV\_URL**

  - **What this setting does:** This is the URL that all the advertising banners (`FANCOUPON_ADV_POS1`, `POS2`, `POS3`) will link to when clicked. This should be the direct URL to your Facebook Fan Page tab where the coupon can be generated.
  - **Effect of changing this setting:**
    - *When set to your Facebook tab URL:* Clicking any of the banners will take the customer directly to the coupon generation tab on your Facebook page.
    - *When left empty or incorrect:* The banners will not be clickable or will lead to an incorrect page.
  - **Recommended value:** The exact URL of your Facebook Fan Page tab where the coupon module is embedded.
  - **Merchant scenario / example:** After setting up the Facebook tab, you’ll get a unique URL for it (e.g., `https://www.facebook.com/YOURPAGE/app_1234567890`). Enter that URL here.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | `FANCOUPON_FONTSTYLE` | Default system font | Font style for the displayed coupon code on Facebook. |
| Module Configuration | `FANCOUPON_VOUCHERCODE` | `FANCOUPON` | Prefix for generated voucher codes. Helps identify campaign. |
| Module Configuration | `FANCOUPON_MODE` | Percentage discount | Type of discount (percentage, fixed, free shipping). |
| Module Configuration | `FANCOUPON_CHARS` | Letters and Numbers | Character set for the random part of the code. |
| Module Configuration | `FANCOUPON_LENGTH` | 6-8 characters | Length of the random part of the code. Affects uniqueness. |
| Module Configuration | `FANCOUPON_VOUCHER_CAT` | Empty (all products) | Restricts coupon use to specific product categories. |
| Module Configuration | `FANCOUPON_ADV_POS1` | Empty | URL of banner image for the left column. |
| Module Configuration | `FANCOUPON_ADV_POS2` | Empty | URL of banner image for the right column. |
| Module Configuration | `FANCOUPON_ADV_POS3` | Empty | URL of banner image for the footer. |
| Module Configuration | `FANCOUPON_ADV_URL` | Empty | Destination URL for all advertising banners (your Facebook tab). |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My coupons aren’t working after generation.**
A: Check the following:
1. **PrestaShop Cart Rules:** Go to **Catalog > Discounts > Cart Rules** in your PrestaShop back office. Search for coupons with the prefix you defined (`FANCOUPON_VOUCHERCODE`). Ensure they are active and have not expired. The module creates these automatically, but sometimes manual intervention or a conflict can occur.
2. **Module Configuration:** Double-check your `FANCOUPON_MODE` and `FANCOUPON_VOUCHER_CAT` settings. If you restricted the coupon to a category, ensure the customer is trying to use it on products from that category.
3. **Cache:** Clear your PrestaShop cache (**Advanced Parameters > Performance**) and your browser cache.

**Q: The advertising banners aren’t showing up in my store.**
A:
1. **Module Hooks:** Ensure the module is hooked correctly. In **Modules > Module Manager**, find “Facebook Fan Coupons” and click “Configure”. Check the “Positions” tab (or “Hooks” tab in older versions) to see if it’s assigned to `displayLeftColumn`, `displayRightColumn`, or `displayFooter`. If not, you may need to manually hook it via **Design > Positions** (or **Modules > Positions**).
2. **Image URLs:** Verify that the URLs entered for `FANCOUPON_ADV_POS1`, `POS2`, `POS3` are correct and the images exist at those locations.
3. **Theme Compatibility:** Some custom themes might override standard hook positions. If the banners still don’t appear, you might need a webmaster to check your theme’s template files.

**Q: The Facebook tab isn’t working or showing the coupon generator.**
A: This module provides the backend logic for coupon generation. The actual Facebook tab setup is done *within Facebook’s developer tools* or a third-party app that embeds custom content.
1. **Facebook App Setup:** Ensure you have correctly set up a Facebook App and linked it to your Fan Page, pointing to the module’s URL (which is typically your PrestaShop store’s domain with a specific path, or a dedicated page you’ve set up to host the module’s output). This module provides the *logic* for the coupon, but the *display on Facebook* requires proper Facebook App configuration.
2. **Facebook Page Permissions:** Ensure your Facebook page has the necessary permissions for custom tabs.
3. **Secure (HTTPS) Connection:** Facebook requires all embedded applications to run over HTTPS. Make sure your PrestaShop store is fully secured with an SSL certificate.

**Q: How do I translate the module’s text?**
A: You can translate the module’s phrases through the PrestaShop back office:
1. Go to **International > Translations** (or **Localization > Translations** in older versions).
2. Select “Installed modules translations”.
3. Choose your theme, your language, and then select “Facebook Fan Coupons” from the module list.
4. You can then edit any translatable strings used by the module.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The Facebook Fan Coupons module (`fancoupon`) is a standard PrestaShop module primarily focused on backend logic for coupon generation and basic front-office advertising. It leverages PrestaShop’s `Module` class and `Configuration` class to store settings. The core functionality involves dynamically creating `CartRule` objects (vouchers) based on user interaction on a Facebook tab (which is external to PrestaShop but interacts with the module’s logic). Front-office components are limited to simple image banners hooked into standard display positions.

### 4.2 Controllers (`controllers/`)

This module does **not** contain any dedicated front-office or back-office controllers. All configuration is handled via the `getContent()` method of the main module class. Any interaction for coupon generation would typically be handled by an external Facebook application that points to a URL on the PrestaShop site, which then triggers the module’s logic (likely via a hook or a custom entry point not explicitly defined as a `ModuleFrontController` in the provided inventory, but rather handled by the module’s core logic when called).

### 4.3 Core Classes & Models (`classes/`)

This module does **not** contain any custom classes or models in the `classes/` directory. It directly utilizes PrestaShop’s core `CartRule` and `Configuration` classes.

### 4.4 JavaScript Assets (`views/js/`)

- `fancoupon/lib/voucherengine/script.js`
  - **Scope:** Likely Front-office (intended for the Facebook tab interface).
  - **Responsibility:** This script is expected to handle the client-side logic for the coupon generation process. This would include:
    - Detecting if a user has “liked” the Facebook page (via Facebook’s API).
    - Triggering an AJAX request to the PrestaShop backend (or the module’s entry point) to generate a coupon.
    - Displaying the generated coupon code to the user.
    - Potentially handling UI elements like loading spinners or success/error messages.
- `fancoupon/views/js/voucherengine/script.js`
  - **Scope:** Likely Front-office (intended for the Facebook tab interface).
  - **Responsibility:** This appears to be a duplicate or a version of the script in `lib/`. It would serve the same purpose as described above, handling the interactive elements of the coupon generation on the Facebook tab. Developers should verify which `script.js` is actually loaded and used.

### 4.5 CSS Stylesheets (`views/css/`)

- `fancoupon/lib/voucherengine/ps16.css`
  - **Scope:** Front-office customer styling.
  - **Responsibility:** Provides basic styling for the coupon generation interface, likely within the Facebook tab. The `ps16` in the filename suggests it might contain styles specifically tailored for PrestaShop 1.6’s default theme structure, but it should be generally compatible or easily adaptable.
  - **Key CSS class selectors:** Would typically include styles for buttons, input fields, text display areas for the coupon code, and overall layout of the coupon generator. Developers can inspect the rendered HTML on the Facebook tab to identify specific selectors for overriding.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/advert-*.tpl`)**:
  - `fancoupon/views/templates/advert-footer.tpl`
    - **Hook:** `displayFooter` (or `footer` in older versions).
    - **Output:** Renders an advertising banner/image in the store’s footer, linking to the Facebook Fan Page tab. It uses `FANCOUPON_ADV_POS3` for the image source and `FANCOUPON_ADV_URL` for the link.
  - `fancoupon/views/templates/advert-left.tpl`
    - **Hook:** `displayLeftColumn` (or `leftcolumn` in older versions).
    - **Output:** Renders an advertising banner/image in the store’s left column, linking to the Facebook Fan Page tab. It uses `FANCOUPON_ADV_POS1` for the image source and `FANCOUPON_ADV_URL` for the link.
  - `fancoupon/views/templates/advert-right.tpl`
    - **Hook:** `displayRightColumn` (or `rightcolumn` in older versions).
    - **Output:** Renders an advertising banner/image in the store’s right column, linking to the Facebook Fan Page tab. It uses `FANCOUPON_ADV_POS2` for the image source and `FANCOUPON_ADV_URL` for the link.
- **Admin templates (`views/templates/admin/`)**: None identified.
- **Front-office templates (`views/templates/front/`)**: None identified. The core coupon generation UI is likely rendered dynamically via JavaScript or directly within the `fancoupon.php` logic when called from Facebook.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  - This module does not create custom SQL tables.
  - It stores its configuration settings in PrestaShop’s `ps_configuration` table using keys like `FANCOUPON_FONTSTYLE`, `FANCOUPON_VOUCHERCODE`, etc.
  - It creates entries in `ps_cart_rule` and related tables (`ps_cart_rule_lang`, `ps_cart_rule_product_rule_group`, etc.) for each generated coupon.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayLeftColumn` | Renders content in the left sidebar of the store. | Displays the left column advertising banner. |
| `displayRightColumn` | Renders content in the right sidebar of the store. | Displays the right column advertising banner. |
| `displayFooter` | Renders content in the footer section of the store. | Displays the footer advertising banner. |
| `leftcolumn` | (PrestaShop 1.6.x and older) Renders content in the left sidebar. | Legacy hook for left column advertising banner. |
| `rightcolumn` | (PrestaShop 1.6.x and older) Renders content in the right sidebar. | Legacy hook for right column advertising banner. |
| `footer` | (PrestaShop 1.6.x and older) Renders content in the footer section. | Legacy hook for footer advertising banner. |

## 5. Official Support & Updates

For the latest module updates, technical support, and any inquiries regarding the Facebook Fan Coupons module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our dedicated support team is available to assist merchants and developers with any issues or questions.
