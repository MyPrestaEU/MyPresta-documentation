---
title: "Disable group discount for specific products - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Disable group discount for specific products PrestaShop module by MyPresta.eu."
sidebar:
  label: "Disable group discount for specific products - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Disable group discount for specific products Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-group-discount-for-specific-products.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/disable-group-discount-for-specific-products/)
>
> ---


# Disable group discount for specific products

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main and only configuration screen for the “Disable group discount for specific products” module. You will find all settings here to control which products are excluded from group discounts.

**Menu Location:** Back Office > Modules > Module Manager > “Disable group discount for specific products” > Configure

#### 2.1.1 “Disable groups discount for specific products” Section

This section contains the core settings for enabling or disabling the module’s functionality and defining which products are affected.

- **Setting: Enabled / Disabled Switch**

  - **What this setting does:** This is the master switch for the module. It determines whether the module’s logic for disabling group discounts is active or inactive.
  - **Effect of changing this setting:**
    - *When Enabled:* The module will actively check if a product or its category is listed in your exclusion rules. If so, any group discounts will be ignored for that product.
    - *When Disabled:* The module will not interfere with PrestaShop’s default group discount calculations. All products will be subject to group discounts if applicable.
  - **Recommended value:** “Enabled” if you intend to use the module’s functionality.
  - **Merchant scenario / example:** If you’re setting up the module for the first time or performing maintenance, you’d enable it. If you temporarily want all group discounts to apply without uninstalling the module, you’d disable it.
- **Setting: Categories (Selection Box)**

  - **What this setting does:** This allows you to select entire product categories whose products should be excluded from group discounts. Any product belonging to a selected category will not receive group discounts.
  - **Effect of changing this setting:**
    - *When categories are selected:* All products within the chosen categories (and their subcategories, depending on PrestaShop’s category structure and how products are assigned) will have group discounts disabled.
    - *When no categories are selected:* Products are not excluded based on their category.
  - **Recommended value:** Select the categories that contain products you want to exclude from group discounts.
  - **Merchant scenario / example:** You sell electronics. Your “New Arrivals” category often contains high-demand items. You want to ensure that even your wholesale customers pay full price for these new products for the first month. You would select the “New Arrivals” category here.
- **Setting: Specific products (Search and Selection Input)**

  - **What this setting does:** This allows you to search for and select individual products that should be excluded from group discounts. This provides a more granular control than categories.
  - **Effect of changing this setting:**
    - *When specific products are selected:* Only the explicitly chosen products will have group discounts disabled, regardless of their category.
    - *When no specific products are selected:* Products are not excluded based on individual selection.
  - **Recommended value:** Select specific products you want to exclude from group discounts.
  - **Merchant scenario / example:** You have a limited edition art print (Product ID 123) and a special bundle offer (Product ID 456) that you never want to discount for any customer group. You would search for and add “Art Print (Limited Edition)” and “Special Bundle Offer” to this list.

#### 2.1.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enabled / Disabled | Enabled | Master switch to activate/deactivate the module’s functionality. |
| Module Configuration | Categories | Select relevant categories | Exclude all products within selected categories from group discounts. |
| Module Configuration | Specific products | Select relevant products | Exclude individually selected products from group discounts. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve configured the module, but group discounts are still applying to my excluded products. What’s wrong?**
A:

- **Is the module enabled?** Double-check the “Enabled / Disabled” switch on the module’s configuration page. It must be set to “Enabled.”
- **Did you save your changes?** Always click the “Save” button after making any changes to the configuration.
- **Clear your PrestaShop cache:** Sometimes, PrestaShop’s cache can prevent changes from appearing immediately. Go to **Advanced Parameters > Performance**, and click “Clear cache” (or “Clear Smarty cache” in older versions).
- **Check product/category assignment:** Ensure the product is correctly assigned to the category you’ve excluded, or that you’ve selected the exact product you intend to exclude.
- **Check for other modules:** Another pricing or discount module might be conflicting. Try disabling other discount-related modules temporarily to see if the issue resolves.

**Q2: Will this module affect my regular catalog price rules or specific prices?**
A: No, this module specifically targets *group discounts*. It does not interfere with catalog price rules, specific prices you set for individual products, or cart rules (vouchers). It only prevents the additional percentage discount applied based on a customer’s group.

**Q3: How does this module handle products in multiple categories?**
A: If a product is in multiple categories, and *any* of those categories are selected for exclusion in the module, the product will be excluded from group discounts. The module checks if the product *belongs* to an excluded category.

**Q4: I’m using a custom theme. Will this module work correctly?**
A: Yes, this module works at the core pricing calculation level and doesn’t introduce any new front-office elements or complex styling that would typically conflict with themes. It should be fully compatible with any PrestaShop theme.

**Q5: Can I exclude products for *some* groups but not others?**
A: No, this module disables group discounts for the selected products/categories *for all customer groups*. If a product is on the exclusion list, no customer group will receive a discount on it. PrestaShop’s core functionality allows you to set group discounts per group, but this module acts as an override for specific products, making them exempt from *any* group discount.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters looking to understand, debug, or extend the “Disable group discount for specific products” module.

### 4.1 Architecture Overview

The module primarily functions by overriding a core PrestaShop class (`Product.php`) to modify the price calculation logic. It hooks into the `Product::getPriceStatic()` method, which is central to how PrestaShop determines a product’s final price. When this method is called, the module checks if the current product or its associated categories are configured for exclusion from group discounts. If they are, it ensures that the group discount component of the price calculation is bypassed.

The module uses PrestaShop’s standard `Module` class for its configuration interface and relies on `Configuration` table entries to store its settings. It also includes a simple search tool for product selection in the back office.

### 4.2 Controllers (`controllers/`)

This module does not introduce any custom front-office or back-office controllers. Its logic is primarily implemented through a class override and the main module file’s `getContent()` method for configuration.

### 4.3 Core Classes & Models (`classes/`)

- **`exgdisc/override/classes/Product.php`**
  - **Responsibility:** This is the most critical file in the module. It overrides the core `Product` class to modify the `getPriceStatic()` method.
  - **Class Name:** `Product` (overrides the original `Product` class)
  - **Parent Class:** `ProductCore`
  - **Key Logic:**
    - The overridden `getPriceStatic()` method first calls the parent’s `getPriceStatic()` to get the base price.
    - It then retrieves the module’s configuration (`exgdisc_categories`, `exgdisc_products`) from `Configuration::get()`.
    - It checks if the current product’s ID (`$id_product`) is in the `exgdisc_products` list.
    - It also checks if any of the categories associated with `$id_product` are in the `exgdisc_categories` list.
    - If either condition is true, it means the product should be excluded from group discounts. The method then recalculates the price, effectively ignoring the group discount component that would normally be applied by the parent `getPriceStatic()` method.
    - The original `Product::getPriceStatic()` method has a `$use_group_reduction` parameter. The override ensures that even if this is `true`, the group reduction is not applied if the product is excluded by the module.

### 4.4 JavaScript Assets (`views/js/`)

- **`exgdisc/lib/searchTool/views/js/autocomplete.js`**
  - **Scope:** Back-office (used on the module configuration page).
  - **Purpose:** Provides the autocomplete functionality for selecting specific products in the module’s configuration form.
  - **Key Logic:**
    - Initializes an autocomplete input field (likely targeting an element with a specific ID, e.g., `#product_autocomplete_input`).
    - Sends AJAX requests to a PrestaShop admin controller (e.g., `AdminProducts` or a custom search controller) to fetch product suggestions based on user input.
    - Handles the selection of products, adding them to a hidden input field or a visual list on the configuration page.
    - Manages the removal of selected products from the list.

### 4.5 CSS Stylesheets (`views/css/`)

- **`exgdisc/lib/searchTool/views/css/autocomplete.css`**
  - **Scope:** Back-office (styles the autocomplete search tool).
  - **Purpose:** Provides styling for the product search input and the list of selected products on the module’s configuration page.
  - **Key Selectors:** Likely includes styles for the autocomplete dropdown, selected item tags/badges, and possibly the search input field itself. Developers can override these classes in their custom admin themes if needed.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`exgdisc/lib/searchTool/views/scripts.tpl`**

  - **Scope:** Back-office (included in the module configuration page).
  - **Purpose:** Renders the HTML structure for the product search input and the area where selected products are displayed. It also likely includes the necessary JavaScript calls to initialize the `autocomplete.js` script.
  - **Key Elements:** Input field for searching products, a container for displaying selected products (e.g., as tags or list items), and hidden input fields to store the IDs of selected products.
- **`exgdisc/views/script.tpl`**

  - **Scope:** Back-office (included in the module configuration page).
  - **Purpose:** This template is likely used to output additional JavaScript or CSS that is specific to the main module configuration form, potentially related to form validation or dynamic UI elements. Given the `ActionAdminControllerSetMedia` hook, it might be used to register assets.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any custom database tables.
  - All configuration settings are stored in the `ps_configuration` table:
    - `exgdisc_categories`: Stores a serialized string or comma-separated list of category IDs to exclude.
    - `exgdisc_products`: Stores a serialized string or comma-separated list of product IDs to exclude.
    - `mypresta_updates`, `update_`, `updatev_`: Related to MyPresta.eu’s update mechanism.
    - `exgdisc_groups`: (Not explicitly used in the provided info, but could be a legacy or future setting for group-specific exclusions).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Executed when an admin controller is loaded and its media (JS/CSS) are being set. | Used by the module to load its back-office JavaScript (`autocomplete.js`) and CSS (`autocomplete.css`) for the configuration page, ensuring the product search tool works. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the “Disable group discount for specific products” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to ensuring the module functions optimally with your PrestaShop store.
