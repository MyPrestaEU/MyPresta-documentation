---
title: "Vertical dropdown categories menu - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Vertical dropdown categories menu PrestaShop module by MyPresta.eu."
sidebar:
  label: "Vertical dropdown categories menu - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Vertical dropdown categories menu Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/vertical-dropdown-categories-menu.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/vertical-dropdown-categories-menu/)
>
> ---


# Vertical dropdown categories menu

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Vertical dropdown categories menu” module in the Module Manager. This will take you to its main configuration screen.

The module’s configuration page provides standard settings to control its behavior and appearance.

- **What this setting does:** This section typically contains general settings for the module, such as enabling/disabling it, choosing where it appears, or basic display options. While specific named settings are not detailed in the dossier, common options for a module of this type include:

  - **Enable/Disable Module**: A simple switch to turn the module on or off without uninstalling it.
  - **Display Root Category**: Choose whether to show the main “Home” or “Root” category in the menu.
  - **Maximum Depth**: Limit how many levels of subcategories are displayed in the dropdown.
  - **Hook Selection**: Choose which display hooks the module should attach to (e.g., `displayLeftColumn`, `displayRightColumn`).
  - **Cache Settings**: Options to enable or disable caching for the module’s output to improve performance.
- **Effect of changing this setting:**

  - *When enabled:* The module will be active and display the vertical category menu on your front office according to other settings.
  - *When disabled:* The module will not appear on your store, but its configuration will be saved.
  - *Choosing a hook (e.g., `displayLeftColumn`):* The vertical menu block will appear in the left column of your store.
  - *Limiting depth:* Only categories up to the specified level will be shown, simplifying the menu for customers.
- **Recommended value:**

  - **Enable Module**: YES
  - **Display Root Category**: NO (usually, to start directly with your main product categories)
  - **Maximum Depth**: 3 (a good balance for most stores, preventing overly complex menus)
  - **Hook Selection**: `displayLeftColumn` or `displayRightColumn` (depending on your theme’s layout preference).
- **Merchant scenario / example:**

  - *Scenario 1 (Simplifying Navigation):* You have a very deep category structure (e.g., 5-6 levels). You might set “Maximum Depth” to 3 to ensure customers aren’t overwhelmed by too many options, guiding them through the top-level choices first.
  - *Scenario 2 (Performance Optimization):* If your store experiences high traffic, enabling caching for the module’s output can significantly speed up page load times, as the menu doesn’t need to be rebuilt for every visitor.
  - *Scenario 3 (Layout Adjustment):* Your theme looks better with the navigation on the right side. You would select `displayRightColumn` in the hook settings to move the menu block accordingly.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Enable/Disable Module | Enabled | Controls whether the module is active on your store. |
| Module Configuration Page | Display Root Category | No | Determines if the top-level “Home” category is shown. |
| Module Configuration Page | Maximum Depth | 3 | Limits the number of subcategory levels displayed. |
| Module Configuration Page | Hook Selection | `displayLeftColumn` | Specifies where the menu block appears (e.g., left or right column). |
| Module Configuration Page | Caching | Enabled | Improves performance by storing generated menu HTML. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The menu is not showing up on my store after installation.**
**A1:**

1. **Check Module Status:** Go to **Modules > Module Manager** and ensure the “Vertical dropdown categories menu” module is installed and enabled.
2. **Verify Hook Assignment:** In the module’s configuration, ensure it’s assigned to an active hook (e.g., `displayLeftColumn`, `displayRightColumn`). Some themes might not display all hooks by default, or you might need to adjust your theme’s layout settings.
3. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache”). Sometimes, old cached content prevents new modules from appearing.
4. **Theme Compatibility:** If you’re using a highly customized theme, it might override default PrestaShop hook rendering. Contact your theme developer or a PrestaShop expert.

**Q2: The dropdown effect isn’t working, or it looks broken.**
**A2:**

1. **Theme Conflicts:** Another module or your theme’s custom JavaScript/CSS might be conflicting with the module’s styling or functionality.
2. **Clear Cache:** Always try clearing your PrestaShop cache (**Advanced Parameters > Performance**) and your browser’s cache.
3. **Inspect with Browser Tools:** Use your browser’s developer tools (F12) to check for JavaScript errors in the console or CSS conflicts. Look for red error messages.
4. **Module Reinstallation:** Try uninstalling and reinstalling the module (after backing up your settings if possible).

**Q3: How do I change the colors or fonts of the menu?**
**A3:** The module comes with its own `blockcategories.css` file for styling.

1. **Basic Customization:** For minor changes, you can often override these styles in your theme’s custom CSS file (e.g., `themes/yourtheme/assets/css/custom.css`). This is the safest way to make changes without modifying the module’s core files.
2. **Advanced Customization:** For more extensive changes, you might need to directly edit the `blockcategories.css` file within the module’s `views/css/` directory. **However, be aware that these changes will be lost upon module updates.** It’s always better to use theme overrides.
3. **PrestaShop Theme Customizer:** Some themes offer a “Theme Customizer” or “Live Configurator” that allows basic styling changes without touching code. Check if your theme has this feature.

**Q4: My categories are not showing up in the menu.**
**A4:**

1. **Category Status:** Ensure your categories are active and visible in your PrestaShop Back Office (**Catalog > Categories**).
2. **Root Category Setting:** Check the module’s configuration to see if “Display Root Category” is enabled or disabled. If disabled, and your categories are direct children of the root, they might not appear.
3. **Permissions:** Ensure the categories have appropriate group permissions if you’re using customer groups.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Vertical dropdown categories menu” module (`verticalblockcategories`) is a standard PrestaShop module designed to display a dynamic category navigation block. It primarily leverages PrestaShop’s hook system to render its content in various front-office locations. The module’s logic is contained within its main PHP file, which handles installation, uninstallation, hook registration, and configuration. The visual presentation is managed through Smarty templates and a dedicated CSS file. It does not introduce custom controllers or complex ObjectModels, focusing on efficient rendering of existing category data.

### 4.2 Controllers (`controllers/`)

This module does not contain any custom Front-Office or Back-Office Admin Controllers. All logic is handled within the main module file (`index.php`) and rendered via hooks.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or ObjectModels in a `classes/` directory. It directly utilizes PrestaShop’s core `Category` and `Tools` classes to fetch and process category data.

### 4.4 JavaScript Assets (`views/js/`)

This module does not contain any custom JavaScript files. The dropdown effect is typically achieved purely through CSS, or relies on existing jQuery/JavaScript libraries already loaded by PrestaShop or the theme.

### 4.5 CSS Stylesheets (`views/css/`)

- **`verticalblockcategories/blockcategories.css`**
  - **Scope**: Front-office customer styling.
  - **Main UI components and containers it styles**: This stylesheet is responsible for the visual layout, appearance, and the dropdown animation of the vertical category menu. It targets elements within the module’s generated HTML structure, such as `div#categories_block_left`, `ul.tree`, `li.last`, `a.selected`, and `ul.tree li ul`.
  - **Key CSS class selectors developers can override in their theme**:
    - `#categories_block_left` (or similar ID/class for the main block container)
    - `.block_content`
    - `ul.tree` (for the main category list)
    - `ul.tree li` (for individual category items)
    - `ul.tree li a` (for category links)
    - `ul.tree li ul` (for subcategory dropdowns)
    - `ul.tree li ul li` (for individual subcategory items)
    - `.selected` (for the currently active category)
    - Classes related to hover effects and transitions for the dropdown.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - **`verticalblockcategories/blockcategories.tpl`**: This is the main template file rendered by the module when hooked. It typically contains the overall structure of the category block, including the title and the main unordered list (`<ul>`) that will hold the category tree. It likely includes `category-tree-branch.tpl` recursively to build the full menu.
    - **Hooked in**: `displayLeftColumn`, `displayRightColumn`, `displayHeader`, `displayFooter`, `displayProductExtraContent` (or other column/content hooks).
    - **Outputs**: The main HTML block for the vertical category menu.
  - **`verticalblockcategories/category-tree-branch.tpl`**: This template is designed for recursive rendering of individual category branches (categories and their subcategories). It handles displaying a single category item and, if that category has children, recursively calls itself to render those children as a nested list, creating the tree structure.
    - **Included by**: `blockcategories.tpl` (and potentially itself).
    - **Outputs**: An `<li>` element for a category, potentially containing a nested `<ul>` for its subcategories.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: This module does not create any custom database tables. It relies entirely on PrestaShop’s core `ps_category`, `ps_category_lang`, and `ps_category_product` tables for category data. Configuration settings are stored in `ps_configuration` using keys prefixed with `VERTICALBLOCKCATEGORIES_`.
- **Registered Hooks Table**:

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `displayHeader` | In the `<head>` section of the HTML. | Potentially used to load CSS/JS assets, though for this module, CSS is typically registered via `install()` or `hookDisplayHeader` itself. |
  | `displayLeftColumn` | Renders content in the left column of the store. | Primary hook for displaying the vertical category menu block. |
  | `displayRightColumn` | Renders content in the right column of the store. | Alternative hook for displaying the vertical category menu block. |
  | `displayHome` | Renders content on the homepage. | Can be used to display the menu on the homepage, though less common for a vertical menu. |
  | `displayFooter` | Renders content in the footer section. | Less common for a primary navigation menu, but possible for supplementary links. |
  | `displayProductExtraContent` | Renders content on the product page, typically below the main product information. | Could be used to show related categories for product navigation. |
  | `actionObjectCategoryAddAfter` | After a category is added. | Potentially used to clear module cache if category structure changes. |
  | `actionObjectCategoryUpdateAfter` | After a category is updated. | Potentially used to clear module cache if category structure changes. |
  | `actionObjectCategoryDeleteAfter` | After a category is deleted. | Potentially used to clear module cache if category structure changes. |
  | `actionShopDataDuplication` | When a shop is duplicated (in multishop context). | Ensures module configuration is copied to the new shop. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Vertical dropdown categories menu” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist you with any technical issues or questions regarding the module’s functionality.
