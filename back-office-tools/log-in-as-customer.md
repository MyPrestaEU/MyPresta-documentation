---
title: "Log in as customer - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Log in as customer PrestaShop module by MyPresta.eu."
sidebar:
  label: "Log in as customer - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Log in as customer Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/log-in-as-customer.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/log-in-as-customer/)
>
> ---


# Log in as customer

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

The “Log in as customer” module has a very straightforward configuration. After installation, when you click “Configure,” you will be taken to a simple screen.

**Screen Name & Menu Location:** Back Office > Modules > Module Manager > Log in as customer > Configure

On this screen, you will typically find a simple confirmation that the module is installed and ready. The core functionality of this module is integrated directly into your customer list, rather than requiring extensive settings on a dedicated configuration page.

- **What this screen does:** This page confirms the module’s installation and provides any basic information or quick links. For “Log in as customer,” its primary purpose is to confirm that the module is active and ready to use.
- **Effect of changing settings:** There are no complex settings to change here. The module’s functionality is activated upon installation.
- **Recommended value:** No specific values to set. Just ensure the module is installed and enabled.
- **Merchant scenario / example:** After installing, you’ll see a message confirming the module is active. You can then proceed directly to the Customers section of your Back Office to use its features.

### 2.2 Using the “Log in as customer” Feature

The main functionality of this module is accessed directly from your PrestaShop customer list.

**Screen Name & Menu Location:** Back Office > Customers > Customers

1. **Navigate to Customers:** In your PrestaShop Back Office, go to the **Customers** menu and then click on **Customers**.
2. **Locate the Customer:** Find the customer you wish to log in as in the customer list. You can use the search and filter options to quickly locate them.
3. **Click the “Log in as customer” Button:** For each customer in the list, you will now see an additional button (often an icon like a person or a key, or a text button) in the “Actions” column. This button is added by the “Log in as customer” module.
   - **What this button does:** When you click this button, the module performs a secure login process. It logs you out of your administrator account (temporarily) and then logs you in as the selected customer.
   - **Effect of clicking this button:** You will be immediately redirected to the front office of your store. You will see the store exactly as that customer sees it, including their active cart, order history, addresses, and any personalized content or pricing.
   - **Merchant scenario / example:** A customer reports an issue adding a specific product to their cart. You navigate to “Customers,” find their name, click “Log in as customer,” and are instantly taken to the front office as them. You can then try to add the product yourself, troubleshoot the issue, or verify their cart contents.
4. **Logging Out as Customer:** To return to your Back Office administrator session, simply log out from the front office (as if you were a regular customer). This will end the customer session, and you can then log back into your Back Office.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | (No direct settings) | N/A | Confirms module installation and readiness. |
| Customers List (Back Office) | “Log in as customer” button | N/A | Allows instant login to the front office as a selected customer for troubleshooting and testing. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve installed the module, but I don’t see the “Log in as customer” button in the customer list.**
A:

1. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions).
2. **Module Status:** Ensure the module is enabled. Go to **Modules > Module Manager**, search for “Log in as customer,” and verify it’s active.
3. **Theme Compatibility:** While rare, some heavily customized themes might interfere with the display of new buttons. If the issue persists, contact MyPresta.eu support.
4. **PrestaShop Version:** Ensure you downloaded the correct module version for your PrestaShop installation.

**Q: When I click the button, I’m redirected to the front office, but I’m not logged in as the customer.**
A:

1. **Browser Cookies:** Ensure your browser accepts cookies. Try clearing your browser’s cache and cookies, then try again.
2. **Session Configuration:** Check your PrestaShop’s `config/defines.inc.php` file for `_PS_COOKIE_DOMAIN_` and `_PS_COOKIE_PATH_` settings. Ensure they are correctly configured for your domain.
3. **Server Configuration:** Verify that your server’s PHP session settings are standard and not overly restrictive.

**Q: Can I log in as a customer and then perform actions like placing an order for them?**
A: Yes, you can. However, exercise extreme caution. Always obtain explicit permission from the customer before performing any actions on their behalf, especially placing orders or modifying personal data. It’s generally best practice to use this feature for viewing and troubleshooting, not for making changes without consent.

**Q: Is it safe to use this module? Does it store customer passwords?**
A: The module does not store or access customer passwords. It uses PrestaShop’s internal session management to simulate a customer login, similar to how PrestaShop’s “Forgot Password” functionality works by generating a temporary secure session. It’s designed to be secure.

**Q: What happens if I log in as a customer and then close my browser without logging out?**
A: The customer session will eventually expire based on your PrestaShop’s session timeout settings. To return to your admin panel, you would simply navigate to your Back Office URL and log in again as an administrator.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Log in as customer” module (`lac`) is a lightweight PrestaShop module primarily focused on extending the Back Office customer list functionality. It leverages PrestaShop’s core `Customer` and `Context` classes to manage user sessions and redirection. The module injects JavaScript into the Back Office to add the “Log in as customer” button and uses a dedicated front controller to handle the secure login process and redirection to the front office. It follows a standard PrestaShop module architecture, integrating seamlessly without custom database tables or complex object models.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `lac/controllers/front/index.php`
    - **Class Name**: `LacIndexModuleFrontController` (likely, based on file naming convention)
    - **Parent Class**: `ModuleFrontController`
    - **Responsibility**: This controller likely serves as a landing point or a fallback. Given the `login.php` controller, `index.php` might be less critical or handle initial setup/redirection if `login.php` is the primary action handler. It could also be a placeholder.
  - `lac/controllers/front/login.php`
    - **Class Name**: `LacLoginModuleFrontController` (likely)
    - **Parent Class**: `ModuleFrontController`
    - **Responsibility**: This is the core controller for the “Log in as customer” functionality.
      - It receives the customer ID via a GET or POST parameter from the Back Office.
      - It performs the necessary steps to log out the current administrator session.
      - It then securely logs in the specified customer by manipulating the `Context` and `Customer` objects (e.g., `Context::getContext()->customer = new Customer($id_customer); Context::getContext()->cookie->id_customer = $id_customer;`).
      - It then redirects the browser to the front office homepage or a specific customer-related page (`my-account`, `history`, etc.).
- **Back-Office Admin Controllers**:

  - None. The module integrates directly into the existing `AdminCustomers` controller’s view via hooks and JavaScript.

### 4.3 Core Classes & Models (`classes/`)

- None. This module does not introduce custom `ObjectModel` classes or database tables. It operates directly on PrestaShop’s native `Customer` and `Context` objects.

### 4.4 JavaScript Assets (`views/js/`)

These JavaScript files are responsible for injecting the “Log in as customer” button into the Back Office customer list and handling the click event to initiate the login process. The different file names suggest compatibility adjustments for various PrestaShop versions.

- `lac/views/js/16customers.js`
  - **Scope**: Back-office (PrestaShop 1.6.x `AdminCustomers` list).
  - **Functionality**: This script targets the customer list table in PrestaShop 1.6.x. It likely uses jQuery selectors to find the “Actions” column for each customer row and appends a new button or link. The click handler for this button will then construct a URL pointing to the module’s front controller (`lac/controllers/front/login.php`) with the customer’s ID and redirect the browser.
- `lac/views/js/176orders.js`
  - **Scope**: Back-office (PrestaShop 1.7.6.x order view).
  - **Functionality**: This script might be intended for adding a “Log in as customer” button directly from the order view in 1.7.6.x, allowing quick access to the customer associated with a specific order. It would extract the customer ID from the order details page and use it for the login redirection.
- `lac/views/js/177orders.js`
  - **Scope**: Back-office (PrestaShop 1.7.7.x+ order view).
  - **Functionality**: Similar to `176orders.js`, but adapted for potential DOM changes or different table structures in PrestaShop 1.7.7.x and later versions of the order view.
- `lac/views/js/17carts.js`
  - **Scope**: Back-office (PrestaShop 1.7.x cart view).
  - **Functionality**: This script likely adds the “Log in as customer” button to the Back Office cart details page, allowing an admin to log in as the customer associated with a specific cart.
- `lac/views/js/17customersview.js`
  - **Scope**: Back-office (PrestaShop 1.7.x, 8.x, 9.x `AdminCustomers` list).
  - **Functionality**: This is the primary script for injecting the button into the customer list for modern PrestaShop versions. It will target the `AdminCustomers` list, identify the customer ID for each row, and append the “Log in as customer” action button. It uses event delegation to handle clicks on these dynamically added buttons, constructing the appropriate URL for the `lac/controllers/front/login.php` controller.

### 4.5 CSS Stylesheets (`views/css/`)

- None. The module does not include custom CSS files. It likely relies on PrestaShop’s default styling for buttons or uses inline styles if necessary, or the button is styled by the Back Office theme itself.

### 4.6 Smarty Template Structure (`views/templates/`)

- None. The module does not use custom Smarty templates. Its Back Office integration is purely via JavaScript injection, and the front-office login is handled by direct redirection from the controller.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  - The module does not create any custom database tables. It stores its configuration (if any, though none were explicitly identified beyond basic module status) in the standard `ps_configuration` table.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayBackOfficeHeader` | Executed in the `<head>` section of every Back Office page. | Used to include the necessary JavaScript files (`16customers.js`, `17customersview.js`, etc.) into the Back Office, specifically when the `AdminCustomers` controller is active. This ensures the “Log in as customer” button is added to the customer list. |
| `displayAdminCustomers` | Executed on the `AdminCustomers` controller page. | This hook is specifically designed for modules to add content or actions to the customer list. The module might use this hook to render a small template or directly inject JavaScript to add the button. |
| `actionAdminControllerSetMedia` | Executed when a Back Office controller is setting its media (JS/CSS). | A more robust hook for adding JS/CSS conditionally based on the active controller. The module would use this to load its specific JS files only when on `AdminCustomers` or `AdminOrders` pages. |
| `displayAdminOrder` | Executed on the `AdminOrders` controller page. | If the module adds a “Log in as customer” button to the order view (as suggested by `176orders.js`, `177orders.js`), this hook would be used to inject the necessary JavaScript or button HTML. |
| `displayAdminCarts` | Executed on the `AdminCarts` controller page. | If the module adds a “Log in as customer” button to the cart view (as suggested by `17carts.js`), this hook would be used. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Log in as customer” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any technical issues or questions you may have.
