---
title: "Sliding sidebar cart - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Sliding sidebar cart PrestaShop module by MyPresta.eu."
sidebar:
  label: "Sliding sidebar cart - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Sliding sidebar cart Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/sliding-sidebar-cart.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/sliding-sidebar-cart/)
>
> ---


# Sliding sidebar cart

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installing the module, click “Configure” to access its settings. This page allows you to control exactly what information is displayed within the sliding sidebar cart.

- **Display product image**

  - **What this setting does:** Controls whether the thumbnail image of each product in the cart is shown in the sidebar.
  - **Effect of changing this setting:**
    - *When enabled (“On”):* A small image of each product will appear next to its name in the sidebar, making it easier for customers to visually identify items.
    - *When disabled (“Off”):* Only the product name and other text details will be shown, saving space but potentially making the cart less visually engaging.
  - **Recommended value:** “On”
  - **Merchant scenario / example:** Enabling this helps customers quickly confirm they’ve added the correct item, especially useful for stores with many similar-sounding products or variations.
- **Display product name**

  - **What this setting does:** Determines if the name of each product is visible in the sliding cart.
  - **Effect of changing this setting:**
    - *When enabled (“On”):* The full name of each product will be displayed.
    - *When disabled (“Off”):* Product names will be hidden. This is generally not recommended as it makes the cart difficult to understand.
  - **Recommended value:** “On”
  - **Merchant scenario / example:** This is a fundamental piece of information. Always keep it “On” so customers know exactly what’s in their cart.
- **Display product attribute values**

  - **What this setting does:** If your products have attributes (like size, color, material), this setting controls whether those selected attributes are shown for each product in the cart.
  - **Effect of changing this setting:**
    - *When enabled (“On”):* For a product like “T-Shirt (Size: M, Color: Blue)”, “Size: M, Color: Blue” will be displayed.
    - *When disabled (“Off”):* Only “T-Shirt” will be shown, potentially confusing customers about the exact variant they added.
  - **Recommended value:** “On” (especially for stores selling configurable products)
  - **Merchant scenario / example:** Crucial for stores selling clothing, electronics with different specifications, or any product with multiple options. It helps customers verify they’ve selected the right variant.
- **Display product price**

  - **What this setting does:** Controls whether the individual price of each product in the cart is displayed.
  - **Effect of changing this setting:**
    - *When enabled (“On”):* The unit price for each item will be visible.
    - *When disabled (“Off”):* Individual product prices will be hidden, though the total cart value will still be shown.
  - **Recommended value:** “On”
  - **Merchant scenario / example:** Transparency is key. Showing individual prices helps customers understand the cost breakdown and confirms their selections.
- **Display quantity input field**

  - **What this setting does:** Allows customers to change the quantity of an item directly within the sidebar cart using an input field.
  - **Effect of changing this setting:**
    - *When enabled (“On”):* A numerical input field (e.g., “1”, “2”, “3”) will appear next to each product, allowing customers to type in a new quantity or use increment/decrement buttons.
    - *When disabled (“Off”):* Customers cannot change quantities in the sidebar; they would need to go to the full cart page to do so.
  - **Recommended value:** “On”
  - **Merchant scenario / example:** This significantly improves usability. A customer who accidentally added 2 of an item instead of 1 can instantly correct it without leaving their current page, reducing frustration and potential cart abandonment.
- **Display remove button**

  - **What this setting does:** Adds a button (usually an “X” or a trash can icon) next to each product, allowing customers to remove it from the cart.
  - **Effect of changing this setting:**
    - *When enabled (“On”):* Customers can easily delete unwanted items from their cart directly from the sidebar.
    - *When disabled (“Off”):* Customers cannot remove items from the sidebar; they would need to go to the full cart page.
  - **Recommended value:** “On”
  - **Merchant scenario / example:** Essential for a flexible shopping experience. If a customer changes their mind about an item, they can remove it instantly, preventing them from abandoning the entire cart due to one unwanted product.
- **Display shipping cost**

  - **What this setting does:** Shows an estimate or the actual shipping cost within the sidebar cart summary.
  - **Effect of changing this setting:**
    - *When enabled (“On”):* The estimated or calculated shipping cost will be displayed in the cart summary.
    - *When disabled (“Off”):* Shipping costs will not be shown in the sidebar, only on the full cart or checkout page.
  - **Recommended value:** “On” (if your shipping calculation is accurate early on)
  - **Merchant scenario / example:** Transparency about shipping costs upfront can prevent “sticker shock” at checkout, which is a major cause of cart abandonment. If your shipping is complex or depends heavily on the customer’s address, you might consider leaving it “Off” to avoid misleading estimates.
- **Display subtotal (total products value)**

  - **What this setting does:** Shows the total value of all products in the cart, *before* any shipping, taxes, or discounts are applied.
  - **Effect of changing this setting:**
    - *When enabled (“On”):* The sum of all product prices will be displayed.
    - *When disabled (“Off”):* This specific subtotal line will be hidden.
  - **Recommended value:** “On”
  - **Merchant scenario / example:** Provides a clear breakdown for the customer, helping them understand the cost of the items themselves separate from other charges.
- **Display subtotal taxes**

  - **What this setting does:** Shows the total amount of taxes applied to the products in the cart.
  - **Effect of changing this setting:**
    - *When enabled (“On”):* The total tax amount will be displayed in the cart summary.
    - *When disabled (“Off”):* Tax details will not be shown in the sidebar.
  - **Recommended value:** “On” (especially in regions where tax transparency is legally required or expected by customers)
  - **Merchant scenario / example:** Important for transparency, particularly in countries where VAT or sales tax is a significant component of the final price. It helps customers understand the full cost breakdown before proceeding to checkout.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Display product image | On | Shows product thumbnails for visual identification. |
| Module Configuration | Display product name | On | Shows the name of each product in the cart. |
| Module Configuration | Display product attribute values | On | Shows selected attributes (size, color) for configurable products. |
| Module Configuration | Display product price | On | Shows the individual price of each product. |
| Module Configuration | Display quantity input field | On | Allows customers to change product quantities directly in the sidebar. |
| Module Configuration | Display remove button | On | Allows customers to remove products from the cart directly in the sidebar. |
| Module Configuration | Display shipping cost | On | Shows estimated/actual shipping cost in the summary. |
| Module Configuration | Display subtotal (total products value) | On | Shows the total value of products before shipping/taxes. |
| Module Configuration | Display subtotal taxes | On | Shows the total tax amount applied to products. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The sidebar isn’t sliding out when I add a product to the cart.**
A1:

- **Check Module Status:** Ensure the “Sliding sidebar cart” module is installed and enabled in **Modules > Module Manager**.
- **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes, old cached files prevent new module functionality from loading.
- **Theme Conflicts:** Your theme might have its own “add to cart” confirmation or JavaScript that conflicts with this module. Temporarily switch to the default PrestaShop theme (Classic) to see if the sidebar works. If it does, the issue is with your custom theme’s JavaScript or CSS. You may need a developer to investigate.
- **JavaScript Errors:** Open your browser’s developer console (usually F12) and check for any JavaScript errors when you add a product. These errors can prevent the sidebar from appearing.

**Q2: The sidebar appears, but the styling looks off (wrong colors, fonts, or layout).**
A2:

- **Theme CSS Conflicts:** This is almost always a CSS conflict with your active PrestaShop theme. Your theme’s stylesheets might be overriding the module’s styles.
- **Solution:** You’ll likely need a webmaster or developer to inspect the CSS using browser developer tools. They can identify the conflicting styles and add custom CSS to your theme (or the module’s custom CSS file if available) to ensure the sidebar displays correctly.

**Q3: The quantities or prices don’t update correctly when I change them in the sidebar.**
A3:

- **Clear Cache:** Again, try clearing your PrestaShop cache (**Advanced Parameters > Performance**).
- **AJAX Issues:** The module uses AJAX to update the cart. If there are server-side errors or JavaScript conflicts preventing the AJAX calls from completing, updates won’t register. Check your browser’s developer console for network errors or JavaScript errors when you try to change quantities.
- **Module Configuration:** Double-check that “Display quantity input field” is enabled in the module’s configuration.

**Q4: How do I translate the text in the sidebar to other languages?**
A4:

- **PrestaShop Translation System:** Go to **International > Translations** in your Back Office.
- **Type of Translation:** Select “Installed modules translations”.
- **Select Module:** Choose “Sliding sidebar cart” from the module dropdown.
- **Select Language:** Pick the language you want to translate.
- **Translate:** You will see a list of translatable strings from the module. Enter your translations and save.

**Q5: Can I change which side the sidebar slides from (left vs. right)?**
A5:

- The module’s default behavior is typically to slide from the right. Changing this would require custom CSS modifications, as it’s controlled by the `sidcart.css` and `sidcart-right.css` files. A developer could adjust the CSS properties (e.g., `right: 0` to `left: 0`) and potentially the animation logic to achieve this.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Sliding sidebar cart” module (`sidcart`) follows a standard PrestaShop module architecture, primarily focusing on front-office enhancements. It leverages PrestaShop’s hook system to inject its functionality and templates into the storefront. The core logic for cart interaction (adding, updating, removing products) is handled via an AJAX front controller, ensuring a dynamic and non-disruptive user experience. Configuration is managed through the main module class’s `getContent()` method, storing settings in `ps_configuration`.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `controllers/front/ajax.php`
    - **Class name & parent class**: `SidcartAjaxModuleFrontController` extends `ModuleFrontController`.
    - **Responsibility**: This controller is responsible for handling all AJAX requests related to the sliding cart. When a user adds a product, updates a quantity, or removes an item from the sidebar, the JavaScript sends a request to this controller. It processes the cart modification using PrestaShop’s core `Cart` class and then returns an updated cart summary (usually HTML fragments or JSON data) to the front-end JavaScript, which then refreshes the sidebar content. This ensures real-time updates without full page reloads.
- **Back-Office Admin Controllers**: None. All configuration is handled within the main module’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

The module does not define any custom `ObjectModel` classes or dedicated classes in the `classes/` directory. Its core logic resides within the `sidcart.php` file and the `ajax.php` front controller, interacting directly with PrestaShop’s native `Cart` and `Product` classes.

### 4.4 JavaScript Assets (`views/js/`)

- `sidcart/views/js/sidcart.js`
  - **Scope**: Front-office.
  - **Details**: This is the primary JavaScript file for the module.
    - It listens for “add to cart” events (e.g., clicks on buttons with specific classes like `.add-to-cart`).
    - It intercepts the default “add to cart” behavior and instead triggers the sliding sidebar.
    - It handles the AJAX communication with `controllers/front/ajax.php` to update the cart contents.
    - It manages the display and animation of the sidebar (sliding in/out).
    - It binds event listeners for quantity changes and remove buttons within the sidebar itself, sending further AJAX requests to update the cart.
    - It likely uses `jQuery` for DOM manipulation and AJAX calls, common in PrestaShop 1.7.x and 8.x.
    - It may also listen to `prestashop.on('updateCart', ...)` or similar events to ensure the sidebar reflects changes made by other modules or core PrestaShop functionality.

### 4.5 CSS Stylesheets (`views/css/`)

- `sidcart/views/css/sidcart-right.css`

  - **Scope**: Front-office customer styling.
  - **Details**: This stylesheet defines the visual appearance and positioning of the sliding sidebar when it appears from the right side of the screen.
    - It includes rules for the sidebar’s width, background, z-index, and initial `right` position (e.g., `right: -300px;` to hide it).
    - It defines the transition properties for smooth sliding animations (e.g., `transition: right 0.3s ease-in-out;`).
    - It styles the overlay that appears behind the sidebar when it’s open.
    - It contains specific rules for mobile responsiveness, adjusting the sidebar’s width or position on smaller screens.
    - **Key CSS class selectors**: `.sidcart-wrapper`, `.sidcart-content`, `.sidcart-overlay`, `.sidcart-open`.
- `sidcart/views/css/sidcart.css`

  - **Scope**: Front-office customer styling.
  - **Details**: This stylesheet contains general styling rules for the elements *inside* the sliding cart, regardless of whether it slides from the left or right.
    - It styles the product list items (`.sidcart-product-line`).
    - It styles product images, names, prices, attributes, quantity input fields, and remove buttons.
    - It styles the cart summary sections (subtotal, shipping, total).
    - It styles the “Continue Shopping” and “Proceed to Checkout” buttons.
    - **Key CSS class selectors**: `.sidcart-product-image`, `.sidcart-product-name`, `.sidcart-product-price`, `.sidcart-qty-input`, `.sidcart-remove-button`, `.sidcart-summary`, `.sidcart-buttons`.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - `sidcart/views/templates/hook/product-line.tpl`
    - **Hook**: This template is not directly hooked but is rendered dynamically by the AJAX controller (`ajax.php`) to represent a single product entry within the sliding cart.
    - **Output**: Renders the HTML for one product, including its image, name, attributes, price, quantity input, and remove button, based on the module’s configuration settings.
  - `sidcart/views/templates/hook/sidcart.tpl`
    - **Hook**: This template is likely rendered by the `displayHeader` or `displayNav2` hook (or similar) to inject the main structure of the sliding sidebar into the page. It might initially be hidden and then revealed by JavaScript.
    - **Output**: Contains the main HTML structure for the entire sliding sidebar, including the container, the product list area, the cart summary, and the action buttons. It acts as the wrapper for the dynamically loaded `product-line.tpl` content.
- **Admin templates (`views/templates/admin/`)**: None.
- **Front-office templates (`views/templates/front/`)**:

  - `sidcart/views/templates/modal.tpl`
    - **Hook**: This template is likely a fallback or an alternative structure for a modal-like display, or it might be used for a specific part of the sidebar (e.g., a confirmation message). Given the module’s description, it’s less likely to be the primary sliding panel itself but could be a component within it or a legacy template.
    - **Output**: Renders a generic modal or popup structure. Developers should verify its actual usage within the `sidcart.js` or `ajax.php` logic.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  The module does not create any custom SQL tables. All configuration settings are stored in PrestaShop’s `ps_configuration` table using keys like `sc_ajaxInfo`, `sc_continueshopping`, `sc_pimage`, `sc_total`, `sc_subtotals_tax`, `sc_subtotals`, `sc_shipping`, `sc_remove`, `sc_qty_change`, `sc_price`, `sc_pname`, `sc_attributes`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Used to include the module’s CSS and JavaScript files (`sidcart.css`, `sidcart-right.css`, `sidcart.js`) and potentially to inject the initial, hidden HTML structure of the sidebar. |
| `actionAdminControllerSetMedia` | When an admin controller is initialized and its media assets are being set. | Used to include any necessary CSS/JS for the module’s configuration page in the Back Office. |
| `displayNav2` | In the navigation bar, typically near the cart icon. | Used to inject a small cart summary (e.g., number of items, total price) or to attach the event listener to the existing cart icon that triggers the sidebar. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Sliding sidebar cart” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
