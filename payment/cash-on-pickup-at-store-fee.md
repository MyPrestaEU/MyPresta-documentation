---
title: "Cash on pickup at store (+fee) - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Cash on pickup at store (+fee) PrestaShop module by MyPresta.eu."
sidebar:
  label: "Cash on pickup at store (+fee) - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Cash on pickup at store (+fee) Module on MyPresta.eu](https://mypresta.eu/modules/payment-process/cash-on-pickup-at-store-fee.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/payment/cash-on-pickup-at-store-fee/)
>
> ---


# Cash on pickup at store (+fee)

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required and are usually enabled by default on most hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen where you’ll set up all the options for your “Cash on Pickup at Store” payment method.

#### **General Settings**

- **Payment logo**

  - **What this setting does:** Allows you to upload a custom image (logo) that will be displayed next to the “Cash on Pickup at Store” payment option during checkout. This helps customers visually identify the payment method.
  - **Effect of changing this setting:**
    - *When an image is uploaded:* The chosen image will appear next to the payment method name on the payment selection page.
    - *When no image is uploaded:* A default or no logo will be displayed, depending on your theme.
  - **Recommended value:** Upload a clear, small logo that represents “pickup” or “cash” for better recognition.
  - **Merchant scenario / example:** You might upload an icon of a shopping bag or a store front to make the payment option stand out.
- **Payment method title** (Config Key: `COPPRO_TITLE`)

  - **What this setting does:** Defines the name of the payment method as it appears to customers during checkout.
  - **Effect of changing this setting:**
    - *When changed:* The new title will be displayed on the payment selection page, order confirmation, and invoices.
  - **Recommended value:** “Cash on Pickup at Store” or “Pay at Store Pickup”.
  - **Merchant scenario / example:** If you have a specific brand name for your pickup service, you can use it here, e.g., “MyStore Local Pickup”.
- **Order Status for New Orders** (Config Key: `COPPRO_OS`)

  - **What this setting does:** Selects the initial status an order will have in your Back Office when a customer chooses “Cash on Pickup at Store”.
  - **Effect of changing this setting:**
    - *When set to “Awaiting Cash on Pickup”:* New orders will automatically be assigned this status, making it easy for you to identify orders that need to be prepared for pickup and payment.
  - **Recommended value:** Create a custom order status like “Awaiting Cash on Pickup” or “Ready for Pickup” for clarity.
  - **Merchant scenario / example:** You might set it to “Awaiting Cash on Pickup” so your staff knows to prepare the items but not to ship them.
- **Order Status when Paid** (Config Key: `COPPRO_OS_READY`)

  - **What this setting does:** Selects the order status to which an order should be changed once the customer has successfully paid and picked up their items at your store.
  - **Effect of changing this setting:**
    - *When set to “Payment accepted”:* Once you manually update the order in the Back Office after pickup and payment, it will move to this status, marking it as complete.
  - **Recommended value:** “Payment accepted” or “Delivered”.
  - **Merchant scenario / example:** After the customer picks up and pays, you’d change the order status to “Payment accepted” to finalize the transaction in your system.

#### **Cart Value Restrictions**

- **Cart total min value** (Config Key: `COPPRO_MINCART`, `COPPRO_MINCART_V`)

  - **What this setting does:** Allows you to set a minimum total value for an order to be eligible for “Cash on Pickup at Store”. If the cart total is below this value, the payment method will not be shown.
  - **Effect of changing this setting:**
    - *When set to a value (e.g., $10):* Customers with a cart total less than $10 will not see “Cash on Pickup at Store” as an option.
    - *When left empty or 0:* There will be no minimum cart value restriction.
  - **Recommended value:** Leave empty or 0 unless you have specific operational reasons to require a minimum.
  - **Merchant scenario / example:** You might set a minimum of $5 to avoid very small orders that are not cost-effective for your staff to process for pickup.
- **Cart total max value** (Config Key: `COPPRO_MAXCART`, `COPPRO_MAXCART_V`)

  - **What this setting does:** Allows you to set a maximum total value for an order to be eligible for “Cash on Pickup at Store”. If the cart total exceeds this value, the payment method will not be shown.
  - **Effect of changing this setting:**
    - *When set to a value (e.g., $500):* Customers with a cart total greater than $500 will not see “Cash on Pickup at Store” as an option.
    - *When left empty or 0:* There will be no maximum cart value restriction.
  - **Recommended value:** Leave empty or 0 unless you have specific concerns about handling very large cash payments.
  - **Merchant scenario / example:** You might set a maximum of $1000 if you’re uncomfortable with staff handling very large sums of cash at the pickup point.

#### **Fee / Discount Configuration**

- **Apply discount (not fee)** (Config Key: `COPPRO_DISCOUNT`)

  - **What this setting does:** This is a toggle switch. If enabled, the module will apply a *discount* to the order total instead of a *fee* when “Cash on Pickup at Store” is selected.
  - **Effect of changing this setting:**
    - *When enabled:* The value you set for “Percentage charge value” or “Fixed charge value” will be subtracted from the order total.
    - *When disabled:* The value you set will be added to the order total as a fee.
  - **Recommended value:** Disabled (to apply a fee) if you want to cover operational costs, or Enabled (to apply a discount) if you want to incentivize pickups.
  - **Merchant scenario / example:** You might enable this and set a 5% discount to encourage customers to pick up their orders, saving you shipping costs.
- **Fee value near payment method** (Config Key: `COPPRO_FEEPAY`)

  - **What this setting does:** This is a toggle switch. If enabled, the fee or discount amount will be displayed directly next to the payment method name on the checkout page.
  - **Effect of changing this setting:**
    - *When enabled:* Customers will see “Cash on Pickup at Store (+ $X.XX fee)” or “Cash on Pickup at Store (- $X.XX discount)”.
    - *When disabled:* Only the payment method name will be shown, and the fee/discount will be applied to the cart total without explicit mention next to the method.
  - **Recommended value:** Enabled, for transparency with your customers.
  - **Merchant scenario / example:** You want customers to be fully aware of any additional costs or savings upfront, so you enable this.
- **Percentage charge** (Config Key: `COPPRO_CHARGEP`, `COPPRO_CHARGEP_V`)

  - **What this setting does:** Allows you to apply a fee or discount based on a percentage of the order total.
  - **Effect of changing this setting:**
    - *When enabled and a value is entered (e.g., 5):* A 5% fee (or discount if “Apply discount” is enabled) will be added/subtracted from the order total.
    - *When disabled:* No percentage-based fee/discount will be applied.
  - **Recommended value:** Disabled, unless you specifically want a percentage-based charge. If enabled, a value between 1-10% is common for fees, or 2-10% for discounts.
  - **Merchant scenario / example:** You want to charge a 3% fee to cover the cost of processing cash and handling, so you enable this and enter “3”.
- **Fixed charge** (Config Key: `COPPRO_CHARGEA`, `COPPRO_CHARGEA_V`)

  - **What this setting does:** Allows you to apply a fixed amount fee or discount to the order total.
  - **Effect of changing this setting:**
    - *When enabled and a value is entered (e.g., 2.50):* A fixed $2.50 fee (or discount if “Apply discount” is enabled) will be added/subtracted from the order total.
    - *When disabled:* No fixed amount fee/discount will be applied.
  - **Recommended value:** Enabled, with a small fixed amount (e.g., $1.00 - $3.00) if you want a simple, consistent fee.
  - **Merchant scenario / example:** You want to charge a flat $2 fee for all pickup orders, so you enable this and enter “2.00”.

#### **Advanced Display & Compatibility Settings**

- **Cart summary** (Config Key: `COPPRO_CARTPRESENTER`)

  - **What this setting does:** This is a toggle switch that controls whether the fee/discount is explicitly shown in the cart summary block (e.g., in the right column or at the bottom of the cart page).
  - **Effect of changing this setting:**
    - *When enabled:* The fee/discount will be itemized in the cart summary, showing how it affects the total.
    - *When disabled:* The fee/discount will be applied to the total but might not be explicitly broken down in the cart summary before the payment step.
  - **Recommended value:** Enabled, for full transparency.
  - **Merchant scenario / example:** You want customers to see the “Pickup Fee” line item in their cart summary before they even reach the payment step, so you enable this.
- **Address summary** (Config Key: `COPPRO_HOWFEE`)

  - **What this setting does:** This setting controls where the fee/discount is displayed on the address summary section of the checkout.
  - **Effect of changing this setting:**
    - *When enabled:* The fee/discount will be visible in the address summary, usually near the shipping cost.
    - *When disabled:* The fee/discount will be applied but not explicitly shown in the address summary.
  - **Recommended value:** Enabled, for consistency and transparency.
  - **Merchant scenario / example:** You want the fee to be visible at multiple stages of checkout, including the address summary, so you enable this.
- **Enabled** (Config Key: `COPPRO_EVENTLISTENER`)

  - **What this setting does:** This is a general toggle to enable or disable the module’s core functionality.
  - **Effect of changing this setting:**
    - *When enabled:* The “Cash on Pickup at Store” payment method will be active and available to customers.
    - *When disabled:* The payment method will be hidden and unavailable.
  - **Recommended value:** Enabled, once you have configured all other settings.
  - **Merchant scenario / example:** You’ve finished setting up the module and are ready to offer this payment method, so you enable it.
- **Disabled** (Config Key: `PS_ONE_PAGE_CHECKOUT_ENABLED`)

  - **What this setting does:** This setting is likely related to compatibility with PrestaShop’s one-page checkout. It might be a legacy setting or a display indicator.
  - **Effect of changing this setting:** This is likely a read-only indicator or a setting that should generally be left at its default unless instructed otherwise by support.
  - **Recommended value:** Leave as default.
  - **Merchant scenario / example:** No direct merchant interaction expected.
- **CSS Selectors for Cart Elements** (Config Keys: `COPPRO_CSS_CART_TOTAL`, `COPPRO_CSS_CART_SUBTOTAL`, `COPPRO_CSS_CART_SHIPPING`)

  - **What these settings do:** These fields allow you to specify the CSS selectors for your theme’s cart total, subtotal, and shipping cost elements. This is crucial for the module to correctly update these values when a fee/discount is applied, especially if your theme uses non-standard selectors.
  - **Effect of changing this setting:**
    - *When correctly configured:* The module will accurately update the displayed cart totals, subtotals, and shipping costs on the checkout page to reflect the fee/discount.
    - *When incorrectly configured or left empty:* The cart totals might not update correctly, leading to customer confusion or incorrect displayed prices.
  - **Recommended value:** Leave empty initially. If you notice the cart totals are not updating correctly after selecting “Cash on Pickup at Store”, you may need to consult your theme’s developer or a webmaster to find the correct CSS selectors.
  - **Merchant scenario / example:** After installing the module, you notice the total price doesn’t change on the checkout page when the pickup fee is applied. Your webmaster would inspect your theme’s code to find the correct CSS selectors (e.g., `#cart-total-price`, `.product-total-price`) and enter them here.

#### **Exclusion Rules**

- **Exclude products** (Config Key: `COPPRO_EXCL_PRODUCTS`)

  - **What this setting does:** Allows you to prevent specific products from being purchased with the “Cash on Pickup at Store” payment method. If any excluded product is in the cart, this payment method will not be available.
  - **Effect of changing this setting:**
    - *When products are selected:* If a customer adds one of these products to their cart, the “Cash on Pickup at Store” option will disappear from the payment methods.
    - *When no products are selected:* All products are eligible.
  - **Recommended value:** Leave empty unless you have specific products that cannot be picked up or paid for in cash.
  - **Merchant scenario / example:** You sell very high-value items (e.g., expensive jewelry) that you prefer to only accept secure online payments for. You would add these products to the exclusion list.
- **Exclude categories** (Config Key: `COPPRO_EXCL_CAT`)

  - **What this setting does:** Similar to excluding products, this allows you to prevent entire product categories from being purchased with “Cash on Pickup at Store”.
  - **Effect of changing this setting:**
    - *When categories are selected:* If a customer adds any product from these categories to their cart, the “Cash on Pickup at Store” option will not be available.
    - *When no categories are selected:* All categories are eligible.
  - **Recommended value:** Leave empty unless you have specific categories that are not suitable for pickup.
  - **Merchant scenario / example:** You have a “Digital Downloads” category. Since these items don’t require physical pickup, you would exclude this category.
- **Enable exclusions** (Config Key: `COPPRO_EXCL_ENABLE`)

  - **What this setting does:** This is a master toggle to enable or disable all product and category exclusion rules you’ve set up.
  - **Effect of changing this setting:**
    - *When enabled:* Your product and category exclusion rules will be active.
    - *When disabled:* All products and categories will be eligible for “Cash on Pickup at Store”, regardless of what you’ve selected in the exclusion lists.
  - **Recommended value:** Enabled, if you have defined any exclusion rules.
  - **Merchant scenario / example:** You’ve set up exclusions for certain products, and you want these rules to be active, so you enable this switch.

#### **Analytics & Internal Settings**

- **Analytics settings** (Config Keys: `COPPRO_ANALYTICS_DEFAULT_CHART`, `COPPRO_ANALYTICS_PERIOD`, `COPPRO_ANALYTICS_IMPACT_DAYS`, `COPPRO_ANALYTICS_CHART_WEEKS`, `COPPRO_ANALYTICS_CHART_MONTHS`, `COPPRO_ANALYTICS_CHART_YEARS`)

  - **What these settings do:** These are internal settings related to any analytics or reporting features the module might have, allowing you to configure how data is collected or displayed for internal use.
  - **Effect of changing this setting:** These typically affect only the Back Office reporting views, not the front-office customer experience.
  - **Recommended value:** Leave as default unless you have specific reporting needs.
  - **Merchant scenario / example:** No direct merchant interaction expected for daily operations.
- **Fee change date / snapshot** (Config Keys: `COPPRO_FEE_CHANGE_DATE`, `COPPRO_FEE_CHANGE_SNAPSHOT`)

  - **What these settings do:** These are likely internal module settings to track when fee configurations were last changed or to store a snapshot of previous fee settings. This is usually for auditing or debugging purposes.
  - **Effect of changing this setting:** No direct impact on customer experience.
  - **Recommended value:** Leave as default.
  - **Merchant scenario / example:** No direct merchant interaction expected.

### 2.2 Dedicated Admin Screens & Controller Views

This module does not appear to have dedicated custom Admin Controllers beyond its main configuration page. All settings are managed through the `getContent()` method of the main module file.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Payment logo | Upload relevant image | Visual identification of payment method. |
| Module Configuration | Payment method title | “Cash on Pickup at Store” | Name displayed to customers for the payment option. |
| Module Configuration | Order Status for New Orders | Custom “Awaiting Cash on Pickup” | Initial status for orders using this method. |
| Module Configuration | Order Status when Paid | “Payment accepted” / “Delivered” | Final status after customer pays and picks up. |
| Module Configuration | Cart total min value | Empty / 0 | Minimum order value for this payment method to appear. |
| Module Configuration | Cart total max value | Empty / 0 | Maximum order value for this payment method to appear. |
| Module Configuration | Apply discount (not fee) | Disabled | Determines if a discount or fee is applied. |
| Module Configuration | Fee value near payment method | Enabled | Displays fee/discount next to payment method name. |
| Module Configuration | Percentage charge | Disabled | Applies a percentage-based fee/discount. |
| Module Configuration | Percentage charge value | 0 | The percentage value for the charge/discount. |
| Module Configuration | Fixed charge | Enabled (with value) | Applies a fixed amount fee/discount. |
| Module Configuration | Fixed charge value | e.g., 2.00 | The fixed amount for the charge/discount. |
| Module Configuration | Cart summary | Enabled | Shows fee/discount itemized in cart summary. |
| Module Configuration | Address summary | Enabled | Shows fee/discount in address summary. |
| Module Configuration | Enabled | Enabled | Activates/deactivates the payment method. |
| Module Configuration | Exclude products | Empty | Prevents specific products from using this method. |
| Module Configuration | Exclude categories | Empty | Prevents products from specific categories from using this method. |
| Module Configuration | Enable exclusions | Enabled (if rules set) | Master switch for product/category exclusion rules. |
| Module Configuration | CSS Selectors (Cart Total, Subtotal, Shipping) | Empty (adjust if needed) | Ensures correct cart total updates with theme. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The “Cash on Pickup at Store” payment method is not showing up during checkout.**
A:

- **Check “Enabled” setting:** Go to Modules > Module Manager > Configure for “Cash on pickup at store (+fee)” and ensure the main “Enabled” switch is turned ON.
- **Check Cart Value Restrictions:** Verify your “Cart total min value” and “Cart total max value” settings. If the customer’s cart total falls outside this range, the method won’t appear.
- **Check Exclusions:** If you’ve set up product or category exclusions, ensure the current cart doesn’t contain any excluded items. Also, check if “Enable exclusions” is turned ON.
- **Check Geo-Restrictions:** Ensure the payment method is not restricted by country or currency in PrestaShop’s general payment settings (Payment > Preferences).
- **Clear Cache:** Sometimes, PrestaShop’s cache can prevent changes from appearing immediately. Go to **Advanced Parameters > Performance** and click “Clear cache”.

**Q2: The fee/discount is not being applied or displayed correctly on the checkout page.**
A:

- **Verify Fee/Discount Settings:** Double-check that “Percentage charge” or “Fixed charge” is enabled, and the corresponding value is correctly entered. Also, ensure “Apply discount (not fee)” is set as intended.
- **Check Display Settings:** Make sure “Fee value near payment method”, “Cart summary”, and “Address summary” are all enabled for maximum visibility.
- **CSS Selectors (Advanced):** If your theme is heavily customized, the module might not be able to find the correct elements to update. Check the “CSS Selectors for Cart Elements” settings. You might need a webmaster to identify the correct selectors for your theme’s cart total, subtotal, and shipping elements.

**Q3: How do I change the text “Cash on Pickup at Store” to something else?**
A:

- You can change the display name directly in the module’s configuration. Look for the “Payment method title” setting on the main configuration page.
- For multi-language stores, ensure you select the correct language from the dropdown at the top of the module configuration page (if available) or use PrestaShop’s translation tool (International > Translations > Installed modules translations).

**Q4: Can I restrict this payment method to only certain carriers or customer groups?**
A:

- **Carriers:** Yes, PrestaShop’s core payment preferences allow you to restrict payment methods by carrier. Go to **Payment > Preferences** in your Back Office. In the “Carrier restrictions” section, ensure “Cash on pickup at store (+fee)” is selected for the carriers you want to allow it with (e.g., your “Local Pickup” carrier).
- **Customer Groups:** Similarly, in **Payment > Preferences**, you can restrict payment methods by customer group. Ensure the relevant customer groups (e.g., “Customer”, “Visitor”) are selected for this payment method.

**Q5: What order status should I use for “Cash on Pickup” orders?**
A:

- It’s highly recommended to create a custom order status in PrestaShop (Orders > Order Statuses) specifically for “Cash on Pickup” orders, such as “Awaiting Cash on Pickup” or “Ready for Pickup”. This helps you easily identify these orders in your Back Office.
- Then, in the module’s configuration, set “Order Status for New Orders” to this custom status.
- Once the customer has paid and picked up, manually change the order status to “Payment accepted” or “Delivered” in the order details page.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The `Cash on pickup at store (+fee)` module (`coppro`) is a standard PrestaShop payment module following the MVC pattern. It extends `PaymentModule` and integrates primarily through hooks to display payment options, process validation, and display order information. The module dynamically calculates fees/discounts based on configuration and updates cart totals via JavaScript on the front-office checkout. It uses `Configuration` for settings storage and does not introduce custom `ObjectModel` classes or database tables.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `controllers/front/index.php`
    - Class name: `CopproIndexModuleFrontController` (likely extends `ModuleFrontController`)
    - Responsibility: This controller might serve as a default entry point or handle general module-related front-office requests that don’t fit into specific payment flows. Given its name, it could be a fallback or a simple display controller.
  - `controllers/front/store.php`
    - Class name: `CopproStoreModuleFrontController` (likely extends `ModuleFrontController`)
    - Responsibility: Potentially handles logic related to store locations or pickup points, though the module description doesn’t explicitly mention multiple store locations. It might be a placeholder or for future expansion.
  - `controllers/front/validation.php`
    - Class name: `CopproValidationModuleFrontController` (likely extends `ModuleFrontController`)
    - Responsibility: This is the critical controller for payment processing. It receives the payment confirmation from the checkout process, validates the order, and redirects the customer to the order confirmation page. It interacts with the main `coppro.php` module to finalize the order with the correct status and applied fees/discounts.
- **Back-Office Admin Controllers**:

  - This module does not include any custom Admin Controllers. All Back Office configuration is handled directly within the `getContent()` method of the main `coppro.php` module file.

### 4.3 Core Classes & Models (`classes/`)

The module does not appear to define any custom classes within a `classes/` directory. Its core logic resides within the `coppro.php` main module file, which extends `PaymentModule`.

### 4.4 JavaScript Assets (`views/js/`)

- `coppro/lib/searchTool/views/js/autocomplete.js`
  - Scope: Likely Back-office.
  - Responsibility: Provides autocomplete functionality, probably for product or category selection in the module’s configuration (e.g., for exclusion lists). It binds to input fields and performs AJAX requests to fetch suggestions.
- `coppro/views/js/adminCopproDashboard.js`
  - Scope: Back-office.
  - Responsibility: Manages JavaScript for any administrative dashboard or analytics features within the module’s configuration page. It might handle chart rendering or data display.
- `coppro/views/js/adminCopproProductSearch.js`
  - Scope: Back-office.
  - Responsibility: Specifically handles the product search interface within the module’s admin configuration, likely for the “Exclude products” setting. It manages search input, results display, and selection.
- `coppro/views/js/adminCopproSelector.js`
  - Scope: Back-office.
  - Responsibility: Manages selection logic for various elements in the admin panel, possibly for categories or other configurable lists.
- `coppro/views/js/coppro-checkout.js`
  - Scope: Front-office.
  - Responsibility: This is the main front-office script. It listens for changes in payment method selection during checkout. When “Cash on Pickup at Store” is chosen, it dynamically updates the cart summary (total, subtotal, shipping) to reflect the calculated fee or discount. It uses the CSS selectors defined in the module configuration (`COPPRO_CSS_CART_TOTAL`, etc.) to target and modify DOM elements. It might also handle AJAX calls to recalculate totals if the backend is needed.
- `coppro/views/js/copproBoMockConsole.js`
  - Scope: Back-office.
  - Responsibility: Likely a debugging or development utility, possibly for simulating console output or logging within the Back Office.

### 4.5 CSS Stylesheets (`views/css/`)

- `coppro/lib/searchTool/views/css/autocomplete.css`
  - Scope: Back-office.
  - Responsibility: Styles the autocomplete dropdowns and search input fields used in the admin configuration.
- `coppro/views/css/admin_coppro.css`
  - Scope: Back-office admin form styling.
  - Responsibility: Provides specific styling for the module’s configuration page in the PrestaShop Back Office, ensuring a consistent and user-friendly interface.
- `coppro/views/css/coppro.css`
  - Scope: Front-office customer styling.
  - Responsibility: Contains styles for the “Cash on Pickup at Store” payment option display, potentially for the payment logo, fee/discount text, or any custom elements introduced by the module on the checkout page. Developers can override these styles in their theme’s `custom.css` or child theme.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - `coppro/views/templates/hook/confirmation.tpl`
    - Hook: Likely `displayPaymentReturn` or similar.
    - Outputs: Content for the order confirmation page after a successful “Cash on Pickup” order, informing the customer about payment upon pickup.
  - `coppro/views/templates/hook/displayAdminOrder16.tpl`
    - Hook: `displayAdminOrder` (for PrestaShop 1.6.x).
    - Outputs: Additional information or actions related to “Cash on Pickup” orders within the Back Office order detail page for PS 1.6.
  - `coppro/views/templates/hook/displayAdminOrder17.tpl`
    - Hook: `displayAdminOrder` (for PrestaShop 1.7.x, 8.x, 9.x).
    - Outputs: Similar to `displayAdminOrder16.tpl` but adapted for the PS 1.7+ Back Office order detail page, potentially showing pickup instructions or fee details.
  - `coppro/views/templates/hook/displayOrderDetail.tpl`
    - Hook: `displayOrderDetail`.
    - Outputs: Information about the “Cash on Pickup” payment method within the customer’s front-office order detail page.
  - `coppro/views/templates/hook/payment.tpl`
    - Hook: `paymentOptions` (or `displayPaymentOptions`).
    - Outputs: The HTML structure for the “Cash on Pickup at Store” payment option on the checkout page, including the payment logo, title, and dynamically calculated fee/discount text.
- **Admin templates (`views/templates/admin/`)**:

  - `coppro/lib/searchTool/views/scripts.tpl`
    - Hook: Likely `actionAdminControllerSetMedia` or included directly in `getContent()`.
    - Outputs: Includes JavaScript and CSS assets for the search tool used in the admin configuration.
  - `coppro/views/templates/admin/productSearchTool.tpl`
    - Outputs: The HTML structure for the product search and selection interface within the module’s configuration, used for the “Exclude products” setting.
  - `coppro/views/templates/admin/scopeSelector.tpl`
    - Outputs: HTML for a generic scope selector, potentially used for categories or other filterable lists in the admin configuration.
- **Front-office templates (`views/templates/front/`)**:

  - `coppro/views/templates/front/validation.tpl`
    - Outputs: Content displayed by the `CopproValidationModuleFrontController` after payment validation, typically a redirect or a simple message before the final confirmation page.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  The module does not create custom database tables. All its configuration settings are stored in the `ps_configuration` table using the `Configuration::updateValue()` and `Configuration::get()` methods, with keys prefixed by `COPPRO_`.
  Example configuration keys:

  - `COPPRO_OS`
  - `COPPRO_OS_READY`
  - `COPPRO_MAXCART_V`
  - `COPPRO_MINCART_V`
  - `COPPRO_FEEPAY`
  - `COPPRO_DISCOUNT`
  - `COPPRO_CHARGEP_V`
  - `COPPRO_CHARGEA_V`
  - `COPPRO_EXCL_PRODUCTS`
  - `COPPRO_EXCL_CAT`
  - `COPPRO_TITLE`
  - `COPPRO_CARTPRESENTER`
  - `COPPRO_HOWFEE`
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | To include front-office CSS (`coppro.css`) and JavaScript (`coppro-checkout.js`) assets. |
| `displayPaymentOptions` | During checkout, to list available payment methods. | To display the “Cash on Pickup at Store” payment option with its title, logo, and calculated fee/discount. |
| `paymentOptions` | Alias for `displayPaymentOptions` (older PS versions). | Same as `displayPaymentOptions`. |
| `displayPaymentReturn` | On the order confirmation page after payment. | To display specific instructions or confirmation messages for “Cash on Pickup” orders. |
| `displayPDFInvoice` | When a PDF invoice is generated. | To ensure the “Cash on Pickup at Store” payment method is correctly stated on the invoice. |
| `displayOrderDetail` | On the customer’s order detail page in the front office. | To show the chosen payment method and any related details. |
| `displayAdminOrder` | On the order detail page in the Back Office. | To display additional information or management tools specific to “Cash on Pickup” orders for administrators. |
| `actionAdminControllerSetMedia` | When an admin controller loads its media assets. | To include Back-office CSS (`admin_coppro.css`, `autocomplete.css`) and JavaScript (`adminCopproDashboard.js`, `adminCopproProductSearch.js`, `adminCopproSelector.js`, `autocomplete.js`) for the module’s configuration page. |
| `actionValidateOrder` | After an order has been successfully validated. | To perform any post-validation actions, such as updating order status or logging details, specific to “Cash on Pickup” orders. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official technical support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions regarding the “Cash on pickup at store (+fee)” module.
