---
title: "Shipping delivery countdown timer - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Shipping delivery countdown timer PrestaShop module by MyPresta.eu."
sidebar:
  label: "Shipping delivery countdown timer - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Shipping delivery countdown timer Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/shipping-delivery-countdown-timer.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/shipping-delivery-countdown-timer/)
>
> ---


# Shipping delivery countdown timer

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen where you control all aspects of the Shipping delivery countdown timer.

#### General Settings

- **Enabled / Disabled (Switch)**
  - **What this setting does:** This is the master switch to turn the entire module on or off across your store.
  - **Effect of changing this setting:**
    - *When enabled:* The countdown timer will appear on your front office according to your other settings.
    - *When disabled:* The countdown timer will not be visible anywhere on your store.
  - **Recommended value:** **Enabled** (once you’ve configured it).
  - **Merchant scenario / example:** You’re setting up the module for the first time and want to configure it fully before making it live. You’d keep it “Disabled” until ready, then switch to “Enabled.”

#### Display & Design

- **Where you want to display timer? (Checkboxes)**

  - **What this setting does:** This determines the specific locations (hooks) in your PrestaShop theme where the countdown timer will be displayed.
  - **Effect of changing this setting:**
    - *Checking a box (e.g., `displayProductAdditionalInfo`):* The timer will appear in that specific area of your theme.
    - *Unchecking a box:* The timer will be removed from that specific area.
  - **Recommended value:** Start with `displayProductAdditionalInfo` or `displayFooterProduct` for product page visibility. You can experiment with others like `displayNav1` or `displayReassurance` based on your theme and desired impact.
  - **Merchant scenario / example:** You want the timer to be highly visible on product pages. You would check `displayProductAdditionalInfo` and `displayFooterProduct`. If you also want it in the header, you might check `displayNav1`.
  - **Available Options:**
    - `displayFooterProduct`
    - `displayReassurance`
    - `displayDeliveryTimer` (Custom hook for advanced theme integration)
    - `displayProductAdditionalInfo`
    - `displayNav1`
- **What design of the module you want to use? (Radio Buttons)**

  - **What this setting does:** Allows you to select a pre-designed visual style for your countdown timer. This includes color schemes and overall layout.
  - **Effect of changing this setting:** The appearance of the countdown timer on your front office will change instantly to the selected design.
  - **Recommended value:** Choose the design that best matches your store’s branding and theme colors.
  - **Merchant scenario / example:** Your store uses a lot of blue and white. You might select “Blue 400x48” or “Blue 200x100” to ensure the timer blends seamlessly with your site’s aesthetic.

#### Shipping Cut-off Times

- **Purchase breakpoint time (Time Picker)**
  - **What this setting does:** This is the daily cut-off time by which an order must be placed to qualify for the current day’s shipping.
  - **Effect of changing this setting:**
    - *Setting to 14:00:* If a customer orders before 2 PM, the timer counts down to 2 PM. If they order after 2 PM, the timer will show the countdown to the next available shipping day’s cut-off time.
  - **Recommended value:** Set this to your actual daily shipping cut-off time (e.g., 15:00 for 3 PM).
  - **Merchant scenario / example:** Your warehouse team processes all orders received by 4 PM for same-day dispatch. You would set this to `16:00`.

#### Daily Messages & Availability

- **Show on Sunday / Monday / Tuesday / Wednesday / Thursday / Friday / Saturday (Checkboxes)**

  - **What this setting does:** These checkboxes control whether the countdown timer is active and displayed on specific days of the week.
  - **Effect of changing this setting:**
    - *Checking a day (e.g., “Show on Sunday”):* The timer will be active and display on Sundays.
    - *Unchecking a day:* The timer will not display on that specific day, and the message for that day will not be shown.
  - **Recommended value:** Check all days you actually ship. If you don’t ship on weekends, uncheck Saturday and Sunday.
  - **Merchant scenario / example:** Your business operates Monday to Friday. You would check Monday through Friday and uncheck Saturday and Sunday.
- **Message (Text Input for each day: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday)**

  - **What this setting does:** Allows you to customize the message displayed alongside the countdown timer for each day of the week. You can use placeholders for dynamic content.
  - **Effect of changing this setting:** The text displayed to the customer will change according to your input for that specific day.
  - **Recommended value:** Craft clear, concise messages. Use placeholders like `{time}` for the remaining time and `{date}` for the estimated delivery date.
  - **Merchant scenario / example:**
    - *Monday Message:* “Order in the next {time} for delivery by Tuesday!”
    - *Saturday Message (if not shipping):* “Orders placed on Saturday will be shipped on Monday.”

#### Product & Category Exclusions/Inclusions

- **Show for in stock products only (Switch)**

  - **What this setting does:** Controls whether the countdown timer is displayed only for products that are currently in stock.
  - **Effect of changing this setting:**
    - *When enabled:* The timer will only appear on product pages where the product has available stock.
    - *When disabled:* The timer will appear regardless of stock status (though it might be confusing for out-of-stock items).
  - **Recommended value:** **Enabled**. It makes little sense to show a shipping countdown for an item that can’t be shipped immediately.
  - **Merchant scenario / example:** You want to avoid promising fast shipping for items you don’t have. Enabling this ensures the timer only shows for available products.
- **Exclude module from selected products / Module visibility for selected products (Radio Buttons)**

  - **What this setting does:** This is a crucial setting to define whether the following product/category/manufacturer selections are for *excluding* the module or *including* it (making it visible only for those selected items).
  - **Effect of changing this setting:**
    - *Exclude module from selected products:* The timer will show everywhere *except* for the items you select below.
    - *Module visibility for selected products:* The timer will *only* show for the items you select below, and nowhere else.
  - **Recommended value:** Depends on your strategy. If you have a few specific products that can’t use the timer, choose “Exclude.” If you only want the timer on a select few products, choose “Module visibility.”
  - **Merchant scenario / example:**
    - *Exclude:* You sell mostly small items with fast shipping, but also a few large furniture pieces that take longer. You’d choose “Exclude” and then select the furniture products.
    - *Visibility:* You’re running a special promotion on a specific category of products and only want the timer to appear there. You’d choose “Module visibility” and select that category.
- **Product Exclusions/Inclusions (Search & Select)**

  - **What this setting does:** Allows you to search for and select specific products to either exclude the timer from or make the timer visible only for (based on the “Exclude module from selected products” setting above).
  - **Effect of changing this setting:** Adds or removes specific products from the exclusion/inclusion list.
  - **Recommended value:** Use this for fine-grained control over individual products.
  - **Merchant scenario / example:** You have a new product that’s on pre-order and won’t ship for weeks. You’d add it to the exclusion list to prevent the countdown from showing.
- **Category Exclusions/Inclusions (Search & Select)**

  - **What this setting does:** Similar to product exclusions, but applies to entire categories.
  - **Effect of changing this setting:** Adds or removes entire categories from the exclusion/inclusion list.
  - **Recommended value:** Useful for applying rules to large groups of products.
  - **Merchant scenario / example:** All products in your “Custom Made” category have long lead times. You’d add this category to the exclusion list.
- **Manufacturer Exclusions/Inclusions (Search & Select)**

  - **What this setting does:** Similar to product/category exclusions, but applies to products from specific manufacturers.
  - **Effect of changing this setting:** Adds or removes manufacturers from the exclusion/inclusion list.
  - **Recommended value:** Handy if certain brands have different shipping policies.
  - **Merchant scenario / example:** One of your suppliers is known for slower shipping. You’d add their manufacturer to the exclusion list.

#### Other Settings

- **mypresta\_updates, update\_, updatev\_ (Internal Settings)**
  - **What this setting does:** These are internal settings used by MyPresta.eu modules for update checks and version management. They are not meant for direct merchant interaction.
  - **Effect of changing this setting:** Changing these could interfere with the module’s ability to check for updates.
  - **Recommended value:** Leave these as they are.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enabled | Enabled | Master switch for the module’s functionality. |
| Module Configuration | Purchase breakpoint time | Your daily shipping cut-off | Defines the daily time an order must be placed for current day’s shipping. |
| Module Configuration | Where you want to display timer? | `displayProductAdditionalInfo`, `displayFooterProduct` | Selects theme locations for the timer. |
| Module Configuration | What design of the module you want to use? | Matches your theme | Visual style of the countdown timer. |
| Module Configuration | Show on Sunday/Monday/…/Saturday | Check all shipping days | Controls on which days the timer is active. |
| Module Configuration | Message (for each day) | “Order in the next {time} for delivery by {date}!” | Customizable text displayed with the timer. |
| Module Configuration | Show for in stock products only | Enabled | Timer only appears for products with available stock. |
| Module Configuration | Exclude module from selected products / Module visibility for selected products | Depends on strategy | Defines if selections are for exclusion or inclusion. |
| Module Configuration | Product Exclusions/Inclusions | Empty | Select specific products to include/exclude. |
| Module Configuration | Category Exclusions/Inclusions | Empty | Select specific categories to include/exclude. |
| Module Configuration | Manufacturer Exclusions/Inclusions | Empty | Select specific manufacturers to include/exclude. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The timer isn’t showing up on my store, or it’s showing in the wrong place.**
A1:

- **Check Module Status:** First, ensure the module is “Enabled” in the configuration page.
- **Check Hook Selection:** Verify that you have selected the correct “Where you want to display timer?” checkboxes. If your theme is heavily customized, some standard hooks might not be rendered, or you might need to use a different hook.
- **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes PrestaShop caches old module positions.
- **Theme Compatibility:** If your theme is highly custom, it might not implement standard PrestaShop hooks in the usual way. You might need to consult your theme developer or a webmaster to manually insert the `displayDeliveryTimer` hook into your theme’s `.tpl` files.

**Q2: The countdown message is incorrect, or the cut-off time seems wrong.**
A2:

- **Verify “Purchase breakpoint time”:** Double-check that the “Purchase breakpoint time” is set correctly to your daily shipping cut-off hour.
- **Check Daily Messages:** Ensure the “Message” for the current day of the week is correctly configured and makes sense.
- **Server Time Zone:** Ensure your PrestaShop store’s server time zone is correctly configured. If the server time is off, the countdown will be inaccurate. You can check this in **Advanced Parameters > Configuration Information** or with your hosting provider.

**Q3: The timer shows for out-of-stock products.**
A3:

- **“Show for in stock products only” Setting:** Make sure the “Show for in stock products only” switch is set to **Enabled** in the module configuration. If it’s disabled, the timer will appear regardless of stock status.

**Q4: I want to change the colors or fonts of the timer beyond the pre-set designs.**
A4:

- The module provides several pre-defined designs. For deeper customization (e.g., specific fonts, exact color codes not available in the designs), you will need a webmaster or developer. They can override the module’s CSS styles by adding custom CSS to your theme’s stylesheet. Refer to Section 7.5 for CSS file details.

**Q5: The timer is not translating into other languages.**
A5:

- Go to **International > Translations** in your PrestaShop Back Office.
- Select “Installed modules translations”, choose your theme, and then select “Shipping delivery countdown timer” from the module dropdown.
- You can then translate all the daily messages and other module strings into your desired languages.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The `Shipping delivery countdown timer` module (`deliverycountdown`) is a standard PrestaShop module following an MVC-like pattern within the module’s scope. It primarily extends `Module` and leverages PrestaShop’s hook system to inject its content and functionality into the front office. Configuration is handled via the `getContent()` method, storing settings in `ps_configuration`. Front-office display relies on Smarty templates and a dedicated JavaScript file for the countdown logic.

### 4.2 Controllers (`controllers/`)

This module does not utilize custom front-office or back-office controllers. All configuration is handled within the main module file’s `getContent()` method. Front-office rendering is achieved directly through hooks and associated templates.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or `ObjectModel`s in the `classes/` directory. All data is stored directly in `ps_configuration` using configuration keys.

### 4.4 JavaScript Assets (`views/js/`)

- **`deliverycountdown/views/js/deliverycountdown.js`**
  - **Scope:** Front-office.
  - **Responsibility:** This is the core JavaScript file responsible for the countdown logic.
  - **Details:**
    - It likely initializes a countdown timer on elements identified by specific CSS classes or IDs.
    - It calculates the remaining time until the “Purchase breakpoint time” for the current day or the next available shipping day.
    - It dynamically updates the displayed time (hours, minutes, seconds) in the front-office template.
    - It handles the transition of messages when the cut-off time is reached (e.g., changing from “Order in X time” to “Orders placed now will ship tomorrow”).
    - It may use `setInterval` or `setTimeout` for real-time updates.
    - It likely reads configuration values (like the cut-off time, daily messages, and enabled days) passed from the Smarty template or inline JavaScript.

### 4.5 CSS Stylesheets (`views/css/`)

The module includes a base CSS file and several theme-specific CSS files for different visual designs.

- **`deliverycountdown/views/css/deliverycountdown.css`**

  - **Scope:** Front-office.
  - **Responsibility:** Contains the fundamental structural and default styling for the countdown timer. This includes basic layout, font sizes, and common elements shared across all designs.
  - **Key Selectors:** Developers can inspect the HTML output of the timer to identify classes like `.deliverycountdown-container`, `.deliverycountdown-message`, `.deliverycountdown-timer`, etc., to override styles in their theme’s `custom.css` or `theme.css`.
- **`deliverycountdown/views/css/deliverycountdown-{color}-{size}.css`** (e.g., `deliverycountdown-black-200x100.css`, `deliverycountdown-blue-400x48.css`)

  - **Scope:** Front-office.
  - **Responsibility:** These files provide the specific color schemes, background images (if any), and size adjustments for the different design options selected in the back office. They typically override or extend the styles defined in `deliverycountdown.css`.
  - **Key Selectors:** These files will target the same core selectors but apply specific `background-color`, `color`, `width`, `height`, `border`, etc., to achieve the chosen visual style.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - **`deliverycountdown/views/hook/displayFooterProduct.tpl`**
    - **Hook:** `displayFooterProduct` (and potentially others like `displayProductAdditionalInfo`, `displayReassurance`, `displayNav1`, `displayDeliveryTimer` if configured).
    - **Purpose:** This is the primary template responsible for rendering the HTML structure of the countdown timer and its associated message on the front office.
    - **Content:**
      - It will contain the main `div` elements for the timer container.
      - It will display the dynamic message (e.g., “Order in the next…”) and the countdown digits.
      - It likely passes necessary configuration variables (like the cut-off time, daily messages, enabled days, current product stock status, exclusion/inclusion rules) to the `deliverycountdown.js` script, either through data attributes or inline `<script>` tags.
      - It includes the selected CSS design file and the `deliverycountdown.js` script.
- **Admin templates (`views/templates/admin/`)**:

  - **`deliverycountdown/views/admin/datepicker.tpl`**
    - **Purpose:** Likely a reusable template for rendering a date picker input field in the module’s back-office configuration. (Though not explicitly used for dates in the current config, it might be a library component).
  - **`deliverycountdown/views/admin/selectedExcludedProducts.tpl`**
    - **Purpose:** Renders the list of products that have been selected for exclusion or inclusion in the module’s configuration. This is part of the product/category/manufacturer selection interface.
  - **`deliverycountdown/views/admin/selectedProducts.tpl`**
    - **Purpose:** Similar to `selectedExcludedProducts.tpl`, but potentially for a different selection context (e.g., if there were separate inclusion and exclusion lists).
  - **`deliverycountdown/views/admin/timepicker.tpl`**
    - **Purpose:** Renders the time picker input field used for setting the “Purchase breakpoint time” in the back-office configuration.
- **Library templates (`deliverycountdown/lib/searchTool/views/scripts.tpl`)**:

  - **`deliverycountdown/lib/searchTool/views/scripts.tpl`**
    - **Purpose:** Likely contains JavaScript or Smarty logic related to the product/category/manufacturer search and selection tool used in the module’s configuration. This script facilitates the AJAX-based search and display of selected items.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create custom SQL tables. All configuration settings are stored in the standard PrestaShop `ps_configuration` table.
  - **Key Configuration Records (examples):**
    - `DC_LAYOUT`: Stores the selected design layout (e.g., ‘black-200x100’).
    - `DC_SUNDAY_MSG`, `DC_MONDAY_MSG`, etc.: Stores the custom message for each day.
    - `DC_TIME`: Stores the “Purchase breakpoint time” (e.g., ‘16:00’).
    - `DC_EXCL`: Boolean for exclusion rule (0 or 1).
    - `DC_INSTOCK`: Boolean for “Show for in stock products only”.
    - `dc_exclusions_products`, `dc_exclusions_cat`, `DC_EXCL_MANUF`: JSON or comma-separated lists of IDs for excluded/included entities.
    - `DC_SUNDAY`, `DC_MONDAY`, etc.: Booleans for enabling/disabling the timer on specific days.
    - `DC_HOOK_displayFooterProduct`, `DC_HOOK_displayReassurance`, etc.: Booleans indicating which hooks are enabled for display.
- **Registered Hooks Table**:

| Hook Name | Scope | Execution Timing | Technical Purpose |
| --- | --- | --- | --- |
| `displayHeader` | Front-office | In the `<head>` section of every page. | Used to load module’s CSS and JS assets globally, or for general site-wide timer display. |
| `displayNav1` | Front-office | Typically in the top navigation bar. | Displays the timer in the primary navigation area. |
| `displayNav2` | Front-office | Often in a secondary navigation bar or utility links. | Displays the timer in a secondary navigation area. |
| `displayTop` | Front-office | In the main header section, below `displayNav`. | Displays the timer in the main header. |
| `displayProductAdditionalInfo` | Front-office | On the product page, often near the “Add to Cart” button. | Strategic placement for product-specific urgency. |
| `displayFooterProduct` | Front-office | On the product page, typically below the product description or details. | Another product-specific placement for urgency. |
| `displayReassurance` | Front-office | In a reassurance block (if theme supports it), often below product info. | Integrates the timer with other trust-building elements. |
| `displayDeliveryTimer` | Front-office | Custom hook. | Allows theme developers to place the timer precisely anywhere in the theme. |
| `actionAdminControllerSetMedia` | Back-office | When an admin controller loads its media assets. | Used to load module-specific CSS/JS for the back-office configuration page (e.g., for the search tool, time picker). |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Shipping delivery countdown timer” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and integration.
