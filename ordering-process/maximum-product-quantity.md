---
title: "Maximum product quantity - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Maximum product quantity PrestaShop module by MyPresta.eu."
sidebar:
  label: "Maximum product quantity"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Maximum product quantity Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/maximum-product-quantity.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/maximum-product-quantity/)
>
> ---


# Maximum product quantity

## 1. Requirements & Compatibility
-   **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **PHP Compatibility**: PHP 5.6 - 8.5
-   **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually required.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Maximum product quantity)

The module's main configuration page is where you define the global settings and manage product-specific quantity limits.

#### **General Settings**

-   **What this setting does:** These are the core settings that enable or disable the module's functionality and define how it behaves globally.
-   **Effect of changing this setting:**
    -   *Enable/Disable Module:* Turns the entire quantity limiting system on or off.
    -   *Global Maximum Quantity:* Sets a default maximum quantity for all products if no specific limit is defined.
-   **Recommended value:** Start by enabling the module and setting a reasonable global maximum if you want to apply a general rule.
-   **Merchant scenario / example:** If you want to ensure no customer can ever buy more than 100 units of *any* product, set the global maximum to 100.

#### **Product-Specific Quantity Limits**

This section is usually a table or a list where you can search for products and define specific limits for them.

-   **What this setting does:** Allows you to override the global settings for individual products. You can specify:
    -   **Maximum quantity per order:** The highest number of units of this product a customer can add to a single cart.
    -   **Maximum quantity per customer (total):** The highest number of units of this product a specific customer can purchase *across all their orders*.
    -   **Customer Group Specific Limits:** Apply different limits based on the customer group (e.g., "Guests," "Customers," "Wholesalers").
-   **Effect of changing this setting:**
    -   *When limits are set:* The module will enforce these specific limits for the chosen product, overriding any global settings.
    -   *When limits are removed:* The product will revert to using the global maximum quantity settings.
-   **Recommended value:** Set specific limits for high-demand, low-stock, or strategically important products.
-   **Merchant scenario / example:**
    -   You have a limited edition product. You set "Maximum quantity per order" to 1 and "Maximum quantity per customer (total)" to 1 to ensure one unit per customer.
    -   For a bulk item, you might set "Maximum quantity per order" to 50 for "Customers" but 500 for "Wholesalers."

#### **Order History Tracking Settings**

-   **What this setting does:** Controls whether the module looks at a customer's past orders to enforce "maximum quantity per customer (total)" limits. You can often specify which order statuses count towards the limit (e.g., only "Delivered" orders, or "Payment accepted").
-   **Effect of changing this setting:**
    -   *When enabled:* The module will query the customer's order history to calculate their total purchases of a product.
    -   *When disabled:* Only the current cart quantity will be checked against the "maximum quantity per order" limit. "Maximum quantity per customer (total)" limits will effectively be ignored.
-   **Recommended value:** Enable this if you want to enforce true per-customer limits over time. Select relevant order statuses (e.g., "Payment accepted," "Delivered") to accurately track purchases.
-   **Merchant scenario / example:** You're running a promotion where each customer can only buy a maximum of 3 units of a specific product *ever*. You enable order history tracking and select "Payment accepted" and "Delivered" statuses. If a customer has already bought 2, they can only add 1 more to their cart.

#### **Error Message Customization**

-   **What this setting does:** Allows you to customize the message displayed to customers when they exceed a quantity limit.
-   **Effect of changing this setting:** The default, generic error message will be replaced with your custom text, which can be more informative or branded.
-   **Recommended value:** Provide a clear, polite, and helpful message. You can use placeholders (if supported by the module) like `{max_quantity}` to show the actual limit.
-   **Merchant scenario / example:** Instead of "Quantity exceeds maximum," you could set it to: "Sorry, you can only purchase a maximum of {max_quantity} units of this item. This helps us ensure fair access for all our customers!"

#### **CSV / JSON Export & Import (if available)**

-   **What this setting does:** Provides tools to export your current quantity limits to a CSV or JSON file, and import new limits from such files. This is useful for bulk editing or migrating settings.
-   **Effect of changing this setting:**
    -   *Export:* Creates a file with all your defined product quantity limits.
    -   *Import:* Overwrites or adds new quantity limits based on the data in the uploaded file.
-   **Recommended value:** Use this for large-scale updates or initial setup if you have many products with specific limits. Always back up your current settings before importing.
-   **Merchant scenario / example:** You're launching a new catalog with 500 products, each needing a unique maximum quantity. Instead of manually entering each, you prepare a CSV file and import it.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|---|
| Module Configuration | Enable/Disable Module | Enabled | Turns on/off all quantity limiting features. |
| Module Configuration | Global Max Quantity per Order | Varies / 100 | Sets a default max quantity for products without specific limits. |
| Module Configuration | Product-Specific Max Qty per Order | Varies / Custom | Overrides global limit for individual products in a single cart. |
| Module Configuration | Product-Specific Max Qty per Customer (Total) | Varies / Custom | Limits total purchases of a product by a customer across all orders. |
| Module Configuration | Customer Group Specific Limits | Varies / Custom | Applies different limits based on customer groups (e.g., Wholesalers). |
| Module Configuration | Track Order History | Enabled | Checks past orders to enforce "Max Qty per Customer (Total)". |
| Module Configuration | Order Statuses for Tracking | Payment accepted, Delivered | Defines which order statuses count towards total customer purchases. |
| Module Configuration | Custom Error Message | "Quantity exceeds limit" | Personalizes the message shown to customers when a limit is hit. |
| Module Configuration | Export/Import CSV/JSON | N/A | Allows bulk management of quantity limits via file upload/download. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I've set limits, but customers can still add more than allowed. What's wrong?**
A1:
*   **Module Enabled?** First, double-check that the module is enabled in the main configuration.
*   **Specific Product vs. Global:** Ensure you've set the limits correctly for the *specific product* in question, or that the global limits are active if no product-specific limits exist.
*   **Customer Group:** Verify that the customer group the customer belongs to has the correct limits applied.
*   **Cache:** Clear your PrestaShop cache (Advanced Parameters > Performance > Clear cache). Sometimes, old settings are still being served.
*   **Theme Conflicts:** Rarely, a highly customized theme might interfere with how quantity inputs are handled. Test with the default PrestaShop theme to rule this out.

**Q2: The "maximum quantity per customer (total)" isn't working, even with order history tracking enabled.**
A2:
*   **Order Statuses:** Go to the module configuration and check which "Order Statuses for Tracking" are selected. If a customer's previous orders are in a status not selected (e.g., "Pending" instead of "Delivered"), they won't count towards the limit. Make sure the relevant statuses are checked.
*   **Customer Login:** Ensure the customer is logged in. The module can only track previous purchases for identified customers, not guests.

**Q3: How do I translate the error messages into other languages?**
A3:
*   Navigate to **International > Translations** in your PrestaShop Back Office.
*   Select "Installed modules translations," choose your theme, and then select your language.
*   Find the "Maximum product quantity" module in the list. You should be able to edit the custom error messages you've set for each language.

**Q4: The module seems to be slowing down my product pages or cart.**
A4:
*   While the module is optimized, if you have an extremely large number of products with complex, group-specific limits and extensive order history tracking, it might add a slight overhead.
*   **Performance > CCC:** Ensure your CCC (Combine, Compress, Cache) settings for CSS and JavaScript are enabled in **Advanced Parameters > Performance**.
*   **Server Resources:** Check your server's PHP memory limit and execution time. If they are too low, it can impact performance.
*   **Database Optimization:** Ensure your PrestaShop database is regularly optimized.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters working with the "Maximum product quantity" module.

### 4.1 Architecture Overview
The `Maximum product quantity` module (internal name `mqc`) is a standard PrestaShop module designed to extend the core ordering process. It primarily operates by hooking into various points of the front-office (product page, cart, checkout) to validate product quantities against configured limits. The configuration is managed through a single `getContent()` method in the main module file, leveraging PrestaShop's `Configuration` class for storing settings. It utilizes JavaScript for front-end validation and user feedback, and Smarty templates for displaying messages and configuration forms.

### 4.2 Controllers (`controllers/`)
This module does not contain dedicated front-office or back-office controllers. All front-office logic is handled via hooks and JavaScript, while back-office configuration is managed directly within the `index.php` module file's `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)
The module does not define custom `ObjectModel` classes. All data is stored directly in the `ps_configuration` table using standard PrestaShop configuration keys. The core logic resides within the `mqc/index.php` file.

### 4.4 JavaScript Assets (`views/js/`)

-   **`mqc/views/js/mqc-17500.js`**:
    *   **Scope:** Front-office (PrestaShop 1.7.5.0+ specific).
    *   **Responsibility:** Contains JavaScript logic tailored for newer PrestaShop 1.7.x and 8.x versions. It likely hooks into `prestashop.on('updateProduct', ...)` or similar events to re-validate quantities when product attributes change or when the quantity input is modified on the product page. It might also handle AJAX calls to the module's `index.php` to get real-time quantity validation.
    *   **Interaction:** Binds to quantity input fields, add-to-cart buttons, and potentially product attribute selectors to provide immediate feedback to the user if a quantity limit is exceeded.

-   **`mqc/views/js/mqc-front.js`**:
    *   **Scope:** Front-office (general, potentially for older PrestaShop versions or common logic).
    *   **Responsibility:** Contains general front-office JavaScript logic for quantity validation. This might include:
        *   Event listeners for quantity input changes in the product page or cart.
        *   AJAX calls to the server to check quantity limits.
        *   Displaying error messages to the user.
        *   Potentially disabling or limiting quantity input fields.
    *   **Interaction:** Similar to `mqc-17500.js` but might use older jQuery-based event binding or less specific PrestaShop events.

-   **`mqc/views/js/mqc.js`**:
    *   **Scope:** Back-office.
    *   **Responsibility:** Handles JavaScript for the module's configuration page in the PrestaShop Back Office. This could include:
        *   Dynamic form elements (e.g., adding/removing product-specific limit rows).
        *   AJAX search for products when setting individual limits.
        *   Validation of input fields on the configuration form.
        *   Logic for CSV/JSON import/export functionalities.
    *   **Interaction:** Binds to form elements on the module configuration page, potentially making AJAX requests to the module's `getContent()` method for data retrieval or submission.

### 4.5 CSS Stylesheets (`views/css/`)

-   **`mqc/views/css/mqc.css`**:
    *   **Scope:** Both Front-office (for error messages) and Back-office (for configuration page styling).
    *   **Main UI components and containers it styles:**
        *   Error message containers (e.g., `div.alert.alert-danger` or custom classes for module-specific messages).
        *   Input fields and labels on the back-office configuration page.
        *   Potentially styling for dynamic elements added by `mqc.js` (e.g., product search results, table rows for limits).
    *   **Key CSS class selectors developers can override:** Look for classes like `.mqc-error-message`, `.mqc-limit-table`, `.mqc-product-search-results` within the module's templates and generated HTML. Developers can override these in their theme's `custom.css` or by creating a child theme.

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses Smarty templates for both front-office display and back-office configuration.

-   **Hook templates (`views/templates/hook/`)**:
    *   **`product-details.tpl`**:
        *   **Hook:** Likely `displayProductExtraContent` or `displayProductButtons` (depending on PrestaShop version and specific implementation).
        *   **Output:** Could display a small informational message about quantity limits on the product page, or render a custom quantity input field if the module replaces the default.
    *   **`productActions.tpl`**:
        *   **Hook:** `displayProductActions` (on the product page).
        *   **Output:** Potentially used to inject JavaScript variables or hidden inputs related to quantity limits near the add-to-cart button, or to display an error message if a quantity limit is exceeded before adding to cart.
    *   **`shoppingCart.tpl`**:
        *   **Hook:** `displayShoppingCartFooter` or `displayShoppingCart` (on the cart page).
        *   **Output:** Used to display error messages directly within the shopping cart if quantities exceed limits, preventing checkout.

-   **Admin templates (`views/templates/admin/`)**: These templates are rendered within the `getContent()` method of `mqc/index.php` to build the module's configuration interface.
    *   **`admintab.tpl`**: Likely a wrapper or a common header/footer for the admin configuration page.
    *   **`button-subcategories-purchases.tpl`**: Could be a button or section related to managing purchases by subcategories, possibly for advanced reporting or limit setting.
    *   **`button-subcategories.tpl`**: Similar to the above, but for subcategories in general.
    *   **`csv.tpl`**: Template for the CSV export functionality, potentially containing form elements for selecting export options.
    *   **`csv_file.tpl`**: Template for the CSV import functionality, usually an upload form.
    *   **`json.tpl`**: Template for JSON export/import, similar to `csv.tpl` and `csv_file.tpl`.
    *   **`main.tpl`**: The primary template for the module's configuration page, containing the main form structure, general settings, and potentially a table for product-specific limits.
    *   **`message.tpl`, `message2.tpl`, `message3.tpl`, `message4.tpl`, `message5.tpl`**: Generic message templates used to display success, error, or informational messages within the back-office configuration.
    *   **`orderstates.tpl`**: Template for selecting which order statuses count towards the "maximum quantity per customer (total)" limit.

### 4.7 Database Schema & Hooks Map

-   **Database Tables**:
    *   The module does not create custom SQL tables.
    *   All configuration settings are stored in the `ps_configuration` table. Configuration keys will typically follow a pattern like `MQC_GLOBAL_MAX_QTY`, `MQC_PRODUCT_LIMITS_[id_product]`, `MQC_TRACK_HISTORY_STATUSES`, etc. Product-specific limits might be stored as serialized arrays or JSON strings in a single configuration key, or individual keys per product/group.
    *   Order history tracking relies on querying existing PrestaShop tables: `ps_orders`, `ps_order_detail`, and `ps_order_state`.

-   **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
|---|---|---|
| `displayHeader` | In the `<head>` section of every page. | Registers CSS and JavaScript assets (`mqc.css`, `mqc-front.js`, `mqc-17500.js`) for front-office functionality. |
| `displayProductButtons` | Near the "Add to Cart" button on the product page. | Injects quantity validation logic or displays messages related to product-specific limits. |
| `displayProductExtraContent` | Below the product description, above related products. | Can be used to display informational messages about quantity limits. |
| `displayShoppingCart` | Within the shopping cart summary. | Validates quantities in the cart and displays error messages if limits are exceeded. |
| `displayShoppingCartFooter` | At the bottom of the shopping cart page. | Similar to `displayShoppingCart`, for final validation before checkout. |
| `actionValidateOrder` | After an order has been validated and saved. | Potentially used for post-order processing or logging, though primary validation is pre-checkout. |
| `actionCartSave` | After a cart is saved or updated (e.g., quantity change). | Crucial for real-time quantity validation when a customer modifies quantities in the cart or adds new products. |
| `actionFrontControllerSetMedia` | Before a front controller renders its output. | Registers front-office assets, similar to `displayHeader` but more specific to the controller context. |
| `actionAdminControllerSetMedia` | Before an admin controller renders its output. | Registers back-office assets (`mqc.js`, `mqc.css`) for the module's configuration page. |

## 5. Official Support & Updates
For the latest updates, bug fixes, and official support for the "Maximum product quantity" module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist merchants and developers with any issues or questions regarding the module's functionality and integration.
