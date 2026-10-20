---
title: "Back office ajax product search - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Back office ajax product search PrestaShop module by MyPresta.eu."
sidebar:
  label: "Back office ajax product search - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Back office ajax product search Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/back-office-ajax-product-search.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/back-office-ajax-product-search/)
>
> ---


# Back office ajax product search

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and are usually available on any modern hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This module is designed to be highly efficient and largely “set it and forget it.” It integrates seamlessly into your back office without requiring complex configurations.

When you click “Configure” after installation, you will typically find a simple interface, often with no specific settings to adjust. The module’s core functionality (AJAX product search with autocomplete) is enabled by default upon installation.

- **What this screen does:** This is the main configuration area for the module. However, for “Back office ajax product search,” its primary function is to confirm the module is installed and active.
- **Effect of changing settings:** Since there are no specific user-configurable settings exposed on this screen, the module will operate with its default, optimized behavior.
- **Recommended value:** No specific actions are usually required here. The module is designed to work out-of-the-box.
- **Merchant scenario / example:** After installation, simply navigate to any back office page. You should notice that when you start typing in a product search field, suggestions appear instantly, and clicking on them takes you directly to the product edit page.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | (No specific settings) | N/A | The module automatically enhances the back office product search with AJAX autocomplete functionality upon installation. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve installed the module, but the search bar doesn’t seem to be working differently.**
A:

1. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” in the top right. Sometimes, PrestaShop’s cache needs to be cleared for new module assets (like JavaScript and CSS) to load correctly.
2. **Browser Cache:** Try clearing your browser’s cache or testing in an incognito/private browsing window.
3. **Module Status:** Ensure the module is enabled in **Modules > Module Manager**.
4. **Theme Compatibility:** While rare for back office modules, a heavily customized admin theme might interfere. If the issue persists, contact MyPresta.eu support.

**Q: Will this module slow down my back office?**
A: No, quite the opposite. By using AJAX, the module performs searches in the background without full page reloads, which is inherently faster and more efficient than traditional search methods. It’s designed to improve performance, not hinder it.

**Q: Does this module affect my front-office search for customers?**
A: No, this module is strictly for the PrestaShop back office. It has no impact on your customer-facing store or its search functionality.

**Q: Can I configure the number of search results shown?**
A: This module is designed for simplicity and out-of-the-box functionality. It typically does not offer configurable options for the number of results. The default behavior is usually optimized for a good user experience.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The `Back office ajax product search` module (boproductfinder) is a lightweight PrestaShop module primarily focused on enhancing the user experience within the back office. It achieves its functionality by injecting custom JavaScript and CSS assets into the back office header, leveraging PrestaShop’s hook system. The core logic resides in client-side JavaScript, which intercepts user input in specific search fields and performs AJAX requests to PrestaShop’s built-in product search endpoints, then displays the results using an autocomplete UI. It does not introduce new database tables or complex server-side logic beyond what PrestaShop already provides for product search.

### 4.2 Controllers (`controllers/`)

This module does not introduce any custom front-office or back-office controllers. It relies on existing PrestaShop controllers for handling product search queries (e.g., `AdminProductsController`’s AJAX methods).

### 4.3 Core Classes & Models (`classes/`)

This module does not introduce any custom PHP classes or `ObjectModel` definitions. Its functionality is primarily client-side.

### 4.4 JavaScript Assets (`views/js/`)

- **`boproductfinder/views/autocomplete.js`**
  - **Scope**: Back-office.
  - **Description**: This script likely implements or integrates a generic autocomplete library. It provides the core functionality for displaying suggestions as the user types in a text input field. It handles the UI rendering of the suggestion list, keyboard navigation within the list, and selection of items. It’s a foundational component for the module’s interactive search.
- **`boproductfinder/views/boproductfinder.js`**
  - **Scope**: Back-office.
  - **Description**: This is the main script for the module.
  - **Event Listeners**: It likely binds to `keyup` or `input` events on specific product search input fields within the PrestaShop back office (e.g., `input[name="product_search"]` or similar selectors).
  - **AJAX Calls**: When a user types, this script triggers AJAX requests to PrestaShop’s internal product search API (e.g., `admin-ajax.php` or a specific admin controller’s AJAX action for product search). It sends the search query and potentially other parameters (e.g., `id_lang`).
  - **DOM Manipulation**: It receives the JSON response from the server (containing product IDs, names, and potentially links) and uses the `autocomplete.js` (or similar logic) to display these results in a dropdown list below the search field.
  - **Navigation**: When a product suggestion is clicked or selected, this script constructs the URL to the product’s edit page (e.g., `admin/index.php?controller=AdminProducts&id_product=X&updateproduct&token=Y`) and redirects the browser to that page.

### 4.5 CSS Stylesheets (`views/css/`)

- **`boproductfinder/views/autocomplete.css`**
  - **Scope**: Back-office admin form styling.
  - **Description**: This stylesheet provides the visual styling for the autocomplete suggestion list.
  - **Main UI components and containers it styles**:
    - The dropdown container for search results.
    - Individual list items within the suggestions.
    - Highlighting for the currently hovered or selected suggestion.
    - Potentially loading indicators or “no results” messages.
  - **Key CSS class selectors developers can override**: Developers can inspect the generated HTML for classes like `.autocomplete-suggestions`, `.autocomplete-suggestion`, `.autocomplete-selected` to customize the appearance in their admin theme.

### 4.6 Smarty Template Structure (`views/templates/`)

This module does not contain any custom Smarty template files (`.tpl`). Its functionality is injected directly via JavaScript and CSS assets loaded through hooks.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: This module does not create any custom database tables. It relies on PrestaShop’s existing `ps_product`, `ps_product_lang`, and related tables for product data. Configuration is stored in `ps_configuration` if any settings were present, but for this module, it’s typically minimal or non-existent.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayBackOfficeHeader` | Executed in the `<head>` section of every back office page. | Used to include the module’s CSS and JavaScript files (`autocomplete.css`, `autocomplete.js`, `boproductfinder.js`) to ensure they are loaded on all admin pages where the search functionality might be needed. |
| `actionAdminControllerSetMedia` | Executed when an Admin Controller is setting its media assets. | An alternative or complementary hook to `displayBackOfficeHeader` for adding CSS and JS files, ensuring compatibility across different PrestaShop versions and back office themes. It ensures the module’s assets are properly registered and loaded. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Back office ajax product search” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality or compatibility.
