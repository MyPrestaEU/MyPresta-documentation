---
title: "Sticky Cart Bar FREE - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Sticky Cart Bar FREE PrestaShop module by MyPresta.eu."
sidebar:
  label: "Sticky Cart Bar FREE - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Sticky Cart Bar FREE Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/sticky-cart-bar-free.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/sticky-cart-bar-free/)
>
> ---


# Sticky Cart Bar FREE

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Sticky Cart Bar FREE)

This is the main configuration screen where you control how the sticky cart bar behaves and appears on your product pages.

#### **Enable Sticky Cart Bar**

- **What this setting does:** This is the master switch to turn the entire sticky cart bar functionality on or off for your store.
- **Effect of changing this setting:**
  - *When enabled (YES):* The sticky cart bar will appear on product pages according to your other settings when customers scroll past the main “Add to Cart” button.
  - *When disabled (NO):* The sticky cart bar will not appear on any product pages, effectively deactivating the module.
- **Recommended value:** YES (to utilize the module’s benefits).
- **Merchant scenario / example:** If you’re testing the module or want to temporarily disable it without uninstalling, set this to NO. For live operation, it should be YES.

#### **Position of Sticky Cart Bar**

- **What this setting does:** Determines where the sticky bar will “stick” on the customer’s screen – either at the top or the bottom.
- **Effect of changing this setting:**
  - *When set to “Top”:* The sticky bar will appear at the very top of the browser window, below the header.
  - *When set to “Bottom”:* The sticky bar will appear at the very bottom of the browser window, above the footer.
- **Recommended value:** “Bottom” (often less intrusive, as it doesn’t cover the main navigation or logo). However, “Top” can be more prominent. Test both to see what works best for your theme and audience.
- **Merchant scenario / example:** If your store has a very busy header or a top-fixed menu, placing the sticky bar at the “Bottom” might prevent visual clutter. If you want maximum visibility for the “Add to Cart” button, “Top” might be preferred.

#### **Display on Mobile Devices**

- **What this setting does:** Controls whether the sticky cart bar is shown to customers browsing your store on smartphones or other mobile devices.
- **Effect of changing this setting:**
  - *When enabled (YES):* The sticky cart bar will be active and visible on mobile product pages.
  - *When disabled (NO):* The sticky cart bar will not appear on mobile devices, only on desktop/tablet.
- **Recommended value:** YES (Mobile users scroll a lot, and this feature is highly beneficial for them).
- **Merchant scenario / example:** Given the limited screen space on mobile, keeping the “Add to Cart” button visible is even more critical. Only disable this if you encounter specific layout conflicts with your mobile theme.

#### **Display on Desktop Devices**

- **What this setting does:** Controls whether the sticky cart bar is shown to customers browsing your store on desktop computers or larger tablet screens.
- **Effect of changing this setting:**
  - *When enabled (YES):* The sticky cart bar will be active and visible on desktop product pages.
  - *When disabled (NO):* The sticky cart bar will not appear on desktop devices, only on mobile (if enabled).
- **Recommended value:** YES (Even on desktop, long product pages benefit from this feature).
- **Merchant scenario / example:** Most stores will want this enabled for all device types to maximize conversion potential.

#### **Hide Original “Add to Cart” Button**

- **What this setting does:** This option allows you to hide the original “Add to Cart” button on the product page once the sticky bar appears.
- **Effect of changing this setting:**
  - *When enabled (YES):* When the sticky bar is visible, the original “Add to Cart” button on the product page will be hidden. This can reduce visual redundancy.
  - *When disabled (NO):* Both the sticky bar’s “Add to Cart” button and the original “Add to Cart” button will be visible simultaneously (when the original is in view).
- **Recommended value:** NO (Generally, it’s safer to keep the original button visible if it’s in the viewport, as some customers might prefer it. Hiding it might cause confusion if the sticky bar disappears quickly).
- **Merchant scenario / example:** If you find the dual “Add to Cart” buttons visually distracting or confusing when the sticky bar is active, you might enable this. Otherwise, leave it disabled.

#### **Theme Compatibility**

- **What this setting does:** This setting helps the module adapt its styling and behavior to different PrestaShop themes, specifically Classic and Hummingbird (the default theme for PrestaShop 8+).
- **Effect of changing this setting:**
  - *When set to “Classic”:* The module will load CSS and JavaScript optimized for the PrestaShop Classic theme and themes based on it.
  - *When set to “Hummingbird”:* The module will load CSS and JavaScript optimized for the PrestaShop Hummingbird theme (PrestaShop 8.x and 9.x default) and themes based on it.
- **Recommended value:** Select the theme that your store is currently using. If you are on PrestaShop 8.x or 9.x, it’s likely “Hummingbird”. If you are on PrestaShop 1.7.x and using the default theme, it’s “Classic”. If you use a custom theme, try both to see which one integrates better.
- **Merchant scenario / example:** If your store is on PrestaShop 8.1 and you select “Classic”, the sticky bar might not look or function correctly. Always match this to your active theme.

#### **Pro Version Teaser**

- **What this setting does:** This section is a promotional area for the “Sticky Cart Bar PRO” module, offering advanced features not available in the FREE version. It doesn’t affect the functionality of the FREE module.
- **Effect of changing this setting:** No direct effect on the FREE module’s behavior. It provides information about upgrading.
- **Recommended value:** N/A (Informational only).
- **Merchant scenario / example:** If you find the FREE module beneficial and need more control over targeting, design, or specific product exclusions, you can review the PRO version features here.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable Sticky Cart Bar | YES | Master switch for the module. YES activates the sticky bar. |
| Module Configuration | Position of Sticky Cart Bar | Bottom | Determines if the bar sticks to the top or bottom of the screen. |
| Module Configuration | Display on Mobile Devices | YES | Controls visibility on smartphones/tablets. YES is recommended. |
| Module Configuration | Display on Desktop Devices | YES | Controls visibility on desktop computers. YES is recommended. |
| Module Configuration | Hide Original “Add to Cart” Button | NO | Hides the original button when the sticky bar is active. NO is generally safer. |
| Module Configuration | Theme Compatibility | Hummingbird (for PS 8/9) | Ensures correct styling and functionality for your active theme. Match your theme. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The sticky cart bar isn’t appearing on my product pages.**
A:

- **Check “Enable Sticky Cart Bar”**: Ensure this setting is set to YES in the module configuration.
- **Check “Theme Compatibility”**: Make sure you’ve selected the correct theme (Classic or Hummingbird) that matches your store’s active theme. Incorrect selection can prevent the bar from loading.
- **Clear Cache**: Go to **Advanced Parameters > Performance** in your PrestaShop back office and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes, old cache files prevent new module changes from appearing.
- **Scroll Past Original Button**: Remember, the bar only appears when you scroll past the original “Add to Cart” button. Make sure you’re scrolling far enough down the page.
- **Check Device Settings**: Ensure “Display on Mobile Devices” and/or “Display on Desktop Devices” are enabled for the device you are testing on.

**Q2: The sticky cart bar looks strange or misaligned with my custom theme.**
A:

- **Theme Compatibility**: Double-check that you’ve selected the correct “Theme Compatibility” option in the module settings. If you have a highly customized theme, it might behave differently. Try switching between “Classic” and “Hummingbird” to see if one works better.
- **Custom CSS (Developer Needed)**: If the issue persists, your custom theme might have conflicting CSS styles. A web developer can inspect the page using browser developer tools and write a few lines of custom CSS to adjust the sticky bar’s appearance. This usually involves overriding existing styles in your theme’s `custom.css` file.

**Q3: The “Add to Cart” button in the sticky bar doesn’t work.**
A:

- **Clear Cache**: As with display issues, clearing your PrestaShop cache (**Advanced Parameters > Performance**) can resolve JavaScript-related problems.
- **Theme Compatibility**: Ensure the correct theme is selected. The JavaScript might not initialize correctly if the wrong theme is chosen.
- **Browser Console Errors (Developer Needed)**: Ask your web developer to check the browser’s JavaScript console for any errors. Conflicts with other modules or theme JavaScript can sometimes prevent the button from functioning.

**Q4: Can I customize the colors or content of the sticky bar?**
A:

- The FREE version of the module offers limited styling options (primarily adapting to your theme). For advanced customization like changing colors, fonts, adding custom text, or more granular control over what information is displayed, you would typically need to upgrade to the **Sticky Cart Bar PRO** module.
- For minor visual tweaks in the FREE version, a web developer can use custom CSS to override the default styles.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The Sticky Cart Bar FREE module follows a standard PrestaShop module architecture, primarily leveraging the `Module` class for installation, uninstallation, and configuration. It integrates with the front-office through hooks, dynamically injecting a sticky bar based on user scroll behavior. The module uses a combination of Smarty templates for structure, CSS for styling, and JavaScript for the sticky functionality and interaction with the main “Add to Cart” button. Compatibility with different PrestaShop themes (Classic vs. Hummingbird) is handled by loading theme-specific assets.

### 4.2 Controllers (`controllers/`)

This module does not utilize custom Front-Office or Back-Office Admin Controllers. All configuration is handled via the main module’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

- `stickycartbarfree/classes/index.php`:
  - This is typically an empty file used to prevent directory listing, a common security practice in PrestaShop modules. It contains no functional code.
- `stickycartbarfree/classes/ScbfCompatibility.php`:
  - **Class Name**: `ScbfCompatibility`
  - **Parent Class**: None (standalone utility class)
  - **Responsibility**: This class likely contains static helper methods to handle compatibility differences between various PrestaShop versions or themes. It might abstract away differences in how product data is retrieved or how assets are registered, ensuring the module works across supported environments. It does not interact with a specific database table directly but might query `ps_configuration` for theme information.
  - **Key Public Methods**: Likely static methods for checking theme context, PrestaShop version, or retrieving configuration values in a compatible way.

### 4.4 JavaScript Assets (`views/js/`)

- `stickycartbarfree/views/js/front.js`:
  - **Scope**: Front-office.
  - **Description**: This is the core JavaScript file responsible for the sticky behavior of the cart bar.
  - **Functionality**:
    - **Event Listeners**: Binds to the `scroll` event on the window to detect when the user scrolls.
    - **DOM Manipulation**:
      - Calculates the position of the original “Add to Cart” button (`#add_to_cart` or similar selector).
      - Monitors the scroll position relative to the original button.
      - Adds/removes a CSS class (e.g., `is-visible`) to the sticky cart bar container (`#sticky-cart-bar`) to show or hide it.
      - Potentially hides the original “Add to Cart” button if the corresponding module setting is enabled.
    - **Interaction**: Handles clicks on the “Add to Cart” button within the sticky bar, likely mimicking the behavior of the original button (e.g., submitting the product form, making an AJAX call to add to cart).
    - **Responsiveness**: May include logic to re-evaluate positions on `resize` events.
    - **PrestaShop Events**: Likely uses `prestashop.on('updateProduct', ...)` or similar events to update the sticky bar’s content (price, quantity, attributes) when product options are changed on the page.

### 4.5 CSS Stylesheets (`views/css/`)

- `stickycartbarfree/views/css/admin-config.css`:
  - **Scope**: Back-office admin form styling.
  - **Description**: Contains styles specifically for the module’s configuration page in the PrestaShop back office, ensuring a consistent and user-friendly admin interface.
  - **Main UI components**: Styles form elements, labels, buttons, and potentially specific layout elements within the `getContent()` output.
- `stickycartbarfree/views/css/admin-pro-teaser.css`:
  - **Scope**: Back-office admin form styling.
  - **Description**: Styles for the promotional content related to the PRO version of the module displayed on the configuration page.
  - **Main UI components**: Styles teaser boxes, upgrade buttons, feature lists, and preview images for the PRO version.
- `stickycartbarfree/views/css/front-classic.css`:
  - **Scope**: Front-office customer styling (Classic theme).
  - **Description**: Provides specific styling adjustments for the sticky cart bar when the “Classic” theme compatibility option is selected. This ensures the bar integrates visually with the Classic theme’s design.
  - **Key CSS class selectors**: Targets elements within `sticky-cart-bar` to match Classic theme fonts, colors, spacing, and button styles.
- `stickycartbarfree/views/css/front-hummingbird.css`:
  - **Scope**: Front-office customer styling (Hummingbird theme).
  - **Description**: Provides specific styling adjustments for the sticky cart bar when the “Hummingbird” theme compatibility option is selected. This ensures the bar integrates visually with the PrestaShop 8.x/9.x default theme.
  - **Key CSS class selectors**: Targets elements within `sticky-cart-bar` to match Hummingbird theme fonts, colors, spacing, and button styles.
- `stickycartbarfree/views/css/front.css`:
  - **Scope**: Front-office customer styling (general).
  - **Description**: Contains the base, common styles for the sticky cart bar that apply regardless of the selected theme compatibility. This includes core positioning, visibility, and responsiveness.
  - **Key CSS class selectors**: Defines `#sticky-cart-bar` properties like `position: fixed`, `z-index`, `width`, `padding`, `background-color`, and responsive media queries.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - `stickycartbarfree/views/templates/hook/sticky-cart-bar-classic.tpl`: Rendered when “Classic” theme compatibility is selected. Contains the main structure for the sticky bar, tailored for the Classic theme’s HTML and CSS expectations.
  - `stickycartbarfree/views/templates/hook/sticky-cart-bar-hummingbird.tpl`: Rendered when “Hummingbird” theme compatibility is selected. Contains the main structure for the sticky bar, tailored for the Hummingbird theme’s HTML and CSS expectations.
  - `stickycartbarfree/views/templates/hook/sticky-cart-bar-inner.tpl`: This template likely contains the core content of the sticky bar (product name, price, quantity input, add to cart button). It’s probably included by `sticky-cart-bar-classic.tpl` and `sticky-cart-bar-hummingbird.tpl` to avoid code duplication.
  - `stickycartbarfree/views/templates/hook/sticky-cart-bar.tpl`: This might be a wrapper template or a fallback, or it could be the main entry point that conditionally includes `sticky-cart-bar-classic.tpl` or `sticky-cart-bar-hummingbird.tpl` based on configuration.
  - **Purpose**: These templates are typically hooked into `displayFooter` or `displayBeforeBodyClosingTag` to ensure the sticky bar HTML is present on product pages. They output the HTML structure for the sticky bar, populated with product data passed from the module.
- **Admin templates (`views/templates/admin/`)**:

  - `stickycartbarfree/views/templates/admin/configure.tpl`: This is the main template for the module’s configuration page in the Back Office. It renders all the settings, input fields, and options defined in the module’s `getContent()` method.
  - `stickycartbarfree/views/templates/admin/pro-teaser-intro.tpl`: Renders the introductory part of the PRO version teaser on the configuration page.
  - `stickycartbarfree/views/templates/admin/pro-teaser-preview.tpl`: Renders a preview or visual representation of the PRO version features.
  - `stickycartbarfree/views/templates/admin/pro-teaser.tpl`: The main template for the PRO version teaser section, likely including the intro and preview templates.
  - **Purpose**: These templates provide the user interface for the module’s settings and promotional content within the PrestaShop Back Office.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create any custom SQL tables.
  - Configuration settings are stored in the standard PrestaShop `ps_configuration` table, with keys typically prefixed by `SCBF_` (e.g., `SCBF_ENABLE`, `SCBF_POSITION`).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Used to register CSS and JavaScript assets (`front.js`, `front.css`, theme-specific CSS) for the front-office. |
| `displayFooter` | Before the closing `</body>` tag on every page. | Used to inject the main HTML structure of the sticky cart bar (`sticky-cart-bar.tpl` or its variants) into the page. |
| `actionFrontControllerSetMedia` | After media (CSS/JS) has been set by the front controller. | Alternative hook for registering assets, ensuring they are loaded correctly. |
| `actionProductUpdate` | After a product is updated in the back office. | (Likely not used in FREE version, but common for modules that need to clear cache or re-index product data). |
| `actionCartUpdateQuantity` | When a product quantity is updated in the cart. | (Likely not used in FREE version, but could be used to update the sticky bar’s quantity selector if it were more interactive). |
| `actionAjaxDieProduct` | When an AJAX request related to product data dies. | (Could be used for debugging or specific AJAX interactions). |

## 5. Official Support & Updates

For official updates, technical support, and to explore advanced features available in the PRO version of the module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist you with any issues or questions regarding the Sticky Cart Bar FREE module.
