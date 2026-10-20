---
title: "Checkout stock checker PRO - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Checkout stock checker PRO PrestaShop module by MyPresta.eu."
sidebar:
  label: "Checkout stock checker PRO"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Checkout stock checker PRO Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/checkout-stock-checker-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/checkout-stock-checker-pro/)
>
> ---


# Checkout stock checker PRO

## 1. Requirements & Compatibility

-   **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
-   **PHP Compatibility**: PHP 5.6 - 8.5
-   **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient and available on most modern hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)
After installation, clicking "Configure" will take you to the main and only configuration screen for the "Checkout stock checker PRO" module. This screen allows you to enable or disable the module's core functionality.

#### **Enable / Disable Module**
-   **What this setting does:** This is the main switch to turn the stock checking functionality on or off.
-   **Effect of changing this setting:**
    -   *When enabled (YES):* The module will actively check product stock levels just before an order is placed. If an item is out of stock, the customer will be redirected to the cart with a notification.
    -   *When disabled (NO):* The module will be inactive. Stock checks will not occur, and customers might be able to place orders for out-of-stock items, relying solely on PrestaShop's default stock management behavior (which typically only checks when adding to cart, not at final order placement).
-   **Recommended value:** **YES**. To fully benefit from the module's purpose, it should always be enabled.
-   **Merchant scenario / example:** You've just installed the module and want to start preventing out-of-stock orders. You would set this to "YES". If you temporarily need to disable the feature for maintenance or testing, you would set it to "NO".

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Module Configuration Page | Enable / Disable Module | YES | Controls whether the module actively checks stock before order placement. Prevents orders for out-of-stock items when enabled. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: The module is enabled, but customers are still placing orders for out-of-stock items. What's wrong?**
A:
1.  **Clear Cache:** First, try clearing your PrestaShop cache. Go to **Advanced Parameters > Performance** and click "Clear cache" in the top right.
2.  **Check Module Status:** Double-check that the module is indeed enabled in its configuration page.
3.  **Theme Conflicts:** Some highly customized themes or other checkout-modifying modules might interfere. Temporarily switch to the default PrestaShop theme (Classic) and test again. If it works, the issue is likely a theme conflict, and you may need a developer to investigate.
4.  **PrestaShop Version:** Ensure you downloaded the correct module version for your specific PrestaShop installation.

**Q: My customers are being redirected to the cart, but the notification message isn't showing up, or it's poorly styled.**
A:
1.  **Clear Cache:** As always, clear your PrestaShop cache.
2.  **Theme Styling:** The notification message uses standard PrestaShop alert classes. If your theme has heavily customized or removed these styles, the message might be invisible or improperly formatted. A webmaster can inspect the HTML and CSS to ensure the message is present and styled correctly.
3.  **Module Files:** Ensure all module files were uploaded correctly. Sometimes, incomplete uploads can lead to missing template files for notifications.

**Q: Does this module work with multi-language stores?**
A: Yes, the module uses standard PrestaShop translation mechanisms. The notification messages displayed to customers can be translated into all languages configured in your store. You can manage these translations under **International > Translations > Installed Modules Translations**.

**Q: Will this module slow down my checkout process?**
A: The stock check performed by the module is very fast, typically adding only milliseconds to the checkout process. It's a direct database query for stock levels, which is highly optimized. The performance impact is negligible and far outweighed by the benefits of preventing out-of-stock orders.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)
This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview
The "Checkout stock checker PRO" module (`csc`) is designed to integrate seamlessly into the PrestaShop checkout flow. It primarily operates by hooking into the final stage of the order placement process, leveraging a front controller to perform an AJAX-based stock verification. This approach ensures that the stock check is performed in real-time just before the order is committed to the database, preventing race conditions where stock might change between the cart review and final order confirmation. The module adheres to PrestaShop's MVC pattern for its front-end interaction and configuration.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers
-   `csc/controllers/front/AjaxCheck.php`
    *   **Class name & parent class:** `CscAjaxCheckModuleFrontController` extending `ModuleFrontController`.
    *   **Responsibility:** This controller is the core of the module's functionality. It's responsible for handling the AJAX request initiated from the front-office checkout page. Upon receiving the request, it iterates through the products in the customer's cart, checks their current stock levels against the requested quantities, and returns a JSON response indicating whether all items are in stock or which items are out of stock. It does not render a full page but provides data for the JavaScript to act upon.
-   `csc/controllers/front/index.php`
    *   **Class name & parent class:** This is a standard empty `index.php` file, typically included in PrestaShop module directories to prevent direct directory listing. It does not contain a class or specific logic.

#### Back-Office Admin Controllers
The module does not utilize any custom Admin Controllers. Its configuration is handled directly within the main module file's `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)
The module does not define any custom `ObjectModel` classes or dedicated business logic classes within the `classes/` directory. All core logic is encapsulated within the main module file (`ajax_csc.php`) and the `AjaxCheck` front controller.

### 4.4 JavaScript Assets (`views/js/`)
-   `csc/views/js/csc.js`
    *   **Scope:** Front-office.
    *   **Details:** This JavaScript file is responsible for initiating the AJAX stock check. It typically hooks into the final "Place Order" button click event (or equivalent form submission) on the checkout page. Before allowing the form submission to proceed, it sends an AJAX request to the `AjaxCheck` front controller. Based on the JSON response, it either allows the checkout to complete or prevents the submission, redirects the user back to the cart, and displays the appropriate error message. It uses standard jQuery or PrestaShop's native JavaScript events (`prestashop.on`) to achieve this.

### 4.5 CSS Stylesheets (`views/css/`)
-   `csc/views/css/csc.css`
    *   **Scope:** Front-office customer styling.
    *   **Details:** This stylesheet provides basic styling for the notification messages displayed on the cart page when products are found to be out of stock. It likely targets specific CSS classes added to the notification `div` elements.
    *   **Key CSS class selectors developers can override:** Developers can inspect the HTML output of the notification message to identify the specific classes (e.g., `.alert-danger`, `.csc-notification`, etc.) and override them in their theme's `custom.css` or `theme.css` to match their store's branding.

### 4.6 Smarty Template Structure (`views/templates/`)

-   **Hook templates (`views/templates/hook/`)**: None explicitly listed, suggesting the module's primary interaction is via AJAX and redirection, with notifications rendered directly by the `AjaxCheck` controller or the main module.
-   **Admin templates (`views/templates/admin/`)**: None, as configuration is handled by `getContent()`.
-   **Front-office templates (`views/templates/front/`)**:
    *   `csc/lib/searchTool/views/scripts.tpl`
        *   **Purpose:** This template likely includes the `csc.js` JavaScript file and potentially passes configuration variables from the module's back-end to the front-end JavaScript. It's probably hooked into `displayHeader` or `displayFooter` to ensure the JS is loaded on relevant pages (e.g., checkout).
    *   `csc/views/errors.tpl`
        *   **Purpose:** This template is rendered when the stock check fails (i.e., items are out of stock). It displays the error message and lists the specific products that are no longer available. This is the template responsible for the visible notification on the cart page after redirection.
    *   `csc/views/no-errors.tpl`
        *   **Purpose:** This template is likely a placeholder or a template that would be rendered if there were no errors, but the module's primary function is to display errors. It might be used for internal logic or simply be an empty template.

### 4.7 Database Schema & Hooks Map

-   **Database Tables**: The module does not create any custom database tables. It relies entirely on PrestaShop's existing `ps_product`, `ps_stock_available`, and `ps_configuration` tables. Configuration settings (like the enable/disable switch) are stored in `ps_configuration` using keys like `CSC_ENABLED`.

-   **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | Renders content in the `<head>` section of every page. | Likely used to include the `csc.js` script and `csc.css` stylesheet, ensuring they are available on checkout pages. |
| `displayFooter` | Renders content at the end of the `<body>` section of every page. | Alternative hook to `displayHeader` for including JS/CSS, often preferred for performance. |
| `displayProductButtons` | Renders content near product buttons (e.g., add to cart). | *Not explicitly used for core functionality, but could be for future features or minor UI elements.* |
| `displayRightColumn` | Renders content in the right column of the store. | *Not explicitly used for core functionality, but could be for future features or minor UI elements.* |
| `actionFrontControllerSetMedia` | Executed when a front controller sets its media (JS/CSS). | A more targeted hook for adding JS/CSS specifically to relevant front controllers (e.g., checkout pages). |
| `actionBeforeUpdateQuantity` | Executed before a product quantity is updated in the cart. | *Not explicitly used for core functionality, but could be for future features or minor UI elements.* |
| `actionCartSave` | Executed after a cart is saved. | *Not explicitly used for core functionality, but could be for future features or minor UI elements.* |
| `actionValidateOrder` | Executed after an order is validated. | *Crucial for the module's logic.* This is the point where the module intervenes to perform the final stock check *before* the order is fully committed. The module's JavaScript likely prevents the form submission that triggers this hook if stock issues are found. |

*Note: The module's primary mechanism for stock checking is through its `AjaxCheck` front controller, which is triggered by JavaScript on the checkout page, rather than solely relying on PrestaShop's native hooks for the stock check itself. Hooks are primarily used for loading assets and potentially for displaying notifications.*

## 5. Official Support & Updates
For the latest updates, bug fixes, and official support for the "Checkout stock checker PRO" module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module's functionality and integration.
