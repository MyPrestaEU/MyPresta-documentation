---
title: "Pay By Phone Pro - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Pay By Phone Pro PrestaShop module by MyPresta.eu."
sidebar:
  label: "Pay By Phone Pro - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Pay By Phone Pro Module on MyPresta.eu](https://mypresta.eu/modules/payment-process/pay-by-phone-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/payment/pay-by-phone-pro/)
>
> ---


# Pay By Phone Pro

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself, and this module has no additional specific requirements beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Pay By Phone Pro)

This is the main configuration screen where you define how the “Pay By Phone Pro” payment method appears and behaves in your store.

- **Menu Location:** Back Office > Modules > Module Manager > Search for “Pay By Phone Pro” > Click “Configure”.

#### Settings & Options

1. **Payment Method Title**

   - **What this setting does:** This is the name of the payment method that your customers will see during checkout. It’s what appears in the list of payment options.
   - **Effect of changing this setting:**
     - *When set to “Pay by Phone”:* Customers will see “Pay by Phone” as an option.
     - *When set to “Call Us to Pay”:* Customers will see “Call Us to Pay” as an option.
   - **Recommended value:** Something clear and professional, like “Pay by Phone” or “Call to Complete Order”.
   - **Merchant scenario / example:** If you want to emphasize direct contact, you might use “Call Our Sales Team to Pay”. If you want it to sound more like a standard payment option, “Pay by Phone” is better.
2. **Payment Method Description**

   - **What this setting does:** This is a short description that appears under the payment method title during checkout. It explains to the customer what this payment method entails.
   - **Effect of changing this setting:**
     - *When set to “Call us to provide your credit card details and finalize your order.”:* This text will appear, guiding the customer on the next steps.
     - *When set to “Contact our customer service to discuss payment options.”:* This alternative text will be displayed.
   - **Recommended value:** Clearly state what the customer needs to do, e.g., “Please call us at [Your Phone Number] to finalize your payment and order details.”
   - **Merchant scenario / example:** You could write, “After placing your order, please call us at +1-800-123-4567 during business hours to complete your payment. Have your order number ready.”
3. **Instructions for Customer on Order Confirmation Page**

   - **What this setting does:** This is a more detailed message displayed to the customer on the order confirmation page *after* they have selected “Pay By Phone Pro” and placed their order. This is where you provide specific instructions.
   - **Effect of changing this setting:**
     - *When set to “Thank you for your order. Please call us to finalize your payment.”:* This message will be shown.
     - *When set to “Your order is pending. Kindly contact our support team with your order number to arrange payment.”:* This alternative message will be displayed.
   - **Recommended value:** Include your phone number, business hours, and what information the customer should have ready (e.g., order number).
   - **Merchant scenario / example:** “Your order #12345 has been placed. Please call our sales team at +1-800-123-4567 (Mon-Fri, 9 AM - 5 PM EST) within 24 hours to provide payment details. Please have your order number ready.”
4. **Order Status for Pending Payments**

   - **What this setting does:** This determines the initial status of an order placed using “Pay By Phone Pro” in your PrestaShop Back Office. This status indicates that the payment is not yet complete and requires your action.
   - **Effect of changing this setting:**
     - *When set to “Awaiting bank wire payment”:* Orders will appear with this status.
     - *When set to “Payment accepted”:* (Not recommended for this module) This would incorrectly mark the order as paid before you’ve processed it.
   - **Recommended value:** Choose a status that clearly indicates “payment pending” or “awaiting payment”. Common choices are “Awaiting bank wire payment”, “Payment pending”, or “Awaiting check payment”. If you have a custom order status like “Awaiting Phone Payment”, that would be ideal.
   - **Merchant scenario / example:** Selecting “Awaiting bank wire payment” ensures that these orders are easily identifiable in your order list as needing manual payment processing.
5. **Enable for Specific Countries**

   - **What this setting does:** Allows you to restrict this payment method to customers from certain countries only. If left empty, it will be available to all countries.
   - **Effect of changing this setting:**
     - *When specific countries are selected (e.g., “United States”, “Canada”):* Only customers with a billing address in these countries will see “Pay By Phone Pro” as an option.
     - *When no countries are selected:* The payment method is available globally.
   - **Recommended value:** Leave empty if you want to offer it worldwide, or select specific countries if you have operational limitations (e.g., only have phone support in certain regions).
   - **Merchant scenario / example:** If your phone support is only available in English and you only ship to the US and Canada, you would select “United States” and “Canada” to avoid offering it to customers you cannot serve.
6. **Enable for Specific Currencies**

   - **What this setting does:** Allows you to restrict this payment method to customers paying in specific currencies. If left empty, it will be available for all currencies.
   - **Effect of changing this setting:**
     - *When specific currencies are selected (e.g., “USD”, “EUR”):* Only customers paying in these currencies will see “Pay By Phone Pro”.
     - *When no currencies are selected:* The payment method is available for all currencies configured in your store.
   - **Recommended value:** Leave empty if you support all currencies, or select specific ones if your manual payment processing system has currency limitations.
   - **Merchant scenario / example:** If your credit card terminal only processes USD and EUR, you would select these two currencies.
7. **Enable for Specific Customer Groups**

   - **What this setting does:** Allows you to restrict this payment method to certain customer groups (e.g., “Guests”, “Customers”, “Wholesalers”). If left empty, it will be available to all customer groups.
   - **Effect of changing this setting:**
     - *When specific groups are selected (e.g., “Wholesalers”):* Only customers belonging to the “Wholesalers” group will see this payment option.
     - *When no groups are selected:* The payment method is available to all customer groups.
   - **Recommended value:** Leave empty for general use, or select specific groups if this payment method is part of a special arrangement (e.g., for VIPs or B2B clients).
   - **Merchant scenario / example:** You might offer this only to your “Wholesale” customer group, as they often have custom payment terms that require direct discussion.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Payment Method Title | “Pay by Phone” | Name displayed to customers during checkout. |
| Module Configuration | Payment Method Description | “Call us to provide your credit card details and finalize your order.” | Short explanation under the payment title. |
| Module Configuration | Instructions for Customer on Order Confirmation Page | “Thank you for your order. Please call us to finalize your payment.” | Detailed instructions on the order confirmation page. |
| Module Configuration | Order Status for Pending Payments | “Awaiting bank wire payment” (or similar pending status) | Initial status of orders placed with this method. |
| Module Configuration | Enable for Specific Countries | Empty (All Countries) | Restrict payment method by customer’s country. |
| Module Configuration | Enable for Specific Currencies | Empty (All Currencies) | Restrict payment method by selected currency. |
| Module Configuration | Enable for Specific Customer Groups | Empty (All Groups) | Restrict payment method by customer group. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The “Pay By Phone Pro” option isn’t showing up during checkout.**
A:

- **Check Module Status:** Go to **Modules > Module Manager** and ensure “Pay By Phone Pro” is installed and enabled.
- **Configuration Settings:** Review the “Enable for Specific Countries,” “Enable for Specific Currencies,” and “Enable for Specific Customer Groups” settings. If you’ve restricted the module, ensure the current test customer/cart meets those criteria.
- **Cache:** Clear your PrestaShop cache under **Advanced Parameters > Performance**. Sometimes, old cache prevents new modules or settings from appearing.
- **Theme Compatibility:** While rare, a highly customized theme might interfere. Temporarily switch to a default PrestaShop theme (e.g., Classic) to rule out theme conflicts.

**Q2: How do I change the text that customers see for this payment method?**
A: All customer-facing text (title, description, and confirmation instructions) can be customized directly from the module’s configuration page in your Back Office. Navigate to **Modules > Module Manager**, find “Pay By Phone Pro”, and click “Configure”. You’ll find fields like “Payment Method Title”, “Payment Method Description”, and “Instructions for Customer on Order Confirmation Page”. Remember to save your changes.

**Q3: What happens if a customer places an order using “Pay By Phone Pro” but never calls?**
A: The order will remain in the “pending payment” status you configured (e.g., “Awaiting bank wire payment”). You will need to monitor these orders in your Back Office. You can set up automated reminders or manually contact the customer after a certain period (e.g., 24-48 hours) to follow up. If no contact is made, you may eventually need to cancel the order.

**Q4: Can I translate the module’s text into other languages?**
A: Yes, PrestaShop’s translation system handles module texts. Go to **International > Translations**, select “Installed modules translations”, choose your theme, and then select “Pay By Phone Pro”. You can then translate all configurable text fields into your store’s active languages.

**Q5: How do I process the payment once a customer calls?**
A: This module does not process payments itself. It facilitates the order placement. Once a customer calls, you will use your existing offline payment processing methods (e.g., a physical credit card terminal, a virtual terminal provided by your bank, or recording a bank transfer) to take their payment details and complete the transaction. After successful payment, you must manually update the order status in your PrestaShop Back Office from “pending payment” to “Payment accepted” (or “Processing in progress”) to reflect the change.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview of the “Pay By Phone Pro” module for developers and webmasters.

### 4.1 Architecture Overview

The “Pay By Phone Pro” module follows a standard PrestaShop module architecture, primarily leveraging `PaymentModule` for its core functionality. It integrates into the checkout flow by registering hooks and providing front controllers for payment execution and validation. Configuration is handled via the main module class’s `getContent()` method.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

These controllers handle the customer-facing aspects of the payment process.

- **`controllers/front/index.php`**

  - **Class name & parent class:** `PayByPhoneIndexModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** This controller is typically responsible for displaying the initial payment form or redirecting to the payment execution page. In this module’s context, it likely acts as a gateway before the actual payment execution, potentially setting up session data or redirecting to `payment_execution.tpl`.
- **`controllers/front/validation.php`**

  - **Class name & parent class:** `PayByPhoneValidationModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** This is the critical controller that processes the order after the customer selects “Pay By Phone Pro”. It validates the order, creates it in the PrestaShop database with the configured pending status, and then redirects the customer to the order confirmation page, displaying the specific instructions. It uses the `validateOrder` method from the parent `PaymentModule` class.

#### Back-Office Admin Controllers

This module does not include any custom Back-Office Admin Controllers. All configuration is handled within the main module’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

This module does not contain any custom classes or `ObjectModel` definitions in the `classes/` directory. It relies on PrestaShop’s core `PaymentModule` and `Configuration` classes.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include any custom JavaScript files. Its functionality is primarily server-side and template-driven.

### 4.5 CSS Stylesheets (`views/css/`)

- **`paybyphone/css/paybyphone.css`**
  - **Scope:** Front-office customer styling.
  - **Main UI components and containers it styles:** This stylesheet is likely used to provide basic styling for the payment method’s appearance during checkout, such as the payment option block, description text, or any specific elements within the `payment.tpl` or `shopping-cart.tpl` templates.
  - **Key CSS class selectors developers can override:** Developers can inspect the generated HTML for the payment method on the checkout page to identify specific classes (e.g., `.paybyphone-payment-option`, `.paybyphone-description`) to override in their theme’s `custom.css` or via the theme’s customization options.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

These templates are rendered when specific PrestaShop hooks are executed.

- **`views/templates/hook/infos.tpl`**

  - **Hook:** Likely `displayPaymentTop` or similar, providing additional information about the payment method.
  - **Visual block:** Could be used to display a general informational block about the “Pay By Phone” option, perhaps on the product page or in a column, before the customer reaches checkout.
- **`views/templates/hook/payment.tpl`**

  - **Hook:** `displayPayment` (PrestaShop 1.6) or `paymentOptions` (PrestaShop 1.7+).
  - **Visual block:** This is the primary template for displaying the “Pay By Phone Pro” option on the payment selection page during checkout. It will contain the payment method title and description as configured in the Back Office.

#### Admin templates (`views/templates/admin/`)

This module does not contain any custom admin templates. The configuration form is likely generated directly within `index.php`’s `getContent()` method using PrestaShop’s `HelperForm`.

#### Front-office templates (`views/templates/front/`)

These templates are rendered by the module’s front controllers.

- **`views/templates/front/payment_execution.tpl`**

  - **Purpose:** This template is likely rendered by `PayByPhoneIndexModuleFrontController` or directly after the customer selects the payment method. It might serve as an intermediate page or a confirmation step before the final validation, potentially displaying a “Confirm Order” button.
- **`views/templates/front/shopping-cart.tpl`**

  - **Purpose:** This template is likely a fallback or an alternative display for the payment option within the shopping cart summary, possibly for older PrestaShop versions or specific theme integrations. It would present the “Pay By Phone” option before the full checkout process begins.
- **`views/templates/front/validation.tpl`**

  - **Purpose:** This is the order confirmation page template, rendered after `PayByPhoneValidationModuleFrontController` successfully validates and creates the order. It displays the “Instructions for Customer on Order Confirmation Page” text, along with a summary of the order.

### 4.7 Database Schema & Hooks Map

#### Database Tables

The “Pay By Phone Pro” module does not create any custom database tables. It stores its configuration settings in PrestaShop’s `ps_configuration` table using keys such as `PAYBYPHONE_TITLE`, `PAYBYPHONE_DESCRIPTION`, `PAYBYPHONE_INSTRUCTIONS`, `PAYBYPHONE_ORDER_STATUS`, `PAYBYPHONE_COUNTRIES`, `PAYBYPHONE_CURRENCIES`, and `PAYBYPHONE_GROUPS`.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayPayment` (PrestaShop 1.6) | On the payment selection page during checkout. | Displays the “Pay By Phone Pro” payment option. |
| `paymentOptions` (PrestaShop 1.7+) | On the payment selection page during checkout. | Displays the “Pay By Phone Pro” payment option (modern hook). |
| `displayPaymentReturn` | On the order confirmation page after payment. | Displays the specific instructions for the customer to call. |
| `displayHeader` | In the `<head>` section of every front-office page. | Potentially used to load CSS files (`paybyphone.css`). |
| `displayLeftColumn` / `displayRightColumn` / `displayFooter` | In the respective column/footer areas. | Could be used to display informational blocks about the payment method (via `infos.tpl`). |
| `actionValidateOrder` | After an order has been successfully validated and created. | Allows the module to perform additional actions or logging post-order creation (e.g., setting specific order details). |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the “Pay By Phone Pro” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to ensuring the smooth operation and continued compatibility of our modules with the latest PrestaShop versions.
