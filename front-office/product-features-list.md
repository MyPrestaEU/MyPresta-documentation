---
title: "Product features list - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Product features list PrestaShop module by MyPresta.eu."
sidebar:
  label: "Product features list - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Product features list Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-features-list.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/product-features-list/)
>
> ---


# Product features list

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Product features list)

This is the main configuration screen for the module, accessed immediately after installation or by clicking “Configure” from the Module Manager.

- **What this setting does:** This setting controls where the list of product features will appear visually on your product listing pages (category pages, search results, etc.).
- **Effect of changing this setting:**
  - *When set to “displayProductListReviews”:* The features will appear near the product reviews section on the product list. This is often a good spot to group social proof with key product attributes.
  - *When set to “displayProductDeliveryTime”:* The features will appear near any displayed delivery time information. This can be useful for products where features are closely tied to logistics or availability.
  - *When set to “displayHeader”:* This option is less common for visual display on product lists and might place the features in the page header, which is generally not where you’d want product-specific features to appear. It’s primarily a technical hook.
- **Recommended value:** “displayProductListReviews” or “displayProductDeliveryTime”. Choose the one that best integrates with your theme’s layout and where you feel the features will be most visible without clutter.
- **Merchant scenario / example:** If your theme shows star ratings and review counts prominently, “displayProductListReviews” would place the features right next to them, creating a rich information block. If your products often have specific delivery details (e.g., “Ships in 24h”), placing features with “displayProductDeliveryTime” might make sense.

### 2.2 Dedicated Admin Screen: Feature Association (Back Office > Modules > Product features list > Configure > “Manage Feature Associations” or similar link)

This screen is crucial for defining *which* features appear for *which* products and categories. It’s where you associate specific product features with categories.

- **Screen Name & Menu Location:** After configuring the main module, you’ll typically find a link or button on the module’s configuration page (or a new menu item under “Catalog”) that leads to “Manage Feature Associations” or “Product Features List.” The exact path might vary slightly depending on your PrestaShop version, but it will be linked from the module’s main configuration.
- **Available Actions & Settings:**
  - **Grid/Management View:** You’ll see a table listing your existing product features (these are the standard features you define under **Catalog > Attributes & Features > Features**).
  - **Edit/Associate Button:** For each feature, there will be an “Edit” or “Associate” button. Clicking this will open a form where you can:
    - **Select Categories:** Choose one or more categories for which this specific feature should be displayed on product lists. For example, if you have a “Material” feature, you might associate it with “T-Shirts,” “Dresses,” and “Jackets” categories.
    - **Enable/Disable:** You might have an option to enable or disable the display of this feature on product lists globally or per category.
- **Effect of changes:**
  - *When you associate a feature with a category:* Products within that category that possess this feature will display it on their product list entry.
  - *When you remove an association:* The feature will no longer appear for products in that category on product lists.
- **Recommended workflow for daily store management:**
  1. First, ensure all your product features are correctly set up under **Catalog > Attributes & Features > Features**.
  2. Navigate to the “Manage Feature Associations” screen of the “Product features list” module.
  3. Go through each relevant feature.
  4. For each feature, select the categories where you want this feature to be visible on product listing pages.
  5. Save your changes.
  6. Periodically review these associations, especially when adding new products, categories, or features, to ensure your product lists remain informative.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Position of tags (fplist\_position) | displayProductListReviews | Determines where features appear on product list pages (e.g., near reviews, near delivery time). |
| Feature Association | Feature Name (e.g., “Material”) | N/A | Standard PrestaShop feature to be managed. |
| Feature Association | Associated Categories | N/A | Select categories where this feature should be visible on product lists. |
| Feature Association | Enable/Disable Feature | Enabled | Controls whether a feature is actively displayed for its associated categories. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve configured the module, but the features aren’t showing on my category pages.**
A:

1. **Check Feature Associations:** Go to the “Manage Feature Associations” screen and ensure that the features you expect to see are actually associated with the categories you are viewing.
2. **Clear Cache:** PrestaShop uses caching. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” if available).
3. **Module Position:** Double-check the “Position of tags” setting in the module’s main configuration. Ensure it’s set to a hook that your theme actually renders in the product list context (e.g., `displayProductListReviews` or `displayProductDeliveryTime`). Some custom themes might not explicitly call all standard hooks.
4. **Product Data:** Verify that the products in question actually *have* values for the features you’re trying to display (e.g., if you want to show “Material,” make sure the product has a material assigned).

**Q: The features are showing, but they look messy or don’t fit my theme’s design.**
A:

1. **CSS Conflict:** This is likely a styling conflict with your theme. The module includes its own CSS (`fplist/views/css/fplist.css`), but your theme’s styles might be overriding it or causing layout issues.
2. **Custom Theme:** If you’re using a highly customized theme, you might need a webmaster or developer to adjust the module’s CSS or your theme’s CSS to ensure proper integration.
3. **Positioning:** Try changing the “Position of tags” setting to see if a different hook integrates better visually with your theme.

**Q: Can I display different features for different categories?**
A: Yes, absolutely! This is one of the core strengths of the module. Use the “Manage Feature Associations” screen to select specific categories for each feature. This allows you to tailor the displayed information precisely to the context of the product list.

**Q: Does this module affect my product pages?**
A: No, this module specifically targets product *listing* pages (category, search results, etc.). It does not alter how features are displayed on individual product detail pages.

**Q: My store is multi-language. Are the feature names translated?**
A: Yes, PrestaShop’s standard features (which this module uses) are fully translatable. Ensure that you have provided translations for your feature names and values under **Catalog > Attributes & Features > Features** for all active languages in your store. The module will then display the correct translation on the front office.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Product features list” module (`fplist`) follows a standard PrestaShop module architecture, primarily extending `Module` for its core functionality and `AdminController` for its Back Office management interface. It leverages PrestaShop’s hook system to inject content into product listing pages and uses an `ObjectModel` (implicitly via `AdminFplistAssociationController`) to manage the association between features and categories. The module’s front-office display is handled by a Smarty template rendered via a hook.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: This module does not contain dedicated front-office controllers. All front-office display logic is handled directly within the main module file (`fplist.php`) through registered hooks.
- **Back-Office Admin Controllers**:

  - `fplist/controllers/admin/AdminFplistAssociation.php`
    - **Class Name:** `AdminFplistAssociationController` (extends `ModuleAdminController`)
    - **Responsibility:** This controller manages the association between PrestaShop features and categories. It provides the Back Office interface (a list and potentially an edit form) for administrators to select which features should be displayed on product lists for specific categories. It interacts with the module’s internal data storage (likely `ps_fplist_association` table, though no explicit `ObjectModel` is provided in the dossier, the controller implies its existence and management).
  - `fplist/controllers/admin/index.php`
    - **Class Name:** N/A (this is typically an empty file or a redirect to prevent direct directory access, not a functional controller).
    - **Responsibility:** Standard PrestaShop security measure to prevent directory listing.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes in the `classes/` directory. The `AdminFplistAssociationController` implies the existence of a data model for feature-category associations, which is likely handled directly within the controller or the main module file using `Db::getInstance()` queries, rather than a dedicated `ObjectModel`. If an `ObjectModel` were present, it would typically be named `FplistAssociation` or similar.

### 4.4 JavaScript Assets (`views/js/`)

The module dossier indicates no custom JavaScript files. Any dynamic behavior or AJAX interactions would need to be implemented directly within the module’s PHP or template files, or rely on PrestaShop’s core JS.

### 4.5 CSS Stylesheets (`views/css/`)

- `fplist/views/css/fplist.css`
  - **Scope:** Front-office customer styling.
  - **Main UI components and containers it styles:** This stylesheet is responsible for the visual presentation of the product features list on category and listing pages. It defines styles for the container holding the features, individual feature items, and potentially icons or labels associated with them.
  - **Key CSS class selectors developers can override:** Developers should inspect the rendered HTML to identify specific classes (e.g., `.fplist-container`, `.fplist-item`, `.fplist-feature-name`, `.fplist-feature-value`) to override in their theme’s `custom.css` or `theme.css` for seamless integration.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `fplist/views/templates/fplist-front.tpl`
    - **Hook:** This template is rendered within the `displayProductListReviews` and `displayProductDeliveryTime` hooks (as configured by `fplist_position`).
    - **Output:** It outputs the HTML structure for the list of features for a single product on a product listing page. It iterates through the features retrieved by the module for the current product and category, displaying their names and values.
  - `fplist/views/templates/fplist.tpl`
    - **Hook:** This template is likely used for the module’s main configuration page in the Back Office (via `getContent()`).
    - **Output:** It renders the form for the “Position of tags” setting and potentially links to the `AdminFplistAssociationController` for managing feature associations.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - `ps_fplist_association` (implied): This table is not explicitly defined in the dossier but is necessary for the `AdminFplistAssociationController` to store the many-to-many relationship between PrestaShop features and categories. It would typically contain columns like `id_feature`, `id_category`, and potentially `id_shop`.
  - Configuration records in `ps_configuration`:
    - `mypresta_updates`: Stores update information for MyPresta.eu modules.
    - `update_`: Related to module update checks.
    - `updatev_`: Related to module update checks.
    - `fplist_position`: Stores the selected hook name for displaying features (e.g., `displayProductListReviews`).
    - `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Standard PrestaShop configuration for employee form language.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Primarily used for loading CSS/JS assets or meta tags. The module uses it as a configurable position for features, though less common for visual display. |
| `displayProductListReviews` | Within the product list item, typically near product reviews. | Injects the feature list HTML into each product entry on category/search pages. |
| `displayProductDeliveryTime` | Within the product list item, typically near delivery time information. | Injects the feature list HTML into each product entry on category/search pages. |
| `actionValidateOrder` | After an order has been successfully validated. | (Not explicitly used by this module, but a common hook for order-related actions). |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and professional support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist you with any issues or questions regarding the “Product features list” module.
