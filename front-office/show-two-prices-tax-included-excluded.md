---
title: "Show two prices - tax included / excluded - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Show two prices - tax included / excluded PrestaShop module by MyPresta.eu."
sidebar:
  label: "Show two prices - tax included / excluded - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Show two prices - tax included / excluded Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/show-two-prices-tax-included-excluded.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/show-two-prices-tax-included-excluded/)
>
> ---


# Show two prices - tax included / excluded

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required for PrestaShop itself and generally for module operations. No special hosting requirements beyond a standard PrestaShop-compatible environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the “Show two prices - tax included / excluded” module. You can access it by navigating to **Modules > Module Manager** and clicking “Configure” next to the module name.

#### General Settings

- **Enabled / Disabled (Global Switch)**
  - **What this setting does:** This is the master switch to turn the entire module’s functionality on or off across your store.
  - **Effect of changing this setting:**
    - *When enabled:* The module will start displaying both tax-included and tax-excluded prices according to your other settings.
    - *When disabled:* The module will stop displaying the additional price information, and your store will revert to its default price display behavior.
  - **Recommended value:** Enabled (to utilize the module’s features).
  - **Merchant scenario / example:** If you’re performing maintenance or temporarily want to hide the dual price display, you can disable it here.

#### Product Page Settings

- **Show on Product Page (BF\_PP)**

  - **What this setting does:** Controls whether both tax-included and tax-excluded prices are displayed on individual product detail pages.
  - **Effect of changing this setting:**
    - *When enabled:* Both prices will appear on product pages.
    - *When disabled:* Only the default PrestaShop price (usually tax-included) will be shown on product pages.
  - **Recommended value:** On (to provide full transparency).
  - **Merchant scenario / example:** If you only want to show dual prices on category listings but keep product pages cleaner, you might disable this.
- **Hide Tax Included Price on Product Page (BOTH\_HIDE\_P)**

  - **What this setting does:** If “Show on Product Page” is enabled, this option allows you to hide the tax-included price, effectively showing only the tax-excluded price alongside the original price (if not hidden).
  - **Effect of changing this setting:**
    - *When enabled:* The tax-included price will be hidden on product pages.
    - *When disabled:* The tax-included price will be visible on product pages (if “Show on Product Page” is enabled).
  - **Recommended value:** Off (unless you have a specific reason to hide it, e.g., B2B-focused store).
  - **Merchant scenario / example:** A B2B store might want to emphasize tax-excluded prices and hide the tax-included price to streamline the view for their business customers.
- **Custom CSS for Product Page (BF\_PPC)**

  - **What this setting does:** Allows you to add custom CSS rules specifically for the dual price display on product pages. This is for advanced users or webmasters.
  - **Effect of changing this setting:** Any CSS code entered here will be applied to the module’s price elements on product pages, allowing you to change colors, fonts, sizes, or positioning.
  - **Recommended value:** Leave empty unless you have specific styling needs.
  - **Merchant scenario / example:** You might want to make the tax-excluded price smaller or a different color than the tax-included price to differentiate them visually.
- **Force Hide Product Page (BP\_FORCE\_HIDE)**

  - **What this setting does:** This is a more aggressive option to hide the module’s output on the product page. It can be useful if the module’s output conflicts with your theme or other modules.
  - **Effect of changing this setting:**
    - *When enabled:* The module will attempt to forcefully hide its price display on product pages, regardless of other settings.
    - *When disabled:* The module will display prices according to other settings.
  - **Recommended value:** Off (only enable if you experience display issues).
  - **Merchant scenario / example:** If the dual price display is overlapping with another element on your product page, enabling this might resolve the conflict.
- **Tax Included Price Label (BP\_TIN)**

  - **What this setting does:** Defines the text label displayed next to the tax-included price on product pages.
  - **Effect of changing this setting:** Changes the label text.
  - **Recommended value:** “Tax incl.” or “VAT incl.”
  - **Merchant scenario / example:** You might change this to “Price with VAT” for clarity in certain regions.
- **Tax Excluded Price Label (BP\_TEX)**

  - **What this setting does:** Defines the text label displayed next to the tax-excluded price on product pages.
  - **Effect of changing this setting:** Changes the label text.
  - **Recommended value:** “Tax excl.” or “VAT excl.”
  - **Merchant scenario / example:** You might change this to “Price without VAT” for clarity.
- **Original Tax Included Price Label (BP\_O\_TIN)**

  - **What this setting does:** Defines the text label for the *original* tax-included price, especially useful when specific prices or discounts are applied.
  - **Effect of changing this setting:** Changes the label text.
  - **Recommended value:** “Original Tax incl.”
  - **Merchant scenario / example:** When a product is on sale, you might want to show the original price with a specific label.

#### Product Listing Page Settings

- **Show on Product Listing (BF\_PL)**

  - **What this setting does:** Controls whether both tax-included and tax-excluded prices are displayed on product listing pages (categories, search results, homepage modules).
  - **Effect of changing this setting:**
    - *When enabled:* Both prices will appear on product listing pages.
    - *When disabled:* Only the default PrestaShop price will be shown on product listing pages.
  - **Recommended value:** On (for consistent transparency).
  - **Merchant scenario / example:** If your category pages are very dense, you might disable this to reduce visual clutter.
- **Hide Tax Included Price on Product Listing (BOTH\_HIDE\_PL)**

  - **What this setting does:** If “Show on Product Listing” is enabled, this option allows you to hide the tax-included price on listing pages.
  - **Effect of changing this setting:**
    - *When enabled:* The tax-included price will be hidden on product listing pages.
    - *When disabled:* The tax-included price will be visible on product listing pages.
  - **Recommended value:** Off (unless you have a specific reason to hide it).
  - **Merchant scenario / example:** A B2B store might want to only show tax-excluded prices on all product listings.
- **Custom CSS for Product Listing (BF\_PLC)**

  - **What this setting does:** Allows you to add custom CSS rules specifically for the dual price display on product listing pages.
  - **Effect of changing this setting:** Any CSS code entered here will be applied to the module’s price elements on listing pages.
  - **Recommended value:** Leave empty unless you have specific styling needs.
  - **Merchant scenario / example:** You might want the tax-excluded price to be smaller and grayed out on category pages to make the primary (tax-included) price stand out more.
- **Tax Included Price Label (BP\_TINL)**

  - **What this setting does:** Defines the text label displayed next to the tax-included price on product listing pages.
  - **Effect of changing this setting:** Changes the label text.
  - **Recommended value:** “Tax incl.” or “VAT incl.”
  - **Merchant scenario / example:** You might use a shorter label like “incl.” on listing pages due to limited space.
- **Tax Excluded Price Label (BP\_TEXL)**

  - **What this setting does:** Defines the text label displayed next to the tax-excluded price on product listing pages.
  - **Effect of changing this setting:** Changes the label text.
  - **Recommended value:** “Tax excl.” or “VAT excl.”
  - **Merchant scenario / example:** You might use a shorter label like “excl.” on listing pages.

#### Visibility Rules

- **Visibility Rule (bp\_visibility\_rule)**

  - **What this setting does:** Determines how the dual price display behaves based on customer groups, specific products, or categories.
  - **Effect of changing this setting:**
    - *Always show:* Dual prices are always shown for all customers, products, and categories.
    - *Hide for selected groups/products/categories:* Dual prices are hidden for specific selections.
    - *Show only for selected groups/products/categories:* Dual prices are only shown for specific selections.
  - **Recommended value:** Always show (for maximum transparency), or “Show only for selected groups” if you target B2B customers specifically.
  - **Merchant scenario / example:** You might choose “Show only for selected groups” and then select your “Wholesale Customers” group to only display dual prices for your B2B clients.
- **Visibility for Customer Groups (actionAdminGroupsControllerSaveAfter)**

  - **What this setting does:** Allows you to select which customer groups will see the dual price display, based on the “Visibility Rule” above.
  - **Effect of changing this setting:** Only customers belonging to the selected groups will see the dual prices (if the rule is “Show only for selected groups”) or will *not* see them (if the rule is “Hide for selected groups”).
  - **Recommended value:** Select “All Customer Groups” if your rule is “Always show”. Otherwise, select the relevant groups.
  - **Merchant scenario / example:** If you want only your “Guest” and “Customer” groups to see tax-included prices primarily, but “Wholesale” to see both, you’d set the rule to “Show only for selected groups” and select “Wholesale”.
- **Visibility for Products (bp\_visibility\_products)**

  - **What this setting does:** Allows you to specify individual products for which the dual price display should apply (or not apply), based on the “Visibility Rule.” This uses an autocomplete search field.
  - **Effect of changing this setting:** The dual price display will be enabled or disabled for the selected products according to your chosen visibility rule.
  - **Recommended value:** Leave empty if you want it to apply to all products.
  - **Merchant scenario / example:** You might have a few specific products where showing both prices is confusing, so you’d set the rule to “Hide for selected products” and add those products here.
- **Visibility for Categories (bp\_visibility\_cat)**

  - **What this setting does:** Allows you to specify categories for which the dual price display should apply (or not apply), based on the “Visibility Rule.”
  - **Effect of changing this setting:** The dual price display will be enabled or disabled for all products within the selected categories according to your chosen visibility rule.
  - **Recommended value:** Leave empty if you want it to apply to all categories.
  - **Merchant scenario / example:** If you sell both physical goods (where tax is relevant) and digital products (where tax might be handled differently), you could hide dual prices for your “Digital Downloads” category.

#### Display Options

- **Show Price Types (BF\_SHOW\_TYPES)**

  - **What this setting does:** Determines which price types are displayed.
  - **Effect of changing this setting:**
    - *Tax included and Tax excluded:* Shows both prices.
    - *Only Tax included:* Shows only the tax-included price (module still processes, but only displays one).
    - *Only Tax excluded:* Shows only the tax-excluded price.
  - **Recommended value:** Tax included and Tax excluded (to leverage the module’s core feature).
  - **Merchant scenario / example:** If your primary goal is to show tax-excluded prices to B2B customers, you might select “Only Tax excluded” in conjunction with a customer group visibility rule.
- **Use Classic Theme CSS (BF\_CLASSICCSS)**

  - **What this setting does:** If your theme is based on the default PrestaShop Classic theme, enabling this will apply specific CSS rules designed to integrate smoothly with that theme’s styling.
  - **Effect of changing this setting:**
    - *When enabled:* The module will load a dedicated stylesheet (`classic.css`) to ensure better visual integration with Classic-based themes.
    - *When disabled:* The module will use its default styling, which might require custom CSS for perfect integration with non-Classic themes.
  - **Recommended value:** Enable if your theme is Classic-based or a child theme of Classic. Disable otherwise.
  - **Merchant scenario / example:** If you’ve just installed the module and the prices look misaligned on your Classic theme, enabling this might fix it.
- **Own CSS (BF\_OWNCSS)**

  - **What this setting does:** Provides a text area where you can input your own custom CSS code to override or add styles to the module’s output. This is for advanced users or webmasters.
  - **Effect of changing this setting:** Any CSS code entered here will be applied globally to the module’s price displays, allowing for complete control over styling.
  - **Recommended value:** Leave empty unless you have specific styling needs.
  - **Merchant scenario / example:** You want to change the font size of the displayed prices or add a border around them to make them more prominent.

#### Advanced Settings

- **Product Page Tax Percentage (BP\_PP\_TPERCENT)**

  - **What this setting does:** Allows you to display the tax percentage on product pages.
  - **Effect of changing this setting:**
    - *On:* The tax percentage (e.g., “20% VAT”) will be shown alongside the prices.
    - *Off:* The tax percentage will not be displayed.
  - **Recommended value:** Off (unless you want to explicitly show the tax rate).
  - **Merchant scenario / example:** In countries where customers are very tax-conscious, showing the percentage can add another layer of transparency.
- **Product Page Tax Percentage (Tax Excluded) (BP\_PP\_TPERCENT\_TEXL)**

  - **What this setting does:** Similar to the above, but specifically for the tax-excluded price display on product pages.
  - **Effect of changing this setting:**
    - *On:* The tax percentage will be shown next to the tax-excluded price.
    - *Off:* The tax percentage will not be displayed.
  - **Recommended value:** Off.
  - **Merchant scenario / example:** Useful if you want to highlight the tax rate that is being excluded.
- **Product Listing Tax Percentage (BP\_PL\_TPERCENT)**

  - **What this setting does:** Allows you to display the tax percentage on product listing pages.
  - **Effect of changing this setting:**
    - *On:* The tax percentage will be shown alongside the prices on listing pages.
    - *Off:* The tax percentage will not be displayed.
  - **Recommended value:** Off (to keep listing pages cleaner).
  - **Merchant scenario / example:** If your product listings are not too crowded, showing the tax percentage can be informative.
- **Product Listing Tax Percentage (Tax Excluded) (BP\_PL\_TPERCENT\_TEXL)**

  - **What this setting does:** Similar to the above, but specifically for the tax-excluded price display on product listing pages.
  - **Effect of changing this setting:**
    - *On:* The tax percentage will be shown next to the tax-excluded price on listing pages.
    - *Off:* The tax percentage will not be displayed.
  - **Recommended value:** Off.
  - **Merchant scenario / example:** Less common, but could be used to emphasize the tax component being removed.

#### Language Settings (Internal)

- **PS\_LANG\_DEFAULT, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG**
  - **What this setting does:** These are internal PrestaShop settings related to default language and employee form language. They are displayed here for informational purposes and are not directly configurable by the module.
  - **Effect of changing this setting:** Not applicable, these are read-only values from your PrestaShop configuration.
  - **Recommended value:** N/A
  - **Merchant scenario / example:** These values help the module determine which language to use for labels if you haven’t explicitly set them for all languages.

### 2.2 Dedicated Admin Screens & Controller Views

#### AdminBothpricesSearchController (Back Office > Modules > Show two prices - tax included / excluded > Search Products)

This dedicated admin screen is used for managing the “Visibility for Products” setting. It provides an interface to search for and select specific products that should be affected by the module’s visibility rules.

- **Screen Name & Menu Location:** You can access this screen by clicking on the “Search Products” link or button within the main module configuration page, usually next to the “Visibility for Products” setting.
- **Available Actions & Settings:**
  - **Product Search Field:** A text input where you can type product names or IDs to find specific products.
  - **Search Results Grid:** Displays a list of products matching your search query.
  - **Add/Remove Buttons:** Allows you to add selected products to or remove them from the list of products affected by the visibility rule.
  - **Selected Products List:** Shows all products currently configured for the visibility rule.
- **Effect of changes:**
  - Adding a product to the list means that the module’s dual price display will either be shown *only* for that product or *hidden* for that product, depending on your overall “Visibility Rule” setting.
  - Removing a product means it will no longer be specifically affected by the product-level visibility rule and will revert to the general module settings.
- **Recommended workflow for daily store management:**
  1. Go to the main module configuration page.
  2. Set your “Visibility Rule” (e.g., “Hide for selected products”).
  3. Click the link/button to open the “AdminBothpricesSearchController” screen.
  4. Use the search field to find the products you want to include in the rule.
  5. Add them to the “Selected Products List.”
  6. Save your changes on the main module configuration page.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Config | Enabled / Disabled | Enabled | Master switch for module functionality. |
| Module Config | Show on Product Page (BF\_PP) | On | Displays dual prices on product detail pages. |
| Module Config | Hide Tax Included Price on Product Page (BOTH\_HIDE\_P) | Off | Hides tax-incl. price on product pages. |
| Module Config | Custom CSS for Product Page (BF\_PPC) | Empty | Custom CSS for product page price display. |
| Module Config | Force Hide Product Page (BP\_FORCE\_HIDE) | Off | Forcefully hides module output on product page. |
| Module Config | Tax Included Price Label (BP\_TIN) | “Tax incl.” | Label for tax-included price on product page. |
| Module Config | Tax Excluded Price Label (BP\_TEX) | “Tax excl.” | Label for tax-excluded price on product page. |
| Module Config | Original Tax Included Price Label (BP\_O\_TIN) | “Original Tax incl.” | Label for original tax-included price on product page. |
| Module Config | Show on Product Listing (BF\_PL) | On | Displays dual prices on category/listing pages. |
| Module Config | Hide Tax Included Price on Product Listing (BOTH\_HIDE\_PL) | Off | Hides tax-incl. price on listing pages. |
| Module Config | Custom CSS for Product Listing (BF\_PLC) | Empty | Custom CSS for listing page price display. |
| Module Config | Tax Included Price Label (BP\_TINL) | “Tax incl.” | Label for tax-included price on listing pages. |
| Module Config | Tax Excluded Price Label (BP\_TEXL) | “Tax excl.” | Label for tax-excluded price on listing pages. |
| Module Config | Visibility Rule (bp\_visibility\_rule) | Always show | Defines how visibility rules are applied (show/hide for selected). |
| Module Config | Visibility for Customer Groups | All Customer Groups | Selects customer groups affected by visibility rule. |
| Module Config | Visibility for Products (bp\_visibility\_products) | Empty | Selects specific products affected by visibility rule. |
| Module Config | Visibility for Categories (bp\_visibility\_cat) | Empty | Selects specific categories affected by visibility rule. |
| Module Config | Show Price Types (BF\_SHOW\_TYPES) | Tax included and Tax excluded | Determines which price types are displayed (both, only incl, only excl). |
| Module Config | Use Classic Theme CSS (BF\_CLASSICCSS) | Off (Enable for Classic themes) | Applies Classic theme specific styling. |
| Module Config | Own CSS (BF\_OWNCSS) | Empty | Global custom CSS for module output. |
| Module Config | Product Page Tax Percentage (BP\_PP\_TPERCENT) | Off | Displays tax percentage on product pages. |
| Module Config | Product Page Tax Percentage (Tax Excluded) (BP\_PP\_TPERCENT\_TEXL) | Off | Displays tax percentage for tax-excluded price on product pages. |
| Module Config | Product Listing Tax Percentage (BP\_PL\_TPERCENT) | Off | Displays tax percentage on listing pages. |
| Module Config | Product Listing Tax Percentage (Tax Excluded) (BP\_PL\_TPERCENT\_TEXL) | Off | Displays tax percentage for tax-excluded price on listing pages. |
| AdminBothpricesSearchController | Product Search / Add/Remove | N/A | Manages the list of products for visibility rules. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The module is enabled, but I don’t see two prices on my store.**
A:

- **Check Global Enablement:** Ensure the main “Enabled / Disabled” switch at the top of the module configuration is set to “Enabled.”
- **Check Page-Specific Settings:** Verify that “Show on Product Page” (BF\_PP) and/or “Show on Product Listing” (BF\_PL) are enabled, depending on where you expect to see the prices.
- **Check Visibility Rules:** If you’ve set a “Visibility Rule,” ensure your current customer group, product, or category is included in the “show” rule or not excluded by a “hide” rule.
- **Clear Cache:** Always clear your PrestaShop cache (Advanced Parameters > Performance > Clear Cache) after making module configuration changes. Also, clear your browser’s cache.
- **Theme Conflicts:** Some highly customized themes might conflict. Try temporarily switching to the default PrestaShop Classic theme to see if the prices appear. If they do, it’s a theme-related CSS or JS conflict.

**Q2: The prices are showing, but they look misaligned or have incorrect styling.**
A:

- **Use Classic Theme CSS:** If your theme is based on the default PrestaShop Classic theme, try enabling the “Use Classic Theme CSS (BF\_CLASSICCSS)” option in the module configuration.
- **Custom CSS:** If you have a custom theme, you might need to add custom CSS. Use your browser’s developer tools (F12) to identify the CSS classes of the module’s price elements. Then, use the “Own CSS (BF\_OWNCSS)” field in the module configuration to add your styling rules.
- **Module Position:** Ensure the module is hooked correctly. While the module handles most hooks automatically, sometimes theme-specific hooks might be needed.

**Q3: The prices don’t update when I change product attributes (e.g., size, color) on the product page.**
A:

- **Module Compatibility:** Ensure your PrestaShop version is within the supported range.
- **JavaScript Conflicts:** This is often caused by JavaScript conflicts with your theme or another module. Check your browser’s console (F12 > Console tab) for any JavaScript errors when changing attributes.
- **Theme Overrides:** If your theme heavily overrides PrestaShop’s default product page JavaScript, it might prevent the module from detecting price changes. Contact your theme developer or a webmaster for assistance.
- **Clear Cache:** Clear PrestaShop and browser cache.

**Q4: How do I translate the price labels (e.g., “Tax incl.”, “Tax excl.”) into other languages?**
A:

- Go to **International > Translations** in your PrestaShop Back Office.
- Select “Installed modules translations.”
- Choose your theme.
- Select your language.
- Find the “Show two prices - tax included / excluded” module in the list.
- You will find fields for “Tax Included Price Label,” “Tax Excluded Price Label,” etc., for both product and listing pages. Enter your translations there and save.

**Q5: I only want to show tax-excluded prices to specific customer groups (e.g., B2B). How do I do this?**
A:

- In the module configuration, set **“Visibility Rule”** to “Show only for selected groups.”
- Then, select the specific customer group(s) (e.g., “Wholesale,” “B2B”) that should see the dual prices.
- Optionally, set **“Show Price Types”** to “Only Tax excluded” if you want to completely hide the tax-included price for these groups.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Show two prices - tax included / excluded” module (`bothprices`) is a standard PrestaShop module following the MVC pattern. It primarily extends the `Module` class, leveraging PrestaShop’s hook system to inject price information and modify display. It uses a dedicated Admin Controller for product search functionality and front controllers for AJAX interactions. The module relies on Smarty templates for rendering and custom JavaScript/CSS for dynamic updates and styling. Configuration is stored in `ps_configuration`.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `controllers/front/ajax.php`
    - **Class name & parent class**: `BothpricesAjaxModuleFrontController` extends `ModuleFrontController`.
    - **Responsibility**: Handles AJAX requests from the front-office, primarily for dynamically updating prices when product attributes are changed. It likely fetches product information and calculates prices based on selected attributes and customer context, returning JSON data.
  - `controllers/front/index.php`
    - **Class name & parent class**: `BothpricesIndexModuleFrontController` extends `ModuleFrontController`.
    - **Responsibility**: This is a placeholder or fallback controller. In many modules, `index.php` controllers are used for basic routing or to prevent directory listing. It might not have significant custom logic beyond basic dispatch.
- **Back-Office Admin Controllers**:

  - `controllers/admin/AdminBothpricesSearchController.php`
    - **Class name & parent class**: `AdminBothpricesSearchController` extends `ModuleAdminController`.
    - **Tab name and managed entity**: This controller manages the product search and selection for the module’s visibility rules. It does not directly manage a specific `ObjectModel` but interacts with `Product` data for selection. It provides a grid-like interface for searching and adding/removing products from the `bp_visibility_products` configuration.

### 4.3 Core Classes & Models (`classes/`)

The module does not appear to define any custom `ObjectModel` classes in the `classes/` directory. It likely relies on existing PrestaShop `Product` and `Configuration` classes.

### 4.4 JavaScript Assets (`views/js/`)

- `bothprices/lib/searchTool/views/js/autocomplete.js`
  - **Scope**: Back-office.
  - **Description**: Provides autocomplete functionality for the product search field within `AdminBothpricesSearchController`, allowing administrators to quickly find and select products for visibility rules.
- `bothprices/views/js/both-hide-p.js`
  - **Scope**: Front-office (Product Page).
  - **Description**: Contains JavaScript logic to hide the tax-included price specifically on the product page, based on the `BOTH_HIDE_P` configuration setting. It likely targets specific DOM elements to apply `display: none` or similar styling.
- `bothprices/views/js/both-hide-pl.js`
  - **Scope**: Front-office (Product Listing Pages).
  - **Description**: Similar to `both-hide-p.js`, but for product listing pages, hiding the tax-included price based on the `BOTH_HIDE_PL` configuration.
- `bothprices/views/js/bothprices-admin.js`
  - **Scope**: Back-office.
  - **Description**: Contains general JavaScript for the module’s back-office configuration page. This might include logic for showing/hiding configuration fields based on other selections (e.g., visibility rule changes), form validation, or AJAX calls for saving settings.
- `bothprices/views/js/bothprices.js`
  - **Scope**: Front-office (Global).
  - **Description**: This is the main front-office JavaScript file. It’s responsible for:
    - Listening to `prestashop.on('updateProduct', ...)` or similar events to detect product attribute changes.
    - Making AJAX calls to `controllers/front/ajax.php` to fetch updated dual prices.
    - Dynamically updating the displayed tax-included and tax-excluded prices on the product page and potentially listing pages.
    - Applying custom CSS or classes based on module settings.

### 4.5 CSS Stylesheets (`views/css/`)

- `bothprices/lib/searchTool/views/css/autocomplete.css`
  - **Scope**: Back-office.
  - **Description**: Styles for the autocomplete dropdown and search results within the `AdminBothpricesSearchController` interface.
- `bothprices/views/css/admin.css`
  - **Scope**: Back-office.
  - **Description**: General styling for the module’s configuration page in the PrestaShop Back Office, ensuring a consistent look with the admin panel.
- `bothprices/views/css/bothprices.css`
  - **Scope**: Front-office (Global).
  - **Description**: Contains the default CSS rules for displaying the dual prices on both product pages and listing pages. This includes basic formatting, positioning, and differentiation of the two price elements.
  - **Key CSS class selectors**: Developers can look for classes like `.bothprices_price_tax_incl`, `.bothprices_price_tax_excl`, `.bothprices_wrapper` to override.
- `bothprices/views/css/classic.css`
  - **Scope**: Front-office (Classic Theme specific).
  - **Description**: Contains additional or override CSS rules specifically designed to improve visual integration with the default PrestaShop Classic theme or themes based on it. This file is loaded conditionally based on the `BF_CLASSICCSS` setting.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `bothprices/views/templates/bothprices.tpl`
    - **Hook**: Likely rendered in hooks like `displayProductPriceBlock`, `displayProductListReviews`, `displayProductPriceBlock`, `displayProductPriceBlock`, `displayAfterProductThumbs` or similar, on both product and listing pages.
    - **Output**: This template is responsible for rendering the actual HTML structure of the dual price display (tax-included and tax-excluded prices) along with their labels. It receives price variables from the module’s PHP logic.
- **Admin templates (`views/templates/admin/`)**:
  - `bothprices/views/templates/admin/configure_shell.tpl`
    - **Hook**: Rendered within the module’s `getContent()` method for the main configuration page.
    - **Output**: This acts as a wrapper or shell for the module’s configuration form, potentially including tabs, headers, and footers for the admin interface.
  - `bothprices/views/templates/selectedProducts.tpl`
    - **Hook**: Used by `AdminBothpricesSearchController`.
    - **Output**: Renders the list of products that have been selected for the visibility rules, typically in a table or list format within the admin search interface.
- **Front-office templates (`views/templates/front/`)**:
  - `bothprices/views/templates/bothprices-product-page.tpl`
    - **Hook**: Likely rendered on the product page, possibly within `displayProductPriceBlock` or similar.
    - **Output**: A specific template for the product page’s dual price display, potentially with more detailed information or different layout compared to listing pages.
- **Library templates (`lib/searchTool/views/scripts.tpl`)**:
  - `bothprices/lib/searchTool/views/scripts.tpl`
    - **Hook**: Likely included in the `AdminBothpricesSearchController` view.
    - **Output**: Contains JavaScript initialization scripts or configuration variables for the autocomplete search tool.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module primarily uses PrestaShop’s `ps_configuration` table to store its settings. Configuration keys include: `mypresta_updates`, `update_`, `updatev_`, `BOTH_HIDE_PL_CSS`, `BOTH_HIDE_P_CSS`, `BF_PP`, `BF_PL`, `bp_visibility_rule`, `bp_visibility_products`, `bp_visibility_cat`, `BF_SHOW_TYPES`, `BF_PLC`, `BF_PPC`, `BP_FORCE_HIDE`, `BP_PP_TPERCENT_TEXL`, `BP_PP_TPERCENT`, `BP_PL_TPERCENT_TEXL`, `BP_PL_TPERCENT`, `BOTH_HIDE_PL`, `BOTH_HIDE_P`, `BF_OWNCSS`, `BF_CLASSICCSS`, `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`, `BP_TIN`, `BP_TIN_L`, `BP_TEX`, `BP_TEX_L`, `BP_TINL`, `BP_TINL_L`, `BP_TEXL`, `BP_TEXL_L`, `BP_O_TIN`, `BP_O_TIN_L`, `BP_O_TEX`.
  - It does not appear to create any custom SQL tables.
- **Registered Hooks Table**:

| Hook Name | Scope | Execution Timing | Technical Purpose |
| --- | --- | --- | --- |
| `ActionFrontControllerSetMedia` | Front-Office | Before controller output, after media initialization. | Injects module’s CSS and JS assets into the front-office. |
| `ActionAdminGroupsControllerSaveAfter` | Back-Office | After an admin saves a customer group. | Potentially used to clear cache or re-evaluate visibility rules related to customer groups. |
| `ActionAdminControllerSetMedia` | Back-Office | Before admin controller output, after media initialization. | Injects module’s CSS and JS assets into the back-office (e.g., for configuration page, search controller). |
| `updateproduct` | Back-Office | After a product is updated. | Clears relevant caches, re-evaluates product-specific price data. |
| `ActionProductDelete` | Back-Office | After a product is deleted. | Cleans up any module-specific data related to the deleted product (e.g., from `bp_visibility_products`). |
| `displayUpdateProduct` | Back-Office | On product edit page. | Potentially injects custom fields or information into the product edit form. |
| `actionProductUpdate` | Back-Office | After a product is updated. | Similar to `updateproduct`, ensures module’s internal data reflects product changes. |
| `displayHeader` | Front-Office | In the `<head>` section of every front-office page. | Injects module’s CSS and JS for global availability, or renders a small snippet. |
| `displayCategoryUpdate` | Back-Office | On category edit page. | Potentially injects custom fields or information into the category edit form. |
| `ActionCategoryUpdate` | Back-Office | After a category is updated. | Clears relevant caches, re-evaluates category-specific price data. |
| `actionProductAdd` | Back-Office | After a new product is added. | Initializes module-specific data for the new product. |
| `actionObjectSpecificPriceUpdateAfter` | Back-Office | After a specific price (discount) is updated. | Ensures dynamic price calculations reflect new specific prices. |
| `categoryUpdate` | Back-Office | After a category is updated. | Alias or duplicate of `ActionCategoryUpdate`. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Show two prices - tax included / excluded” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any technical issues or questions you may have regarding the module’s functionality.
