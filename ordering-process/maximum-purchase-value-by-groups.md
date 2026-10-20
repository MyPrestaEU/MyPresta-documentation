---
title: "Maximum purchase value by groups - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Maximum purchase value by groups PrestaShop module by MyPresta.eu."
sidebar:
  label: "Maximum purchase value by groups - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Maximum purchase value by groups Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/maximum-purchase-value-by-groups.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/maximum-purchase-value-by-groups/)
>
> ---


# Maximum purchase value by groups

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installing the module, navigate to **Modules > Module Manager** and search for “Maximum purchase value by groups”. Click the “Configure” button to access its settings.

The configuration page will display a list of all your customer groups, allowing you to set a maximum purchase value for each.

#### **Setting: Maximum purchase value for [Customer Group Name]**

- **What this setting does:** This input field allows you to define the highest total order value (including or excluding tax, depending on the “Apply tax to maximum purchase value” setting) that customers belonging to a specific group can place.
- **Effect of changing this setting:**
  - *When a value is entered (e.g., 500):* Customers in this group will be prevented from completing an order if their cart total exceeds this amount. A warning message will appear in the cart and checkout.
  - *When left empty or set to 0:* There will be no maximum purchase value limit for this specific customer group. They can order any amount.
- **Recommended value:** This depends entirely on your business model and customer segmentation.
  - For **Wholesale Groups**, you might set a high limit (e.g., 5000) or leave it empty if you trust them.
  - For **New Customer Groups**, you might set a lower limit (e.g., 200) to manage risk.
  - For **Default Customer Groups**, you might leave it empty unless you have a specific reason to limit general customers.
- **Merchant scenario / example:** You have a “Wholesale Tier 1” group. You want to ensure that no single order from this group exceeds €10,000 without prior approval. You would enter `10000` in the field next to “Wholesale Tier 1”. If a customer from this group tries to order €10,001, they will be blocked.

#### **Setting: Apply tax to maximum purchase value**

- **What this setting does:** This switch determines whether the maximum purchase value you set for each group should be calculated based on the cart total *including* taxes or *excluding* taxes.
- **Effect of changing this setting:**
  - *When enabled (YES):* The module will compare the customer’s cart total *including all applicable taxes* against the maximum value you’ve defined. This is generally how customers perceive their total cost.
  - *When disabled (NO):* The module will compare the customer’s cart total *excluding taxes* against the maximum value you’ve defined. This might be useful if your internal accounting or wholesale agreements are based on pre-tax values.
- **Recommended value:** **YES**. Most merchants and customers think in terms of the final price, including tax. Enabling this ensures the limit applies to the actual amount the customer will pay.
- **Merchant scenario / example:** You set a maximum value of €500 for a group.
  - If “Apply tax” is YES: A customer with a cart total of €450 (products) + €50 (tax) = €500 will be allowed. A cart of €460 (products) + €50 (tax) = €510 will be blocked.
  - If “Apply tax” is NO: A customer with a cart total of €500 (products) + €50 (tax) = €550 will be allowed because the product total is exactly €500.

#### **Setting: Display message about limitations**

- **What this setting does:** This switch controls whether the informative message about exceeding the maximum purchase value is shown to the customer on the front-office.
- **Effect of changing this setting:**
  - *When enabled (YES):* Customers will see a clear, user-friendly message on the cart and checkout pages if their order total exceeds the limit for their group. This helps them understand why they cannot proceed.
  - *When disabled (NO):* The limitation will still be enforced (customers will be blocked from ordering), but no explicit message will be displayed. This can lead to confusion and a poor customer experience, as they won’t know *why* they can’t complete their order.
- **Recommended value:** **YES**. Always inform your customers clearly. Hiding the message will only lead to frustration and support tickets.
- **Merchant scenario / example:** A customer tries to order too much. If this is enabled, they see “Your order exceeds the maximum allowed value for your customer group (€500). Please reduce your cart total to proceed.” If disabled, they just see an error or the “Proceed to checkout” button remains inactive without explanation.

#### **Setting: Message to display**

- **What this setting does:** This text area allows you to customize the message that customers see when they exceed their group’s maximum purchase value. You can make it more specific to your store’s branding or policies.
- **Effect of changing this setting:**
  - *When a custom message is entered:* This message will be displayed to customers instead of the module’s default message. You can use HTML for basic formatting.
  - *When left empty:* The module will display a default, generic message (e.g., “Your order exceeds the maximum allowed value for your customer group.”).
- **Recommended value:** Customize it to be friendly and helpful. Include placeholders like `{max_value}` and `{currency_sign}` if the module supports them (check the module’s actual behavior, as this specific module might not use placeholders directly but rather dynamically inserts the value). A good default is often sufficient.
- **Merchant scenario / example:** Instead of a generic message, you might want to say: “Dear valued customer, your current order total exceeds the maximum allowed purchase value of {max\_value} {currency\_sign} for your account type. Please adjust your cart or contact our sales team for larger orders.”

Remember to click the **“Save”** button at the bottom of the configuration page after making any changes.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Maximum purchase value for [Group Name] | Empty / Varies | Sets the upper spending limit for a specific customer group. Empty means no limit. |
| Module Configuration | Apply tax to maximum purchase value | YES | Determines if the limit applies to the cart total with or without taxes. Recommended: YES (final price). |
| Module Configuration | Display message about limitations | YES | Controls whether customers see an explanation when blocked. Recommended: YES (for clarity). |
| Module Configuration | Message to display | Default message | Customizes the warning message shown to customers. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve set a limit, but customers can still order more than that. What’s wrong?**
A:

1. **Check the customer’s group:** Ensure the customer you’re testing with actually belongs to the group for which you’ve set the limit.
2. **“Apply tax” setting:** Double-check if the “Apply tax to maximum purchase value” setting is correctly configured. If your limit is 500 and it’s set to “NO” (exclude tax), a customer might be able to order 500 in products + tax, which appears to exceed 500.
3. **Module enabled:** Make sure the module is actually enabled in your Module Manager.
4. **Cache:** Clear your PrestaShop cache (Advanced Parameters > Performance > Clear cache) and your browser cache.

**Q: The message about the limitation isn’t showing, but customers are still blocked.**
A: Check the “Display message about limitations” setting in the module configuration. Ensure it is set to “YES”. If it’s set to “NO”, the module will enforce the limit silently, which can be confusing for customers.

**Q: Can I set different messages for different customer groups?**
A: No, the module currently uses a single “Message to display” setting that applies to all groups. If you need group-specific messages, this would require custom development.

**Q: Does this module affect discounts or shipping costs?**
A: The module typically evaluates the *final cart total* at the point of checkout, which usually includes discounts, shipping costs, and taxes (depending on your “Apply tax” setting). So, the limit applies to the ultimate amount the customer is expected to pay.

**Q: My custom theme doesn’t display the message correctly.**
A: This can happen if your theme has highly customized cart or checkout templates.

1. **Clear Smarty cache:** Go to **Advanced Parameters > Performance**, set “Template compilation” to “Force compilation” and “Cache” to “No”, then clear the cache. Test again. Revert settings afterward.
2. **CSS conflict:** Your theme’s CSS might be overriding the module’s styling. You might need a web developer to inspect the element and apply custom CSS to ensure the message is visible and styled correctly.
3. **Hook issue:** Ensure your theme correctly calls the standard PrestaShop hooks where the module injects its content (e.g., `displayShoppingCart`, `displayPaymentTop`).

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The `Maximum purchase value by groups` module (`cgmaxa`) is a standard PrestaShop module implementing the MVC pattern. It primarily operates by hooking into key front-office events during the cart and checkout process to validate the current cart total against group-specific limits stored in the `ps_configuration` table. It uses a front controller for AJAX requests to provide dynamic feedback and a main module class for configuration and hook registration.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `cgmaxa/controllers/front/ajax.php`
  - **Class name**: `CgmaxaAjaxModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility**: This controller handles AJAX requests from the front-office, likely for real-time validation of the cart total as items are added/removed or during the checkout steps. It would typically receive cart data, perform the limit check, and return a JSON response indicating whether the limit is exceeded and the relevant message.
- `cgmaxa/controllers/front/index.php`
  - **Class name**: `CgmaxaIndexModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility**: This controller might be a placeholder or used for specific routing that doesn’t fit into the main module dispatch. Given its name, it could potentially be a default entry point or handle non-AJAX front-office interactions if the module had a dedicated page, though its primary function for this module is likely minimal or for fallback.

#### Back-Office Admin Controllers

This module does not appear to use any dedicated admin controllers. All configuration is handled directly within the main module’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

This module does not appear to define any custom classes or `ObjectModel`s in a `classes/` directory. All logic is encapsulated within the main module file (`cgmaxa.php`) and its controllers. Configuration values are stored directly in `ps_configuration`.

### 4.4 JavaScript Assets (`views/js/`)

- `cgmaxa/views/js/cgmaxa.js`
  - **Scope**: Front-office.
  - **Details**: This script is responsible for client-side interactions. It likely binds to events such as quantity changes in the cart, adding/removing products, or navigating through checkout steps. It would send AJAX requests to `cgmaxa/controllers/front/ajax.php` to validate the cart total in real-time. Upon receiving a response, it would dynamically display the warning message (if the limit is exceeded) and potentially disable the “Proceed to checkout” or “Payment” buttons to prevent order finalization. It might also update the message dynamically with the current cart value and the maximum allowed value.

### 4.5 CSS Stylesheets (`views/css/`)

- `cgmaxa/css.css`
  - **Scope**: Front-office.
  - **Details**: This stylesheet provides the basic styling for the warning message displayed to customers when they exceed the purchase limit. It likely defines classes for the message container, text color, background, and possibly icons to make the alert stand out. Developers can override these styles in their theme’s `custom.css` or by using more specific selectors.
- `cgmaxa/views/css/cgmaxa.css`
  - **Scope**: Front-office.
  - **Details**: Similar to `cgmaxa/css.css`, this file provides styling for the front-office elements. It might contain more specific or updated styles compared to `cgmaxa/css.css`, or one might be a legacy file. Developers should inspect both to understand the full styling applied. Key selectors would target the message container and its content.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `cgmaxa/views/templates/front/displayShoppingCart.tpl`
  - **Hook**: `displayShoppingCart` (and potentially `displayPaymentTop`, `stepBeforePaymentOPC`, `displaystepBeforePaymentOPC`).
  - **Output**: This template is responsible for rendering the warning message on the shopping cart page and potentially other checkout steps. It would contain the HTML structure for the alert box, dynamically inserting the custom message and the maximum allowed value if the limit is exceeded. It likely uses Smarty variables passed from the module’s hook methods to determine if the message should be displayed and what content it should contain.

#### Admin templates (`views/templates/admin/`)

- `cgmaxa/admin.tpl`
  - **Scope**: Back-office configuration.
  - **Output**: This template is used by the module’s `getContent()` method to render the configuration form in the PrestaShop Back Office. It includes the input fields for each customer group’s maximum value, the “Apply tax” switch, the “Display message” switch, and the custom message text area. It iterates through available customer groups to create the dynamic input fields.

### 4.7 Database Schema & Hooks Map

#### Database Tables

The module does not create any custom database tables. All configuration settings (maximum values per group, tax setting, message display, custom message) are stored in the `ps_configuration` table using keys like `CGMAXA_GROUP_[ID_GROUP]`, `CGMAXA_TAX`, `CGMAXA_DISPLAY_MESSAGE`, `CGMAXA_MESSAGE`.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | To include necessary CSS and JavaScript files (`cgmaxa.js`, `cgmaxa.css`) for front-office functionality and AJAX validation. |
| `displayShoppingCart` | On the shopping cart summary page. | To display the warning message if the cart total exceeds the group’s limit and potentially disable the “Proceed to checkout” button. |
| `displayPaymentTop` | At the top of the payment selection step in the checkout process. | To re-validate the cart total before payment and display the warning message, blocking further progress if the limit is exceeded. |
| `stepBeforePaymentOPC` | Before the payment step in the One-Page Checkout (OPC). | Similar to `displayPaymentTop`, this hook ensures validation occurs right before the customer can select a payment method, crucial for OPC flows. |
| `displaystepBeforePaymentOPC` | Another hook related to the step before payment in OPC. | Provides an additional point for validation and message display in specific OPC themes or configurations. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Maximum purchase value by groups” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and configuration.
