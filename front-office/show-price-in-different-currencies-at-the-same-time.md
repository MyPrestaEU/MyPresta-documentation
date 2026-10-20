---
title: "Show price in different currencies at the same time - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Show price in different currencies at the same time PrestaShop module by MyPresta.eu."
sidebar:
  label: "Show price in different currencies at the same time - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Show price in different currencies at the same time Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/show-price-in-different-currencies-at-the-same-time.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/show-price-in-different-currencies-at-the-same-time/)
>
> ---


# Show price in different currencies at the same time

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for a PrestaShop installation and are sufficient for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the “Show price in different currencies at the same time” module. You can access it by navigating to **Modules > Module Manager** and clicking “Configure” next to the module name.

The configuration page will present a series of options to control how and where the multi-currency prices are displayed.

#### General Settings

- **Enable Multi-Currency Price Display:**

  - **What this setting does:** This is the master switch to activate or deactivate the module’s core functionality.
  - **Effect of changing this setting:**
    - *When enabled:* The module will start displaying prices in multiple currencies according to your other settings.
    - *When disabled:* The module will cease to function, and only the primary currency price will be shown.
  - **Recommended value:** YES
  - **Merchant scenario / example:** If you’re setting up the module for the first time or performing maintenance, you might disable it temporarily. For normal operation, it should always be enabled.
- **Select Currencies to Display:**

  - **What this setting does:** This allows you to choose which additional currencies, beyond the primary one, you want to show prices for. You will typically see a list of all active currencies in your PrestaShop store.
  - **Effect of changing this setting:**
    - *When selected:* Prices will be displayed in the chosen currencies.
    - *When not selected:* Prices will not be shown in that specific currency.
  - **Recommended value:** Select all currencies relevant to your target international markets.
  - **Merchant scenario / example:** If you sell to customers in the Eurozone, USA, and UK, you would select EUR, USD, and GBP.
- **Display on Product Listing Pages (Categories, Search Results, etc.):**

  - **What this setting does:** Controls whether the multi-currency prices appear on pages that list multiple products (e.g., category pages, search results, manufacturer pages).
  - **Effect of changing this setting:**
    - *When enabled:* Multi-currency prices will be visible below the main price on product cards.
    - *When disabled:* Multi-currency prices will only appear on the individual product detail page.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Enabling this provides immediate pricing clarity as customers browse, helping them quickly compare products in their preferred currency.
- **Display on Product Detail Page:**

  - **What this setting does:** Controls whether the multi-currency prices appear on the individual product page.
  - **Effect of changing this setting:**
    - *When enabled:* Multi-currency prices will be visible near the main price on the product page.
    - *When disabled:* Multi-currency prices will not be shown on the product page.
  - **Recommended value:** YES
  - **Merchant scenario / example:** This is crucial for customers making a final decision, especially when considering product combinations or quantity discounts, as the module ensures these dynamic prices are also converted.
- **Price Display Format:**

  - **What this setting does:** Defines how the additional currency prices are formatted (e.g., with or without currency symbol, number of decimal places). This usually leverages PrestaShop’s native currency formatting.
  - **Effect of changing this setting:** Changes the visual presentation of the converted prices.
  - **Recommended value:** Use a format that is clear and consistent with international standards for each currency (e.g., “$100.00 USD” or “€100,00”).
  - **Merchant scenario / example:** You might choose to display “USD 100.00” instead of “$100.00” to avoid confusion with other dollar-denominated currencies.
- **Position of Additional Prices:**

  - **What this setting does:** Determines where the additional currency prices are placed relative to the main product price. Options might include “Below main price,” “Next to main price,” or “In a separate block.”
  - **Effect of changing this setting:** Alters the visual layout of the prices on your product pages.
  - **Recommended value:** “Below main price” is often the clearest and least intrusive.
  - **Merchant scenario / example:** If your product page layout is very compact, placing prices below might be better than next to, to avoid crowding.
- **Update Prices with Combinations/Quantity Discounts:**

  - **What this setting does:** Ensures that when a customer selects a different product combination (e.g., a larger size with a different price) or changes the quantity (triggering a quantity discount), the displayed multi-currency prices are dynamically updated to reflect the new total.
  - **Effect of changing this setting:**
    - *When enabled:* The module will use JavaScript to recalculate and display the correct converted prices in real-time.
    - *When disabled:* The additional prices might not update, leading to incorrect information for the customer.
  - **Recommended value:** YES (Crucial for accuracy and customer trust).
  - **Merchant scenario / example:** A customer selects a “Large” t-shirt (which costs more) or adds 10 items (triggering a bulk discount). This setting ensures they see the correct converted price for the large t-shirt or the discounted bulk price in their chosen currencies.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable Multi-Currency Price Display | YES | Activates/deactivates the module’s core functionality. |
| Module Configuration | Select Currencies to Display | Select relevant currencies | Determines which additional currencies are shown. |
| Module Configuration | Display on Product Listing Pages | YES | Shows multi-currency prices on category, search, etc., pages. |
| Module Configuration | Display on Product Detail Page | YES | Shows multi-currency prices on individual product pages. |
| Module Configuration | Price Display Format | Varies (use PrestaShop defaults) | Controls the visual formatting of converted prices. |
| Module Configuration | Position of Additional Prices | Below main price | Sets the layout of additional prices relative to the main price. |
| Module Configuration | Update Prices with Combinations/Quantity Discounts | YES | Ensures dynamic price updates for combinations and discounts. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The multi-currency prices are not showing up on my store.**
**A1:**

- **Check Module Status:** First, ensure the “Enable Multi-Currency Price Display” option is set to YES in the module’s configuration.
- **Selected Currencies:** Verify that you have selected the specific currencies you wish to display in the module settings.
- **Cache:** Clear your PrestaShop cache (Advanced Parameters > Performance > Clear Cache) and your browser cache. Sometimes, old cached content prevents new module displays.
- **Theme Compatibility:** If you are using a highly customized theme, there might be a conflict. Contact MyPresta.eu support with details of your theme.

**Q2: The prices in other currencies are incorrect or not updating.**
**A2:**

- **Exchange Rates:** Ensure your PrestaShop currency exchange rates are up-to-date. Go to **International > Currencies** in your Back Office and check the exchange rates for each currency. You can usually update them automatically or manually.
- **Dynamic Update Setting:** Make sure “Update Prices with Combinations/Quantity Discounts” is enabled in the module configuration if you expect prices to change with product options.
- **Cache:** Clear all caches (PrestaShop and browser) after updating exchange rates.

**Q3: The multi-currency prices look strange or are not styled correctly on my theme.**
**A3:**

- **Module Configuration:** Check the “Price Display Format” and “Position of Additional Prices” settings in the module.
- **Theme CSS:** Your custom theme’s CSS might be overriding the module’s default styling. This usually requires a webmaster or developer to inspect the CSS. You can often add custom CSS to your theme to adjust the appearance.
- **Contact Support:** If you’re unable to resolve styling issues, provide screenshots and your store URL to MyPresta.eu support for assistance.

**Q4: Will this module slow down my store?**
**A4:** The module is designed to be lightweight. It primarily fetches existing currency rates and performs simple calculations. The dynamic updates for combinations use JavaScript, which runs client-side. In most cases, any performance impact should be negligible. Ensure your server meets PrestaShop’s minimum requirements for optimal performance.

**Q5: How do I translate the module’s text (e.g., “Price in USD”)?**
**A5:** You can translate any text strings added by the module through PrestaShop’s translation interface:

- Navigate to **International > Translations**.
- Select “Installed modules translations”.
- Choose your theme, your language, and then select the “Show price in different currencies at the same time” module.
- You can then edit the translations for any phrases the module introduces.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical architecture of the “Show price in different currencies at the same time” module, intended for developers, webmasters, and technical agencies.

### 4.1 Architecture Overview

The module `multiprice` (internal name `ajax_multiprice`) is a standard PrestaShop module primarily focused on front-office display. It leverages PrestaShop’s hook system to inject multi-currency price information into product listings and product detail pages. The core logic resides within the main module file, handling configuration and hook registration. Client-side JavaScript is used for dynamic updates of prices when product combinations or quantities change, ensuring real-time accuracy without full page reloads. It does not introduce custom database tables or complex ObjectModels, relying instead on PrestaShop’s existing currency and product pricing mechanisms.

### 4.2 Controllers (`controllers/`)

This module does not use custom Front-Office or Back-Office Admin Controllers. All configuration is handled via the `getContent()` method in the main module file, and front-office interactions are managed through hooks and client-side JavaScript.

### 4.3 Core Classes & Models (`classes/`)

The module does not define any custom classes or ObjectModels in the `classes/` directory. Its logic is encapsulated within the main `ajax_multiprice.php` module file.

### 4.4 JavaScript Assets (`views/js/`)

- **`multiprice/lib/searchTool/views/js/autocomplete.js`**

  - **Scope:** Potentially Front-office (if used for a search feature within the module, though not directly related to the core multi-price display).
  - **Responsibility:** This file appears to be part of a generic autocomplete search tool library bundled with the module. It would typically handle AJAX requests for search suggestions, bind to input fields, and display results. Its direct relevance to the multi-currency price display is likely minimal unless the module integrates a search feature that also displays prices.
  - **Details:** Binds to input fields, listens for `keyup` events, makes AJAX calls to a backend endpoint (not defined in this module’s controllers, likely a generic PrestaShop search controller or a bundled search tool’s controller), and manipulates the DOM to show a dropdown list of suggestions.
- **`multiprice/views/js/multiprice.js`**

  - **Scope:** Front-office.
  - **Responsibility:** This is the core JavaScript file for the multi-currency price display. It’s responsible for dynamically updating the displayed prices when product attributes (combinations) or quantities change on the product page.
  - **Details:**
    - Listens for `change` events on product combination selectors (e.g., `select` elements for attributes, radio buttons).
    - Listens for `change` or `blur` events on the quantity input field.
    - Hooks into PrestaShop’s native `prestashop.on('updatedProduct', ...)` event (for PS 1.7+), which is triggered when product data (including price) is updated after combination selection.
    - Retrieves the new base price from the updated product data.
    - Performs client-side calculations to convert the new base price into the configured additional currencies, using exchange rates potentially passed from the backend or stored in a global JS variable.
    - Updates the DOM elements (`<span>`, `<div>`) where the additional currency prices are displayed.
    - Ensures proper formatting of the converted prices (currency symbol, decimals).

### 4.5 CSS Stylesheets (`views/css/`)

- **`multiprice/lib/searchTool/views/css/autocomplete.css`**

  - **Scope:** Front-office.
  - **Responsibility:** Styles the autocomplete search results dropdown, including suggestions, highlighting, and general layout.
  - **Key CSS class selectors:** Likely targets classes like `.autocomplete-results`, `.autocomplete-item`, `.highlighted`. Developers can override these in their theme’s `custom.css` or `theme.css`.
- **`multiprice/views/css/multiprice.css`**

  - **Scope:** Front-office customer styling.
  - **Responsibility:** Provides the default styling for the multi-currency price display blocks. This includes font sizes, colors, margins, and potentially layout (e.g., stacking prices vertically).
  - **Key CSS class selectors:** Will target specific classes added by the module’s templates (e.g., `.multiprice-container`, `.multiprice-currency-item`, `.multiprice-price`). Developers can override these selectors in their theme’s CSS to match their store’s design.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`multiprice/lib/searchTool/views/scripts.tpl`**

  - **Scope:** Front-office.
  - **Purpose:** This template likely includes the JavaScript and CSS for the `autocomplete.js` functionality. It would be hooked into `displayHeader` or `displayFooter` to ensure the necessary assets are loaded.
- **`multiprice/views/templates/multiprice-custom.tpl`**

  - **Scope:** Front-office (hook template).
  - **Purpose:** This template is likely a fallback or an alternative template for displaying the multi-currency prices, possibly for specific hooks or custom placements. It would contain the HTML structure to render the primary price and then iterate through the additional currencies to display their converted prices.
- **`multiprice/views/templates/multiprice.tpl`**

  - **Scope:** Front-office (hook template).
  - **Purpose:** This is the primary template responsible for rendering the multi-currency price block. It’s injected into product listing items and the product detail page via PrestaShop hooks. It receives an array of currencies and their converted prices and formats them according to the module’s configuration.
  - **Variables:** Expects variables like `$product_price`, `$additional_currencies` (an array of currency objects with converted prices), `$currency_format`, etc.
- **`multiprice/views/templates/selectedProducts.tpl`**

  - **Scope:** Front-office.
  - **Purpose:** This template’s name suggests it might be used in a context where a list of selected products is displayed, potentially in a cart summary, a comparison page, or a custom product selection widget. It would iterate over a collection of products and display their prices, potentially with the multi-currency feature.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any custom SQL tables.
  - It stores its configuration settings (e.g., enabled status, selected currencies, display options) in the `ps_configuration` table, using keys prefixed with `MULTIPRICE_` or similar.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | To include `multiprice.js` and `multiprice.css` (and potentially `autocomplete` assets) on front-office pages. |
| `displayProductPriceBlock` (type `after_price`) | After the main price block on product pages. | To inject the `multiprice.tpl` or `multiprice-custom.tpl` content displaying additional currency prices on the product detail page. |
| `displayProductListReviews` (or similar for product list) | Within product list items (e.g., category pages). | To inject `multiprice.tpl` or `multiprice-custom.tpl` content displaying additional currency prices below the main price on product listing pages. The exact hook might vary depending on the PrestaShop version and theme structure (e.g., `displayProductPriceBlock` can also be used here, or a custom hook provided by the theme). |
| `actionProductUpdate` (or similar) | After a product is updated in the back office. | (Less likely for this module) Could be used to clear cache related to product prices, though not strictly necessary for its core function. |
| `actionFrontControllerSetMedia` | Before a front controller renders its content. | To register JavaScript and CSS files for the front office, ensuring they are loaded correctly. |

## 5. Official Support & Updates

For official updates, technical support, and any inquiries regarding the “Show price in different currencies at the same time” module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist you with installation, configuration, and any issues you may encounter.
