---
title: "Limit quantity of products in cart for unlogged users - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Limit quantity of products in cart for unlogged users PrestaShop module by MyPresta.eu."
sidebar:
  label: "Limit quantity of products in cart for unlogged users - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Limit quantity of products in cart for unlogged users Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/limit-quantity-of-products-in-cart-for-unlogged-users.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/limit-quantity-of-products-in-cart-for-unlogged-users/)
>
> ---


# Limit quantity of products in cart for unlogged users

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main and only configuration screen for the module. You will find it by navigating to **Modules > Module Manager**, searching for “Limit quantity of products in cart for unlogged users”, and clicking “Configure”.

#### **Maximum quantity of products in cart for unlogged users**

- **What this setting does:** This is the core setting of the module. It defines the absolute maximum total quantity of items that an unlogged customer can have in their shopping cart.
- **Effect of changing this setting:**
  - *If set to 0:* The module will be effectively disabled, and unlogged users can add an unlimited quantity of products to their cart, just like logged-in users.
  - *If set to a number greater than 0 (e.g., 5):* An unlogged customer will be able to add items to their cart until the total quantity of all items reaches this number. If they try to add another item that would exceed this limit, the module will prevent the addition and display the warning popup.
- **Recommended value:** This depends entirely on your business strategy.
  - *For B2C stores wanting to gently encourage login:* A value like `3` or `5` can be effective.
  - *For B2B stores or stores with high-value items:* A lower value like `1` or `2` might be appropriate to ensure only serious, logged-in buyers can reserve stock.
  - *If you don’t want any limits:* Set to `0`.
- **Merchant scenario / example:** You sell custom-printed t-shirts. You want casual browsers to see a few designs in their cart, but for them to commit to a larger order, you prefer they log in. You set this to `3`. An unlogged customer adds a t-shirt (quantity 1), then another (quantity 1), then a third (quantity 1). Their cart now has 3 items. If they try to add a fourth t-shirt, they will see the popup message, prompting them to log in.

#### **Message for unlogged users**

- **What this setting does:** This allows you to customize the text of the popup message that appears when an unlogged user tries to exceed the defined cart quantity limit.
- **Effect of changing this setting:**
  - *If you leave it as default:* The standard message “As an unlogged customer you can not add more products to cart. Please log in to continue add to cart process.” will be displayed.
  - *If you customize it:* Your custom message will be shown instead. This allows you to tailor the tone, add specific instructions, or even include a link (though direct links in popups can be tricky without further customization).
- **Recommended value:** The default message is clear and effective. Only change it if you have a specific branding voice or additional instructions you want to convey. Keep it concise.
- **Merchant scenario / example:** You want a slightly softer tone. You change the message to: “To add more items to your cart, please log in or create an account. We’d love to see you join our community!”

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | **Maximum quantity of products in cart for unlogged users** | `0` (disabled) / `3-5` (recommended for B2C) | Sets the total number of items an unlogged customer can add to their cart. Prevents further additions and shows a popup if exceeded. |
| Module Configuration | **Message for unlogged users** | “As an unlogged customer you can not add more products to cart. Please log in to continue add to cart process.” | Customizes the text displayed in the popup when an unlogged user hits the cart limit. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve set a limit, but unlogged users can still add unlimited products. What’s wrong?**
A:

1. **Check the “Maximum quantity” setting:** Ensure it’s set to a number greater than `0`. If it’s `0`, the module is disabled.
2. **Clear your browser cache:** Your browser might be showing you an old version of the page. Try clearing your browser’s cache and cookies, or test in an incognito/private browsing window.
3. **Clear PrestaShop cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” in the top right.
4. **Ensure you are truly unlogged:** Double-check that you are not logged into a customer account in your browser. The easiest way to test is to open a new incognito/private browsing window.

**Q: The popup message isn’t showing, or it looks strange.**
A:

1. **Check the module’s “Message for unlogged users” setting:** Ensure it’s not empty if you expect a custom message.
2. **Theme compatibility:** While the module is designed to be compatible, very heavily customized themes might sometimes interfere with JavaScript or CSS. If the popup doesn’t appear at all, check your browser’s developer console for JavaScript errors (F12 key, then Console tab). If it looks strange, it might be a CSS conflict. Contact MyPresta.eu support with details of your theme.

**Q: Does this module affect logged-in customers?**
A: No, this module specifically targets *unlogged* users. Once a customer logs into their account, the quantity limit imposed by this module no longer applies to them.

**Q: Can I set different limits for different product categories?**
A: No, this module applies a single, global quantity limit for all products in the cart for unlogged users. It does not support category-specific or product-specific limits.

**Q: What happens if an unlogged user adds 3 items, then logs in, and then tries to add more?**
A: Once the user logs in, they are no longer considered “unlogged.” The module’s restriction is lifted, and they can continue adding products to their cart without any quantity limit from this module.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Limit quantity of products in cart for unlogged users” module (`lqfu`) is a lightweight PrestaShop module primarily implemented through a main module class (`lqfu/index.php`) and a custom JavaScript file (`lqfu/views/js/lqfu.js`). It leverages PrestaShop’s hook system to inject its JavaScript into the front office and uses AJAX to communicate with the server-side logic to check and enforce the cart quantity limit for guest users. The module stores its configuration in `ps_configuration`.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. The module’s front-office logic is handled directly via the main module file’s `hookDisplayHeader` and AJAX requests, which are processed by PrestaShop’s core `CartController` or `ProductController` and intercepted by the module’s logic.
- **Back-Office Admin Controllers**: None. All configuration is handled within the main module’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

- No custom classes extending `ObjectModel` are defined in this module. All logic resides within the main `Lqfu` class in `index.php`.

### 4.4 JavaScript Assets (`views/js/`)

- **`lqfu/views/js/lqfu.js`**
  - **Scope:** Front-office.
  - **Purpose:** This script is responsible for intercepting “Add to Cart” actions, checking the current cart quantity for unlogged users, and displaying the custom popup message if the limit is exceeded.
  - **Key Functionality:**
    - Binds event listeners to “Add to Cart” buttons (or forms) across the store (e.g., product page, category listings).
    - On an “Add to Cart” attempt, it first checks if the user is logged in.
    - If the user is not logged in, it retrieves the current cart quantity (either from a hidden element or by making an AJAX call if necessary).
    - Compares the current cart quantity + the quantity being added against the configured maximum limit.
    - If the limit is exceeded, it prevents the default “Add to Cart” action, displays a custom modal/popup with the configured message, and potentially disables the “Add to Cart” button temporarily.
    - The script likely uses jQuery for DOM manipulation and event handling, common in PrestaShop front-office.

### 4.5 CSS Stylesheets (`views/css/`)

- **`lqfu/views/css/lqfu.css`**
  - **Scope:** Front-office customer styling.
  - **Purpose:** Provides basic styling for the popup message that appears when an unlogged user exceeds the cart quantity limit.
  - **Key CSS Class Selectors:** Developers can expect classes related to the popup container, message text, and possibly close buttons. These can be overridden in a custom theme’s `custom.css` or `theme.css` to match the store’s branding.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**: None explicitly listed, but the module might implicitly render content via `displayHeader` or similar hooks if it needs to inject hidden data or initial JS variables.
- **Admin templates (`views/templates/admin/`)**:
  - **`lqfu/views/templates/admin/json.tpl`**: This template is likely used for rendering JSON data in a structured way within the Back Office, possibly for debugging or specific AJAX responses from the module’s configuration page, though its direct use for the main configuration is less common. It might be a remnant or used for a specific internal module function.
- **Front-office templates (`views/templates/front/`)**: None. The popup is likely generated dynamically via JavaScript.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  - The module does not create any custom SQL tables.
  - Configuration settings are stored in the `ps_configuration` table:
    - `PS_LQFU_MAX_QUANTITY`: Stores the integer value for the maximum quantity of products for unlogged users.
    - `PS_LQFU_MESSAGE`: Stores the string value for the custom message displayed in the popup.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Injects the module’s CSS (`lqfu.css`) and JavaScript (`lqfu.js`) files into the front office. May also pass configuration variables (like the max quantity and message) to the JavaScript. |
| `actionCartSave` | After a cart is saved (e.g., product added/removed). | The module likely intercepts this hook (or a similar one like `actionObjectCartAddAfter`) to re-evaluate the cart quantity and potentially prevent the addition of items if the limit is exceeded for an unlogged user. This is where the server-side validation would occur before the JS popup is triggered. |

## 5. Official Support & Updates

For official updates, technical support, and further assistance with the “Limit quantity of products in cart for unlogged users” module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to help with any issues or questions you may have.
