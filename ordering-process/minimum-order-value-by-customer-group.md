---
title: "Minimum order value by customer group - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Minimum order value by customer group PrestaShop module by MyPresta.eu."
sidebar:
  label: "Minimum order value by customer group - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Minimum order value by customer group Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/minimum-order-value-by-customer-group.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/minimum-order-value-by-customer-group/)
>
> ---


# Minimum order value by customer group

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen where you define the minimum order values for each customer group.

#### General Settings

- **Exclude specific customer groups from minimum order value rule:**

  - **What this setting does:** This allows you to select customer groups that will *not* be subject to any minimum order value, even if you’ve set one for them below. They can always checkout regardless of their cart total.
  - **Effect of changing this setting:**
    - *When enabled (groups selected):* Customers belonging to the selected groups will bypass all minimum order value checks.
    - *When disabled (no groups selected):* All customer groups will be subject to the minimum order values you define.
  - **Recommended value:** Depends on your business model. If you have VIPs or specific B2C customers you want to exempt, select them here. Otherwise, leave empty.
  - **Merchant scenario / example:** You have a “VIP Customers” group who you want to always be able to checkout, even if their order is small. Select “VIP Customers” here.
- **Include tax in minimum order value:**

  - **What this setting does:** Determines whether the minimum order value you set should include or exclude the tax amount calculated for the products in the cart.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The module will check the cart total *including* taxes against your defined minimum.
    - *When disabled (NO):* The module will check the cart total *excluding* taxes against your defined minimum.
  - **Recommended value:** “YES” for most B2C stores, as customers typically see and pay the total price including tax. “NO” might be preferred for B2B stores where prices are often quoted ex-tax.
  - **Merchant scenario / example:** If you set a minimum of $100 and this is enabled, a cart total of $90 (ex-tax) + $10 (tax) = $100 would pass. If disabled, the same cart would fail because $90 is less than $100.
- **Include shipping cost in minimum order value:**

  - **What this setting does:** Determines whether the shipping cost for the order should be added to the cart total before checking against the minimum order value.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The module will check (Cart Total + Shipping Cost) against your defined minimum.
    - *When disabled (NO):* The module will check only the Cart Total (products) against your defined minimum.
  - **Recommended value:** “NO” in most cases, as minimums are usually about product value. However, if your shipping costs are very high and you want to ensure a certain total transaction value, you might enable this.
  - **Merchant scenario / example:** You want customers to buy at least $50 worth of products. If this is “NO”, a $50 product cart passes. If this is “YES” and shipping is $10, the customer would need $50 in products + $10 shipping = $60 total to pass, meaning they’d need $60 worth of products to meet the $50 minimum. This setting is usually “NO” to avoid confusion.
- **Apply minimum order value for first order only:**

  - **What this setting does:** If enabled, the minimum order value rules will only apply to a customer’s very first order in your store. Subsequent orders will not be subject to the minimums.
  - **Effect of changing this setting:**
    - *When enabled (YES):* Only new customers (those who haven’t placed an order before) will face the minimum order value restrictions.
    - *When disabled (NO):* All orders, regardless of whether they are a customer’s first or tenth, will be checked against the minimum order value.
  - **Recommended value:** “NO” for most scenarios where you want consistent minimums. “YES” could be useful for encouraging initial larger purchases from new clients, then relaxing the rules for repeat business.
  - **Merchant scenario / example:** You want new B2B clients to place a substantial first order of $500 to establish their account, but after that, they can order any amount. Enable this and set the $500 minimum for your B2B group.

#### Minimum Order Values by Customer Group

Below the general settings, you will find a list of all your customer groups. For each group, you can define a minimum order value.

- **Customer Group Name (e.g., “Visitor”, “Guest”, “Customer”, “Wholesale”):**
  - **What this setting does:** This is where you input the specific minimum order amount required for customers belonging to this particular group.
  - **Effect of changing this setting:**
    - *When a value is entered (e.g., 50.00):* Customers in this group must have a cart total equal to or greater than this value to proceed to checkout.
    - *When left empty or set to 0.00:* There is no minimum order value for this customer group. They can checkout with any cart total.
  - **Recommended value:** Set a value that makes business sense for each group. Leave empty for groups like “Visitor” or “Guest” unless you specifically want to block them from ordering.
  - **Merchant scenario / example:**
    - For “Customer” group: Set to `25.00` to encourage slightly larger retail purchases.
    - For “Wholesale” group: Set to `200.00` to ensure profitability on B2B orders.
    - For “Guest” group: Leave empty (`0.00`) to allow quick purchases without registration.

#### Multi-Store & Multi-Currency Considerations

- **Multi-Store:** If you have multiple stores enabled, you will see a dropdown at the top of the configuration page (usually next to the “Save” button) allowing you to select which store you are configuring. The minimum order values can be set independently for each store.
- **Multi-Currency:** The minimum order values you enter are always in the *default currency* of your PrestaShop store. The module automatically converts these values to the customer’s selected currency at the current exchange rate when checking the cart total.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Exclude specific customer groups | Empty | Select groups to bypass minimum order rules. |
| Module Configuration | Include tax in minimum order value | YES | Determines if tax is part of the minimum total. |
| Module Configuration | Include shipping cost in minimum order value | NO | Determines if shipping is part of the minimum total. |
| Module Configuration | Apply minimum order value for first order only | NO | Applies minimums only to a customer’s initial purchase. |
| Module Configuration | Minimum order value for [Customer Group Name] | 0.00 (empty) | Set the required cart total for each customer group. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My customers are seeing the minimum order message even though their cart total seems correct. What’s wrong?**
A:

1. **Check Tax/Shipping Settings:** Double-check if “Include tax in minimum order value” or “Include shipping cost in minimum order value” are enabled. The displayed cart total might be different from the value the module is checking against.
2. **Currency Conversion:** If you operate in multiple currencies, ensure the exchange rates are up-to-date. The module converts your default currency minimums to the customer’s selected currency.
3. **Customer Group Assignment:** Verify that the customer is correctly assigned to the customer group you intend, and that the minimum value for that group is set as expected.
4. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes, old cached data can cause issues.

**Q: I’ve set a minimum, but a specific customer group can still checkout with any amount. Why?**
A: Check the “Exclude specific customer groups from minimum order value rule” setting on the module configuration page. If that customer group is selected there, they will bypass all minimum order checks. Remove them from this exclusion list if you want the minimum to apply.

**Q: The module message isn’t showing up, or it looks strange on my custom theme.**
A:

1. **Theme Compatibility:** Custom themes might override standard PrestaShop templates or CSS, potentially affecting how module messages are displayed.
2. **CSS Conflicts:** Another module or your theme’s CSS might be conflicting with the module’s styling.
3. **Smarty Cache:** Clear your Smarty cache (Advanced Parameters > Performance > Clear cache) to ensure the latest template files are being used.
   For visual issues, you may need to consult a web developer to inspect your theme’s CSS and template files.

**Q: Can I set different minimums for different products?**
A: No, this module sets a minimum for the *total cart value* based on the customer group, not for individual products. If you need product-specific minimums, you would require a different type of module.

**Q: How does this module handle multi-store setups?**
A: The module is multi-store friendly. When configuring, use the “Shop context” selector at the top of the PrestaShop back office (usually next to the “Save” button) to switch between your stores. You can then set unique minimum order values for each customer group, per store.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Minimum order value by customer group” module (`cgma`) is built following PrestaShop’s standard module architecture. It primarily uses hooks to inject its logic into the front-office cart and checkout process. Configuration is managed via the main module class’s `getContent()` method, storing settings in `ps_configuration`. Front-office interaction is handled by a dedicated AJAX controller for real-time cart validation.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `cgma/controllers/front/ajax.php`
    - **Class Name:** `CgmaAjaxModuleFrontController` (extends `ModuleFrontController`)
    - **Responsibility:** This controller handles AJAX requests from the front-office, primarily for real-time validation of the cart total against the customer group’s minimum order value. It likely returns a JSON response indicating whether the cart meets the requirements and potentially a message to display to the user. This is crucial for dynamic updates without full page reloads.
  - `cgma/controllers/front/index.php`
    - **Class Name:** `CgmaIndexModuleFrontController` (extends `ModuleFrontController`)
    - **Responsibility:** This is a placeholder or fallback controller. In many modules, if a specific action isn’t defined, requests might fall to an `index` controller. It might also be used for simple redirects or to ensure a valid module route exists, though its primary function in this module is likely minimal compared to `ajax.php`.
- **Back-Office Admin Controllers**:

  - None explicitly defined in the inventory. All back-office configuration is handled directly within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

- No custom classes or `ObjectModel` definitions are explicitly listed in the inventory. The module likely relies on PrestaShop’s core `Customer`, `Group`, `Cart`, and `Configuration` classes for its functionality. Configuration values are stored directly in the `ps_configuration` table.

### 4.4 JavaScript Assets (`views/js/`)

- `cgma/views/js/cgma.js`
  - **Scope:** Front-office.
  - **Details:** This script is responsible for client-side interaction and validation. It likely listens for changes in the shopping cart (e.g., quantity updates, product removals) or attempts to proceed to checkout. It would then trigger AJAX calls to `cgma/controllers/front/ajax.php` to validate the cart total against the minimum order value. Upon receiving a response, it would dynamically update the cart summary or checkout buttons, displaying messages to the user if the minimum is not met and potentially disabling the “Proceed to Checkout” button. It might also handle displaying the minimum order value message in various front-office locations.

### 4.5 CSS Stylesheets (`views/css/`)

- `cgma/css.css`

  - **Scope:** Likely front-office.
  - **Details:** This stylesheet provides the basic styling for the module’s front-office messages or elements, such as the warning message displayed when the minimum order value is not met.
  - **Key CSS class selectors:** Developers should inspect this file for classes like `.cgma-warning-message`, `.cgma-disabled-button`, or similar, which can be overridden in a custom theme.
- `cgma/views/css/cgma.css`

  - **Scope:** Likely front-office.
  - **Details:** Similar to `cgma/css.css`, this file provides additional or more specific styling for the module’s front-office components. It might contain responsive adjustments or specific layout rules.
  - **Key CSS class selectors:** Check for selectors related to cart summary, checkout buttons, or specific message containers.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - None explicitly listed in the inventory, but the module’s `displayShoppingCart` hook implementation would likely render a template. It’s possible the `displayShoppingCart.tpl` is directly in `views/templates/front/` and used by the hook.
- **Admin templates (`views/templates/admin/`)**:

  - `cgma/admin.tpl`
    - **Scope:** Back-office configuration.
    - **Details:** This template is rendered by the `getContent()` method of the main module class (`cgma.php`). It contains the HTML structure for the module’s configuration form, including input fields for general settings (exclude groups, tax/shipping inclusion, first order only) and dynamic fields for setting minimum order values for each customer group.
- **Front-office templates (`views/templates/front/`)**:

  - `cgma/views/templates/front/displayShoppingCart.tpl`
    - **Scope:** Front-office, specifically the shopping cart page.
    - **Details:** This template is likely rendered when the module hooks into `displayShoppingCart`. It displays the warning message to the customer if their cart total does not meet the minimum order value for their group. It might also contain logic to disable the “Proceed to Checkout” button or provide instructions on how to meet the minimum.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create custom SQL tables.
  - Configuration settings are stored in the `ps_configuration` table using keys such as `CGMA_EXCV`, `CGMA_TAX`, `CGMA_FREE`, `CGMA_FIRST_ORDER`, and `CGMA_[GROUP_ID]_[CURRENCY_ID]` for the minimum values per group and currency. `PS_CURRENCY_DEFAULT` is also referenced.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `stepBeforePaymentOPC` | Before the payment step in the One-Page Checkout. | Prevents customers from proceeding to payment if minimum order value is not met. |
| `displayPaymentTop` | At the top of the payment options section during checkout. | Displays a warning message if the minimum order value is not met. |
| `displaystepBeforePaymentOPC` | Similar to `stepBeforePaymentOPC`, often used for displaying content or additional checks. | Ensures minimum order value is met before payment, potentially displaying a message. |
| `displayShoppingCart` | On the shopping cart summary page. | Validates the cart total and displays a warning message if the minimum is not met, potentially disabling checkout buttons. |
| `displayHeader` | In the `<head>` section of every front-office page. | Injects necessary CSS (`cgma.css`) and JavaScript (`cgma.js`) files for front-office functionality and styling. |

## 5. Official Support & Updates

For official updates, technical support, and to access the latest versions of the “Minimum order value by customer group” module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have.
