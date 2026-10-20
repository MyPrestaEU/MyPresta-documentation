---
title: "Attribute values in product name - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Attribute values in product name PrestaShop module by MyPresta.eu."
sidebar:
  label: "Attribute values in product name - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Attribute values in product name Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/attribute-values-in-product-name.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/attribute-values-in-product-name/)
>
> ---


# Attribute values in product name

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installing the module, click “Configure” to access its settings.

#### Product name CSS class

- **What this setting does:** This field allows you to specify the CSS class of the HTML element that displays the product name on your product pages. The module needs to know this class so it can correctly identify and modify the product name element when a customer selects a new attribute combination.
- **Effect of changing this setting:**
  - *When a correct CSS class is entered:* The module will successfully locate the product name on the page and dynamically append the selected attribute values to it.
  - *When an incorrect or no CSS class is entered:* The module will not be able to find the product name element, and therefore, the attribute values will not be added to the product name. The product name will remain static.
- **Recommended value:** This value depends on your PrestaShop theme.
  - For **PrestaShop’s default themes (Classic)**, a common class for the product name is `h1.product-detail-name` or `h1[itemprop="name"]`. You might need to inspect your product page using your browser’s developer tools to find the exact class or ID of the `<h1>` tag containing the product name.
  - If you are unsure, try `h1.product-detail-name` first. If it doesn’t work, you’ll need to consult your theme developer or use browser developer tools (right-click on the product name, select “Inspect”) to find the correct CSS selector for the main product name heading.
- **Merchant scenario / example:**
  - You’ve installed a custom theme, and the product name is wrapped in an `<h2>` tag with the class `my-custom-product-title`. You would enter `h2.my-custom-product-title` into this field.
  - If your theme uses the standard PrestaShop Classic theme structure, entering `h1.product-detail-name` should work perfectly, ensuring that when a customer selects “Blue” for a shirt, the title updates from “T-Shirt” to “T-Shirt (Blue)”.

#### Other Configuration Keys (Internal)

You may see other configuration keys like `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`, `mypresta_updates`, `update_`, `updatev_`. These are internal settings used by PrestaShop and MyPresta.eu for managing module updates and language preferences. You do not need to interact with these.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Product name CSS class | `h1.product-detail-name` (for Classic theme) | Specifies the CSS selector for the product name element. Essential for the module to identify and modify the product title on the product page. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: The product name isn’t changing when I select attributes. What’s wrong?**
A: The most common reason is an incorrect “Product name CSS class” setting.
- **Solution**:
1. Go to your product page in your browser.
2. Right-click on the product name and select “Inspect” (or “Inspect Element”).
3. Look for the `<h1>` or `<h2>` tag that contains the product name. Note down its class (e.g., `class="product-detail-name"`) or ID (e.g., `id="product_name"`).
4. Enter the correct CSS selector into the module’s configuration. For example, if the tag is `<h1 class="my-product-title">`, you would enter `h1.my-product-title`. If it’s `<h2 id="product_heading">`, you would enter `h2#product_heading`.
5. Save the module configuration and clear your PrestaShop cache (Advanced Parameters > Performance > Clear cache).

**Q: The module worked initially, but after updating my theme, it stopped working.**
A: Theme updates often change the HTML structure and CSS classes.
- **Solution**: Re-check the “Product name CSS class” setting as described above. Your new theme might use a different class or ID for the product name.

**Q: Will this module affect my SEO?**
A: No, this module only changes the product name dynamically on the client-side (in the customer’s browser) using JavaScript. It does not alter the product’s original name stored in your database or the `<h1>` tag that search engines typically index. Your SEO remains unaffected.

**Q: Does this module support multiple languages?**
A: Yes, the module works with the attribute values as they are configured in your PrestaShop back office, which are already multi-language compatible. The module simply appends the currently selected attribute values in the active language to the product name.

**Q: I see the attribute values, but they are styled incorrectly (e.g., wrong font, color).**
A: The module appends text to an existing HTML element. Its styling will inherit from your theme’s CSS for that product name element.
- **Solution**: If you want to style the appended attribute values differently, you’ll need custom CSS. You can target the product name element and potentially use pseudo-elements or specific selectors if the module wraps the appended text in a unique span (though this module typically just appends text). A web developer can help you with custom CSS.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers, webmasters, and agencies.

### 4.1 Architecture Overview

The “Attribute values in product name” module (`anpn`) is a lightweight PrestaShop module primarily focused on front-office client-side manipulation. It leverages PrestaShop’s hook system to inject its JavaScript into the product page header. The core logic resides in a single JavaScript file that listens for changes in product attribute selections and dynamically updates the product name’s text content. It does not introduce new database tables or complex server-side logic beyond its configuration.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. All front-office functionality is handled via JavaScript injected through hooks.
- **Back-Office Admin Controllers**: None. Configuration is managed directly within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

- No custom classes or `ObjectModel` instances are defined. The module operates directly on configuration values and front-office DOM manipulation.

### 4.4 JavaScript Assets (`views/js/`)

- **`anpn/views/js/anpn.js`**
  - **Scope**: Front-office (product page).
  - **Purpose**: This script is responsible for the dynamic update of the product name.
  - **Functionality**:
    1. **DOM Ready / `prestashop.on`**: It waits for the DOM to be fully loaded and specifically listens for the `updatedProduct` event triggered by PrestaShop’s core JavaScript when a product combination is changed (e.g., by selecting a different size or color).
    2. **Product Name Identification**: It retrieves the CSS selector for the product name from the module’s configuration (passed via `anpn_pn_class` global variable or similar mechanism). It then uses this selector to find the target HTML element on the page.
    3. **Attribute Value Extraction**: When `updatedProduct` is triggered, it accesses the current product combination data (which includes selected attribute values) from the event payload.
    4. **Dynamic Update**: It constructs a string of the selected attribute values (e.g., “(M, Blue)”) and appends it to the original product name (which it typically stores on initial load or retrieves from a data attribute).
    5. **DOM Manipulation**: The script updates the `textContent` or `innerText` of the identified product name element with the new, combined string.
  - **Dependencies**: Relies on jQuery (if PrestaShop 1.7.x) or native DOM APIs, and PrestaShop’s `prestashop.on` event system.

### 4.5 CSS Stylesheets (`views/css/`)

- No custom CSS files are provided by the module. The appended attribute values inherit the styling of the existing product name element in the theme.

### 4.6 Smarty Template Structure (`views/templates/`)

- No custom template files are provided by the module. All output is handled by the main module file (`anpn.php`) for configuration, and JavaScript for front-office display.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  - The module does not create any custom database tables.
  - It stores its configuration settings in the `ps_configuration` table:
    - `ANPN_PN_CLASS`: Stores the CSS class/selector for the product name element.
- **Registered Hooks Table**:

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `displayHeader` | In the `<head>` section of every front-office page. | Used to register the module’s JavaScript (`anpn.js`) and pass the `ANPN_PN_CLASS` configuration value to the front-end script. |
  | `displayProductAdditionalInfo` | On the product page, typically below the main product information. | While not explicitly used for visual output in this module, it’s a common hook for modules to inject content or scripts on the product page. In this module’s context, it might be used to ensure the JS is loaded at the right time, or it could be a legacy hook registration. The primary interaction is via `displayHeader` and the `updatedProduct` event. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Attribute values in product name” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have.
