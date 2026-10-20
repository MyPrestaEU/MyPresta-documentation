---
title: "Cart rule for the most expensive product - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Cart rule for the most expensive product PrestaShop module by MyPresta.eu."
sidebar:
  label: "Cart rule for the most expensive product"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Cart rule for the most expensive product Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/cart-rule-for-the-most-expensive-product.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/cart-rule-for-the-most-expensive-product/)
>
> ---


# Cart rule for the most expensive product

## 1. Requirements & Compatibility

-   **Supported PrestaShop Versions**: PrestaShop 1.7.x
-   **PHP Compatibility**: PHP 7.1 - 8.5
-   **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)
After installation, click "Configure" next to the module in the Module Manager. This will take you to the main configuration screen for "Cart rule for the most expensive product."

#### Settings & Options:

-   **MyPresta.eu Live Updates (mypresta_updates)**
    -   **What this setting does:** This setting controls whether the module can check for updates directly from MyPresta.eu. It helps ensure you're always running the latest version with bug fixes and new features.
    -   **Effect of changing this setting:**
        -   *When enabled (YES):* The module will periodically connect to MyPresta.eu to check for new versions. If an update is available, you might see a notification in your PrestaShop back office.
        -   *When disabled (NO):* The module will not check for updates automatically. You will need to manually check for and download updates from your MyPresta.eu account.
    -   **Recommended value:** YES
    -   **Merchant scenario / example:** Keeping this enabled ensures you receive timely notifications for critical updates, improving security and compatibility without manual effort.

-   **Excluded Products (csc_excluded_products)**
    -   **What this setting does:** This field allows you to specify products that should *never* be considered for the "most expensive product" discount, even if they are indeed the highest-priced item in the cart. This is useful for products with very low margins, special promotions, or items you don't want to discount.
    -   **Effect of changing this setting:**
        -   *When product IDs are entered:* The module will ignore these specific products when determining which item is the "most expensive" for the cart rule. If one of these excluded products is the highest priced, the module will then look for the next most expensive *non-excluded* product to apply the discount to.
        -   *When left empty:* All products in the cart are eligible to be identified as the "most expensive" for the discount.
    -   **Recommended value:** Leave empty unless you have specific products you want to exclude.
    -   **Merchant scenario / example:** You sell a very popular, high-margin product (ID 123) and a few loss-leader items (ID 456, ID 789). You want the "most expensive product" discount to apply to your high-margin items, but not to the loss-leaders. You would enter `456,789` (comma-separated product IDs) into this field.

#### 2.1.1 Cart Rule Edit Page (Back Office > Catalog > Discounts > Cart Rules > Add New / Edit)
This module adds a new option directly to the standard PrestaShop cart rule creation/edit page. You will find this option when you are creating or modifying a cart rule that uses a **percentage discount**.

-   **Menu Location:** Back Office > Catalog > Discounts > Cart Rules. Click "Add new cart rule" or edit an existing one.
-   **Available Action:** On the "Actions" tab of the cart rule configuration, after you select "Percentage" for the "Apply a discount" option, a new checkbox will appear.

    -   **Apply discount to the most expensive product only**
        -   **What this setting does:** This is the core functionality of the module. When enabled for a specific cart rule, the percentage discount defined for that rule will only be applied to the single most expensive product in the customer's cart.
        -   **Effect of changing this setting:**
            -   *When enabled (checked):* The cart rule's percentage discount will be calculated based solely on the price of the highest-priced product in the cart (excluding any products you've globally excluded in the module's main configuration).
            -   *When disabled (unchecked):* The cart rule will behave as a standard PrestaShop percentage discount, applying the discount to the entire cart total or to eligible products as per other cart rule configurations (e.g., product selection, minimum amount).
        -   **Recommended value:** Enable this only for cart rules where you specifically want to target the most expensive item.
        -   **Merchant scenario / example:** You want to run a "20% off your biggest item" promotion. You create a new cart rule, set the discount to 20% (percentage), and then check this box. When customers use this voucher, they'll get 20% off their most expensive item, not 20% off their entire order.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Module Config | MyPresta.eu Live Updates | YES | Enables automatic update checks for the module. |
| Module Config | Excluded Products | Empty | Comma-separated product IDs to exclude from "most expensive" calculation. |
| Cart Rule Edit (Actions Tab) | Apply discount to the most expensive product only | Unchecked | When checked, applies percentage discount only to the highest-priced item in cart. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: The discount isn't applying to the most expensive product, or it's not working at all.**
A:
1.  **Check Cart Rule Configuration:** Go to **Catalog > Discounts > Cart Rules**, edit your rule, and ensure that on the "Actions" tab, "Apply a discount" is set to "Percentage" and the "Apply discount to the most expensive product only" checkbox is **checked**.
2.  **Verify Product Eligibility:** Check the module's main configuration (**Modules > Module Manager > Configure** for "Cart rule for the most expensive product"). Make sure the product you expect the discount to apply to is not listed in the "Excluded Products" field.
3.  **Clear Cache:** Sometimes PrestaShop's cache can prevent changes from taking effect immediately. Go to **Advanced Parameters > Performance** and click "Clear cache" in the top right.
4.  **Module Conflicts:** If you have other modules that heavily modify cart or discount calculations, there might be a conflict. Try disabling other discount-related modules temporarily to see if the issue resolves.

**Q: Can I apply this discount to a specific category of products only?**
A: Yes, you can combine this module's functionality with PrestaShop's standard cart rule restrictions. On the "Conditions" tab of your cart rule, you can add conditions like "Product selection" to specify that the discount only applies if a product from a certain category is in the cart. However, remember that *if* such a product is present, the module will still pick the *overall* most expensive product in the cart (unless that product is excluded) and apply the discount to it, not necessarily the most expensive product *from that specific category*.

**Q: Does this module work with fixed amount discounts?**
A: No, this module is specifically designed to work with **percentage discounts** only. The option "Apply discount to the most expensive product only" will only appear and function when you select "Percentage" as the discount type on the cart rule's "Actions" tab.

**Q: My custom theme doesn't display the discount correctly.**
A: The module primarily modifies the discount calculation logic, not the front-office display. PrestaShop's default templates should show the discount correctly. If your custom theme has heavily customized the cart or checkout summary, it might require minor adjustments to correctly reflect how discounts are applied. In most cases, clearing the Smarty cache (**Advanced Parameters > Performance > Clear cache**) should resolve display issues. If not, consult your theme developer.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview
The "Cart rule for the most expensive product" module (`crexpensive`) primarily extends PrestaShop's core `CartRule` class through an override. This allows it to inject custom logic into the discount calculation process without directly modifying core files. The module also provides a minimal configuration interface in the Back Office and registers a hook to inject necessary JavaScript for the admin forms.

### 4.2 Controllers (`controllers/`)
This module does not introduce any custom front-office or back-office controllers. Its functionality is integrated directly into existing PrestaShop processes via overrides and hooks.

### 4.3 Core Classes & Models (`classes/`)

-   **`crexpensive/override/classes/CartRule.php`**
    *   **Class Name:** `CartRule` (overrides the core `CartRule` class)
    *   **Parent Class:** `CartRuleCore`
    *   **Responsibility:** This override is the heart of the module's functionality. It modifies the behavior of how cart rules are applied, specifically targeting the `reduction_percent` calculation.
    *   **Key Methods & Logic:**
        *   The override likely intercepts or modifies methods related to `reduction_percent` calculation within the `CartRule` class. It will contain logic to:
            1.  Check if the current cart rule has the `apply_to_most_expensive_product` flag enabled (a custom field added by the module).
            2.  If enabled, iterate through the products in the cart to identify the most expensive one, taking into account any globally excluded products configured in the module.
            3.  Adjust the `reduction_percent` application to only affect the identified most expensive product, ensuring the discount is calculated against its price rather than the entire cart or other products.
        *   It also adds a new field to the `CartRule` definition (`$definition`) to store the `apply_to_most_expensive_product` flag in the `ps_cart_rule` database table.

### 4.4 JavaScript Assets (`views/js/`)

-   **`crexpensive/views/js/crexpensive.js`**
    *   **Scope:** Back-office (specifically the Cart Rule edit page).
    *   **Responsibility:** This script is responsible for dynamically showing/hiding the "Apply discount to the most expensive product only" checkbox on the Cart Rule edit page.
    *   **Key Logic:**
        *   It likely listens for changes on the "Apply a discount" dropdown/radio buttons (specifically when "Percentage" is selected).
        *   When "Percentage" is chosen, it makes the custom checkbox visible.
        *   When other discount types (e.g., "Amount," "Free Shipping") are chosen, it hides the checkbox, as the module only applies to percentage discounts.
        *   Ensures the checkbox's state is correctly loaded when editing an existing cart rule.

### 4.5 CSS Stylesheets (`views/css/`)
This module does not include any custom CSS files. It relies on PrestaShop's default styling for its configuration elements and the injected checkbox on the cart rule page.

### 4.6 Smarty Template Structure (`views/templates/`)
This module does not include any custom Smarty template files. The configuration form is rendered via `getContent()` in the main module file, and the custom checkbox is injected into the existing Cart Rule edit page via JavaScript.

### 4.7 Database Schema & Hooks Map

-   **Database Tables**:
    *   The module modifies the `ps_cart_rule` table by adding a new column, likely named `apply_to_most_expensive_product` (or similar), which is a tinyint (boolean) field to store the state of the custom checkbox for each cart rule.
    *   Configuration values (`mypresta_updates`, `csc_excluded_products`) are stored in the `ps_configuration` table.

-   **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| :-------- | :--------------- | :---------------- |
| `actionAdminControllerSetMedia` | Executed when an admin controller is setting its media assets (JS/CSS). | This hook is used to load `crexpensive.js` onto the Cart Rule edit page in the Back Office, enabling the dynamic display of the "Apply discount to the most expensive product only" checkbox. |

## 5. Official Support & Updates
For official updates, technical support, and to access the latest versions of the "Cart rule for the most expensive product" module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have.
