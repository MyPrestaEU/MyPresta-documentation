---
title: "Free Shipping Progress Bar for free - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Free Shipping Progress Bar for free PrestaShop module by MyPresta.eu."
sidebar:
  label: "Free Shipping Progress Bar for free - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Free Shipping Progress Bar for free Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/free-shipping-progress-bar-for-free.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/free-shipping-progress-bar-for-free/)
>
> ---


# Free Shipping Progress Bar for free

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the “Free Shipping Progress Bar for free” module. You can access it by navigating to **Modules > Module Manager** and clicking “Configure” next to the module name.

#### General Settings

- **Enable Free Shipping Progress Bar:**

  - **What this setting does:** This is the master switch to turn the entire progress bar functionality on or off for your store.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The progress bar will appear in the selected positions on your front office, and all other module settings will take effect.
    - *When disabled (NO):* The progress bar will be completely hidden from your store, regardless of other settings.
  - **Recommended value:** YES (to utilize the module’s features).
  - **Merchant scenario / example:** If you’re temporarily running a different promotion or performing maintenance, you might disable it. Otherwise, keep it enabled to encourage sales.
- **Free Shipping Threshold:**

  - **What this setting does:** This defines the exact amount (in your shop’s default currency) that a customer needs to spend to qualify for free shipping.
  - **Effect of changing this setting:**
    - *When set to a specific amount (e.g., 50.00):* The progress bar will calculate the remaining amount based on this threshold.
    - *When changed:* The target for free shipping updates instantly for all customers.
  - **Recommended value:** Set this to your store’s actual free shipping threshold. If you offer free shipping above €50, set it to 50.00.
  - **Merchant scenario / example:** If your shipping carrier offers free shipping for orders over €75, you would set this to 75.00.
- **Display Hook:**

  - **What this setting does:** This determines where on your website the free shipping progress bar will be displayed. You can choose from several common locations.
  - **Effect of changing this setting:**
    - *When set to ‘displayHeader’:* The bar will appear in the top section of your website, usually above or below your logo/menu.
    - *When set to ‘displayLeftColumn’ or ‘displayRightColumn’:* The bar will appear in the respective side column of your store.
    - *When set to ‘displayFooter’:* The bar will appear at the bottom of your website.
    - *When set to ‘displayProductButtons’ (or similar product page hook):* The bar will appear on product pages, often near the add-to-cart button.
  - **Recommended value:** ‘displayHeader’ or ‘displayProductButtons’ are often most effective for visibility and encouraging immediate action.
  - **Merchant scenario / example:** To ensure maximum visibility, you might choose `displayHeader`. If you want to encourage adding more items directly from the product page, `displayProductButtons` is a good choice.
- **Progress Bar Color:**

  - **What this setting does:** Allows you to customize the color of the progress bar itself. This helps you match it to your store’s branding.
  - **Effect of changing this setting:**
    - *When set to a specific color (e.g., #4CAF50 for green):* The bar will display in that color.
  - **Recommended value:** A color that contrasts well with your background but complements your brand’s color palette.
  - **Merchant scenario / example:** If your brand uses a lot of blue, you might choose a shade of blue or a complementary orange to make the bar stand out.
- **Background Color:**

  - **What this setting does:** Allows you to customize the background color of the progress bar container.
  - **Effect of changing this setting:**
    - *When set to a specific color (e.g., #F0F0F0 for light grey):* The background behind the progress will display in that color.
  - **Recommended value:** A subtle color that provides good contrast with the progress bar color, often a light grey or white.
  - **Merchant scenario / example:** To make the progress bar itself pop, you might use a light background color like white or a very light grey.
- **Text Color:**

  - **What this setting does:** Allows you to customize the color of the text displayed within or around the progress bar (e.g., “You are X away from free shipping!”).
  - **Effect of changing this setting:**
    - *When set to a specific color (e.g., #333333 for dark grey):* The text will display in that color.
  - **Recommended value:** A color that is easily readable against both the progress bar and its background.
  - **Merchant scenario / example:** If your progress bar is green and its background is light grey, a dark grey or black text color would ensure readability.

#### Pro Edition Teaser

This section typically contains information and links to upgrade to the “Pro” version of the module, which offers more advanced features. These are not configuration settings for the free module but rather promotional content.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable Free Shipping Progress Bar | YES | Master switch for module functionality. |
| Module Configuration | Free Shipping Threshold | Your store’s free shipping amount | Defines the target amount for free shipping. |
| Module Configuration | Display Hook | displayHeader / displayProductButtons | Determines where the bar appears in your store. |
| Module Configuration | Progress Bar Color | Customizable (e.g., #4CAF50) | Sets the color of the filled part of the progress bar. |
| Module Configuration | Background Color | Customizable (e.g., #F0F0F0) | Sets the background color of the progress bar container. |
| Module Configuration | Text Color | Customizable (e.g., #333333) | Sets the color of the text displayed with the bar. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The progress bar isn’t showing up on my store. What should I do?**
A1:

- **Check Module Status:** Go to **Modules > Module Manager** and ensure “Free Shipping Progress Bar for free” is installed and enabled.
- **Check Configuration:** Navigate to the module’s configuration page. Make sure “Enable Free Shipping Progress Bar” is set to YES. Also, verify that the “Display Hook” setting is correctly chosen and that your theme actually renders that hook (some custom themes might not).
- **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache”). Sometimes, old cache prevents new module content from appearing.
- **Theme Compatibility:** While the module is designed for standard PrestaShop themes (Classic, Hummingbird), highly customized themes might require minor adjustments. If the above steps don’t work, contact MyPresta.eu support.

**Q2: The progress bar is showing, but it’s not updating when I add items to the cart.**
A2:

- **Check JavaScript:** Ensure there are no JavaScript errors on your site that might be preventing the module’s script from running. You can check your browser’s developer console (usually F12) for errors.
- **AJAX Cart:** The module relies on PrestaShop’s AJAX cart functionality. Ensure your theme’s cart update mechanism is standard and not overriding core PrestaShop AJAX calls in a way that prevents the module from detecting changes.
- **Module Conflicts:** Temporarily disable other modules that modify cart behavior or display elements in the same hooks to check for conflicts.

**Q3: How do I change the text displayed in the progress bar (e.g., “You are X away from free shipping!”)?**
A3: The free version of the module typically uses predefined text. To customize this text, you would usually need to edit the module’s template file (`progress.tpl`). However, this requires basic knowledge of Smarty templates. For a more user-friendly way to customize text, the Pro version of the module often includes dedicated text fields in the back office.

**Q4: The progress bar looks strange or doesn’t match my theme’s styling.**
A4:

- **Module Configuration Colors:** First, use the “Progress Bar Color,” “Background Color,” and “Text Color” settings in the module’s configuration to try and match your theme.
- **CSS Conflicts:** Your theme’s CSS might be overriding the module’s default styles. A webmaster can inspect the element using browser developer tools to identify conflicting CSS rules and add custom CSS to your theme to override them. The module’s CSS files (`front.css`) can be a good starting point for identifying the selectors to target.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Free Shipping Progress Bar for free” module follows a standard PrestaShop module architecture, primarily leveraging the `Module` class for installation, uninstallation, and configuration. It uses front controllers for AJAX interactions to dynamically update the progress bar without full page reloads. The module integrates with PrestaShop’s hook system to display its content in various front-office locations and uses Smarty templates for rendering its UI. Configuration is stored in `ps_configuration` table.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `controllers/front/index.php`
    - **Class name & parent class:** `SmartFreeShippingFreeIndexModuleFrontController` extends `ModuleFrontController`.
    - **Responsibility:** This controller likely serves as a base or entry point for front-office interactions, though its specific methods might be minimal if `refresh.php` handles the primary AJAX. It could be used for initial data loading or setting up context.
  - `controllers/front/refresh.php`
    - **Class name & parent class:** `SmartFreeShippingFreeRefreshModuleFrontController` extends `ModuleFrontController`.
    - **Responsibility:** This is the core AJAX controller. It responds to requests (likely POST or GET) from the front-office JavaScript to fetch the current cart total, calculate the remaining amount for free shipping, and return the updated progress bar HTML or data. It handles currency conversion and ensures the progress bar reflects real-time cart changes.
- **Back-Office Admin Controllers**:

  - None. All configuration is handled within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

- None. The module does not define custom `ObjectModel` classes or complex business logic classes beyond what’s contained in the main module file (`index.php`) and front controllers.

### 4.4 JavaScript Assets (`views/js/`)

- `views/js/front.js`
  - **Scope:** Front-office.
  - **Details:** This script is responsible for the dynamic behavior of the progress bar.
    - It likely binds event listeners to cart update events (e.g., `prestashop.on('updateCart', ...)` or custom events triggered by theme’s AJAX cart).
    - When a cart update is detected, it makes an AJAX call to the `refresh.php` front controller to get the updated progress bar status.
    - It then updates the DOM to reflect the new progress (e.g., width of the progress bar, remaining amount text).
    - May include logic for initial rendering on page load and handling different display hooks.

### 4.5 CSS Stylesheets (`views/css/`)

- `views/css/admin-config.css`

  - **Scope:** Back-office admin form styling.
  - **Details:** Contains styles specifically for the module’s configuration page in the PrestaShop back office, ensuring a clean and user-friendly layout for settings.
  - **Key CSS class selectors:** Likely targets elements within the module’s configuration form, such as `.panel`, `.form-group`, `.control-label`, etc., specific to the module’s HTML structure.
- `views/css/admin-pro-teaser.css`

  - **Scope:** Back-office admin form styling.
  - **Details:** Styles for the promotional content related to the “Pro” version of the module, ensuring it looks appealing and distinct within the configuration page.
  - **Key CSS class selectors:** Targets elements like `.pro-teaser-block`, `.pro-feature-list`, etc.
- `views/css/front.css`

  - **Scope:** Front-office customer styling.
  - **Details:** Contains the core CSS for the free shipping progress bar itself, including its layout, colors, animations, and responsiveness.
  - **Key CSS class selectors:** Targets elements like `#smartfreeshippingfree-progress-bar-container`, `.progress-bar-fill`, `.progress-bar-text`, etc. Developers can override these classes in their theme’s `custom.css` or `theme.css` to match their specific design.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Admin templates (`views/templates/admin/`)**:

  - `views/templates/admin/configure.tpl`
    - **Purpose:** This is the main Smarty template for the module’s configuration page in the Back Office. It renders the form fields, switches, and input elements for all the module settings. It likely includes the `get-pro-hero.tpl` and `get-pro.tpl` for promotional content.
  - `views/templates/admin/get-pro-hero.tpl`
    - **Purpose:** Renders a prominent “hero” section promoting the Pro version of the module, often at the top of the configuration page.
  - `views/templates/admin/get-pro.tpl`
    - **Purpose:** Renders a detailed section outlining the features and benefits of upgrading to the Pro version, typically including a call to action.
- **Hook templates (`views/templates/hook/`)**:

  - `views/templates/hook/progress.tpl`
    - **Purpose:** This is the primary front-office template. It renders the HTML structure of the free shipping progress bar, including the container, the filled progress section, and the dynamic text (e.g., “You are X away from free shipping!”). This template is rendered by the `displayHook` method of the main module file.
- **Front-office templates (`views/templates/front/`)**:

  - None. The front-office display is handled via the `hook/progress.tpl`.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create custom SQL tables. All configuration settings are stored in the standard PrestaShop `ps_configuration` table, using keys prefixed with `SMARTFREESHIPPINGFREE_` (e.g., `SMARTFREESHIPPINGFREE_ENABLED`, `SMARTFREESHIPPINGFREE_THRESHOLD`).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page, or at the very top of the `<body>`. | Used to inject CSS/JS assets and potentially render the progress bar in the header. |
| `displayLeftColumn` | In the left column of the theme. | Alternative position for displaying the progress bar. |
| `displayRightColumn` | In the right column of the theme. | Alternative position for displaying the progress bar. |
| `displayFooter` | In the footer section of the theme. | Alternative, less intrusive position for displaying the progress bar. |
| `displayProductButtons` (or similar) | On the product page, often near the add-to-cart button. | Specific placement to encourage adding items directly from product pages. |
| `actionCartSave` | After a cart is saved (e.g., item added/removed). | Internal hook (not for display) used by the module to trigger AJAX updates for the progress bar. |
| `actionFrontControllerSetMedia` | Before a front controller renders its output, to add CSS/JS. | Used to register `front.js` and `front.css` for front-office pages. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the “Free Shipping Progress Bar for free” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any technical issues or questions you may have.
