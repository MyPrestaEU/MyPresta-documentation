---
title: "Ship to pay + virtual products support - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Ship to pay + virtual products support PrestaShop module by MyPresta.eu."
sidebar:
  label: "Ship to pay + virtual products support - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Ship to pay + virtual products support Module on MyPresta.eu](https://mypresta.eu/modules/payment-process/ship-to-pay-virtual-products-support.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/payment/ship-to-pay-virtual-products-support/)
>
> ---


# Ship to pay + virtual products support

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required by PrestaShop itself and are usually present on any compatible hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Ship to pay + virtual products support” module. You will be presented with a single, comprehensive configuration screen.

This screen displays a matrix (a grid) where you can link your available shipping carriers with your installed payment modules.

**Understanding the Configuration Grid:**

- **Rows (Carriers):** Each row represents a shipping carrier you have configured in your PrestaShop store (e.g., “My Carrier,” “PrestaShop default carrier,” “DHL,” “UPS,” etc.).
- **Columns (Payment Modules):** Each column represents a payment module you have installed and enabled in your PrestaShop store (e.g., “Bank wire,” “Cash on delivery,” “PayPal,” “Stripe,” etc.).
- **Checkboxes:** At the intersection of each carrier row and payment module column, there is a checkbox.

**How to Configure:**

1. **Identify your Carriers:** Look at the left-hand column to see all your active shipping carriers.
2. **Identify your Payment Methods:** Look at the top row to see all your active payment modules.
3. **Link Them Up:** For each carrier, go across its row and **check the box** for every payment method you want to allow for that specific carrier.
   - *What this setting does:* This checkbox determines if a particular payment method will be offered to the customer when they select the corresponding shipping carrier during checkout.
   - *Effect of changing this setting:*
     - **When checked:** The payment method will be visible and selectable by the customer if they choose this carrier.
     - **When unchecked:** The payment method will be hidden and unavailable to the customer if they choose this carrier.
   - *Recommended value:* Check only the combinations that make sense for your business logic.
   - *Merchant scenario / example:* If “DHL Express” is a fast, premium service, you might only check “PayPal” and “Credit Card (Stripe)” for it, and uncheck “Bank wire” to ensure quick payment for quick delivery.

**Special Row: “Virtual products”**

This module includes a unique feature for virtual products. You will see a dedicated row labeled **“Virtual products”** (or similar, depending on your PrestaShop version and language).

- **What this setting does:** This row allows you to specify which payment methods are available when a customer’s cart contains *only* virtual products. Since virtual products don’t have a traditional shipping method, this row acts as their “carrier” for payment method association.
- *Effect of changing this setting:*
  - **When checked (for a payment method in the “Virtual products” row):** That payment method will be available if the customer’s cart consists solely of virtual products.
  - **When unchecked:** That payment method will not be available for carts containing only virtual products.
- *Recommended value:* Check the payment methods that are suitable for immediate digital delivery, typically online payment gateways like PayPal, Stripe, or credit card modules.
- *Merchant scenario / example:* If you sell e-books, you would likely check “PayPal” and “Credit Card (Stripe)” in the “Virtual products” row, but uncheck “Cash on delivery” or “Bank wire” as these are unsuitable for instant digital delivery.

**Saving Your Configuration:**

- After making all your selections, remember to click the **“Save”** button (usually at the bottom of the page) to apply your changes.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Checkbox for Carrier X / Payment Y | Unchecked by default | **Purpose:** Links a specific payment method to a specific shipping carrier. **Impact:** If checked, the payment method is available when Carrier X is chosen. If unchecked, it’s hidden. |
| Module Configuration Page | Checkbox for “Virtual products” / Payment Y | Unchecked by default | **Purpose:** Links a specific payment method to carts containing only virtual products. **Impact:** If checked, the payment method is available for virtual product-only carts. If unchecked, it’s hidden. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve configured the module, but the payment methods aren’t changing in checkout. What’s wrong?**
A1:

- **Clear Cache:** The most common issue. Go to **Advanced Parameters > Performance** in your PrestaShop Back Office and click “Clear cache” (or “Clear Smarty cache” in older versions).
- **Module Enabled:** Ensure the “Ship to pay + virtual products support” module is actually enabled in **Modules > Module Manager**.
- **Payment Modules Enabled:** Make sure the payment modules you are trying to link are also enabled and configured correctly in your store.
- **Theme Compatibility:** While rare, some heavily customized themes might interfere. If clearing cache doesn’t work, try switching to the default PrestaShop theme temporarily to see if the issue persists. If it resolves, your theme might need adjustment.

**Q2: Why are some payment methods still showing even if I unchecked them for a carrier?**
A2:

- **Multiple Carriers in Cart:** If a customer has products in their cart that would use different carriers (e.g., one product shipped by Carrier A, another by Carrier B), PrestaShop’s checkout logic might become complex. This module primarily works when a single shipping method is selected for the entire cart.
- **Virtual Products in Cart:** If the cart contains a mix of physical and virtual products, the module’s logic for virtual products might interact with the carrier-specific logic. Ensure your “Virtual products” row is configured as intended.
- **Other Modules:** Another module might be overriding payment options. Disable other payment-related modules temporarily to check for conflicts.

**Q3: How do I translate the module’s text into other languages?**
A3:

- Go to **International > Translations** in your PrestaShop Back Office.
- Select “Installed modules translations,” choose your theme, and then select the language you want to translate.
- Find the “Ship to pay + virtual products support” module in the list and click “Modify.” You can then edit any translatable strings.

**Q4: I added a new carrier or payment module, but it’s not showing in the configuration grid.**
A4:

- **Refresh Module Configuration:** Sometimes, PrestaShop needs a refresh to pick up new entities. Go to **Modules > Module Manager**, find “Ship to pay + virtual products support,” and click “Configure” again. This should reload the configuration page and display the new carrier/payment module.
- **Ensure Enabled:** Make sure the new carrier or payment module is fully enabled and configured in its respective section of the PrestaShop Back Office.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Ship to pay + virtual products support” module operates by overriding a core PrestaShop class responsible for finding available payment options during checkout. This allows it to inject its custom logic based on selected carriers and the presence of virtual products in the cart, filtering the payment methods presented to the customer. It leverages PrestaShop’s override system and standard configuration storage.

### 4.2 Controllers (`controllers/`)

This module does not introduce any custom front-office or back-office controllers. Its logic is primarily handled through the main module file and an override.

### 4.3 Core Classes & Models (`classes/`)

- **`shiptopay/override/classes/checkout/PaymentOptionsFinder.php`**
  - **Purpose:** This is the core of the module’s functionality. It overrides PrestaShop’s default `PaymentOptionsFinder` class, which is responsible for determining which payment options are available to the customer during checkout.
  - **Parent Class:** `PaymentOptionsFinderCore`
  - **Key Methods & Logic:**
    - The overridden `find()` method (or similar, depending on PrestaShop version) is intercepted.
    - Inside this method, the module retrieves the currently selected carrier ID (from the cart or session) and checks if the cart contains only virtual products.
    - It then queries the module’s configuration (stored in `ps_configuration`) to determine which payment modules are allowed for the selected carrier or for virtual products.
    - The original list of payment options returned by `PaymentOptionsFinderCore` is then filtered, removing any payment methods that are not allowed according to the module’s configuration.
    - This ensures that only permitted payment methods are displayed to the customer.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include any custom JavaScript files. The dynamic updating of payment options is handled by PrestaShop’s core checkout JavaScript, which reacts to changes in shipping method selection and re-renders the payment section based on the filtered options provided by the overridden `PaymentOptionsFinder`.

### 4.5 CSS Stylesheets (`views/css/`)

This module does not include any custom CSS files. It integrates seamlessly with the existing PrestaShop theme styling for payment options.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`shiptopay/views/shiptopay.tpl`**
  - **Purpose:** This template is likely used for rendering the module’s configuration form in the PrestaShop Back Office. It constructs the HTML matrix (grid) of carriers and payment methods with checkboxes, allowing the merchant to link them.
  - **Scope:** Admin template.
  - **Variables:** It would typically iterate over `$carriers` and `$payment_modules` arrays, using `Configuration::get()` to retrieve the saved settings for each checkbox.

### 4.7 Database Schema & Hooks Map

- **Database Tables:**

  - The module does not create any custom SQL tables.
  - Configuration settings (the links between carriers/virtual products and payment methods) are stored in the `ps_configuration` table. Each setting would typically be stored as a key-value pair, where the key might be `SHIP_TO_PAY_CARRIER_X_PAYMENT_Y` and the value `1` (enabled) or `0` (disabled). The “Virtual products” settings would follow a similar naming convention.
- **Registered Hooks Table:**

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `displayHeader` | In the `<head>` section of every page. | While listed as a potential front-office hook, this module primarily uses an override and does not typically render visible content via `displayHeader`. It might be used for internal module initialization or asset loading if any were present. |
  | `displayRightColumn` | In the right column of pages (if enabled by theme). | Not directly used for the module’s core functionality, as its impact is on checkout payment options. |
  | `displayLeftColumn` | In the left column of pages (if enabled by theme). | Not directly used for the module’s core functionality, as its impact is on checkout payment options. |
  | `displayFooter` | In the footer section of every page. | Not directly used for the module’s core functionality, as its impact is on checkout payment options. |
  | `displayModuleConfigureExtraButtons` | In the module manager, next to the configure button. | Not explicitly used for core functionality, but could be used for additional admin actions. |
  | `actionPaymentOptionsModifier` | (Implicit/Internal) | This module primarily works by overriding `PaymentOptionsFinder`, which is called internally during the checkout process to generate the list of payment options. While not a traditional `hookDisplay` or `action` hook, the override acts as an interception point. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Ship to pay + virtual products support” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist you with any technical issues or questions regarding the module’s functionality.
