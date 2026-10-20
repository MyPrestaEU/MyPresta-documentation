---
title: "Last orders slider - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Last orders slider PrestaShop module by MyPresta.eu."
sidebar:
  label: "Last orders slider - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Last orders slider Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/last-orders-slider.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/last-orders-slider/)
>
> ---


# Last orders slider

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.6+, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient and are usually enabled by default on most PrestaShop-compatible hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the “Last orders slider” module. You can access it by navigating to **Modules > Module Manager** and clicking “Configure” next to the “Last orders slider” module.

#### General Settings

- **What this setting does:** This section controls the fundamental behavior and appearance of your order slider.
- **Effect of changing this setting:** Adjusting these will directly impact how the slider looks, where it appears, and what information it displays to your customers.

| Setting / Option | What this setting does | Effect of changing this setting | Recommended value | Merchant scenario / example |
| --- | --- | --- | --- | --- |
| **Enable module** | Turns the entire slider functionality on or off. | *When enabled:* The slider will appear on your front office based on other settings. *When disabled:* The slider will not be visible to customers. | YES | You want to temporarily hide the slider for maintenance or a special campaign. |
| **Number of orders to display** | Determines how many recent orders the slider will cycle through. | *When set to 5:* The slider will show information for the 5 most recent orders. *When set to 10:* It will show 10. | 5-10 (depending on order volume) | If you have a very high volume of orders, showing more might be overwhelming. If you have fewer orders, showing more ensures there’s always content. |
| **Order states to display** | Selects which order statuses (e.g., “Payment accepted,” “Delivered”) are considered “recent orders” for the slider. | *When “Payment accepted” is selected:* Only orders that have reached this status will appear. *When “Canceled” is selected:* Canceled orders might appear (not recommended for social proof). | “Payment accepted”, “Processing in progress”, “Delivered” | You only want to show orders that are confirmed and being processed or have been successfully delivered, to build positive trust. |
| **Display customer name** | Controls whether the customer’s first name and last initial are shown. | *When enabled:* “John D. from New York…” *When disabled:* “Someone from New York…” | YES | Showing a partial name adds a personal touch and makes the orders feel more real, enhancing social proof. |
| **Display customer city** | Controls whether the customer’s city is shown. | *When enabled:* “…from New York just bought…” *When disabled:* “…just bought…” | YES | Showing the city adds a layer of authenticity and can resonate with local customers. |
| **Display product name** | Controls whether the name of the purchased product is shown. | *When enabled:* “…just bought a T-Shirt.” *When disabled:* “…just placed an order.” | YES | Showing the product name makes the purchase more tangible and can highlight popular items. |
| **Display product image** | Controls whether a small image of the purchased product is shown. | *When enabled:* A small thumbnail of the product will appear next to the text. *When disabled:* Only text will be displayed. | YES | Visuals are engaging. A product image makes the slider more attractive and informative. |
| **Animation speed (milliseconds)** | Sets how fast the slider transitions between different orders. | *Lower value (e.g., 3000):* Faster transitions, orders change every 3 seconds. *Higher value (e.g., 8000):* Slower transitions, orders change every 8 seconds. | 5000 (5 seconds) | A moderate speed keeps the slider dynamic without being too fast to read or too slow to update. |
| **Text color** | Sets the color of the text displayed in the slider. | *When set to #000000 (black):* Text will be black. *When set to #FF0000 (red):* Text will be red. | #FFFFFF (white) or a color contrasting with your background | Choose a color that stands out against your chosen background color and matches your brand’s aesthetic. |
| **Background color** | Sets the background color of the slider bar. | *When set to #FFFFFF (white):* The slider background will be white. *When set to #000000 (black):* The slider background will be black. | #000000 (black) or a color contrasting with your theme | Choose a color that makes the slider visible and complements your store’s design. |
| **Hook to display the slider** | Selects where in your PrestaShop theme the slider will appear. | *When “displayTop” is selected:* The slider appears near the top of your store. *When “displayFooter” is selected:* The slider appears at the bottom. | displayTop or displayNavFullWidth | Choose a prominent location where customers will easily see it without obstructing critical content. |

#### 2.1.1 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable module | YES | Turns the slider on/off. |
| Module Configuration | Number of orders to display | 5-10 | Controls how many recent orders are shown. |
| Module Configuration | Order states to display | Payment accepted, Processing, Delivered | Filters orders by their status for display. |
| Module Configuration | Display customer name | YES | Shows customer’s first name and last initial. |
| Module Configuration | Display customer city | YES | Shows the customer’s city. |
| Module Configuration | Display product name | YES | Shows the name of the purchased product. |
| Module Configuration | Display product image | YES | Shows a small image of the purchased product. |
| Module Configuration | Animation speed (milliseconds) | 5000 | Sets the transition speed between orders. |
| Module Configuration | Text color | #FFFFFF (white) | Defines the color of the text in the slider. |
| Module Configuration | Background color | #000000 (black) | Defines the background color of the slider. |
| Module Configuration | Hook to display the slider | displayTop / displayNavFullWidth | Determines the position of the slider in your theme. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The slider isn’t showing up on my store. What should I do?**
A:

- **Check Module Status:** Go to **Modules > Module Manager** and ensure “Last orders slider” is installed and enabled.
- **Verify Hook Selection:** In the module’s configuration, double-check that you’ve selected a valid “Hook to display the slider” (e.g., `displayTop`, `displayNavFullWidth`). Some hooks might not be present or active in all themes.
- **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes, PrestaShop’s cache prevents new content from appearing immediately.
- **Check Order States:** Ensure you have selected at least one “Order state to display” that has recent orders associated with it. If no orders match the selected states, the slider will be empty.
- **Theme Compatibility:** While the module is designed for broad compatibility, very heavily customized themes might require minor adjustments. If all else fails, contact MyPresta.eu support.

**Q2: The slider is showing, but the colors don’t match my theme.**
A:

- **Adjust Colors in Configuration:** Go to the module’s configuration page. Use the “Text color” and “Background color” settings to select colors that complement your store’s design. You can use a color picker tool (available online or as browser extensions) to find the exact hex codes from your theme.
- **Custom CSS (Advanced):** If the module’s color options aren’t enough, your webmaster can add custom CSS rules to your theme’s stylesheet to override the module’s default styles. (See Section 7.5 for developer details).

**Q3: The slider is empty or not updating with new orders.**
A:

- **Order States:** Ensure that the “Order states to display” setting includes the statuses of your most recent orders (e.g., “Payment accepted”, “Delivered”). If your recent orders are in a status not selected, they won’t appear.
- **Recent Orders:** The module displays *recent* orders. If your store hasn’t had any orders in a while, or if the “Number of orders to display” is set too low, it might appear empty.
- **Cache:** Again, clearing your PrestaShop cache (**Advanced Parameters > Performance**) can help ensure the module fetches the latest data.

**Q4: How do I translate the text in the slider to other languages?**
A:

- **PrestaShop Translation Tool:** Go to **International > Translations**.
- Select “Installed modules translations”, choose your theme, and then select your language.
- Find the “Last orders slider” module in the list. You will be able to translate any hardcoded strings (like “just bought” or “from”) that the module uses.
- **Dynamic Content:** Customer names, cities, and product names are pulled directly from your store’s data and will appear in the language they were entered or configured in your product catalog.

**Q5: The slider is too fast/slow or shows too many/few orders.**
A:

- **Animation Speed:** Adjust the “Animation speed (milliseconds)” setting in the module configuration. A higher number means slower transitions.
- **Number of Orders:** Modify the “Number of orders to display” setting to control how many unique orders are cycled through. Experiment with these values to find the perfect balance for your store’s traffic and order volume.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a technical deep dive into the “Last orders slider” module, intended for developers, webmasters, and technical agencies.

### 4.1 Architecture Overview

The “Last orders slider” module (`lastord`) is a standard PrestaShop module primarily designed to display dynamic content in the front office. It leverages PrestaShop’s hook system to inject its content into various parts of the theme. The core logic resides within the main module file (`index.php`), which handles configuration, data retrieval, and template rendering. It does not introduce custom controllers or complex ObjectModels, relying instead on direct database queries (via `Db::getInstance()`) to fetch order data and Smarty templates for presentation. Styling is managed through a dedicated CSS file.

### 4.2 Controllers (`controllers/`)

This module does **not** utilize custom Front-Office or Back-Office Admin Controllers. All configuration is handled via the `getContent()` method within the main module file, and front-office rendering is done directly through hook methods.

### 4.3 Core Classes & Models (`classes/`)

This module does **not** define any custom classes or ObjectModels within the `classes/` directory. All data fetching and business logic are encapsulated within the `Lastord` class in `index.php`.

### 4.4 JavaScript Assets (`views/js/`)

This module does **not** include any custom JavaScript files. The animation and slider functionality are likely handled either by CSS animations or a very lightweight, inline script within the template, or by a third-party library already loaded by PrestaShop.

### 4.5 CSS Stylesheets (`views/css/`)

- **`lastord/views/css/lastord.css`**
  - **Scope:** Front-office customer styling.
  - **Main UI components and containers it styles:** This stylesheet is responsible for the visual appearance of the order slider bar itself, including its positioning, background, text styles, and potentially the animation properties.
  - **Key CSS class selectors developers can override in their theme:**
    - `.lastord_wrapper`: The main container for the entire slider.
    - `.lastord_item`: Individual order item within the slider.
    - `.lastord_text`: The text content (customer, product, city).
    - `.lastord_image`: The product image container.
    - `@keyframes` rules (if any are defined for animation).
      Developers can override these selectors in their theme’s `custom.css` or `theme.css` to match their specific design requirements.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - **`lastord/views/templates/hook/lo_orders.tpl`**
    - **Hook:** This is the primary template rendered by the module’s `hook` methods (e.g., `hookDisplayTop`, `hookDisplayNavFullWidth`, `hookDisplayFooter`, etc.).
    - **Purpose:** It contains the HTML structure for the slider wrapper and iterates through the `$orders` variable (passed from the module’s PHP logic) to display each recent order. It includes conditional logic to show/hide customer name, city, product name, and image based on module configuration. It also applies inline styles for text and background colors.
  - **`lastord/views/templates/hook/displayBanner.tpl`**
    - **Hook:** `displayBanner`
    - **Purpose:** This template likely acts as a wrapper or direct inclusion point for `lo_orders.tpl` when the module is hooked to `displayBanner`. It ensures the slider content is rendered correctly within this specific hook.
  - **`lastord/views/templates/hook/displayNavFullWidth.tpl`**
    - **Hook:** `displayNavFullWidth`
    - **Purpose:** Similar to `displayBanner.tpl`, this template is used to render the `lo_orders.tpl` content when the module is hooked to `displayNavFullWidth`.
  - **`lastord/views/templates/hook/displayTop.tpl`**
    - **Hook:** `displayTop`
    - **Purpose:** This template is used to render the `lo_orders.tpl` content when the module is hooked to `displayTop`.
- **Admin templates (`views/templates/admin/`)**:

  - **`lastord/views/templates/admin/orderstates.tpl`**
    - **Purpose:** This template is used within the module’s `getContent()` method to render the list of order states checkboxes on the back-office configuration page. It iterates through available order states and displays them with their current selection status.
- **Front-office templates (`views/templates/front/`)**: None identified.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create custom SQL tables.
  - It stores its configuration settings in the `ps_configuration` table using keys such as `LASTORD_ENABLED`, `LASTORD_ORDERS_COUNT`, `LASTORD_ORDER_STATES`, `LASTORD_DISPLAY_NAME`, `LASTORD_DISPLAY_CITY`, `LASTORD_DISPLAY_PRODUCT`, `LASTORD_DISPLAY_IMAGE`, `LASTORD_ANIMATION_SPEED`, `LASTORD_TEXT_COLOR`, `LASTORD_BACKGROUND_COLOR`, `LASTORD_HOOK`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of the front office. | Used to register assets (CSS) and potentially inline JavaScript. |
| `displayTop` | Typically at the very top of the page, below the header. | Renders the slider in a prominent top position. |
| `displayNavFullWidth` | Often a full-width section above or below the main navigation. | Renders the slider in a full-width navigation area. |
| `displayBanner` | A common hook for banners, often at the very top. | Renders the slider as a banner. |
| `displayLeftColumn` | In the left sidebar. | Renders the slider in the left column. |
| `displayRightColumn` | In the right sidebar. | Renders the slider in the right column. |
| `displayFooter` | In the footer section of the page. | Renders the slider at the bottom of the page. |
| `displayProductButtons` | On the product page, near the add-to-cart button. | Renders the slider on the product page for conversion focus. |
| `displayFooterProduct` | In the footer section of the product page. | Renders the slider at the bottom of the product page. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Last orders slider” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any technical issues or questions you may have regarding the module’s functionality and integration.
