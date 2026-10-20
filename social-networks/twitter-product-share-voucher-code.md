---
title: "Twitter product share + voucher code - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Twitter product share + voucher code PrestaShop module by MyPresta.eu."
sidebar:
  label: "Twitter product share + voucher code - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Twitter product share + voucher code Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/twitter-product-share-voucher-code.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/twitter-product-share-voucher-code/)
>
> ---


# Twitter product share + voucher code

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop and are usually enabled by default on most hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the “Twitter product share + voucher code” module, accessible after installation by clicking the “Configure” button. Here, you will define how the sharing button behaves and how the voucher codes are generated.

#### **General Settings**

- **Enable Module:**

  - **What this setting does:** This is the master switch to turn the entire module on or off.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The Twitter share button will appear on your product pages (based on your hook selection), and the voucher code generation system will be active.
    - *When disabled (NO):* The Twitter share button will not appear, and no voucher codes will be generated for shares.
  - **Recommended value:** YES (to activate the module’s functionality).
  - **Merchant scenario / example:** If you’re setting up the module for the first time or performing maintenance, you might disable it temporarily. Otherwise, keep it enabled to benefit from social sharing.
- **Hook to display the button:**

  - **What this setting does:** Determines where the Twitter share button will be visually placed on your product pages.
  - **Effect of changing this setting:**
    - *Options (examples):* `displayProductButtons`, `displayRightColumnProduct`, `displayFooterProduct`, `displayProductExtraContent`.
    - *When set to `displayProductButtons` (common):* The button will likely appear near the “Add to Cart” button or product quantity selector.
    - *When set to `displayRightColumnProduct`:* The button will appear in the right column of your product page (if your theme has one).
    - *When set to `displayFooterProduct`:* The button will appear in the footer section of the product page.
  - **Recommended value:** `displayProductButtons` or `displayProductExtraContent` for maximum visibility and engagement, as these are typically close to the main product information.
  - **Merchant scenario / example:** You might test different hooks to see which placement generates the most shares on your specific theme. A prominent location is usually best.
- **Number of shares required for a voucher:**

  - **What this setting does:** Defines how many unique product shares a customer must perform before they receive a discount voucher.
  - **Effect of changing this setting:**
    - *When set to 1:* A customer receives a voucher immediately after their first share.
    - *When set to 3:* A customer must share three different products (or the same product three times, depending on internal logic) before a voucher is issued.
  - **Recommended value:** 1 (to encourage immediate action and reward) or 2 (to encourage slightly more engagement without being too demanding).
  - **Merchant scenario / example:** If you want to make it easy for customers to get a discount, set it to 1. If you want to encourage more extensive sharing, set it higher, but be aware that a higher number might reduce participation.

#### **Voucher Code Settings**

- **Voucher code prefix:**

  - **What this setting does:** A custom string of characters that will appear at the beginning of every generated voucher code.
  - **Effect of changing this setting:**
    - *When set to `TWITTER-`:* A voucher code might look like `TWITTER-ABCDE123`.
    - *When left empty:* The voucher code will be purely random characters.
  - **Recommended value:** `TWITTER-` or `SHARE-` to easily identify the source of the voucher.
  - **Merchant scenario / example:** Using a prefix helps you track which marketing campaigns are generating specific vouchers in your PrestaShop sales reports.
- **Voucher code value (percentage):**

  - **What this setting does:** The percentage discount applied by the generated voucher code.
  - **Effect of changing this setting:**
    - *When set to 10:* The voucher will give a 10% discount on the customer’s order.
    - *When set to 5:* The voucher will give a 5% discount.
  - **Recommended value:** 5-15% (depending on your profit margins and desired incentive level).
  - **Merchant scenario / example:** A 10% discount is often a good balance between enticing customers and maintaining profitability.
- **Voucher code validity (days):**

  - **What this setting does:** How many days the generated voucher code will be valid from the moment it’s issued.
  - **Effect of changing this setting:**
    - *When set to 7:* The voucher will expire 7 days after the customer receives it.
    - *When set to 30:* The voucher will be valid for a month.
  - **Recommended value:** 7-14 days (to create a sense of urgency without being too restrictive).
  - **Merchant scenario / example:** A shorter validity period encourages customers to make a purchase sooner rather than later, preventing them from forgetting about the voucher.
- **Minimum amount for voucher to be valid:**

  - **What this setting does:** The minimum total order amount (before shipping) required for the customer to be able to use the discount voucher.
  - **Effect of changing this setting:**
    - *When set to 50:* The voucher can only be used if the customer’s cart total is €50 or more.
    - *When set to 0 (or empty):* The voucher can be used on any order amount.
  - **Recommended value:** A reasonable amount that encourages a slightly larger purchase, or 0 if you want to allow it on any order.
  - **Merchant scenario / example:** If your average order value is €40, setting a minimum of €50 might encourage customers to add another item to their cart to reach the threshold and use the discount.
- **Voucher code description:**

  - **What this setting does:** A short text description that will be associated with the voucher code in your PrestaShop back office (and potentially visible to the customer in their account if they check their vouchers).
  - **Effect of changing this setting:**
    - *When set to “Twitter Share Discount”:* This text will appear in the voucher details.
  - **Recommended value:** “Discount for Twitter Share” or “Thank you for sharing on Twitter!”
  - **Merchant scenario / example:** This helps you and your customers understand the origin of the voucher.
- **Voucher code name:**

  - **What this setting does:** The internal name for the voucher rule in PrestaShop. This is primarily for your internal organization.
  - **Effect of changing this setting:**
    - *When set to “Twitter Share Coupon”:* This name will appear in your PrestaShop “Cart Rules” section.
  - **Recommended value:** “Twitter Share Coupon” or “Social Share Discount”.
  - **Merchant scenario / example:** A clear name makes it easy to find and manage these automatically generated vouchers within your PrestaShop admin.

#### **Twitter Share Text Settings**

- **Default share text:**
  - **What this setting does:** The default text that will be pre-filled in the Twitter sharing pop-up when a customer clicks the share button. This text will be combined with the product name and link.
  - **Effect of changing this setting:**
    - *When set to “Check out this awesome product!”:* The tweet might look like “Check out this awesome product! [Product Name] [Product Link]”.
  - **Recommended value:** Something engaging like “Check out this amazing product from [Your Store Name]!” or “I just found this great product!”
  - **Merchant scenario / example:** A compelling default text encourages more clicks and engagement from the customer’s followers.

#### **Save Button**

- **Save:**
  - **What this button does:** Applies all the changes you’ve made on this configuration page.
  - **Effect of clicking this button:** Your settings are saved to the database, and the module’s behavior will update immediately on your front office.
  - **Recommended action:** Always click “Save” after making any changes.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable Module | YES | Turns the module on/off. |
|  | Hook to display the button | `displayProductButtons` | Controls where the share button appears on product pages. |
|  | Number of shares required for a voucher | 1 | How many shares before a customer gets a voucher. |
|  | Voucher code prefix | `TWITTER-` | Adds a custom prefix to generated voucher codes. |
|  | Voucher code value (percentage) | 10 | The discount percentage of the voucher. |
|  | Voucher code validity (days) | 7-14 | How long the voucher is valid after generation. |
|  | Minimum amount for voucher to be valid | 0 (or reasonable amount) | Minimum cart total required to use the voucher. |
|  | Voucher code description | “Discount for Twitter Share” | Internal description for the voucher. |
|  | Voucher code name | “Twitter Share Coupon” | Internal name for the voucher rule. |
|  | Default share text | “Check out this amazing product!” | Pre-filled text for the Twitter share pop-up. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The Twitter share button isn’t showing up on my product pages.**

- **A:** First, ensure the module is **enabled** in its configuration. Second, check the **“Hook to display the button”** setting. Your theme might not render the chosen hook in a visible location, or the hook might not exist. Try switching to a different common hook like `displayProductButtons` or `displayProductExtraContent`. If it still doesn’t appear, your theme might require custom integration for certain hooks, or there might be a conflict.
- **Pro Tip:** Clear your PrestaShop cache (Advanced Parameters > Performance) after making any changes to module settings or theme files.

**Q2: Customers are sharing, but they’re not receiving voucher codes.**

- **A:**
  1. **Check “Number of shares required for a voucher”:** Is it set to 1? If it’s higher, customers need to share more times before getting a voucher.
  2. **Verify Voucher Settings:** Ensure “Voucher code value (percentage)” is set to a number greater than 0, and “Voucher code validity (days)” is also set.
  3. **PrestaShop Cart Rules:** Check your PrestaShop Back Office under **Catalog > Discounts > Cart Rules**. You should see automatically generated vouchers with the name you specified (e.g., “Twitter Share Coupon”). If no new rules are appearing, there might be an issue with the voucher generation logic.
- **Pro Tip:** Test the process yourself. Share a product from your store while logged in as a customer and see if a voucher is generated.

**Q3: The Twitter share pop-up looks strange or doesn’t work correctly.**

- **A:** This is often due to JavaScript conflicts with other modules or your theme.
  1. **Check Browser Console:** Open your browser’s developer tools (usually F12) and look for errors in the “Console” tab when you click the share button.
  2. **Module Conflicts:** Temporarily disable other modules that add JavaScript to product pages (especially social sharing or pop-up modules) to see if the issue resolves.
- **Pro Tip:** Ensure your PrestaShop installation and theme are up-to-date. Outdated components can sometimes cause unexpected conflicts.

**Q4: Can I customize the appearance of the share button?**

- **A:** The module uses its own CSS (`twittercoupon/css.css` and `twittercoupon/css/css.css`). You can override these styles in your theme’s custom CSS file. Inspect the button using your browser’s developer tools to identify its CSS classes and then add your custom styles to your theme’s `custom.css` or equivalent file.
- **Pro Tip:** Avoid directly editing the module’s CSS files, as your changes will be lost during module updates. Always use your theme’s custom CSS capabilities.

**Q5: How does the module prevent abuse (e.g., someone sharing repeatedly to get multiple vouchers)?**

- **A:** The module typically tracks shares per customer (often by IP address or customer ID if logged in) to prevent a single user from generating unlimited vouchers. The “Number of shares required for a voucher” setting also helps manage this. For more advanced fraud prevention, you might need additional PrestaShop security modules.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Twitter product share + voucher code” module (`twittercoupon`) is a standard PrestaShop module primarily implemented within its main PHP file, `ajax_twittercoupon.php`. It leverages PrestaShop’s hook system for front-office display and `Configuration` class for settings storage. The module dynamically generates `CartRule` objects (vouchers) based on user actions. Its front-office functionality relies on JavaScript to interact with the Twitter API and an AJAX endpoint within the module to process shares and issue vouchers.

### 4.2 Controllers (`controllers/`)

This module does not utilize dedicated front-office or back-office controllers in the `controllers/` directory. All front-office AJAX requests and back-office configuration handling are managed directly within the main module file, `ajax_twittercoupon.php`, specifically through its `getContent()` method for configuration and a custom AJAX dispatch for share processing.

### 4.3 Core Classes & Models (`classes/`)

This module does not define custom classes or extend `ObjectModel` in a dedicated `classes/` directory. The core logic for voucher generation directly interacts with PrestaShop’s `CartRule` and `Configuration` classes.

### 4.4 JavaScript Assets (`views/js/`)

The module includes JavaScript files to handle front-office interactions.

- `twittercoupon/lib/voucherengine/script.js`
  - **Scope:** Front-office.
  - **Responsibility:** This appears to be the primary script responsible for the client-side logic of the module. It likely handles:
    - Binding click events to the Twitter share button.
    - Opening the Twitter sharing pop-up (using Twitter’s Web Intent API).
    - Detecting successful shares (possibly via callbacks or polling).
    - Making AJAX calls to the module’s backend to register the share and request a voucher.
    - Displaying the voucher code to the user upon successful generation.
    - May include logic to prevent multiple shares from the same user within a short period or to track share counts.
- `twittercoupon/trusted.js`
  - **Scope:** Front-office.
  - **Responsibility:** The name “trusted.js” suggests it might be related to security, tracking, or ensuring the integrity of the sharing process. It could potentially handle:
    - Client-side validation before initiating a share.
    - Tracking user interactions for anti-fraud measures.
    - Integration with other tracking scripts or analytics.

### 4.5 CSS Stylesheets (`views/css/`)

The module provides CSS files for styling the front-office elements.

- `twittercoupon/css.css`
  - **Scope:** Front-office customer styling.
  - **Responsibility:** Contains the main styles for the Twitter share button, any associated pop-ups, or messages displayed to the customer.
  - **Key CSS class selectors:** Developers should inspect the rendered HTML to identify specific classes (e.g., `.twitter-share-button`, `.twitter-coupon-message`) to override in their theme’s `custom.css`.
- `twittercoupon/css/css.css`
  - **Scope:** Front-office customer styling.
  - **Responsibility:** This file appears to be a duplicate or an alternative path for the main CSS. It’s common for modules to have redundant paths or for one to be a fallback. Developers should check which one is actually loaded in the browser.
  - **Key CSS class selectors:** Same as above.

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses Smarty templates for rendering its front-office content.

- **Hook templates (`views/templates/hook/`)**:
  - `twittercoupon/share.tpl`
    - **Hook:** This template is rendered in the hook chosen in the module’s configuration (e.g., `displayProductButtons`, `displayRightColumnProduct`, `displayFooterProduct`).
    - **Purpose:** It outputs the HTML for the “Share on Twitter” button and potentially a placeholder for the voucher code message or a modal trigger. It will likely include variables for the product name, product URL, and the default share text.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module primarily stores its configuration settings in PrestaShop’s `ps_configuration` table.
    - `PS_TWITTERCOUPON_ENABLED` (boolean)
    - `PS_TWITTERCOUPON_HOOK` (string)
    - `PS_TWITTERCOUPON_SHARES_REQUIRED` (int)
    - `PS_TWITTERCOUPON_PREFIX` (string)
    - `PS_TWITTERCOUPON_VALUE` (float)
    - `PS_TWITTERCOUPON_VALIDITY` (int)
    - `PS_TWITTERCOUPON_MIN_AMOUNT` (float)
    - `PS_TWITTERCOUPON_DESCRIPTION` (string)
    - `PS_TWITTERCOUPON_NAME` (string)
    - `PS_TWITTERCOUPON_DEFAULT_TEXT` (string)
  - It also likely uses a custom table (e.g., `ps_twittercoupon_shares` or similar) to track individual customer shares (by `id_customer` or `ip_address`, `id_product`) and prevent abuse, although no explicit SQL file was listed, this logic would be handled in the main module’s `install()` method. This table would track:
    - `id_customer` (if logged in)
    - `ip_address`
    - `id_product`
    - `share_date`
    - `voucher_issued` (boolean)
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | To load module’s CSS and JavaScript assets (`twittercoupon/css.css`, `twittercoupon/lib/voucherengine/script.js`, `twittercoupon/trusted.js`). |
| `displayProductButtons` | On the product page, typically near the add-to-cart button. | To display the Twitter share button (`share.tpl`). |
| `displayRightColumnProduct` | On the product page, in the right column. | Alternative hook to display the Twitter share button (`share.tpl`). |
| `displayFooterProduct` | On the product page, in the footer area. | Alternative hook to display the Twitter share button (`share.tpl`). |
| `displayProductExtraContent` | On the product page, often below the main product description. | Alternative hook to display the Twitter share button (`share.tpl`). |
| `actionFrontControllerSetMedia` | Before a front controller renders its content, allowing modules to add assets. | To load module’s CSS and JavaScript assets conditionally based on the page. |
| (Internal AJAX Call) | Triggered by JavaScript on share event. | To process the share, update share count, and generate a `CartRule` (voucher) if conditions are met. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and dedicated technical support for the “Twitter product share + voucher code” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is committed to providing timely assistance and ensuring the optimal performance of your module.
