---
title: "Free Shipping Progress Bar Pro - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Free Shipping Progress Bar Pro PrestaShop module by MyPresta.eu."
sidebar:
  label: "Free Shipping Progress Bar Pro - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Free Shipping Progress Bar Pro Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/free-shipping-progress-bar-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/free-shipping-progress-bar-pro/)
>
> ---


# Free Shipping Progress Bar Pro

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required and are usually enabled by default on most modern hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration area where you’ll set up all the rules, appearance, and behavior of your Free Shipping Progress Bar. The page is designed to be intuitive, guiding you through various sections.

#### General Settings

- **What this setting does:** Controls the overall activation and basic behavior of the progress bar.
- **Effect of changing this setting:**
  - *Enable/Disable Module:* Turns the entire progress bar functionality on or off for your store.
  - *Display Position:* Determines where the progress bar appears on your front office (e.g., Header, Footer, Product Page, Cart Page).
  - *Sticky Bar:* Makes the bar “stick” to the top or bottom of the screen as the user scrolls, keeping it visible.
- **Recommended value:**
  - *Enable Module:* YES (to activate the feature).
  - *Display Position:* Header (often the most effective for visibility).
  - *Sticky Bar:* YES (for maximum impact).
- **Merchant scenario / example:** You want the progress bar to always be visible at the top of your store to constantly remind customers about free shipping. You would enable the module, set the display position to “Header,” and enable “Sticky Bar.”

#### Free Shipping Thresholds

- **What this setting does:** Defines the amount customers need to spend to qualify for free shipping. This is the core of the module’s functionality. You can set a default threshold and then override it with specific rules for countries or customer groups.
- **Effect of changing this setting:**
  - *Default Threshold:* Sets the base amount for all customers not covered by specific rules.
  - *Country-Specific Thresholds:* Allows you to set different free shipping amounts for customers from particular countries (e.g., higher for international shipping).
  - *Customer Group-Specific Thresholds:* Tailor thresholds for different customer groups (e.g., lower for VIP customers, higher for wholesalers).
- **Recommended value:** Start with a default threshold that makes sense for your average order value and shipping costs. Then, add specific rules as needed.
- **Merchant scenario / example:** Your default free shipping is $100. However, for customers in Canada, you want it to be $150 due to higher shipping costs. You’d set the default to $100 and then add a country rule for Canada at $150. For your “Wholesale” customer group, you might set it to $500.

#### Visual Designer

- **What this setting does:** Provides a user-friendly interface to customize the look and feel of your progress bar without any coding. You can change colors, fonts, bar styles, and more.
- **Effect of changing this setting:** Directly impacts the visual appearance of the progress bar on your front office.
  - *Colors:* Adjust background, text, and progress bar fill colors to match your brand.
  - *Fonts & Sizes:* Customize text styles for messages.
  - *Bar Style:* Choose between different visual styles for the progress bar itself (e.g., rounded, flat).
  - *Animations:* Add subtle animations for a more engaging experience.
- **Recommended value:** Experiment to find a design that is visually appealing, clearly visible, and consistent with your store’s branding.
- **Merchant scenario / example:** Your store uses a specific shade of blue and a clean, modern font. You would use the visual designer to set the progress bar’s background to that blue, the text to white, and choose a sans-serif font to match your theme.

#### Dynamic Messages

- **What this setting does:** Allows you to create custom messages that appear in the progress bar, changing based on the customer’s progress towards free shipping. You can use placeholders to insert dynamic values like the remaining amount.
- **Effect of changing this setting:**
  - *Messages for “Not yet qualified”:* Displays when the customer has not reached the threshold.
  - *Messages for “Qualified”:* Displays once the customer has reached or exceeded the threshold.
  - *Placeholders:* Using `[amount_left]`, `[total_cart]`, `[free_shipping_threshold]`, `[currency_symbol]` will dynamically insert these values into your messages.
- **Recommended value:** Keep messages clear, concise, and encouraging. Use placeholders to make them dynamic and personal.
- **Merchant scenario / example:**
  - *Not qualified:* “Spend [amount\_left] more to get FREE Shipping!”
  - *Qualified:* “Congratulations! Your order qualifies for FREE Shipping!”
    This clearly communicates the goal and celebrates achievement.

#### A/B Testing & Analytics

- **What this setting does:** Enables you to run A/B tests on different progress bar configurations (e.g., different messages, colors, or thresholds) and track their performance.
- **Effect of changing this setting:**
  - *Enables A/B Test Mode:* Allows you to create variations of your progress bar.
  - *Tracks Conversions:* Records how different variations impact your conversion rates and average order value.
- **Recommended value:** Enable this feature once your basic setup is stable. Use it to continuously optimize your progress bar’s effectiveness.
- **Merchant scenario / example:** You want to test if “Spend $X more for FREE Shipping!” performs better than “Unlock FREE Shipping with just $X more!”. You would set up two variations and let the module track which one leads to more sales.

#### Advanced Settings

- **What this setting does:** Contains options for more technical aspects, such as caching, compatibility with specific themes, or custom CSS/JS.
- **Effect of changing this setting:** Can impact performance, theme integration, or allow for highly specific customizations.
  - *Cache Settings:* Improves loading speed by caching bar content.
  - *Custom CSS/JS:* Allows developers to add their own styling or scripts.
- **Recommended value:** Generally, leave these at their default unless you have a specific need or are advised by a developer.
- **Merchant scenario / example:** Your custom theme has a unique header structure, and the progress bar isn’t aligning perfectly. A developer might use the “Custom CSS” field to add specific styling rules to fix the alignment.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **General Settings** | Enable Module | YES | Activates/deactivates the entire progress bar feature. |
|  | Display Position | Header | Where the bar appears (Header, Footer, Product, Cart, Columns). |
|  | Sticky Bar | YES | Makes the bar stick to the top/bottom of the screen. |
| **Free Shipping Thresholds** | Default Threshold | Your store’s free shipping amount | Base amount for free shipping. |
|  | Country Rules | As needed | Overrides default for specific countries. |
|  | Customer Group Rules | As needed | Overrides default for specific customer groups. |
| **Visual Designer** | Bar Background Color | Theme-dependent | Changes the background color of the bar. |
|  | Progress Fill Color | Theme-dependent | Changes the color of the filled progress section. |
|  | Text Color | Theme-dependent | Changes the color of the messages. |
|  | Font Family / Size | Theme-dependent | Customizes text appearance. |
|  | Bar Style | Default | Visual design of the progress bar itself. |
| **Dynamic Messages** | Message - Not Qualified | “Spend [amount\_left] more for FREE Shipping!” | Message displayed when goal is not met. |
|  | Message - Qualified | “Congratulations! Your order qualifies for FREE Shipping!” | Message displayed when goal is met. |
| **A/B Testing & Analytics** | Enable A/B Testing | NO (initially) | Allows running tests on different bar configurations. |
|  | Track Conversions | YES (when A/B testing) | Records performance of different bar versions. |
| **Advanced Settings** | Enable Cache | YES | Improves loading speed of the bar. |
|  | Custom CSS | Leave empty | For advanced styling overrides by developers. |
|  | Custom JS | Leave empty | For advanced script additions by developers. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The progress bar isn’t showing up on my store, or it’s not updating.**
**A1:**

- **Check Module Status:** First, ensure the module is enabled in your PrestaShop Back Office under **Modules > Module Manager**.
- **Verify Display Position:** Go to the module’s configuration and check the “Display Position” setting. Make sure it’s set to a visible hook (e.g., Header, Footer). If you’ve chosen a column hook, ensure your theme actually displays that column.
- **Clear Cache:** PrestaShop often caches content. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Also, clear your browser’s cache.
- **Theme Compatibility:** Some highly customized themes might require minor adjustments. If the issue persists after clearing cache, contact MyPresta.eu support with details about your theme.

**Q2: The progress bar looks strange or doesn’t match my theme’s design.**
**A2:**

- **Use Visual Designer:** The module includes a “Visual Designer” section in its configuration. Use this to adjust colors, fonts, and styles to better match your theme.
- **Custom CSS:** If the visual designer isn’t enough, your webmaster or a developer can use the “Custom CSS” field in the module’s advanced settings to add specific styling rules that override the default.
- **Theme Cache:** After making design changes, always clear your PrestaShop cache (**Advanced Parameters > Performance**) and your browser cache.

**Q3: The free shipping amount is incorrect or not changing for certain customers.**
**A3:**

- **Check Threshold Rules:** Go to the “Free Shipping Thresholds” section in the module configuration.
  - Verify the “Default Threshold” is correct.
  - Check if any “Country-Specific Thresholds” or “Customer Group-Specific Thresholds” are overriding the default for the affected customers. Ensure the rules are set up correctly for the relevant countries/groups.
- **Currency:** Ensure your default currency and the currency used for the threshold match.
- **Cart Calculation:** The module relies on PrestaShop’s cart total. Ensure your products have correct prices and tax rules are applied as expected.

**Q4: How do I translate the messages into different languages for my international customers?**
**A4:**

- The module supports PrestaShop’s native translation system.
- Go to **International > Translations** in your PrestaShop Back Office.
- Select “Installed modules translations,” choose your theme, and then select the “Free Shipping Progress Bar Pro” module.
- You can then translate all the dynamic messages and other text displayed by the module into your desired languages. Remember to save your changes.

**Q5: The progress bar is not showing on mobile devices, or it’s not responsive.**
**A5:**

- The module is designed to be fully responsive.
- **Clear Cache:** As always, clear PrestaShop cache (**Advanced Parameters > Performance**) and your mobile browser’s cache.
- **Check Display Position:** Ensure the chosen display position (e.g., Header) is one that your theme renders prominently on mobile. Some themes might hide certain elements on smaller screens.
- **Theme Conflicts:** Very rarely, a highly customized mobile theme might have conflicting CSS. If the issue persists, consult with MyPresta.eu support or your webmaster.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the Free Shipping Progress Bar Pro module, intended for developers, webmasters, and technical agencies.

### 4.1 Architecture Overview

The `Free Shipping Progress Bar Pro` module (`smartfreeshippingpro`) follows the standard PrestaShop module architecture, primarily leveraging hooks for front-office display and a dedicated `ModuleFrontController` for AJAX interactions. Configuration is managed via the main module class’s `getContent()` method, rendering a Smarty template for the back-office interface. It uses PrestaShop’s `Configuration` class to store settings and relies on core PrestaShop services for cart and currency information. The module emphasizes a visual configuration approach with dedicated JS for the admin interface.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `smartfreeshippingpro/controllers/front/index.php`
    - **Class Name:** `SmartFreeShippingProIndexModuleFrontController` (likely, based on file naming convention)
    - **Parent Class:** `ModuleFrontController`
    - **Responsibility:** This controller likely serves as a base or entry point for front-office interactions, though its specific methods might be minimal if `refresh.php` handles the primary AJAX. It might be responsible for initial data setup or non-AJAX front-office logic.
  - `smartfreeshippingpro/controllers/front/refresh.php`
    - **Class Name:** `SmartFreeShippingProRefreshModuleFrontController`
    - **Parent Class:** `ModuleFrontController`
    - **Responsibility:** This is the critical AJAX endpoint. It responds to requests (e.g., from `front.js`) to update the free shipping progress bar. It fetches the current cart total, calculates the remaining amount for free shipping based on configured thresholds (default, country, group rules), and returns the updated progress data and messages, typically in JSON format. This controller is responsible for the real-time updates of the bar.
- **Back-Office Admin Controllers**:

  - No dedicated `AdminController` files are present. All back-office configuration is handled within the `getContent()` method of the main module file (`index.php`).

### 4.3 Core Classes & Models (`classes/`)

No custom classes extending `ObjectModel` or other core PrestaShop classes are explicitly listed in the provided inventory. The module likely relies on PrestaShop’s built-in `Cart`, `Context`, `Configuration`, `Currency`, and `Country` classes for its logic.

### 4.4 JavaScript Assets (`views/js/`)

- `smartfreeshippingpro/views/js/admin-config.js`
  - **Scope:** Back-office.
  - **Description:** Likely handles general configuration form interactions, saving settings, and potentially form validation for the main module configuration page.
- `smartfreeshippingpro/views/js/admin-placeholders.js`
  - **Scope:** Back-office.
  - **Description:** Manages the dynamic insertion of placeholders (e.g., `[amount_left]`, `[total_cart]`) into the message input fields within the admin configuration, making it easier for merchants to craft dynamic messages.
- `smartfreeshippingpro/views/js/admin-threshold-picker.js`
  - **Scope:** Back-office.
  - **Description:** Handles the logic for adding, editing, and removing country-specific and customer group-specific free shipping thresholds. This would involve dynamic form elements for selecting countries/groups and inputting amounts.
- `smartfreeshippingpro/views/js/admin-visual-designer.js`
  - **Scope:** Back-office.
  - **Description:** Powers the visual customization interface. It likely uses JavaScript to dynamically update a preview of the progress bar as the admin changes colors, fonts, and styles, providing immediate visual feedback.
- `smartfreeshippingpro/views/js/admin.js`
  - **Scope:** Back-office.
  - **Description:** A general-purpose admin script that might initialize other admin-specific JS files, handle global admin events, or provide utility functions for the back-office interface.
- `smartfreeshippingpro/views/js/front.js`
  - **Scope:** Front-office.
  - **Description:** This is the core front-end script.
    - **Event Listeners:** Binds to `prestashop.on('updateCart', ...)` or similar events to detect changes in the shopping cart (add, remove, quantity update).
    - **AJAX Calls:** Triggers AJAX requests to the `refresh.php` front controller to get updated progress bar data.
    - **DOM Manipulation:** Updates the progress bar’s width, text messages, and potentially its visibility based on the AJAX response.
    - **Animations:** May include logic for smooth transitions or animations of the progress bar.
    - **Sticky Bar Logic:** If the sticky bar feature is enabled, this script would handle the CSS positioning (`position: fixed`) and potentially scroll event listeners to manage its visibility.

### 4.5 CSS Stylesheets (`views/css/`)

- `smartfreeshippingpro/views/css/admin-config.css`
  - **Scope:** Back-office admin form styling.
  - **Description:** Styles for the general layout and elements of the module’s main configuration page.
- `smartfreeshippingpro/views/css/admin-threshold-picker.css`
  - **Scope:** Back-office admin form styling.
  - **Description:** Specific styles for the country and customer group threshold selection interfaces.
- `smartfreeshippingpro/views/css/admin-visual-designer.css`
  - **Scope:** Back-office admin form styling.
  - **Description:** Styles for the visual designer interface, including color pickers, preview elements, and layout.
- `smartfreeshippingpro/views/css/admin.css`
  - **Scope:** Back-office admin form styling.
  - **Description:** General admin styles, potentially including common elements used across different admin sections of the module.
- `smartfreeshippingpro/views/css/front.css`
  - **Scope:** Front-office customer styling.
  - **Description:**
    - Main UI components: Styles the progress bar container, the progress fill, and the text messages.
    - Key CSS class selectors: Likely includes classes like `.smartfreeshippingpro-bar`, `.smartfreeshippingpro-progress`, `.smartfreeshippingpro-message`, `.smartfreeshippingpro-sticky`. Developers can override these in their theme’s `custom.css` or by adding custom CSS in the module’s advanced settings.
    - Responsive design rules for various screen sizes.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Admin templates (`views/templates/admin/`)**:

  - `smartfreeshippingpro/views/templates/admin/configure.tpl`
    - **Description:** The main template for the module’s configuration page in the Back Office. It renders the entire form, including general settings, links to other sub-templates for specific sections (like visual designer, threshold picker).
  - `smartfreeshippingpro/views/templates/admin/country-priority.tpl`
    - **Description:** Likely a sub-template used within `configure.tpl` to manage the priority of country-specific rules if multiple rules could apply (e.g., a customer is in a country with a specific rule, but also part of a group with another rule).
  - `smartfreeshippingpro/views/templates/admin/country-rules-picker.tpl`
    - **Description:** A sub-template for the interface where administrators define and manage free shipping thresholds based on customer countries.
  - `smartfreeshippingpro/views/templates/admin/group-rules-picker.tpl`
    - **Description:** A sub-template for the interface where administrators define and manage free shipping thresholds based on customer groups.
  - `smartfreeshippingpro/views/templates/admin/visual-designer.tpl`
    - **Description:** A sub-template for the visual designer interface, containing the HTML structure for the preview bar and the input fields (color pickers, sliders, text inputs) for customization.
- **Hook templates (`views/templates/hook/`)**:

  - `smartfreeshippingpro/views/templates/hook/progress.tpl`
    - **Description:** This is the primary front-office template. It contains the HTML structure for the free shipping progress bar itself (e.g., a `div` for the bar, a `div` for the progress fill, and a `span` for the dynamic message).
    - **Rendered in hooks:** This template is rendered in various front-office hooks such as `displayHeader`, `displayFooter`, `displayProductButtons`, `displayShoppingCart`, `displayLeftColumn`, `displayRightColumn`, depending on the merchant’s configuration.
    - **Visual block output:** Outputs the complete, styled progress bar with its dynamic message.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not appear to create custom SQL tables based on the inventory.
  - Configuration records are stored in PrestaShop’s `ps_configuration` table. Keys would typically follow a pattern like `SMARTFREESHIPPINGPRO_ENABLED`, `SMARTFREESHIPPINGPRO_THRESHOLD_DEFAULT`, `SMARTFREESHIPPINGPRO_COLOR_BAR`, `SMARTFREESHIPPINGPRO_MESSAGE_NOT_QUALIFIED`, etc.
  - Country and group-specific rules might be stored as serialized arrays within a single `ps_configuration` entry or potentially in a simple custom table if the structure is complex, though the inventory suggests `ObjectModel` is not used.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Renders in the `<head>` section or at the very top of the `<body>`. | Injects CSS/JS assets and/or the progress bar HTML (especially for sticky bars). |
| `displayFooter` | Renders at the bottom of the `<body>` before the closing tag. | Injects CSS/JS assets and/or the progress bar HTML. |
| `displayLeftColumn` | Renders content in the left sidebar of the store. | Displays the progress bar in the left column. |
| `displayRightColumn` | Renders content in the right sidebar of the store. | Displays the progress bar in the right column. |
| `displayProductButtons` | Renders near the “Add to Cart” button on product pages. | Displays the progress bar directly on product pages. |
| `displayShoppingCart` | Renders on the shopping cart summary page. | Displays the progress bar on the cart page to encourage more purchases. |
| `actionFrontControllerSetMedia` | Executed when a front controller sets its media (CSS/JS). | Injects front-office specific CSS and JavaScript files. |
| `actionAdminControllerSetMedia` | Executed when an admin controller sets its media (CSS/JS). | Injects back-office specific CSS and JavaScript files for the configuration page. |
| `actionCartSave` | Executed after a cart is saved (e.g., item added/removed). | Triggers the front-office JS to refresh the progress bar via AJAX. |
| `actionObjectCartUpdateAfter` | Executed after a cart object has been updated. | Similar to `actionCartSave`, used to trigger updates. |
| `actionObjectOrderAddAfter` | Executed after a new order has been added. | Potentially used for A/B testing analytics to track conversions. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for your Free Shipping Progress Bar Pro module, please refer to your customer account at MyPresta.eu. Our team is dedicated to ensuring your module runs smoothly and effectively.

- **Access Updates:** Log in to your MyPresta.eu account and navigate to your order history and downloads section to get the most recent version of the module.
- **Technical Support:** If you encounter any issues, have questions, or require assistance with configuration, please open a support ticket through your MyPresta.eu customer account. Our expert team will be happy to help.
