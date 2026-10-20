---
title: "Minimal product quantity - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Minimal product quantity PrestaShop module by MyPresta.eu."
sidebar:
  label: "Minimal product quantity - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Minimal product quantity Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/minimal-product-quantity.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/minimal-product-quantity/)
>
> ---


# Minimal product quantity

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” will take you to the main settings page for the “Minimal product quantity” module. This is where you define the core rules for minimum quantities.

The configuration page is designed to be intuitive, allowing you to set minimum quantities for individual products and specific customer groups.

**How to set a minimum quantity for a product:**

1. **Search for a Product:**

   - You will see a search bar or a list of products. Start typing the name of the product you want to configure. As you type, the module will suggest matching products.
   - *What this setting does:* Allows you to quickly locate the specific product you want to apply a minimum quantity rule to.
   - *Effect of changing this setting:* N/A (search function).
   - *Recommended value:* Type the exact product name for precision.
   - *Merchant scenario:* You want to set a minimum for “Organic Coffee Beans (1kg)”. Type “Organic Coffee”.
2. **Select the Product:**

   - Click on the desired product from the search results. This will add it to a list of configured products below.
   - *What this setting does:* Confirms which product you are applying the rule to.
   - *Effect of changing this setting:* The product appears in the configuration list, ready for quantity and group settings.
   - *Recommended value:* Select the correct product.
   - *Merchant scenario:* After typing “Organic Coffee”, you click on “Organic Coffee Beans (1kg)”.
3. **Set Minimum Quantity:**

   - Next to the selected product, there will be an input field (e.g., “Minimal quantity”). Enter the lowest number of units a customer must purchase for this specific product.
   - *What this setting does:* Defines the absolute minimum number of units for this product.
   - *Effect of changing this setting:*
     - *When set to 5:* Customers must add at least 5 units of this product to their cart. If they try to add 1, 2, 3, or 4, they will receive an error message.
     - *When set to 1 (or default PrestaShop behavior):* No special minimum quantity is enforced beyond PrestaShop’s default.
   - *Recommended value:* A number greater than 1, reflecting your business needs (e.g., 6, 12, 24).
   - *Merchant scenario:* You sell coffee beans in bulk. You set the “Minimal quantity” to 5.
4. **Select Customer Group (Optional):**

   - You will likely see a dropdown or list of customer groups (e.g., “Guest”, “Customer”, “Wholesaler”). You can select one or more groups for which this minimum quantity applies.
   - *What this setting does:* Allows you to apply different minimum quantity rules based on the customer’s group. If no group is selected, the rule applies to all customers.
   - *Effect of changing this setting:*
     - *When “Wholesaler” is selected:* Only customers belonging to the “Wholesaler” group will be subject to this minimum quantity. Other groups might have a different minimum (or no minimum).
     - *When no specific group is selected (or “All Customers” is implied):* The minimum quantity applies to every customer, regardless of their group.
   - *Recommended value:* Select specific groups if you have different pricing or sales strategies for them. Otherwise, leave it for “All Customers”.
   - *Merchant scenario:* You want wholesalers to buy at least 10 units, but regular customers only need to buy 5. You would create two separate rules for the same product, one for “Wholesaler” group with quantity 10, and another for “Customer” group with quantity 5.
5. **Save Changes:**

   - After configuring the product(s) and their minimum quantities/groups, remember to click the “Save” or “Update” button to apply your settings.
   - *What this setting does:* Persists your configuration changes to the database.
   - *Effect of changing this setting:* The new minimum quantity rules become active on your front office immediately.
   - *Recommended value:* Always save after making changes.
   - *Merchant scenario:* You’ve set up all your minimums; now you click “Save” to make them live.

**General Module Settings (if present):**

While the primary function is per-product minimums, some modules might include general settings:

- **Enable/Disable Module:**

  - *What this setting does:* Turns the entire module’s functionality on or off.
  - *Effect of changing this setting:*
    - *When enabled:* Minimum quantity rules are enforced.
    - *When disabled:* All minimum quantity rules are ignored, and customers can add any quantity.
  - *Recommended value:* YES (enabled) once configured.
  - *Merchant scenario:* You’re testing the module and want to temporarily disable it without losing your settings.
- **Display Error Message Type (e.g., Pop-up, Inline):**

  - *What this setting does:* Controls how the customer is notified when they try to add less than the minimum quantity.
  - *Effect of changing this setting:*
    - *When set to Pop-up:* A modal window appears, interrupting the user flow, clearly stating the issue.
    - *When set to Inline:* A message appears directly on the product page or cart, without a pop-up.
  - *Recommended value:* Pop-up is often more effective for critical errors like minimum quantities, as it demands attention.
  - *Merchant scenario:* You want to ensure customers don’t miss the minimum quantity requirement, so you choose a pop-up.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Product Search | N/A | Locate products to apply minimum quantity rules. |
| Module Configuration Page | Minimal quantity (per product) | Varies (e.g., 5, 10) | Sets the lowest number of units a customer must purchase for that product. |
| Module Configuration Page | Customer Group (per product) | All Customers | Applies the minimum quantity rule to specific customer groups or all customers. |
| Module Configuration Page | Save Button | N/A | Applies all configured minimum quantity rules to the store. |
| Module Configuration Page | Enable/Disable Module | Enabled | Turns the module’s functionality on or off globally. |
| Module Configuration Page | Error Message Type | Pop-up | Defines how minimum quantity errors are displayed to customers. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve set a minimum quantity, but it’s not working on my store. What’s wrong?**
A:

1. **Is the module enabled?** Double-check the main configuration page to ensure the “Minimal product quantity” module is active.
2. **Did you save your changes?** Always click the “Save” or “Update” button after making any configuration changes.
3. **Clear your PrestaShop cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes, PrestaShop caches old settings.
4. **Check for theme conflicts:** If you have a highly customized theme, it might interfere with how the module displays messages or interacts with the “Add to Cart” button. Temporarily switch to the default PrestaShop theme (Classic or Hummingbird) to see if the issue persists. If it resolves, your theme needs adjustment.
5. **Customer Group:** Ensure the customer you are testing with belongs to the group for which the minimum quantity is set. If no group is specified, it should apply to all.

**Q2: The pop-up notification looks strange or doesn’t match my store’s design.**
A: The module uses its own CSS for the pop-up. If your theme has very specific styling rules, they might override or conflict.

1. **Check module settings:** See if the module offers options to customize the pop-up’s appearance or choose a different display method (e.g., inline message instead of pop-up).
2. **Custom CSS:** For developers or webmasters, custom CSS can be added to your theme’s `custom.css` file to override the module’s default styles. (See Section 7.5 for CSS file details).

**Q3: Can I set a minimum quantity for product combinations (attributes)?**
A: The module typically applies minimum quantities at the product level. If you need specific minimums for combinations (e.g., “Red T-shirt, Size S” vs. “Blue T-shirt, Size L”), you might need to check if the module explicitly supports this in its configuration. If not, you would set the minimum for the parent product, which applies to any combination of that product.

**Q4: How do I translate the module’s messages into other languages?**
A:

1. Go to **International > Translations** in your PrestaShop Back Office.
2. Select “Installed modules translations”.
3. Choose your theme, the language you want to translate, and then select “Minimal product quantity” from the module list.
4. You will find all translatable strings used by the module (e.g., “You must add at least X units of this product”). Translate them and save.

**Q5: What happens if a customer has a product in their cart that later has a minimum quantity applied?**
A: When the customer next visits their cart or attempts to checkout, the module will detect the discrepancy. They will be prompted with the error message and prevented from proceeding until they adjust the quantity to meet the new minimum.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Minimal product quantity” module (`minqc`) follows a standard PrestaShop module architecture, primarily leveraging hooks to inject its logic and front-end assets. It operates by intercepting quantity changes and cart additions, validating against configured minimums, and displaying feedback to the user. The module’s core logic resides within its main `index.php` file, which handles installation, uninstallation, configuration, and hook registration. Front-end interaction is managed through a suite of JavaScript files tailored for different PrestaShop versions and contexts (product page, cart, quick view).

### 4.2 Controllers (`controllers/`)

This module does not appear to utilize custom Front-Office or Back-Office Admin Controllers. Its configuration is handled directly within the `getContent()` method of the main module class, and front-office interactions are managed via JavaScript and AJAX calls to core PrestaShop functionalities or the module’s own `ajax.php` (if present, though not explicitly listed as a dedicated controller, it’s a common pattern for modules to handle AJAX requests via their main file or a simple script).

### 4.3 Core Classes & Models (`classes/`)

Based on the provided inventory, this module does not define custom `ObjectModel` classes or other complex PHP classes in a dedicated `classes/` directory. Its logic is likely encapsulated within the main `minqc/index.php` file, directly interacting with `Configuration` for settings and potentially `Db` for custom data storage if product-specific minimums are stored outside `ps_configuration`.

### 4.4 JavaScript Assets (`views/js/`)

The module extensively uses JavaScript to provide a dynamic user experience and enforce quantity rules in real-time.

- `minqc/views/js/minqc.js`:

  - **Scope:** Likely a core JS file, potentially loaded globally or on multiple pages.
  - **Responsibility:** Contains general utility functions, event binding for common elements, and potentially the main logic for checking minimum quantities before adding to cart or updating the cart. It might handle the display of the pop-up notification.
  - **Interactions:** Binds to `click` events on “Add to Cart” buttons, `change` events on quantity input fields, and potentially `prestashop.on` events for AJAX cart updates.
- `minqc/views/js/minqc-17500.js`:

  - **Scope:** Front-office, specifically for PrestaShop 1.7.5.0 and newer versions (or similar version ranges).
  - **Responsibility:** Contains version-specific JavaScript logic to adapt to changes in PrestaShop’s front-office structure, AJAX cart behavior, or product page elements introduced in these versions.
  - **Interactions:** Overrides or extends `minqc.js` for specific PrestaShop 1.7+ DOM structures and event handling.
- `minqc/views/js/minqc-admin-product.js`:

  - **Scope:** Back-office, specifically on the product editing page (`AdminProducts`).
  - **Responsibility:** If the module allows setting minimum quantities directly on the product edit page, this script would handle the UI for that (e.g., adding input fields, saving values via AJAX).
  - **Interactions:** Binds to events on product form elements, makes AJAX calls to save product-specific minimums.
- `minqc/views/js/minqc-cart.js`:

  - **Scope:** Front-office, specifically on the shopping cart page.
  - **Responsibility:** Monitors quantity changes within the cart, validates against minimums, and prevents checkout if rules are violated. Displays error messages or pop-ups on the cart page.
  - **Interactions:** Binds to quantity input changes, “Proceed to Checkout” button clicks, and potentially `prestashop.on` events related to cart updates.
- `minqc/views/js/minqc-front.js`:

  - **Scope:** General front-office usage.
  - **Responsibility:** Could be a more generic front-end script, potentially handling the display of minimum quantity information on product listings or other non-specific product/cart pages.
  - **Interactions:** DOM manipulation for displaying messages, potentially AJAX calls for validation.
- `minqc/views/js/minqc-no-autoadd.js`:

  - **Scope:** Front-office.
  - **Responsibility:** Suggests a specific behavior related to preventing automatic addition of products to the cart if minimums are not met, or handling scenarios where a product might be auto-added but then fails validation.
  - **Interactions:** Modifies default “Add to Cart” behavior to ensure validation occurs *before* the item is added.
- `minqc/views/js/minqc-product-classic.js`:

  - **Scope:** Front-office, specifically for themes based on the PrestaShop Classic theme (PrestaShop 1.7+).
  - **Responsibility:** Adapts the minimum quantity enforcement and display to the DOM structure and JavaScript events specific to the Classic theme’s product page.
  - **Interactions:** Binds to “Add to Cart” button and quantity input elements on the Classic theme product page.
- `minqc/views/js/minqc-product-hummingbird.js`:

  - **Scope:** Front-office, specifically for themes based on the PrestaShop Hummingbird theme (PrestaShop 8+).
  - **Responsibility:** Adapts the minimum quantity enforcement and display to the DOM structure and JavaScript events specific to the Hummingbird theme’s product page.
  - **Interactions:** Binds to “Add to Cart” button and quantity input elements on the Hummingbird theme product page.

### 4.5 CSS Stylesheets (`views/css/`)

- `minqc/views/css/minqc.css`:
  - **Scope:** Front-office and potentially Back-office for module-specific UI elements.
  - **Main UI components:** Styles for the pop-up notification (modal background, content box, close button, message text), inline error messages, and potentially visual indicators on product pages.
  - **Key CSS class selectors:** Developers can inspect the module’s output HTML to identify specific classes (e.g., `.minqc-popup`, `.minqc-error-message`, `.minqc-quantity-input-error`) and override them in their theme’s `custom.css` or `theme.css` to match their store’s branding.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**: Not explicitly listed, but common for modules to use `displayHeader` for JS/CSS, or `displayProductActions` for product page messages.
- **Admin templates (`views/templates/admin/`)**:

  - `minqc/views/templates/admin/admin.tpl`: Likely the main configuration template for the module, rendered by `getContent()` method. It would contain the product search, list of configured products, and general settings.
  - `minqc/views/templates/admin/admintab.tpl`: Could be a sub-template for a specific tab or section within the admin configuration, or a legacy template.
  - `minqc/views/templates/admin/_configure/helpers/list/list_content.tpl`: This suggests the module uses PrestaShop’s `HelperList` for displaying the list of products with configured minimum quantities in the back office. This template would define how each row in that list is rendered.
- **Ajax templates (`views/templates/ajax/`)**:

  - `minqc/views/templates/ajax/minqcErrors.tpl`: This template is likely used to render the HTML content of the error pop-up or inline messages displayed to the customer when a minimum quantity is not met. It would be loaded via AJAX.
- **Front-office templates (`views/templates/front/`)**:

  - `minqc/views/templates/front/beforeShoppingCart.tpl`: This template is likely hooked into a position before the main shopping cart content, potentially to display a warning or summary related to minimum quantities if the cart is invalid.
  - `minqc/views/templates/front/product-details.tpl`: This template would be used to inject minimum quantity information or warnings directly into the product details page, often near the quantity selector or “Add to Cart” button.
  - `minqc/views/templates/front/productActions.tpl`: Similar to `product-details.tpl`, this template would be hooked into the `displayProductActions` hook (or similar) to display messages or modify the “Add to Cart” button behavior based on minimum quantity rules.
  - `minqc/views/templates/front/qv.tpl`: This template is specifically for the “Quick View” functionality, injecting minimum quantity information or warnings into the quick view modal.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module likely stores its configuration for product-specific minimum quantities and customer group associations in the `ps_configuration` table for simple global settings.
  - For product-specific and group-specific minimums, it’s highly probable that the module creates its own custom database table (e.g., `ps_minqc_product_quantity`) to store `id_product`, `id_customer_group`, and `min_quantity` values. This table would be created during the `install()` method and dropped during `uninstall()`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Injects module’s CSS (`minqc.css`) and JavaScript files (`minqc.js`, `minqc-front.js`, version-specific JS like `minqc-17500.js`, `minqc-product-classic.js`, `minqc-product-hummingbird.js`, `minqc-cart.js`, `minqc-no-autoadd.js`) for front-end functionality. |
| `displayProductActions` | On the product page, typically near the “Add to Cart” button. | Injects `productActions.tpl` to display minimum quantity requirements or warnings directly on the product page. |
| `displayProductExtraContent` (or similar) | On the product page, for additional content blocks. | Could be used to display `product-details.tpl` or other information. |
| `displayShoppingCartFooter` (or similar) | At the bottom of the shopping cart summary. | Injects `beforeShoppingCart.tpl` or similar to display warnings if cart items don’t meet minimums, preventing checkout. |
| `actionCartSave` | After a cart is saved or updated. | Triggers the module’s PHP logic to re-validate all quantities in the cart against configured minimums. |
| `actionValidateOrder` | Before an order is officially validated. | Final check to ensure all product quantities in the cart meet their minimums before the order is placed. |
| `actionProductUpdate` / `actionProductAdd` | When a product is updated or added in the Back Office. | Potentially used to update or clear cached minimum quantity data for that product. |
| `displayAdminProductsExtra` | On the product edit page in the Back Office. | Injects UI elements (e.g., via `admintab.tpl` or `admin.tpl`) to allow setting product-specific minimum quantities directly from the product form, utilizing `minqc-admin-product.js`. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please log in to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions related to the “Minimal product quantity” module.
