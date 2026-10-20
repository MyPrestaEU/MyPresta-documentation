---
title: "Facebook product share + discount code - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Facebook product share + discount code PrestaShop module by MyPresta.eu."
sidebar:
  label: "Facebook product share + discount code"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Facebook product share + discount code Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-product-share-discount-code.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/facebook-product-share-discount-code/)
>
> ---


# Facebook product share + discount code

## 1. Requirements & Compatibility
-   **Supported PrestaShop Versions**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x
-   **PHP Compatibility**: PHP 5.6 - 8.5
-   **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop and are usually available on most hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)
After installation, navigate to **Modules > Module Manager** and click "Configure" next to "Facebook product share + discount code". This screen allows you to control the core functionality and appearance of the module.

#### **General Settings**

-   **Enable / Disable Module:**
    -   **What this setting does:** This is the master switch for the entire module.
    -   **Effect of changing this setting:**
        -   *When enabled:* The Facebook share button will appear on product pages, and the discount code functionality will be active.
        -   *When disabled:* The module will be completely inactive. The share button will not appear, and no discount codes will be generated.
    -   **Recommended value:** YES (to activate the module's features).
    -   **Merchant scenario / example:** If you're setting up the module for the first time or performing maintenance, you might disable it temporarily. Once ready, enable it to start generating shares and discounts.

-   **Facebook App ID:**
    -   **What this setting does:** This field requires your unique Facebook Application ID. This ID is crucial for Facebook to correctly identify your website and track shares. You need to create a Facebook App on the Facebook Developers platform (developers.facebook.com) to obtain this ID.
    -   **Effect of changing this setting:**
        -   *When correctly entered:* The module will communicate properly with Facebook, allowing shares to be tracked and the discount mechanism to function.
        -   *When incorrect or empty:* The Facebook share functionality may not work, or shares might not be tracked, preventing discount codes from being issued.
    -   **Recommended value:** Your valid Facebook App ID (e.g., `123456789012345`).
    -   **Merchant scenario / example:** You've created a Facebook App for your store. Copy the App ID from your Facebook Developer dashboard and paste it here. This is a one-time setup.

-   **Discount Type:**
    -   **What this setting does:** Determines the type of discount customers receive after sharing.
    -   **Effect of changing this setting:**
        -   *When set to "Percentage":* The discount code will offer a percentage off the order total (e.g., 10% off).
        -   *When set to "Amount":* The discount code will offer a fixed monetary value off the order total (e.g., $5 off).
    -   **Recommended value:** "Percentage" or "Amount" based on your marketing strategy.
    -   **Merchant scenario / example:** If you want to encourage larger orders, a percentage discount might be more appealing. For smaller, frequent purchases, a fixed amount might be more effective.

-   **Discount Value:**
    -   **What this setting does:** Specifies the actual value of the discount.
    -   **Effect of changing this setting:**
        -   *If "Discount Type" is Percentage:* Enter the percentage value (e.g., `10` for 10%).
        -   *If "Discount Type" is Amount:* Enter the monetary value (e.g., `5.00` for $5).
    -   **Recommended value:** A value that is attractive to customers but also profitable for your business (e.g., `10` for 10% off, or `5.00` for $5 off).
    -   **Merchant scenario / example:** You decide to offer a 15% discount for sharing. You would set "Discount Type" to "Percentage" and "Discount Value" to `15`.

-   **Minimum Amount for Discount:**
    -   **What this setting does:** Sets a minimum order total (before shipping) that a customer must meet to use the generated discount code.
    -   **Effect of changing this setting:**
        -   *When a value is entered (e.g., `50.00`):* The discount code will only be valid if the customer's cart total is equal to or greater than this amount.
        -   *When left empty or set to `0`:* The discount code can be used on any order, regardless of its total value.
    -   **Recommended value:** A value that encourages customers to add more items to their cart, or `0` if you want no minimum.
    -   **Merchant scenario / example:** To prevent customers from using a 10% discount on a $1 item, you might set a minimum amount of `$25.00`.

-   **Discount Code Validity (in days):**
    -   **What this setting does:** Defines how many days the generated discount code will be valid from the moment it's issued.
    -   **Effect of changing this setting:**
        -   *When a value is entered (e.g., `7`):* The discount code will expire after 7 days, creating a sense of urgency.
        -   *When left empty or set to `0`:* The discount code will have no expiration date (not recommended, as it reduces urgency).
    -   **Recommended value:** `7` to `30` days to encourage prompt use.
    -   **Merchant scenario / example:** You want customers to use their discount quickly. Setting this to `7` days will prompt them to make a purchase within a week.

-   **Discount Code Prefix:**
    -   **What this setting does:** Allows you to add a custom prefix to all generated discount codes. This helps you identify codes generated by this module in your PrestaShop discount management.
    -   **Effect of changing this setting:**
        -   *When a prefix is entered (e.g., `FBSHARE-`):* All generated codes will start with this prefix (e.g., `FBSHARE-XYZ123`).
        -   *When left empty:* Codes will be generated without a specific prefix.
    -   **Recommended value:** A short, descriptive prefix (e.g., `FB-`, `SHARE-`, `SOCIAL-`).
    -   **Merchant scenario / example:** To easily track the success of your Facebook sharing campaign, you could use `FB2023-` as a prefix.

-   **Display Share Button On:**
    -   **What this setting does:** Determines where the Facebook share button will appear on your product pages. This is typically a dropdown or radio button selection.
    -   **Effect of changing this setting:**
        -   *Header:* Button appears in the store's header (less common for product-specific shares).
        -   *Columns (Left/Right):* Button appears in one of the side columns.
        -   *Product Page (Main Content):* Button appears within the main product information area (most common and recommended).
        -   *Footer:* Button appears in the store's footer.
    -   **Recommended value:** "Product Page (Main Content)" for maximum visibility and relevance.
    -   **Merchant scenario / example:** You want the share button to be easily noticeable right next to the product image and description. Selecting "Product Page (Main Content)" ensures this.

-   **Text for Share Button:**
    -   **What this setting does:** Allows you to customize the text displayed on the Facebook share button.
    -   **Effect of changing this setting:**
        -   *When text is entered (e.g., "Share & Get Discount!"):* The button will display your custom text.
        -   *When left empty:* A default text (e.g., "Share on Facebook") will be used.
    -   **Recommended value:** Clear, action-oriented text that highlights the benefit (e.g., "Share for a Discount!", "Get X% Off - Share Now!").
    -   **Merchant scenario / example:** To entice customers, you might change the button text to "Share & Unlock Your Discount!".

-   **Popup Message Title:**
    -   **What this setting does:** Sets the title of the popup window that appears after a successful share, displaying the discount code.
    -   **Effect of changing this setting:**
        -   *When a title is entered (e.g., "Congratulations!"):* The popup will show your custom title.
        -   *When left empty:* A default title will be used.
    -   **Recommended value:** A welcoming and congratulatory title (e.g., "Your Discount Code!", "Thank You for Sharing!").
    -   **Merchant scenario / example:** You want to make the customer feel rewarded, so you set the title to "Here's Your Exclusive Discount!".

-   **Popup Message Content:**
    -   **What this setting does:** Allows you to customize the main text content within the discount code popup. You can include instructions or additional messages.
    -   **Effect of changing this setting:**
        -   *When content is entered:* The popup will display your custom message.
        -   *When left empty:* A default message will be used.
    -   **Recommended value:** A clear message instructing the customer to copy the code and how to use it (e.g., "Copy this code and apply it at checkout to receive your discount.").
    -   **Merchant scenario / example:** You want to remind customers where to use the code: "Thank you for sharing! Use the code below at checkout for your savings."

#### **Advanced Settings (if available)**

-   **CSS Stylesheet for Button/Popup:**
    -   **What this setting does:** Allows you to select or input custom CSS to style the share button and/or the discount popup to better match your theme.
    -   **Effect of changing this setting:**
        -   *When custom CSS is applied:* The visual appearance (colors, fonts, sizes) of the button and popup will change according to your styles.
        -   *When default is used:* The module will use its built-in styling.
    -   **Recommended value:** Leave empty initially, then customize if the default styling doesn't match your brand.
    -   **Merchant scenario / example:** Your store uses a specific shade of blue for buttons. You can add a CSS rule here to change the share button's background color to that shade.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Module Configuration | Enable / Disable Module | YES | Activates/deactivates all module features. |
| | Facebook App ID | Your App ID | Links your store to your Facebook App for tracking shares. |
| | Discount Type | Percentage | Defines if discount is a percentage or fixed amount. |
| | Discount Value | e.g., 10 (for 10%) | The actual value of the discount offered. |
| | Minimum Amount for Discount | 0 (no minimum) | Sets a minimum order value for discount code usage. |
| | Discount Code Validity (in days) | 7-30 days | Sets an expiration period for generated discount codes. |
| | Discount Code Prefix | FB- | Adds a custom prefix to generated codes for easy identification. |
| | Display Share Button On | Product Page (Main Content) | Controls the placement of the share button on product pages. |
| | Text for Share Button | Share for a Discount! | Customizes the text displayed on the share button. |
| | Popup Message Title | Your Discount Code! | Sets the title of the discount code popup. |
| | Popup Message Content | Copy this code... | Customizes the main message within the discount code popup. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The Facebook share button isn't appearing on my product pages.**
**A1:**
*   **Check Module Status:** Ensure the module is enabled in the configuration settings.
*   **Verify Facebook App ID:** Double-check that your Facebook App ID is correctly entered in the module configuration. An incorrect or missing ID will prevent the button from loading.
*   **Check Button Placement:** Confirm that the "Display Share Button On" setting is correctly chosen (e.g., "Product Page (Main Content)"). If your theme has heavily customized hooks, you might need to try different placements or consult a developer.
*   **Clear Cache:** Go to **Advanced Parameters > Performance** in your PrestaShop Back Office and clear the Smarty cache and all caches. Sometimes, old cached files prevent new module elements from appearing.

**Q2: Customers are sharing, but they are not receiving a discount code.**
**A2:**
*   **Facebook App ID:** This is the most common cause. The module relies on the Facebook App ID to track successful shares. Ensure it's correct and that your Facebook App is properly configured (e.g., website URL is added).
*   **Facebook Permissions/Privacy:** Sometimes, a customer's Facebook privacy settings or browser ad-blockers can interfere with the share tracking. This is less common but can happen.
*   **Module Configuration:** Review all discount-related settings (Discount Type, Value, Validity). Ensure they are set to valid values.
*   **PrestaShop Voucher Settings:** Ensure your PrestaShop store's general voucher/cart rule settings are not preventing the creation of new codes (e.g., maximum number of vouchers reached, though this is rare).

**Q3: The discount code popup looks strange or doesn't match my store's design.**
**A3:**
*   **Theme Conflicts:** Your custom PrestaShop theme might have conflicting CSS styles.
*   **Module CSS:** The module includes its own CSS. You can try to override it.
*   **Solution:** In the module configuration, look for any "Custom CSS" or "Stylesheet" options. You might need to add custom CSS rules there to adjust the popup's appearance. If you're not comfortable with CSS, a webmaster or developer can help. Clearing your browser's cache can also sometimes resolve minor display issues.

**Q4: Can I translate the button text and popup messages into other languages?**
**A4:** Yes, PrestaShop's translation system supports module translations.
*   Go to **International > Translations** in your Back Office.
*   Select "Installed modules translations", choose your theme, and then select your language.
*   Find the "Facebook product share + discount code" module and you can translate all user-facing texts, including the button text and popup messages.

**Q5: What if a customer shares a product multiple times? Do they get multiple discounts?**
**A5:** The module is designed to issue a unique discount code per *successful share event* for a given user. However, depending on the exact implementation, a user might be able to share different products and receive multiple codes. It's generally best practice to encourage unique shares for unique rewards. If you want to limit it to one code per customer regardless of shares, you might need custom development or to manually manage generated vouchers.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)
This section provides a deep dive into the technical structure of the "Facebook product share + discount code" module for developers and webmasters.

### 4.1 Architecture Overview
The module follows a standard PrestaShop module architecture, primarily leveraging the `Module` class for installation, uninstallation, and configuration. It integrates with the front-office through hooks to display the share button and uses AJAX for handling the post-share discount code generation. The core logic for voucher creation is likely encapsulated within the module's main class or a helper.

### 4.2 Controllers (`controllers/`)
This module does not appear to use dedicated `ModuleFrontController` or `AdminController` files in the `controllers/` directory based on the provided inventory. Front-office AJAX interactions are likely handled directly within the main module file (`ajax_productlike.php`) or through a generic PrestaShop AJAX dispatcher.

### 4.3 Core Classes & Models (`classes/`)
Based on the provided inventory, there are no custom `ObjectModel` classes defined in a `classes/` directory. The module likely manages its configuration directly via `Configuration::get()` and `Configuration::updateValue()` and creates PrestaShop `CartRule` objects for discounts.

### 4.4 JavaScript Assets (`views/js/`)
The module includes several JavaScript files, indicating client-side logic for Facebook interaction and popup display.

-   `productlike/js/productlike.js`:
    *   **Scope:** Front-office.
    *   **Responsibility:** Likely handles the core logic for initiating the Facebook share dialog, listening for the share completion event from Facebook's SDK, and then making an AJAX call back to the PrestaShop store to request the discount code. It would also manage the display of the discount code popup.
    *   **Key functionalities:** Facebook SDK initialization, `FB.ui` method calls for sharing, AJAX requests to the module's backend, DOM manipulation for popup display.

-   `productlike/js/script.js`:
    *   **Scope:** Front-office.
    *   **Responsibility:** This could be a general utility script or a fallback/alternative to `productlike.js`. It might contain event listeners for the share button click, or handle the display/hide logic for the discount popup.
    *   **Key functionalities:** Event binding, potentially simple animations or DOM manipulation.

-   `productlike/lib/voucherengine/script.js`:
    *   **Scope:** Front-office.
    *   **Responsibility:** Suggests a dedicated script for the voucher display and interaction. This might handle copying the voucher code to the clipboard, closing the popup, or other user interface elements related to the discount.
    *   **Key functionalities:** Clipboard API interaction, popup close events, UI feedback.

### 4.5 CSS Stylesheets (`views/css/`)
The module uses several CSS files for styling its front-office components.

-   `productlike/css/css.css`:
    *   **Scope:** Front-office customer styling.
    *   **Responsibility:** Contains general styles for the Facebook share button and potentially the discount code popup.
    *   **Key selectors:** `.productlike-button`, `.productlike-popup`, `.productlike-voucher-code`. Developers can override these in their theme's `custom.css` or by using the module's custom CSS input if available.

-   `productlike/css.css`:
    *   **Scope:** Front-office customer styling.
    *   **Responsibility:** Potentially an older or alternative stylesheet, or specific styles for certain elements not covered by `css.css`.
    *   **Key selectors:** Similar to `css.css`, depending on its content.

-   `productlike/lib/voucherengine/ps16.css`:
    *   **Scope:** Front-office customer styling, specifically for PrestaShop 1.6 compatibility.
    *   **Responsibility:** Provides styling adjustments to ensure the voucher popup and button look correct on PrestaShop 1.6 themes, which might have different default element styles.
    *   **Key selectors:** Likely targets common PrestaShop 1.6 UI elements to ensure visual consistency.

### 4.6 Smarty Template Structure (`views/templates/`)
The module utilizes Smarty templates for rendering its front-office components.

-   **Hook templates (`views/templates/hook/`)**:
    *   `productlike/header.tpl`:
        *   **Hook:** `displayHeader`
        *   **Purpose:** This template is likely responsible for initializing the Facebook JavaScript SDK, loading necessary JavaScript files, and potentially passing configuration variables (like the Facebook App ID) from the module's backend to the front-end JavaScript. It ensures the Facebook API is ready before the share button is rendered.
    *   `productlike/share.tpl`:
        *   **Hook:** `displayProductButtons`, `displayRightColumnProduct`, `displayLeftColumnProduct`, `displayFooterProduct` (or similar product page hooks, depending on configuration).
        *   **Purpose:** Renders the actual "Share on Facebook" button on the product page. It will contain the HTML structure for the button and potentially a placeholder for the discount code popup, which is then dynamically populated by JavaScript.

-   **Admin templates (`views/templates/admin/`)**: None explicitly listed, implying the configuration is handled directly by `getContent()` in the main module file.

-   **Front-office templates (`views/templates/front/`)**: None explicitly listed, as the main interaction is via hooks and popups.

### 4.7 Database Schema & Hooks Map

-   **Database Tables**:
    *   The module likely does not create custom database tables.
    *   Configuration settings (Facebook App ID, discount values, etc.) are stored in the `ps_configuration` table using keys like `PRODUCTLIKE_FACEBOOK_APP_ID`, `PRODUCTLIKE_DISCOUNT_TYPE`, `PRODUCTLIKE_DISCOUNT_VALUE`, etc.
    *   Generated discount codes are standard PrestaShop `CartRule` entries, stored in `ps_cart_rule` and related tables.

-   **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | In the `<head>` section of every page. | Initializes Facebook SDK, loads module JS/CSS, passes config variables. |
| `displayProductButtons` | On the product page, typically near the Add to Cart button. | Renders the Facebook share button. (Common for PS 1.7+) |
| `displayRightColumnProduct` | In the right column of the product page. | Renders the Facebook share button (if configured). |
| `displayLeftColumnProduct` | In the left column of the product page. | Renders the Facebook share button (if configured). |
| `displayFooterProduct` | In the footer area of the product page. | Renders the Facebook share button (if configured). |
| `displayProductExtraContent` | On the product page, for extra content tabs/blocks. | Alternative hook for button placement (PS 1.7+). |
| `actionFrontControllerSetMedia` | Before the front controller renders the page. | Registers module's JS and CSS files. |
| `actionObjectCartRuleAddAfter` | After a new cart rule (voucher) is added. | Potentially used for logging or further processing of generated vouchers. |

## 5. Official Support & Updates
For the latest updates, bug fixes, and professional support for your "Facebook product share + discount code" module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our team is dedicated to providing assistance and ensuring your module functions optimally.
