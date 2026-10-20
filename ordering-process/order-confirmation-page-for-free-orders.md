---
title: "Order confirmation page for free orders - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Order confirmation page for free orders PrestaShop module by MyPresta.eu."
sidebar:
  label: "Order confirmation page for free orders - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Order confirmation page for free orders Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/order-confirmation-page-for-free-orders.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/order-confirmation-page-for-free-orders/)
>
> ---


# Order confirmation page for free orders

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and are sufficient for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Order confirmation page for free orders)

This is the main and only configuration screen for the module. It’s straightforward and allows you to enable or disable the module’s core functionality.

![Module Configuration Screenshot Placeholder]

- **Turn on order confirmation page**
  - **What this setting does:** This is the main switch to activate or deactivate the module’s functionality. It controls whether free orders display the standard confirmation page or revert to PrestaShop’s default behavior (redirecting to order history).
  - **Effect of changing this setting:**
    - *When enabled (selected “Enabled”):* All orders, including those with a €0.00 total, will display the standard “Order Confirmation” page after checkout.
    - *When disabled (selected “Disabled”):* Free orders will revert to PrestaShop’s default behavior, redirecting customers directly to their order history page instead of showing the confirmation page.
  - **Recommended value:** **Enabled**. This is the primary purpose of the module and provides a better customer experience.
  - **Merchant scenario / example:** If you offer a free e-book download, enabling this ensures customers see a confirmation page with a download link, rather than being confused by a direct redirect to their order history. If you temporarily want to revert to the default PrestaShop behavior for free orders (e.g., for specific testing), you can disable it.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Turn on order confirmation page | Enabled | Controls whether free orders display the standard order confirmation page (Enabled) or redirect to order history (Disabled). |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My free orders are still redirecting to the order history page, even after enabling the module. What should I do?**
A:

1. **Check Module Status:** Go to **Modules > Module Manager** and ensure “Order confirmation page for free orders” is installed and enabled.
2. **Check Module Configuration:** Go to **Modules > Module Manager > Configure** for this module and ensure the “Turn on order confirmation page” setting is set to **“Enabled”**.
3. **Clear PrestaShop Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” in the top right corner. This is often necessary after module configuration changes.
4. **Browser Cache:** Try clearing your browser’s cache or testing in an incognito/private browsing window to rule out local caching issues.

**Q: Will this module affect my paid orders?**
A: No, this module specifically targets the behavior of orders with a €0.00 total. Paid orders will continue to display the standard order confirmation page as they always have.

**Q: Does this module require any special theme modifications?**
A: No, the module works by overriding a core PrestaShop controller. It leverages your existing theme’s order confirmation page template. No theme modifications are required. If your order confirmation page looks good for paid orders, it will look good for free orders too.

**Q: What if I want to show different content on the confirmation page for free orders versus paid orders?**
A: This module ensures the *same* confirmation page is displayed. To show different content, you would need to customize your `order-confirmation.tpl` template (usually found in `themes/your-theme/templates/checkout/`) to include conditional logic based on the order total or payment method. This would require developer assistance.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Order confirmation page for free orders” module achieves its functionality by overriding a core PrestaShop front controller. Specifically, it targets `OrderConfirmationController` to modify the redirection logic that occurs after a free order is placed. This is a standard PrestaShop override mechanism, ensuring minimal impact on core files and allowing for easy uninstallation.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:
  - `freeorderconfirmation/override/controllers/front/index.php`
    - This file is a placeholder or an artifact of the override process. In PrestaShop 1.7+, overrides are typically handled by placing the overridden class directly in the `override/classes` or `override/controllers` directory, and PrestaShop’s autoloader handles the rest. This `index.php` file itself does not contain a class definition or direct logic for the module’s functionality. Its presence ensures the override mechanism is correctly triggered for the `OrderConfirmationController`.
  - `freeorderconfirmation/override/controllers/front/OrderConfirmationController.php`
    - **Class name & parent class**: `OrderConfirmationController` (overrides the core `OrderConfirmationController` class).
    - **Responsibility**: This is the core of the module’s functionality. It overrides the `initContent()` method (or similar logic within the controller’s lifecycle) of the original `OrderConfirmationController`. The original PrestaShop logic checks if the order total is zero and, if so, redirects the customer to their order history. This overridden controller removes or modifies that conditional redirection, ensuring that the standard `OrderConfirmationController`’s `initContent()` method (which renders the confirmation page) is always executed, even for free orders. It effectively prevents the `Tools::redirect()` call for zero-value orders.

### 4.3 Core Classes & Models (`classes/`)

No custom classes or `ObjectModel` definitions are present in this module. The module operates purely by overriding a core PrestaShop controller.

### 4.4 JavaScript Assets (`views/js/`)

No custom JavaScript files are included with this module.

### 4.5 CSS Stylesheets (`views/css/`)

No custom CSS files are included with this module. The module relies on the existing theme’s styling for the order confirmation page.

### 4.6 Smarty Template Structure (`views/templates/`)

No custom Smarty template files are included with this module. The module ensures that the *standard* PrestaShop order confirmation template (typically `themes/your-theme/templates/checkout/order-confirmation.tpl`) is rendered for free orders, just as it is for paid orders.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create any custom SQL tables.
  - It stores its configuration settings (e.g., `freeorderconfirmation_oc`) in the `ps_configuration` table.
  - It also stores `mypresta_updates`, `update_`, `updatev_` for internal update tracking by MyPresta.eu.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Executed when an Admin Controller sets its media (CSS/JS). | Used by the module to potentially include its own assets for the back-office configuration page. In this module’s case, it’s likely used to ensure the module’s configuration form is correctly rendered within the PrestaShop admin interface, even if no custom assets are explicitly loaded. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and technical support, please refer to your customer account at MyPresta.eu. Our team is available to assist with any issues or questions regarding the “Order confirmation page for free orders” module.
