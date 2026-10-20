---
title: "Cash on delivery with fee - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Cash on delivery with fee PrestaShop module by MyPresta.eu."
sidebar:
  label: "Cash on delivery with fee - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Cash on delivery with fee Module on MyPresta.eu](https://mypresta.eu/modules/payment-process/cash-on-delivery-with-fee.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/payment/cash-on-delivery-with-fee/)
>
> ---


# Cash on delivery with fee

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and are usually available on any modern hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the “Cash on delivery with fee” module, accessible directly after installation or by navigating to **Modules > Module Manager**, searching for “Cash on delivery with fee”, and clicking “Configure”.

#### **General Settings**

- **Disable \ / Enabled / Disabled (Main Module Status)**

  - **What this setting does:** This is the master switch to enable or disable the entire Cash on Delivery with fee payment method in your store.
  - **Effect of changing this setting:**
    - *When Enabled:* The COD payment option, along with its configured fees, will be available to customers during checkout.
    - *When Disabled:* The COD payment option will not be shown to customers, regardless of other settings.
  - **Recommended value:** `Enabled` if you intend to offer COD.
  - **Merchant scenario / example:** If you’re testing the module or temporarily want to stop offering COD, you would set this to `Disabled`.
- **Value (COD Fee Value)**

  - **What this setting does:** This field determines the base amount or percentage of the COD fee. The exact interpretation (fixed amount or percentage) depends on the “How to include the fee?” setting below.
  - **Effect of changing this setting:** Directly changes the cost added to COD orders.
  - **Recommended value:** Start with `0.00` and adjust based on your carrier fees.
  - **Merchant scenario / example:** If your carrier charges €2.50 for COD, you might enter `2.50`. If they charge 1% of the order, you might enter `1`.
- **How to include the fee?**

  - **What this setting does:** Defines how the “Value” (from the previous setting) is applied to the order total.
  - **Effect of changing this setting:**
    - *Include to shipping costs:* The COD fee is added to the shipping cost displayed to the customer. This can simplify the checkout display by combining charges.
    - *Include as a separate product/service:* The COD fee appears as a distinct line item in the cart summary and invoice, often labeled as “COD Fee” or similar. This provides maximum transparency.
  - **Recommended value:** `Include as a separate product/service` for clarity and legal compliance.
  - **Merchant scenario / example:** If you want customers to clearly see the COD charge as a separate item, choose “Include as a separate product/service”. If you prefer a cleaner, combined shipping cost, choose “Include to shipping costs”.
- **Order status after purchase with COD module**

  - **What this setting does:** Specifies the initial status of an order placed using the COD payment method.
  - **Effect of changing this setting:** Determines how COD orders appear in your Back Office immediately after they are placed.
  - **Recommended value:** `Payment accepted` (or a similar “awaiting payment” status you’ve configured). This allows you to differentiate COD orders that are confirmed but not yet physically paid.
  - **Merchant scenario / example:** You might set this to “Awaiting Cash on Delivery Payment” (if you’ve created such a status) to easily filter and manage COD orders that are pending physical payment upon delivery.
- **Show additional summary before the confirmation**

  - **What this setting does:** Controls whether an extra summary block is displayed on the final checkout step, just before the customer confirms their order.
  - **Effect of changing this setting:**
    - *When enabled:* A detailed breakdown including cart total, shipping, and COD fee will be shown.
    - *When disabled:* The standard PrestaShop summary will be used, which might not explicitly break down the COD fee as a separate line item.
  - **Recommended value:** `Enabled` for maximum transparency and legal compliance.
  - **Merchant scenario / example:** To ensure customers are fully aware of all charges before committing, especially the COD fee, enable this option.
- **Cart summary / Address summary / Cart total min value (CSS Selectors)**

  - **What this setting does:** These fields allow you to specify CSS selectors for various elements in your checkout page. The module uses these selectors to correctly inject the COD fee information into your theme’s checkout summary.
  - **Effect of changing this setting:** If your theme uses non-standard CSS classes for these elements, adjusting these selectors ensures the COD fee is displayed correctly. Incorrect values can lead to the fee not appearing or appearing in the wrong place.
  - **Recommended value:** Leave empty for auto-detection or use the default values provided by the module. Only change if the COD fee display is broken in your custom theme.
  - **Merchant scenario / example:** If you’ve installed a custom theme and the COD fee isn’t showing up in the cart summary, your web developer might need to inspect your theme’s HTML and update these selectors to match your theme’s structure.

#### **Fee Calculation & Conditions**

- **Disable \ / Enabled / Disabled (Max Cart Value Condition)**

  - **What this setting does:** Enables or disables a condition where the COD payment method is only available if the cart total is *below* a certain maximum value.
  - **Effect of changing this setting:**
    - *When Enabled:* Customers with carts exceeding the specified maximum value will not see COD as a payment option.
    - *When Disabled:* No maximum cart value restriction applies to COD.
  - **Recommended value:** `Disabled` unless you have specific reasons to limit high-value COD orders.
  - **Merchant scenario / example:** If you’ve had issues with fraudulent or uncollected high-value COD orders, you might enable this and set a `CODPRO_MOD_MAXCART_V` to €500 to mitigate risk.
- **CODPRO\_MOD\_MAXCART\_V (Maximum Cart Value)**

  - **What this setting does:** The specific monetary value for the maximum cart total condition.
  - **Effect of changing this setting:** Defines the upper limit for COD eligibility.
  - **Recommended value:** Set to a value that aligns with your risk tolerance for COD orders.
  - **Merchant scenario / example:** If `Disable \ / Enabled / Disabled (Max Cart Value Condition)` is enabled, and you set this to `500.00`, customers with orders over €500 cannot use COD.
- **Disable \ / Enabled / Disabled (Min Cart Value Condition)**

  - **What this setting does:** Enables or disables a condition where the COD payment method is only available if the cart total is *above* a certain minimum value.
  - **Effect of changing this setting:**
    - *When Enabled:* Customers with carts below the specified minimum value will not see COD as a payment option.
    - *When Disabled:* No minimum cart value restriction applies to COD.
  - **Recommended value:** `Disabled` unless you have specific reasons to avoid very small COD orders.
  - **Merchant scenario / example:** If the fixed COD fee makes very small orders unprofitable, you might enable this and set a `CODPRO_MOD_MINCART_V` to €10.
- **CODPRO\_MOD\_MINCART\_V (Minimum Cart Value)**

  - **What this setting does:** The specific monetary value for the minimum cart total condition.
  - **Effect of changing this setting:** Defines the lower limit for COD eligibility.
  - **Recommended value:** Set to a value that makes COD profitable for you.
  - **Merchant scenario / example:** If `Disable \ / Enabled / Disabled (Min Cart Value Condition)` is enabled, and you set this to `10.00`, customers with orders under €10 cannot use COD.
- **CODPRO\_CHARGEP\_V (Percentage Fee Value)**

  - **What this setting does:** This field defines the percentage value of the COD fee.
  - **Effect of changing this setting:** If “How to include the fee?” is set to a percentage-based option, this value will be used to calculate the fee.
  - **Recommended value:** `0.00` initially, adjust based on your carrier’s percentage charge.
  - **Merchant scenario / example:** If your carrier charges 1.5% of the order value for COD, you would enter `1.5` here.
- **CODPRO\_PERCENTAGE\_TYPE (Percentage Calculation Base)**

  - **What this setting does:** Determines what the percentage fee is calculated *on*.
  - **Effect of changing this setting:**
    - *Cart total (with shipping):* Percentage is calculated on the total amount including products and shipping.
    - *Cart total (without shipping):* Percentage is calculated only on the product subtotal.
  - **Recommended value:** `Cart total (with shipping)` as this is typically how carriers calculate their COD fees.
  - **Merchant scenario / example:** If your carrier charges 1% of the *entire* amount they collect from the customer (products + shipping), choose “Cart total (with shipping)”.
- **CODPRO\_CHARGEA\_V (Fixed Amount Fee Value)**

  - **What this setting does:** This field defines the fixed monetary amount of the COD fee.
  - **Effect of changing this setting:** If “How to include the fee?” is set to a fixed amount option, this value will be used.
  - **Recommended value:** `0.00` initially, adjust based on your carrier’s fixed charge.
  - **Merchant scenario / example:** If your carrier charges a flat €3.00 for COD, you would enter `3.00` here.
- **CODPRO\_MIN\_CHARGEV (Minimum Charge for Percentage Fee)**

  - **What this setting does:** If you’re using a percentage-based fee, this sets a minimum fixed amount that the COD fee will be, even if the calculated percentage is lower.
  - **Effect of changing this setting:** Ensures you always recover at least a certain amount for COD, especially on small orders where a percentage might be very low.
  - **Recommended value:** `0.00` (no minimum) or a small amount like `1.00` or `2.00` if you have a minimum cost.
  - **Merchant scenario / example:** If your percentage fee is 1%, and a €50 order would result in a €0.50 fee, but you want to ensure a minimum of €1.50, you’d set this to `1.50`.
- **CODPRO\_MAX\_CHARGEV (Maximum Charge for Percentage Fee)**

  - **What this setting does:** If you’re using a percentage-based fee, this sets a maximum fixed amount that the COD fee will be, even if the calculated percentage is higher.
  - **Effect of changing this setting:** Prevents the COD fee from becoming excessively high on very large orders.
  - **Recommended value:** `0.00` (no maximum) or a reasonable cap like `10.00` or `15.00`.
  - **Merchant scenario / example:** If your percentage fee is 1% and a €2000 order would result in a €20 fee, but you want to cap the COD fee at €10, you’d set this to `10.00`.
- **CODPRO\_FEETAX (Apply Tax to Fee)**

  - **What this setting does:** Determines whether the COD fee itself should be subject to VAT/taxes.
  - **Effect of changing this setting:**
    - *When enabled:* The COD fee will have tax applied according to the selected tax rule.
    - *When disabled:* The COD fee will be treated as tax-exempt.
  - **Recommended value:** `Enabled` if your local tax regulations require fees to be taxed. Consult your accountant.
  - **Merchant scenario / example:** In many countries, service fees like COD charges are subject to VAT. You would enable this to ensure compliance.
- **CODPRO\_FEETAXRULE (Tax Rule for Fee)**

  - **What this setting does:** If `CODPRO_FEETAX` is enabled, this dropdown allows you to select which PrestaShop tax rule applies to the COD fee.
  - **Effect of changing this setting:** The selected tax rate will be applied to the COD fee.
  - **Recommended value:** Select the appropriate tax rule for services in your country.
  - **Merchant scenario / example:** If you have a “Standard VAT (20%)” tax rule for services, you would select that here.

#### **Carrier-Specific Fees**

- **codpro\_carrier (Carrier Selection)**
  - **What this setting does:** This section allows you to define different COD fees for each shipping carrier you offer.
  - **Effect of changing this setting:** When a customer selects a specific carrier during checkout, the COD fee associated with that carrier will be applied instead of the general fee.
  - **Recommended value:** Configure fees for all carriers that offer COD.
  - **Merchant scenario / example:** If Carrier A charges €3.00 for COD and Carrier B charges 1.5% of the order, you can set these distinct fees here.

#### **Advanced Settings (Usually for Developers/Specific Scenarios)**

- **PS\_LANG\_DEFAULT / PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG (Language Settings)**

  - **What this setting does:** These are standard PrestaShop configuration values related to default language and employee form language. The module might display them for reference but typically doesn’t require modification here.
  - **Effect of changing this setting:** No direct effect on the module’s core functionality, but ensures correct language display in the Back Office.
  - **Recommended value:** Leave as default.
- **CODPRO\_ANALYTICS\_DEFAULT\_CHART / CODPRO\_ANALYTICS\_PERIOD / CODPRO\_ANALYTICS\_IMPACT\_DAYS / CODPRO\_ANALYTICS\_CHART\_WEEKS / CODPRO\_ANALYTICS\_CHART\_MONTHS (Analytics Settings)**

  - **What this setting does:** These settings relate to potential internal analytics or dashboard features within the module (if implemented). They control how data might be displayed or filtered.
  - **Effect of changing this setting:** Changes how any analytics data related to COD orders might be presented in the Back Office.
  - **Recommended value:** Leave as default unless you have specific analytics requirements.
  - **Merchant scenario / example:** If the module includes a dashboard, these settings might control the default view (e.g., last 7 days, last month) for COD order performance.

### 2.2 Dedicated Admin Screens & Controller Views

#### **4.2.1 AdminCodProCarriersFeesController (Back Office > Modules > Cash on delivery with fee > Carrier Fees)**

- **Screen Name & Menu Location:** “Carrier Fees” (usually found under the “Cash on delivery with fee” menu item in the PrestaShop Back Office).
- **Available Actions & Settings:** This screen provides a grid or list view to manage COD fees specifically for each shipping carrier. You can add new carrier-specific rules, edit existing ones, or delete them. For each carrier, you can define:
  - Whether the fee is a fixed amount or a percentage.
  - The specific fixed amount or percentage value.
  - Minimum and maximum charges for percentage fees.
  - Whether tax applies and which tax rule to use.
- **Effect of changes:** Any rules configured here will override the general COD fee settings for the specified carriers. If a carrier has a rule here, that rule’s fee will be applied. If a carrier is not listed here, the general COD fee settings will apply.
- **Recommended workflow for daily store management:** Regularly review this section if your carrier contracts or COD charges change. Add new carriers as you introduce them to your store and configure their specific COD fees.

#### **4.2.2 AdminCodProCarriersRangeFeesController (Back Office > Modules > Cash on delivery with fee > Range Fees)**

- **Screen Name & Menu Location:** “Range Fees” (usually found under the “Cash on delivery with fee” menu item in the PrestaShop Back Office).
- **Available Actions & Settings:** This screen allows you to define COD fees based on the total value of the customer’s cart. You can set up different fee structures for various price ranges (e.g., orders from €0-€50, €50-€100, etc.). For each range, you can define:
  - The minimum and maximum cart value for the range.
  - Whether the fee is a fixed amount or a percentage.
  - The specific fixed amount or percentage value.
  - Minimum and maximum charges for percentage fees within that range.
  - Whether tax applies and which tax rule to use.
- **Effect of changes:** These range-based rules provide an additional layer of flexibility. If a customer’s cart total falls within a defined range, the fee specified for that range will be applied. These rules can interact with carrier-specific rules, potentially allowing for very granular control (e.g., Carrier A charges X for orders under €50, and Y for orders over €50).
- **Recommended workflow for daily store management:** Use this section to implement dynamic pricing for COD based on order value. This is particularly useful for managing risk on high-value orders or making COD more attractive for mid-range orders.

#### **4.2.3 index.php (Back Office > Modules > Cash on delivery with fee > Dashboard/Analytics)**

- **Screen Name & Menu Location:** This `index.php` controller typically serves as a placeholder or a default entry point for a module’s admin section. In this module’s context, it might be used to display a dashboard or analytics related to COD orders.
- **Available Actions & Settings:** If this controller is used for a dashboard, it would likely display charts, statistics, or key performance indicators (KPIs) related to COD orders (e.g., number of COD orders, total revenue from COD, average COD fee collected). There might be filters for date ranges or other parameters.
- **Effect of changes:** Interacting with a dashboard here would only change the displayed data, not the store’s configuration.
- **Recommended workflow for daily store management:** Periodically check this dashboard (if available) to monitor the performance and impact of your COD payment method.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Main Configuration** | Enabled / Disabled | Enabled | Master switch for COD payment method. |
|  | Value (Base Fee) | 0.00 | Default fee amount/percentage. |
|  | How to include the fee? | Include as a separate product/service | Determines how fee appears in cart/invoice. |
|  | Order status after purchase | Payment accepted | Initial status for COD orders. |
|  | Show additional summary | Enabled | Displays detailed fee breakdown before confirmation. |
|  | Max Cart Value Condition | Disabled | Restricts COD for orders above a value. |
|  | Max Cart Value | 0.00 | The specific maximum cart value. |
|  | Min Cart Value Condition | Disabled | Restricts COD for orders below a value. |
|  | Min Cart Value | 0.00 | The specific minimum cart value. |
|  | Percentage Fee Value | 0.00 | The percentage value for COD fee. |
|  | Percentage Calculation Base | Cart total (with shipping) | What the percentage is calculated on. |
|  | Fixed Amount Fee Value | 0.00 | The fixed amount value for COD fee. |
|  | Minimum Charge (for %) | 0.00 | Ensures a minimum fee for percentage calculations. |
|  | Maximum Charge (for %) | 0.00 | Caps the fee for percentage calculations. |
|  | Apply Tax to Fee | Enabled (if applicable) | Determines if the COD fee is taxed. |
|  | Tax Rule for Fee | Select appropriate tax rule | Which tax rule applies to the fee. |
| **AdminCodProCarriersFees** | Carrier-specific fee rules | Configure as needed | Overrides general fee for specific carriers. |
| **AdminCodProCarriersRangeFees** | Order value range fee rules | Configure as needed | Applies different fees based on cart total ranges. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The COD fee isn’t showing up on my checkout page, or it’s in the wrong place.**
A1: This usually happens with custom themes.
- **Check “Show additional summary before the confirmation”:** Make sure this is `Enabled` in the module’s main configuration.
- **CSS Selectors:** If your theme uses non-standard CSS classes, the module might not find the right spots to inject the fee. Go to the module’s configuration page and check the “Cart summary”, “Address summary”, and “Cart total min value” CSS selector fields. You might need a web developer to inspect your theme’s HTML and provide the correct selectors.
- **Clear Cache:** Always clear your PrestaShop cache (Advanced Parameters > Performance > Clear Cache) after making configuration changes.

**Q2: I’ve set up a fee, but it’s not being applied to orders.**
A2:
- **Module Enabled:** Ensure the main “Enabled / Disabled” switch for the module is set to `Enabled`.
- **Fee Value:** Double-check that you’ve entered a non-zero “Value” in the main configuration, or configured specific fees in the “Carrier Fees” or “Range Fees” sections.
- **Conditions Met:** Verify that the customer’s cart meets any “Min Cart Value” or “Max Cart Value” conditions you’ve set.
- **Carrier-Specific Overrides:** If you’ve configured fees in “Carrier Fees”, ensure the customer is selecting one of those carriers. If not, the general fee should apply.
- **Tax Rule:** If you’re using a tax rule for the fee, ensure the tax rule itself is correctly configured in PrestaShop.

**Q3: How do I translate the module’s text (e.g., “COD Fee”) into other languages?**
A3: You can translate module strings directly within PrestaShop:
- Navigate to **International > Translations**.
- Select “Installed modules translations”.
- Choose your theme, your language, and then select “Cash on delivery with fee” from the module dropdown.
- You’ll see a list of all translatable strings from the module. Enter your translations and save.

**Q4: Can I offer COD only for specific customer groups or countries?**
A4: The “Cash on delivery with fee” module itself does not have built-in options for customer group or country restrictions. However, PrestaShop’s core payment module restrictions can be used:
- Go to **Shop Parameters > Order Settings > Payment**.
- You can restrict payment methods by currency, country, or group. Find “Cash on delivery with fee” and apply your desired restrictions there.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Cash on delivery with fee” module (`codpro`) follows a standard PrestaShop module architecture, extending `PaymentModule` to integrate into the checkout flow. It utilizes several front and admin controllers for specific functionalities like payment validation, carrier-specific fee management, and range-based fee configurations. The module heavily relies on PrestaShop’s hook system to inject its logic and display elements at various stages of the front-office (checkout, order confirmation, invoice) and back-office (order view). Configuration is primarily stored in `ps_configuration`, with custom tables likely used for carrier and range-based fee definitions.

### 4.2 Controllers (`controllers/`)

#### **Front-Office Controllers**

- `controllers/front/index.php`
  - Class name: `CodProIndexModuleFrontController` (likely extends `ModuleFrontController`)
  - Responsibility: This controller might serve as a default entry point or handle basic routing for front-office module actions. Given the module’s purpose, it could be a placeholder or used for simple AJAX requests related to fee calculation updates during checkout.
- `controllers/front/validation.php`
  - Class name: `CodProValidationModuleFrontController` (likely extends `ModuleFrontController`)
  - Responsibility: This is the critical controller for processing the payment when a customer chooses “Cash on delivery with fee”. It handles the final validation of the order, applies the calculated COD fee to the cart, and redirects the customer to the order confirmation page. It interacts with the main `codpro.php` module class to retrieve fee settings and update the order.

#### **Back-Office Admin Controllers**

- `controllers/admin/AdminCodProCarriersFees.php`
  - Class name: `AdminCodProCarriersFeesController` (extends `ModuleAdminController`)
  - Tab name: “Carrier Fees” (or similar, accessible via the module’s menu).
  - Managed entity: `Configuration` (though it manages specific configuration entries related to carriers).
  - Responsibility: Provides the interface for managing COD fees on a per-carrier basis. It displays a list of configured carrier fees, allows adding new ones, and editing/deleting existing entries. It likely uses PrestaShop’s `HelperList` and `HelperForm` for its UI.
- `controllers/admin/AdminCodProCarriersRangeFees.php`
  - Class name: `AdminCodProCarriersRangeFeesController` (extends `ModuleAdminController`)
  - Tab name: “Range Fees” (or similar, accessible via the module’s menu).
  - Managed entity: `CodProTotal` (likely a custom `ObjectModel` for range-based fees).
  - Responsibility: Manages COD fees based on order total ranges. It provides a grid to define, edit, and delete fee rules for different cart value ranges. This controller also leverages PrestaShop’s `HelperList` and `HelperForm` for its administrative interface.
- `controllers/admin/index.php`
  - Class name: `AdminCodProIndexController` (likely extends `ModuleAdminController`)
  - Tab name: Placeholder or Dashboard.
  - Managed entity: None directly.
  - Responsibility: This controller likely serves as the entry point for a module dashboard or a default view when navigating to the module’s admin section. It might display analytics or a summary of COD orders.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes in the `classes/` directory. This suggests that the core logic for managing carrier and range fees might be handled directly within the `AdminCodProCarriersFeesController` and `AdminCodProCarriersRangeFeesController` using direct database interactions or by defining simple arrays for configuration. However, `AdminCodProCarriersRangeFeesController` managing `codprototal` implies there *should* be an `ObjectModel` named `CodProTotal` (or similar) in the `classes/` directory, even if not explicitly listed in the dossier. If not, it means direct SQL queries are used, which is less ideal.

### 4.4 JavaScript Assets (`views/js/`)

- `views/js/adminCodProCarriersFees.js`
  - Scope: Back-office (AdminCodProCarriersFeesController).
  - Functionality: Likely handles dynamic behavior on the carrier fees configuration page. This could include AJAX calls for saving/loading data, form validation, or interactive elements for adding/removing carrier fee rules.
- `views/js/adminCodProDashboard.js`
  - Scope: Back-office (AdminCodProIndexController or similar dashboard view).
  - Functionality: Responsible for rendering charts, updating statistics, and handling interactive elements on the module’s dashboard. It might use charting libraries (e.g., Chart.js) and make AJAX requests to fetch analytical data.
- `views/js/codpro-checkout.js`
  - Scope: Front-office (Checkout page).
  - Functionality: This is crucial for the front-end user experience. It listens for changes in payment method selection (specifically to “Cash on delivery with fee”), updates the order summary dynamically to reflect the COD fee, and potentially handles AJAX requests to recalculate fees if shipping carrier or cart contents change. It ensures the fee is visible before order confirmation.

### 4.5 CSS Stylesheets (`views/css/`)

- `views/css/admin_codpro.css`
  - Scope: Back-office (Admin panel).
  - Functionality: Provides styling for the module’s configuration pages, carrier fee management, range fee management, and any dashboard elements. It ensures a consistent look and feel within the PrestaShop Back Office.
  - Key selectors: Likely targets specific IDs or classes within the module’s admin forms and lists (e.g., `.codpro-admin-form`, `.codpro-dashboard-chart`).
- `views/css/codpro.css`
  - Scope: Front-office (Checkout page, order confirmation, invoice).
  - Functionality: Styles the display of the COD fee in the checkout summary, payment options, order confirmation page, and potentially the PDF invoice. It ensures the fee is clearly visible and integrated with the store’s theme.
  - Key selectors: Targets elements where the COD fee is injected (e.g., `.codpro-fee-display`, `.payment_option_codpro`, `.order-summary-cod-fee`). Developers might need to override these in their theme for perfect visual integration.

### 4.6 Smarty Template Structure (`views/templates/`)

#### **Hook templates (`views/templates/hook/`)**

- `views/templates/hook/confirmation.tpl`
  - Hook: `paymentReturn` or similar.
  - Outputs: The COD fee details on the order confirmation page after a successful COD order.
- `views/templates/hook/displayAdminOrder16.tpl`
  - Hook: `displayAdminOrder` (for PrestaShop 1.6).
  - Outputs: Additional information about the COD fee within the order details page in the PrestaShop 1.6 Back Office.
- `views/templates/hook/displayAdminOrder17.tpl`
  - Hook: `displayAdminOrder` (for PrestaShop 1.7+).
  - Outputs: Similar to `displayAdminOrder16.tpl`, but adapted for the PrestaShop 1.7+ Back Office order detail page layout.
- `views/templates/hook/displayOrderDetail.tpl`
  - Hook: `displayOrderDetail` (front-office customer order history).
  - Outputs: Displays the COD fee as part of the order summary when a customer views their past order details in their “My Account” section.
- `views/templates/hook/payment.tpl`
  - Hook: `displayPaymentOptions` or `paymentOptions`.
  - Outputs: The “Cash on delivery with fee” payment option on the checkout page, including the dynamically calculated fee amount.
- `views/templates/hook/pdf.tpl`
  - Hook: `displayPDFInvoice`.
  - Outputs: The COD fee as a line item on the generated PDF invoice for the order.

#### **Front-office templates (`views/templates/front/`)**

- `views/templates/front/validation.tpl`
  - Purpose: This template is likely used by the `validation.php` front controller. It might display a simple message during the payment validation process or serve as a redirect page.

### 4.7 Database Schema & Hooks Map

#### **Database Tables**

- `ps_configuration`: Stores all general module settings (e.g., `CODPRO_MOD_MAXCART_V`, `CODPRO_CHARGEP_V`, `CODPRO_FEETAX`).
- `ps_codpro_carrier_fees` (likely): A custom table to store carrier-specific COD fee rules.
  - Columns: `id_codpro_carrier_fee`, `id_carrier`, `fee_type` (fixed/percentage), `fee_value`, `min_charge`, `max_charge`, `tax_enabled`, `id_tax_rule`.
- `ps_codpro_range_fees` (likely): A custom table to store order value range-based COD fee rules.
  - Columns: `id_codpro_range_fee`, `min_value`, `max_value`, `fee_type`, `fee_value`, `min_charge`, `max_charge`, `tax_enabled`, `id_tax_rule`.

#### **Registered Hooks Table**

| Hook Name | Scope | Execution Timing | Technical Purpose |
| --- | --- | --- | --- |
| `displayHeader` | Front-Office | In the `<head>` section of all pages. | To include front-office CSS (`codpro.css`) and JS (`codpro-checkout.js`) on relevant pages (e.g., checkout). |
| `displayPaymentOptions` | Front-Office | During payment method selection in checkout. | To display “Cash on delivery with fee” as a payment option, including the calculated fee. |
| `paymentOptions` | Front-Office | PrestaShop 1.6 equivalent of `displayPaymentOptions`. | To display “Cash on delivery with fee” as a payment option. |
| `paymentReturn` | Front-Office | On the order confirmation page after payment. | To display the COD fee details on the confirmation page. |
| `displayPaymentReturn` | Front-Office | PrestaShop 1.6 equivalent of `paymentReturn`. | To display the COD fee details on the confirmation page. |
| `displayPDFInvoice` | Front-Office (PDF Generation) | When a PDF invoice is generated. | To add the COD fee as a line item on the invoice. |
| `displayOrderDetail` | Front-Office (My Account) | When a customer views their order details. | To show the COD fee in the customer’s order history. |
| `displayAdminOrder` | Back-Office (Order View) | When an admin views an order in the Back Office. | To display COD fee details within the order summary for admin review. |
| `ActionAdminControllerSetMedia` | Back-Office (Admin Pages) | Before an admin controller renders its view. | To include back-office CSS (`admin_codpro.css`) and JS (`adminCodProCarriersFees.js`, `adminCodProDashboard.js`) on the module’s admin pages. |
| `actionValidateOrder` | Back-Office (Order Processing) | After an order has been validated. | To potentially perform additional actions or data logging related to COD orders. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please refer to your customer account at MyPresta.eu.

- **MyPresta.eu Order History & Downloads:** <https://mypresta.eu/my-account/orders/>
- **MyPresta.eu Support:** <https://mypresta.eu/contact>
