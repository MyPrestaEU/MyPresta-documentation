---
title: "Responsive popup coupons - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Responsive popup coupons PrestaShop module by MyPresta.eu."
sidebar:
  label: "Responsive popup coupons - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Responsive popup coupons Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/responsive-popup-coupons.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/responsive-popup-coupons/)
>
> ---


# Responsive popup coupons

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 1.6.x, 1.5.x, 1.4.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient and usually enabled by default on most hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen where you will set up all the parameters for your popup coupons.

#### General Settings

- **Enable module:**

  - **What this setting does:** This is the master switch to turn the entire popup coupon functionality on or off for your store.
  - **Effect of changing this setting:**
    - *When enabled:* The popup will start appearing on your selected pages according to your other settings.
    - *When disabled:* The popup will not appear anywhere on your store, regardless of other settings.
  - **Recommended value:** YES (when you want to use the module).
  - **Merchant scenario / example:** You’re running a holiday promotion and want to activate the popup for a limited time. You enable it at the start and disable it once the promotion ends.
- **Display on:**

  - **What this setting does:** This allows you to choose on which types of pages the popup will be shown to your customers.
  - **Effect of changing this setting:**
    - *Homepage:* Popup appears only on your store’s main page.
    - *Category pages:* Popup appears when customers browse product categories.
    - *Product pages:* Popup appears when customers view individual product details.
    - *CMS pages:* Popup appears on informational pages like “About Us” or “Contact.”
    - *All pages:* Popup appears on every page of your store.
  - **Recommended value:** Product pages or All pages (depending on your marketing strategy).
  - **Merchant scenario / example:** You want to encourage purchases directly on product pages, so you select “Product pages.” If you want maximum exposure, you might choose “All pages.”
- **Delay (in seconds) before popup appears:**

  - **What this setting does:** Controls how long after a page loads the popup will wait before appearing.
  - **Effect of changing this setting:**
    - *Set to 0:* Popup appears immediately upon page load.
    - *Set to 5:* Popup appears 5 seconds after the page loads.
  - **Recommended value:** 3-5 seconds (allows customers to see content first).
  - **Merchant scenario / example:** You don’t want to overwhelm customers immediately. Setting a 3-second delay gives them a moment to orient themselves before the offer appears.
- **Display popup only once per session:**

  - **What this setting does:** Determines if a customer will see the popup multiple times during a single visit to your store.
  - **Effect of changing this setting:**
    - *When enabled:* Once a customer sees the popup (and potentially closes it), they won’t see it again until they close their browser and start a new session.
    - *When disabled:* The popup could appear every time they visit a page where it’s configured to display.
  - **Recommended value:** YES (to avoid annoying customers).
  - **Merchant scenario / example:** A customer visits several product pages. If this is enabled, they only see the coupon offer once, preventing irritation.
- **Display popup only once per customer (forever):**

  - **What this setting does:** This is a more permanent setting, preventing a logged-in customer from ever seeing the popup again once they’ve seen it once.
  - **Effect of changing this setting:**
    - *When enabled:* The module remembers that a specific customer (via their account) has seen the popup and will not show it to them again, even in future sessions.
    - *When disabled:* The “once per session” rule applies, or if that’s off, they’ll see it repeatedly.
  - **Recommended value:** YES (for a less intrusive experience for loyal customers).
  - **Merchant scenario / example:** You want to give each customer a chance to get the coupon, but not constantly remind them if they’ve already seen or used it.
- **Display popup only for guests (not logged-in customers):**

  - **What this setting does:** Restricts the popup’s visibility to only visitors who are not logged into a customer account.
  - **Effect of changing this setting:**
    - *When enabled:* Only new or returning non-logged-in visitors will see the popup. Logged-in customers will not.
    - *When disabled:* Both guests and logged-in customers will see the popup (subject to other display rules).
  - **Recommended value:** YES (often, you want to convert new visitors, not necessarily offer discounts to existing loyal customers).
  - **Merchant scenario / example:** Your goal is to attract new customers or encourage first-time purchases. You enable this to focus your offer on potential new clients.
- **Display popup only for selected customer groups:**

  - **What this setting does:** Allows you to target specific groups of customers (e.g., “Visitors,” “Customers,” “Guests,” or custom groups you’ve created) with the popup.
  - **Effect of changing this setting:**
    - *When specific groups are selected:* Only customers belonging to those groups will see the popup.
    - *When no groups are selected (or all are selected):* All customers will see the popup (subject to other rules).
  - **Recommended value:** Select “Guests” and “Visitors” if your goal is new customer acquisition.
  - **Merchant scenario / example:** You want to offer a special discount only to your VIP customer group. You would select only that group here.
- **Display popup only for selected countries:**

  - **What this setting does:** Restricts the popup’s appearance based on the customer’s geographical location.
  - **Effect of changing this setting:**
    - *When specific countries are selected:* Only customers from those countries will see the popup.
    - *When no countries are selected (or all are selected):* All customers will see the popup.
  - **Recommended value:** Select specific countries if you have geo-targeted promotions, otherwise leave empty.
  - **Merchant scenario / example:** You’re running a promotion exclusive to customers in France and Germany. You would select only these two countries.
- **Display popup only for selected currencies:**

  - **What this setting does:** Controls popup visibility based on the currency the customer is currently using on your store.
  - **Effect of changing this setting:**
    - *When specific currencies are selected:* Only customers using those currencies will see the popup.
    - *When no currencies are selected (or all are selected):* All customers will see the popup.
  - **Recommended value:** Select specific currencies if your promotion is currency-dependent, otherwise leave empty.
  - **Merchant scenario / example:** You have a special offer for customers paying in USD. You would select only USD here.
- **Display popup only for selected languages:**

  - **What this setting does:** Determines if the popup appears based on the language the customer has selected for your store.
  - **Effect of changing this setting:**
    - *When specific languages are selected:* Only customers viewing your store in those languages will see the popup.
    - *When no languages are selected (or all are selected):* All customers will see the popup.
  - **Recommended value:** Select specific languages if your popup content is only translated for certain languages, otherwise leave empty.
  - **Merchant scenario / example:** Your popup message is only available in English and Spanish. You would select these two languages to ensure customers see a relevant message.

#### Coupon Settings

- **Voucher value:**

  - **What this setting does:** Defines the discount amount or percentage offered by the coupon.
  - **Effect of changing this setting:**
    - *Set to 10:* The coupon will provide a 10 unit discount (e.g., $10, €10).
    - *Set to 15%:* The coupon will provide a 15% discount.
  - **Recommended value:** A compelling discount (e.g., 10%, $5, €10).
  - **Merchant scenario / example:** You want to offer a 10% discount, so you enter “10%” here.
- **Voucher type:**

  - **What this setting does:** Specifies whether the voucher is a fixed amount or a percentage.
  - **Effect of changing this setting:**
    - *Percentage:* The “Voucher value” will be treated as a percentage of the order total.
    - *Amount:* The “Voucher value” will be treated as a fixed monetary deduction.
  - **Recommended value:** Percentage (often more appealing for varying order sizes).
  - **Merchant scenario / example:** You want to give 10% off, so you select “Percentage.” If you want to give a flat $5 off, you select “Amount.”
- **Voucher minimum amount:**

  - **What this setting does:** Sets a minimum order value that a customer must reach to be able to use the coupon.
  - **Effect of changing this setting:**
    - *Set to 50:* The coupon can only be used if the cart total is $50 or more.
    - *Set to 0 (or empty):* No minimum order amount is required.
  - **Recommended value:** A reasonable minimum to protect your margins, or 0 if you want to encourage any purchase.
  - **Merchant scenario / example:** You want to ensure the discount is only applied to orders over $50, so you enter “50.”
- **Voucher expiration (in days):**

  - **What this setting does:** Defines how many days the generated coupon code will be valid from the moment it’s issued.
  - **Effect of changing this setting:**
    - *Set to 7:* The coupon will expire 7 days after the customer receives it.
    - *Set to 0 (or empty):* The coupon will not expire.
  - **Recommended value:** 7-30 days (creates urgency without being too restrictive).
  - **Merchant scenario / example:** You want customers to use the coupon quickly, so you set an expiration of 7 days.
- **Voucher description:**

  - **What this setting does:** Provides a descriptive name for the coupon in your PrestaShop back office (e.g., in the “Cart Rules” section). This is for your internal reference.
  - **Effect of changing this setting:** This text will appear in your PrestaShop admin panel when you view the generated cart rules, helping you identify their origin. It does not appear to the customer.
  - **Recommended value:** “Popup Coupon - [Date]” or “Facebook Like Discount.”
  - **Merchant scenario / example:** You enter “Facebook Like Popup Discount” so you know exactly where these coupons came from when reviewing your cart rules.
- **Voucher free shipping:**

  - **What this setting does:** Determines if the coupon also grants free shipping on the order.
  - **Effect of changing this setting:**
    - *When enabled:* The customer will not be charged for shipping when using this coupon.
    - *When disabled:* Standard shipping costs will apply.
  - **Recommended value:** NO (unless you want to offer free shipping as a strong incentive).
  - **Merchant scenario / example:** You want to offer a very attractive deal, so you enable free shipping along with the discount.
- **Voucher apply to specific products:**

  - **What this setting does:** Allows you to restrict the coupon’s usage to only certain products in your store.
  - **Effect of changing this setting:**
    - *When specific products are selected:* The coupon will only work if those products are in the cart.
    - *When no products are selected:* The coupon applies to all products in the cart.
  - **Recommended value:** Leave empty unless you have a specific product promotion.
  - **Merchant scenario / example:** You’re promoting a new line of shoes. You select only those shoes here, so the coupon only works for them.
- **Voucher apply to specific categories:**

  - **What this setting does:** Allows you to restrict the coupon’s usage to products within specific categories.
  - **Effect of changing this setting:**
    - *When specific categories are selected:* The coupon will only work if products from those categories are in the cart.
    - *When no categories are selected:* The coupon applies to all products.
  - **Recommended value:** Leave empty unless you have a specific category promotion.
  - **Merchant scenario / example:** You want to clear out old stock in your “Summer Collection” category. You select that category here.
- **Voucher apply to specific manufacturers:**

  - **What this setting does:** Allows you to restrict the coupon’s usage to products from specific brands/manufacturers.
  - **Effect of changing this setting:**
    - *When specific manufacturers are selected:* The coupon will only work if products from those manufacturers are in the cart.
    - *When no manufacturers are selected:* The coupon applies to all products.
  - **Recommended value:** Leave empty unless you have a specific brand promotion.
  - **Merchant scenario / example:** You have a partnership with a specific brand and want to offer a discount only on their products.

#### Popup Design & Content

- **Popup width (in pixels):**

  - **What this setting does:** Controls the horizontal size of the popup window.
  - **Effect of changing this setting:** A larger number makes the popup wider, a smaller number makes it narrower.
  - **Recommended value:** 600px - 800px (for good visibility on desktop, responsive design will handle mobile).
  - **Merchant scenario / example:** You want the popup to be prominent but not too wide, so you set it to 700px.
- **Popup background color:**

  - **What this setting does:** Sets the background color of the popup window.
  - **Effect of changing this setting:** Changes the visual appearance of the popup to match your brand or stand out.
  - **Recommended value:** A color that contrasts well with your text and brand (e.g., #FFFFFF for white, #F0F0F0 for light grey).
  - **Merchant scenario / example:** Your brand uses a lot of blue, so you pick a light blue hex code like #E0F2F7.
- **Popup text color:**

  - **What this setting does:** Sets the color of the text displayed within the popup.
  - **Effect of changing this setting:** Ensures readability against your chosen background color.
  - **Recommended value:** A color that provides good contrast (e.g., #000000 for black, #333333 for dark grey).
  - **Merchant scenario / example:** With a light background, you choose a dark text color like #333333 for optimal readability.
- **Popup border color:**

  - **What this setting does:** Sets the color of the border around the popup window.
  - **Effect of changing this setting:** Adds a visual frame to the popup.
  - **Recommended value:** A subtle color that complements your design or a strong color to make it pop (e.g., #CCCCCC for light grey, or your brand accent color).
  - **Merchant scenario / example:** You want a clean look, so you choose a subtle grey border #DDDDDD.
- **Popup border width (in pixels):**

  - **What this setting does:** Controls the thickness of the popup’s border.
  - **Effect of changing this setting:** A higher number makes the border thicker.
  - **Recommended value:** 1-3px.
  - **Merchant scenario / example:** You want a thin, elegant border, so you set it to 1px.
- **Popup border radius (in pixels):**

  - **What this setting does:** Controls the roundness of the popup’s corners.
  - **Effect of changing this setting:**
    - *Set to 0:* Sharp, square corners.
    - *Set to 10:* Slightly rounded corners.
    - *Set to 50 (or higher):* Very rounded, pill-like corners.
  - **Recommended value:** 5-10px (for a modern, soft look).
  - **Merchant scenario / example:** You prefer a softer aesthetic, so you set the border radius to 8px.
- **Popup shadow:**

  - **What this setting does:** Adds a shadow effect around the popup, making it appear to float above the page.
  - **Effect of changing this setting:**
    - *When enabled:* The popup will have a subtle shadow, giving it depth.
    - *When disabled:* The popup will have no shadow.
  - **Recommended value:** YES (adds a professional, modern touch).
  - **Merchant scenario / example:** You want the popup to visually stand out from the background, so you enable the shadow.
- **Popup close button color:**

  - **What this setting does:** Sets the color of the ‘X’ button that customers use to close the popup.
  - **Effect of changing this setting:** Ensures the close button is visible and matches your design.
  - **Recommended value:** A contrasting color for visibility (e.g., #000000, #FF0000).
  - **Merchant scenario / example:** You want the close button to be clearly visible, so you set it to black #000000.
- **Popup content (HTML allowed):**

  - **What this setting does:** This is where you enter the main message and content for your popup. You can use HTML to format text, add images, and include your social media buttons.
  - **Effect of changing this setting:** This text and HTML will be displayed inside the popup.
  - **Recommended value:** Clear, concise message with a strong call to action. Include your Facebook Like button code or similar social media widget.
  - **Merchant scenario / example:** You might enter: `<p>Like us on Facebook and get <strong>10% OFF</strong> your next order!</p><div class="fb-like" data-href="YOUR_FACEBOOK_PAGE_URL" data-layout="button_count" data-action="like" data-size="large" data-show-faces="false" data-share="false"></div>` (Remember to replace `YOUR_FACEBOOK_PAGE_URL`).
- **Popup coupon message (HTML allowed):**

  - **What this setting does:** This is the message displayed *after* the customer performs the required action (e.g., likes your page) and receives their coupon code.
  - **Effect of changing this setting:** This message will appear in the popup, typically above the generated coupon code.
  - **Recommended value:** A thank-you message and instructions on how to use the coupon.
  - **Merchant scenario / example:** You might enter: `<p>Thank you for liking us! Here is your exclusive discount code:</p><p>Use code <strong>{coupon_code}</strong> at checkout.</p>` (The `{coupon_code}` placeholder will be automatically replaced).

#### Advanced Settings

- **Custom CSS code:**

  - **What this setting does:** Allows you to add your own custom CSS rules to further style the popup or override default styles.
  - **Effect of changing this setting:** Any CSS you enter here will be applied to the popup, giving you fine-grained control over its appearance.
  - **Recommended value:** Leave empty unless you have specific styling needs.
  - **Merchant scenario / example:** You want to change the font size of the coupon code. You might add: `.coupon-code { font-size: 24px !important; }`
- **Custom JavaScript code:**

  - **What this setting does:** Allows you to add your own custom JavaScript code to interact with the popup or integrate with other services.
  - **Effect of changing this setting:** Any JavaScript you enter here will be executed when the popup is displayed or interacted with.
  - **Recommended value:** Leave empty unless you have specific scripting needs (e.g., Google Analytics event tracking).
  - **Merchant scenario / example:** You want to send an event to Google Analytics when the popup is displayed. You might add: `ga('send', 'event', 'Popup', 'Displayed', 'Coupon Offer');`

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Enable module | YES | Master switch for popup functionality. |
|  | Display on | Product pages / All pages | Select where popup appears (Homepage, Category, Product, CMS, All). |
|  | Delay (in seconds) before popup appears | 3-5 seconds | Time before popup shows after page load. |
|  | Display popup only once per session | YES | Prevents popup from showing multiple times in one browser session. |
|  | Display popup only once per customer (forever) | YES | Prevents logged-in customers from seeing popup again. |
|  | Display popup only for guests | YES | Targets non-logged-in visitors. |
|  | Display popup only for selected customer groups | Guests, Visitors | Restricts popup to specific customer groups. |
|  | Display popup only for selected countries | Leave empty | Restricts popup to specific countries. |
|  | Display popup only for selected currencies | Leave empty | Restricts popup to specific currencies. |
|  | Display popup only for selected languages | Leave empty | Restricts popup to specific languages. |
|  | Voucher value | e.g., 10% | The discount amount or percentage. |
|  | Voucher type | Percentage / Amount | Defines if voucher is % or fixed amount. |
|  | Voucher minimum amount | 0 (or reasonable value) | Minimum order value for coupon use. |
|  | Voucher expiration (in days) | 7-30 days | Validity period of the generated coupon. |
|  | Voucher description | “Facebook Like Popup Discount” | Internal name for the coupon in BO. |
|  | Voucher free shipping | NO | Grants free shipping with the coupon. |
|  | Voucher apply to specific products | Leave empty | Restricts coupon to specific products. |
|  | Voucher apply to specific categories | Leave empty | Restricts coupon to specific categories. |
|  | Voucher apply to specific manufacturers | Leave empty | Restricts coupon to specific manufacturers. |
|  | Popup width (in pixels) | 600px - 800px | Horizontal size of the popup. |
|  | Popup background color | #FFFFFF (white) | Background color of the popup. |
|  | Popup text color | #000000 (black) | Text color inside the popup. |
|  | Popup border color | #DDDDDD (light grey) | Color of the popup border. |
|  | Popup border width (in pixels) | 1-3px | Thickness of the popup border. |
|  | Popup border radius (in pixels) | 5-10px | Roundness of popup corners. |
|  | Popup shadow | YES | Adds a shadow effect to the popup. |
|  | Popup close button color | #000000 (black) | Color of the ‘X’ close button. |
|  | Popup content (HTML allowed) | Engaging message + Social widget | Main content displayed in the popup. |
|  | Popup coupon message (HTML allowed) | Thank you message + {coupon\_code} | Message displayed after coupon is generated. |
|  | Custom CSS code | Leave empty | Add custom CSS styles. |
|  | Custom JavaScript code | Leave empty | Add custom JavaScript. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The popup isn’t appearing on my store. What should I check first?**
A1:

- **Is the module enabled?** Go to **Modules > Module Manager** and ensure “Responsive popup coupons” is installed and enabled.
- **Check “Enable module” setting:** In the module’s configuration, ensure the “Enable module” switch is set to YES.
- **Verify “Display on” settings:** Make sure you’ve selected the correct page types (e.g., Homepage, Product pages) where you expect the popup to appear.
- **Clear your cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Browser cache might also need clearing (Ctrl+F5 or Cmd+Shift+R).
- **Check for conflicts:** Temporarily disable other modules that might interact with popups or page content to rule out conflicts.

**Q2: The popup appears, but the Facebook Like button (or other social widget) isn’t working or showing correctly.**
A2:

- **Incorrect HTML:** Double-check the HTML code you’ve entered in the “Popup content” field. Even a small typo can break it. Ensure your Facebook page URL is correct.
- **Facebook SDK:** For Facebook Like buttons to work, the Facebook JavaScript SDK needs to be loaded. PrestaShop themes often include this, but if not, you might need to add it via custom code or ensure your theme supports it.
- **Ad Blockers:** Some ad blockers might prevent social widgets from loading. Test in an incognito window without extensions.

**Q3: The coupon code is generated, but it’s not working at checkout.**
A3:

- **Check coupon settings:** Review all “Voucher” settings in the module configuration:
  - **Minimum amount:** Is the customer’s cart value above the “Voucher minimum amount”?
  - **Expiration:** Has the “Voucher expiration” date passed?
  - **Specific products/categories/manufacturers:** Does the customer’s cart contain the required items if these settings are used?
  - **Customer groups/countries/currencies/languages:** Does the customer meet the criteria set for these restrictions?
- **PrestaShop Cart Rules:** The module creates a “Cart Rule” in PrestaShop. Go to **Catalog > Discounts > Cart Rules** (or **Price Rules > Cart Rules** in older versions) and search for the coupon code. Check its details to see if any restrictions were applied incorrectly.

**Q4: The popup’s design doesn’t match my store’s theme perfectly.**
A4:

- **Use module’s design settings:** Adjust “Popup background color,” “Popup text color,” “Popup border color,” “Popup border width,” and “Popup border radius” to better match your theme.
- **Custom CSS:** For more advanced styling, use the “Custom CSS code” field in the module configuration. You can inspect the popup elements using your browser’s developer tools (F12) to find the correct CSS selectors to target.
- **Theme overrides:** If you’re comfortable with coding, you can also override the module’s CSS in your theme’s `custom.css` or `theme.css` file.

**Q5: How do I translate the popup content into multiple languages?**
A5:

- The “Popup content” and “Popup coupon message” fields are typically designed to be entered once. For multi-language support, you would need to use PrestaShop’s translation system.
- Go to **International > Translations**. Select “Installed modules translations,” choose your theme, and then select “Responsive popup coupons.” You should find the text fields for translation there.
- If the fields are not directly translatable via the standard PrestaShop interface, you might need to create separate popups for each language (if the module supports multiple instances) or use a custom solution involving Smarty variables and conditional logic within the HTML content, which requires developer assistance.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview of the “Responsive popup coupons” module for developers and webmasters.

### 4.1 Architecture Overview

The “Responsive popup coupons” module (`popcoupon`) is a standard PrestaShop module primarily implemented within its main PHP file, `ajax_popcoupon.php`. It leverages PrestaShop’s hook system for front-office display and `Configuration` class for settings storage. The module’s core functionality involves displaying a popup, handling user interaction (e.g., social media action), and dynamically generating PrestaShop `CartRule` (voucher) codes. It uses client-side JavaScript for popup display logic and styling, and a minimal template for rendering the popup structure.

### 4.2 Controllers (`controllers/`)

This module does not contain any dedicated Front-Office or Back-Office Admin Controllers in separate files. All back-office configuration logic is handled within the `getContent()` method of the main module class. Front-office display is managed via hooks and client-side JavaScript.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom `ObjectModel` classes or other core PHP classes in a `classes/` directory. All logic is contained within the main module file `ajax_popcoupon.php`. The module directly interacts with PrestaShop’s `Configuration` class for settings and `CartRule` class for voucher generation.

### 4.4 JavaScript Assets (`views/js/`)

The module includes several JavaScript files:

- **`popcoupon/jscolor/jscolor.js`**

  - **Scope:** Back-office.
  - **Purpose:** This is a third-party JavaScript library for a color picker. It’s used in the module’s back-office configuration form to allow merchants to easily select colors for the popup’s background, text, border, and close button. It binds to input fields with specific classes to provide a visual color selection interface.
- **`popcoupon/lib/voucherengine/script.js`**

  - **Scope:** Front-office.
  - **Purpose:** This is the primary JavaScript file responsible for the front-office popup functionality.
    - **Event Listeners:** It listens for page load events to trigger the popup after the configured delay. It also handles events related to closing the popup (e.g., clicking the ‘X’ button or outside the popup).
    - **DOM Manipulation:** It dynamically injects the popup HTML structure into the page, manages its visibility (show/hide), and updates its content (e.g., displaying the coupon code after a social action).
    - **AJAX Calls:** It likely makes AJAX calls to the module’s `ajax_popcoupon.php` (or a similar entry point) to:
      1. Check if the popup should be displayed for the current user/session.
      2. Generate a unique coupon code after the user completes the required action (e.g., Facebook Like).
      3. Store user/session data (e.g., a cookie) to prevent repeated popup display based on configuration settings (“once per session,” “once per customer”).
    - **Third-party SDKs:** If the “Popup content” includes a Facebook Like button, this script might interact with the Facebook JavaScript SDK (if loaded by the theme) to detect when the ‘like’ action is completed.
- **`popcoupon/trusted.js`**

  - **Scope:** Front-office.
  - **Purpose:** This file’s exact purpose is not explicitly defined in the provided information, but based on common module practices, it could be:
    - A small utility script for tracking or analytics.
    - A script related to trust badges or security features.
    - A fallback or supplementary script for the main `script.js`.
    - It might contain logic related to cookie handling or local storage for the “display once” features.

### 4.5 CSS Stylesheets (`views/css/`)

The module includes the following CSS files:

- **`popcoupon/css.css`**

  - **Scope:** Front-office.
  - **Purpose:** This is the main stylesheet for the popup window.
    - **UI Components:** Styles the overall popup container, its overlay, the close button, and potentially the content area.
    - **Key Selectors:** Developers can expect selectors like `.popcoupon-overlay`, `.popcoupon-modal`, `.popcoupon-close`, etc. These can be overridden in a custom theme’s `custom.css` or by using the module’s “Custom CSS code” setting.
    - **Responsiveness:** Contains media queries or flexible box/grid properties to ensure the popup adapts well to different screen sizes.
- **`popcoupon/lib/voucherengine/ps16.css`**

  - **Scope:** Front-office.
  - **Purpose:** This stylesheet likely contains specific styling adjustments or overrides tailored for PrestaShop 1.6 themes. It might address layout differences or default element styles prevalent in PS 1.6 to ensure the popup looks consistent across different PrestaShop versions. For PS 1.7/8, some of these styles might be overridden by `css.css` or the theme itself.

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses a single Smarty template:

- **`popcoupon/views/header.tpl`**
  - **Hook:** `displayHeader` (or similar, depending on how it’s registered in `ajax_popcoupon.php`).
  - **Purpose:** This template is likely responsible for injecting the necessary HTML structure for the popup (which is initially hidden) and potentially the JavaScript and CSS assets into the `<head>` or `<body>` of the front-office page. It might contain:
    - The basic HTML skeleton for the popup modal and its overlay.
    - Conditional logic to include the JavaScript and CSS files only when the module is enabled.
    - Placeholders for dynamic content that will be filled by JavaScript.

### 4.7 Database Schema & Hooks Map

- **Database Tables:**

  - This module does not create custom SQL tables.
  - It stores its configuration settings in PrestaShop’s `ps_configuration` table. Configuration keys will typically start with `POPCOUPON_` (e.g., `POPCOUPON_ENABLED`, `POPCOUPON_DELAY`, `POPCOUPON_VOUCHER_VALUE`).
  - It leverages PrestaShop’s `ps_cart_rule` and `ps_cart_rule_lang` tables for generating and managing the unique coupon codes.
  - For “display once per customer/session” features, it likely uses cookies or `ps_customer` specific configuration entries.
- **Registered Hooks Table:**

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Injecting CSS, JavaScript, and the initial (hidden) HTML structure for the popup. |
| `displayFooter` | At the end of the `<body>` section of every front-office page. | Alternative hook for injecting JS/CSS or the popup HTML, often preferred for performance. |
| `displayLeftColumn` | In the left column of the front-office. | Less common for popups, but could be used to trigger or display a smaller popup element. |
| `displayRightColumn` | In the right column of the front-office. | Similar to `displayLeftColumn`. |
| `displayProductButtons` | On the product page, near the add-to-cart button. | Could be used to trigger a product-specific popup or display a small coupon offer. |
| `actionFrontControllerSetMedia` | When a front controller sets its media (JS/CSS). | A more robust way to register JS/CSS assets, ensuring they are loaded correctly. |
| `actionValidateOrder` | After an order has been successfully validated. | (Less likely for this module, but could be used for post-purchase actions related to coupons). |

*Note: The exact hooks used are determined by the `hook` methods implemented in `ajax_popcoupon.php` (e.g., `hookDisplayHeader()`). The module description mentions “Header, Columns, Product, or Footer,” indicating it registers for at least one of these display hooks.*

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Responsive popup coupons” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist merchants and developers with any issues or questions regarding the module’s functionality and integration.
