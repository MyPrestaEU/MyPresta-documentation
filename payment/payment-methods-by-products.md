---
title: "Payment methods by products - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Payment methods by products PrestaShop module by MyPresta.eu."
sidebar:
  label: "Payment methods by products - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Payment methods by products Module on MyPresta.eu](https://mypresta.eu/modules/payment-process/payment-methods-by-products.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/payment/payment-methods-by-products/)
>
> ---


# Payment methods by products

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required by PrestaShop itself and are sufficient for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

This module has two main configuration areas: the initial module configuration page and a dedicated management screen for creating product-payment associations.

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Payment methods by products)

Upon clicking “Configure” after installation, you will land on the module’s main configuration page. This page typically contains general settings for the module.

**Currently, there are no specific settings detected on this main configuration page beyond the standard module information. The core functionality is managed through the dedicated “Payment - Product associations” screen.**

If future versions introduce settings here, they would appear as switches, input fields, or dropdowns. For now, you can proceed directly to the dedicated management screen.

### 2.2 Dedicated Admin Screen: Payment - Product associations (Back Office > Modules > Payment methods by products > Payment - Product associations)

This is the central hub for managing your product-payment restrictions. You’ll find this screen by navigating to **Modules > Module Manager**, finding “Payment methods by products”, clicking “Configure”, and then looking for a tab or link labeled “Payment - Product associations” (or similar, depending on the module’s navigation).

**Screen Name & Menu Location:**

- **Menu Path:** Back Office > Modules > Module Manager > Payment methods by products > Configure > **Payment - Product associations** (or a similar tab/link on the configuration page).
- This screen allows you to view, add, edit, and delete associations between products and payment methods.

**Available Actions & Settings:**

#### 2.2.1 The “Payment - Product associations” List View

This view presents a table of all existing product-payment restrictions you have set up.

| Column Name | Purpose & Impact |
| --- | --- |
| **ID** | A unique identifier for each association. |
| **Product** | The name of the product involved in the restriction. |
| **Payment** | The name of the payment method that is restricted or allowed for this product. |
| **Country** | (If applicable) The country for which this restriction applies. If left empty, it applies globally. |
| **Actions** | Icons to **Edit** (pencil icon) or **Delete** (trash can icon) an existing association. |

**Recommended workflow for daily store management:**

- **Review existing rules:** Regularly check this list to ensure your restrictions are up-to-date with your product catalog and business needs.
- **Identify conflicts:** Look for any overlapping or conflicting rules, especially if you have many products and payment methods.
- **Use search/filter:** If the list grows large, use any available search or filter options to quickly find specific product or payment restrictions.

#### 2.2.2 Adding or Editing a “Payment - Product association”

To add a new restriction, you’ll typically find an “Add new” button on the list view. When editing, you click the pencil icon next to an existing entry. This will open a form with the following fields:

| Form Field | What this setting does | Effect of changing this setting | Recommended value | Merchant scenario / example |
| --- | --- | --- | --- | --- |
| **ID Product** | This field allows you to select the specific product you want to associate with payment restrictions. | When you select a product, the module will apply the chosen payment restrictions whenever this product is in a customer’s cart. | Select the exact product from your catalog. Use the search functionality if you have many products. | You sell “Digital Ebook: Marketing Guide”. You want to ensure it’s only paid via PayPal or Credit Card, not Cash on Delivery. You select this product here. |
| **Payment methods** | This is a list of all active payment methods in your PrestaShop store. You select which payment methods are **allowed** for the chosen product. | - *When you select one or more payment methods:* Only these selected methods will be available at checkout if the associated product is in the cart. All other payment methods will be hidden.   - *When you select NO payment methods:* This effectively means the product cannot be purchased, or it will inherit rules from other products in the cart. It’s generally not recommended to leave this empty unless you have a very specific use case. | Select all payment methods that are acceptable for the chosen product. | For “Digital Ebook: Marketing Guide”, you check “PayPal” and “Credit Card”. If a customer buys this ebook, only these two options will appear at checkout. |
| **Country** | (Optional) This field allows you to specify a country for which this particular product-payment restriction applies. | - *When a country is selected:* The restriction (product + allowed payments) will only apply if the customer’s shipping address is in the selected country.   - *When left empty:* The restriction applies globally, regardless of the customer’s country. | Leave empty for global application, or select a specific country if the restriction is geographically limited. | You sell “Fragile Glass Sculpture” which can only be paid via “Bank Transfer” in France due to shipping insurance requirements. You select the sculpture, “Bank Transfer”, and “France”. For customers outside France, other payment methods might still be available for this product (if no other global rules apply). |
| **Save** | This button saves your new or updated product-payment association. | The changes are immediately applied to your store’s checkout process. | Always click “Save” after making any changes. | After setting up the rules for your “Digital Ebook”, you click “Save” to activate them. |

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | (No specific settings detected) | N/A | General module information. |
| Payment - Product associations (List) | ID | N/A | Unique identifier for the association. |
| Payment - Product associations (List) | Product | N/A | Name of the product in the association. |
| Payment - Product associations (List) | Payment | N/A | Name of the payment method in the association. |
| Payment - Product associations (List) | Country | N/A | Country for which the restriction applies (if any). |
| Payment - Product associations (Add/Edit Form) | ID Product | Select a product | Specifies the product for which payment methods will be restricted. |
| Payment - Product associations (Add/Edit Form) | Payment methods | Select all acceptable methods | Defines which payment methods are **allowed** for the selected product. |
| Payment - Product associations (Add/Edit Form) | Country | Leave empty for global, or select specific | Limits the restriction to a specific country. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve set up a restriction, but all payment methods are still showing at checkout. What’s wrong?**
A:

1. **Cache:** Always clear your PrestaShop cache after making changes. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions).
2. **Product in Cart:** Ensure the specific product you’ve restricted is actually in the customer’s shopping cart when testing. The module only applies rules if the product is present.
3. **Payment Method Enabled:** Double-check that the payment methods you *expect* to see are actually enabled in **Modules > Payment > Payment Methods**. This module filters *enabled* methods, it doesn’t enable them itself.
4. **Conflicting Rules:** If you have multiple products in the cart, and each has restrictions, the module will only show payment methods that are allowed by *all* restricted products. If there’s no common allowed method, it might appear as if no methods are showing. Review your associations carefully.

**Q: I’ve set up a restriction, and now NO payment methods are showing at checkout!**
A: This usually happens if:

1. **No Common Methods:** You have multiple restricted products in the cart, and there are no payment methods that are allowed by *all* of them. For example, Product A allows PayPal, Product B allows Credit Card. If both are in the cart, neither will show. You need to ensure there’s at least one common allowed method.
2. **Empty Allowed List:** You created an association for a product but didn’t select *any* payment methods as allowed. The module will then hide all methods for that product. Edit the association and select the appropriate payment methods.

**Q: Does this module affect payment methods for products that are NOT in any association?**
A: No. If a product is not part of any “Payment - Product association,” it does not impose any restrictions. The module only acts on products for which you have explicitly defined rules. If a cart contains only unrestricted products, all your store’s standard enabled payment methods will be displayed.

**Q: How does this module interact with other payment restriction modules (e.g., by customer group, by total amount)?**
A: This module typically works by overriding PrestaShop’s core `PaymentOptionsFinder` class (as seen in the `override` folder). This means it takes precedence or integrates at a fundamental level. Generally, the most restrictive rule will apply. If another module restricts a payment method, and this module allows it for a product, the payment method will likely still be restricted by the other module. It’s crucial to test thoroughly if you use multiple restriction modules.

**Q: Can I restrict payment methods based on country without restricting by product?**
A: This module’s primary function is product-based restriction. While it has a “Country” field, it applies *to the product-payment association*. If you need purely country-based payment restrictions (regardless of product), you might need a separate module designed for that, or check if your payment gateways offer country restrictions directly.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a technical deep dive into the “Payment methods by products” module for developers and webmasters.

### 4.1 Architecture Overview

The module primarily extends PrestaShop’s core payment option discovery mechanism. It leverages an `override` to modify the `PaymentOptionsFinder` class, which is responsible for determining available payment methods during checkout. This allows the module to inject its product-based filtering logic directly into the payment option retrieval process, ensuring seamless integration with PrestaShop’s checkout flow.
The module follows a standard PrestaShop MVC pattern for its Back Office management, using an AdminController to manage the `pobp` entity (Product-Payment Association).

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. The module’s front-office functionality is handled via an override of a core class, not a dedicated front controller.
- **Back-Office Admin Controllers**:

  - `pobp/controllers/admin/AdminPobpController.php`
    - **Class Name & Parent Class**: `AdminPobpController` extends `ModuleAdminController`.
    - **Tab Name**: This controller manages the “Payment - Product associations” entity. It’s likely registered as a sub-tab under the module’s main configuration.
    - **Responsibility**: This is the main CRUD (Create, Read, Update, Delete) controller for the product-payment associations. It handles:
      - Displaying the list of existing associations (ID, Product, Payment, Country).
      - Providing the form for adding new associations or editing existing ones.
      - Processing form submissions to save new or updated associations to the database.
      - Handling deletion of associations.
      - The form fields “ID Product”, “Payment methods”, and “Country” are managed here.
  - `pobp/controllers/admin/index.php`
    - This file is typically an empty placeholder or contains basic security measures (e.g., `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../"); exit;`). It does not represent a functional controller view itself but ensures direct access to the `controllers/admin` directory is redirected.

### 4.3 Core Classes & Models (`classes/`)

- `pobp/override/classes/checkout/PaymentOptionsFinder.php`
  - **Purpose**: This is a critical override file. It modifies the core PrestaShop class responsible for finding and returning available payment options during checkout.
  - **Class Name & Parent Class**: `PaymentOptionsFinder` (overrides the original `PaymentOptionsFinder` class).
  - **Key Logic**: The overridden `getPaymentOptions()` method (or a similar method) will contain the module’s core logic.
    - It retrieves the products currently in the customer’s cart.
    - For each product, it checks if there are any defined “Payment - Product associations” in the module’s database.
    - It then filters the initially available payment options (returned by the parent `getPaymentOptions()` method) based on these associations.
    - The filtering logic ensures that only payment methods explicitly allowed for *all* restricted products in the cart are returned. If a product has no association, it doesn’t restrict anything. If multiple products have associations, the intersection of allowed payment methods is used.
  - **Database Interaction**: This class will query the module’s custom database table (likely `ps_pobp` or similar) to fetch the product-payment associations.

### 4.4 JavaScript Assets (`views/js/`)

No specific JavaScript files were detected in the provided inventory. Any dynamic behavior in the Back Office (like product search in the association form) is likely handled by PrestaShop’s core JS or a minimal inline script.

### 4.5 CSS Stylesheets (`views/css/`)

No specific CSS files were detected in the provided inventory. Styling for the Back Office forms and lists is likely inherited from PrestaShop’s default admin theme.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**: None explicitly listed, as the module operates via an override rather than direct hook rendering in the front office.
- **Admin templates (`views/templates/admin/`)**:
  - `pobp/lib/searchTool/views/scripts.tpl`
    - **Purpose**: This template likely contains JavaScript or Smarty logic related to a search tool used within the Back Office, possibly for searching products when creating or editing an association. It might include AJAX calls or dynamic filtering for product selection.
- **Front-office templates (`views/templates/front/`)**: None.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module will create at least one custom table during its `install()` method (defined in `pobp/index.php`).
  - **`ps_pobp` (or similar name, e.g., `ps_payment_by_product_association`)**:
    - This table stores the actual product-payment associations.
    - Expected columns:
      - `id_pobp` (Primary Key, INT)
      - `id_product` (INT, foreign key to `ps_product`)
      - `id_payment_module` (INT, foreign key to `ps_module` or `ps_payment_module` if such a table exists, or simply stores the module’s name/ID)
      - `id_country` (INT, foreign key to `ps_country`, nullable for global rules)
      - Other potential columns for settings or timestamps.
  - Configuration values (if any were present in `getContent()`) would be stored in `ps_configuration`.
- **Registered Hooks Table**:
  The module’s core functionality relies on the `override` mechanism rather than direct hook execution for its primary filtering. However, for its Back Office integration and potentially for future features, it might register standard hooks.

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `displayAdminProductsExtra` | On the product edit page in the Back Office. | Could be used to display a quick link or a summary of payment restrictions for the current product. (Not explicitly detected but a common integration point). |
  | `actionPaymentOptionsModifier` | During the payment options retrieval process. | This hook is specifically designed for modules to modify the list of payment options. The override of `PaymentOptionsFinder` effectively achieves a similar result at a lower level. |
  | `actionModuleInstall` | When the module is installed. | To create database tables and register necessary hooks. |
  | `actionModuleUninstall` | When the module is uninstalled. | To clean up database tables and unregister hooks. |

## 5. Official Support & Updates

For official updates, technical support, and to ensure you have the latest compatible version of the “Payment methods by products” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions regarding the module’s functionality and integration.
