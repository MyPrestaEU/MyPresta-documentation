---
title: "Bank wire with order summary - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Bank wire with order summary PrestaShop module by MyPresta.eu."
sidebar:
  label: "Bank wire with order summary - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Bank wire with order summary Module on MyPresta.eu](https://mypresta.eu/modules/payment-process/bank-wire-with-order-summary.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/payment/bank-wire-with-order-summary/)
>
> ---


# Bank wire with order summary

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required by PrestaShop itself and are usually available on most hosting environments. No specific unusual extensions are needed for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen where you define your bank account details and how the bank wire payment method behaves in your store.

#### **Bank Wire Account Settings**

This section allows you to define multiple bank account profiles. Each profile can have its own details and can be activated or deactivated independently. This is useful if you have different bank accounts for different currencies, countries, or even different brands.

- **Profile name:**

  - **What this setting does:** This is an internal name for your bank account profile, helping you identify it in the back office. It’s not visible to customers.
  - **Effect of changing this setting:** Changing this only affects how you see the profile in the admin panel.
  - **Recommended value:** A descriptive name, e.g., “Main Euro Account”, “USD Account for US Orders”.
  - **Merchant scenario / example:** If you have a bank account in Germany for EUR payments and another in the USA for USD payments, you would create two profiles, naming them accordingly.
- **Active:**

  - **What this setting does:** Controls whether this specific bank account profile is available as a payment option for customers.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* This bank account profile will be offered to customers if it meets all other eligibility criteria (currency, country, etc.).
    - *When disabled (No):* This profile will not be shown as a payment option, regardless of other settings.
  - **Recommended value:** “Yes” for active accounts, “No” for inactive or temporary accounts.
  - **Merchant scenario / example:** You might disable a profile if a bank account is temporarily unavailable or if you’re phasing out a particular currency.
- **Priority:**

  - **What this setting does:** If multiple bank wire profiles are active and eligible for a customer’s order, this number determines which one is displayed first or preferred. Lower numbers mean higher priority.
  - **Effect of changing this setting:** Influences the order in which eligible bank wire options are presented to the customer.
  - **Recommended value:** Use sequential numbers (e.g., 1, 2, 3) to order your preferences.
  - **Merchant scenario / example:** If you prefer customers to use your main EUR account over a secondary one, give the main account a lower priority number (e.g., 1) than the secondary one (e.g., 2).
- **Currency:**

  - **What this setting does:** Specifies which currency this bank account profile is set up to receive payments in.
  - **Effect of changing this setting:** This profile will only be offered to customers whose order total is in the selected currency.
  - **Recommended value:** Select the primary currency for this bank account.
  - **Merchant scenario / example:** If you have a bank account that only accepts EUR, select “Euro”. If a customer places an order in USD, this profile won’t be shown.
- **Eligible countries:**

  - **What this setting does:** Determines which countries this bank account profile is available for. You can select multiple countries.
  - **Effect of changing this setting:** This profile will only be offered to customers whose billing address is in one of the selected countries.
  - **Recommended value:** Select all countries from which you are willing to accept bank transfers to this specific account.
  - **Merchant scenario / example:** If your German bank account is only for customers in Germany and Austria, select “Germany” and “Austria”.
- **Eligible zones:**

  - **What this setting does:** Determines which geographical zones this bank account profile is available for. You can select multiple zones.
  - **Effect of changing this setting:** Similar to countries, this profile will only be offered to customers whose billing address is in one of the selected zones.
  - **Recommended value:** Select the zones relevant to this bank account.
  - **Merchant scenario / example:** If you have a bank account specifically for European customers, you might select the “Europe” zone.
- **Eligible customer groups:**

  - **What this setting does:** Restricts this payment option to specific customer groups (e.g., “Visitors”, “Guests”, “Customers”, “Wholesalers”).
  - **Effect of changing this setting:** Only customers belonging to the selected groups will see this bank wire option.
  - **Recommended value:** Typically “Customers” and “Guests”, but can be customized for B2B.
  - **Merchant scenario / example:** You might only want to offer bank wire to your “Wholesalers” group for large B2B orders, and not to regular retail customers.
- **Account holder:**

  - **What this setting does:** The full name of the account holder (your company name or personal name) as it appears on the bank account.
  - **Effect of changing this setting:** This information is displayed to the customer on the payment confirmation page, so they know who to transfer money to.
  - **Recommended value:** Your exact legal company name or personal name.
  - **Merchant scenario / example:** “MyPresta.eu Sp. z o.o.”
- **IBAN:**

  - **What this setting does:** Your International Bank Account Number. This is a standardized international bank account identifier.
  - **Effect of changing this setting:** This is crucial information displayed to the customer for making the bank transfer.
  - **Recommended value:** Your full and correct IBAN.
  - **Merchant scenario / example:** “DE89370400440532013000”
- **BIC / SWIFT:**

  - **What this setting does:** Your Bank Identifier Code (BIC) or SWIFT code. This identifies your bank globally.
  - **Effect of changing this setting:** This is essential information displayed to the customer for making international bank transfers.
  - **Recommended value:** Your full and correct BIC/SWIFT code.
  - **Merchant scenario / example:** “COBADEFFXXX”
- **Account number / details:**

  - **What this setting does:** Your traditional bank account number or other specific details required by your bank or country, if IBAN/BIC are not sufficient or applicable.
  - **Effect of changing this setting:** This information is displayed to the customer.
  - **Recommended value:** Your account number if IBAN is not used, or any other specific details. Leave empty if IBAN/BIC are sufficient.
  - **Merchant scenario / example:** In some countries, a local account number might still be preferred alongside or instead of IBAN.
- **Bank / holder address:**

  - **What this setting does:** The address of your bank or the registered address of the account holder.
  - **Effect of changing this setting:** This information is displayed to the customer, sometimes required for bank transfers.
  - **Recommended value:** The full address of your bank branch or your company’s registered address.
  - **Merchant scenario / example:** “Bank of Example, Main Street 123, 10001 City, Country”
- **Additional instructions:**

  - **What this setting does:** A text field where you can provide extra notes for the customer regarding the bank transfer (e.g., “Please include your order reference number in the transfer description,” “Payments usually take 1-3 business days to clear”).
  - **Effect of changing this setting:** This text will be displayed to the customer on the payment confirmation page.
  - **Recommended value:** Clear, concise instructions to help customers complete the transfer correctly.
  - **Merchant scenario / example:** “Important: Please use your Order ID # [ORDER\_ID] as the payment reference to ensure quick processing.”

#### **Cart Total Restrictions**

These settings allow you to control the minimum and maximum order values for which the bank wire payment option is available.

- **Minimum cart total:**

  - **What this setting does:** Enables or disables the minimum cart total restriction for this payment method.
  - **Effect of changing this setting:**
    - *When enabled:* The “Minimum cart total value” field becomes active, and bank wire will only be available for orders above that value.
    - *When disabled:* No minimum cart total restriction is applied.
  - **Recommended value:** “Enabled” if you want to set a minimum, “Disabled” otherwise.
  - **Merchant scenario / example:** You might enable this if bank transfers are more cost-effective for larger orders, or to discourage bank transfers for very small purchases.
- **Minimum cart total value:**

  - **What this setting does:** The actual monetary value that the customer’s cart must exceed for the bank wire option to appear.
  - **Effect of changing this setting:** If the customer’s cart total is below this value, the bank wire option will not be shown.
  - **Recommended value:** A reasonable minimum, e.g., “50.00”.
  - **Merchant scenario / example:** Set to “50.00” if you only want to offer bank wire for orders of €50 or more.
- **Maximum cart total:**

  - **What this setting does:** Enables or disables the maximum cart total restriction for this payment method.
  - **Effect of changing this setting:**
    - *When enabled:* The “Maximum cart total value” field becomes active, and bank wire will only be available for orders below that value.
    - *When disabled:* No maximum cart total restriction is applied.
  - **Recommended value:** “Enabled” if you want to set a maximum, “Disabled” otherwise.
  - **Merchant scenario / example:** You might enable this if you prefer other payment methods (like direct negotiation or custom invoicing) for extremely large orders.
- **Maximum cart total value:**

  - **What this setting does:** The actual monetary value that the customer’s cart must be below for the bank wire option to appear.
  - **Effect of changing this setting:** If the customer’s cart total is above this value, the bank wire option will not be shown.
  - **Recommended value:** A reasonable maximum, e.g., “5000.00”.
  - **Merchant scenario / example:** Set to “5000.00” if you don’t want to accept bank wire for orders exceeding €5000.

#### **Order Summary Display**

These settings control what information is shown to the customer on the payment confirmation page before they finalize their order. This is crucial for legal compliance.

- **Order summary before confirmation:**

  - **What this setting does:** Controls whether a detailed order summary is displayed to the customer on the payment confirmation page.
  - **Effect of changing this setting:**
    - *When enabled:* A summary of products, prices, and totals will be shown.
    - *When disabled:* The detailed summary will not be shown, potentially impacting legal compliance in some regions.
  - **Recommended value:** “Enabled” to ensure legal compliance and customer clarity.
  - **Merchant scenario / example:** Always keep this enabled to provide full transparency to your customers before they commit to the purchase.
- **Display customer summary before confirmation:**

  - **What this setting does:** Controls whether the customer’s billing and shipping address summary is displayed on the payment confirmation page.
  - **Effect of changing this setting:**
    - *When enabled:* The customer’s address details will be shown.
    - *When disabled:* Address details will not be shown.
  - **Recommended value:** “Enabled” for full transparency.
  - **Merchant scenario / example:** Enabling this allows customers to double-check their delivery information one last time before placing the order.

#### **Advanced Analytics (Internal)**

These settings are typically for internal module analytics and reporting, not directly impacting the front-office customer experience.

- **BANKWIREPRO\_ANALYTICS\_DEFAULT\_CHART, BANKWIREPRO\_ANALYTICS\_PERIOD, BANKWIREPRO\_ANALYTICS\_CHART\_WEEKS, BANKWIREPRO\_ANALYTICS\_CHART\_MONTHS, BANKWIREPRO\_ANALYTICS\_CHART\_YEARS:**
  - **What these settings do:** These are internal configuration values related to how the module might track or display payment statistics within the PrestaShop back office (if such a feature is implemented). They define default chart types, reporting periods, and timeframes for analytics.
  - **Effect of changing these settings:** These do not affect the customer-facing payment process. They might influence how data is presented in an internal analytics dashboard, if available.
  - **Recommended value:** Leave as default unless specifically instructed by support.
  - **Merchant scenario / example:** Not directly applicable to merchant decision-making for payment processing.

#### **Language Settings (Internal)**

- **PS\_LANG\_DEFAULT, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG:**

  - **What these settings do:** These are standard PrestaShop configuration variables that determine the default language of your store and whether employees can change the language of back office forms. They are displayed here for reference but are not specific to this module.
  - **Effect of changing these settings:** Changes to these would be made in PrestaShop’s general settings, not here. They influence the default language for text fields in the back office.
  - **Recommended value:** Your store’s default language.
  - **Merchant scenario / example:** If your store’s primary language is English, `PS_LANG_DEFAULT` would be set to the ID of the English language.
- **PS\_CURRENCY\_DEFAULT:**

  - **What this setting does:** This is the default currency of your PrestaShop store. It’s displayed here for reference.
  - **Effect of changing this setting:** This is a global PrestaShop setting. Changing it would affect all prices and currency displays across your store.
  - **Recommended value:** Your store’s primary operating currency.
  - **Merchant scenario / example:** If your store primarily trades in Euros, this would be set to “Euro”.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Profile name | Descriptive name | Internal identification of bank account. |
| Module Configuration | Active | Yes | Enables/disables this bank account profile for customer use. |
| Module Configuration | Priority | 1 (or sequential) | Orders display of multiple eligible bank wire options. |
| Module Configuration | Currency | Your store’s currency | Restricts profile to orders in this currency. |
| Module Configuration | Eligible countries | All countries | Restricts profile to customers from selected countries. |
| Module Configuration | Eligible zones | All zones | Restricts profile to customers from selected zones. |
| Module Configuration | Eligible customer groups | All groups | Restricts profile to selected customer groups. |
| Module Configuration | Account holder | Your company/name | Displays to customer for bank transfer. |
| Module Configuration | IBAN | Your IBAN | Displays to customer for bank transfer. |
| Module Configuration | BIC / SWIFT | Your BIC/SWIFT | Displays to customer for international bank transfer. |
| Module Configuration | Account number / details | (Optional) | Additional bank details for customer. |
| Module Configuration | Bank / holder address | Your bank/company address | Displays to customer for bank transfer. |
| Module Configuration | Additional instructions | Clear instructions | Extra notes for customer (e.g., reference number). |
| Module Configuration | Minimum cart total | Disabled | Enables/disables minimum order value restriction. |
| Module Configuration | Minimum cart total value | 0.00 | Minimum order value for bank wire to be available. |
| Module Configuration | Maximum cart total | Disabled | Enables/disables maximum order value restriction. |
| Module Configuration | Maximum cart total value | 0.00 | Maximum order value for bank wire to be available. |
| Module Configuration | Order summary before confirmation | Enabled | Displays detailed product summary on confirmation page. |
| Module Configuration | Display customer summary before confirmation | Enabled | Displays customer address summary on confirmation page. |
| Module Configuration | BANKWIREPRO\_ANALYTICS\_\* | Default | Internal analytics settings (no front-office impact). |
| Module Configuration | PS\_LANG\_DEFAULT | Store default | PrestaShop’s default language setting. |
| Module Configuration | PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG | Store default | PrestaShop’s employee form language setting. |
| Module Configuration | PS\_CURRENCY\_DEFAULT | Store default | PrestaShop’s default currency setting. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: Why isn’t the Bank Wire option showing up for my customers?**
A1: Check the following settings in the module configuration:
\* **“Active”** switch for the bank account profile: Ensure it’s set to “Yes”.
\* **“Currency”**: Does the customer’s order currency match the profile’s currency?
\* **“Eligible countries” / “Eligible zones”**: Is the customer’s billing address country/zone included?
\* **“Eligible customer groups”**: Is the customer’s group allowed to use this payment method?
\* **“Minimum cart total” / “Maximum cart total”**: Does the customer’s cart value fall within the allowed range?
\* **PrestaShop Cache**: Sometimes, clearing the Smarty cache (Advanced Parameters > Performance > Clear cache) can resolve display issues.

**Q2: My bank details are incorrect or outdated. How do I change them?**
A2: Go to **Modules > Module Manager**, find “Bank wire with order summary”, and click “Configure”. You will see your existing bank account profiles. Click the “Edit” button (pencil icon) next to the profile you wish to update, modify the “Account holder”, “IBAN”, “BIC / SWIFT”, etc., fields, and then save your changes.

**Q3: The order summary isn’t showing on the confirmation page. Is something wrong?**
A3: Ensure the “Order summary before confirmation” and “Display customer summary before confirmation” settings are both set to “Enabled” in the module’s configuration. If they are, and you’ve cleared your PrestaShop cache, there might be a theme conflict. Test with the default PrestaShop theme to rule this out.

**Q4: Can I offer different bank accounts for different types of customers or products?**
A4: Yes, absolutely! This module supports multiple bank account profiles. You can create separate profiles and use the “Eligible customer groups”, “Currency”, “Eligible countries”, and “Cart total” settings to define when each specific bank account is offered. For example, one account for retail customers in EUR, another for wholesale customers in USD.

**Q5: After updating my theme or PrestaShop, the bank wire page looks strange. What should I do?**
A5: This often indicates a CSS conflict or a template override issue.
1. **Clear Cache:** Always start by clearing your PrestaShop cache (Advanced Parameters > Performance).
2. **Check Module Updates:** Ensure you have the latest version of the “Bank wire with order summary” module from MyPresta.eu, as updates often include compatibility fixes.
3. **Theme Conflict:** If the issue persists, temporarily switch to the default PrestaShop theme (e.g., “Classic”) to see if the problem disappears. If it does, your custom theme is likely overriding or conflicting with the module’s styling or templates. You may need to consult your theme developer or a webmaster to adjust the theme’s CSS or template files.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The `bankwirepro` module follows the standard PrestaShop module architecture, leveraging `ModuleFrontController` for front-office interactions and the main `Module` class for configuration. It integrates into the checkout flow via payment hooks (`displayPaymentOptions`, `paymentOptions`, `displayPaymentReturn`). Configuration is managed through `Configuration` table entries, and bank account details are stored as serialized arrays or individual `Configuration` keys, allowing for multiple profiles. The module’s primary function is to present bank details and an order summary to the customer before and after order validation.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:
  - `controllers/front/index.php`
    - **Class Name**: `BankwireproIndexModuleFrontController` (extends `ModuleFrontController`)
    - **Responsibility**: This controller likely serves as a default entry point or a fallback. In many modules, `index.php` controllers redirect to a more specific controller or handle basic module display if no other specific action is requested. It might handle initial setup or redirection to the payment selection.
  - `controllers/front/payment.php`
    - **Class Name**: `BankwireproPaymentModuleFrontController` (extends `ModuleFrontController`)
    - **Responsibility**: This controller is responsible for rendering the payment selection page when the bank wire option is chosen. It gathers the necessary bank account details based on the current cart, customer, and currency, and prepares them for display in the `payment.tpl` template. It acts as the bridge between the payment option selection and the final validation step.
  - `controllers/front/validation.php`
    - **Class Name**: `BankwireproValidationModuleFrontController` (extends `ModuleFrontController`)
    - **Responsibility**: This is the critical controller that handles the final step of the bank wire payment process. It validates the order, creates the order in PrestaShop’s database, and then renders the `validation.tpl` template. This template displays the full order summary, customer address summary, and the chosen bank account details, along with additional instructions, before the customer is redirected to the standard `order-confirmation` page. It ensures all necessary information is presented for legal compliance.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes in `classes/`. The core logic for handling bank account profiles and configuration is likely contained within the main `bankwirepro.php` file, using `Configuration::get()` and `Configuration::updateValue()` to store settings, potentially with serialized arrays for multiple bank account profiles.

### 4.4 JavaScript Assets (`views/js/`)

The module dossier indicates no custom JavaScript files. This suggests that the module’s front-office functionality is primarily server-side rendered and relies on standard PrestaShop JavaScript for basic interactions, or that any minimal JS is inlined in templates.

### 4.5 CSS Stylesheets (`views/css/`)

The module dossier indicates no custom CSS files. This implies that the module either relies entirely on the PrestaShop default theme’s styling, or any minimal styling is inlined within the templates. Developers should be aware that the module’s appearance will largely be dictated by the active theme’s CSS.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Admin templates (`views/templates/admin/`)**:

  - `accountSelector.tpl`: This template is likely used in the module’s back-office configuration to display a list of configured bank account profiles, allowing the admin to select, edit, or delete them. It would typically render a table or list with profile names, status, and action buttons.
- **Front-office templates (`views/templates/front/`)**:

  - `validation.tpl`: This is a crucial template rendered by `BankwireproValidationModuleFrontController`. It displays the comprehensive order summary (products, totals), customer address summary, and the selected bank account details (account holder, IBAN, BIC/SWIFT, instructions) to the customer before the order is fully confirmed. This template is key for legal compliance.
- **Hook templates (`views/templates/hook/`)**:

  - `infos.tpl`: This template is likely hooked into `displayPaymentReturn` or a similar hook on the `order-confirmation` page. It reiterates the bank wire payment instructions and bank details after the order has been successfully placed, serving as a reminder for the customer to complete the transfer.
  - `payment.tpl`: This template is likely used for the `displayPayment` hook (PrestaShop 1.6.x) or `paymentOptions` (PrestaShop 1.7+). It renders the bank wire option itself on the payment selection page during checkout, presenting it as an available payment method to the customer.
  - `payment_return.tpl`: Similar to `infos.tpl`, this template is also likely hooked into `displayPaymentReturn`. It provides the final confirmation message and bank details on the order confirmation page, ensuring the customer has all information to proceed with the bank transfer.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create custom SQL tables. All configuration settings, including multiple bank account profiles, are stored in the `ps_configuration` table.
  - Configuration keys used:
    - `BANK_WIRE_PRO_MINCART`, `BANK_WIRE_PRO_MINCART_V`, `BANK_WIRE_PRO_MAXCART`, `BANK_WIRE_PRO_MAXCART_V`: For cart total restrictions.
    - `BANK_WIRE_PRO_OWNER_`, `BANK_WIRE_PRO_DETAILS_`, `BANK_WIRE_PRO_ADDRESS_`, `BANK_WIRE_PRO_SWIFT_`, `BANK_WIRE_PRO_IBAN_`, `BANK_WIRE_PRO_MORE_`: These are likely prefixes for storing details of *each* bank account profile, possibly with a language ID or profile ID suffix (e.g., `BANK_WIRE_PRO_OWNER_1_1` for profile 1, language 1).
    - `BANK_WIRE_PRO_OWNER_SUMMARY`, `BANK_WIRE_PRO_CSUMMARY`, `BANK_WIRE_PRO_ASUMMARY`: For controlling the display of order and address summaries.
    - `BANKWIREPRO_ANALYTICS_*`: Internal analytics settings.
    - Standard PrestaShop keys like `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`, `PS_CURRENCY_DEFAULT` are read but not managed by the module.
- **Registered Hooks Table**:

| Hook Name | Scope | Execution Timing | Technical Purpose |
| --- | --- | --- | --- |
| `displayPayment` | Front-Office | Payment selection step (PrestaShop 1.6.x) | Renders the bank wire payment option on the checkout page. |
| `paymentOptions` | Front-Office | Payment selection step (PrestaShop 1.7.x, 8.x, 9.x) | Provides `PaymentOption` objects for bank wire to the checkout page. |
| `displayPaymentReturn` | Front-Office | Order confirmation page (`order-confirmation`) | Displays bank details and instructions after order validation. |
| `displayPaymentOptions` | Front-Office | Payment selection step (PrestaShop 1.7.x, 8.x, 9.x) | Alternative or supplementary hook for rendering payment options. |
| `actionPaymentConfirmation` | Back-Office | After an order is confirmed as paid | (Implied, common for payment modules) May update order status or perform post-payment actions. |
| `actionValidateOrder` | Back-Office | After an order is validated | (Implied, common for payment modules) Used to set initial order status, save payment details. |

## 5. Official Support & Updates

For official updates, technical support, and to ensure you are running the most secure and compatible version of the “Bank wire with order summary” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions regarding the module’s functionality and integration.
