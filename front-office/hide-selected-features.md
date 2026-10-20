---
title: "Hide selected features - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Hide selected features PrestaShop module by MyPresta.eu."
sidebar:
  label: "Hide selected features - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Hide selected features Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/hide-selected-features.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/hide-selected-features/)
>
> ---


# Hide selected features

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

You can access this page by navigating to **Modules > Module Manager** and searching for “Hide selected features”, then clicking “Configure”.

This screen presents a list of all product features currently defined in your PrestaShop store. For each feature, you will see a toggle switch to control its visibility.

- **What this setting does:** This section lists all your existing product features (e.g., “Material”, “Color”, “Weight”, “Dimensions”). Next to each feature, there’s a switch that controls whether that specific feature will be displayed on your product pages in the front office.
- **Effect of changing this setting:**
  - *When enabled (switch is ON):* The feature will be visible to customers on all product pages where it is assigned. This is the default PrestaShop behavior.
  - *When disabled (switch is OFF):* The feature will be hidden from customers on all product pages, even if it’s assigned to a product. It will still exist in your back office for internal use or filtering.
- **Recommended value:** This depends entirely on your business needs.
  - **Enable** features that are crucial for customer decision-making (e.g., “Material” for clothing, “Capacity” for electronics).
  - **Disable** features that are internal notes, technical specifications irrelevant to the average customer, or redundant information.
- **Merchant scenario / example:**
  - **Scenario 1 (Hiding internal notes):** You use a feature called “Supplier SKU” to track internal product codes. This information is not useful for customers. You would **disable** the “Supplier SKU” feature here to keep your product pages clean.
  - **Scenario 2 (Simplifying display):** You sell t-shirts and have features like “Material: Cotton”, “Sleeve Length: Short”, “Neckline: Crew”. You decide that “Sleeve Length” and “Neckline” are usually clear from the product image and you want to emphasize “Material”. You would **disable** “Sleeve Length” and “Neckline” and **enable** “Material”.

**Other Configuration Keys (Internal/Advanced):**
You might see some other configuration keys like `mypresta_updates`, `update_`, `updatev_`, `hidefeatures_OSTATE`, `PS_OS_PREPARATION`, `hidefeatures_MIN_CHARGE`. These are typically internal module settings related to updates, order states, or minimum charges, and are not directly configurable by the merchant through the main interface. They are usually managed automatically by the module or used for specific, advanced scenarios not exposed in the primary UI. For this module, the core functionality is managed by the feature toggles.

### 2.2 Dedicated Admin Screens & Controller Views

#### 2.2.1 AdminFeaturesController (Back Office > Catalog > Attributes & Features > Features)

This module overrides the standard PrestaShop “Features” management screen.

- **Screen Name & Menu Location:** **Back Office > Catalog > Attributes & Features > Features**.
- **Available Actions & Settings:** When you go to this screen, you’ll see a list of all your product features. The module adds a new column or indicator to this list, typically labeled **“Active in front office”** or similar. This column will show you at a glance whether a feature is currently set to be visible or hidden on your store’s front end, based on the settings you made in the module’s main configuration page.
- **Effect of changes:** While you can’t directly change the visibility from this screen (you do that on the module’s configuration page), this screen provides a convenient overview. It helps you quickly verify the front-office status of each feature without having to navigate back to the module.
- **Recommended workflow for daily store management:** Use this screen as a quick reference when managing your product features. If you add a new feature, remember to visit the “Hide selected features” module configuration page to decide if it should be visible to customers.

#### 2.2.2 index.php (hidefeatures/override/controllers/admin/index.php)

This file is part of the override structure and typically serves as a placeholder or entry point for the overridden controller logic. It doesn’t represent a distinct, user-facing configuration screen but rather facilitates the module’s modification of existing PrestaShop admin pages.

- **Managed Table / Entity:** This file doesn’t manage a specific table or entity directly but rather ensures the correct loading and execution of the overridden `AdminFeaturesController`.
- **Form Fields & Columns:** No direct form fields or columns are managed by this specific file. Its purpose is architectural, ensuring the module’s changes to the “Features” grid/management view are applied.
- **Effect of changes:** This file ensures that the “Active in front office” column (or similar indicator) is correctly displayed in the **Catalog > Attributes & Features > Features** list, providing the enhanced management view.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration Page** | List of all Features with ON/OFF toggles | Varies by feature (ON for new features) | Controls whether a specific product feature is displayed on product pages in the front office. ON = Visible, OFF = Hidden. |
| **AdminFeaturesController** (Catalog > Attributes & Features > Features) | “Active in front office” column/indicator | Reflects module config | Provides a quick overview of a feature’s front-office visibility status directly in the feature list. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve hidden a feature, but it’s still showing on my product page. What’s wrong?**
A:

1. **Clear Cache:** The most common reason is that your PrestaShop cache (and possibly your browser cache) hasn’t updated. Go to **Advanced Parameters > Performance** in your Back Office and click “Clear cache” (or “Clear Smarty cache” in older versions). Also, try clearing your browser’s cache or viewing the page in an incognito/private window.
2. **Module Configuration Saved?** Double-check that you clicked “Save” after making changes in the module’s configuration page.
3. **Correct Feature?** Ensure you’ve disabled the exact feature you intend to hide. Feature names can sometimes be similar.

**Q: Can I hide features only for specific products, not globally?**
A: No, this module hides features globally across all products. If you need product-specific feature visibility, you would typically manage that by not assigning the feature to the product in the first place, or by using a more advanced custom solution. This module provides a store-wide toggle for feature types.

**Q: Will hiding a feature affect my product filters or search results?**
A: No, this module only affects the *display* of features on the front office product page. The feature data itself remains in your database. If you use features for layered navigation (filters) or search, they should continue to function as expected, as long as the feature is assigned to the product.

**Q: The “Active in front office” column isn’t showing up in my Features list (Catalog > Attributes & Features > Features).**
A:

1. **Module Installed & Enabled?** Ensure the “Hide selected features” module is correctly installed and enabled in **Modules > Module Manager**.
2. **Cache:** Clear your PrestaShop cache as described above.
3. **Theme Compatibility:** In rare cases, a highly customized theme might interfere with overrides. If clearing cache doesn’t help, contact MyPresta.eu support.

**Q: How do I translate the module’s text (if any)?**
A: While this module primarily uses existing PrestaShop feature names, if there are any module-specific texts or labels, you can translate them by going to **International > Translations** in your Back Office. Select “Installed modules translations”, choose your theme, select your language, and then find the “Hide selected features” module to edit its translations.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Hide selected features” module operates by overriding core PrestaShop classes and controllers to inject its visibility logic. It extends the `Feature` and `Product` classes to add a new property for front-office visibility and modifies the `AdminFeaturesController` to display this status in the back office. The module uses a custom hook (`displayHiddenFeatures`) to render the actual feature list on the product page, allowing it to filter out hidden features before display.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: This module does not introduce any custom front-office controllers. All front-office logic is handled via overrides to core classes and hooks.
- **Back-Office Admin Controllers**:

  - `hidefeatures/override/controllers/admin/AdminFeaturesController.php`
    - **Class name & parent class**: `AdminFeaturesController` (overrides core `AdminFeaturesController`)
    - **Responsibility**: This override modifies the `AdminFeaturesController` to display the front-office visibility status of each feature in the features list. It likely adds a new column to the list table, allowing administrators to quickly see which features are hidden/visible without going into the module’s configuration. It leverages the `Feature` class override to retrieve this status.
  - `hidefeatures/override/controllers/admin/index.php`
    - **Class name & parent class**: Not a class file, typically an empty `index.php` to prevent directory listing.
    - **Responsibility**: Standard practice for `override` directories to prevent direct access and ensure security. It does not contain functional code.

### 4.3 Core Classes & Models (`classes/`)

- `hidefeatures/override/classes/Feature.php`

  - **What database table it interacts with**: `ps_feature` (main feature table) and `ps_configuration` (for module settings).
  - **Extends `ObjectModel`**: Yes, it extends the core `Feature` class which itself extends `ObjectModel`.
  - **`$definition` fields**: This override likely adds a new field to the `$definition` array of the `Feature` class, or more commonly, it adds a dynamic property to the `Feature` object to store its front-office visibility status, which is then retrieved from `ps_configuration` or a custom table. It would also contain methods to retrieve and set this visibility status.
  - **Key public methods and business logic encapsulated**:
    - Methods to retrieve the visibility status of a specific feature.
    - Methods to update the visibility status, likely interacting with `Configuration::updateValue()`.
    - Potentially modifies `getFeatures()` or similar methods to filter results based on visibility.
- `hidefeatures/override/classes/index.php`

  - **Class name & parent class**: Not a class file, typically an empty `index.php` to prevent directory listing.
  - **Responsibility**: Standard practice for `override` directories to prevent direct access and ensure security. It does not contain functional code.
- `hidefeatures/override/classes/Product.php`

  - **What database table it interacts with**: `ps_product` and `ps_feature_product`.
  - **Extends `ObjectModel`**: Yes, it extends the core `Product` class which itself extends `ObjectModel`.
  - **`$definition` fields**: No direct modification to `$definition` is expected here.
  - **Key public methods and business logic encapsulated**: This override is crucial for filtering features on the product page. It likely modifies methods like `getFeatures()` or `getFrontFeatures()` (if they exist in the core `Product` class) to:
    1. Fetch all assigned features for a product.
    2. Iterate through these features.
    3. For each feature, check its visibility status using the logic from the overridden `Feature` class.
    4. Return only the features that are marked as visible.
       This ensures that when a product’s features are retrieved for display, the hidden ones are automatically excluded.

### 4.4 JavaScript Assets (`views/js/`)

The module does not appear to contain any custom JavaScript files. Its functionality is primarily server-side via PHP overrides and Smarty template logic.

### 4.5 CSS Stylesheets (`views/css/`)

The module does not appear to contain any custom CSS files. Any styling for the added column in the AdminFeaturesController would typically be handled by PrestaShop’s default back-office CSS.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - `hidefeatures/views/templates/front/hook/displayHiddenFeatures.tpl`
    - **Hook**: `displayHiddenFeatures` (custom hook, likely called within the overridden `Product` class or a theme’s product.tpl)
    - **Output**: This template is responsible for rendering the list of product features on the front office product page. It receives the filtered list of features (after hidden ones have been removed by the `Product` class override) and displays them in the standard PrestaShop feature table/list format. Developers can inspect this template to understand how features are iterated and displayed.
- **Admin templates (`views/templates/admin/`)**:

  - `hidefeatures/views/templates/admin/_configure/helpers/list/list_content.tpl`
    - **Purpose**: This template is an override for the standard PrestaShop list content template, specifically used within the `AdminFeaturesController`. It’s responsible for rendering the rows of the features list table in the back office.
    - **Content**: It will contain logic to display the “Active in front office” column (or similar) for each feature, showing a visual indicator (e.g., a checkmark, a red X, or a toggle) based on the feature’s visibility status. This template works in conjunction with the `AdminFeaturesController` override to present the additional information.
- **Front-office templates (`views/templates/front/`)**:

  - No dedicated standalone front-office page templates.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create new custom database tables.
  - It stores its configuration (which features are hidden/visible) in the `ps_configuration` table. The configuration keys would typically follow a pattern like `HIDEFEATURES_FEATURE_ID_X` or similar, where `X` is the `id_feature`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHiddenFeatures` | Custom hook, likely called within `product.tpl` or via `Product::getFrontFeatures()` override. | Renders the filtered list of product features on the front-office product page, ensuring only visible features are shown. |
| `actionProductUpdate` | After a product is updated. | (Implicit, if module needs to re-evaluate feature visibility on product save, though not explicitly listed as a primary hook for this module’s core function). |
| `actionFeatureSave` / `actionFeatureDelete` | After a feature is saved or deleted. | (Implicit, if module needs to update its internal configuration when features are added/removed). |
| `displayBackOfficeHeader` | Renders content in the `<head>` section of the Back Office. | (Possible, for injecting JS/CSS if needed for admin UI, but not present in inventory). |

## 5. Official Support & Updates

For official updates, technical support, and any inquiries regarding the “Hide selected features” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu). Our support team is available to assist you with any issues or questions you may have.
