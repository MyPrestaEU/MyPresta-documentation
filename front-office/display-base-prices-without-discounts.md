---
title: "Display base prices (without discounts) - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Display base prices (without discounts) PrestaShop module by MyPresta.eu."
sidebar:
  label: "Display base prices (without discounts) - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Display base prices (without discounts) Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/display-base-prices-without-discounts.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/display-base-prices-without-discounts/)
>
> ---


# Display base prices (without discounts)

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the module name to access its settings. This is the main screen where you control how and where the base prices are displayed.

| Setting / Option | What this setting does | Effect of changing this setting | Recommended value | Merchant scenario / example |
| --- | --- | --- | --- | --- |
| **Enable module** | This is the master switch to turn the module’s functionality on or off. | *When enabled:* The module will start displaying base prices on your front-office according to other settings. *When disabled:* The module will stop displaying base prices, and your store will revert to showing only current prices. | YES | You’ve just installed the module and want to activate its features. |
| **Display on product page** | Controls whether the base price is shown on individual product detail pages. | *When enabled:* The original price will appear next to the discounted price on every product’s page. *When disabled:* The base price will not be shown on product pages, even if enabled elsewhere. | YES | You want customers viewing a specific product to clearly see the savings. |
| **Display on category pages** | Controls whether the base price is shown on product listing pages (e.g., category pages, search results). | *When enabled:* The original price will appear next to the discounted price for each product listed in categories, search results, etc. *When disabled:* The base price will not be shown on product listing pages. | YES | You want customers browsing categories to quickly identify discounted items and their savings. |
| **Display in cart summary** | Controls whether the base price is shown in the shopping cart summary. | *When enabled:* The original price will be visible for each product in the customer’s shopping cart, reinforcing the total savings. *When disabled:* Only the current, discounted price will be shown in the cart. | NO (or YES, depending on theme) | You want to remind customers of their total savings before they proceed to checkout. However, some themes might not have a suitable display area, or it might clutter the cart. Test thoroughly. |
| **Custom CSS for base price** | Allows you to add custom CSS rules to style the displayed base price. | *When filled with CSS:* The base price will be styled according to your input (e.g., font size, color, strikethrough). *When empty:* The module will use its default styling or inherit styles from your theme. | `text-decoration: line-through; color: #999; font-size: 0.9em;` | You want the base price to be greyed out and struck through to clearly differentiate it from the current price. |
| **Position of base price** | Determines where the base price is injected relative to the current price. | *Options: Before current price, After current price.* *When set to ‘Before’:* Base price will appear to the left of the current price. *When set to ‘After’:* Base price will appear to the right of the current price. | Before current price | You want the customer to see the original price first, then the new, lower price. |

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable module | YES | Activates/deactivates the module’s core functionality. |
| Module Configuration | Display on product page | YES | Shows base price on individual product pages. |
| Module Configuration | Display on category pages | YES | Shows base price on product listing pages (categories, search). |
| Module Configuration | Display in cart summary | NO (or YES, test) | Shows base price in the shopping cart. |
| Module Configuration | Custom CSS for base price | `text-decoration: line-through; color: #999; font-size: 0.9em;` | Customizes the visual style of the base price. |
| Module Configuration | Position of base price | Before current price | Controls placement relative to the current price. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: The base prices are not showing up on my store, even though the module is enabled.**
A:

1. **Check module settings:** Ensure “Enable module” and the specific display options (e.g., “Display on product page”) are set to YES.
2. **Clear PrestaShop Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” in the top right. Smarty cache often needs to be cleared for template changes to appear.
3. **Check for Discounts:** Make sure the products you are testing actually have active discounts (catalog price rules, specific prices, or percentage reductions) applied. The module only shows a base price if there’s a difference.
4. **Theme Compatibility:** Some highly customized themes might override core PrestaShop price display functions. If the issue persists, contact MyPresta.eu support.

**Q: The base price is showing, but it doesn’t look good with my theme (wrong color, size, etc.).**
A: Use the “Custom CSS for base price” setting in the module configuration. You can add CSS rules to match your theme’s design. For example, to make it grey and struck through: `text-decoration: line-through; color: #999; font-size: 0.9em;`. If you’re unsure about CSS, a web developer can help.

**Q: Will this module slow down my store?**
A: The module is designed to be lightweight. It primarily overrides a core PrestaShop class (`Product.php`) to fetch the base price and injects a small template. The performance impact should be negligible. Always ensure your PrestaShop cache is enabled for optimal speed.

**Q: Does this module work with multi-language stores?**
A: Yes, the module works with PrestaShop’s multi-language capabilities. Prices are displayed in the currency and format of the active language/country.

**Q: I see an “Override conflict” error after installing the module.**
A: This module overrides the `Product.php` class. If another module also tries to override this same class, you might encounter a conflict. PrestaShop 1.7+ has better override management, but conflicts can still occur. You’ll need to either disable one of the conflicting modules or merge the overrides manually (requires developer knowledge). Contact MyPresta.eu support for assistance.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Display base prices (without discounts)” module primarily operates by overriding the core `Product` class to introduce a method for retrieving the product’s base price without reductions. It then uses a Smarty template to display this price in the front office, injected via a custom hook mechanism. The module’s configuration is managed through a standard PrestaShop `getContent()` method in the main module file.

### 4.2 Controllers (`controllers/`)

This module does not introduce any custom front-office or back-office controllers. Its functionality is integrated directly into existing PrestaShop price display mechanisms and through an override.

### 4.3 Core Classes & Models (`classes/`)

- **`baseprices/override/classes/index.php`**: A standard empty `index.php` file to prevent directory listing.
- **`baseprices/override/classes/Product.php`**:
  - **Class Name**: `Product` (overrides the core `Product` class)
  - **Parent Class**: `ProductCore`
  - **Responsibility**: This override is the core of the module’s functionality. It introduces a new method, `getBasePrice()`, which calculates and returns the product’s price *before* any specific prices, catalog price rules, or group reductions are applied. This method ensures that the true original price is always available for display. It typically involves bypassing the standard price calculation logic that accounts for discounts.

### 4.4 JavaScript Assets (`views/js/`)

- **`baseprices/views/js/baseprices-admin.js`**:
  - **Scope**: Back-office (module configuration page).
  - **Responsibility**: This script likely handles any dynamic behavior or validation on the module’s configuration form. For example, it might show/hide settings based on other selections, or provide real-time feedback for the custom CSS field.
- **`baseprices/views/js/baseprices.js`**:
  - **Scope**: Front-office.
  - **Responsibility**: This script is responsible for dynamically injecting the base price into the DOM where needed, especially for AJAX-loaded content or when product attributes change (e.g., selecting a different combination on the product page). It listens for PrestaShop’s `updateProduct` event or similar events to refresh the price display. It might also handle styling or visibility toggles for the base price element.

### 4.5 CSS Stylesheets (`views/css/`)

- **`baseprices/views/css/baseprices.css`**:
  - **Scope**: Front-office customer styling.
  - **Main UI components and containers it styles**: This stylesheet provides the default visual presentation for the base price. It typically includes rules for:
    - `span.base-price` or similar selectors.
    - `text-decoration: line-through;` to strike through the price.
    - `color`, `font-size`, `margin`, `padding` to position and style the base price relative to the current price.
  - **Key CSS class selectors developers can override**: `span.base-price`, `div.product-price-and-shipping .base-price`, etc. Developers can target these classes in their theme’s custom CSS to override the module’s default styling.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`baseprices/views/templates/baseprices.tpl`**:
  - **Scope**: Front-office.
  - **Responsibility**: This template is the primary output for displaying the base price. It’s designed to be included or rendered wherever a product’s price is shown. It typically receives variables like `$base_price` and `$current_price` and formats them according to the module’s settings (e.g., custom CSS, position). It will contain the HTML structure (e.g., `<span class="base-price">...</span>`) that the CSS targets.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: This module does not create any custom database tables. Its configuration settings are stored in the `ps_configuration` table, using keys prefixed with `BASEPRICES_`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Used to load the module’s front-office CSS and JavaScript assets. |
| `displayProductPriceBlock` | Within the product price display block on product pages and listings. | The module likely leverages this hook (or similar price-related hooks) to inject its `baseprices.tpl` template, displaying the base price alongside the current price. |
| `actionProductUpdate` / `actionProductSave` | After a product is updated or saved in the Back Office. | While not explicitly listed, modules that override `Product.php` might use such hooks to clear caches or re-index product data if necessary, though this module’s primary function is display-only. |
| `actionFrontControllerSetMedia` | Before a front controller renders its template. | Used to register front-office JavaScript and CSS files for the current page. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the “Display base prices (without discounts)” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have.
