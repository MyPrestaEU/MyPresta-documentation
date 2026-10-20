---
title: "Add to cart for logged only - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Add to cart for logged only PrestaShop module by MyPresta.eu."
sidebar:
  label: "Add to cart for logged only - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Add to cart for logged only Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/add-to-cart-for-logged-only.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/add-to-cart-for-logged-only/)
>
> ---


# Add to cart for logged only

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Add to cart for logged only” module to access its settings.

#### **Show**

- **What this setting does:** This is the main toggle to enable or disable the module’s core functionality.
- **Effect of changing this setting:**
  - *When enabled (Yes):* The module will be active. Unlogged users will be prevented from adding products to their cart, and a message will be displayed prompting them to log in.
  - *When disabled (No):* The module will be inactive. All users, whether logged in or not, will be able to add products to their cart as per standard PrestaShop behavior.
- **Recommended value:** **Yes** if you want to enforce the “logged-in only” cart rule. **No** if you want to temporarily disable the feature without uninstalling the module.
- **Merchant scenario / example:** If you’re running a B2B store and only want your registered business clients to place orders, you would set this to “Yes”. If you’re temporarily opening up your store to public browsing and cart additions for a special promotion, you might set it to “No” for that period.

#### **Configuration Quick Reference Table**

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Show | Yes | Enables/disables the module’s core functionality, restricting “Add to Cart” to logged-in users. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve enabled the module, but unlogged users can still add products to the cart. What’s wrong?**
A:

1. **Clear Cache:** The most common issue is caching. Go to **Advanced Parameters > Performance** in your PrestaShop Back Office and click “Clear cache” (or “Clear Smarty cache” in older versions).
2. **Module Position:** Ensure the module is hooked correctly. While the module handles this automatically, sometimes theme conflicts can interfere. Check the module’s configuration and ensure it’s active.
3. **Theme Compatibility:** Very rarely, a highly customized theme might override standard PrestaShop button behaviors. If clearing cache doesn’t work, temporarily switch to the default PrestaShop theme (e.g., Classic) to see if the issue persists. If it resolves, your theme is likely causing a conflict, and you may need a developer to investigate.

**Q: Can I customize the message shown to unlogged users?**
A: Yes, the message is typically translatable. Go to **International > Translations** in your Back Office. Select “Installed modules translations”, choose your theme, and then select “Add to cart for logged only”. You should find the text string there to modify for each language.

**Q: Will this module affect my SEO?**
A: No, this module primarily affects the “Add to Cart” button’s functionality for front-end users. It does not block search engine crawlers from indexing your product pages or content. Your products will still be visible and discoverable.

**Q: What if a customer logs out after adding items to the cart?**
A: The module prevents *adding* to the cart when unlogged. If a customer logs in, adds items, and then logs out, the items typically remain in their cart (associated with their account) for when they log back in. The module’s restriction applies to the action of adding new items while not logged in.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview of the “Add to cart for logged only” module for developers and webmasters.

### 4.1 Architecture Overview

The “Add to cart for logged only” module is a lightweight PrestaShop module primarily designed to intercept and modify the behavior of the “Add to Cart” action based on the user’s login status. It achieves this by leveraging PrestaShop’s hook system and injecting JavaScript to disable or modify the “Add to Cart” button and display a message for unlogged users. It does not introduce new database tables or complex object models, focusing instead on front-end interaction and existing PrestaShop core functionalities.

### 4.2 Controllers (`controllers/`)

This module does not utilize custom Front-Office or Back-Office Admin Controllers. All configuration is handled within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

This module does not introduce any custom classes or extend `ObjectModel`. Its logic is primarily contained within the main `cartforlogged.php` file.

### 4.4 JavaScript Assets (`views/js/`)

- **`cartforlogged/views/js/cfl-17500.js`**

  - **Scope:** Front-office.
  - **Purpose:** This script is likely designed for PrestaShop 1.7.x and 8.x versions (indicated by `17500`). It targets the “Add to Cart” button (`#add_to_cart button`, `.add-to-cart`) and potentially other elements like quantity inputs.
  - **Functionality:**
    - Checks if the user is logged in (`isLogged`).
    - If not logged in, it disables the “Add to Cart” button, changes its text (e.g., to “Only logged users…”), and potentially adds a CSS class to visually style it as disabled.
    - It might also prevent form submission or AJAX calls related to adding products to the cart.
    - It likely uses `prestashop.on('updateCart', ...)` or similar event listeners to re-apply its logic after cart updates or page changes (e.g., when product attributes are changed).
- **`cartforlogged/views/js/cfl.js`**

  - **Scope:** Front-office.
  - **Purpose:** This script is likely a more generic or fallback version, potentially for older PrestaShop versions (1.5.x, 1.6.x) or as a base for the more specific `cfl-17500.js`.
  - **Functionality:** Similar to `cfl-17500.js`, it identifies the “Add to Cart” button (e.g., `#add_to_cart button`, `.exclusive button`), checks login status, and disables the button for unlogged users. It might use jQuery’s `$(document).ready()` and event delegation to handle dynamic content.

### 4.5 CSS Stylesheets (`views/css/`)

- **`cartforlogged/views/css/cfl.css`**
  - **Scope:** Front-office customer styling.
  - **Purpose:** Provides basic styling for the disabled “Add to Cart” button or the message displayed to unlogged users.
  - **Key CSS class selectors developers can override:**
    - `.cfl_disabled_button`: Likely applied to the “Add to Cart” button when it’s disabled by the module. Developers can use this to change background color, cursor, opacity, etc., to clearly indicate it’s inactive.
    - `.cfl_message`: If the module injects a specific message element, this class would style it.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`cartforlogged/views/templates/admin/json.tpl`**
  - **Scope:** Admin templates.
  - **Purpose:** This template is likely used internally by the module’s `getContent()` method to output JSON data, possibly for AJAX requests within the configuration page or for dynamic content updates. It’s not a front-office visible template. It might be used to return configuration status or other data to the JavaScript on the admin page.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: This module does not create any custom database tables. It stores its configuration settings (e.g., `CFL_LOGIN`) in the standard `ps_configuration` table.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Used to include CSS and JavaScript assets (`cfl.css`, `cfl.js`, `cfl-17500.js`) that modify the “Add to Cart” button behavior. |
| `actionCartSave` | After a cart is saved or updated. | This hook could potentially be used to re-evaluate cart contents or apply restrictions, but given the module’s description, its primary function is likely front-end JS injection via `displayHeader`. It might be a fallback or a way to ensure server-side validation, though the module description emphasizes client-side. |
| `actionAdminControllerSetMedia` | When an admin controller is loaded and its media (JS/CSS) are being set. | Used to include any necessary JavaScript or CSS for the module’s Back Office configuration page. |
| `header` | Similar to `displayHeader`, often used interchangeably or for specific legacy themes. | Used to include CSS and JavaScript assets, ensuring compatibility across different PrestaShop versions and themes. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Add to cart for logged only” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
