---
title: "Bankwire with discount - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Bankwire with discount PrestaShop module by MyPresta.eu."
sidebar:
  label: "Bankwire with discount - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Bankwire with discount Module on MyPresta.eu](https://mypresta.eu/modules/payment-process/bankwire-with-discount.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/payment/bankwire-with-discount/)
>
> ---


# Bankwire with discount

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required for PrestaShop itself and generally available on all modern hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Bankwire with discount)

This is the main configuration screen where you’ll set up all the core functionalities of the module.

#### **General Settings**

- **Enable Bank Wire Payment:**

  - **What this setting does:** This is the master switch to enable or disable the “Bankwire with discount” payment method in your store.
  - **Effect of changing this setting:**
    - *When enabled:* Customers will see “Pay by Bank Wire” as a payment option during checkout.
    - *When disabled:* The bank wire payment option will be hidden from customers.
  - **Recommended value:** YES (to use the module’s features).
  - **Merchant scenario:** You want to offer bank wire payments.
- **Bank Wire Title:**

  - **What this setting does:** Defines the title displayed for the bank wire payment option on the checkout page.
  - **Effect of changing this setting:** Changes the text customers see when choosing this payment method.
  - **Recommended value:** “Pay by Bank Wire”, “Bank Transfer (with discount!)”, or similar.
  - **Merchant scenario:** You want to clearly label the payment method for customers.
- **Payment Instructions (Summary on Checkout):**

  - **What this setting does:** A short text displayed on the payment selection page (before confirmation) to give customers quick instructions or information about the bank wire.
  - **Effect of changing this setting:** Provides immediate context to the customer about the bank wire method.
  - **Recommended value:** “You will receive bank details after confirming your order. Discount applied!”
  - **Merchant scenario:** You want to inform customers about the next steps or highlight the discount benefit early.
- **Payment Instructions (After Order Confirmation):**

  - **What this setting does:** Detailed instructions displayed on the order confirmation page after a customer has placed a bank wire order. This is where you put your bank account details.
  - **Effect of changing this setting:** Provides the essential information for customers to make the bank transfer.
  - **Recommended value:** Include your bank name, account holder, IBAN, SWIFT/BIC, and any specific notes (e.g., “Please include your order reference in the transfer description”).
  - **Merchant scenario:** This is crucial for customers to successfully complete their payment.

#### **Bank Account Details**

These fields are used to provide your bank account information to customers.

- **Account Owner:**

  - **What this setting does:** The name of the account holder for the bank account.
  - **Effect of changing this setting:** Displays this name to the customer.
  - **Recommended value:** Your company name or personal name.
  - **Merchant scenario:** Essential for the bank transfer.
- **Bank Name:**

  - **What this setting does:** The name of your bank.
  - **Effect of changing this setting:** Displays this name to the customer.
  - **Recommended value:** e.g., “Deutsche Bank”, “Bank of America”.
  - **Merchant scenario:** Essential for the bank transfer.
- **Address:**

  - **What this setting does:** The address of your bank.
  - **Effect of changing this setting:** Displays this address to the customer.
  - **Recommended value:** Your bank’s branch address.
  - **Merchant scenario:** May be required for international transfers.
- **IBAN (International Bank Account Number):**

  - **What this setting does:** Your IBAN, a standardized international bank account number.
  - **Effect of changing this setting:** Displays this number to the customer.
  - **Recommended value:** Your full IBAN.
  - **Merchant scenario:** Crucial for bank transfers, especially within Europe.
- **SWIFT/BIC (Bank Identifier Code):**

  - **What this setting does:** Your SWIFT/BIC code, used for international bank transfers.
  - **Effect of changing this setting:** Displays this code to the customer.
  - **Recommended value:** Your full SWIFT/BIC code.
  - **Merchant scenario:** Essential for international bank transfers.
- **Additional Information:**

  - **What this setting does:** Any extra notes or instructions you want to provide regarding the bank transfer (e.g., “Please allow 1-3 business days for processing”).
  - **Effect of changing this setting:** Provides additional guidance to the customer.
  - **Recommended value:** Any specific instructions not covered by other fields.
  - **Merchant scenario:** You want to manage customer expectations about transfer times.

#### **Discount & Surcharge Settings**

This section allows you to configure discounts or surcharges for using bank wire.

- **Discount Type:**

  - **What this setting does:** Determines how the discount is calculated.
  - **Effect of changing this setting:**
    - *Percentage:* Discount is a percentage of the order total.
    - *Fixed Amount:* Discount is a flat amount, regardless of the order total.
  - **Recommended value:** Percentage (often more appealing for varying order values).
  - **Merchant scenario:** You want to offer 5% off or a fixed $10 discount.
- **Discount Value:**

  - **What this setting does:** The actual value of the discount (e.g., “5” for 5% or “$10” for a fixed amount).
  - **Effect of changing this setting:** Directly applies the discount to the order total if bank wire is chosen.
  - **Recommended value:** A value that makes bank wire attractive without hurting your margins.
  - **Merchant scenario:** You decide to offer a 3% discount or a $5 discount.
- **Percentage Base (if Discount Type is Percentage):**

  - **What this setting does:** Specifies which part of the order total the percentage discount is applied to.
  - **Effect of changing this setting:** Changes the base amount for discount calculation.
    - *Order total (with taxes):* Discount calculated on the full price including tax.
    - *Order total (without taxes):* Discount calculated on the price before tax.
    - *Products total (with taxes):* Discount only on product value, including tax.
    - *Products total (without taxes):* Discount only on product value, excluding tax.
  - **Recommended value:** Order total (with taxes) for simplicity and clarity to the customer.
  - **Merchant scenario:** You want to give 5% off the entire final price the customer sees.
- **Minimum Cart Value:**

  - **What this setting does:** The minimum total value an order must have for the bank wire discount to be applied.
  - **Effect of changing this setting:** The discount will only appear and be applied if the cart total meets or exceeds this value.
  - **Recommended value:** Leave empty if no minimum, or set a value to encourage larger orders.
  - **Merchant scenario:** You only want to offer a discount on orders over $100.
- **Maximum Cart Value:**

  - **What this setting does:** The maximum total value an order can have for the bank wire discount to be applied.
  - **Effect of changing this setting:** The discount will not be applied if the cart total exceeds this value.
  - **Recommended value:** Leave empty if no maximum, or set a value to limit discount exposure on very large orders.
  - **Merchant scenario:** You don’t want to give a discount on orders over $1000.
- **Currencies:**

  - **What this setting does:** Select which currencies the bank wire payment method (and its discount) will be available for.
  - **Effect of changing this setting:** The payment option will only appear for customers shopping in the selected currencies.
  - **Recommended value:** Select all currencies you accept.
  - **Merchant scenario:** You only accept bank transfers in EUR and USD.
- **Zones:**

  - **What this setting does:** Select which geographical zones the bank wire payment method (and its discount) will be available for.
  - **Effect of changing this setting:** The payment option will only appear for customers whose shipping address falls within the selected zones.
  - **Recommended value:** Select all zones you ship to.
  - **Merchant scenario:** You only offer bank wire in Europe.
- **Countries:**

  - **What this setting does:** Select specific countries where the bank wire payment method (and its discount) will be available.
  - **Effect of changing this setting:** Overrides zone settings for specific countries.
  - **Recommended value:** Select all countries you ship to.
  - **Merchant scenario:** You want to exclude a specific country from bank wire payments.
- **Customer Groups:**

  - **What this setting does:** Select which customer groups can see and use the bank wire payment method (and its discount).
  - **Effect of changing this setting:** Only customers belonging to the selected groups will see this payment option.
  - **Recommended value:** Select all relevant customer groups (e.g., “Customer”, “Visitor”, “Guest”).
  - **Merchant scenario:** You only want to offer bank wire to registered customers.

#### **Unpaid Order Management**

These features help you manage orders that are placed via bank wire but not yet paid.

- **Send reminders for unpaid orders:**

  - **What this setting does:** Enables or disables automated email reminders to customers for unpaid bank wire orders.
  - **Effect of changing this setting:**
    - *When enabled:* The module will send reminder emails.
    - *When disabled:* No reminders will be sent.
  - **Recommended value:** YES (helps reduce abandoned payments).
  - **Merchant scenario:** You want to gently remind customers to complete their payment.
- **First reminder after (days):**

  - **What this setting does:** The number of days after an order is placed before the first reminder email is sent.
  - **Effect of changing this setting:** Controls the timing of the first reminder.
  - **Recommended value:** 2-3 days (gives customers time to pay, but not too long).
  - **Merchant scenario:** You want to send a reminder if payment isn’t received within 2 days.
- **Max reminders per order:**

  - **What this setting does:** The maximum number of reminder emails an order will trigger.
  - **Effect of changing this setting:** Prevents spamming customers with too many reminders.
  - **Recommended value:** 1-2 (sufficient to remind without annoying).
  - **Merchant scenario:** You want to send only one reminder email.
- **Auto-cancel unpaid orders:**

  - **What this setting does:** Enables or disables the automatic cancellation of bank wire orders that remain unpaid after a specified period.
  - **Effect of changing this setting:**
    - *When enabled:* Orders will be automatically cancelled, freeing up inventory.
    - *When disabled:* Orders will remain in “Awaiting Bank Wire Payment” status indefinitely.
  - **Recommended value:** YES (automates inventory management and keeps order list clean).
  - **Merchant scenario:** You don’t want to hold inventory for unpaid orders for too long.
- **Cancel after (days):**

  - **What this setting does:** The number of days after an order is placed before it is automatically cancelled if unpaid.
  - **Effect of changing this setting:** Controls when unpaid orders are cancelled.
  - **Recommended value:** 5-7 days (allows reasonable time for payment, but prevents indefinite holds).
  - **Merchant scenario:** You want to cancel orders if payment isn’t received within 7 days.
- **Auto-blacklist offenders:**

  - **What this setting does:** If enabled, customers who repeatedly place bank wire orders and then have them cancelled due to non-payment will be added to a blacklist.
  - **Effect of changing this setting:**
    - *When enabled:* Customers exceeding the threshold will be blacklisted.
    - *When disabled:* No customers will be blacklisted automatically.
  - **Recommended value:** YES (helps deter fraudulent or time-wasting customers).
  - **Merchant scenario:** You want to prevent customers who never pay from placing future bank wire orders.
- **Cancelled orders threshold:**

  - **What this setting does:** The number of cancelled bank wire orders a customer can have before they are automatically blacklisted.
  - **Effect of changing this setting:** Defines the tolerance for non-payment before blacklisting.
  - **Recommended value:** 2-3 (allows for genuine mistakes but catches repeat offenders).
  - **Merchant scenario:** You want to blacklist a customer after 3 unpaid and cancelled bank wire orders.

#### **Advanced Settings**

- **Cron Job Token:**

  - **What this setting does:** A unique security token used to secure the module’s cron job URL. This is essential for the automated reminder and cancellation features to work.
  - **Effect of changing this setting:** The cron job will only execute if this token is correctly included in the URL.
  - **Recommended value:** Leave as generated. Do not change unless you know what you’re doing.
  - **Merchant scenario:** You need to set up a cron job on your server to run the module’s automated tasks. The cron URL will look something like `yourstore.com/module/bankwiredis/cron?token=YOUR_TOKEN_HERE`.
- **CSS Selectors for Dynamic Updates:**

  - **What this setting does:** These fields allow you to specify CSS selectors for elements on your checkout page that display the cart total, subtotal, and shipping cost. The module uses these to dynamically update the prices when a discount is applied.
  - **Effect of changing this setting:** If your theme uses non-standard CSS classes for these elements, adjusting these selectors ensures the discount is correctly reflected in the displayed prices during checkout.
  - **Recommended value:** Leave as default unless the discount is not showing correctly on your checkout page. If issues, consult your theme developer or a webmaster.
  - **Merchant scenario:** Your custom theme uses `.my-custom-total-price` instead of the default `.cart-total-price`. You would update this field to ensure the discount is applied visually.
- **Email Template:**

  - **What this setting does:** Allows you to select a custom email template for the bank wire payment instructions and reminders.
  - **Effect of changing this setting:** Changes the design and content of the emails sent by the module.
  - **Recommended value:** Default (unless you have a custom template).
  - **Merchant scenario:** You want to use a branded email template for bank wire communications.

#### **Visibility Rules (Advanced Discount Targeting)**

This section allows you to create highly specific rules for when the bank wire discount is offered.

- **Rule Name:**

  - **What this setting does:** A descriptive name for your discount rule (e.g., “Holiday Discount for Bankwire”).
  - **Effect of changing this setting:** Helps you identify and manage different rules.
  - **Recommended value:** Clear and concise name.
  - **Merchant scenario:** You have multiple discount rules and need to distinguish them.
- **Active:**

  - **What this setting does:** Enables or disables this specific discount rule.
  - **Effect of changing this setting:**
    - *When enabled:* The rule is active and its conditions will be checked.
    - *When disabled:* The rule is ignored.
  - **Recommended value:** YES (if you want the rule to apply).
  - **Merchant scenario:** You want to temporarily disable a seasonal discount.
- **Position (priority):**

  - **What this setting does:** Determines the order in which rules are evaluated if multiple rules could apply. Lower numbers have higher priority.
  - **Effect of changing this setting:** If a customer’s cart matches multiple rules, the one with the lowest position will be applied.
  - **Recommended value:** Use sequential numbers (1, 2, 3…) to manage priority.
  - **Merchant scenario:** If a customer qualifies for both a “General 5% off” rule (position 10) and a “VIP 10% off” rule (position 5), the VIP rule will be applied.
- **Discount Type, Discount Value, Percentage Base, Minimum Cart Value, Maximum Cart Value, Currencies, Zones, Countries, Customer Groups:**

  - **What this setting does:** These are the same settings as described in the “Discount & Surcharge Settings” section above, but applied specifically to *this individual rule*. This allows you to have different discount amounts or conditions for different scenarios.
  - **Effect of changing this setting:** The discount defined within this rule will only apply if all its specific conditions are met.
  - **Recommended value:** Configure based on your specific promotional strategy.
  - **Merchant scenario:** You want to offer a 10% discount for bank wire payments only for customers in the “Wholesaler” group, and only for orders over $500.
- **Products:**

  - **What this setting does:** Allows you to specify that this discount rule only applies if certain products are in the cart.
  - **Effect of changing this setting:** The bank wire discount will only be offered if one or more of the selected products are present in the customer’s cart.
  - **Recommended value:** Leave empty to apply to all products, or select specific products for targeted promotions.
  - **Merchant scenario:** You want to offer a bank wire discount only if a customer buys a specific high-value item.
- **Categories:**

  - **What this setting does:** Allows you to specify that this discount rule only applies if products from certain categories are in the cart.
  - **Effect of changing this setting:** The bank wire discount will only be offered if one or more products from the selected categories are present in the customer’s cart.
  - **Recommended value:** Leave empty to apply to all categories, or select specific categories for targeted promotions.
  - **Merchant scenario:** You want to offer a bank wire discount only for products in your “Electronics” category.

#### **Configuration Quick Reference Table**

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Enable Bank Wire Payment | YES | Activates/deactivates the payment method. |
|  | Bank Wire Title | “Pay by Bank Wire” | Text displayed for the payment option. |
|  | Payment Instructions (Checkout) | Short, clear text | Info shown on payment selection page. |
|  | Payment Instructions (Confirmation) | Detailed bank info | Bank details and instructions after order. |
|  | Account Owner | Your Company Name | Name on bank account. |
|  | Bank Name | Your Bank | Name of your bank. |
|  | Address | Your Bank Address | Address of your bank. |
|  | IBAN | Your IBAN | International Bank Account Number. |
|  | SWIFT/BIC | Your SWIFT/BIC | Bank Identifier Code for international transfers. |
|  | Additional Information | Optional notes | Extra instructions for customers. |
|  | Discount Type | Percentage | How discount is calculated (percentage/fixed). |
|  | Discount Value | 0 (or desired value) | The actual discount amount or percentage. |
|  | Percentage Base | Order total (with taxes) | Which amount the percentage discount applies to. |
|  | Minimum Cart Value | Empty (or desired value) | Minimum order value for discount. |
|  | Maximum Cart Value | Empty (or desired value) | Maximum order value for discount. |
|  | Currencies | All active | Currencies where bank wire is available. |
|  | Zones | All active | Geographical zones where bank wire is available. |
|  | Countries | All active | Specific countries where bank wire is available. |
|  | Customer Groups | All active | Customer groups who can use bank wire. |
|  | Send reminders for unpaid orders | YES | Enables email reminders for unpaid orders. |
|  | First reminder after (days) | 2-3 days | Delay before first reminder. |
|  | Max reminders per order | 1-2 | Max number of reminder emails. |
|  | Auto-cancel unpaid orders | YES | Automatically cancels unpaid orders. |
|  | Cancel after (days) | 5-7 days | Delay before auto-cancellation. |
|  | Auto-blacklist offenders | YES | Blacklists customers with too many cancelled orders. |
|  | Cancelled orders threshold | 2-3 | Number of cancelled orders before blacklisting. |
|  | Cron Job Token | Auto-generated | Security token for cron job. |
|  | CSS Selectors | Default (or theme-specific) | For dynamic price updates on checkout. |
|  | Email Template | Default | Email template for bank wire communications. |
|  | **Visibility Rules** | Rule Name | Descriptive name |
|  | Active | YES | Activates/deactivates a specific rule. |
|  | Position (priority) | 1, 2, 3… | Order of rule evaluation (lower = higher priority). |
|  | Products | Empty (or specific products) | Discount applies only if these products are in cart. |
|  | Categories | Empty (or specific categories) | Discount applies only if products from these categories are in cart. |

### 2.2 Back-Office Controller Screen: AdminBankwiredisSearchController

- **Screen Name & Menu Location:** This controller is typically used for managing specific entities related to the module, such as blacklisted customers or specific discount rules, often accessible via a sub-tab under the main module configuration or a dedicated menu item. In this module, it’s likely used for managing the visibility rules or blacklisted customers.
  - **Menu Location:** Likely accessed via a tab or link within the main “Bankwire with discount” module configuration page, or potentially under **Sell > Orders > Bankwire with discount Blacklist** (example, actual location may vary based on PrestaShop version and module design).
- **Available Actions & Settings:** This screen provides a grid-based management view.
  - **Listing Table:** Displays a list of items (e.g., blacklisted customers, discount rules). Each row typically shows relevant details like Customer ID, Customer Email, Reason for blacklist, Rule Name, Active status, etc.
  - **Add/Edit Buttons:** Allows you to manually add new entries (e.g., manually blacklist a customer) or edit existing ones.
  - **Bulk Actions:** Options to perform actions on multiple selected items (e.g., delete multiple blacklisted customers).
  - **Search/Filter:** Tools to find specific entries within the list.
- **Effect of changes:**
  - **Adding/Editing Blacklist Entries:** Directly impacts which customers are prevented from using the bank wire payment method.
  - **Adding/Editing Discount Rules:** Modifies the conditions under which discounts are applied, affecting pricing and customer incentives.
- **Recommended workflow for daily store management:**
  1. Regularly review the list of blacklisted customers to ensure it’s up-to-date.
  2. If you need to manually blacklist a customer (e.g., after direct communication), use the “Add” function here.
  3. If you need to adjust or create new discount rules, this is where you’d manage them, ensuring they align with your current promotions.

### 2.3 Back-Office Controller Screen: index.php (Admin Controller)

- **Screen Name & Menu Location:** The `index.php` file in an admin controller directory often serves as a placeholder or a redirect, or in some cases, it can be the entry point for a dashboard or a simple listing. Given the module’s features, this might be a dashboard for bank wire statistics or a simple listing of pending bank wire orders.
  - **Menu Location:** Potentially a sub-tab under the main module configuration, or a dedicated menu item like **Sell > Orders > Bankwire with discount Dashboard**.
- **Available Actions & Settings:** This screen likely presents a grid or a dashboard.
  - **Grid / Management View:** Could display a list of recent bank wire orders, their status, payment reminders sent, or cancellation status.
  - **Analytics/Statistics:** Might show charts or summaries related to bank wire payments, such as conversion rates, average discount applied, or number of unpaid orders.
- **Effect of changes:** This screen is typically for monitoring and reporting, rather than direct configuration changes. Any actions taken here (e.g., manually marking an order as paid) would update the order status in PrestaShop.
- **Recommended workflow for daily store management:**
  1. Periodically check this dashboard to monitor the performance of your bank wire payment method.
  2. Review pending bank wire orders to ensure they are being processed or reminded/cancelled as expected.
  3. Use any available statistics to evaluate the effectiveness of your bank wire discounts and reminder system.

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The bank wire payment option is not showing up on my checkout page.**

- **A:** First, check if “Enable Bank Wire Payment” is set to YES in the module configuration.
- **A:** Next, verify your “Currencies,” “Zones,” “Countries,” and “Customer Groups” settings. If the customer’s context (currency, shipping address, or group) doesn’t match your selections, the payment method won’t appear.
- **A:** If you have specific visibility rules, ensure the customer’s cart meets all conditions (min/max cart value, specific products/categories).
- **A:** Clear your PrestaShop cache (Advanced Parameters > Performance > Clear cache).

**Q2: The discount is not being applied or displayed correctly on the checkout page.**

- **A:** Double-check your “Discount Type” and “Discount Value” settings.
- **A:** Review any “Minimum Cart Value” or “Maximum Cart Value” settings – the cart total must fall within these ranges.
- **A:** If you’re using a custom theme, the module might not be able to find the correct CSS selectors to update the prices dynamically. Go to the “Advanced Settings” section and ensure the “CSS Selectors for Dynamic Updates” match your theme’s actual selectors for cart total, subtotal, and shipping. You might need a webmaster to inspect your theme’s code.
- **A:** Clear your PrestaShop cache.

**Q3: Automated reminders or cancellations are not working.**

- **A:** This is almost always a cron job issue. You need to set up a cron job on your server to periodically run the module’s tasks.
- **A:** In the module’s “Advanced Settings,” copy the “Cron Job Token” and the full cron URL.
- **A:** Access your hosting control panel (cPanel, Plesk, etc.) and find the “Cron Jobs” section.
- **A:** Add a new cron job that executes the provided URL every few hours (e.g., `wget -O /dev/null "https://yourstore.com/module/bankwiredis/cron?token=YOUR_TOKEN_HERE"`).
- **A:** Ensure “Send reminders for unpaid orders” and “Auto-cancel unpaid orders” are enabled, and the days are correctly set.

**Q4: How do I translate the module’s texts into other languages?**

- **A:** In your PrestaShop Back Office, go to **International > Translations**.
- **A:** Select “Installed modules translations,” choose your theme, and then select “Bankwire with discount” from the module dropdown.
- **A:** You can then edit all translatable strings for the module. Remember to save your changes.

**Q5: A customer was blacklisted, but I want to allow them to use bank wire again.**

- **A:** Navigate to the module’s dedicated admin screen (likely under **Sell > Orders > Bankwire with discount Blacklist** or similar, or a tab within the module config).
- **A:** Find the customer in the list and either delete their blacklist entry or edit it to deactivate the blacklist for them.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Bankwire with discount” module (`bankwiredis`) extends PrestaShop’s payment functionality, adhering to the MVC pattern. It integrates with the checkout process via `PaymentOptions` hooks, manages order states, and implements automated tasks (reminders, cancellations, blacklisting) through a cron job. Discount logic is applied dynamically during checkout and persisted with the order. Custom admin controllers provide management interfaces for discount rules and blacklisted customers.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `controllers/front/cron.php`
  - **Class Name:** `BankwiredisCronModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** This controller handles the execution of scheduled tasks. It’s designed to be called by a server-side cron job using a secure token. It processes unpaid order reminders, auto-cancellations, and customer blacklisting based on the module’s configuration. It does not render any front-office content directly but performs background operations.
- `controllers/front/index.php`
  - **Class Name:** `BankwiredisIndexModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** Often a placeholder or a default entry point. In this module, it might handle redirects or serve as a fallback if other specific front controllers aren’t matched. It typically doesn’t have a direct user-facing function.
- `controllers/front/payment.php`
  - **Class Name:** `BankwiredisPaymentModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** This controller is responsible for displaying the bank wire payment details and instructions to the customer *after* they have selected bank wire as their payment method but *before* the order is fully validated. It prepares the data (bank details, final amount with discount) for the `payment.tpl` or `validation.tpl` template.
- `controllers/front/validation.php`
  - **Class Name:** `BankwiredisValidationModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** This is the crucial controller that processes the final validation of a bank wire order. After the customer confirms their choice, this controller creates the order in PrestaShop, sets its initial status (e.g., “Awaiting Bank Wire Payment”), applies the calculated discount, and redirects the customer to the order confirmation page.

#### Back-Office Admin Controllers

- `controllers/admin/AdminBankwiredisSearchController.php`
  - **Class Name:** `AdminBankwiredisSearchController` (extends `ModuleAdminController`)
  - **Tab Name:** Likely a sub-tab under the main module configuration or a dedicated menu entry.
  - **Managed Entity:** This controller manages the module’s custom entities, specifically the discount visibility rules and potentially the blacklisted customers. It provides a standard PrestaShop `HelperList` or `HelperForm` interface for viewing, adding, editing, and deleting these records.
- `controllers/admin/index.php`
  - **Class Name:** `AdminBankwiredisIndexController` (extends `ModuleAdminController`)
  - **Tab Name:** Similar to `AdminBankwiredisSearchController`, this would be a dedicated admin page.
  - **Managed Entity:** Given the module’s features, this controller likely serves as a dashboard or a management interface for the module’s core data, such as a list of pending bank wire orders, statistics, or a simplified view of the blacklisted customers.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes in the `classes/` directory. This suggests that the module’s data (like discount rules, blacklisted customers) might be stored directly in `ps_configuration` or managed through generic `ObjectModel` instances defined within the main `bankwiredis.php` file or directly within the admin controllers.

- **Note:** If custom tables are used, their `ObjectModel` definitions would typically reside here. The module likely uses `Configuration::get()` and `Configuration::updateValue()` for most settings and potentially `Db::getInstance()` for direct database interactions for more complex data structures like discount rules or blacklisted customers, if not mapped to a custom `ObjectModel`.

### 4.4 JavaScript Assets (`views/js/`)

- `bankwiredis/lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Back-office.
  - **Functionality:** Provides autocomplete functionality, likely used in admin forms (e.g., `AdminBankwiredisSearchController`) for selecting products or categories when defining discount visibility rules. It listens for user input in specific text fields and makes AJAX requests to suggest matching items.
- `bankwiredis/views/js/adminBankwiredisAccounts.js`
  - **Scope:** Back-office.
  - **Functionality:** Likely handles dynamic behavior on the module’s configuration page related to bank account details. This could include showing/hiding fields based on selected options, input validation, or AJAX calls to save account information.
- `bankwiredis/views/js/adminBankwiredisDashboard.js`
  - **Scope:** Back-office.
  - **Functionality:** Manages interactive elements and data visualization on the module’s admin dashboard (e.g., `AdminBankwiredisIndexController`). This could involve fetching data via AJAX to populate charts, tables, or update statistics, and handling user interactions with dashboard widgets.
- `bankwiredis/views/js/bankwiredis-checkout.js`
  - **Scope:** Front-office.
  - **Functionality:** This is a critical script for the customer experience. It listens for the selection of the bank wire payment option on the checkout page. Upon selection, it makes an AJAX call to the module’s front controller to calculate and display the dynamic discount, updating the order total, subtotal, and shipping cost elements on the page. It uses the CSS selectors configured in the back office (`BDIS_CSS_PAY_INPUT`, `BDIS_CSS_CART_TOTAL`, etc.) to target the correct DOM elements for update.

### 4.5 CSS Stylesheets (`views/css/`)

- `bankwiredis/lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Back-office.
  - **Functionality:** Styles the autocomplete dropdown suggestions and input fields used in the admin search tools.
- `bankwiredis/views/css/admin_bankwiredis.css`
  - **Scope:** Back-office.
  - **Functionality:** Provides specific styling for the module’s configuration page and custom admin controller views, ensuring a consistent and user-friendly interface within the PrestaShop back office.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `bankwiredis/views/templates/hook/infos.tpl`
  - **Hook:** Likely `displayPaymentInfo` or similar.
  - **Output:** Displays general information or a summary about the bank wire payment method, potentially including the discount offer, on the payment selection page or in the order summary.
- `bankwiredis/views/templates/hook/payment.tpl`
  - **Hook:** `displayPaymentOptions` (PrestaShop 1.7+), `displayPayment` (PrestaShop 1.6).
  - **Output:** Renders the actual bank wire payment option on the checkout page, including its title, description, and the dynamically calculated discount amount. This is where the customer selects “Pay by Bank Wire.”
- `bankwiredis/views/templates/hook/payment_return.tpl`
  - **Hook:** `displayPaymentReturn`.
  - **Output:** Displays the bank account details and payment instructions on the order confirmation page after a customer has successfully placed a bank wire order.
- `bankwiredis/views/templates/hook/payment_return_pdf_invoice.tpl`
  - **Hook:** `displayPDFInvoice` (or similar for PDF generation).
  - **Output:** Provides the necessary content (bank details, discount summary) to be included in the PDF invoice generated for bank wire orders.

#### Admin templates (`views/templates/admin/`)

- `bankwiredis/lib/searchTool/views/scripts.tpl`
  - **Output:** Likely includes JavaScript and CSS assets for the autocomplete search tool within admin forms.
- `bankwiredis/views/templates/admin/scopeSelector.tpl`
  - **Output:** A template for selecting scope (e.g., shop, group, all shops) in a multi-store environment, often used in configuration forms.
- `bankwiredis/views/templates/admin/selectedProducts.tpl`
  - **Output:** Displays a list of products that have been selected for a specific discount rule (e.g., in `AdminBankwiredisSearchController` when configuring a rule based on products).

#### Front-office templates (`views/templates/front/`)

- `bankwiredis/views/templates/front/validation.tpl`
  - **Output:** This template is rendered by `BankwiredisPaymentModuleFrontController` or `BankwiredisValidationModuleFrontController` to display the final bank details and instructions *before* the order is fully confirmed or immediately after, providing a dedicated page for payment instructions.

### 4.7 Database Schema & Hooks Map

#### Database Tables

The module primarily uses PrestaShop’s `ps_configuration` table for most of its settings (e.g., `BANK_WIRE_DIS_OWNER_`, `BDIS_CRON_TOKEN`, `BANK_WIRE_DIS_CHARGEP`).
For more complex data like discount visibility rules and blacklisted customers, the module likely creates custom tables during its `install()` method. Based on the configuration options, these tables would typically be:

- `ps_bankwiredis_rules`: Stores the definition of each discount rule (rule name, active status, discount type, value, min/max cart, currencies, zones, countries, customer groups, products, categories).
- `ps_bankwiredis_blacklist`: Stores records of blacklisted customers (customer ID, email, reason, date blacklisted).
- `ps_bankwiredis_reminders`: Stores a log of reminder emails sent for each order to track `Max reminders per order`.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Used to load front-office CSS and JavaScript assets (`bankwiredis-checkout.js`) for dynamic discount display. |
| `actionAdminControllerSetMedia` | When an admin controller loads its media assets. | Used to load back-office CSS and JavaScript assets (`admin_bankwiredis.css`, `adminBankwiredisAccounts.js`, `autocomplete.js`) for the module’s configuration and admin pages. |
| `displayPaymentOptions` | On the checkout page, when payment options are listed. | Renders the bank wire payment option, including the calculated discount, using `payment.tpl`. |
| `displayPaymentReturn` | On the order confirmation page after a successful order. | Displays bank account details and payment instructions to the customer, using `payment_return.tpl`. |
| `displayPDFInvoice` | When a PDF invoice is generated. | Injects bank account details and discount information into the PDF invoice, using `payment_return_pdf_invoice.tpl`. |
| `actionValidateOrder` | After an order has been successfully validated. | Used to capture order details, apply the final discount, and potentially log the order for reminder/cancellation processing. |
| `displayPaymentInfo` | (Implicit) Often used to display additional info on payment selection. | Renders `infos.tpl` with general bank wire information. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official developer support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Ensure you are running the latest compatible version of the module for your PrestaShop store.
