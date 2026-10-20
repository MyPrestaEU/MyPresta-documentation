---
title: "Prepaid Wallet & Store Credit - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Prepaid Wallet & Store Credit PrestaShop module by MyPresta.eu."
sidebar:
  label: "Prepaid Wallet & Store Credit - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Prepaid Wallet & Store Credit Module on MyPresta.eu](https://mypresta.eu/modules/payment-process/prepaid-wallet-store-credit.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/payment/prepaid-wallet-store-credit/)
>
> ---


# Prepaid Wallet & Store Credit

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required, which are typically available on most modern hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen where you’ll set up the core behavior of your Prepaid Wallet system.

#### General Settings Tab

- **Enable Module:**

  - **What this setting does:** This is the master switch to turn the entire Prepaid Wallet system on or off for your store.
  - **Effect of changing this setting:**
    - *When enabled:* Customers will see wallet options, be able to top up, use credit, and you can manage wallets in the back office.
    - *When disabled:* All wallet functionality is hidden from customers, and they cannot use or manage their credit. Admin management might still be accessible but won’t affect the front office.
  - **Recommended value:** YES (to activate the module).
  - **Merchant scenario / example:** You’re ready to launch your loyalty program. Enable this setting. If you need to temporarily disable it for maintenance, switch it off.
- **Allow Customers to Top Up Wallet:**

  - **What this setting does:** Determines if customers can actively add funds to their wallet themselves.
  - **Effect of changing this setting:**
    - *When enabled:* Customers will see a “Top Up Wallet” option in their account, allowing them to purchase store credit.
    - *When disabled:* Customers can only receive credit from gift codes or admin-issued refunds/bonuses. They cannot buy credit directly.
  - **Recommended value:** YES (to encourage self-service loyalty).
  - **Merchant scenario / example:** You want customers to be able to buy store credit whenever they want. Enable this. If you only want to issue credit as rewards or gift cards, disable it.
- **Minimum Top-Up Amount:**

  - **What this setting does:** Sets the lowest amount a customer can add to their wallet in a single transaction.
  - **Effect of changing this setting:**
    - *When set to a value (e.g., 10.00):* Customers cannot top up less than this amount.
    - *When set to 0 or empty:* No minimum top-up amount is enforced.
  - **Recommended value:** 10.00 (or a reasonable amount for your business to cover transaction fees and encourage meaningful top-ups).
  - **Merchant scenario / example:** You don’t want customers topping up 0.50 EUR. Set this to 5.00 EUR to ensure a minimum value.
- **Maximum Top-Up Amount:**

  - **What this setting does:** Sets the highest amount a customer can add to their wallet in a single transaction.
  - **Effect of changing this setting:**
    - *When set to a value (e.g., 500.00):* Customers cannot top up more than this amount.
    - *When set to 0 or empty:* No maximum top-up amount is enforced.
  - **Recommended value:** 500.00 (or a suitable upper limit to manage risk and large transactions).
  - **Merchant scenario / example:** You want to prevent extremely large single top-ups for security or cash flow reasons. Set this to 1000.00 EUR.
- **Allow Customers to Buy Gift Codes:**

  - **What this setting does:** Controls whether customers can purchase gift codes to give to others.
  - **Effect of changing this setting:**
    - *When enabled:* Customers can buy gift codes of a specified value, which can then be redeemed by anyone.
    - *When disabled:* Gift codes can only be generated and issued by the store administrator.
  - **Recommended value:** YES (to expand your gift-giving options).
  - **Merchant scenario / example:** You want to offer digital gift cards. Enable this so customers can buy them for friends and family.
- **Gift Code Expiry (Days):**

  - **What this setting does:** Defines how many days a gift code remains valid after it’s purchased or generated.
  - **Effect of changing this setting:**
    - *When set to a number (e.g., 365):* Gift codes will expire after this many days.
    - *When set to 0 or empty:* Gift codes will not expire.
  - **Recommended value:** 365 (a common duration for gift cards, or 0 for no expiry).
  - **Merchant scenario / example:** You want gift codes to be used within a year. Set this to 365.
- **Wallet Balance Expiry (Days):**

  - **What this setting does:** Defines how many days wallet funds remain valid after they are added (either by top-up, gift code redemption, or admin credit).
  - **Effect of changing this setting:**
    - *When set to a number (e.g., 180):* Funds in the customer’s wallet will expire after this many days.
    - *When set to 0 or empty:* Wallet funds will not expire.
  - **Recommended value:** 0 (no expiry, to maximize customer satisfaction), or 180/365 if you want to encourage usage.
  - **Merchant scenario / example:** You want to encourage customers to use their wallet balance within 6 months. Set this to 180. Be aware of consumer protection laws regarding gift card expiry in your region.
- **Send Expiry Reminder Email (Days Before Expiry):**

  - **What this setting does:** If wallet balance expiry is enabled, this setting determines how many days before expiry an email reminder is sent to the customer.
  - **Effect of changing this setting:**
    - *When set to a number (e.g., 7):* Customers will receive an email 7 days before their wallet balance expires.
    - *When set to 0 or empty:* No expiry reminder emails will be sent.
  - **Recommended value:** 7 (gives customers enough time to react).
  - **Merchant scenario / example:** You have a 180-day expiry. Set this to 7 to remind customers to use their funds before they lose them.
- **Allow Partial Payments with Wallet:**

  - **What this setting does:** Controls whether customers can use their wallet balance to pay for only a portion of their order, combining it with another payment method.
  - **Effect of changing this setting:**
    - *When enabled:* If the wallet balance is less than the order total, customers can use the full balance and pay the remainder with another method.
    - *When disabled:* Customers can only use their wallet if it covers the *entire* order total. Otherwise, they must choose another payment method.
  - **Recommended value:** YES (to maximize wallet usage and reduce cart abandonment).
  - **Merchant scenario / example:** A customer has 10 EUR in their wallet and an order of 50 EUR. If enabled, they pay 10 EUR with the wallet and 40 EUR with a credit card. If disabled, they can’t use the wallet at all for this order.
- **Refund to Wallet Option:**

  - **What this setting does:** Allows you to offer customers the option to receive refunds for returned orders directly into their store wallet instead of back to their original payment method.
  - **Effect of changing this setting:**
    - *When enabled:* When processing a refund in the back office, you’ll see an option to refund to the customer’s wallet.
    - *When disabled:* Refunds must be processed through standard PrestaShop methods (e.g., back to credit card).
  - **Recommended value:** YES (to keep funds in your store and simplify refunds).
  - **Merchant scenario / example:** A customer returns an item. Instead of a credit card refund, you offer to put the money into their wallet, encouraging them to buy something else from your store.
- **Enable Multi-Currency Support:**

  - **What this setting does:** Activates the module’s ability to handle wallet balances and transactions in multiple currencies, matching your store’s configured currencies.
  - **Effect of changing this setting:**
    - *When enabled:* Wallet balances are managed per currency. A customer topping up in EUR will have a EUR balance, and topping up in USD will have a USD balance.
    - *When disabled:* All wallet transactions are converted to your store’s default currency, which can lead to conversion rate issues.
  - **Recommended value:** YES (if your store operates in multiple currencies).
  - **Merchant scenario / example:** You have customers in the EU and the US. Enabling this ensures a customer who tops up 50 EUR has 50 EUR in their wallet, and a customer who tops up 50 USD has 50 USD, preventing currency conversion losses.

#### Top-Up Bonuses Tab

- **Enable Top-Up Bonuses:**

  - **What this setting does:** Activates the system for rewarding customers with extra credit when they top up their wallet above certain thresholds.
  - **Effect of changing this setting:**
    - *When enabled:* The bonus rules you define below will be applied to customer top-ups.
    - *When disabled:* No bonuses will be given for top-ups.
  - **Recommended value:** YES (to incentivize larger top-ups and increase AOV).
  - **Merchant scenario / example:** You want to give customers an extra 5% credit if they top up 100 EUR or more. Enable this.
- **Bonus Tiers (Add/Edit/Delete):**

  - **What this setting does:** Allows you to define specific bonus rules based on the top-up amount. Each tier consists of a minimum top-up value and a bonus percentage.
  - **Effect of changing this setting:**
    - *Adding a tier (e.g., “Min Amount: 100, Bonus %: 5”):* Customers topping up 100 EUR or more will receive an additional 5% of that amount in their wallet.
    - *Editing a tier:* Changes the bonus rules for that specific threshold.
    - *Deleting a tier:* Removes a bonus rule.
  - **Recommended value:** Create 2-3 tiers (e.g., 5% for 100 EUR, 10% for 200 EUR) to encourage progressively larger top-ups.
  - **Merchant scenario / example:**
    - Tier 1: Min Amount = 50 EUR, Bonus % = 2% (Customer tops up 50 EUR, gets 51 EUR in wallet)
    - Tier 2: Min Amount = 100 EUR, Bonus % = 5% (Customer tops up 100 EUR, gets 105 EUR in wallet)
    - Tier 3: Min Amount = 200 EUR, Bonus % = 10% (Customer tops up 200 EUR, gets 220 EUR in wallet)

#### Display Options Tab

- **Display Wallet Balance in Header:**

  - **What this setting does:** Shows the customer’s current wallet balance prominently in your store’s header section.
  - **Effect of changing this setting:**
    - *When enabled:* Logged-in customers will see their balance (e.g., “Your Wallet: 25.00 EUR”) near their account link.
    - *When disabled:* The balance is only visible on the dedicated “My Wallet” page.
  - **Recommended value:** YES (for high visibility and convenience).
  - **Merchant scenario / example:** You want customers to always be aware of their available credit, encouraging them to use it.
- **Display Wallet Link in Customer Account Menu:**

  - **What this setting does:** Adds a direct link to the “My Wallet” page in the customer’s account navigation menu.
  - **Effect of changing this setting:**
    - *When enabled:* A “My Wallet” or “Store Credit” link appears in the left-hand menu of the customer’s account dashboard.
    - *When disabled:* Customers would need to navigate to the wallet page via another link (e.g., from the header if enabled).
  - **Recommended value:** YES (essential for easy access).
  - **Merchant scenario / example:** You want customers to easily find and manage their wallet funds.
- **Display Wallet Link in Footer:**

  - **What this setting does:** Adds a link to the “My Wallet” page in your store’s footer section.
  - **Effect of changing this setting:**
    - *When enabled:* A “My Wallet” or “Store Credit” link appears in the footer, accessible from any page.
    - *When disabled:* No wallet link in the footer.
  - **Recommended value:** NO (usually redundant if in header/account menu, but can be YES for maximum visibility).
  - **Merchant scenario / example:** If your customer account menu is not very prominent, or you want to highlight the wallet feature more broadly, you might enable this.
- **Display Wallet Link in Left/Right Column:**

  - **What this setting does:** Adds a link to the “My Wallet” page in one of your store’s side columns (if your theme supports them).
  - **Effect of changing this setting:**
    - *When enabled:* A “My Wallet” or “Store Credit” link appears in the chosen column.
    - *When disabled:* No wallet link in the columns.
  - **Recommended value:** NO (can clutter the layout, usually better in header/account).
  - **Merchant scenario / example:** If you have a very minimalist header/footer and want to use a column for navigation, this could be an option.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **General Settings** | Enable Module | YES | Activates/deactivates all wallet features. |
|  | Allow Customers to Top Up Wallet | YES | Customers can buy store credit. |
|  | Minimum Top-Up Amount | 10.00 | Lowest amount customer can add. |
|  | Maximum Top-Up Amount | 500.00 | Highest amount customer can add. |
|  | Allow Customers to Buy Gift Codes | YES | Customers can purchase gift cards. |
|  | Gift Code Expiry (Days) | 365 | Validity period for gift codes (0 for no expiry). |
|  | Wallet Balance Expiry (Days) | 0 | Validity period for wallet funds (0 for no expiry). |
|  | Send Expiry Reminder Email (Days Before Expiry) | 7 | Days before expiry to send a reminder email. |
|  | Allow Partial Payments with Wallet | YES | Customers can combine wallet with other payment methods. |
|  | Refund to Wallet Option | YES | Option to refund orders directly to customer’s wallet. |
|  | Enable Multi-Currency Support | YES (if multi-currency store) | Manages separate balances for each currency. |
| **Top-Up Bonuses** | Enable Top-Up Bonuses | YES | Activates bonus system for top-ups. |
|  | Bonus Tiers | (Custom) | Define bonus percentages for different top-up amounts. |
| **Display Options** | Display Wallet Balance in Header | YES | Shows balance in store header for logged-in users. |
|  | Display Wallet Link in Customer Account Menu | YES | Adds “My Wallet” link to customer account navigation. |
|  | Display Wallet Link in Footer | NO | Adds “My Wallet” link to store footer. |
|  | Display Wallet Link in Left/Right Column | NO | Adds “My Wallet” link to side columns. |

### 2.2 Dedicated Admin Screens & Controller Views

The module provides dedicated administration screens for managing customer wallets and gift codes.

#### 2.2.1 Wallet Management (Back Office > Modules > Prepaid Wallet & Store Credit > Wallets)

- **Screen Name & Menu Location:** **Wallets** (found under the “Prepaid Wallet & Store Credit” menu item, which appears under “Modules” or “Payment” depending on your PrestaShop version and menu configuration).
- **Available Actions & Settings:** This screen displays a list of all customers who have a wallet, along with their current balance, total top-ups, and other relevant information.
  - **Customer List:** A searchable and filterable table showing each customer’s name, email, current wallet balance (per currency if multi-currency is enabled), and total amount topped up.
  - **View/Edit Wallet:** Click on a customer’s row or an “Edit” icon to view their detailed wallet history and make adjustments.
    - **Add/Remove Funds:** Manually add or subtract funds from a customer’s wallet. This is useful for issuing goodwill credit, compensation, or correcting errors.
    - **View Transaction History:** See a detailed log of all wallet activities for that customer (top-ups, purchases, refunds, bonuses, expiry).
    - **Set Expiry Date:** Manually set or adjust the expiry date for specific funds in a customer’s wallet.
- **Effect of changes:**
  - *Adding/Removing Funds:* Directly impacts the customer’s available balance in the front office.
  - *Editing Expiry Dates:* Affects when funds become unusable for the customer.
  - *Viewing History:* Provides a complete audit trail for customer service and accounting.
- **Recommended workflow for daily store management:**
  1. **Customer Inquiry:** If a customer asks about their balance or a specific transaction, use this screen to quickly look up their wallet and history.
  2. **Issuing Credit:** If you need to give a customer a store credit (e.g., for a complaint, loyalty reward), navigate to their wallet and use the “Add Funds” option.
  3. **Refunds to Wallet:** When processing a refund for an order, you can choose to send the money to the customer’s wallet from the order details page. This action will be reflected here.

#### 2.2.2 Gift Code Management (Back Office > Modules > Prepaid Wallet & Store Credit > Codes)

- **Screen Name & Menu Location:** **Codes** (found under the “Prepaid Wallet & Store Credit” menu item).
- **Available Actions & Settings:** This screen allows you to generate, manage, and track all gift codes in your system.
  - **Code List:** A table showing all generated gift codes, their value, current status (active, redeemed, expired), who purchased it (if applicable), who redeemed it, and expiry date.
  - **Generate New Code:** Create new gift codes with a specified value, currency, and optional expiry date. These can be used for promotions, giveaways, or manual customer service credits.
  - **Edit Code:** Modify the value, status, or expiry of an existing code (if not yet redeemed).
  - **Delete Code:** Remove a code (only if not redeemed).
  - **Search/Filter:** Easily find specific codes by value, status, or customer.
- **Effect of changes:**
  - *Generating a code:* Creates a new, usable gift code that can be given to a customer.
  - *Editing a code:* Changes its properties, affecting its redeemability and value.
  - *Deleting a code:* Prevents it from being redeemed.
- **Recommended workflow for daily store management:**
  1. **Promotional Campaigns:** Generate a batch of gift codes for a marketing campaign (e.g., “10 EUR off for new sign-ups”).
  2. **Customer Service:** If a customer has an issue, you can quickly generate a unique gift code to compensate them.
  3. **Tracking Usage:** Monitor which codes have been redeemed and by whom, helping you analyze campaign effectiveness.

#### 2.2.3 Audit Log (Back Office > Modules > Prepaid Wallet & Store Credit > Audit)

- **Screen Name & Menu Location:** **Audit** (found under the “Prepaid Wallet & Store Credit” menu item).
- **Available Actions & Settings:** This screen provides a comprehensive log of all wallet-related activities across your store.
  - **Activity List:** A detailed table showing every transaction, top-up, redemption, admin adjustment, and expiry event.
  - **Details:** Each entry includes the date, customer involved, type of activity, amount, and any relevant notes (e.g., order ID, admin who made the change).
  - **Search/Filter:** Filter the audit log by customer, date range, or activity type to quickly find specific events.
- **Effect of changes:** This is a read-only log; no changes can be made here. It serves as a crucial record for accountability and troubleshooting.
- **Recommended workflow for daily store management:**
  1. **Troubleshooting:** If a customer reports an incorrect balance, use the audit log to trace all transactions and identify any discrepancies.
  2. **Compliance:** Maintain a clear record of all financial movements related to the wallet system for accounting and legal purposes.
  3. **Performance Review:** Analyze overall wallet activity to understand customer engagement and module usage.

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My customers can’t see the wallet options in the front office.**
A1:

- **Check Module Enablement:** Go to **Modules > Module Manager**, find “Prepaid Wallet & Store Credit,” and ensure the module is enabled.
- **Check General Settings:** On the module’s configuration page, ensure “Enable Module” is set to YES. Also, check specific display options like “Display Wallet Link in Customer Account Menu” are enabled.
- **Customer Login:** Wallet features are typically only visible to logged-in customers. Ask your customer to log in.
- **Theme Compatibility:** While the module is designed for compatibility, some highly customized themes might require minor adjustments. If you suspect a theme conflict, try switching to the default PrestaShop theme temporarily to see if the issue resolves.

**Q2: A customer’s wallet balance seems incorrect.**
A2:

- **Check Audit Log:** Go to **Modules > Prepaid Wallet & Store Credit > Audit**. Search for the customer’s name and review their entire transaction history. This will show all top-ups, purchases, refunds, bonuses, and admin adjustments.
- **Check Wallet Details:** Go to **Modules > Prepaid Wallet & Store Credit > Wallets**, find the customer, and click to view their detailed wallet. Compare the balance with the audit log.
- **Currency Issue:** If “Enable Multi-Currency Support” is active, ensure you are looking at the balance in the correct currency. A customer might have balances in multiple currencies.
- **Expiry:** Check if any funds have expired. The audit log will show expiry events.

**Q3: My customers are not receiving expiry reminder emails.**
A3:

- **Check Expiry Settings:** Ensure “Wallet Balance Expiry (Days)” is set to a value greater than 0, and “Send Expiry Reminder Email (Days Before Expiry)” is also set to a value greater than 0.
- **Cron Job:** The module likely uses a cron job to trigger these emails. Ensure your PrestaShop cron job is correctly configured and running regularly. (See Section 7.2 for `cron.php`).
- **Email Configuration:** Verify your PrestaShop email settings (**Advanced Parameters > E-mail**) are correctly configured and sending emails successfully. Test sending a general email from PrestaShop.
- **Spam Folders:** Advise customers to check their spam or junk folders.

**Q4: How do I clear the Smarty cache if I’m seeing old content or display issues?**
A4:

- Go to **Advanced Parameters > Performance** in your PrestaShop Back Office.
- Under the “Smarty” section, set “Template compilation” to “Recompile templates if the files have been updated” (or “Force compilation” temporarily).
- Click “Clear cache” in the top right corner.
- After clearing, you can revert “Template compilation” back to “Never recompile template files” for better performance.

**Q5: The module doesn’t look right on my custom theme.**
A5:

- **CSS Overrides:** Your custom theme’s CSS might be overriding the module’s default styles.
- **Inspect Element:** Use your browser’s developer tools (right-click, “Inspect”) to identify the CSS rules affecting the module’s elements. You can then add custom CSS to your theme’s stylesheet to override these.
- **Contact Developer:** If you’re not comfortable with CSS, contact your theme developer or MyPresta.eu support for assistance. Provide screenshots and your theme name.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the “Prepaid Wallet & Store Credit” module, designed for developers and webmasters.

### 4.1 Architecture Overview

The “Prepaid Wallet & Store Credit” module follows the standard PrestaShop MVC (Model-View-Controller) pattern. It extends core PrestaShop functionalities through hooks, custom controllers, and dedicated classes.

- **Controllers:** Handles front-office interactions (top-ups, code redemption, payment processing) and back-office administration (wallet/code management).
- **Models:** Custom `ObjectModel` classes (`PrepaidWalletService`, `PrepaidCodeService`, etc.) manage data persistence for wallets, codes, and transactions, interacting with dedicated database tables.
- **Views:** Smarty `.tpl` files render both front-office customer interfaces (wallet page, top-up forms) and back-office administration grids/forms.
- **Services:** Several helper classes encapsulate specific business logic (e.g., `PrepaidCartCreditService` for checkout integration, `PrepaidExpiry` for managing fund expiry).
- **Hooks:** The module extensively uses PrestaShop hooks to inject its functionality into various parts of the store (header, customer account, payment process, order details).

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `prepaidpayment/controllers/front/applycode.php`
  - **Class name & parent class:** `PrepaidPaymentApplyCodeModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** Handles the AJAX request for applying a gift code during the checkout process or on the dedicated redemption page. It validates the code and updates the cart’s credit.
- `prepaidpayment/controllers/front/buycode.php`
  - **Class name & parent class:** `PrepaidPaymentBuyCodeModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** Manages the process of customers purchasing gift codes. It handles the display of the gift code purchase form and the creation of the gift code product in the cart.
- `prepaidpayment/controllers/front/cron.php`
  - **Class name & parent class:** `PrepaidPaymentCronModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** This controller is designed to be called by a cron job. It executes background tasks such as checking for expired wallet funds, sending expiry reminder emails, and potentially other scheduled maintenance.
- `prepaidpayment/controllers/front/entercode.php`
  - **Class name & parent class:** `PrepaidPaymentEnterCodeModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** Displays the dedicated page where customers can enter a gift code to redeem it and add funds to their wallet.
- `prepaidpayment/controllers/front/index.php`
  - **Class name & parent class:** `PrepaidPaymentIndexModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** Likely serves as a default or fallback front controller, or a base for other front controllers. In many modules, this might redirect or display a general module page.
- `prepaidpayment/controllers/front/payment.php`
  - **Class name & parent class:** `PrepaidPaymentPaymentModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** Handles the payment process when a customer chooses to pay with their wallet. It validates the wallet balance against the order total and processes the payment.
- `prepaidpayment/controllers/front/redeempay.php`
  - **Class name & parent class:** `PrepaidPaymentRedeemPayModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** This controller likely manages the redemption of a gift code and its application to the current cart, potentially combining the logic of `applycode.php` and `payment.php` in a specific flow.
- `prepaidpayment/controllers/front/topup.php`
  - **Class name & parent class:** `PrepaidPaymentTopupModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** Manages the customer wallet top-up process. It displays the top-up form, handles the selection of top-up amounts (and associated bonuses), and adds the top-up product to the cart.

#### Back-Office Admin Controllers

- `prepaidpayment/controllers/admin/index.php`
  - **Class name & parent class:** `AdminPrepaidPaymentController` extending `ModuleAdminController`.
  - **Tab name and managed entity:** This controller serves as the main entry point for the module’s administration interface. It likely dispatches to various views (Wallets, Codes, Audit) and manages the overall configuration and data for the module. It doesn’t manage a single `ObjectModel` directly but orchestrates the management of `PrepaidWalletService` and `PrepaidCodeService` data.

### 4.3 Core Classes & Models (`classes/`)

- `prepaidpayment/classes/index.php`
  - **Purpose:** Typically an empty file or contains a basic `die()` statement to prevent direct directory listing, a common security practice.
- `prepaidpayment/classes/PrepaidAdmin.php`
  - **Purpose:** Likely a helper class for administrative tasks, potentially containing methods for rendering admin forms, handling AJAX requests within the back office, or specific data manipulations for admin views.
- `prepaidpayment/classes/PrepaidCartCreditService.php`
  - **Purpose:** Encapsulates the logic for applying wallet credit or gift codes to a customer’s cart during checkout. It handles calculations, validations, and updates to the cart total.
- `prepaidpayment/classes/PrepaidCodeService.php`
  - **Purpose:** Manages the lifecycle of gift codes.
  - **ObjectModel interaction:** Likely extends `ObjectModel` and interacts with a custom database table (e.g., `ps_prepaid_codes`).
  - **`$definition` fields:** Would include fields like `id_prepaid_code`, `code`, `value`, `id_currency`, `id_customer_buyer`, `id_customer_redeemer`, `date_add`, `date_redeem`, `date_expiry`, `active`.
  - **Key public methods:** `generateCode()`, `redeemCode()`, `getCodeByCode()`, `isCodeValid()`, `getCodesForCustomer()`.
- `prepaidpayment/classes/PrepaidCurrency.php`
  - **Purpose:** A helper class for handling multi-currency aspects of the wallet, ensuring correct currency conversions and display. It might extend `Currency` or provide utility methods for currency-aware operations.
- `prepaidpayment/classes/PrepaidExpiry.php`
  - **Purpose:** Manages the expiry logic for both gift codes and wallet balances. It contains methods to calculate expiry dates, check for expired funds, and potentially trigger expiry actions (e.g., setting funds to inactive).
- `prepaidpayment/classes/PrepaidThemeCompat.php`
  - **Purpose:** Provides compatibility layers or specific adjustments for different PrestaShop themes (e.g., Classic, Hummingbird) or versions, ensuring the module’s front-office elements display correctly across various environments.
- `prepaidpayment/classes/PrepaidTopupCart.php`
  - **Purpose:** Manages the specific cart logic when a customer is topping up their wallet. It might create a virtual product in the cart representing the top-up amount and handle associated bonuses.
- `prepaidpayment/classes/PrepaidWalletService.php`
  - **Purpose:** The core class for managing customer wallets.
  - **ObjectModel interaction:** Likely extends `ObjectModel` and interacts with a custom database table (e.g., `ps_prepaid_wallets` for balances and `ps_prepaid_wallet_history` for transactions).
  - **`$definition` fields:** For `ps_prepaid_wallets`: `id_prepaid_wallet`, `id_customer`, `id_currency`, `balance`, `date_update`. For `ps_prepaid_wallet_history`: `id_prepaid_wallet_history`, `id_customer`, `id_currency`, `amount`, `type` (topup, purchase, refund, bonus, expiry), `id_order`, `date_add`, `notes`.
  - **Key public methods:** `getBalance()`, `addFunds()`, `deductFunds()`, `getHistory()`, `getWalletsForCustomer()`, `processRefundToWallet()`.

### 4.4 JavaScript Assets (`views/js/`)

- `prepaidpayment/lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Likely Back-office.
  - **Details:** Provides autocomplete functionality, probably for searching customers or products within the admin interface, for example, when assigning a gift code to a specific customer or managing a wallet.
- `prepaidpayment/views/js/adminPrepaid.js`
  - **Scope:** Back-office.
  - **Details:** General JavaScript for the module’s admin pages. It might handle form submissions, AJAX updates for lists (wallets, codes), general UI enhancements, and interactions on the main configuration page.
- `prepaidpayment/views/js/adminPrepaidBonusBuilder.js`
  - **Scope:** Back-office.
  - **Details:** Specifically handles the dynamic creation and management of bonus tiers on the module’s configuration page. It likely adds/removes input fields for bonus percentages and minimum amounts, and validates these inputs.
- `prepaidpayment/views/js/adminPrepaidDashboard.js`
  - **Scope:** Back-office.
  - **Details:** JavaScript for the admin dashboard or overview screen, potentially handling data visualization, quick statistics, or interactive elements related to overall wallet usage.
- `prepaidpayment/views/js/adminPrepaidSelector.js`
  - **Scope:** Back-office.
  - **Details:** Manages selection components in the admin, possibly for choosing customers, currencies, or specific codes within various forms or lists.

### 4.5 CSS Stylesheets (`views/css/`)

- `prepaidpayment/lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Back-office admin styling.
  - **Details:** Styles for the autocomplete search tool used in the back office, ensuring dropdowns and suggestions are visually consistent.
- `prepaidpayment/views/css/admin_prepaidpayment.css`
  - **Scope:** Back-office admin styling.
  - **Details:** Core CSS for the module’s administration pages, styling forms, tables, buttons, and overall layout within the PrestaShop back office.
- `prepaidpayment/views/css/front-hummingbird.css`
  - **Scope:** Front-office customer styling (specifically for the Hummingbird theme).
  - **Details:** Provides specific styling adjustments or overrides to ensure optimal visual integration with the PrestaShop Hummingbird theme.
- `prepaidpayment/views/css/front.css`
  - **Scope:** Front-office customer styling (general).
  - **Details:** General CSS for the module’s front-office components, such as the “My Wallet” page, top-up forms, gift code redemption forms, and wallet display in the header/checkout.
- `prepaidpayment/views/css/prepaidpayment.css`
  - **Scope:** Both Front-office and Back-office (or general module-wide styles).
  - **Details:** Contains common styles used across both front and back office, or foundational styles for the module’s unique elements.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `prepaidpayment/views/templates/hook/adminOrder.tpl`
  - **Hook:** `displayAdminOrder` or similar.
  - **Output:** Displays wallet-related information or actions within the PrestaShop order detail page in the back office (e.g., option to refund to wallet, wallet payment details).
- `prepaidpayment/views/templates/hook/customerAccount-hummingbird.tpl`
  - **Hook:** `displayCustomerAccount` (specifically for Hummingbird theme).
  - **Output:** Adds a “My Wallet” link or block to the customer’s account dashboard, styled for the Hummingbird theme.
- `prepaidpayment/views/templates/hook/customerAccount.tpl`
  - **Hook:** `displayCustomerAccount`.
  - **Output:** Adds a “My Wallet” link or block to the customer’s account dashboard, for general themes.
- `prepaidpayment/views/templates/hook/orderDetail.tpl`
  - **Hook:** `displayOrderDetail` or similar.
  - **Output:** Displays wallet payment details on the customer’s order detail page in the front office.
- `prepaidpayment/views/templates/hook/payment.tpl`
  - **Hook:** `displayPayment` (PrestaShop 1.6) or `paymentOptions` (PrestaShop 1.7+).
  - **Output:** Renders the “Pay with Wallet” option on the checkout payment selection page.
- `prepaidpayment/views/templates/hook/paymentReturn.tpl`
  - **Hook:** `displayPaymentReturn`.
  - **Output:** Displays information about wallet payments on the order confirmation page after checkout.
- `prepaidpayment/views/templates/hook/paymentTop.tpl`
  - **Hook:** `displayPaymentTop`.
  - **Output:** May display a summary of wallet balance or an option to apply a gift code at the top of the payment page.
- `prepaidpayment/views/templates/hook/walletNav.tpl`
  - **Hook:** `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`.
  - **Output:** Renders the wallet balance or a link to the wallet page in various navigational areas of the store.

#### Admin templates (`views/templates/admin/`)

- `prepaidpayment/views/templates/admin/audit.tpl`
  - **Output:** Renders the audit log table and filtering options in the back office.
- `prepaidpayment/views/templates/admin/codes.tpl`
  - **Output:** Renders the list of gift codes, the form for generating new codes, and editing existing ones in the back office.
- `prepaidpayment/views/templates/admin/dashboard.tpl`
  - **Output:** Renders the main dashboard or overview page for the module in the back office, potentially showing statistics or quick links.
- `prepaidpayment/views/templates/admin/scopeSelector.tpl`
  - **Output:** A reusable template for selecting specific scopes, such as currencies or customer groups, within admin forms.
- `prepaidpayment/views/templates/admin/wallets.tpl`
  - **Output:** Renders the list of customer wallets, detailed wallet view, and options to add/remove funds in the back office.

#### Front-office templates (`views/templates/front/`)

- `prepaidpayment/views/templates/front/buycode.tpl`
  - **Output:** Renders the form and interface for customers to purchase gift codes.
- `prepaidpayment/views/templates/front/entercode.tpl`
  - **Output:** Renders the dedicated page where customers can enter a gift code to redeem it.
- `prepaidpayment/views/templates/front/topup.tpl`
  - **Output:** Renders the form and options for customers to top up their wallet, including bonus information.

#### Library templates (`prepaidpayment/lib/searchTool/views/scripts.tpl`)

- `prepaidpayment/lib/searchTool/views/scripts.tpl`
  - **Output:** Contains JavaScript or Smarty logic for the search tool, likely included in admin templates where autocomplete is needed.

### 4.7 Database Schema & Hooks Map

#### Database Tables

- `ps_prepaid_wallets`: Stores the current balance for each customer and currency.
  - `id_prepaid_wallet` (PK)
  - `id_customer` (FK to `ps_customer`)
  - `id_currency` (FK to `ps_currency`)
  - `balance` (decimal)
  - `date_upd` (datetime)
- `ps_prepaid_wallet_history`: Logs all transactions and changes to customer wallets.
  - `id_prepaid_wallet_history` (PK)
  - `id_customer` (FK to `ps_customer`)
  - `id_currency` (FK to `ps_currency`)
  - `amount` (decimal, positive for credit, negative for debit)
  - `type` (varchar, e.g., ‘topup’, ‘purchase’, ‘refund’, ‘bonus’, ‘expiry’, ‘admin\_add’, ‘admin\_deduct’)
  - `id_order` (FK to `ps_order`, nullable)
  - `id_prepaid_code` (FK to `ps_prepaid_codes`, nullable)
  - `notes` (text, e.g., “Admin adjustment”, “Gift code redemption”)
  - `date_add` (datetime)
  - `date_expiry` (datetime, nullable)
- `ps_prepaid_codes`: Stores information about generated and purchased gift codes.
  - `id_prepaid_code` (PK)
  - `code` (varchar, unique, the actual gift code string)
  - `value` (decimal, initial value of the code)
  - `id_currency` (FK to `ps_currency`)
  - `id_customer_buyer` (FK to `ps_customer`, nullable, if purchased by customer)
  - `id_customer_redeemer` (FK to `ps_customer`, nullable, once redeemed)
  - `date_add` (datetime)
  - `date_redeem` (datetime, nullable)
  - `date_expiry` (datetime, nullable)
  - `active` (tinyint, 0 or 1)
- `ps_prepaid_bonus_tiers`: Stores the configured top-up bonus rules.
  - `id_prepaid_bonus_tier` (PK)
  - `min_amount` (decimal)
  - `bonus_percentage` (decimal)
  - `position` (int)
- `ps_configuration`: Module settings are stored here with keys like `PREPAIDPAYMENT_ENABLED`, `PREPAIDPAYMENT_MIN_TOPUP`, etc.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Inject CSS/JS, display wallet balance for logged-in users. |
| `displayLeftColumn` | In the left column of the store. | Display wallet link. |
| `displayRightColumn` | In the right column of the store. | Display wallet link. |
| `displayFooter` | In the footer section of every page. | Display wallet link. |
| `displayCustomerAccount` | On the customer’s “My Account” page. | Add “My Wallet” link/block. |
| `displayPayment` (PS 1.6) / `paymentOptions` (PS 1.7+) | On the checkout payment selection page. | Display “Pay with Wallet” payment option. |
| `displayPaymentReturn` | On the order confirmation page after checkout. | Show wallet payment details. |
| `displayPaymentTop` | At the top of the payment page. | Potentially display wallet balance or gift code input. |
| `displayAdminOrder` | On the order detail page in the back office. | Add option to refund to wallet, show wallet payment info. |
| `displayOrderDetail` | On the customer’s order detail page in the front office. | Show wallet payment details. |
| `actionValidateOrder` | After an order has been successfully validated. | Deduct funds from wallet, record transaction. |
| `actionOrderStatusPostUpdate` | After an order’s status has been updated. | Potentially trigger refunds to wallet based on status change. |
| `actionFrontControllerSetMedia` | Before a front controller renders its content. | Add module-specific CSS and JS to front-office pages. |
| `actionAdminControllerSetMedia` | Before an admin controller renders its content. | Add module-specific CSS and JS to back-office pages. |
| `actionCronJob` (custom hook) | Triggered by the module’s cron controller. | Execute scheduled tasks like expiry checks and email reminders. |

## 5. Official Support & Updates

For official updates, technical support, and any further assistance with the “Prepaid Wallet & Store Credit” module, please refer to your customer account at MyPresta.eu. Our team is dedicated to providing comprehensive support and ensuring your module runs smoothly.

- **MyPresta.eu Order History & Downloads:** <https://mypresta.eu/my-account/orders/>
- **MyPresta.eu Support Contact:** <https://mypresta.eu/contact>
