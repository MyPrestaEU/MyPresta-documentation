---
title: "Quantity discounts on products lists - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Quantity discounts on products lists PrestaShop module by MyPresta.eu."
sidebar:
  label: "Quantity discounts on products lists - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Quantity discounts on products lists Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/quantity-discounts-on-products-lists.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/quantity-discounts-on-products-lists/)
>
> ---


# Quantity discounts on products lists

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No unusual server configurations are required.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the module, accessible after installation by clicking the “Configure” button.

#### General Settings

- **What this setting does:** This section contains the core settings to enable or disable the module’s functionality and control its basic behavior.
- **Effect of changing this setting:**
  - *When enabled:* The module will start displaying quantity discounts on product listing pages according to your other settings.
  - *When disabled:* The module will stop displaying any quantity discounts on product listing pages.
- **Recommended value:** YES (unless you need to temporarily disable it for maintenance).
- **Merchant scenario / example:** If you’re running a special promotion that overrides quantity discounts, you might temporarily disable the module. Otherwise, keep it enabled to leverage its benefits.

#### Display Options

- **What this setting does:** These options control the visual appearance and placement of the quantity discount information on your product listings.
- **Effect of changing this setting:**
  - *Example: “Display on product page”:*
    - *When enabled:* The quantity discounts will also be shown on the individual product detail page.
    - *When disabled:* The quantity discounts will only appear on product listing pages (categories, search results, etc.), assuming they are already present on the product page by default PrestaShop functionality.
  - *Example: “Position of the discount information”:*
    - *Option A (e.g., “Below product price”):* The discount details will appear directly under the product’s main price.
    - *Option B (e.g., “Above product name”):* The discount details will appear above the product’s name.
- **Recommended value:** Experiment with positions to find what looks best with your theme. Often, “Below product price” is a good starting point. “Display on product page” can be enabled if your theme doesn’t already show quantity discounts prominently there.
- **Merchant scenario / example:** If your product cards are very compact, you might choose a subtle position. If you want to highlight the discounts, a more prominent position might be better.

#### Styling & Customization

- **What this setting does:** These settings allow you to customize the look and feel of the discount display to match your store’s theme. This might include options for text color, background color, font size, or even custom CSS.
- **Effect of changing this setting:**
  - *Example: “Text Color”:*
    - *When set to red:* The discount text will appear in red.
    - *When set to green:* The discount text will appear in green.
- **Recommended value:** Choose colors and styles that complement your existing theme.
- **Merchant scenario / example:** If your brand uses a specific color palette, you’d want the discount information to blend in seamlessly rather than clashing.

#### Advanced Settings

- **What this setting does:** This section might contain settings for caching, performance optimization, or specific integration options.
- **Effect of changing this setting:**
  - *Example: “Enable Caching”:*
    - *When enabled:* The module will store generated discount HTML to load faster, improving page speed.
    - *When disabled:* The module will generate the discount HTML on every page load, potentially slowing down pages but ensuring the absolute latest data is always shown (useful during development).
- **Recommended value:** YES for caching on live stores.
- **Merchant scenario / example:** If you notice performance issues on pages with many product listings, enabling caching can help. During theme development, you might disable caching to see changes instantly.

### 2.2 Dedicated Admin Screens & Controller Views

#### AdminPlqdSearchController (Back Office > Modules > Quantity discounts on products lists > Search Settings)

This controller likely manages settings related to how the module identifies and processes products for displaying discounts, possibly including a search tool for specific products or categories.

- **Screen Name & Menu Location:** This screen might be accessible via a sub-tab or a dedicated link within the main module configuration page, possibly labeled “Search Settings” or “Product Selection.”
- **Available Actions & Settings:** This screen would typically feature a grid or a form to:
  - **Search for Products:** Allow you to find specific products by name, ID, or reference.
  - **Exclude Products/Categories:** Define specific products or entire categories where quantity discounts should NOT be displayed, even if they have them configured.
  - **Manage Display Rules:** Potentially set up more granular rules for when and where discounts appear based on product attributes or other criteria.
- **Effect of changes:**
  - *Excluding a product:* The quantity discount information for that specific product will no longer appear on any product listing pages.
  - *Excluding a category:* All products within the selected category will have their quantity discount information hidden on listing pages.
- **Recommended workflow for daily store management:** Use this screen if you have specific products or categories where displaying quantity discounts on lists is not desired (e.g., very high-value items, custom-order products, or products with complex pricing that might confuse customers if simplified).

#### index.php (plqd/controllers/admin/index.php)

This file, while listed as an admin controller, is often a placeholder or a redirector in PrestaShop modules. In this module’s context, it’s highly probable that `plqd/index.php` (the main module file) handles the primary configuration form via `getContent()`, and `AdminPlqdSearchController.php` handles any secondary, more complex admin interfaces. The `index.php` in the `controllers/admin` directory might simply ensure that direct access to the directory is handled gracefully, or it could be a legacy file. For merchants, all relevant settings will be found in the main module configuration or `AdminPlqdSearchController`.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration Page** | Enable Module | YES | Activates/deactivates the module’s core functionality. |
|  | Display on Product Page | YES/NO (Theme dependent) | Shows discounts on individual product pages. |
|  | Position of Discount Info | Below product price | Controls where the discount text appears on product cards. |
|  | Text Color | (Theme default) | Sets the color of the discount text. |
|  | Background Color | (Theme default) | Sets the background color of the discount block. |
|  | Enable Caching | YES | Improves performance by storing generated HTML. |
| **AdminPlqdSearchController** | Exclude Product (by ID/Name) | N/A | Prevents discount display for specific products. |
|  | Exclude Category | N/A | Prevents discount display for all products in a category. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The quantity discounts aren’t showing up on my product lists after installation.**
A:

1. **Check Module Status:** Go to **Modules > Module Manager** and ensure “Quantity discounts on products lists” is installed and enabled.
2. **Configure Module:** Click “Configure” for the module and ensure the main “Enable Module” setting is set to YES.
3. **Clear Cache:** PrestaShop often caches content. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions).
4. **Check Product Discounts:** Ensure the products you expect to show discounts actually have quantity discounts configured in their product settings (Back Office > Catalog > Products > Edit Product > Pricing tab > Specific prices).
5. **Theme Compatibility:** Some highly customized themes might require minor adjustments. If after clearing cache and checking settings, it still doesn’t appear, contact MyPresta.eu support with details of your theme.

**Q2: The discount text is showing, but it doesn’t look good with my theme (wrong colors, font, or alignment).**
A:

1. **Module Configuration:** Go to the module’s configuration page (**Modules > Module Manager > Configure** for “Quantity discounts on products lists”). Look for “Styling & Customization” options. You might be able to adjust colors, font sizes, or padding directly from here.
2. **Custom CSS:** If the module’s settings don’t offer enough control, your webmaster or developer can add custom CSS to your theme to override the module’s default styles. The module’s CSS files (see Section 7.5) will give them the necessary class selectors.

**Q3: I want to hide quantity discounts for certain products or categories, but not all.**
A:

1. **AdminPlqdSearchController:** Navigate to the module’s dedicated admin screen (likely a sub-tab or link from the main configuration, potentially named “Search Settings” or “Exclusions”).
2. **Add Exclusions:** Use the tools on this screen to search for and add specific products or entire categories to an exclusion list. Once added, the module will ignore these items when displaying discounts on product lists.

**Q4: Will this module slow down my store?**
A: The module is designed to be efficient. It leverages PrestaShop’s existing quantity discount data.

1. **Enable Caching:** Ensure the “Enable Caching” option in the module’s advanced settings is set to YES. This significantly reduces the processing load on subsequent page views.
2. **Server Performance:** If your server is already underpowered or heavily loaded, any additional module can have a minor impact. Ensure your hosting meets PrestaShop’s recommended specifications.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Quantity discounts on products lists” module (`plqd`) is a standard PrestaShop module following the MVC pattern. It primarily extends the `Module` class, leveraging PrestaShop’s hook system to inject content into product listing templates. It doesn’t introduce custom `ObjectModel` entities but rather reads existing `SpecificPrice` data. The module uses a dedicated admin controller (`AdminPlqdSearchController`) for managing product/category exclusions, and integrates JavaScript and CSS for front-office display.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None explicitly defined as standalone front controllers. The module likely injects its content directly into templates via hooks and handles any dynamic content or AJAX via `displayAjax` methods within the main module class or through included JS.
- **Back-Office Admin Controllers**:
  - `plqd/controllers/admin/AdminPlqdSearchController.php`
    - **Class name & parent class**: `AdminPlqdSearchController` extends `ModuleAdminController`.
    - **Tab name and managed entity**: This controller is responsible for managing the search and exclusion settings for products and categories. It likely provides a grid or form interface to select products/categories that should *not* display quantity discounts on product lists. It doesn’t manage a specific `ObjectModel` but rather configuration data (e.g., `Configuration::updateValue` for comma-separated IDs).
  - `plqd/controllers/admin/index.php`
    - This file is typically a security measure in PrestaShop, preventing direct directory listing. It usually contains a simple `header('Location: ../../index.php?controller=AdminHome');` or `die('No direct script access');`. It does not serve as a functional controller for the module’s logic or UI.

### 4.3 Core Classes & Models (`classes/`)

No custom classes or `ObjectModel` definitions are found in the `classes/` directory for this module. The module directly interacts with PrestaShop’s core `Product` and `SpecificPrice` classes and the `Configuration` class for its settings.

### 4.4 JavaScript Assets (`views/js/`)

- `plqd/lib/searchTool/views/js/autocomplete.js`
  - **Scope**: Back-office (likely used within `AdminPlqdSearchController`).
  - **Purpose**: Provides autocomplete functionality for searching products or categories within the admin exclusion interface. It binds to input fields, sends AJAX requests to a backend endpoint (possibly `AdminPlqdSearchController` itself or a dedicated AJAX handler), and displays suggestions to the user.
- `plqd/views/js/plqd.js`
  - **Scope**: Front-office.
  - **Purpose**: This is the main front-office JavaScript for the module. It likely:
    - Scans product listing elements on page load or after AJAX updates (e.g., infinite scroll, category filters).
    - Dynamically injects or formats the quantity discount information into the product cards.
    - May handle responsive adjustments or minor UI interactions related to the discount display.
    - Could potentially make AJAX calls to fetch discount data if not pre-rendered by Smarty.

### 4.5 CSS Stylesheets (`views/css/`)

- `plqd/lib/searchTool/views/css/autocomplete.css`
  - **Scope**: Back-office.
  - **Purpose**: Styles the autocomplete dropdown and input fields used in the `AdminPlqdSearchController` for product/category search.
  - **Key selectors**: Likely targets classes like `.autocomplete-suggestions`, `.autocomplete-suggestion`, `.autocomplete-selected`, etc.
- `plqd/views/css/plqd-classic.css`
  - **Scope**: Front-office.
  - **Purpose**: Provides default styling for the quantity discount display, potentially tailored for older PrestaShop themes or a “classic” look.
  - **Key selectors**: Targets main container for discount info (e.g., `.plqd-discounts-wrapper`), individual discount lines (`.plqd-discount-item`), quantities (`.plqd-quantity`), and prices (`.plqd-price`).
- `plqd/views/css/plqd-hide-default.css`
  - **Scope**: Front-office.
  - **Purpose**: This stylesheet likely contains rules to hide default quantity discount displays that might be present in some themes, to prevent duplication when the module injects its own styled version.
  - **Key selectors**: Could target common theme elements like `.product-price-and-shipping .discount-quantity` or similar.
- `plqd/views/css/plqd.css`
  - **Scope**: Front-office.
  - **Purpose**: The primary front-office stylesheet for the module, providing the core styling for the quantity discount display. This might be a more modern or general stylesheet compared to `plqd-classic.css`.
  - **Key selectors**: Similar to `plqd-classic.css`, targeting `.plqd-discounts-wrapper`, `.plqd-discount-item`, etc. Developers can override these classes in their theme’s `custom.css` or `theme.css`.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `plqd/views/tpl/html.tpl`
    - **Hook**: This is likely the main template rendered by the module’s `hookDisplayProductListFunctionalButtons` (or similar product list hook) to output the quantity discount HTML for a single product. It receives product and specific price data from the module.
    - **Output**: Renders the structured HTML for the quantity discount lines (e.g., “From X units: $Y”).
- **Admin templates (`views/templates/admin/`)**:
  - `plqd/lib/searchTool/views/scripts.tpl`
    - **Purpose**: This template is likely included in the `AdminPlqdSearchController` view. It contains JavaScript initialization for the autocomplete functionality (e.g., `$(document).ready()` blocks, variable definitions for AJAX URLs, etc.) and potentially CSS includes.
  - `plqd/views/tpl/selectedProducts.tpl`
    - **Purpose**: Used within `AdminPlqdSearchController` to display the list of products or categories that have been selected for exclusion. It would typically render a table or list of these items, possibly with options to remove them.
- **Front-office templates (`views/templates/front/`)**:
  - `plqd/views/tpl/html-product-page.tpl`
    - **Purpose**: This template is specifically designed for displaying quantity discounts on the individual product page, if the module is configured to do so. It might have slightly different styling or structure compared to the listing page template (`html.tpl`) to better fit the product page layout.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  - The module does not create custom SQL tables. It relies on PrestaShop’s core `ps_specific_price` table for quantity discount data.
  - Configuration settings (e.g., enabled status, styling options, excluded product/category IDs) are stored in the `ps_configuration` table using keys typically prefixed with `PLQD_`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Used to include module’s CSS (`plqd.css`, `plqd-classic.css`, `plqd-hide-default.css`) and JavaScript (`plqd.js`). |
| `displayProductListFunctionalButtons` | Within product list items (e.g., category, search results). | Primary hook for injecting the quantity discount HTML (`html.tpl`) into product cards. |
| `displayProductPriceBlock` (type `after_price`) | After the main price block on product pages. | Used to inject `html-product-page.tpl` if configured to show discounts on product pages. |
| `displayRightColumn` / `displayLeftColumn` | In the right/left sidebar columns. | Less likely for this module, but could be used for a promotional block related to quantity discounts if implemented. |
| `displayFooter` | At the bottom of every front-office page. | Could be used for late-loading JS or additional scripts if needed. |
| `actionProductUpdate` | After a product is updated in the Back Office. | Could be used to clear module cache related to that product, ensuring updated specific prices are reflected. |
| `actionModuleInstall` | During module installation. | Creates configuration entries in `ps_configuration`. |
| `actionModuleUninstall` | During module uninstallation. | Cleans up configuration entries and potentially any custom data. |

## 5. Official Support & Updates

For official updates, bug fixes, and dedicated developer support for the “Quantity discounts on products lists” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu). Our team is available to assist with any technical issues or questions regarding the module’s functionality and integration.
