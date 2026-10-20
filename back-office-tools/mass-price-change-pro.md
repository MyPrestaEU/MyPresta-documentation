---
title: "Mass price change pro - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Mass price change pro PrestaShop module by MyPresta.eu."
sidebar:
  label: "Mass price change pro - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Mass price change pro Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/mass-price-change-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/mass-price-change-pro/)
>
> ---


# Mass price change pro

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.0.0 - 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for general PrestaShop operation and are sufficient for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The “Mass price change pro” module provides a comprehensive interface within the PrestaShop Back Office to define and execute your price changes. All settings are accessed via the main module configuration page.

### 2.1 Module Configuration Page (Back Office > Modules > Module Manager > Mass price change pro > Configure)

Upon entering the module’s configuration page, you’ll find a series of tabs or sections designed to guide you through the process of defining your price change operation.

#### **Main Tabs / Sections:**

The module’s configuration is typically organized into several key sections, often presented as tabs or distinct blocks on the main page. While the exact labels might vary slightly between versions, the core functionality remains consistent:

1. **What to do (WTD):** Define the type of price change.
2. **Target Products:** Select which products will be affected.
3. **Constraints:** Add additional conditions for targeting.
4. **Rules:** Define specific pricing rules.
5. **Preview:** See the impact before applying.
6. **History:** Review past operations.
7. **Scheduler:** Schedule future price changes.
8. **CSV Import/Export:** Manage prices via CSV.
9. **Cron Setup:** Configure automated tasks.

Let’s go through each section in detail:

#### **4.1.1 What to do (WTD)**

This section is where you define the core action of your price change.

- **What this setting does:** Determines how product prices will be modified. You choose between increasing, decreasing, or setting a new price, and whether this applies to the base price, specific price, or impact on combinations.
- **Effect of changing this setting:**
  - *Increase by percentage:* Adds a percentage of the current price to the product.
  - *Decrease by percentage:* Subtracts a percentage of the current price from the product.
  - *Increase by fixed amount:* Adds a specific monetary value to the product price.
  - *Decrease by fixed amount:* Subtracts a specific monetary value from the product price.
  - *Set new price to:* Overwrites the current price with a new, specified value.
  - *Apply to base price:* Modifies the main product price.
  - *Apply to specific price:* Modifies prices set via “Specific Prices” rules (e.g., for groups, countries, or quantity).
  - *Apply to impact on combinations:* Modifies the price adjustment for product combinations (attributes).
- **Recommended value:** Depends entirely on your business goal. Start with a clear objective (e.g., “increase all prices by 5%”) before selecting.
- **Merchant scenario / example:**
  - *Scenario 1 (Inflation):* “I need to increase all my product prices by 3% due to rising supplier costs.” -> Select “Increase by percentage,” enter “3,” and choose “Apply to base price.”
  - *Scenario 2 (Clearance Sale):* “I want to reduce the price of all products in the ‘Summer Collection’ category by $5.” -> Select “Decrease by fixed amount,” enter “5,” and choose “Apply to base price.”

#### **4.1.2 Target Products**

This is where you precisely select *which* products will be affected by the price change.

- **What this setting does:** Allows you to filter products based on various criteria like categories, manufacturers, suppliers, specific product IDs, or even products with no specific price.
- **Effect of changing this setting:**
  - *Selecting Categories:* Only products within the chosen categories will be considered.
  - *Selecting Manufacturers/Suppliers:* Only products from these brands/sources will be affected.
  - *Entering Product IDs:* Only the exact products you list will be targeted.
  - *Filtering by “Products with no specific price”:* Useful for ensuring you don’t accidentally override existing specific price rules.
- **Recommended value:** Be as specific as possible to avoid unintended changes. Use multiple filters if necessary.
- **Merchant scenario / example:**
  - *Scenario 1 (Brand Update):* “My main supplier, ‘Fashionista Co.’, has increased their prices. I need to update all products from this manufacturer.” -> Select “Manufacturer,” then choose “Fashionista Co.”
  - *Scenario 2 (Seasonal Stock):* “I want to put all products in the ‘Winter Apparel’ category on sale.” -> Select “Category,” then choose “Winter Apparel.”

#### **4.1.3 Constraints**

This section allows you to add even more specific conditions to your product targeting.

- **What this setting does:** Provides advanced filtering options, such as targeting products within a certain price range, products with specific features or attributes, or products that are currently in stock.
- **Effect of changing this setting:**
  - *Price Range:* Only products whose current price falls within the specified minimum and maximum will be included.
  - *Features/Attributes:* Target products that have a particular feature (e.g., “Color: Red”) or attribute (e.g., “Size: XL”).
  - *In Stock Only:* Ensures only products currently available for purchase are affected.
- **Recommended value:** Use these to refine your target list further, especially for complex promotions or inventory-based adjustments.
- **Merchant scenario / example:**
  - *Scenario 1 (Premium Product Sale):* “I want to offer a discount on high-value items. Reduce prices by 10% for all products over $100 in the ‘Electronics’ category.” -> In “Target Products,” select “Electronics.” In “Constraints,” set “Price Range” from “$100” to “Max.”
  - *Scenario 2 (Clearance of Specific Stock):* “I need to clear out all ‘Blue’ colored shirts that are currently in stock.” -> In “Target Products,” select “Shirts.” In “Constraints,” select “Attribute: Color > Blue” and “In Stock Only.”

#### **4.1.4 Rules**

This section allows you to define more complex pricing logic, potentially overriding or adding to the general “What to do” action.

- **What this setting does:** Enables you to create conditional price adjustments. For example, “If a product is in Category A, increase its price by 5%, but if it’s in Category B, decrease it by 10%.”
- **Effect of changing this setting:** Allows for highly nuanced pricing strategies where different groups of products receive different adjustments within a single operation.
- **Recommended value:** Use this when a single, uniform price change isn’t sufficient for all targeted products.
- **Merchant scenario / example:**
  - *Scenario (Tiered Discount):* “For products in the ‘Accessories’ category, if their price is between $10 and $50, decrease by 5%. If their price is over $50, decrease by 10%.” -> You would set up multiple rules here, each with its own price range and adjustment.

#### **4.1.5 Preview**

Before committing any changes, this crucial section allows you to review the proposed modifications.

- **What this setting does:** Displays a list of products that will be affected, showing their current price and what their new price will be after the operation.
- **Effect of changing this setting:** This is a read-only section. It provides a safety net, allowing you to catch any errors in your targeting or rules before they are applied to your live store.
- **Recommended value:** **ALWAYS** review the preview carefully before proceeding with the actual price change.
- **Merchant scenario / example:**
  - *Scenario (Double-checking):* “I’ve set up a 10% discount for all ‘Summer Dresses’. The preview shows a dress that I know should not be discounted. I can go back to ‘Target Products’ or ‘Constraints’ to refine my selection.”

#### **4.1.6 History**

This section keeps a record of all past price change operations.

- **What this setting does:** Shows a log of who performed which price change, when it was done, and what type of operation it was.
- **Effect of changing this setting:** This is a read-only log. It’s invaluable for auditing, troubleshooting, and understanding past pricing decisions.
- **Recommended value:** Regularly check the history, especially if multiple people manage the store, to ensure all changes are intentional and tracked.
- **Merchant scenario / example:**
  - *Scenario (Auditing):* “A customer reported an incorrect price. I can check the history to see if a recent mass price change might have caused it and who initiated the change.”

#### **4.1.7 Scheduler**

Plan your price changes to execute automatically at a future date and time.

- **What this setting does:** Allows you to define a price change operation and set it to run automatically at a specified date and time. You can also set it to revert prices after a certain period, perfect for temporary sales.
- **Effect of changing this setting:**
  - *Scheduled Execution:* The price change will be applied without manual intervention at the chosen time.
  - *Revert Prices:* Products will return to their original prices (or a different specified price) after the sale period ends.
- **Recommended value:** Essential for managing promotions, seasonal sales, or any price changes that need to go live outside of business hours.
- **Merchant scenario / example:**
  - *Scenario (Black Friday Sale):* “I want to apply a 20% discount to all products at 00:00 on Black Friday and revert to original prices at 23:59 on Cyber Monday.” -> Set up the discount operation, schedule it for Black Friday, and add a revert schedule for Cyber Monday.

#### **4.1.8 CSV Import/Export**

Manage your product prices using CSV files for advanced control or external data manipulation.

- **What this setting does:**
  - *Export:* Allows you to export a list of products (based on your targeting criteria) with their current prices into a CSV file.
  - *Import:* Allows you to upload a CSV file containing product IDs and new prices, applying these changes to your store.
- **Effect of changing this setting:**
  - *Export:* Provides a spreadsheet of your targeted products and their prices, which can be edited externally.
  - *Import:* Overwrites or updates prices for products listed in the CSV, offering a powerful way to manage large, complex price lists.
- **Recommended value:** Use export for detailed analysis or when you need to make very specific, non-formulaic price adjustments that are easier to manage in a spreadsheet. Use import when you have a pre-defined list of new prices from a supplier or an external system.
- **Merchant scenario / example:**
  - *Scenario (Supplier Price List):* “My supplier sent me a new price list for 500 products. Instead of manually updating each, I can export my current product list, match it with the supplier’s, adjust the prices in the CSV, and then import it back.”

#### **4.1.9 Cron Setup**

Configure the module’s cron job for automated tasks, especially for scheduled price changes.

- **What this setting does:** Provides the necessary command or URL to set up a cron job on your server. This cron job is essential for the “Scheduler” feature to work, as it periodically checks for and executes scheduled price changes.
- **Effect of changing this setting:**
  - *Correct Cron Setup:* Ensures that your scheduled price changes run automatically at the specified times. Without a properly configured cron job, scheduled tasks will not execute.
- **Recommended value:** Follow the instructions provided by the module to set up the cron job on your hosting server. Typically, this involves adding a line to your server’s crontab. The module usually provides the exact command.
- **Merchant scenario / example:**
  - *Scenario (Automated Sales):* “I’ve scheduled a flash sale for next week. To ensure it starts exactly on time, I need to make sure the cron job is correctly set up and running every 5-15 minutes.” -> Copy the provided cron command and add it to your server’s cron manager.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **What to do** | Operation Type (Increase/Decrease/Set) | N/A (depends on goal) | Defines how prices are changed (e.g., +5%, -$10, set to $25). |
|  | Value (Percentage/Fixed) | N/A (depends on goal) | The amount or percentage of the price adjustment. |
|  | Apply to (Base/Specific/Combinations) | Base price | Determines which price type is affected. |
| **Target Products** | Categories | Select specific | Filters products by category. |
|  | Manufacturers | Select specific | Filters products by brand. |
|  | Suppliers | Select specific | Filters products by supplier. |
|  | Product IDs | Enter list | Targets specific products by ID. |
|  | Products with no specific price | Yes/No | Excludes products with existing specific prices. |
| **Constraints** | Price Range (Min/Max) | N/A (optional) | Filters products within a price bracket. |
|  | Features / Attributes | Select specific | Filters products by their features or attributes. |
|  | In Stock Only | Yes/No | Only affects products currently in stock. |
| **Rules** | Add Rule | N/A (optional) | Defines conditional price adjustments based on criteria. |
| **Preview** | (Read-only table) | N/A | Shows current vs. new prices for affected products. **Always review!** |
| **History** | (Read-only log) | N/A | Records all past price change operations. |
| **Scheduler** | Schedule Operation | N/A (optional) | Sets a future date/time for price changes to run automatically. |
|  | Revert Prices | N/A (optional) | Schedules a price reversion after a set period. |
| **CSV Import/Export** | Export Products | N/A (optional) | Downloads targeted product data for external editing. |
|  | Import Prices | N/A (optional) | Uploads a CSV to apply new prices to products. |
| **Cron Setup** | Cron Command | Copy from module | Essential for automated scheduled tasks. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My prices didn’t change after I applied the operation. What went wrong?**
A1:

- **Check the History tab:** Verify that the operation was recorded and completed successfully.
- **Clear Cache:** PrestaShop uses caching. Go to **Advanced Parameters > Performance** and click “Clear cache.” Your browser might also be caching old data, so try clearing your browser cache or viewing the store in incognito mode.
- **Check Targeting:** Revisit your “Target Products” and “Constraints” settings. Did you accidentally exclude the products you intended to change?
- **Specific Prices:** If you were trying to change base prices but products have specific prices, the specific prices might be overriding them. Check if your operation was set to affect “Specific Prices” or “Base Price.”

**Q2: My scheduled price change didn’t run at the specified time.**
A2:

- **Cron Job:** The most common reason for this is an incorrectly set up or non-running cron job. Go to the **Cron Setup** tab in the module configuration. Ensure the provided cron command is correctly added to your server’s crontab and is running at the recommended frequency (e.g., every 5-15 minutes). If you’re unsure how to do this, contact your hosting provider or a webmaster.
- **Module Enabled:** Ensure the “Mass price change pro” module is still enabled in your Module Manager.

**Q3: I accidentally changed the wrong prices. Can I revert the changes?**
A3:

- **History Tab:** The module’s “History” tab often provides an option to revert a previous operation. Look for a “Revert” or “Undo” button next to the specific operation you want to reverse.
- **Database Backup:** If a revert option isn’t available or doesn’t work as expected, this highlights the importance of having a recent database backup. You would need to restore your database to a point before the erroneous price change. **Always back up before major operations!**

**Q4: The module isn’t displaying correctly or is causing errors after installation.**
A4:

- **PrestaShop Version:** Ensure you downloaded and installed the correct module version for your specific PrestaShop installation (e.g., PrestaShop 8.x, 1.7.x).
- **PHP Compatibility:** Verify your server’s PHP version is within the module’s supported range (PHP 5.6 - 8.5).
- **Theme Conflicts:** Sometimes, custom themes can interfere. Temporarily switch to the default PrestaShop theme to see if the issue resolves. If it does, your theme might require adjustments.
- **Error Logs:** Check your PrestaShop debug mode (if enabled) or your server’s PHP error logs for specific error messages. These can provide clues for developers.

**Q5: How do I translate the module’s text into other languages?**
A5:

- In your PrestaShop Back Office, navigate to **International > Translations**.
- Select “Installed modules translations,” choose your theme, and then select “Mass price change pro” from the module dropdown.
- You can then translate all the module’s strings into your desired languages.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters working with the “Mass price change pro” module.

### 4.1 Architecture Overview

The “Mass price change pro” module follows a standard PrestaShop module architecture, primarily leveraging the `Module` class for its core functionality and `ModuleFrontController` for specific front-office tasks like cron execution. The module heavily relies on its `index.php` (main module file) for back-office configuration and processing, using Smarty templates for rendering various configuration sections. It integrates custom JavaScript for enhanced UI elements like product targeting and autocomplete, and CSS for styling. While it doesn’t explicitly define `ObjectModel` classes in the provided inventory, it likely interacts directly with PrestaShop’s core `Product`, `SpecificPrice`, and `Configuration` tables.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `controllers/front/cron.php`
  - **Class Name:** `MassPriceProCronModuleFrontController` (likely, based on file naming convention)
  - **Parent Class:** `ModuleFrontController`
  - **Responsibility:** This controller is designed to be called by a server-side cron job. Its primary role is to execute scheduled price change operations defined within the module’s back-office configuration. It processes tasks like applying scheduled discounts, reverting prices, or running other automated price adjustments. It typically returns a simple success/failure message or logs its activity.
- `controllers/front/index.php`
  - **Class Name:** `MassPriceProIndexModuleFrontController` (likely)
  - **Parent Class:** `ModuleFrontController`
  - **Responsibility:** This controller might serve as a general entry point for front-office module actions that don’t fit into a specific category, or it could be a placeholder. Given the module’s nature, it’s less likely to have direct customer-facing functionality and more likely to handle background AJAX requests or specific data retrieval if needed by front-end scripts.

#### Back-Office Admin Controllers

The module does not appear to use dedicated `AdminController` files based on the provided inventory. All back-office configuration and processing are likely handled directly within the `getContent()` method of the main `masspricepro/index.php` file.

### 4.3 Core Classes & Models (`classes/`)

Based on the provided inventory, there are no custom classes or `ObjectModel` definitions within a `classes/` directory. This suggests that the module directly interacts with PrestaShop’s core `Product`, `SpecificPrice`, `Category`, `Manufacturer`, `Supplier` `Configuration` and potentially other related `ObjectModel` classes and their associated database tables. Price change logic is likely encapsulated within methods of the main `MassPricePro` class (in `index.php`).

### 4.4 JavaScript Assets (`views/js/`)

- `masspricepro/lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Likely both Front-office (if used for product search) and Back-office (for product targeting).
  - **Details:** Provides generic autocomplete functionality. It listens for user input in text fields, sends AJAX requests to a backend endpoint (possibly `controllers/front/index.php` or a dedicated AJAX handler in the main module file), and displays suggestions in a dropdown list.
- `masspricepro/views/js/jquery.autocomplete.js`
  - **Scope:** Likely Back-office.
  - **Details:** A jQuery-based autocomplete plugin. This might be a specific implementation or a dependency for the module’s product selection interfaces in the back office, such as when targeting products by name or ID. It handles UI rendering of suggestions and selection events.
- `masspricepro/views/js/mpp_pro.js`
  - **Scope:** Back-office.
  - **Details:** This is likely the main JavaScript file for the module’s back-office configuration. It would contain:
    - Event listeners for form submissions, tab changes, button clicks (e.g., “Apply Changes,” “Preview,” “Add Rule”).
    - AJAX calls to the `getContent()` method or a front controller for data processing (e.g., generating previews, saving settings, executing price changes).
    - DOM manipulation to dynamically show/hide sections, update preview tables, or manage rule inputs.
    - Validation logic for form fields.
- `masspricepro/views/js/mpp_target_products.js`
  - **Scope:** Back-office.
  - **Details:** Specifically handles the logic for the “Target Products” section of the module. This would include:
    - Managing selection of categories, manufacturers, suppliers (e.g., using multiselect dropdowns or tree views).
    - Handling input for product IDs, potentially with validation.
    - Interacting with the autocomplete scripts to allow administrators to search for and select products.
    - Dynamically updating the list of selected target products.

### 4.5 CSS Stylesheets (`views/css/`)

- `masspricepro/lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Both Front-office and Back-office.
  - **Details:** Provides styling for the autocomplete suggestion dropdowns and input fields, ensuring they are visually consistent and user-friendly.
- `masspricepro/views/css/mpp_admin.css`
  - **Scope:** Back-office admin form styling.
  - **Details:** This is the primary stylesheet for the module’s configuration interface in the PrestaShop Back Office. It styles:
    - The layout of the configuration tabs/sections.
    - Form elements (inputs, buttons, selects, checkboxes).
    - Tables (e.g., for history, preview).
    - Any custom UI components specific to the module.
    - Key CSS class selectors developers can override: `.mpp-container`, `.mpp-tab-content`, `.mpp-form-group`, `.mpp-table`, etc.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Admin templates (`views/templates/admin/`)

These templates are rendered within the `getContent()` method of the main module file to build the back-office configuration interface.

- `constraints.tpl`: Renders the section for defining additional constraints (e.g., price range, features, attributes).
- `cron_setup.tpl`: Displays instructions and the command for setting up the server cron job.
- `csv.tpl`: Renders the interface for CSV import functionality.
- `csv_export_target.tpl`: Renders the interface for CSV export functionality, specifically for targeted products.
- `history.tpl`: Displays the table and details of past price change operations.
- `mpp_operation_block.tpl`: Likely a reusable block for defining a single price change operation (increase/decrease/set).
- `mpp_target_block.tpl`: Likely a reusable block for defining product targeting criteria.
- `mpp_target_products_full.tpl`: Renders the complete interface for selecting target products, possibly including autocomplete fields and selected product lists.
- `preview.tpl`: Displays the table showing the current and proposed new prices before execution.
- `rules.tpl`: Renders the interface for defining conditional pricing rules.
- `scheduler.tpl`: Displays the form for scheduling future price changes and reverts.
- `target_products.tpl`: A more concise or alternative template for product targeting, potentially used within other sections.
- `wtd.tpl`: Renders the “What to do” section, where the main type of price adjustment is selected.

#### Hook templates (`views/templates/hook/`)

- `form.tpl`: This template is likely used to render the main configuration form or a specific part of it when the module is hooked into a generic display hook (though the module primarily uses `getContent()` for its main configuration). Given the module’s purpose, it’s unlikely to display anything directly on the front office via hooks like `displayHeader` or `displayFooter`, but rather uses these hooks for loading assets or internal processing.

### 4.7 Database Schema & Hooks Map

#### Database Tables

The module does not create custom SQL tables based on the provided inventory. It primarily relies on PrestaShop’s core tables:

- `ps_product`: For base product prices.
- `ps_product_shop`: For shop-specific product prices.
- `ps_specific_price`: For specific price rules.
- `ps_product_attribute`, `ps_product_attribute_shop`: For combination prices and impacts.
- `ps_category_product`, `ps_manufacturer`, `ps_supplier`: For product targeting.
- `ps_configuration`: For storing module settings and configuration values (e.g., `MPP_LAST_OPERATION_DATE`, `MPP_CRON_TOKEN`, `MPP_SCHEDULED_TASKS`).

#### Registered Hooks Table

The module likely registers hooks to integrate with PrestaShop’s lifecycle and display assets.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | To load module-specific CSS (`mpp_admin.css` if needed for some reason, though unlikely for front-office) and JavaScript (`autocomplete.js`, `jquery.autocomplete.js` if used for front-end search). |
| `actionModuleInstall` | During module installation. | To perform initial setup, create configuration entries, and register other hooks. |
| `actionModuleUninstall` | During module uninstallation. | To clean up configuration entries and unregister hooks. |
| `actionAdminControllerSetMedia` | When an admin controller is loaded. | To load Back-office specific CSS (`mpp_admin.css`) and JavaScript (`mpp_pro.js`, `mpp_target_products.js`, `autocomplete.js`) for the module’s configuration page. |
| `actionScheduler` (or similar custom hook) | Triggered by the module’s cron job. | To execute scheduled price changes and revert operations. This is a custom internal hook or method called by the `cron.php` controller. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Mass price change pro” module, please refer to your customer account at MyPresta.eu. You can download the newest versions from your order history and access support resources directly through the platform.
