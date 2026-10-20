---
title: "Exclude selected products from free shipping - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Exclude selected products from free shipping PrestaShop module by MyPresta.eu."
sidebar:
  label: "Exclude selected products from free shipping - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Exclude selected products from free shipping Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/exclude-selected-products-from-free-shipping.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/exclude-selected-products-from-free-shipping/)
>
> ---


# Exclude selected products from free shipping

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main screen where you’ll define the core rules for excluding products from free shipping.

#### 2.1.1 General Settings

- **Remove voucher code with free shipping**

  - **What this setting does:** This option determines whether a free shipping voucher (a `CartRule` that grants free shipping) should be removed or invalidated from the customer’s cart if an excluded product is present.
  - **Effect of changing this setting:**
    - *When enabled (YES):* If a customer applies a free shipping voucher and then adds a product you’ve marked for exclusion, the module will attempt to remove that voucher from their cart. This ensures that even with a voucher, free shipping is not granted for excluded items.
    - *When disabled (NO):* Free shipping vouchers will remain active even if an excluded product is in the cart. This means a customer could still get free shipping via a voucher, overriding the module’s product-based exclusion.
  - **Recommended value:** **YES**. This provides the most consistent control over your shipping costs, preventing free shipping even when a voucher is used.
  - **Merchant scenario / example:** You sell large furniture items that always incur a shipping cost. You also offer a “FREESHIP” voucher for orders over $100. If a customer adds a sofa (an excluded product) and uses the “FREESHIP” voucher, enabling this setting will remove the voucher, ensuring they pay for shipping the sofa.
- **Exclude out of stock products**

  - **What this setting does:** This option allows you to automatically exclude products that are currently out of stock from qualifying for free shipping.
  - **Effect of changing this setting:**
    - *When enabled (YES):* If a product is out of stock and in the customer’s cart, and you’ve also marked it for exclusion, the module will apply its rules. This is generally less relevant as out-of-stock products often can’t be ordered anyway, but it ensures consistency.
    - *When disabled (NO):* The module will not consider the stock status when applying its exclusion rules.
  - **Recommended value:** **NO**. This setting is often redundant as out-of-stock products usually cannot be added to the cart or ordered. Keep it disabled unless you have a specific reason to use it (e.g., allowing backorders where free shipping should still be blocked).
  - **Merchant scenario / example:** You allow backorders for certain items. If an item is on backorder (out of stock) and is also a large, heavy item you never ship for free, enabling this setting ensures that even on backorder, it contributes to disabling free shipping.

#### 2.1.2 Free Shipping Exclusion Rules

- **Disable free shipping for selected products**

  - **What this setting does:** This is the core functionality. It allows you to specify individual products that, when in the cart, will disable free shipping.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The module will look for the specific products you’ve added to the exclusion list. If any of these products are in the customer’s cart, free shipping will be disabled.
    - *When disabled (NO):* No individual products will disable free shipping, regardless of what’s in the exclusion list.
  - **Recommended value:** **YES**. Enable this to use the module’s primary feature.
  - **Merchant scenario / example:** You sell fine jewelry (small, light, usually free shipping) and also large display cases (heavy, expensive to ship). You would enable this and add the display cases to the exclusion list.
- **Disable free shipping for selected categories**

  - **What this setting does:** Similar to products, this option allows you to select entire product categories. If *any* product from a selected category is in the customer’s cart, free shipping will be disabled.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The module will check if any product in the cart belongs to one of the categories you’ve selected for exclusion. If so, free shipping is disabled.
    - *When disabled (NO):* No categories will disable free shipping.
  - **Recommended value:** **YES** if you have entire groups of products that should never qualify for free shipping.
  - **Merchant scenario / example:** You sell both books and large art prints. All art prints require special packaging and shipping. You would enable this and select the “Art Prints” category. Any art print in the cart will disable free shipping.

#### 2.1.3 Product & Category Selection Interface

Below these settings, you will find two sections:

- **Products to exclude from free shipping:** A search bar and a list of currently excluded products.
  - **How to use:** Start typing the name of a product in the search bar. As you type, a list of matching products will appear. Click on a product to add it to the exclusion list. To remove a product, click the “X” next to its name in the list.
- **Categories to exclude from free shipping:** A tree-view of your store’s categories with checkboxes.
  - **How to use:** Check the box next to any category you wish to exclude. All products within that category (and its subcategories, depending on your PrestaShop version’s category behavior) will disable free shipping if present in the cart.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Main Configuration | Remove voucher code with free shipping | YES | Ensures free shipping vouchers are removed if excluded products are in cart. |
| Module Main Configuration | Exclude out of stock products | NO | Generally not needed, as out-of-stock items often can’t be ordered. |
| Module Main Configuration | Disable free shipping for selected products | YES | Activates product-specific free shipping exclusion. |
| Module Main Configuration | Disable free shipping for selected categories | YES | Activates category-specific free shipping exclusion. |
| Module Main Configuration | Products to exclude from free shipping | (Empty) | Add specific products here using the search tool. |
| Module Main Configuration | Categories to exclude from free shipping | (None selected) | Select categories from the tree view. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve configured the module, but free shipping is still showing for an excluded product. What’s wrong?**
A:

1. **Check your settings:** Double-check that “Disable free shipping for selected products” (or categories) is enabled, and that the specific product/category is correctly added to the exclusion list.
2. **Clear PrestaShop Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” in the top right. Sometimes PrestaShop caches shipping calculations.
3. **Test with a new cart:** Ensure you’re testing with a fresh cart, as browser cache or session data might interfere. Try in an incognito window.
4. **Voucher conflict:** If you’re using a free shipping voucher, ensure “Remove voucher code with free shipping” is enabled.

**Q: Does this module affect my standard shipping rates?**
A: No, this module only affects the *availability* of the “Free Shipping” option (either via cart rules or specific free shipping carriers). It does not modify your standard shipping rates or other carrier configurations. If free shipping is disabled, customers will simply see and pay for your regular shipping options.

**Q: Can I exclude products based on weight or dimensions instead of specific products/categories?**
A: This module specifically targets products and categories. PrestaShop’s built-in shipping rules allow you to define free shipping thresholds based on total cart weight or price. This module adds an *exception* layer on top of those rules. If you need more complex rules based purely on weight/dimensions for *all* products, you might need a more advanced shipping module or custom carrier configurations.

**Q: What happens if a customer has an excluded product and a non-excluded product in their cart?**
A: If *any* product in the cart is on your exclusion list (either directly or via its category), free shipping will be disabled for the entire cart, even if other products in the cart would normally qualify. The module’s logic is “if any excluded product is present, then no free shipping.”

**Q: I’m using a custom theme, and the product search tool isn’t working correctly.**
A: Custom themes can sometimes interfere with JavaScript.

1. **Check for JavaScript errors:** Open your browser’s developer console (usually F12) and look for any errors in the “Console” tab when you try to use the search tool.
2. **Theme compatibility:** Ensure your theme is fully compatible with your PrestaShop version.
3. **Contact support:** If you see errors or the issue persists, provide screenshots and console logs to MyPresta.eu support.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Exclude selected products from free shipping” module primarily operates by overriding core PrestaShop classes related to cart and cart rule management. This allows it to intercept the free shipping calculation logic and apply its exclusion rules before the final shipping options are presented to the customer. It leverages PrestaShop’s override system for `CartController`, `Cart`, and `CartRule` classes. The module also includes a dedicated admin controller for searching and managing excluded products/categories.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `exfreeshipping/override/controllers/front/CartController.php`
    - **Class name & parent class**: `CartController` (overrides `CartControllerCore`)
    - **Responsibility**: This override is crucial for intercepting actions related to the cart, particularly when products are added or removed, or when shipping calculations are performed. It ensures that the module’s logic is applied whenever the cart state changes, affecting free shipping eligibility.
- **Back-Office Admin Controllers**:

  - `exfreeshipping/controllers/admin/AdminExfreeshippingSearchController.php`
    - **Tab name and managed entity**: This controller handles the AJAX search functionality for products within the module’s configuration. It does not manage a specific `ObjectModel` directly but provides data for the product exclusion list.
    - **Purpose**: Responds to AJAX requests from the module configuration page to search for products by name, allowing the administrator to easily select products to exclude.
  - `exfreeshipping/controllers/admin/index.php`
    - **Purpose**: This is a standard empty `index.php` file often included in directories to prevent directory listing on web servers. It does not contain any functional controller logic.

### 4.3 Core Classes & Models (`classes/`)

- `exfreeshipping/override/classes/Cart.php`

  - **Class name & parent class**: `Cart` (overrides `CartCore`)
  - **Database table**: `ps_cart`
  - **Responsibility**: This override is central to the module’s functionality. It likely modifies methods related to shipping cost calculation or free shipping eligibility within the `Cart` object. It will contain the logic to check if any product in the cart (or its category) is on the exclusion list and, if so, to disable the free shipping flag for that cart.
  - **Key methods (likely modified/extended)**: `getProducts()`, `getPackageList()`, `getWsShippingCost()`, `getShippingCost()`, or similar methods that determine shipping eligibility.
- `exfreeshipping/override/classes/CartRule.php`

  - **Class name & parent class**: `CartRule` (overrides `CartRuleCore`)
  - **Database table**: `ps_cart_rule`
  - **Responsibility**: This override is responsible for handling the “Remove voucher code with free shipping” setting. It modifies methods related to cart rule application or validation to remove free shipping vouchers if an excluded product is present in the cart.
  - **Key methods (likely modified/extended)**: `checkValidity()`, `addCartRule()`, `removeCartRule()` or similar methods that interact with cart rules and their validity.
- `exfreeshipping/override/classes/index.php`

  - **Purpose**: Similar to the admin `index.php`, this is an empty file to prevent directory listing.

### 4.4 JavaScript Assets (`views/js/`)

- `exfreeshipping/lib/searchTool/views/js/autocomplete.js`
  - **Scope**: Back-office (module configuration page).
  - **Functionality**: This script powers the product search and selection interface on the module’s configuration page.
  - **Details**:
    - Initializes an autocomplete input field for searching products.
    - Binds event listeners (e.g., `keyup`, `change`, `click`) to the search input and result list.
    - Sends AJAX requests to `AdminExfreeshippingSearchController` to fetch product suggestions based on user input.
    - Handles the display of search results and allows administrators to select products, adding them to a hidden input field or a visible list of excluded products.
    - Manages the removal of selected products from the exclusion list.

### 4.5 CSS Stylesheets (`views/css/`)

- `exfreeshipping/lib/searchTool/views/css/autocomplete.css`
  - **Scope**: Back-office (module configuration page).
  - **Styling**: Provides styling for the product search autocomplete input, the dropdown list of search results, and the display of selected excluded products on the module’s configuration page.
  - **Key selectors**: Likely includes styles for `.autocomplete-input`, `.autocomplete-results`, `.selected-product-tag`, etc. Developers can override these in their custom admin themes if needed.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Admin templates (`views/templates/admin/`)**:
  - `exfreeshipping/lib/searchTool/views/scripts.tpl`
    - **Purpose**: This template is likely included in the module’s `getContent()` method to render the necessary HTML structure for the product search tool, including the search input field and the area where selected products are displayed. It also likely includes the `<script>` tag to load `autocomplete.js`.
  - `exfreeshipping/views/tpl/selectedProducts.tpl`
    - **Purpose**: This template is used to render the list of products that have been selected for exclusion from free shipping. It’s dynamically updated by the JavaScript when products are added or removed.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create custom SQL tables.
  - Configuration settings are stored in the `ps_configuration` table using keys like `exfreeshipping_oos`, `exfreeshipping_vcode`, `exfreeshipping_visibility_rule`, `exfreeshipping_visibility_products`, `exfreeshipping_visibility_cat`.
  - The lists of excluded products and categories are stored as serialized arrays or comma-separated strings within `ps_configuration` under `exfreeshipping_visibility_products` and `exfreeshipping_visibility_cat` respectively.
- **Registered Hooks Table**:
  The module primarily uses overrides rather than direct hook calls for its core logic. However, it might register some standard hooks for initialization or specific display purposes.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionFrontControllerSetMedia` | Executed when a front controller is setting its media (CSS/JS). | Potentially used to load any front-office specific CSS/JS, though the module’s primary impact is backend logic. |
| `displayHeader` | In the `<head>` section of every front-office page. | Could be used for initial setup or loading of very lightweight scripts/styles if needed, but not directly for the core logic. |
| `displayBackOfficeHeader` | In the `<head>` section of every back-office page. | Used to load the `autocomplete.js` and `autocomplete.css` for the module’s configuration page. |
| `actionCartSave` | After a cart is saved or updated. | This is where the module’s core logic for checking excluded products and disabling free shipping would be triggered or re-evaluated. |
| `actionValidateOrder` | When an order is validated. | Ensures that free shipping rules are correctly applied at the final stage of checkout. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and technical support for the “Exclude selected products from free shipping” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist you with any issues or questions regarding the module’s functionality and compatibility.
