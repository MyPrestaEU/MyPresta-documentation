---
title: "Perfect Money - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Perfect Money PrestaShop module by MyPresta.eu."
sidebar:
  label: "Perfect Money - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Perfect Money Module on MyPresta.eu](https://mypresta.eu/modules/payment-process/perfect-money.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/payment/perfect-money/)
>
> ---


# Perfect Money

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 1.6.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for secure payment gateway communication, which are almost always available on modern hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Perfect Money)

This is the main configuration screen for the Perfect Money module, where you will enter your Perfect Money account details and set up how the payment method appears and functions in your store.

#### **Perfect Money Account Settings**

- **What this setting does:** These fields are crucial for connecting your PrestaShop store to your Perfect Money merchant account. They tell the module which Perfect Money account to send payments to and how to verify transactions.
- **Effect of changing this setting:** Incorrect values will prevent customers from making payments, or payments might not be correctly attributed to your account.
  - *When correctly configured:* Payments will be processed successfully through your Perfect Money account.
  - *When incorrectly configured:* Payments will fail, or customers will encounter errors during checkout.
- **Recommended value:** Enter the exact details provided by your Perfect Money merchant account.
- **Merchant scenario / example:** You’ve registered a merchant account with Perfect Money. They provide you with a “Perfect Money Account ID” (e.g., U1234567) and a “Perfect Money Account Name” (e.g., MyStorePayments). You also set up a “Perfect Money Alternate Passphrase” within your Perfect Money account settings for enhanced security. You must enter these exact values here.

#### **Payment Display Settings**

- **What this setting does:** This section controls how the Perfect Money payment option is presented to your customers during checkout.
- **Effect of changing this setting:**
  - *When enabled:* Customers will see the Perfect Money option and can choose it for payment.
  - *When disabled:* Perfect Money will not appear as a payment option.
- **Recommended value:** “YES” (Enabled) if you want to offer Perfect Money as a payment method.
- **Merchant scenario / example:** You want to offer Perfect Money as a payment option. You enable it. If you temporarily want to disable it for maintenance or if you no longer wish to accept Perfect Money, you would set it to “NO”.

#### **Order Status Settings**

- **What this setting does:** These settings determine the status an order will have in your PrestaShop back office after a customer completes a payment via Perfect Money.
- **Effect of changing this setting:**
  - *When set to “Payment accepted”:* Orders paid via Perfect Money will automatically be marked as “Payment accepted” in your PrestaShop back office, indicating a successful transaction.
  - *When set to “Payment error”:* If a payment fails or an issue occurs, the order will be marked with this status.
- **Recommended value:**
  - **Order status for a successful payment:** “Payment accepted” (or a similar status you’ve configured for successful payments).
  - **Order status for a payment error:** “Payment error” (or a similar status for failed payments).
- **Merchant scenario / example:** A customer successfully pays with Perfect Money. You want to quickly identify these orders as ready for processing. By setting the “Order status for a successful payment” to “Payment accepted,” your team immediately knows the payment has cleared. If a customer attempts to pay but the transaction fails, the order will be marked “Payment error,” allowing you to follow up or for the customer to try again.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Perfect Money Account ID | Your Perfect Money Account ID (e.g., U1234567) | Identifies your Perfect Money merchant account for receiving payments. **CRITICAL for payment processing.** |
| Module Configuration | Perfect Money Account Name | Your Perfect Money Account Name | The name associated with your Perfect Money account. |
| Module Configuration | Perfect Money Alternate Passphrase | Your Perfect Money Alternate Passphrase | Security key for verifying transactions. Set this in your Perfect Money account. **CRITICAL for security.** |
| Module Configuration | Enable Perfect Money Payment | YES | Toggles the visibility of Perfect Money as a payment option on your checkout page. |
| Module Configuration | Order status for a successful payment | Payment accepted | The PrestaShop order status assigned to orders successfully paid via Perfect Money. |
| Module Configuration | Order status for a payment error | Payment error | The PrestaShop order status assigned to orders where Perfect Money payment failed. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My customers are seeing an error when trying to pay with Perfect Money.**
A:

- **Check your Perfect Money Account Settings:** Double-check that your “Perfect Money Account ID,” “Perfect Money Account Name,” and “Perfect Money Alternate Passphrase” are entered *exactly* as they appear in your Perfect Money merchant account. Even a small typo can cause errors.
- **Verify Perfect Money Account Status:** Log into your Perfect Money account directly to ensure it’s active, in good standing, and configured to receive payments.
- **Review PrestaShop Error Logs:** In your PrestaShop back office, navigate to **Advanced Parameters > Logs** to see if any specific errors related to the Perfect Money module are being recorded.

**Q: Orders are not being marked as “Payment accepted” after a successful Perfect Money payment.**
A:

- **Check Order Status Settings:** Go to the module configuration and ensure that “Order status for a successful payment” is set to the correct status (e.g., “Payment accepted”).
- **Perfect Money IPN/Callback:** Ensure that your Perfect Money account is correctly configured to send Instant Payment Notifications (IPN) or callbacks to your PrestaShop store. The module relies on these notifications to update order statuses. While the module handles the URL, sometimes Perfect Money account settings can interfere.

**Q: Perfect Money is not showing up as a payment option on my checkout page.**
A:

- **Module Enabled:** In the module configuration, ensure “Enable Perfect Money Payment” is set to “YES”.
- **Module Installed:** Verify that the module is correctly installed and enabled in **Modules > Module Manager**.
- **Cache:** Clear your PrestaShop cache (under **Advanced Parameters > Performance**) and your browser cache. Sometimes old cached data can prevent new payment options from appearing.
- **Theme Compatibility:** While the module is designed to be compatible, very heavily customized themes might occasionally require minor adjustments. If you suspect a theme conflict, try switching to the default PrestaShop theme temporarily to see if the option appears.

**Q: Can I customize the Perfect Money logo or text on the checkout page?**
A: The module uses a standard template for displaying the payment option. You can typically customize the text by going to **International > Translations** in your PrestaShop back office, selecting “Installed modules translations,” choosing your theme, and then finding the “Perfect Money” module. For logo changes, you would need to modify the module’s template file (`perfectmoney.tpl`) or use CSS overrides in your theme.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview of the Perfect Money module for developers and webmasters.

### 4.1 Architecture Overview

The Perfect Money module follows the standard PrestaShop module architecture, primarily utilizing a main module class (`PerfectMoney`) for installation, uninstallation, and configuration, and `ModuleFrontController` classes to handle the payment redirection and validation processes. It integrates with the Perfect Money payment gateway using a server-to-server communication model (IPN/callback) to confirm transactions and update order statuses.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

These controllers handle the customer-facing aspects of the payment process, including redirection to Perfect Money and handling the callback after payment.

- **`perfectmoney/controllers/front/index.php`**

  - **Class Name**: `PerfectMoneyIndexModuleFrontController`
  - **Parent Class**: `ModuleFrontController`
  - **Responsibility**: This controller is typically responsible for initiating the payment process. When a customer selects Perfect Money and confirms their order, this controller prepares the payment request parameters (merchant ID, amount, currency, order description, return URLs) and redirects the customer’s browser to the Perfect Money payment gateway. It gathers necessary order details from the cart and constructs the payment form.
- **`perfectmoney/controllers/front/validation.php`**

  - **Class Name**: `PerfectMoneyValidationModuleFrontController`
  - **Parent Class**: `ModuleFrontController`
  - **Responsibility**: This is the crucial controller that handles the callback (Instant Payment Notification - IPN) from Perfect Money after a payment has been processed.
    - It receives POST data from Perfect Money containing transaction details and a security hash.
    - It verifies the integrity and authenticity of the payment notification using the configured Alternate Passphrase.
    - If the payment is valid and successful, it updates the PrestaShop order status (e.g., to “Payment accepted”), creates an order history entry, and potentially sends order confirmation emails.
    - If the payment fails or is invalid, it updates the order status accordingly (e.g., to “Payment error”).
    - It then redirects the customer back to the appropriate PrestaShop page (e.g., order confirmation or error page).

### 4.3 Core Classes & Models (`classes/`)

The module does not appear to define any custom classes extending `ObjectModel` or other core PrestaShop classes in a dedicated `classes/` directory. All core logic is likely encapsulated within the main `PerfectMoney` module class (`index.php`) and the front controllers.

### 4.4 JavaScript Assets (`views/js/`)

No custom JavaScript files were detected in the module archive. The payment process is primarily handled by server-side redirects and Perfect Money’s own payment interface.

### 4.5 CSS Stylesheets (`views/css/`)

No custom CSS files were detected in the module archive. The styling for the payment option on the checkout page is likely inherited from the PrestaShop theme or inline styles within the template.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`perfectmoney/views/admin.tpl`**

  - **Scope**: Back-office admin configuration.
  - **Purpose**: This template is used to render the module’s configuration form within the PrestaShop back office. It displays the input fields for Perfect Money Account ID, Account Name, Alternate Passphrase, and the order status selection dropdowns. It uses standard PrestaShop form helpers and styling.
- **`perfectmoney/views/perfectmoney.tpl`**

  - **Scope**: Front-office (checkout payment step).
  - **Purpose**: This template is responsible for displaying the Perfect Money payment option to the customer on the checkout page. It typically includes the payment method title, description, and potentially the Perfect Money logo. It’s rendered within a payment hook (e.g., `displayPaymentOptions` in PS 1.7+ or `displayPayment` in PS 1.6).
- **`perfectmoney/views/success_page.tpl`**

  - **Scope**: Front-office (order confirmation/success page).
  - **Purpose**: This template is likely used to display a custom success message or additional information to the customer after a successful Perfect Money payment, before or as part of the standard order confirmation page. It might be rendered by the `validation.php` controller.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not appear to create any custom SQL tables.
  - Configuration settings (Perfect Money Account ID, Passphrase, etc.) are stored in the `ps_configuration` table, using keys prefixed with `PERFECTMONEY_`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayPaymentOptions` (PS 1.7+) | On the checkout page, payment step. | Renders the Perfect Money payment option using `perfectmoney.tpl`. |
| `displayPayment` (PS 1.6) | On the checkout page, payment step. | Renders the Perfect Money payment option using `perfectmoney.tpl`. |
| `displayHeader` | In the `<head>` section of every front-office page. | Potentially used for loading module-specific assets (JS/CSS) if any were present, or for meta tags. (No assets detected, so likely for module initialization or compatibility). |
| `actionPaymentConfirmation` | After an order’s payment status is confirmed. | Could be used for post-payment processing, though the primary status update is handled by the `validation.php` controller. |
| `actionValidateOrder` | After an order has been successfully validated and created. | Used by the module to create the order in PrestaShop with the initial status before redirection to Perfect Money. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the Perfect Money module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and integration.
