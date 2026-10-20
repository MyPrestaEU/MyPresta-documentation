---
title: "Mass product combinations editor - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Mass product combinations editor PrestaShop module by MyPresta.eu."
sidebar:
  label: "Mass product combinations editor - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Mass product combinations editor Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/mass-product-combinations-editor.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/mass-product-combinations-editor/)
>
> ---


# Mass product combinations editor

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server requirements beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Mass product combinations editor)

Upon clicking “Configure” for the “Mass product combinations editor” module, you will be taken to a dedicated administration interface. This is where you will perform all your mass combination edits.

The main configuration page for this module acts as its primary interface. It does not have a traditional “settings form” with switches and input fields for the module itself, but rather it IS the tool for editing combinations.

Here’s a breakdown of what you’ll see and how to use it:

**Screen Name & Menu Location:**

- **Menu Path:** After installation, you will typically find a new menu item under **Catalog** or **Modules** (depending on your PrestaShop version and theme) or you can always access it via **Modules > Module Manager** and clicking “Configure” next to “Mass product combinations editor”.
- **Screen Title:** “Mass product combinations editor” or similar.

**Available Actions & Settings:**

The main interface will present you with a powerful grid or table that lists product combinations. The exact appearance may vary slightly between PrestaShop versions, but the core functionality remains consistent.

1. **Product Selection / Filtering:**

   - **What this does:** This area allows you to select which products’ combinations you want to edit. You might see a search bar, a product dropdown, or filters by category, manufacturer, etc.
   - **Effect of changing this setting:** By selecting a product or applying filters, the table below will populate with only the combinations belonging to the chosen products. This is crucial for narrowing down your focus.
   - **Recommended value:** Start by searching for a specific product or filtering by a category to get familiar with the interface.
   - **Merchant scenario / example:** You want to update the stock for all combinations of your “Summer T-Shirt” product. You would search for “Summer T-Shirt” and select it.
2. **Combination Listing Table:**

   - **What this does:** This is the core of the module. It displays a table where each row represents a unique product combination (e.g., “T-Shirt - Red - Small”). The columns represent editable fields like:
     - **Reference:** Internal product code for this specific combination.
     - **EAN13 / UPC:** Barcode numbers.
     - **Quantity:** Stock level for this combination.
     - **Impact on Price:** How this combination affects the base product price (e.g., +$5 for XL size).
     - **Wholesale Price:** The cost price of this combination.
     - **Weight:** How this combination affects the base product weight.
     - **Minimum Quantity:** The minimum number of this combination a customer must buy.
     - **Default Combination:** A checkbox to mark one combination as the default for the product.
     - **Image:** The image associated with this combination.
   - **Effect of changing this setting:** You can directly click into cells in this table and type new values. For example, changing the “Quantity” from 5 to 10 will update the stock level for that specific combination.
   - **Recommended value:** Carefully review each combination and its current values before making changes.
   - **Merchant scenario / example:** You just received a new shipment. You can go down the “Quantity” column and update the stock levels for all relevant combinations in seconds.
3. **Save Button:**

   - **What this does:** After making all your desired changes in the table, you **must** click a “Save” or “Apply Changes” button (usually found at the top or bottom of the table) to commit your modifications to the database.
   - **Effect of changing this setting:** Until you click save, your changes are only visible on the screen and are not live on your store. Clicking save applies all pending modifications.
   - **Recommended value:** Always save your work frequently, especially after making a batch of changes.
   - **Merchant scenario / example:** You’ve updated prices for 20 combinations. Click “Save” to make these new prices live on your product pages.

**Recommended workflow for daily store management:**

1. **Identify your task:** Do you need to update stock, change prices, or modify references?
2. **Navigate to the module:** Go to **Modules > Module Manager** and click “Configure” for “Mass product combinations editor”.
3. **Select products:** Use the search or filter options to load the combinations you need to work with.
4. **Make changes:** Directly edit the values in the table cells. You can often use keyboard shortcuts (like Tab) to move quickly between fields.
5. **Review:** Double-check your changes before saving.
6. **Save:** Click the “Save” button to apply all modifications.
7. **Clear Cache (if necessary):** In some cases, especially after major price or stock changes, it’s good practice to clear your PrestaShop cache (**Advanced Parameters > Performance**) to ensure changes are immediately visible on the front office.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Product Selection/Filter | (Varies by product) | Narrows down the combinations displayed for editing. |
| Module Configuration Page | Combination Listing Table (e.g., Quantity, Price Impact, Reference, EAN13) | (Varies by product) | Direct editing of combination attributes. Changes are applied to the selected combination. |
| Module Configuration Page | Save Button | Click after changes | Commits all on-screen modifications to the database, making them live on your store. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My changes aren’t showing up on the front office after I save!**
A: This is usually a caching issue. Go to **Advanced Parameters > Performance** in your PrestaShop Back Office and click “Clear cache” (or “Clear Smarty cache” / “Clear cache” depending on your version). Your changes should then appear.

**Q: The module is slow to load combinations for products with many variations.**
A: For products with hundreds or thousands of combinations, loading all data can take time. This is normal due to the amount of data being processed. Ensure your server meets PrestaShop’s recommended specifications. If it’s consistently very slow, check your server’s PHP memory limit and execution time settings (your hosting provider can help with this).

**Q: Can I undo changes made with this module?**
A: The module directly updates your database. There is no built-in “undo” button. This is why it’s crucial to **always have a recent backup of your store** before making mass changes. If you make a mistake, you would need to manually correct the values or restore from a backup.

**Q: I can’t find the module in the menu after installation.**
A: After installing, navigate to **Modules > Module Manager**. Search for “Mass product combinations editor” and click the “Configure” button next to it. This will always take you to the module’s interface. Depending on your PrestaShop version and theme, a direct menu link might appear under “Catalog” or “Modules” for quicker access.

**Q: Does this module work with custom themes?**
A: Yes, this module operates entirely within the PrestaShop Back Office. It does not output any front-office elements, so it should be fully compatible with any custom theme without conflicts.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Mass product combinations editor” module (`qce`) is primarily a Back-Office administration tool. It leverages PrestaShop’s `Module` class for its core functionality and uses a custom AJAX endpoint to handle the dynamic loading and saving of product combination data. The module’s interface is rendered via a Smarty template, with JavaScript handling user interactions and data submission. It directly interacts with PrestaShop’s core product and combination data structures without introducing new `ObjectModel` classes or database tables.

### 4.2 Controllers (`controllers/`)

This module does not use dedicated `ModuleFrontController` or `AdminController` classes in the `controllers/` directory. All Back-Office logic, including the AJAX endpoint, is handled directly within the main module file `qce/ajax_qce.php` via the `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

The module does not introduce any custom classes in a `classes/` directory. It directly utilizes PrestaShop’s core classes, such as `Product`, `Combination`, `Tools`, `Configuration`, etc., to retrieve and update data.

### 4.4 JavaScript Assets (`views/js/`)

- **`qce/views/admin/js/qce.js`**
  - **Scope:** Back-office (admin panel).
  - **Purpose:** This is the primary JavaScript file for the module’s interface. It handles:
    - **Product Selection:** Likely manages the dropdown or search input for selecting a product.
    - **AJAX Data Loading:** Sends AJAX requests to the module’s `getContent()` method (or a specific AJAX handler within it) to fetch combination data for the selected product.
    - **Table Rendering:** Dynamically populates the HTML table with combination data received from the server.
    - **In-place Editing:** Implements functionality for users to click on table cells and edit values directly (e.g., input fields appearing on click).
    - **Data Validation:** May include client-side validation for input fields (e.g., ensuring quantity is a number).
    - **AJAX Data Saving:** Gathers all modified combination data from the table and sends it via AJAX to the module’s `getContent()` method for processing and saving to the database.
    - **User Feedback:** Displays loading spinners, success messages, or error alerts.
    - **Event Listeners:** Binds listeners to elements like product selection dropdowns, input fields within the table, and the “Save” button.

### 4.5 CSS Stylesheets (`views/css/`)

- **`qce/lib/blue/style.css`**

  - **Scope:** Back-office (admin panel).
  - **Purpose:** This appears to be a third-party or generic stylesheet, possibly for a UI component or a specific styling theme used within the module’s interface. It likely defines general table styles, input field styles, or button aesthetics. Developers should inspect this file to understand its impact on the module’s visual presentation.
- **`qce/views/admin/css/qce.css`**

  - **Scope:** Back-office (admin panel).
  - **Purpose:** This is the module’s specific stylesheet. It contains custom CSS rules to style the combination editing table, product selection elements, and any other unique UI components within the module’s configuration page.
  - **Key CSS Class Selectors:** Developers looking to override or customize the module’s appearance should inspect this file for class names like `.qce-table`, `.qce-product-selector`, `.qce-input-field`, etc., and target them in their custom admin theme or by overriding the module’s CSS.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`qce/views/admin/qce.tpl`**
  - **Scope:** Admin template.
  - **Purpose:** This is the main Smarty template file responsible for rendering the entire “Mass product combinations editor” interface within the PrestaShop Back Office.
  - **Content:** It typically includes:
    - The HTML structure for the product selection/filtering area.
    - The placeholder (e.g., an empty `<table>` or `<div>`) where the combination data will be dynamically loaded and rendered by `qce.js`.
    - The “Save” button and any other action buttons.
    - Includes for the necessary JavaScript (`qce.js`) and CSS (`qce.css`, `style.css`) files.
    - Any initial messages or instructions for the merchant.
  - **Rendering:** This template is rendered by the `getContent()` method of the `ajax_qce.php` module file.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does **not** create any custom database tables.
  - It directly reads from and writes to PrestaShop’s core tables related to products and combinations, primarily:
    - `ps_product_attribute` (main combination data)
    - `ps_product_attribute_shop` (shop-specific combination data)
    - `ps_product_attribute_combination` (links attributes to combinations)
    - `ps_product` (for product information)
    - `ps_attribute`, `ps_attribute_lang`, `ps_attribute_group`, `ps_attribute_group_lang` (for attribute definitions)
    - `ps_image`, `ps_image_shop`, `ps_image_lang` (for combination images)
  - Configuration settings (if any were present beyond the main interface) would be stored in `ps_configuration`.
- **Registered Hooks Table**:
  The module does not explicitly register any front-office or back-office display hooks (`displayHeader`, `actionValidateOrder`, etc.) in a traditional sense. Its functionality is accessed directly via its configuration page in the Back Office. The module’s `install()` method would register itself as an admin module, making it accessible via the Modules Manager.

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Mass product combinations editor” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality.
