---
title: "Cash on delivery with order summary - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Cash on delivery with order summary PrestaShop module by MyPresta.eu."
sidebar:
  label: "Cash on delivery with order summary"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Cash on delivery with order summary Module on MyPresta.eu](https://mypresta.eu/modules/payment-process/cash-on-delivery-with-order-summary.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/payment/cash-on-delivery-with-order-summary/)
>
> ---


# Cash on delivery with order summary

## 1. Requirements & Compatibility

-   **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **PHP Compatibility**: PHP 5.6 - 8.5
-   **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required by PrestaShop itself and are sufficient for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen where you set up the core behavior and fees for your Cash on Delivery payment method.

-   **Menu Location:** Back Office > Modules > Module Manager > Search for "Cash on delivery with order summary" > Click "Configure".

#### General Settings

1.  **Disable COD for specific carriers**
    -   **What this setting does:** Allows you to prevent the Cash on Delivery payment option from being available if a customer chooses certain shipping carriers.
    -   **Effect of changing this setting:**
        -   *When enabled (checked for specific carriers):* If a customer selects one of the chosen carriers during checkout, the Cash on Delivery payment option will not appear.
        -   *When disabled (unchecked for all carriers):* Cash on Delivery will be available regardless of the chosen shipping carrier (unless other restrictions apply).
    -   **Recommended value:** Depends on your shipping logistics. If some carriers do not support COD or charge excessive fees, enable this.
    -   **Merchant scenario / example:** You use a specific courier service that doesn't handle cash payments. You would check that carrier in this list to disable COD for them.

2.  **How to include the fee?**
    -   **What this setting does:** Determines how the Cash on Delivery fee is calculated and applied to the order.
    -   **Effect of changing this setting:**
        -   *Include to shipping costs:* The COD fee will be added directly to the shipping cost shown to the customer. This can simplify the checkout display but might obscure the separate COD charge.
        -   *Include as a separate product:* The COD fee will appear as a distinct line item in the cart and order summary, often labeled as "Cash on Delivery Fee" or similar. This provides maximum transparency.
    -   **Recommended value:** "Include as a separate product" for clarity and legal compliance, especially in the EU.
    -   **Merchant scenario / example:** To clearly show customers the exact cost of using COD, you would select "Include as a separate product."

3.  **Order status after purchase with COD module**
    -   **What this setting does:** Sets the initial status of an order placed using the Cash on Delivery method.
    -   **Effect of changing this setting:**
        -   *When set to "Payment accepted":* The order will immediately be marked as paid, which might be misleading since cash hasn't been collected yet.
        -   *When set to "Awaiting Cash on Delivery validation" (or similar):* The order will be in a pending state, indicating that payment is expected upon delivery. This is generally safer and more accurate.
    -   **Recommended value:** A pending status like "Awaiting Cash on Delivery validation" or "Payment pending" to accurately reflect the payment status.
    -   **Merchant scenario / example:** To avoid prematurely shipping an order that hasn't been paid for, you'd set this to a pending status.

4.  **Show additional summary before the confirmation**
    -   **What this setting does:** Controls whether the module displays the dedicated pre-confirmation order summary page. This is the module's core compliance feature.
    -   **Effect of changing this setting:**
        -   *When enabled:* After selecting COD, customers will see a detailed summary of their order, including all costs, before they can click the final "Confirm Order" button.
        -   *When disabled:* The module will skip this summary page, and customers will proceed directly to the standard PrestaShop order confirmation (which might not be legally compliant in some regions).
    -   **Recommended value:** **Enabled**. This is a key feature for legal compliance and customer trust.
    -   **Merchant scenario / example:** To comply with EU consumer laws requiring a clear order summary before final confirmation, you **must** enable this setting.

#### Cart Value Restrictions

5.  **Cart total min value**
    -   **What this setting does:** Sets the minimum total value an order must have for the Cash on Delivery payment option to be available.
    -   **Effect of changing this setting:**
        -   *When set to a value (e.g., 10.00):* If the customer's cart total is below this amount, Cash on Delivery will not be offered as a payment option.
        -   *When left empty or set to 0:* There will be no minimum cart value restriction for COD.
    -   **Recommended value:** Set a reasonable minimum if the operational cost of processing small COD orders is too high. Otherwise, leave empty.
    -   **Merchant scenario / example:** If the cost of processing a COD order (courier fees, administrative work) is €5, you might set a minimum cart value of €10 to ensure profitability.

6.  **Cart total max value**
    -   **What this setting does:** Sets the maximum total value an order can have for the Cash on Delivery payment option to be available.
    -   **Effect of changing this setting:**
        -   *When set to a value (e.g., 500.00):* If the customer's cart total exceeds this amount, Cash on Delivery will not be offered as a payment option.
        -   *When left empty or set to 0:* There will be no maximum cart value restriction for COD.
    -   **Recommended value:** Set a maximum if you want to limit your risk for very high-value orders that might be subject to fraud or non-collection. Otherwise, leave empty.
    -   **Merchant scenario / example:** To mitigate the risk of non-payment for very expensive orders, you might set a maximum cart value of €200 for COD.

#### Cash on Delivery Fee Settings

7.  **COD Fee Type (Percentage or Amount)**
    -   **What this setting does:** Determines whether the COD fee is a fixed amount or a percentage of the order total.
    -   **Effect of changing this setting:**
        -   *Percentage:* The fee will be calculated as a percentage of the order total.
        -   *Amount:* The fee will be a fixed monetary value.
    -   **Recommended value:** Choose based on your cost structure. If your costs scale with order value, use percentage. If it's a flat handling fee, use amount.
    -   **Merchant scenario / example:** If your bank charges a percentage of the transaction value for cash handling, you'd choose "Percentage." If your courier charges a flat fee for COD, you'd choose "Amount."

8.  **COD Fee Value (Percentage)** (Appears if "Percentage" is selected above)
    -   **What this setting does:** The percentage value to be charged as the COD fee.
    -   **Effect of changing this setting:**
        -   *When set to 5:* The COD fee will be 5% of the order total.
    -   **Recommended value:** A percentage that covers your costs without deterring customers.
    -   **Merchant scenario / example:** To cover a 2% bank charge for cash deposits, you might set this to "2".

9.  **COD Fee Value (Amount)** (Appears if "Amount" is selected above)
    -   **What this setting does:** The fixed monetary value to be charged as the COD fee.
    -   **Effect of changing this setting:**
        -   *When set to 2.50:* The COD fee will be €2.50 (or your default currency) regardless of the order total.
    -   **Recommended value:** A fixed amount that covers your flat handling costs.
    -   **Merchant scenario / example:** If your courier charges a fixed €3 for COD service, you would set this to "3".

10. **Minimum COD Fee**
    -   **What this setting does:** Sets a minimum amount for the COD fee, regardless of the percentage calculation.
    -   **Effect of changing this setting:**
        -   *When set to 1.00 and percentage calculates 0.50:* The fee will be 1.00.
        -   *When set to 1.00 and percentage calculates 2.00:* The fee will be 2.00.
    -   **Recommended value:** Useful if you have a minimum cost associated with COD even for small orders.
    -   **Merchant scenario / example:** If 5% of a €10 order is only €0.50, but your minimum handling cost is €1, you'd set this to "1.00".

11. **Maximum COD Fee**
    -   **What this setting does:** Sets a maximum amount for the COD fee, regardless of the percentage calculation.
    -   **Effect of changing this setting:**
        -   *When set to 10.00 and percentage calculates 15.00:* The fee will be 10.00.
        -   *When set to 10.00 and percentage calculates 5.00:* The fee will be 5.00.
    -   **Recommended value:** Useful to prevent the COD fee from becoming excessively high on very large orders.
    -   **Merchant scenario / example:** To ensure the COD fee doesn't become prohibitive for large orders, you might cap it at €15.

12. **Apply Tax to COD Fee**
    -   **What this setting does:** Determines whether the Cash on Delivery fee itself is subject to sales tax.
    -   **Effect of changing this setting:**
        -   *When enabled:* You will be able to select a tax rule to apply to the COD fee.
        -   *When disabled:* The COD fee will be tax-exempt.
    -   **Recommended value:** Consult your local tax regulations. In many regions, payment processing fees are taxable.
    -   **Merchant scenario / example:** If your country's tax laws require you to charge VAT on payment service fees, you would enable this and select the appropriate tax rule.

13. **Tax Rule for COD Fee** (Appears if "Apply Tax to COD Fee" is enabled)
    -   **What this setting does:** Allows you to select an existing tax rule from your PrestaShop store to apply to the COD fee.
    -   **Effect of changing this setting:** The selected tax rate will be applied to the calculated COD fee.
    -   **Recommended value:** Select the tax rule that corresponds to payment processing fees in your jurisdiction.
    -   **Merchant scenario / example:** If you have a "VAT 20%" tax rule, you would select it here to apply 20% VAT to the COD fee.

#### Advanced Display Settings

14. **CSS Selector for Cart Total**
    -   **What this setting does:** Allows you to specify the CSS selector for the element that displays the total cart value on your checkout page. This helps the module accurately update the total when a COD fee is applied.
    -   **Effect of changing this setting:** If correctly set, the module can dynamically update the total on the checkout page to include the COD fee. If incorrect, the total might not update, leading to confusion.
    -   **Recommended value:** Leave empty unless you experience display issues with the total not updating. If needed, consult your theme's developer or use browser developer tools to find the correct selector (e.g., `.cart-total-value`).
    -   **Merchant scenario / example:** If your theme uses a custom class like `.mytheme-total-price` for the cart total, you would enter that here.

15. **CSS Selector for Cart Subtotal**
    -   **What this setting does:** Similar to the cart total, this specifies the CSS selector for the cart subtotal.
    -   **Effect of changing this setting:** Helps the module correctly identify and potentially update the subtotal display.
    -   **Recommended value:** Leave empty unless display issues occur.
    -   **Merchant scenario / example:** If your theme has a specific element for the subtotal, you might need to enter its selector here.

16. **CSS Selector for Cart Shipping**
    -   **What this setting does:** Similar to the cart total, this specifies the CSS selector for the shipping cost display.
    -   **Effect of changing this setting:** Helps the module correctly identify and potentially update the shipping cost display, especially if the COD fee is included in shipping.
    -   **Recommended value:** Leave empty unless display issues occur.
    -   **Merchant scenario / example:** If your theme has a specific element for the shipping cost, you might need to enter its selector here.

17. **COD Logo**
    -   **What this setting does:** Allows you to upload a custom logo that will be displayed next to the Cash on Delivery payment option during checkout.
    -   **Effect of changing this setting:**
        -   *When uploaded:* A visual icon or logo will appear, making the COD option more prominent and visually appealing.
        -   *When empty:* No custom logo will be displayed.
    -   **Recommended value:** Upload a small, clear logo (e.g., a cash icon) to enhance the user experience.
    -   **Merchant scenario / example:** To make the COD option stand out, you might upload a small image of banknotes or coins.

#### Analytics Settings (Internal Module Use)

These settings are typically for internal module analytics and usually do not require merchant intervention.

18. **CODPRO_ANALYTICS_DEFAULT_CHART, CODPRO_ANALYTICS_PERIOD, CODPRO_ANALYTICS_IMPACT_DAYS, CODPRO_ANALYTICS_CHART_WEEKS, CODPRO_ANALYTICS_CHART_MONTHS**
    -   **What these settings do:** These are internal configuration keys used by the module for potential future analytics features or dashboard displays within the module's own administration. They control how data might be collected or displayed for performance monitoring.
    -   **Effect of changing these settings:** Unlikely to have a direct, immediate impact on the front-office customer experience. Primarily affects potential back-office reporting.
    -   **Recommended value:** Leave at their default values.
    -   **Merchant scenario / example:** These are not typically adjusted by merchants.

### 2.2 Dedicated Admin Screens & Controller Views

The module provides two additional administration screens for more granular control over COD fees, especially useful for complex shipping and pricing strategies.

#### 2.2.1 AdminCodProCarriersFeesController: Carrier-Specific COD Fees

-   **Screen Name & Menu Location:** Back Office > Modules > Module Manager > Search for "Cash on delivery with order summary" > Click "Configure" > Look for a tab or link labeled "Carrier Fees" or similar (this might be integrated into the main config or a separate menu item depending on PrestaShop version).
-   **Available Actions & Settings:** This screen typically presents a grid or table where you can define different Cash on Delivery fees based on the selected shipping carrier. You can add, edit, or delete these carrier-specific fee rules.
    -   **Carrier Selection:** Choose a specific shipping carrier.
    -   **Fee Type:** Select whether the fee is a fixed amount or a percentage.
    -   **Fee Value:** Enter the amount or percentage.
    -   **Tax Rule:** Apply a specific tax rule to this carrier's COD fee.
-   **Effect of changes:** When a customer selects a carrier for which you've defined a specific COD fee here, that fee will override the general COD fee set in the main module configuration. This allows for highly customized pricing.
-   **Recommended workflow for daily store management:**
    1.  Access this screen if you need to charge different COD fees based on which courier delivers the package.
    2.  Click "Add new carrier fee" (or similar button).
    3.  Select the carrier, define the fee type (amount/percentage), value, and tax rule.
    4.  Save your changes.
    5.  Review the list to ensure all carrier-specific fees are correctly set.
-   **Merchant scenario / example:** Your national postal service charges a flat €2 for COD, but a private express courier charges 3% of the order value. You would use this screen to set these distinct fees for each carrier.

#### 2.2.2 AdminCodProCarriersRangeFeesController: Carrier & Total-Range Specific COD Fees

-   **Screen Name & Menu Location:** Back Office > Modules > Module Manager > Search for "Cash on delivery with order summary" > Click "Configure" > Look for a tab or link labeled "Range Fees" or similar.
-   **Available Actions & Settings:** This screen provides an even more advanced level of fee control. You can define COD fees that vary not only by carrier but also by the *total value of the customer's cart*. This is often presented as a grid where you define ranges (e.g., "Order total from €0 to €50", "Order total from €50 to €100").
    -   **Carrier Selection:** Choose a specific shipping carrier.
    -   **Minimum Order Total:** The lower bound of the order value range.
    -   **Maximum Order Total:** The upper bound of the order value range.
    -   **Fee Type:** Fixed amount or percentage.
    -   **Fee Value:** The amount or percentage for this specific carrier and order total range.
    -   **Tax Rule:** Apply a specific tax rule.
-   **Effect of changes:** These range-based fees take precedence over both the general COD fee and the simple carrier-specific fees. They allow for highly dynamic pricing strategies.
-   **Recommended workflow for daily store management:**
    1.  Use this screen for the most complex COD fee structures.
    2.  Click "Add new range fee" (or similar).
    3.  Select the carrier, define the minimum and maximum order total for this rule.
    4.  Specify the fee type, value, and tax rule for this particular range.
    5.  Save and repeat for all necessary ranges and carriers.
-   **Merchant scenario / example:** For a specific carrier, you might charge a €3 COD fee for orders under €50, but a 2% fee for orders between €50 and €200, and a flat €5 fee for orders over €200. This screen allows you to set up such tiered pricing.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|---|
| **Module Configuration** | Disable COD for specific carriers | No (all enabled) | Restrict COD availability by chosen shipping carrier. |
| | How to include the fee? | Include as a separate product | Determines how the COD fee appears in the cart/order. "Separate product" for clarity. |
| | Order status after purchase with COD module | Awaiting COD validation | Sets initial order status; "Awaiting COD validation" is recommended for accuracy. |
| | Show additional summary before the confirmation | Enabled | **CRITICAL:** Displays legal pre-confirmation summary. **Enabled** for compliance. |
| | Cart total min value | Empty / 0 | Minimum order value for COD. Set if small orders are unprofitable. |
| | Cart total max value | Empty / 0 | Maximum order value for COD. Set to mitigate risk on large orders. |
| | COD Fee Type | Amount | Choose if fee is fixed or percentage-based. |
| | COD Fee Value (Percentage) | 0 | Percentage of order total for COD fee. |
| | COD Fee Value (Amount) | 0 | Fixed monetary amount for COD fee. |
| | Minimum COD Fee | 0 | Ensures a minimum fee is charged, even if percentage is low. |
| | Maximum COD Fee | 0 | Caps the COD fee to prevent it from becoming too high. |
| | Apply Tax to COD Fee | No | Determines if tax is applied to the COD fee. Consult local tax laws. |
| | Tax Rule for COD Fee | (None) | Selects the tax rule if "Apply Tax" is enabled. |
| | CSS Selector for Cart Total | Empty | Advanced: CSS selector for cart total display. Leave empty unless issues. |
| | CSS Selector for Cart Subtotal | Empty | Advanced: CSS selector for cart subtotal display. Leave empty unless issues. |
| | CSS Selector for Cart Shipping | Empty | Advanced: CSS selector for shipping cost display. Leave empty unless issues. |
| | COD Logo | Empty | Upload a custom logo for the COD payment option. |
| **AdminCodProCarriersFees** | Carrier-specific fees | N/A | Define COD fees that vary by shipping carrier. |
| **AdminCodProCarriersRangeFees** | Carrier & Range-specific fees | N/A | Define COD fees that vary by carrier AND order total range. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The COD option isn't showing up for customers.**
A1: Check the following:
    *   **Module Enabled:** Is the "Cash on delivery with order summary" module enabled in **Modules > Module Manager**?
    *   **Payment Restrictions:** Go to **Shop Parameters > Order Settings > Payments** (or **Payment > Preferences** in older versions). Ensure "Cash on delivery with order summary" is not restricted by customer group, currency, or country.
    *   **Carrier Restrictions:** In the module's configuration, check "Disable COD for specific carriers." Is the customer's chosen carrier accidentally checked?
    *   **Cart Value Restrictions:** Check "Cart total min value" and "Cart total max value" in the module's configuration. Does the customer's cart fall within these limits?
    *   **Geographical Zones:** Ensure the module is enabled for the customer's country in **Shop Parameters > Order Settings > Payments > Restrictions by Zone/Country**.

**Q2: The COD fee isn't appearing or isn't calculated correctly.**
A2:
    *   **Fee Settings:** Double-check your "COD Fee Type" (Percentage/Amount) and "COD Fee Value" settings in the main module configuration.
    *   **Carrier/Range Fees:** If you're using `AdminCodProCarriersFees` or `AdminCodProCarriersRangeFees`, ensure the rules are correctly defined for the specific carrier and order total. These specific rules override the general settings.
    *   **Tax Rules:** If "Apply Tax to COD Fee" is enabled, ensure a valid tax rule is selected.
    *   **Cache:** Clear your PrestaShop cache (**Advanced Parameters > Performance > Clear cache**). Sometimes old data can prevent fees from updating.

**Q3: The pre-confirmation summary page isn't showing, or the order goes straight to confirmation.**
A3:
    *   **"Show additional summary before the confirmation" Setting:** In the module's main configuration, ensure this setting is **Enabled**. This is crucial for the summary page to appear.
    *   **Theme Compatibility:** While the module is designed to be compatible, some heavily customized themes might interfere. If the summary page still doesn't appear, temporarily switch to the default PrestaShop theme to rule out a theme conflict. If it works on the default theme, contact your theme developer or a PrestaShop expert.

**Q4: The COD fee is not showing on the PDF invoice.**
A4:
    *   **Module is active:** Ensure the module is enabled.
    *   **Invoice Generation:** Re-generate the PDF invoice for an order placed with COD *after* the module was configured correctly. Old invoices might not reflect new settings.
    *   **PrestaShop Version:** Ensure your PrestaShop version is fully supported. While the module aims for broad compatibility, very old or very new versions might have minor display quirks.

**Q5: How do I change the text "Cash on Delivery" or the fee description?**
A5:
    *   **Translations:** Go to **International > Translations**. Select "Installed modules translations", choose your theme, and then select "Cash on delivery with order summary". You can then find and modify all translatable strings used by the module.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview
The "Cash on delivery with order summary" module (`codpro`) is a standard PrestaShop payment module following the MVC (Model-View-Controller) pattern. It extends `PaymentModule` and leverages various PrestaShop hooks to inject its payment option, display the pre-confirmation summary, and manage order status and fees. It uses configuration values stored in `ps_configuration` for its settings and includes custom admin controllers for advanced fee management. The module dynamically calculates and displays COD fees, integrating them into the cart and order totals.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers
-   `controllers/front/index.php`
    *   **Class Name:** `CodProIndexModuleFrontController` (likely, based on file naming convention)
    *   **Parent Class:** `ModuleFrontController`
    *   **Responsibility:** This controller might be a placeholder or handle initial routing for the module's front-office components. Given the `validation.php` controller, `index.php` might not have a direct user-facing route but could be used for internal module logic or redirects.
-   `controllers/front/validation.php`
    *   **Class Name:** `CodProValidationModuleFrontController`
    *   **Parent Class:** `ModuleFrontController`
    *   **Responsibility:** This is the critical controller for processing the final order confirmation. It receives the POST data from the pre-confirmation summary page, validates the order, creates the order in PrestaShop, and redirects the customer to the order confirmation page (`paymentReturn`). It handles the logic for applying the COD fee to the order.

#### Back-Office Admin Controllers
-   `controllers/admin/AdminCodProCarriersFees.php`
    *   **Class Name:** `AdminCodProCarriersFeesController`
    *   **Parent Class:** `ModuleAdminController`
    *   **Tab Name:** Likely a sub-tab under the module's main configuration or a custom menu entry.
    *   **Managed Entity:** Manages configuration entries related to carrier-specific COD fees.
    *   **Responsibility:** Provides the interface (a `HelperList` or `HelperForm` based on `AdminController` patterns) for administrators to define, edit, and delete Cash on Delivery fees that are specific to individual shipping carriers. It handles CRUD operations for these fee rules.
-   `controllers/admin/AdminCodProCarriersRangeFees.php`
    *   **Class Name:** `AdminCodProCarriersRangeFeesController`
    *   **Parent Class:** `ModuleAdminController`
    *   **Tab Name:** Likely a sub-tab under the module's main configuration.
    *   **Managed Entity:** Manages entries in the `codprototal` table (or similar, based on `CODPRO_MOD_MAXCART_V` and `CODPRO_MOD_MINCART_V` config keys).
    *   **Responsibility:** Provides the interface for administrators to define, edit, and delete Cash on Delivery fees that are contingent on both the selected shipping carrier and the total value of the customer's cart (i.e., range-based fees). It handles CRUD operations for these complex fee rules.
-   `controllers/admin/index.php`
    *   **Class Name:** (Not a typical controller class, usually a redirect or security measure)
    *   **Parent Class:** N/A
    *   **Responsibility:** Often a security measure to prevent direct directory listing or to redirect to the main module configuration. It typically contains a simple `header('Location: ../../index.php?controller=AdminModules&token=...')` or `die('Forbidden');`.

### 4.3 Core Classes & Models (`classes/`)
The provided module information indicates no custom classes in the `classes/` directory. This suggests that the module's core logic, data handling, and potentially `ObjectModel` definitions (if any custom tables are used beyond `ps_configuration`) are encapsulated directly within the main `codpro.php` file or handled through standard PrestaShop `ObjectModel`s like `Order` and `Cart`.

### 4.4 JavaScript Assets (`views/js/`)

-   `codpro/views/js/adminCodProCarriersFees.js`
    *   **Scope:** Back-office (AdminCodProCarriersFeesController)
    *   **Responsibility:** Likely handles dynamic interactions on the carrier-specific fees administration page. This could include AJAX calls for adding/editing fees, form validation, or updating the display of the fee list.
-   `codpro/views/js/adminCodProDashboard.js`
    *   **Scope:** Back-office (potentially the main module configuration page if it includes analytics)
    *   **Responsibility:** Given the `CODPRO_ANALYTICS_` configuration keys, this script is probably responsible for rendering charts, graphs, or other analytical data related to COD orders within the module's back-office interface. It might use a charting library (e.g., Chart.js) and make AJAX requests to fetch data.
-   `codpro/views/js/codpro-checkout.js`
    *   **Scope:** Front-office (Checkout page)
    *   **Responsibility:** This is a crucial script for the front-office experience. It listens for changes in the checkout process (e.g., selecting COD as a payment method, changing shipping carrier, updating cart quantity). It dynamically updates the cart total, subtotal, and shipping cost displays (using the CSS selectors defined in the module config) to reflect the calculated COD fee. It might also handle the redirection to the pre-confirmation summary page.

### 4.5 CSS Stylesheets (`views/css/`)

-   `codpro/views/css/admin_codpro.css`
    *   **Scope:** Back-office (Admin pages related to the module)
    *   **Responsibility:** Provides styling for the module's configuration forms, lists, and potentially any custom dashboard elements within the PrestaShop back office. Ensures a consistent and user-friendly admin interface.
    *   **Key CSS class selectors:** Likely targets elements within the module's `HelperForm` or `HelperList` templates, or custom elements specific to the module's admin views.
-   `codpro/views/css/codpro.css`
    *   **Scope:** Front-office (Checkout page, pre-confirmation summary, order details)
    *   **Responsibility:** Styles the display of the Cash on Delivery payment option, the pre-confirmation summary page, and the COD fee display on order detail pages and invoices. Ensures the module's elements integrate visually with the store's theme.
    *   **Key CSS class selectors:** Will target elements like the COD payment option block, the summary table, fee line items, and potentially any custom alerts or messages introduced by the module. Developers can override these in their theme's `custom.css` or by using more specific selectors.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)
-   `codpro/views/templates/hook/confirmation.tpl`
    *   **Hook:** `displayPaymentReturn`
    *   **Output:** Content displayed on the order confirmation page after a successful COD order. Might include a message reminding the customer about cash payment on delivery.
-   `codpro/views/templates/hook/displayAdminOrder16.tpl`
    *   **Hook:** `displayAdminOrder` (for PrestaShop 1.6.x)
    *   **Output:** Adds specific information related to the COD payment (e.g., fee details) to the order view page in the PrestaShop 1.6 back office.
-   `codpro/views/templates/hook/displayAdminOrder17.tpl`
    *   **Hook:** `displayAdminOrder` (for PrestaShop 1.7.x, 8.x, 9.x)
    *   **Output:** Similar to `displayAdminOrder16.tpl`, but adapted for the PrestaShop 1.7+ back office order view, displaying COD payment details.
-   `codpro/views/templates/hook/displayOrderDetail.tpl`
    *   **Hook:** `displayOrderDetail`
    *   **Output:** Displays COD specific information (e.g., the fee breakdown) on the customer's order detail page in the front office.
-   `codpro/views/templates/hook/payment.tpl`
    *   **Hook:** `paymentOptions` or `displayPaymentOptions`
    *   **Output:** Renders the "Cash on Delivery" payment option block on the checkout page, including the module's logo and any displayed fee.
-   `codpro/views/templates/hook/pdf.tpl`
    *   **Hook:** `displayPDFInvoice`
    *   **Output:** Injects the Cash on Delivery fee as a line item or summary into the generated PDF invoices.

#### Front-office templates (`views/templates/front/`)
-   `codpro/views/templates/front/validation.tpl`
    *   **Output:** This is the template for the crucial pre-confirmation order summary page. It displays the full cart summary, shipping address, total costs (including COD fee), and the final "Confirm Order" button. This template is rendered by the `validation.php` front controller.

### 4.7 Database Schema & Hooks Map

#### Database Tables
The module primarily uses the standard `ps_configuration` table to store its settings (e.g., `CODPRO_MOD_MAXCART`, `CODPRO_FEEPAY`, `CODPRO_CHARGEP_V`, etc.).

Based on the `AdminCodProCarriersRangeFeesController` managing the `codprototal` entity, it's highly probable that the module creates a custom database table, likely named `ps_codprototal` (or similar, following PrestaShop's `ps_` prefix convention).
-   **`ps_codprototal` (Likely Table):**
    *   **Purpose:** Stores the range-based COD fee rules, linking carriers, min/max cart totals, fee amounts/percentages, and tax rules.
    *   **Likely Fields:** `id_codprototal` (PK), `id_carrier`, `min_total`, `max_total`, `fee_type` (e.g., 'amount', 'percentage'), `fee_value`, `id_tax_rule`.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
|---|---|---|
| `displayHeader` | In the `<head>` section of every page. | To include module's CSS/JS assets (e.g., `codpro-checkout.js`, `codpro.css`) on relevant front-office pages. |
| `paymentOptions` | During the checkout process, when payment options are listed. | To inject the "Cash on Delivery" payment option into the list. |
| `displayPaymentOptions` | (Alias or alternative to `paymentOptions` for some versions) | To inject the "Cash on Delivery" payment option into the list. |
| `paymentReturn` | On the order confirmation page after a successful order. | To display a confirmation message specific to COD orders. |
| `displayAdminOrder` | On the order detail page in the PrestaShop back office. | To display COD fee details and payment method information for the administrator. |
| `displayOrderDetail` | On the customer's order detail page in the front office. | To display COD fee details to the customer. |
| `displayPDFInvoice` | When a PDF invoice is generated. | To ensure the COD fee is correctly included and displayed on the invoice. |
| `ActionAdminControllerSetMedia` | When an admin controller is initialized and its media assets are being set. | To include module's admin-specific CSS/JS assets (e.g., `admin_codpro.css`, `adminCodProCarriersFees.js`, `adminCodProDashboard.js`). |

## 5. Official Support & Updates
For the latest module updates, bug fixes, and official developer support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Ensure you are always using the version of the module compatible with your specific PrestaShop installation.
