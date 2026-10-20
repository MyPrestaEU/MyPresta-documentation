---
title: "Back office menu manager - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Back office menu manager PrestaShop module by MyPresta.eu."
sidebar:
  label: "Back office menu manager - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Back office menu manager Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/back-office-menu-manager.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/back-office-menu-manager/)
>
> ---


# Back office menu manager

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” will take you to the main configuration screen for the “Back office menu manager” module.

This screen typically contains standard module settings, which might include:

- **Enable/Disable Module:**

  - **What this setting does:** This is a master switch to activate or deactivate the module’s functionality.
  - **Effect of changing this setting:**
    - *When enabled:* The module’s features, including the new menu management options, will be active in your Back Office.
    - *When disabled:* The module will stop affecting your Back Office menu, and the default PrestaShop menu behavior will resume.
  - **Recommended value:** **YES** (Enabled) to use the module.
  - **Merchant scenario / example:** If you’re testing the module or temporarily want to revert to the default PrestaShop menu, you can disable it here.
- **Reset Module Settings:**

  - **What this setting does:** This option allows you to revert all module-specific settings and potentially any custom menu configurations back to their default state.
  - **Effect of changing this setting:**
    - *When clicked:* All your custom menu arrangements and module preferences will be erased, and the module will behave as if it was just installed for the first time.
  - **Recommended value:** Use with caution. Only click if you want to completely restart your menu configuration.
  - **Merchant scenario / example:** If you’ve made many changes and want to start fresh, or if you encounter an unexpected issue and want to rule out configuration problems, this can be a useful troubleshooting step.

### 2.2 Dedicated Admin Screens & Controller Views

This module introduces a new, dedicated section in your PrestaShop Back Office to manage the menu tabs.

#### Screen Name & Menu Location: AdminMenuTabsController

- **Menu Location:** After installing the module, you will find a new menu item, typically under **Advanced Parameters** or a similar administrative section, named something like **“Menu Manager”** or **“Back Office Menu”**. Clicking this will take you to the `AdminMenuTabsController` screen.
- **Available Actions & Settings:**
  This screen provides a comprehensive grid (table) view of all the menu tabs currently available in your PrestaShop Back Office. For each menu tab, you will typically see:

  - **ID:** The unique identifier for the menu tab.
  - **Name:** The display name of the menu tab (e.g., “Orders,” “Products,” “Customers”).
  - **Parent Tab:** Which main menu item this tab belongs to (e.g., “Orders” is a parent of “Orders,” “Invoices,” “Credit Slips”).
  - **Position:** The numerical order of the tab within its parent group.
  - **Active/Inactive Switch:** A toggle to enable or disable the visibility of the menu tab.
  - **Edit/Delete Actions:** Buttons to modify the details of a specific tab or remove it (use delete with extreme caution, as it might remove core functionality).

  **Key functionalities you can perform here:**

  - **Reorder Menu Items:** You can usually drag and drop rows in the grid or manually change the ‘Position’ value to reorder how menu items appear.
  - **Hide/Show Menu Items:** Use the active/inactive switch to hide menu items you don’t use or want to restrict from certain staff roles (if combined with PrestaShop’s native permissions).
  - **Edit Menu Item Details:** You might be able to change the display name of a menu item, its icon, or its parent association (though changing parent associations for core tabs is generally not recommended without advanced knowledge).
  - **Add New Menu Items:** While less common for this specific module (which focuses on managing *existing* tabs), some advanced versions might allow adding custom menu links.
- **Effect of changes:**

  - **Hiding a tab:** The tab will immediately disappear from your Back Office menu for all users (unless specific permission overrides are in place).
  - **Reordering tabs:** The order of menu items will change instantly in the Back Office navigation.
  - **Editing a tab name:** The name displayed in the Back Office menu will update.
- **Recommended workflow for daily store management:**

  1. **Initial Setup:** Go through all your main menu items and their sub-items. Decide which ones your team uses regularly, rarely, or never.
  2. **Declutter:** For rarely or never-used items, use the “Active/Inactive” switch to hide them. This simplifies the menu significantly.
  3. **Prioritize:** Reorder frequently accessed items to be at the top of their respective sections. For example, if you spend most of your time on “Orders,” make sure “Orders” is the first sub-item under the “Orders” main menu.
  4. **Review Regularly:** As your store operations evolve or new modules are installed (which often add their own menu items), revisit this screen to keep your menu optimized.

#### Screen Name & Menu Location: index.php (adminmenu/controllers/admin/index.php)

This file, `index.php` within an admin controller directory, typically serves as a placeholder or an entry point for the controller’s functionality, rather than a standalone screen with configurable options. In PrestaShop, the actual logic and display for an admin controller are handled by the main class (e.g., `AdminMenuTabsController.php`).

Therefore, you won’t directly interact with an “index.php” screen. Its presence is part of the module’s internal structure, ensuring the `AdminMenuTabsController` functions correctly. All your interactions will be through the `AdminMenuTabsController` interface described above.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable/Disable Module | Enabled | Activates/deactivates the module’s menu management features. |
| Module Configuration | Reset Module Settings | N/A (Action) | Resets all module settings and menu configurations to default. Use with caution. |
| AdminMenuTabsController | Tab Name (e.g., “Orders”) | Original PrestaShop Name | Displays the name of the menu item. Can be edited. |
| AdminMenuTabsController | Parent Tab | Original PrestaShop Parent | Shows the main menu category for this item. |
| AdminMenuTabsController | Position | Varies | Controls the display order of the menu item within its parent. Can be changed by drag-and-drop or direct input. |
| AdminMenuTabsController | Active/Inactive Switch | Active | Toggles the visibility of the menu item in the Back Office. |
| AdminMenuTabsController | Edit/Delete Actions | N/A (Action) | Allows modification of tab details or removal (delete with caution). |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve hidden a menu item, but it’s still showing up for some users. Why?**
A: This module manages the *visibility* and *order* of menu items. PrestaShop’s native user permissions (under **Advanced Parameters > Team > Profiles** and **Permissions**) determine *who can access what*. If a user profile has explicit permission to a tab, they might still see it even if you’ve marked it as inactive in this module. Always check both this module’s settings and PrestaShop’s permissions.

**Q: I made changes, but the menu hasn’t updated. What should I do?**
A:

1. **Clear PrestaShop Cache:** Go to **Advanced Parameters > Performance**. Click “Clear cache” in the top right corner. This is often necessary for Back Office changes to take effect.
2. **Refresh Browser:** Sometimes a hard refresh of your browser (Ctrl+F5 or Cmd+Shift+R) is needed to clear local browser cache.
3. **Check Module Status:** Ensure the “Back office menu manager” module is still enabled in **Modules > Module Manager**.

**Q: Can I add entirely new custom links to the Back Office menu with this module?**
A: This module primarily focuses on managing *existing* PrestaShop menu tabs. While some advanced versions might offer custom link creation, its core purpose is to enable the management of the default PrestaShop menu structure. If you need to add complex custom links, you might require a more advanced module or custom development.

**Q: I accidentally deleted a core PrestaShop menu item. How do I get it back?**
A: Deleting core menu items is generally not recommended. If you’ve done so, the safest way to restore it is to:

1. **Disable and Re-enable the module:** Go to **Modules > Module Manager**, find “Back office menu manager,” disable it, and then re-enable it. This often triggers a re-initialization of default menu entries.
2. **Reset Module Settings:** If the above doesn’t work, go to the module’s configuration page and use the “Reset Module Settings” option. Be aware this will erase ALL your custom menu configurations.
3. **Restore from Backup:** As a last resort, if critical menu items are missing, you may need to restore your database from a backup taken *before* the deletion.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a technical overview for developers and webmasters working with the “Back office menu manager” module.

### 4.1 Architecture Overview

The “Back office menu manager” module primarily extends PrestaShop’s core Back Office functionality by overriding specific helper classes to re-introduce menu management capabilities. It leverages PrestaShop’s MVC pattern, with a dedicated Admin Controller (`AdminMenuTabsController`) to provide the user interface for managing menu tabs. The module interacts with the `ps_tab` database table, which stores information about Back Office menu items. The key architectural decision is the use of overrides to modify core PrestaShop behavior without directly altering core files, ensuring better compatibility and upgrade paths.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:
  This module does not contain any front-office controllers as its functionality is exclusively for the PrestaShop Back Office.
- **Back-Office Admin Controllers**:

  - `adminmenu/controllers/admin/AdminMenuTabs.php`

    - **Class name & parent class**: `AdminMenuTabsController` extends `ModuleAdminController`.
    - **Tab name and managed entity**: This controller manages the `Tab` entity (representing Back Office menu items). It creates a dedicated menu entry in the Back Office for “Menu Manager”.
    - **Responsibility**: This is the primary controller for the module’s UI. It handles the display of the list of all Back Office tabs, allowing administrators to view, edit, enable/disable, and reorder them. It typically uses `HelperList` for the grid display and `HelperForm` for any edit forms. It processes POST requests for saving changes (e.g., position updates, status toggles).
  - `adminmenu/controllers/admin/index.php`

    - **Responsibility**: This file is a standard placeholder within PrestaShop’s controller structure. It typically contains a simple `die('No direct script access allowed');` statement to prevent direct access to the directory and ensure that requests are routed through PrestaShop’s dispatcher. It does not contain any functional logic for the module itself.

### 4.3 Core Classes & Models (`classes/`)

The module uses overrides to modify core PrestaShop behavior.

- `adminmenu/override/classes/helper/HelperList.php`

  - **Class name & parent class**: `HelperList` (overrides the core `HelperList` class).
  - **What it does**: This override likely modifies the behavior of `HelperList` specifically when rendering the list of `Tab` entities in the Back Office. This is crucial for re-enabling features like drag-and-drop reordering or specific column displays that were removed from the default `HelperList` implementation for `Tab` in newer PrestaShop versions. It might inject custom actions or modify how data is fetched or displayed for menu tabs.
- `adminmenu/override/classes/helper/index.php`

  - **Responsibility**: Similar to `controllers/admin/index.php`, this is a placeholder file to prevent direct directory listing or access.
- `adminmenu/override/classes/index.php`

  - **Responsibility**: Another placeholder file to prevent direct directory listing or access.

### 4.4 JavaScript Assets (`views/js/`)

The provided inventory indicates no custom JavaScript files within the module. This suggests that the menu management functionality, including features like drag-and-drop reordering, is either handled by:

1. PrestaShop’s native `HelperList` JavaScript (which the module’s override might re-enable or configure).
2. Server-side processing for position updates.
3. Minimal inline JS generated by the `HelperList` or `HelperForm` classes.

Developers should inspect the generated HTML and network requests on the `AdminMenuTabsController` page to understand the exact JS implementation for interactive elements.

### 4.5 CSS Stylesheets (`views/css/`)

The provided inventory indicates no custom CSS files within the module. This implies that the module relies entirely on PrestaShop’s default Back Office styling. Any custom styling for the menu manager interface would either be:

1. Injected inline via Smarty templates or PHP.
2. Leveraging existing PrestaShop CSS classes.

### 4.6 Smarty Template Structure (`views/templates/`)

The provided inventory indicates no custom Smarty template files (`.tpl`) within the module. This is a strong indicator that the module primarily relies on PrestaShop’s default `HelperList` and `HelperForm` templates for rendering its Back Office interface.

The `AdminMenuTabsController` would instantiate `HelperList` and `HelperForm` objects, passing them configuration arrays, and these helpers would then render the UI using PrestaShop’s core templates (e.g., `_partials/helpers/list_action_enable.tpl`, `helpers/list/list_content.tpl`, `helpers/form/form.tpl`).

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  This module primarily interacts with the existing PrestaShop core table:

  - `ps_tab`: This table stores all Back Office menu entries, including their names, parent IDs, positions, and active status. The module’s `AdminMenuTabsController` and `HelperList` override directly read from and write to this table to manage the menu.
  - `ps_configuration`: Standard PrestaShop configuration table. The module’s main configuration settings (e.g., enable/disable status) would be stored here (e.g., `PS_ADMINMENU_MANAGER_ENABLED`).
- **Registered Hooks Table**:
  Based on the module’s description and functionality, it does not explicitly register any front-office or back-office display hooks (`displayHeader`, `actionValidateOrder`, etc.) in the traditional sense. Its functionality is achieved through:

  1. **Admin Controller Registration**: The module registers `AdminMenuTabsController` as a new Back Office tab, making it accessible via the Back Office menu.
  2. **Class Overrides**: The core mechanism relies on overriding `classes/helper/HelperList.php` to modify how menu tabs are managed and displayed in the Back Office. This isn’t a “hook” but a direct modification of core behavior.

  Therefore, a table of registered hooks is not applicable in the typical sense for this module. Its impact is on the internal workings of the Back Office menu rendering.

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the “Back office menu manager” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
