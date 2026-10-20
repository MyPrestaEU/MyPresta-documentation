---
title: "Voucher code after registration - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Voucher code after registration PrestaShop module by MyPresta.eu."
sidebar:
  label: "Voucher code after registration - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Voucher code after registration Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/voucher-code-after-registration.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/voucher-code-after-registration/)
>
> ---


# Voucher code after registration

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient and usually pre-installed on most web hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click the “Configure” button next to the “Voucher code after registration” module. This will take you to the main configuration screen where you can define how your new customer vouchers will work.

The configuration page will present you with options to define the characteristics of the voucher that new customers will receive. These settings directly correspond to the standard PrestaShop “Cart Rule” (voucher) features.

Here are the typical settings you will encounter:

- **Description:**

  - **What this setting does:** This is the internal name for the cart rule (voucher) that will be created. It helps you identify the voucher in your Back Office.
  - **Effect of changing this setting:** This name is for your reference only and is not visible to customers.
  - **Recommended value:** Something descriptive like “New Customer Registration Voucher” or “Welcome Discount”.
  - **Merchant scenario / example:** If you run multiple promotions, a clear description like “Welcome Voucher - 10% Off” helps you track its performance.
- **Code:**

  - **What this setting does:** This defines the prefix for the unique voucher codes generated. The module will append a unique string to this prefix for each new customer.
  - **Effect of changing this setting:** If you set it to “WELCOME”, customers might receive codes like “WELCOME12345” or “WELCOMEABCDE”. This makes the codes easily identifiable.
  - **Recommended value:** A short, memorable prefix like “WELCOME”, “NEWCUSTOMER”, or “MYSTORE”. Leave empty for a fully random code.
  - **Merchant scenario / example:** Using “WELCOME” makes it clear to the customer that this is a welcome offer.
- **Highlight:**

  - **What this setting does:** If enabled, this voucher will be displayed in the cart summary (if applicable) and on the product page (if configured to do so by PrestaShop’s core settings).
  - **Effect of changing this setting:**
    - *When enabled:* The voucher’s existence might be subtly hinted at in places where cart rules are usually promoted.
    - *When disabled:* The voucher is only known to the customer via email and their account.
  - **Recommended value:** YES (Enabled), as it can subtly remind customers of available discounts.
  - **Merchant scenario / example:** Enabling this can encourage customers to use the voucher they received, even if they forgot about it.
- **Partial use:**

  - **What this setting does:** Determines if the voucher can be used multiple times if its value is greater than the order total.
  - **Effect of changing this setting:**
    - *When enabled:* If a customer has a $50 voucher and buys a $30 item, they will have a $20 balance remaining on the voucher for a future purchase.
    - *When disabled:* The entire voucher value must be used in one transaction, or the remaining balance is forfeited.
  - **Recommended value:** NO (Disabled) for most welcome vouchers, to encourage a full purchase.
  - **Merchant scenario / example:** For a “10% off” voucher, this setting is less relevant, but for a “fixed amount” voucher (e.g., “$10 off”), disabling partial use encourages a larger first order.
- **Priority:**

  - **What this setting does:** If a customer has multiple vouchers, this number determines the order in which they are applied. Lower numbers mean higher priority.
  - **Effect of changing this setting:** A voucher with priority 1 will be applied before a voucher with priority 2. This is important if vouchers cannot be combined.
  - **Recommended value:** 1 (Highest priority) for welcome vouchers, ensuring they are applied first.
  - **Merchant scenario / example:** If you have a general “free shipping” voucher (priority 5) and a “welcome discount” voucher (priority 1), the welcome discount will be calculated first.
- **Status:**

  - **What this setting does:** Controls whether the module is active and generating vouchers.
  - **Effect of changing this setting:**
    - *When enabled:* New customers will receive vouchers upon registration.
    - *When disabled:* The module will stop generating and sending vouchers.
  - **Recommended value:** YES (Enabled) to activate the module’s core functionality.
  - **Merchant scenario / example:** You might disable it temporarily during a specific sales event where you don’t want to offer additional registration discounts.
- **Discount type:**

  - **What this setting does:** Defines whether the discount is a percentage, a fixed amount, or free shipping.
  - **Effect of changing this setting:**
    - *Percentage:* e.g., “10%” off the order.
    - *Amount:* e.g., “$10” off the order.
    - *Free shipping:* Waives shipping costs.
  - **Recommended value:** Percentage or Amount, depending on your marketing strategy.
  - **Merchant scenario / example:** Offering “10% off” is common for welcome discounts. “$5 off” might be better for lower-priced items.
- **Value:**

  - **What this setting does:** The actual discount value, corresponding to the “Discount type” selected.
  - **Effect of changing this setting:** If “Discount type” is Percentage and “Value” is 10, customers get 10% off. If “Discount type” is Amount and “Value” is 10, they get $10 off.
  - **Recommended value:** A value that is attractive but also profitable, e.g., “10” for 10% or “$5”.
  - **Merchant scenario / example:** A 10% discount is a good starting point to entice new customers.
- **Minimum amount:**

  - **What this setting does:** The minimum order total (before shipping) required for the voucher to be valid.
  - **Effect of changing this setting:** If set to $50, the customer must place an order of $50 or more to use the voucher.
  - **Recommended value:** Set a reasonable minimum to encourage larger first orders, or 0 if no minimum is required.
  - **Merchant scenario / example:** Setting a $50 minimum for a 10% off voucher ensures you still make a good profit on the first order.
- **Cumulative:**

  - **What this setting does:** Determines if this voucher can be combined with other vouchers.
  - **Effect of changing this setting:**
    - *When enabled:* Customers can use this welcome voucher along with other active vouchers (e.g., a free shipping voucher).
    - *When disabled:* This voucher cannot be used if another voucher is already applied to the cart.
  - **Recommended value:** NO (Disabled) for most welcome vouchers to prevent excessive discounting.
  - **Merchant scenario / example:** You usually want to limit stacking discounts to protect your margins, so disabling cumulative use is often preferred.
- **Valid from / Valid to:**

  - **What this setting does:** Defines the date range during which the voucher is active.
  - **Effect of changing this setting:** The voucher will only be valid between these dates.
  - **Recommended value:** Leave “Valid from” as the current date. For “Valid to”, consider setting an expiration date (e.g., 30 days from registration) to create urgency, or leave it far in the future if you want it to be evergreen.
  - **Merchant scenario / example:** Setting “Valid to” 30 days in the future encourages customers to use the voucher quickly.
- **Quantity:**

  - **What this setting does:** This refers to the total number of *unique* vouchers that can be generated by the module.
  - **Effect of changing this setting:** If set to 100, only the first 100 new registrants will receive a voucher.
  - **Recommended value:** A very high number (e.g., 999999) or leave empty if you want an unlimited number of vouchers to be generated for new registrants.
  - **Merchant scenario / example:** For an ongoing welcome offer, you typically want an unlimited quantity. If you’re running a limited-time campaign for the first X registrants, you’d set a specific number.
- **Quantity per customer:**

  - **What this setting does:** Defines how many times a *single customer* can receive this specific voucher.
  - **Effect of changing this setting:** Set to 1 to ensure each customer only receives one welcome voucher upon their initial registration.
  - **Recommended value:** 1.
  - **Merchant scenario / example:** You want each new customer to get one welcome discount, not multiple if they register again with a different email (though PrestaShop’s core usually prevents this).

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | **Description** | “New Customer Voucher” | Internal name for the voucher in BO. |
| Module Configuration | **Code** | Empty (random) / “WELCOME” | Prefix for generated voucher codes. |
| Module Configuration | **Highlight** | YES | Display voucher in cart summary/product page. |
| Module Configuration | **Partial use** | NO | Allow multiple uses if value > order total. |
| Module Configuration | **Priority** | 1 | Order of application if multiple vouchers. |
| Module Configuration | **Status** | YES | Activate/deactivate module’s voucher generation. |
| Module Configuration | **Discount type** | Percentage | Type of discount (%, amount, free shipping). |
| Module Configuration | **Value** | 10 | The actual discount value (e.g., 10 for 10%). |
| Module Configuration | **Minimum amount** | 0 | Minimum order total for voucher validity. |
| Module Configuration | **Cumulative** | NO | Allow combining with other vouchers. |
| Module Configuration | **Valid from** | Current Date | Start date for voucher validity. |
| Module Configuration | **Valid to** | Far Future / 30 days | End date for voucher validity. |
| Module Configuration | **Quantity** | 999999 | Total number of unique vouchers to generate. |
| Module Configuration | **Quantity per customer** | 1 | How many times a single customer can get it. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My customers aren’t receiving the voucher email. What should I check?**
A:

1. **Module Status:** Ensure the “Status” setting in the module configuration is set to YES (Enabled).
2. **Email Configuration:** Check your PrestaShop email settings under **Advanced Parameters > E-mail**. Send a test email to ensure your store’s email system is working correctly.
3. **Spam Folders:** Advise customers to check their spam or junk folders.
4. **Module Logs:** If available, check for any error logs related to the module or email sending.
5. **Smarty Cache:** Sometimes, clearing the Smarty cache under **Advanced Parameters > Performance** can resolve display or functionality issues.

**Q: The voucher code is generated, but it’s not applying correctly at checkout.**
A:

1. **Voucher Settings:** Double-check all the voucher settings in the module configuration (e.g., “Minimum amount,” “Valid from/to,” “Cumulative”). Ensure the customer’s cart meets all conditions.
2. **Code Entry:** Confirm the customer is entering the code correctly in the cart/checkout.
3. **Product Restrictions:** Ensure there are no hidden product or category restrictions applied to the generated cart rule (though this module typically creates simple, broad rules).

**Q: Can I customize the email template that sends the voucher?**
A: Yes, the module uses PrestaShop’s standard email templating system. You can find and customize the relevant email template files (usually in `themes/your_theme/mail/en/` or `mails/en/` for older versions) that are triggered when a new cart rule is created and sent. Look for templates related to `voucher` or `cart_rule`.

**Q: What happens if a customer registers multiple times with different email addresses?**
A: The module will generate a new unique voucher for each new registration. PrestaShop’s core functionality usually prevents duplicate email registrations, but if a customer uses different emails, they would receive a new voucher each time. The “Quantity per customer” setting applies to a single customer ID, not necessarily unique email addresses if they bypass core checks.

**Q: The module is installed, but I don’t see any new menu items in the Back Office.**
A: This module integrates directly into the existing “Modules > Module Manager” section and does not add new top-level menu items. Its configuration is accessible by clicking “Configure” next to its name in the module list.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Voucher code after registration” module (`registervoucher`) is a standard PrestaShop module primarily designed to extend the `actionCustomerAccountAdd` hook. It leverages PrestaShop’s core `CartRule` (voucher) functionality to automatically create and assign a unique discount code to new customer accounts. The module’s configuration is handled via the `getContent()` method in the main module file, storing settings in `ps_configuration`. It includes minimal front-office interaction, mainly relying on PrestaShop’s native email system and customer account display for voucher delivery.

### 4.2 Controllers (`controllers/`)

This module does not contain any custom Front-Office or Back-Office Admin Controllers. All logic is encapsulated within the main module file and its registered hooks.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or extend `ObjectModel`. It directly interacts with PrestaShop’s core `CartRule` class to create and manage vouchers.

### 4.4 JavaScript Assets (`views/js/`)

- `registervoucher/lib/voucherengine/script.js`
  - **Scope:** Potentially Back-office, or a generic script included for compatibility.
  - **Description:** Given the module’s primary function (backend voucher generation), this script is likely a utility or compatibility script. It might handle UI enhancements on the configuration page, form validation, or provide compatibility fixes for older PrestaShop versions, especially concerning dynamic form elements or AJAX interactions within the `getContent()` method. Without further inspection, its exact purpose is speculative but generally related to enhancing the module’s configuration interface or ensuring cross-version compatibility for the admin panel.

### 4.5 CSS Stylesheets (`views/css/`)

- `registervoucher/css.css`

  - **Scope:** Likely Back-office admin form styling.
  - **Description:** This stylesheet probably contains custom styles for the module’s configuration page within the PrestaShop Back Office. It might adjust layout, spacing, colors, or specific element appearances to ensure the configuration form is visually consistent or to apply custom branding.
  - **Key CSS class selectors developers can override:** `.registervoucher-config`, `.form-group`, `.control-label`, `.help-block` (specific to the module’s generated HTML).
- `registervoucher/lib/voucherengine/ps16.css`

  - **Scope:** Back-office admin form styling, specifically for PrestaShop 1.6 compatibility.
  - **Description:** This stylesheet is almost certainly included to ensure the module’s configuration page renders correctly and consistently with the PrestaShop 1.6 Back Office theme. It addresses styling differences between PS 1.6 and newer versions, providing necessary overrides or specific styles for elements like buttons, form fields, and layout containers to maintain a proper look and feel.
  - **Key CSS class selectors developers can override:** Specific to PS 1.6 admin theme, e.g., `.panel`, `.form-horizontal`, `.btn`.

### 4.6 Smarty Template Structure (`views/templates/`)

The module dossier indicates no custom `.tpl` files. This suggests that the module’s configuration form is rendered directly within the `getContent()` method using PrestaShop’s helper classes (e.g., `HelperForm`), and any front-office display (like the voucher in the customer account) is handled by overriding core PrestaShop templates or by injecting content directly via hooks without dedicated module templates. The email content is managed through PrestaShop’s native mail templates.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any custom database tables.
  - Configuration settings are stored in the `ps_configuration` table (e.g., `PS_REGISTERVOUCHER_DESCRIPTION`, `PS_REGISTERVOUCHER_CODE`, etc.).
  - The generated vouchers are stored in PrestaShop’s core `ps_cart_rule` and `ps_cart_rule_lang` tables.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionCustomerAccountAdd` | Executed immediately after a new customer account is successfully created. | This is the primary hook. The module listens to this event to trigger the voucher generation and assignment process for the newly registered customer. |
| `displayHeader` | Executed in the `<head>` section of every front-office page. | Often used for adding CSS/JS, but in this module, it’s not explicitly used for front-office display. Could be for internal module setup or compatibility. |
| `displayRightColumn` | Executed in the right column of the front-office. | Not directly used for the module’s core functionality of voucher display. |
| `displayLeftColumn` | Executed in the left column of the front-office. | Not directly used for the module’s core functionality of voucher display. |
| `displayFooter` | Executed in the footer section of every front-office page. | Not directly used for the module’s core functionality of voucher display. |
| `displayProductButtons` | Executed on the product page, near the add-to-cart button. | Not directly used for the module’s core functionality of voucher display. |
| `displayCustomerAccount` | Executed on the customer’s “My Account” page. | This hook is crucial for displaying the generated voucher code directly within the customer’s account area, making it easily accessible. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the “Voucher code after registration” module, please refer to your customer account at MyPresta.eu. Our support team is available to assist you with any technical issues or questions regarding the module’s functionality.
