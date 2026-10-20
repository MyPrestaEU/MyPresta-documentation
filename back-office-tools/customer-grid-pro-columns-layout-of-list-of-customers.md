---
title: "Customer Grid Pro - columns & layout of list of customers - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Customer Grid Pro - columns & layout of list of customers PrestaShop module by MyPresta.eu."
sidebar:
  label: "Customer Grid Pro - columns & layout of list of customers"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Customer Grid Pro - columns & layout of list of customers Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/customer-grid-pro-columns-layout-of-list-of-customers.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/customer-grid-pro-columns-layout-of-list-of-customers/)
>
> ---


# Customer Grid Pro - columns & layout of list of customers

## 1. Requirements & Compatibility
- **Supported PrestaShop Versions**: PrestaShop 9.x, 8.x, 1.7.8.x, 1.7.7.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)
After installing the module, click "Configure" to access its settings. This page allows you to select which columns appear in your customer list and in what order.

The configuration page will display a list of all available columns for your customer grid. These include standard PrestaShop columns and new ones added by the module (like phone, address, order statistics).

**How to use the configuration interface:**

1.  **Available Columns List:** On the left side, you'll see a list of all columns that *can* be displayed.
2.  **Active Columns List:** On the right side, you'll see a list of columns that are currently *active* and will be shown in your customer list.
3.  **Adding a Column:** To add a column to your customer list, simply drag it from the "Available Columns" list on the left and drop it into the "Active Columns" list on the right.
4.  **Removing a Column:** To remove a column from your customer list, drag it from the "Active Columns" list on the right and drop it back into the "Available Columns" list on the left.
5.  **Reordering Columns:** Within the "Active Columns" list, you can drag and drop columns up or down to change their display order in your customer grid. The column at the top of the list will appear first (leftmost) in your customer list.
6.  **Save Button:** After making any changes (adding, removing, or reordering columns), remember to click the **"Save"** button at the bottom of the page to apply your new configuration.

**List of available columns and their purpose:**

| Column Name (Example) | What this setting does | Effect of changing this setting | Recommended value | Merchant scenario / example |
|---|---|---|---|---|
| **ID** | Displays the unique identification number for each customer. | *When active:* Shows the customer's ID. *When inactive:* Hides the ID column. | Active | Useful for quickly referencing customers by their internal ID, especially when dealing with support tickets. |
| **Social Title** | Displays the customer's chosen title (e.g., Mr., Ms.). | *When active:* Shows the social title. *When inactive:* Hides the social title column. | Active (optional) | Good for formal communication or if your business requires specific salutations. |
| **First Name** | Displays the customer's first name. | *When active:* Shows the first name. *When inactive:* Hides the first name column. | Active | Essential for identifying customers. |
| **Last Name** | Displays the customer's last name. | *When active:* Shows the last name. *When inactive:* Hides the last name column. | Active | Essential for identifying customers. |
| **Email Address** | Displays the customer's email address. | *When active:* Shows the email address. *When inactive:* Hides the email column. | Active | Crucial for contacting customers and often used as a primary identifier. |
| **Age** | Displays the customer's age (if birthdate is provided). | *When active:* Shows the customer's calculated age. *When inactive:* Hides the age column. | Active (optional) | Useful for marketing segmentation or age-restricted products. |
| **Registration Date** | Displays the date the customer registered their account. | *When active:* Shows the registration date. *When inactive:* Hides the registration date column. | Active | Helps track customer acquisition and identify new vs. old customers. |
| **Last Visit** | Displays the date of the customer's last login/visit. | *When active:* Shows the last visit date. *When inactive:* Hides the last visit column. | Active (optional) | Useful for identifying active vs. inactive customers for re-engagement campaigns. |
| **Total Orders** | Displays the total number of orders placed by the customer. | *When active:* Shows a count of all orders. *When inactive:* Hides this column. | Active | Excellent for identifying frequent buyers or customers with multiple purchases. |
| **Total Spent** | Displays the total monetary value spent by the customer across all orders. | *When active:* Shows the sum of all order totals. *When inactive:* Hides this column. | Active | Critical for identifying high-value customers (VIPs) and for B2B account management. |
| **Phone Number** | Displays the customer's primary phone number (from their default address). | *When active:* Shows the phone number. *When inactive:* Hides this column. | Active | Essential for direct contact, especially for delivery issues or urgent inquiries. |
| **Mobile Phone** | Displays the customer's mobile phone number (from their default address). | *When active:* Shows the mobile phone number. *When inactive:* Hides this column. | Active | Provides an alternative contact method, often preferred for quick communication. |
| **Address 1** | Displays the first line of the customer's default address. | *When active:* Shows the address line. *When inactive:* Hides this column. | Active (optional) | Useful for quick reference of location without opening the full address. |
| **Address 2** | Displays the second line of the customer's default address. | *When active:* Shows the address line. *When inactive:* Hides this column. | Active (optional) | Provides additional address detail. |
| **Postcode** | Displays the postcode of the customer's default address. | *When active:* Shows the postcode. *When inactive:* Hides this column. | Active (optional) | Useful for geographical segmentation or delivery planning. |
| **City** | Displays the city of the customer's default address. | *When active:* Shows the city. *When inactive:* Hides this column. | Active (optional) | Useful for geographical segmentation or local marketing. |
| **State** | Displays the state/province of the customer's default address. | *When active:* Shows the state/province. *When inactive:* Hides this column. | Active (optional) | Important for regional targeting and shipping. |
| **Country** | Displays the country of the customer's default address. | *When active:* Shows the country. *When inactive:* Hides this column. | Active (optional) | Essential for international stores and shipping logistics. |
| **Newsletter** | Indicates if the customer is subscribed to your newsletter. | *When active:* Shows a "Yes" or "No" indicator. *When inactive:* Hides this column. | Active | Helps identify marketing opportunities and manage email lists. |
| **Opt-in** | Indicates if the customer has opted in for partner offers. | *When active:* Shows a "Yes" or "No" indicator. *When inactive:* Hides this column. | Active (optional) | Useful for managing partner marketing efforts. |
| **Active** | Indicates if the customer account is currently active. | *When active:* Shows a "Yes" or "No" indicator. *When inactive:* Hides this column. | Active | Helps identify disabled accounts. |
| **Default Group** | Displays the customer's primary customer group. | *When active:* Shows the default group name. *When inactive:* Hides this column. | Active | Crucial for B2B stores or stores with tiered pricing/access. |
| **Shop Name** | Displays the shop name if using multi-store mode. | *When active:* Shows the shop name. *When inactive:* Hides this column. | Active (if multi-store) | Essential for multi-store environments to differentiate customers by shop. |
| **Outstanding Amount** | Displays any outstanding balance the customer owes (if applicable, e.g., for B2B credit). | *When active:* Shows the outstanding amount. *When inactive:* Hides this column. | Active (if applicable) | Important for B2B credit management. |
| **Allowed Backorder** | Indicates if the customer is allowed to place backorders. | *When active:* Shows "Yes" or "No". *When inactive:* Hides this column. | Active (if applicable) | Relevant for inventory management and specific customer agreements. |

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|---|
| Module Configuration Page | Drag & Drop Column Order | User-defined | Controls the visual order of columns in the Back Office customer list. |
| Module Configuration Page | Active Columns List | User-defined | Determines which columns are visible in the Back Office customer list. |
| Module Configuration Page | Available Columns List | User-defined | Lists all possible columns that can be added to the customer list. |
| Module Configuration Page | Save Button | Click after changes | Applies all column visibility and order changes to the customer grid. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I've configured the columns, but I don't see any changes in my customer list.**
A:
1.  **Did you click "Save"?** After making changes on the module configuration page, you must click the "Save" button.
2.  **Clear PrestaShop Cache:** Sometimes, PrestaShop's cache can prevent changes from appearing immediately. Go to **Advanced Parameters > Performance** and click "Clear cache" (or "Clear Smarty cache" in older versions).
3.  **Check Browser Cache:** Try clearing your browser's cache or opening the Back Office in an incognito/private browsing window.

**Q: Some columns I expect to see (like "Company Name" or "Outstanding Amount") are not available in the list.**
A:
1.  **Module Compatibility:** Ensure you have downloaded and installed the correct version of the module for your specific PrestaShop version.
2.  **PrestaShop Features:** Some columns (e.g., "Outstanding Amount") are only relevant if you have specific PrestaShop features enabled (like B2B mode) or other modules installed that provide this data. If the data doesn't exist in your store, the module might not be able to display it.

**Q: The drag-and-drop functionality isn't working on the configuration page.**
A:
1.  **Browser Compatibility:** Ensure you are using a modern web browser (Chrome, Firefox, Edge, Safari) and that JavaScript is enabled.
2.  **Conflicting Modules:** Rarely, another module or a custom theme modification might interfere with JavaScript. Try temporarily disabling other modules to see if the issue resolves. If it does, contact MyPresta.eu support.

**Q: Can I translate the new column names into other languages?**
A: Yes, PrestaShop's translation system should allow you to translate the module's strings.
1.  Go to **International > Translations**.
2.  Select "Installed modules translations".
3.  Choose your theme, your language, and then select "Customer Grid Pro".
4.  You should find the strings for the column names there to translate.

**Q: Will this module slow down my Back Office?**
A: The module is optimized to integrate with PrestaShop's core customer grid. While adding many complex columns (especially those requiring calculations like "Total Spent") might slightly increase load time compared to a barebones list, the impact is generally negligible on a well-configured server. The benefits in efficiency usually far outweigh any minor performance differences.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview
The `Customer Grid Pro` module primarily extends the functionality of the PrestaShop Back Office customer list. It achieves this by hooking into the `actionCustomerGridDefinitionModifier` and `actionCustomerGridDataModifier` hooks, which are part of PrestaShop's new grid system introduced in 1.7.x. This allows the module to dynamically add, remove, and reorder columns and their associated data without directly modifying core files. The configuration is managed via a standard `getContent()` method in the main module file, utilizing a custom JavaScript and CSS for the drag-and-drop interface.

### 4.2 Controllers (`controllers/`)
This module does not introduce any custom Front-Office or Back-Office controllers. All configuration is handled within the main module file's `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)
This module does not define any custom classes or `ObjectModel` entities in a `classes/` directory. All logic is self-contained within the main `index.php` module file.

### 4.4 JavaScript Assets (`views/js/`)

-   **`mycustomergridpro/views/js/customer_grid_admin.js`**
    *   **Scope:** Back-office (specifically the module configuration page).
    *   **Purpose:** This script provides the drag-and-drop functionality for the column selection interface on the module's configuration page. It uses jQuery UI's `sortable` widget to enable reordering and moving items between the "Available Columns" and "Active Columns" lists.
    *   **Key Functionality:**
        *   Initializes two sortable lists: `#available_columns` and `#active_columns`.
        *   Configures `connectWith` to allow items to be moved between these two lists.
        *   Handles the `update` event for the sortable lists to potentially trigger saving or update hidden input fields (though the actual saving is handled by the form submission).
        *   Ensures that the order of elements in the `#active_columns` list is correctly submitted with the form.

### 4.5 CSS Stylesheets (`views/css/`)

-   **`mycustomergridpro/views/css/customer_grid_admin.css`**
    *   **Scope:** Back-office (specifically the module configuration page).
    *   **Purpose:** Provides styling for the drag-and-drop column selection interface.
    *   **Key Styling:**
        *   Styles for the column list containers (`#available_columns`, `#active_columns`).
        *   Styles for individual column items (`.column-item`).
        *   Visual cues for drag-and-drop operations (e.g., `ui-sortable-helper`, `ui-sortable-placeholder`).
        *   Ensures the two column lists are displayed side-by-side or in a clear layout for usability.

### 4.6 Smarty Template Structure (`views/templates/`)
This module does not use separate `.tpl` files for its configuration or front-office display. The entire configuration form HTML is generated directly within the `getContent()` method of the main `index.php` module file.

### 4.7 Database Schema & Hooks Map

-   **Database Tables**:
    *   This module does not create any custom SQL tables.
    *   It stores its configuration (the list of active columns and their order) in the `ps_configuration` table using keys like `MYCUSTOMERGRIDPRO_ACTIVE_COLUMNS`. This configuration is stored as a serialized array or JSON string.

-   **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
|---|---|---|
| `actionCustomerGridDefinitionModifier` | Executed when the customer grid definition is being built in the Back Office. | Allows the module to add new columns (e.g., phone, total orders, total spent, address fields) and remove existing ones from the grid definition. This hook receives the `GridDefinition` object. |
| `actionCustomerGridDataModifier` | Executed after the customer grid data has been fetched, but before it's rendered. | Allows the module to populate the data for the custom columns added via `actionCustomerGridDefinitionModifier`. This hook receives the `QueryResult` object, allowing modification of the data rows. |
| `displayBackOfficeHeader` | Executed in the `<head>` section of Back Office pages. | Used to include the module's custom CSS (`customer_grid_admin.css`) and JavaScript (`customer_grid_admin.js`) files on the module's configuration page, enabling the drag-and-drop interface. |

## 5. Official Support & Updates
For the latest updates, bug fixes, and official support for the "Customer Grid Pro - columns & layout of list of customers" module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist merchants and developers with any issues or questions related to the module's functionality and integration.
