---
title: "Mass quantity update pro - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Mass quantity update pro PrestaShop module by MyPresta.eu."
sidebar:
  label: "Mass quantity update pro - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Mass quantity update pro Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/mass-quantity-update-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/mass-quantity-update-pro/)
>
> ---


# Mass quantity update pro

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The “Mass quantity update pro” module provides a single, intuitive configuration screen in your PrestaShop back office where you define the products to update and the quantity changes to apply.

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

To access the module’s configuration, navigate to **Modules > Module Manager**, search for “Mass quantity update pro”, and click the “Configure” button.

The configuration page is divided into two main sections: **Target Products** and **What to do?**.

#### 2.1.1 Target Products

This section allows you to define *which* products or product combinations will be affected by the quantity update. You can select products based on various criteria.

- **What this setting does:** This section defines the scope of your quantity update. You choose the specific group of products that will have their quantities modified.
- **Effect of changing this setting:** Only products matching the selected criteria will be considered for the quantity update. If no criteria are selected, no products will be targeted.
- **Recommended value:** Select one or more criteria that precisely define the products you intend to modify.

**Available Criteria:**

1. **Products from categories:**

   - **What this setting does:** Allows you to select one or more specific product categories. All products (and their combinations) belonging to these categories will be targeted.
   - **Effect of changing this setting:**
     - *When selected:* Products within the chosen categories will be included.
     - *When not selected:* Products are not filtered by category.
   - **Recommended value:** Select this if you need to update stock for an entire product line or department.
   - **Merchant scenario / example:** You’ve received a new shipment for all products in your “Summer Collection” category. You can select this category to update their stock.
2. **Products by brand:**

   - **What this setting does:** Allows you to select one or more specific product brands (manufacturers). All products (and their combinations) associated with these brands will be targeted.
   - **Effect of changing this setting:**
     - *When selected:* Products from the chosen brands will be included.
     - *When not selected:* Products are not filtered by brand.
   - **Recommended value:** Select this if you need to update stock for products from a particular supplier or brand.
   - **Merchant scenario / example:** Your supplier “Fashionista Inc.” has delivered new stock. You select “Fashionista Inc.” to update all their products.
3. **Products by features:**

   - **What this setting does:** Allows you to select products based on their assigned features (e.g., “Color: Red”, “Material: Cotton”). You can choose a feature and then specific values for that feature.
   - **Effect of changing this setting:**
     - *When selected:* Only products possessing the specified feature and value will be included.
     - *When not selected:* Products are not filtered by features.
   - **Recommended value:** Useful for highly specific updates based on product characteristics.
   - **Merchant scenario / example:** You want to update stock for all “Organic Cotton” t-shirts. You select “Material” as the feature and “Organic Cotton” as the value.
4. **Products by attributes:**

   - **What this setting does:** Allows you to select products based on their attributes (e.g., “Size: M”, “Color: Blue”). This is particularly useful for product combinations.
   - **Effect of changing this setting:**
     - *When selected:* Only product combinations with the specified attribute and value will be included.
     - *When not selected:* Products are not filtered by attributes.
   - **Recommended value:** Essential for managing stock of specific product variations.
   - **Merchant scenario / example:** You’ve received a new delivery of “Size L” t-shirts. You select “Size” as the attribute and “L” as the value to update only those combinations.
5. **Products by tax rule associations:**

   - **What this setting does:** Allows you to select products based on the tax rule group applied to them.
   - **Effect of changing this setting:**
     - *When selected:* Only products associated with the chosen tax rule group will be included.
     - *When not selected:* Products are not filtered by tax rule.
   - **Recommended value:** Useful for stores with complex tax structures or when stock updates are tied to tax-related inventory.
   - **Merchant scenario / example:** You need to adjust stock for all products subject to a specific “Import Duty” tax rule.
6. **Specific products:**

   - **What this setting does:** Provides an autocomplete search box to manually select individual products by name.
   - **Effect of changing this setting:**
     - *When products are added:* Only the explicitly selected products (and their combinations) will be targeted.
     - *When empty:* No specific products are targeted this way.
   - **Recommended value:** Use this for very precise updates on a small, hand-picked set of products.
   - **Merchant scenario / example:** You need to update stock for “Product A”, “Product B”, and “Product C” which are unrelated by category or brand.

#### 2.1.2 What to do?

This section defines *how* the quantities of the targeted products will be changed.

- **What this setting does:** This section specifies the type of quantity modification (increase, decrease, or set to a fixed value) and the amount of the change.
- **Effect of changing this setting:** The selected operation will be applied to the quantities of all products defined in the “Target Products” section.
- **Recommended value:** Choose the operation that accurately reflects your inventory adjustment.

**Available Operations:**

1. **Increase quantity by:**

   - **What this setting does:** Adds a specified number to the current quantity of each targeted product/combination.
   - **Effect of changing this setting:** The stock level for each targeted item will go up by the entered amount.
   - **Recommended value:** Use when new stock arrives. Enter a positive integer (e.g., `10`).
   - **Merchant scenario / example:** You received 50 units of a product. You select “Increase quantity by” and enter `50`.
2. **Decrease quantity by:**

   - **What this setting does:** Subtracts a specified number from the current quantity of each targeted product/combination.
   - **Effect of changing this setting:** The stock level for each targeted item will go down by the entered amount.
   - **Recommended value:** Use when stock needs to be reduced due to damage, returns, or internal use. Enter a positive integer (e.g., `5`).
   - **Merchant scenario / example:** 5 items were damaged in the warehouse. You select “Decrease quantity by” and enter `5`.
3. **Set quantity to:**

   - **What this setting does:** Changes the current quantity of each targeted product/combination to a specific, fixed number.
   - **Effect of changing this setting:** The stock level for each targeted item will become exactly the entered amount, regardless of its previous quantity.
   - **Recommended value:** Use when you need to synchronize stock with an external system or correct an absolute stock count. Enter a non-negative integer (e.g., `100`).
   - **Merchant scenario / example:** After a full inventory count, you know you have exactly 100 units of a product. You select “Set quantity to” and enter `100`.

**Important Note:** After defining both “Target Products” and “What to do?”, you must click the **“Update quantities”** button to apply the changes. There is no “undo” button, so always double-check your selections before confirming.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | **Target Products** |  | Defines which products/combinations will be affected. |
|  | Products from categories | Select as needed | Targets all products within chosen categories. |
|  | Products by brand | Select as needed | Targets all products from chosen brands. |
|  | Products by features | Select as needed | Targets products with specific features/values. |
|  | Products by attributes | Select as needed | Targets product combinations with specific attributes/values. |
|  | Products by tax rule associations | Select as needed | Targets products associated with chosen tax rules. |
|  | Specific products | Select as needed | Targets individually selected products. |
|  | **What to do?** |  | Defines how quantities will be changed. |
|  | Increase quantity by | Enter positive integer | Adds specified amount to current stock. |
|  | Decrease quantity by | Enter positive integer | Subtracts specified amount from current stock. |
|  | Set quantity to | Enter non-negative integer | Sets stock to an exact, specified amount. |
|  | **Update quantities button** | Click to apply | Executes the defined quantity changes. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I updated quantities, but my store still shows the old numbers. What’s wrong?**
**A1:** This is usually a caching issue. PrestaShop uses caching to speed up your store.

- **Solution:** Go to **Advanced Parameters > Performance** in your PrestaShop back office. Click “Clear cache” (or “Clear Smarty cache” / “Clear cache” depending on your PrestaShop version). This should force your store to display the updated quantities.

**Q2: I made a mistake and updated the wrong products/quantities. Can I undo it?**
**A2:** The module does not have an “undo” button. This is why it’s crucial to double-check your selections before clicking “Update quantities.”

- **Solution:** If you have a recent backup of your database, you can restore it (though this might revert other recent changes). Otherwise, you will need to manually correct the quantities for the affected products, or use the module again with the correct settings to re-adjust them. For example, if you accidentally increased by 10, you can decrease by 10.

**Q3: The module isn’t finding products when I type in the “Specific products” search box.**
**A3:** Ensure you are typing the full or partial name of an existing product in your store. The autocomplete feature relies on JavaScript.

- **Solution:**
  1. Check your browser’s console for any JavaScript errors (F12 key, then “Console” tab).
  2. Try clearing your browser cache.
  3. Ensure your PrestaShop store is running on a compatible PHP version (see section 3).
  4. If the issue persists, contact MyPresta.eu support.

**Q4: Can I update quantities for products that have combinations (attributes)?**
**A4:** Yes, absolutely! The module is designed to handle product combinations. When you select products by category, brand, feature, or specific product, it will apply the quantity change to all associated combinations of those products. If you use “Products by attributes,” you can even target specific combinations directly.

**Q5: The module seems slow when updating a very large number of products.**
**A5:** Updating thousands of products can be resource-intensive.

- **Solution:**
  1. Ensure your server meets PrestaShop’s recommended specifications.
  2. Increase PHP execution time limits (`max_execution_time`) and memory limits (`memory_limit`) in your `php.ini` file (consult your hosting provider or webmaster).
  3. If possible, break down very large updates into smaller batches (e.g., update one category at a time instead of all categories).

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters working with the “Mass quantity update pro” module.

### 4.1 Architecture Overview

The `MassQtyPro` module follows a standard PrestaShop module architecture, primarily leveraging the `Module` class for its core functionality and `getContent()` method for its single back-office configuration interface. It integrates a custom search tool for product selection, utilizing AJAX for autocomplete functionality. The module directly interacts with PrestaShop’s `Product` and `StockAvailable` classes to perform quantity updates.

### 4.2 Controllers (`controllers/`)

The module does not utilize custom front-office or back-office controllers. All configuration and processing logic for the back-office is handled within the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)

The module does not define any custom `ObjectModel` classes or dedicated classes within a `classes/` directory. All core logic resides within the main `massqtypro.php` file.

### 4.4 JavaScript Assets (`views/js/`)

- **`massqtypro/lib/searchTool/views/js/autocomplete.js`**
  - **Scope:** Back-office (used on the module configuration page).
  - **Description:** This script likely implements or integrates a generic autocomplete functionality. It listens for user input in text fields (specifically for product search) and sends AJAX requests to fetch matching product names. It then displays these suggestions in a dropdown list, allowing the user to select products. It manages the display and selection of autocomplete results.
- **`massqtypro/views/js/jquery.autocomplete.js`**
  - **Scope:** Back-office (used on the module configuration page).
  - **Description:** This appears to be a jQuery plugin for autocomplete functionality. It provides the core framework for the product search box on the module’s configuration page. It handles the AJAX calls to the server (likely to the `getContent()` method or a specific hook that provides product data), processes the JSON response, and renders the suggestions. It also manages the selection of an item from the list and populating the input field or a hidden field with the selected product’s ID.

### 4.5 CSS Stylesheets (`views/css/`)

- **`massqtypro/lib/searchTool/views/css/autocomplete.css`**
  - **Scope:** Back-office (styling for the module configuration page).
  - **Description:** This stylesheet provides the visual presentation for the autocomplete search box and its suggestion list. It defines styles for the input field, the dropdown container, individual suggestion items, and potentially hover/active states for better user interaction. Developers can override these styles in their custom admin theme or by adding specific CSS rules to target the module’s elements.

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses Smarty templates for rendering its back-office configuration form.

- **`massqtypro/lib/searchTool/views/scripts.tpl`**
  - **Scope:** Back-office (included in the module configuration page).
  - **Description:** This template likely includes the necessary JavaScript and CSS files for the autocomplete search tool. It might also contain inline JavaScript for initializing the autocomplete plugin on specific input fields, passing configuration options, and defining callback functions for when a product is selected.
- **`massqtypro/views/templates/admin/target_products.tpl`**
  - **Scope:** Back-office (part of the module configuration form).
  - **Description:** This template renders the “Target Products” section of the module’s configuration page. It contains the HTML for all the product selection criteria: category dropdowns, brand dropdowns, feature/attribute selectors, tax rule selectors, and the specific product autocomplete input field. It uses standard PrestaShop form helpers and potentially custom HTML for the dynamic selection elements.
- **`massqtypro/views/templates/admin/wtd.tpl`**
  - **Scope:** Back-office (part of the module configuration form).
  - **Description:** This template renders the “What to do?” section of the module’s configuration page. It contains the HTML for the quantity update operations: radio buttons for “Increase,” “Decrease,” or “Set to,” and the corresponding input field for the quantity value. It also includes the “Update quantities” submission button.
- **`massqtypro/views/templates/hook/form.tpl`**
  - **Scope:** Back-office (main configuration form).
  - **Description:** This is the main template for the module’s configuration page. It likely wraps the `target_products.tpl` and `wtd.tpl` templates, combining them into the complete configuration form. It would also handle the overall form submission and display any success or error messages.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: The module does not create any custom database tables. It primarily interacts with existing PrestaShop tables, notably `ps_product`, `ps_product_attribute`, `ps_stock_available`, `ps_category_product`, `ps_manufacturer`, `ps_feature_product`, `ps_product_attribute_combination`, and `ps_tax_rule_group_product`. Configuration settings are stored in `ps_configuration`.
- **Registered Hooks Table**:
  The module’s primary functionality is executed via its `getContent()` method in the back-office. It does not explicitly register to front-office hooks for display purposes. However, the module might internally use hooks for administrative actions or data retrieval.

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `displayBackOfficeHeader` | Renders in the `<head>` section of the Back Office. | Potentially used to load module-specific CSS/JS for the configuration page, though often handled directly in `getContent()`. |
  | `actionProductUpdate` | After a product is updated. | Could be used for internal logging or to trigger related actions, though not explicitly stated in features. |
  | `actionUpdateQuantity` | After a product’s quantity is updated. | Could be used for internal logging or to trigger related actions, though not explicitly stated in features. |

  The module’s core logic for quantity updates directly manipulates `StockAvailable` entries, which internally triggers PrestaShop’s stock update mechanisms.

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official technical support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist merchants and developers with any issues or questions related to the “Mass quantity update pro” module.
