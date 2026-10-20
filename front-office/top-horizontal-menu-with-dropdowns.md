---
title: "Top horizontal menu with dropdowns - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Top horizontal menu with dropdowns PrestaShop module by MyPresta.eu."
sidebar:
  label: "Top horizontal menu with dropdowns - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Top horizontal menu with dropdowns Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/top-horizontal-menu-with-dropdowns.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/top-horizontal-menu-with-dropdowns/)
>
> ---


# Top horizontal menu with dropdowns

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required by PrestaShop itself and should be available on any compatible hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” to access the module’s settings. This screen allows you to manage the items that appear in your top horizontal menu and configure the search bar.

The configuration page is divided into two main sections: **Menu Items** and **Search Bar**.

#### 2.1.1 Menu Items Management

This section allows you to define which items appear in your main navigation menu. You can add links to categories, CMS pages, manufacturers, suppliers, or custom URLs.

- **Adding a New Menu Item:**

  - **Label:** This is the text that will be displayed in your menu (e.g., “New Arrivals”, “Summer Collection”, “About Us”). You can enter different labels for each language your store supports.
    - *Effect of changing:* Directly changes the visible text of the menu item for customers.
    - *Recommended value:* Clear, concise, and descriptive text that accurately represents the link’s destination.
    - *Merchant scenario:* You want to add a link to your “Contact Us” page. You’d enter “Contact Us” here.
  - **Link:** This is the URL that the menu item will point to. You can select from a list of existing categories, CMS pages, manufacturers, or suppliers, or enter a custom URL.
    - *Effect of changing:* Determines where the customer is taken when they click on this menu item.
    - *Recommended value:* Always ensure the link is valid and points to the correct page. For internal pages, use the provided selection tools. For external links, ensure the full URL (e.g., `https://example.com/blog`) is entered.
    - *Merchant scenario:* You want to link to your “T-Shirts” category. You’d select “T-Shirts” from the categories dropdown. If you want to link to an external blog, you’d type the full blog URL.
  - **New window:** A toggle switch (Yes/No) that determines if the link opens in a new browser tab or window.
    - *When enabled (Yes):* The link will open in a new tab, keeping your store’s current page open in the original tab.
    - *When disabled (No):* The link will open in the same tab, navigating the customer away from the current page.
    - *Recommended value:* “Yes” for external links (e.g., a blog, social media profile) to keep customers on your store. “No” for internal links (categories, products, CMS pages) to maintain a natural browsing flow within your site.
    - *Merchant scenario:* You’re linking to your Facebook page. Set “New window” to “Yes” so customers can easily return to your store.
- **Managing Existing Menu Items:**

  - The module displays a list of your current menu items. You can drag and drop items to reorder them, which directly affects their display order in the front office.
  - You can click “Edit” to modify an existing item’s label, link, or new window setting.
  - You can click “Delete” to remove an item from the menu.
    - *Effect of changes:* Reordering, editing, or deleting items immediately updates the menu structure and appearance on your live store.
    - *Recommended workflow:* Regularly review your menu structure to ensure it’s logical and up-to-date. Prioritize important categories or promotions by placing them earlier in the menu.

#### 2.1.2 Search Bar Configuration

This section controls the visibility of the search bar within your top menu.

- **Search bar:** A toggle switch (Enabled/Disabled) to show or hide the search bar.
  - *When enabled (Enabled):* A search input field will appear within or near your top horizontal menu, allowing customers to quickly search for products.
  - *When disabled (Disabled):* The search bar will be hidden from the top menu area.
  - *Recommended value:* “Enabled”. A search bar is a crucial navigation tool for most e-commerce stores, especially those with a large product catalog. It significantly improves user experience.
  - *Merchant scenario:* You want customers to easily find products by typing keywords. Enable this setting. If your store is very small with only a few products, you might consider disabling it to save space, but this is generally not recommended.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | **Menu Items** |  |  |
|  | Label | N/A | Text displayed for the menu item. |
|  | Link | N/A | URL the menu item points to. |
|  | New window | No (for internal links), Yes (for external links) | Determines if the link opens in a new tab. |
|  | Reordering | N/A | Changes the display order of menu items. |
|  | Edit/Delete | N/A | Modifies or removes existing menu items. |
| Module Configuration Page | **Search bar** | Enabled | Shows/hides the search input field in the top menu. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My menu changes aren’t showing up on the front office.**
A: After making changes in the module configuration, you might need to clear your PrestaShop cache.
- Go to **Advanced Parameters > Performance**.
- Click the “Clear cache” button in the top right corner.
- Also, clear your browser’s cache (Ctrl+F5 or Cmd+R) to ensure you’re seeing the latest version of your site.

**Q2: The dropdowns look strange or don’t appear correctly with my custom theme.**
A: This module modifies the standard PrestaShop top menu. Custom themes often have their own specific CSS (styling) for the menu.
- **Solution:** The module includes its own CSS to enable the dropdowns. Your theme’s CSS might be overriding it or conflicting. You may need a web developer to inspect the CSS and adjust your theme’s styles or the module’s styles to ensure compatibility.
- **Temporary Check:** Try switching to the default PrestaShop theme (e.g., Classic) temporarily to see if the dropdowns work there. If they do, it confirms a theme-related CSS conflict.

**Q3: How do I translate my menu item labels into other languages?**
A: When you add or edit a menu item, you’ll see a language selector next to the “Label” field.
- Click the flag icon to switch to a different language.
- Enter the translated label for that specific language.
- Repeat for all languages your store supports.

**Q4: Can I have multiple levels of dropdowns (e.g., Category > Subcategory > Sub-subcategory)?**
A: The module enhances the standard PrestaShop menu, which typically supports one or two levels of dropdowns effectively. While technically possible to nest items, too many levels can become cumbersome for users.
- **Best Practice:** Aim for a maximum of two levels (main item > dropdown items). For deeper hierarchies, consider using category landing pages or faceted navigation on category pages rather than overly complex dropdown menus.

**Q5: The search bar is enabled, but it’s not showing up.**
A:
- First, ensure the “Search bar” setting in the module’s configuration is indeed “Enabled.”
- Second, check if your theme has a specific hook or styling for the search bar in the header. Some themes might place the search bar in a different location or require specific configuration within the theme itself.
- If the issue persists, clear your cache (as described in Q1).

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview of the “Top horizontal menu with dropdowns” module for developers and webmasters.

### 4.1 Architecture Overview

The `blocktopdropdownmenu` module is designed as a standard PrestaShop module, primarily extending the functionality of the core `blocktopmenu` module (or its equivalent in newer PS versions) by injecting custom JavaScript and CSS to enable dropdown behavior. It follows a classic PrestaShop MVC pattern for its configuration, using `getContent()` for the back-office form and registering hooks for front-office display. It does not introduce new database tables or complex `ObjectModel` structures, instead relying on `Configuration` values to store its settings and leveraging existing PrestaShop entities (Categories, CMS, etc.) for menu item links.

### 4.2 Controllers (`controllers/`)

This module does not introduce any custom Front-Office or Back-Office Admin Controllers. All configuration is handled within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

This module does not introduce any custom PHP classes or `ObjectModel` definitions in the `classes/` directory. All logic is contained within the main `blocktopdropdownmenu.php` file.

### 4.4 JavaScript Assets (`views/js/`)

The module relies heavily on JavaScript to create the dropdown menu functionality.

- `blocktopdropdownmenu/js/blocktopdropdownmenu.js`
  - **Scope:** Front-office.
  - **Responsibility:** This is the main initialization script for the dropdown menu. It likely contains the logic to apply the Superfish plugin (or a similar dropdown library) to the main navigation element. It binds event listeners for hover intents, handles menu item expansion/collapse, and ensures mobile responsiveness (e.g., converting hover to tap for touch devices or integrating with a hamburger menu). It might also contain logic for the search bar’s behavior if it’s dynamically loaded or toggled.
- `blocktopdropdownmenu/js/hoverIntent.js`
  - **Scope:** Front-office.
  - **Responsibility:** A jQuery plugin that attempts to determine the user’s intent to hover over an element. It helps prevent accidental triggering of dropdowns by introducing a delay and checking mouse movement, making the menu feel smoother and less “flickery.” This is typically a dependency for Superfish.
- `blocktopdropdownmenu/js/superfish-modified.js`
  - **Scope:** Front-office.
  - **Responsibility:** This is likely a modified version of the popular Superfish jQuery plugin, which is designed to create multi-level dropdown menus. It handles the core mechanics of showing and hiding sub-menus on hover, managing animations, and potentially adding accessibility features. The “modified” suffix suggests it might include custom adaptations for PrestaShop’s DOM structure or specific theme compatibility.

### 4.5 CSS Stylesheets (`views/css/`)

The module provides styling to visually present the dropdown menus.

- `blocktopdropdownmenu/css/blocktopdropdownmenu.css`
  - **Scope:** Front-office customer styling.
  - **Responsibility:** Contains custom CSS rules specific to this module, potentially overriding default theme styles or adding new styles for elements like the search bar, specific menu item states, or general layout adjustments for the dropdowns.
  - **Key CSS class selectors:** Developers should inspect this file for classes like `.sf-menu`, `.sf-menu li`, `.sf-menu li ul`, `.sf-menu li li`, etc., which are common Superfish selectors, as well as any custom classes introduced by the module.
- `blocktopdropdownmenu/css/superfish-modified.css`
  - **Scope:** Front-office customer styling.
  - **Responsibility:** Provides the base visual styling for the Superfish dropdown menu structure. This includes styles for menu item spacing, background colors, text colors, hover effects, dropdown arrow indicators, and the positioning of the dropdown panels. It’s crucial for the visual appearance of the multi-level menu.
  - **Key CSS class selectors:** Similar to `blocktopdropdownmenu.css`, this file will contain core Superfish selectors. Developers can override these in their theme’s `custom.css` or `theme.css` to match their brand’s aesthetic.

### 4.6 Smarty Template Structure (`views/templates/`)

- `blocktopdropdownmenu/blocktopdropdownmenu.tpl`
  - **Scope:** Hook template.
  - **Hook:** `displayTop` (and potentially `displayNav` if the theme structure allows).
  - **Responsibility:** This is the main front-office template responsible for rendering the HTML structure of the top horizontal menu, including the main menu items and their nested dropdowns. It iterates through the menu items configured in the back office and generates the `<ul><li>` structure required by the Superfish JavaScript. It also includes the logic for rendering the search bar if enabled.
- `blocktopdropdownmenu/views/templates/admin/advert.tpl`
  - **Scope:** Admin template.
  - **Responsibility:** Likely displays an advertisement or promotional message from MyPresta.eu within the module’s configuration page in the Back Office.
- `blocktopdropdownmenu/views/templates/admin/_configure/helpers/form/form.tpl`
  - **Scope:** Admin template.
  - **Responsibility:** This template is a standard PrestaShop helper template used to render the main configuration form for the module. It defines the structure and fields for managing menu items and the search bar setting, as configured in `getContent()`.
- `blocktopdropdownmenu/views/templates/admin/_configure/helpers/list/list_content.tpl`
  - **Scope:** Admin template.
  - **Responsibility:** This template is a standard PrestaShop helper template used to render the list of menu items within the configuration form, allowing for drag-and-drop reordering, editing, and deletion.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create any custom database tables.
  - Configuration settings (e.g., `MOD_blocktopdropdownmenu_ITEMS`, `MOD_blocktopdropdownmenu_SEARCH`) are stored in the `ps_configuration` table. `MOD_blocktopdropdownmenu_ITEMS` will store a serialized array or JSON string representing the menu structure.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Injects CSS and JavaScript assets (`blocktopdropdownmenu.js`, `hoverIntent.js`, `superfish-modified.js`, `blocktopdropdownmenu.css`, `superfish-modified.css`) required for the dropdown functionality. |
| `displayTop` | Typically in the main header area of the theme. | Renders the main HTML structure of the horizontal menu with dropdowns and the search bar. |
| `displayNav` | Often in the very top navigation bar (above `displayTop`). | May be used by some themes to display the menu, or for additional navigation elements. The module might register here for broader theme compatibility. |
| `actionObjectProductUpdateAfter` | After a product is updated. | Potentially used to clear module cache related to product links, ensuring menu items linking to products are up-to-date. |
| `actionObjectProductDeleteAfter` | After a product is deleted. | Potentially used to clear module cache or remove menu items linking to the deleted product. |
| `actionObjectManufacturerAddAfter` | After a manufacturer is added. | Potentially used to clear module cache related to manufacturer links. |
| `actionObjectManufacturerUpdateAfter` | After a manufacturer is updated. | Potentially used to clear module cache related to manufacturer links. |
| `actionObjectManufacturerDeleteAfter` | After a manufacturer is deleted. | Potentially used to clear module cache or remove menu items linking to the deleted manufacturer. |
| `actionObjectSupplierAddAfter` | After a supplier is added. | Potentially used to clear module cache related to supplier links. |
| `actionObjectSupplierUpdateAfter` | After a supplier is updated. | Potentially used to clear module cache related to supplier links. |
| `actionObjectSupplierDeleteAfter` | After a supplier is deleted. | Potentially used to clear module cache or remove menu items linking to the deleted supplier. |
| `actionObjectCmsAddAfter` | After a CMS page is added. | Potentially used to clear module cache related to CMS page links. |
| `actionObjectCmsUpdateAfter` | After a CMS page is updated. | Potentially used to clear module cache related to CMS page links. |
| `actionObjectCmsDeleteAfter` | After a CMS page is deleted. | Potentially used to clear module cache or remove menu items linking to the deleted CMS page. |
| `actionShopDataDuplication` | When a shop is duplicated (in multi-store context). | Ensures module configuration (menu items, search bar setting) is correctly duplicated for the new shop. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Top horizontal menu with dropdowns” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist merchants and developers with any issues or questions related to the module’s functionality and compatibility.
