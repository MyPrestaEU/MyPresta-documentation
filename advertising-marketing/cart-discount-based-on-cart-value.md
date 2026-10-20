---
title: "Cart discount based on cart value - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Cart discount based on cart value PrestaShop module by MyPresta.eu."
sidebar:
  label: "Cart discount based on cart value - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Cart discount based on cart value Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/cart-discount-based-on-cart-value.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/cart-discount-based-on-cart-value/)
>
> ---


# Cart discount based on cart value

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required, which are typically available on most PrestaShop-compatible hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main screen where you control the overall behavior and settings of your cart discount program.

- **Activate program**

  - **What this setting does:** This is the master switch to turn the entire cart discount program on or off.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The module will actively check cart values and apply discounts according to your defined rules.
    - *When disabled (NO):* No cart discounts will be applied, and no related messages will appear on the cart page, regardless of other settings.
  - **Recommended value:** YES (once you have configured your discount rules).
  - **Merchant scenario / example:** You might disable it temporarily during a special sale where other discount rules apply, or if you need to perform maintenance.
- **Disable cart discounts program for selected groups of customers**

  - **What this setting does:** Allows you to prevent specific customer groups (e.g., wholesalers, VIPs, or guests) from receiving these cart value-based discounts.
  - **Effect of changing this setting:**
    - *When selected:* Customers belonging to the chosen groups will not receive any discounts from this module, even if their cart value meets the criteria.
    - *When not selected:* All customer groups are eligible for the discounts.
  - **Recommended value:** Depends on your business strategy. If you have special pricing for certain groups, you might exclude them.
  - **Merchant scenario / example:** You have a “Wholesale” customer group that already receives special pricing. You would select this group here to avoid stacking discounts.
- **Type of price**

  - **What this setting does:** Determines whether the cart value for discount calculation should include or exclude taxes.
  - **Effect of changing this setting:**
    - *When set to “Price with tax”:* The discount is calculated based on the total cart value *including* VAT/taxes.
    - *When set to “Price without tax”:* The discount is calculated based on the total cart value *excluding* VAT/taxes.
  - **Recommended value:** “Price with tax” for most B2C stores, “Price without tax” for B2B stores or if your primary pricing is ex-tax.
  - **Merchant scenario / example:** If your customers are used to seeing prices with tax, calculating the discount based on the “Price with tax” will feel more natural and transparent to them.
- **Exclude products with discount**

  - **What this setting does:** Controls whether products that are already on sale or have a specific price (e.g., from a catalog rule) should count towards the cart value for discount calculation.
  - **Effect of changing this setting:**
    - *When enabled (YES):* Products already discounted will be ignored when calculating the cart’s total value for the tiered discount.
    - *When disabled (NO):* All products in the cart, regardless of whether they are already discounted, will contribute to the cart value for the tiered discount.
  - **Recommended value:** YES, to prevent “double discounting” and protect your margins.
  - **Merchant scenario / example:** You’re running a 20% off sale on specific T-shirts. If a customer buys a T-shirt and other items, and this setting is YES, the T-shirt’s value won’t help them reach the next cart discount tier.
- **Exclude products from manufacturer**

  - **What this setting does:** Allows you to specify certain manufacturers whose products should not contribute to the cart value when calculating the tiered discount.
  - **Effect of changing this setting:**
    - *When selected:* Products from the chosen manufacturers will be ignored when calculating the cart’s total value for the tiered discount.
    - *When not selected:* All products, regardless of manufacturer, contribute to the cart value.
  - **Recommended value:** Leave empty unless you have specific agreements or low-margin products from certain manufacturers.
  - **Merchant scenario / example:** You sell products from a premium brand that has strict pricing rules and cannot be included in general discounts. You would select that manufacturer here.
- **Exclude discounted products from discount value**

  - **What this setting does:** Determines if the *value* of products that are already discounted should be excluded from the *amount* of the cart discount applied. This is a subtle but important distinction from “Exclude products with discount”.
  - **Effect of changing this setting:**
    - *When enabled (YES):* If a cart discount of 5% is applied, and some products in the cart are already discounted, the 5% will only apply to the non-discounted items.
    - *When disabled (NO):* The 5% cart discount will apply to the *entire* cart value, even if some items within it are already discounted.
  - **Recommended value:** YES, to protect margins and prevent excessive discounts on already reduced items.
  - **Merchant scenario / example:** A customer has a €100 cart, with one €20 item already 10% off. If a 5% cart discount applies and this setting is YES, the 5% will only apply to the €80 worth of non-discounted items.
- **Exclude cart with voucher code**

  - **What this setting does:** Prevents the module’s cart value-based discounts from applying if a customer has already entered a separate voucher code (coupon) in their cart.
  - **Effect of changing this setting:**
    - *When enabled (YES):* If a customer uses a voucher code, the module’s automatic cart discount will not be applied, avoiding stacked discounts.
    - *When disabled (NO):* The module’s discount will apply even if a voucher code is present, potentially stacking discounts.
  - **Recommended value:** YES, to prevent over-discounting and maintain control over your promotions.
  - **Merchant scenario / example:** You’re running a special email campaign with a unique 10% off voucher. You want customers to choose between that voucher or the tiered cart discount, not both.
- **Show discount program info on cart page**

  - **What this setting does:** Controls whether messages about the cart discount program (e.g., “Spend X more for Y% discount!”) are displayed on the shopping cart page.
  - **Effect of changing this setting:**
    - *When enabled (YES):* Informative messages will appear on the cart page, guiding customers towards higher spending.
    - *When disabled (NO):* No messages related to this module’s discounts will be shown on the cart page. The discount will still apply if active, but without the promotional messaging.
  - **Recommended value:** YES, as this is a key feature for encouraging higher AOV.
  - **Merchant scenario / example:** You want to actively encourage customers to reach the next discount tier. Enabling this will show them exactly how much more they need to spend.
- **Additional custom contents**

  - **What this setting does:** Allows you to add custom text, HTML, or even images that will be displayed alongside the discount program information on the cart page. This content can be translated into different languages.
  - **Effect of changing this setting:**
    - *When content is entered:* Your custom message will appear on the cart page, enhancing the promotional message.
    - *When left empty:* No additional custom content will be displayed.
  - **Recommended value:** Use this to add a compelling call to action or explain the benefits of the discount program.
  - **Merchant scenario / example:** You could add “Don’t miss out on savings! The more you buy, the more you save!” or a link to your terms and conditions for discounts.

### 2.2 Dedicated Admin Screens & Controller Views

#### 2.2.1 AdminCdisListController (Back Office > Modules > Cart discount based on cart value > “Configure” button, then navigate to the “Discounts” tab or similar)

This screen is where you define and manage your actual discount rules. It’s typically accessed after clicking “Configure” on the module and then navigating to a specific tab or link for “Discounts” or “Rules”.

- **Screen Name & Menu Location:** This screen is usually accessed via a dedicated tab or link within the module’s main configuration page, often labeled “Discounts,” “Rules,” or “Manage Discounts.”
- **Available Actions & Settings:**
  - **Grid / Management View:** You’ll see a table listing all your defined discount rules. Each row represents a rule with columns like:
    - **Minimum Cart Value:** The threshold the cart must reach.
    - **Discount Type:** Whether it’s a percentage or a fixed amount.
    - **Discount Value:** The percentage (e.g., 5) or fixed amount (e.g., 10.00).
    - **Active:** Whether the rule is currently enabled.
    - **Actions:** Buttons to “Edit” or “Delete” individual rules.
  - **Add New Rule Button:** A button (e.g., “Add new discount rule”) to create a new discount condition. When clicked, it will open a form to define a new rule.
  - **Edit Rule Form:** When adding or editing a rule, you’ll typically find fields for:
    - **Minimum Cart Value:** (e.g., 500) - The minimum total value of the cart for this discount to apply.
    - **Discount Type:** (e.g., Percentage, Fixed Amount) - Choose how the discount is calculated.
    - **Discount Value:** (e.g., 5 for 5%, or 10.00 for €10) - The actual discount to apply.
    - **Active:** (Yes/No switch) - To enable or disable this specific rule without deleting it.
    - **Priority:** (e.g., 1, 2, 3) - If multiple rules could apply (e.g., cart value is €1000, and you have rules for €500 and €1000), priority determines which one takes precedence. Lower numbers usually mean higher priority.
- **Effect of changes:**
  - **Adding a rule:** A new discount condition becomes active in your store, automatically applying to customer carts that meet the criteria.
  - **Editing a rule:** Modifies an existing discount condition, changing its threshold, value, or active status.
  - **Deleting a rule:** Permanently removes a discount condition, and it will no longer be applied to carts.
  - **Activating/Deactivating:** Toggles the availability of a specific discount rule without removing its configuration.
- **Recommended workflow for daily store management:**
  1. Start by planning your discount tiers (e.g., €250 for 2%, €500 for 5%, €1000 for 10%).
  2. Click “Add new discount rule” for each tier.
  3. Enter the “Minimum Cart Value,” select “Discount Type” (usually Percentage), and enter the “Discount Value.”
  4. Ensure “Active” is set to YES.
  5. Set priorities if you have overlapping ranges (e.g., a rule for >€500 and another for >€1000, ensure the €1000 rule has higher priority if you want it to apply instead of the €500 rule when the cart is over €1000). The module typically handles this by applying the highest-value discount for the highest tier met.
  6. Regularly review your discount rules, especially before major sales or promotional periods, to ensure they align with your current marketing strategy.

#### 2.2.2 index.php (cartdiscount/controllers/admin/index.php)

This file is a placeholder and typically contains only a security `die()` statement to prevent direct access to the directory. It does not represent a configurable screen or entity management view for the merchant.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration Page** | Activate program | YES | Master switch for the entire discount program. |
|  | Disable cart discounts program for selected groups of customers | (None selected) | Excludes chosen customer groups from receiving discounts. |
|  | Type of price | Price with tax | Determines if cart value includes or excludes tax for calculation. |
|  | Exclude products with discount | YES | Prevents already discounted products from contributing to the cart value threshold. |
|  | Exclude products from manufacturer | (None selected) | Ignores products from selected manufacturers for cart value calculation. |
|  | Exclude discounted products from discount value | YES | Ensures the cart discount only applies to non-discounted items in the cart. |
|  | Exclude cart with voucher code | YES | Prevents module discounts if a separate voucher code is used. |
|  | Show discount program info on cart page | YES | Displays promotional messages on the cart page. |
|  | Additional custom contents | (Empty) | Adds custom text/HTML to the cart page discount info. |
| **AdminCdisListController (Discounts List)** | Minimum Cart Value | (Defined by merchant) | The cart total threshold to trigger a discount. |
|  | Discount Type | Percentage | How the discount is calculated (percentage or fixed amount). |
|  | Discount Value | (Defined by merchant) | The actual discount amount (e.g., 5 for 5%, 10.00 for €10). |
|  | Active | YES | Enables or disables a specific discount rule. |
|  | Priority | (Auto/Defined by merchant) | Determines which rule applies if multiple thresholds are met. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My discounts aren’t applying, even though I’ve set up rules. What’s wrong?**
A:

1. **Check “Activate program”:** Ensure the main switch on the module’s configuration page is set to YES.
2. **Check individual rule “Active” status:** Make sure each discount rule you’ve created in the AdminCdisListController is also set to YES.
3. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). PrestaShop often caches module settings.
4. **Check Customer Groups:** Verify that the customer group you are testing with is not excluded under “Disable cart discounts program for selected groups of customers.”
5. **Cart Value Threshold:** Double-check that your cart value actually meets the “Minimum Cart Value” for the discount to trigger.

**Q: The discount is applying, but the message on the cart page isn’t showing up.**
A:

1. **Check “Show discount program info on cart page”:** Ensure this setting is enabled (YES) on the module’s main configuration page.
2. **Theme Compatibility:** Your custom theme might be overriding the standard cart display. Check if the `displayShoppingCartFooter` hook is properly implemented in your theme’s `shopping-cart.tpl` or equivalent file. If not, a developer might need to manually add the hook.
3. **Clear Cache:** Always clear your PrestaShop cache after making configuration changes.

**Q: The discount value seems incorrect, or it’s not applying to all items.**
A:

1. **“Type of price”:** Verify if you’ve selected “Price with tax” or “Price without tax” for the calculation.
2. **“Exclude products with discount”:** If enabled, products already on sale won’t contribute to the threshold.
3. **“Exclude discounted products from discount value”:** If enabled, the percentage discount will only apply to non-discounted items in the cart. Review these settings to ensure they match your intended behavior.
4. **“Exclude cart with voucher code”:** If a customer has applied a separate voucher, and this setting is YES, the module’s discount will not apply.

**Q: How do I translate the custom content I added?**
A:

1. Go to **International > Translations** in your PrestaShop Back Office.
2. Select “Installed modules translations,” choose your theme, and then select the language you want to translate.
3. Find the “Cart discount based on cart value” module. You should see fields to translate the “Additional custom contents” for each language.

**Q: I’m seeing an error after updating PrestaShop or another module.**
A:

1. **Check Module Version:** Ensure you are using the latest version of the “Cart discount based on cart value” module compatible with your PrestaShop version. Download the correct ZIP from MyPresta.eu.
2. **PHP Compatibility:** Verify your server’s PHP version is within the module’s supported range (PHP 5.6 - 8.5).
3. **Disable Overrides (for developers):** If you suspect a conflict, temporarily disable overrides in **Advanced Parameters > Performance** (set “Disable non PrestaShop modules” to YES, then clear cache). If the issue resolves, it’s likely an override conflict. Re-enable and consult a developer.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Cart discount based on cart value” module extends PrestaShop’s core `Cart` and `CartRule` functionalities through overrides to dynamically apply discounts. It leverages a dedicated Admin Controller (`AdminCdisListController`) for managing discount rules stored in a custom database table. Front-office integration is primarily achieved through hooks to display informational messages and ensure discount application during cart and checkout processes.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None explicitly defined in the module’s `controllers/front/` directory. Front-office logic for discount application is handled via overrides and hooks.
- **Back-Office Admin Controllers**:

  - `cartdiscount/controllers/admin/AdminCdisList.php`
    - **Class Name & Parent Class:** `AdminCdisListController` extends `ModuleAdminController`.
    - **Tab Name and Managed Entity:** Manages the list and forms for `Cdis` (Cart Discount) entities. This controller provides the interface for creating, editing, and deleting the tiered discount rules. It defines the list view (`renderList()`) and the form view (`renderForm()`) for the discount rules.
  - `cartdiscount/controllers/admin/index.php`
    - **Class Name & Parent Class:** N/A (security file).
    - **Responsibility:** Contains a `die('No direct script access allowed');` statement to prevent direct access to the directory, a standard PrestaShop security practice.

### 4.3 Core Classes & Models (`classes/`)

The module heavily relies on overrides to inject its logic into core PrestaShop classes.

- `cartdiscount/override/classes/Cart.php`
  - **Original Class:** `Cart`
  - **Responsibility:** This override is crucial. It extends the `Cart` class to modify how cart totals are calculated, specifically to apply the dynamic discounts based on the module’s rules. It likely intercepts methods like `getProducts()`, `getProductsTotal()`, or `getPackageShippingCost()` to adjust prices before they are finalized. It also contains logic to determine if a discount should be applied based on the cart’s current value and the configured rules.
- `cartdiscount/override/classes/CartRule.php`
  - **Original Class:** `CartRule`
  - **Responsibility:** This override likely extends the `CartRule` class to allow the module to create and manage its own internal `CartRule` objects dynamically. When the module applies a discount, it’s often done by creating a temporary or specific `CartRule` that reflects the calculated discount, which then gets applied to the cart. This override ensures compatibility and proper handling of these dynamically generated rules.
- `cartdiscount/override/classes/index.php`
  - **Responsibility:** Security file, `die('No direct script access allowed');`.
- `cartdiscount/override/classes/order/index.php`
  - **Responsibility:** Security file, `die('No direct script access allowed');`.
- `cartdiscount/override/classes/order/Order.php`
  - **Original Class:** `Order`
  - **Responsibility:** This override ensures that the discounts applied by the module are correctly carried over and stored when an order is placed. It might modify methods related to order creation or total calculation to reflect the applied cart rules.

### 4.4 JavaScript Assets (`views/js/`)

- `cartdiscount/views/admin/js/cdis.js`
  - **Scope:** Back-office.
  - **Responsibility:** This script likely handles client-side interactions for the `AdminCdisListController`. This could include:
    - AJAX calls for saving/updating discount rules.
    - Form validation for the “Add/Edit Discount Rule” form.
    - Dynamic UI updates or interactions within the discount rule management grid.
    - Potentially, handling the “Exclude products from manufacturer” or other dynamic selection fields.

### 4.5 CSS Stylesheets (`views/css/`)

- `cartdiscount/views/admin/css/cdis.css`
  - **Scope:** Back-office admin form styling.
  - **Responsibility:** Provides specific styling for the `AdminCdisListController` interface, ensuring the discount rule management forms and lists are well-presented and consistent with PrestaShop’s back-office UI.
  - **Key CSS class selectors:** Developers can inspect the HTML generated by `AdminCdisListController` to find specific classes (e.g., `.cdis-form`, `.cdis-list-table`) to override if custom admin styling is needed.
- `cartdiscount/views/css/cartdiscount.css`
  - **Scope:** Front-office customer styling.
  - **Responsibility:** Styles the informational messages displayed on the cart page (e.g., “Spend X more for Y% discount!”).
  - **Key CSS class selectors:** Likely targets elements within the `myDiscount.tpl` template (e.g., `.cartdiscount-info`, `.cartdiscount-message`, `.cartdiscount-progress`). Developers can override these classes in their theme’s `custom.css` or equivalent to match the store’s branding.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `cartdiscount/views/templates/hook/myDiscount.tpl`
    - **Hook:** `displayShoppingCartFooter` (and potentially others like `displayHeader` for JS/CSS inclusion).
    - **Visual Block:** This template is responsible for rendering the dynamic messages on the shopping cart page. It displays information about the current cart value, the discount applied, and how much more the customer needs to spend to reach the next discount tier. It also renders the “Additional custom contents” if configured.
- **Admin templates (`views/templates/admin/`)**:
  - The `AdminCdisListController` will use standard PrestaShop admin templates for rendering its list and form views, usually found in `_partials` or `helpers/list/list_header.tpl`, `helpers/form/form.tpl`, etc., which are part of the PrestaShop core. The module itself might not have custom `.tpl` files in `views/templates/admin/` but rather relies on the controller to pass data to the core helpers.
- **Front-office templates (`views/templates/front/`)**: None explicitly defined.
- `cartdiscount/lib/searchTool/views/scripts.tpl`
  - **Scope:** Likely used for including JavaScript or CSS assets for a search tool component within the module’s configuration or a specific feature. Its exact usage would depend on the implementation of the search tool (e.g., for selecting manufacturers to exclude).

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - `ps_cdis`: This custom table stores the actual discount rules defined by the merchant (minimum cart value, discount type, discount value, active status, priority).
  - `ps_configuration`: Module settings like `CDIS_ACTIVE`, `CDIS_PRICETYPE`, `CDIS_GROUPSNOT`, `CDIS_EXMANUFACTURER`, `CDIS_SHOWINFO_CART`, `CDIS_EXSPECIFIC`, `CDIS_ORDERCOUPON`, `cdis_contents` (for custom content), and `mypresta_updates` are stored here.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Used to include module’s front-office CSS (`cartdiscount.css`) and potentially JavaScript, ensuring styles and scripts are loaded for the cart page. |
| `ActionAdminControllerSetMedia` | When an Admin Controller is initialized and its media (JS/CSS) is being set. | Used to include module’s back-office CSS (`cdis.css`) and JavaScript (`cdis.js`) for the `AdminCdisListController`, ensuring proper styling and functionality of the admin interface. |
| `displayShoppingCartFooter` | At the bottom of the shopping cart summary page. | Renders the `myDiscount.tpl` template, displaying informational messages about the discount program, current savings, and next discount tiers to the customer. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Cart discount based on cart value” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
