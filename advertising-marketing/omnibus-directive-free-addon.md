---
title: "Omnibus Directive - Free Addon - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Omnibus Directive - Free Addon PrestaShop module by MyPresta.eu."
sidebar:
  label: "Omnibus Directive - Free Addon - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Omnibus Directive - Free Addon Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/omnibus-directive-free-addon.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/omnibus-directive-free-addon/)
>
> ---


# Omnibus Directive - Free Addon

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5 (The module is designed to be compatible with a wide range of PHP versions, up to the latest stable versions supported by PrestaShop 9.x)
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required by PrestaShop itself and are sufficient for this module. No special server configurations are needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

To access the module’s configuration, navigate to **Modules > Module Manager**, search for “Omnibus Directive - Free Addon”, and click the “Configure” button.

#### General Settings

- **Enable Omnibus Directive Compliance:**

  - **What this setting does:** This is the master switch to activate or deactivate the module’s core functionality.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The module will start tracking product prices and display the lowest 30-day price on product pages when a discount is active.
    - *When disabled (NO):* The module will stop tracking prices and will not display any Omnibus-related information on your storefront.
  - **Recommended value:** YES (unless you are not selling to EU customers or are temporarily disabling it for maintenance).
  - **Merchant scenario / example:** You’ve just installed the module and want to ensure your store is compliant. You would set this to YES. If you’re testing a new theme and want to temporarily hide the display, you might set it to NO.
- **Display Lowest Price Text:**

  - **What this setting does:** This allows you to customize the text that appears before the lowest 30-day price.
  - **Effect of changing this setting:**
    - *When changed:* The text displayed to customers will reflect your custom message.
    - *When left as default:* The default text (e.g., “Lowest price in the last 30 days:”) will be used.
  - **Recommended value:** “Lowest price in the last 30 days:” or similar, ensuring clarity for your customers.
  - **Merchant scenario / example:** You might want to use a slightly different phrasing like “Our lowest price recently was:” to match your brand’s tone.
- **Display on Product Page (Hook Selection):**

  - **What this setting does:** This crucial setting determines *where* on your product page the lowest 30-day price information will be displayed. The module provides predefined options for common theme structures (Classic, Hummingbird) and a custom hook option.
  - **Effect of changing this setting:**
    - *When “Classic Theme Profile” is selected:* The module will attempt to inject the price history into a suitable location within the standard Classic theme structure (e.g., `displayProductPriceBlock` or `displayProductButtons`).
    - *When “Hummingbird Theme Profile” is selected:* The module will attempt to inject the price history into a suitable location within the standard Hummingbird theme structure.
    - *When “Custom Hook” is selected:* You will need to manually specify a PrestaShop hook where the module should display its content. This requires some technical knowledge or theme modification.
  - **Recommended value:** Start with “Classic Theme Profile” or “Hummingbird Theme Profile” depending on your active theme. If the display isn’t satisfactory, consult a webmaster for “Custom Hook” integration.
  - **Merchant scenario / example:** If your store uses the default PrestaShop Classic theme, choose “Classic Theme Profile”. If you’ve upgraded to PrestaShop 8.x and use the Hummingbird theme, select “Hummingbird Theme Profile”. If you have a highly customized theme, you might need to use “Custom Hook” and ask your developer to add `{hook h='displayMyCustomOmnibusHook'}` to your product page template.
- **Custom Hook Name (if “Custom Hook” is selected above):**

  - **What this setting does:** If you chose “Custom Hook” in the previous setting, this field allows you to specify the exact name of the hook where the module should render its content.
  - **Effect of changing this setting:** The module will only display its content if a hook with this exact name is present in your theme’s product page template.
  - **Recommended value:** Leave empty unless you have selected “Custom Hook” above and know the exact hook name. Example: `displayProductExtraContent`.
  - **Merchant scenario / example:** Your webmaster has modified your product page template (`product.tpl`) to include `{hook h='displayMyCustomOmnibusHook'}`. You would then enter `displayMyCustomOmnibusHook` into this field.

#### Data Management

- **Clear Omnibus Data:**
  - **What this setting does:** This button allows you to delete all previously recorded price history data stored by the module.
  - **Effect of changing this setting:** Clicking this button will permanently remove all historical price records. The module will then start collecting data anew from the moment products are viewed or updated.
  - **Recommended value:** Use with caution. Only clear data if you need to reset the price history, for example, after a major product catalog overhaul or if you suspect data corruption.
  - **Merchant scenario / example:** You’ve imported a completely new set of products with different pricing strategies, and you want to ensure the Omnibus data starts fresh without any legacy prices. You would click this button.

#### 2.1.1 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable Omnibus Directive Compliance | YES | Activates/deactivates price tracking and display for EU compliance. |
| Module Configuration | Display Lowest Price Text | “Lowest price in the last 30 days:” | Customizes the text shown before the historical price. |
| Module Configuration | Display on Product Page (Hook Selection) | Classic/Hummingbird Profile (based on theme) | Determines where the price history appears on the product page. |
| Module Configuration | Custom Hook Name | (Empty) | Specifies a custom hook for display if “Custom Hook” is selected. |
| Module Configuration | Clear Omnibus Data | (Button) | Deletes all stored price history, forcing a fresh start. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: The lowest price information isn’t showing up on my product pages.**
A:

1. **Check “Enable Omnibus Directive Compliance”:** Make sure it’s set to YES in the module configuration.
2. **Verify “Display on Product Page (Hook Selection)”:** Try switching between “Classic Theme Profile” and “Hummingbird Theme Profile” if you’re unsure which one matches your theme best.
3. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes, theme changes or module updates require a cache refresh.
4. **Check for Discounts:** The information only appears when a product is actually discounted. Ensure the product you’re testing has an active specific price or catalog price rule applied.
5. **Custom Theme:** If you’re using a heavily customized theme, the module might not be able to automatically inject the content. You’ll likely need to use the “Custom Hook” option and have your webmaster integrate it into your theme’s `product.tpl` file.

**Q: The displayed lowest price seems incorrect or too high/low.**
A:

1. **Data Collection Time:** The module needs time to collect data. If you’ve just installed it, it will only start tracking prices from that point. It will take 30 days to have a full 30-day history.
2. **Clear Omnibus Data:** If you suspect old, incorrect data is being used, you can click the “Clear Omnibus Data” button in the module configuration. Be aware this will delete all history, and the module will start collecting data from scratch.
3. **Product Combinations/Currencies:** Ensure you’re looking at the correct combination and currency. The module tracks prices per combination and currency.

**Q: Will this module slow down my store?**
A: The module is designed to be lightweight. Price tracking happens in the background or during product views, and the display on the front office is a simple text output. Any performance impact should be negligible.

**Q: How does this module handle multi-language stores?**
A: The “Display Lowest Price Text” setting is translatable. You can go to **International > Translations**, select “Installed modules translations”, choose your theme, and then select the “Omnibus Directive - Free Addon” module to translate the text into all your active languages.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Omnibus Directive - Free Addon” module follows a standard PrestaShop module architecture. Its core functionality resides within the main `index.php` file, which acts as the module’s entry point and handles installation, uninstallation, configuration, and hook registration. Price history is managed by observing product price changes and storing them, likely in a custom table or `ps_configuration` (though the dossier indicates no custom SQL, implying `ps_configuration` or dynamic data generation). Front-office display is achieved by hooking into standard PrestaShop display points, with specific logic for Classic and Hummingbird themes.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None explicitly defined in the dossier. Front-office logic is likely handled directly within the main module file’s hook methods.
- **Back-Office Admin Controllers**: None explicitly defined in the dossier. All back-office configuration is handled via the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)

- None explicitly defined in the dossier. The module’s logic, including price tracking and storage, is likely encapsulated within the `Omnifree` class in `index.php`.
  - **`Omnifree` class (in `omnifree/index.php`)**:
    - Extends `Module`.
    - Handles module installation (`install()`) and uninstallation (`uninstall()`).
    - Registers necessary hooks (e.g., `displayHeader`, `displayProductPriceBlock`, `displayProductButtons`, `displayFooter`, `actionProductUpdate`, `actionProductSave`).
    - Manages configuration settings via `getContent()`.
    - Contains methods for price tracking and retrieval, likely interacting with `ps_configuration` for storing historical prices or dynamically calculating them based on order history.
    - Implements hook methods (`hookDisplayHeader`, `hookDisplayProductPriceBlock`, `hookDisplayProductButtons`, `hookDisplayFooter`, etc.) to inject content into the front office.
    - Implements action hooks (`hookActionProductUpdate`, `hookActionProductSave`) to record price changes.

### 4.4 JavaScript Assets (`views/js/`)

- **`omnifree/views/js/admin-config.js`**:
  - **Scope:** Back-office.
  - **Purpose:** This script likely handles the dynamic behavior of the module’s configuration page. This could include:
    - Showing/hiding the “Custom Hook Name” input field based on the “Display on Product Page (Hook Selection)” dropdown value.
    - AJAX calls for the “Clear Omnibus Data” button to perform the data cleanup without a full page reload.
    - Input validation or other interactive elements on the configuration form.
  - **Event listeners:** Likely listens for `change` events on dropdowns and `click` events on buttons within the module configuration form.

### 4.5 CSS Stylesheets (`views/css/`)

- **`omnifree/views/css/admin-config.css`**:
  - **Scope:** Back-office admin form styling.
  - **Purpose:** Provides specific styling for elements within the module’s configuration page in the PrestaShop back office, ensuring a consistent and user-friendly admin interface.
  - **Key CSS class selectors:** Likely targets specific IDs or classes within the `configure.tpl` template.
- **`omnifree/views/css/omnibus-classic.css`**:
  - **Scope:** Front-office customer styling (specifically for the Classic theme).
  - **Purpose:** Contains CSS rules to ensure the displayed lowest price information is correctly styled and positioned within the PrestaShop Classic theme, avoiding conflicts and maintaining visual harmony.
  - **Key CSS class selectors:** Targets elements like `.product-prices`, `.product-information`, or custom classes added by the module for the price history display.
- **`omnifree/views/css/omnibus-hummingbird.css`**:
  - **Scope:** Front-office customer styling (specifically for the Hummingbird theme).
  - **Purpose:** Provides specific styling and positioning adjustments for the lowest price information when the Hummingbird theme (PrestaShop 8.x default) is active.
  - **Key CSS class selectors:** Targets elements specific to the Hummingbird theme’s product page structure.
- **`omnifree/views/css/omnibus.css`**:
  - **Scope:** Front-office customer styling (general).
  - **Purpose:** Contains general, theme-agnostic CSS rules for the lowest price display. This might include basic font styling, color, or margin that applies regardless of the specific theme profile chosen.
  - **Key CSS class selectors:** Generic classes used in `omnibus.tpl`.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - **`omnifree/views/templates/hook/omnibus.tpl`**:
    - **Purpose:** This is the primary front-office template responsible for rendering the lowest 30-day price information. It will be rendered by the module’s hook methods (e.g., `hookDisplayProductPriceBlock`, `hookDisplayProductButtons`, or a custom hook).
    - **Variables:** Likely expects variables such as `$lowest_price_30_days`, `$currency_symbol`, `$display_text`, and potentially `$product_id` or `$id_product_attribute`.
    - **Output:** A small HTML snippet containing the configured text and the formatted lowest price.
- **Admin templates (`views/templates/admin/`)**:
  - **`omnifree/views/templates/admin/configure.tpl`**:
    - **Purpose:** This template renders the main configuration form for the module in the PrestaShop back office. It includes all the settings described in Section 4.1.
    - **Variables:** Receives configuration values from `getContent()` for pre-filling form fields.
    - **Structure:** Uses PrestaShop’s helper form structure (e.g., `AdminForm`) to create the input fields, switches, and buttons.
  - **`omnifree/views/templates/admin/pro-teaser.tpl`**:
    - **Purpose:** This template likely displays promotional content or a “teaser” for a “Pro” or paid version of the Omnibus Directive module by MyPresta.eu. It might highlight additional features available in the premium version.
    - **Placement:** Likely included within `configure.tpl` or displayed as a separate block on the configuration page.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  - The dossier indicates no custom SQL files. This suggests that price history data is either:
    1. Stored directly in `ps_configuration` as serialized arrays (less efficient for large datasets).
    2. Dynamically calculated based on `ps_order_detail` and `ps_product_attribute_combination` tables (more complex, but avoids custom tables).
    3. A custom table is created programmatically within `install()` without a separate SQL file. Given the “Free Addon” nature, option 1 or 2 is more probable for simplicity.
- **Registered Hooks Table**:

| Hook Name | Scope | Execution Timing | Technical Purpose |
| --- | --- | --- | --- |
| `displayHeader` | Front-Office | On every page load in the `<head>` section. | To load module’s CSS/JS assets (e.g., `omnibus.css`, `omnibus-classic.css`, `omnibus-hummingbird.css`). |
| `displayProductPriceBlock` | Front-Office | On product pages, typically near the price. | One of the primary hooks for displaying the lowest price information in the Classic theme. |
| `displayProductButtons` | Front-Office | On product pages, typically near the add-to-cart button. | Another potential hook for displaying the lowest price information in the Classic theme. |
| `displayFooter` | Front-Office | At the bottom of every page. | Less likely for price display, but could be used for general compliance messages or if a custom hook is placed here. |
| `actionProductUpdate` | Back-Office | When a product is updated/saved in the back office. | To trigger the price tracking mechanism and record the current product price for history. |
| `actionProductSave` | Back-Office | When a product is saved (new or existing) in the back office. | Similar to `actionProductUpdate`, ensures price changes are captured. |
| `actionFrontControllerSetMedia` | Front-Office | Before a front controller renders its output. | To conditionally load specific CSS/JS based on the current page or theme. |
| (Custom Hook Name) | Front-Office | Where the merchant places `{hook h='CustomHookName'}` in their template. | Allows flexible placement of the lowest price display for highly customized themes. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Omnibus Directive - Free Addon” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu). Our support team is available to assist merchants and developers with any issues or questions related to the module’s functionality and integration.
