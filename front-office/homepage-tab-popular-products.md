---
title: "Homepage tab popular products - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Homepage tab popular products PrestaShop module by MyPresta.eu."
sidebar:
  label: "Homepage tab popular products - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Homepage tab popular products Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-tab-popular-products.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/homepage-tab-popular-products/)
>
> ---


# Homepage tab popular products

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click the “Configure” button next to the “Homepage tab popular products” module in the Module Manager. This will take you to its main configuration screen.

#### General Settings

- **What this setting does:** This module primarily focuses on displaying popular products. The configuration screen for this module is quite straightforward, often including standard MyPresta.eu update notification settings. The core functionality of displaying “popular products” is usually handled automatically by PrestaShop’s internal logic for identifying popular items (e.g., based on sales, views, or a combination).
- **Effect of changing this setting:**
  - **`mypresta_updates` (Enable/Disable MyPresta.eu updates notifications):**
    - *When enabled:* You will receive notifications in your PrestaShop back office when new versions or important updates for MyPresta.eu modules (including this one) are available. This helps you keep your modules secure and up-to-date with the latest features and bug fixes.
    - *When disabled:* You will not receive these notifications. You would need to manually check your MyPresta.eu account for updates.
  - **`update_` and `updatev_` (Internal update check parameters):** These are typically internal settings used by MyPresta.eu modules to manage and track update checks. They are not usually meant for direct merchant interaction.
- **Recommended value:**
  - For `mypresta_updates`: **YES** (Enabled). Keeping this enabled ensures you are always informed about critical updates, improving your store’s security and performance.
  - For `update_` and `updatev_`: Leave as default. These are internal and should not be changed.
- **Merchant scenario / example:**
  - You want to ensure your store is always running the latest, most secure versions of your MyPresta.eu modules. By enabling update notifications, you’ll see a clear alert in your PrestaShop admin panel whenever an update for “Homepage tab popular products” (or any other MyPresta.eu module) is released. This allows you to promptly download and install the new version, benefiting from improvements without having to constantly check manually.

#### Important Note on “Popular Products” Logic:

This module leverages PrestaShop’s existing mechanisms to determine what constitutes a “popular product.” Typically, PrestaShop identifies popular products based on sales data (products with the most orders) or views. The module itself doesn’t usually offer specific settings to define “popularity” (e.g., “show products sold in the last 30 days” or “products with X views”). It relies on PrestaShop’s core functionality for this. If you need to influence which products appear as “popular,” you would generally need to increase their sales or visibility through other marketing efforts.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | MyPresta.eu updates notifications | Enabled (YES) | Receive alerts for module updates, ensuring security and new features. |
| Module Configuration Page | `update_` | Default | Internal setting for update tracking. Leave unchanged. |
| Module Configuration Page | `updatev_` | Default | Internal setting for update tracking. Leave unchanged. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The “Popular Products” tab is not showing on my homepage.**
A1:

- **Check Module Status:** Go to **Modules > Module Manager** and ensure “Homepage tab popular products” is installed and enabled.
- **Clear Cache:** Sometimes, PrestaShop’s cache prevents new content from appearing. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” if available).
- **Theme Compatibility:** While the module is designed for PrestaShop 1.7.x, 8.x, and 9.x, some highly customized themes might require minor adjustments. If clearing the cache doesn’t work, contact your theme developer or MyPresta.eu support.
- **Hook Check:** Ensure the `displayHome` hook is active and rendered by your theme.

**Q2: The products displayed in the “Popular Products” tab don’t seem “popular” to me.**
A2:

- **PrestaShop’s Definition:** The module relies on PrestaShop’s internal logic for identifying popular products, which is typically based on sales volume or product views. If your store is new or has low sales, the “popular” list might not be as dynamic.
- **Data Refresh:** Ensure your store has recent sales data. The “popularity” is calculated over time.
- **Cache:** Clear your PrestaShop cache as described in Q1.

**Q3: Can I change the title of the tab (e.g., from “Popular Products” to “Our Bestsellers”)?**
A3:

- This module typically uses a default title. To change it, you would usually need to edit the module’s translation files or, in some cases, directly modify the template file.
  - Go to **International > Translations**.
  - Select “Installed modules translations,” your theme, and your language.
  - Find the “Homepage tab popular products” module and look for the tab title string.
  - If it’s not translatable this way, it might require a small code change in `homepagetabs.tpl` (see Section 7).

**Q4: The styling of the products in the tab doesn’t match my theme.**
A4:

- The module uses its own CSS (`homepagetabs.css`). Your theme’s CSS might override some styles, or the module’s styles might conflict.
- **Custom CSS:** The best approach is to add custom CSS to your theme’s `custom.css` file (or equivalent) to override the module’s styles and make it match your theme perfectly. Use your browser’s developer tools to inspect the elements and identify the CSS selectors used by the module.

**Q5: How do I translate the tab title or other module texts into different languages?**
A5:

- Go to **International > Translations** in your PrestaShop back office.
- Select “Installed modules translations,” then choose your theme and the language you want to translate.
- Find the “Homepage tab popular products” module in the list and you should be able to edit the text strings associated with it.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the “Homepage tab popular products” module, intended for developers, webmasters, and technical agencies.

### 4.1 Architecture Overview

The `Homepage tab popular products` module (`homepagetabs`) is a straightforward PrestaShop module primarily designed to extend the `displayHome` hook. It follows a standard PrestaShop MVC-like pattern for modules, where the main module file (`homepagetabs.php`) handles installation, uninstallation, configuration, and hook registration. The module injects a custom tab and its content into the homepage, leveraging PrestaShop’s existing product fetching mechanisms for “popular products.”

### 4.2 Controllers (`controllers/`)

This module does not contain any custom Front-Office or Back-Office Admin Controllers. All logic is encapsulated within the main module file and its associated templates and assets.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or extend `ObjectModel`. It operates by utilizing PrestaShop’s core functionalities for product retrieval.

### 4.4 JavaScript Assets (`views/js/`)

- **`homepagetabs/views/js/homepagetabs.js`**
  - **Scope:** Front-office.
  - **Purpose:** This file likely contains JavaScript logic to handle the tab switching functionality on the homepage. It might listen for click events on the “Popular Products” tab, show/hide the corresponding product content, and potentially interact with other homepage tabs to ensure only one tab’s content is visible at a time. It may also include logic for responsive behavior or lazy loading of product images within the tab.
  - **Key Functionality:**
    - Event listeners for tab clicks.
    - DOM manipulation to toggle visibility of product lists.
    - Potentially integrates with PrestaShop’s default tab behavior or custom theme tab systems.

### 4.5 CSS Stylesheets (`views/css/`)

- **`homepagetabs/views/css/homepagetabs.css`**
  - **Scope:** Front-office customer styling.
  - **Purpose:** This stylesheet defines the visual appearance of the “Popular Products” tab and the product listings within it. It ensures the tab is properly positioned, styled, and that the product grid/list is presented neatly.
  - **Main UI Components Styled:**
    - The tab header itself (e.g., `.homepagetabs-tab-title`).
    - The container for the popular products (e.g., `.homepagetabs-products-container`).
    - Individual product elements within the tab (e.g., product images, names, prices, buttons).
    - Responsive adjustments for different screen sizes.
  - **Key CSS Class Selectors for Overriding:** Developers can inspect the generated HTML to find specific selectors. Common ones might include:
    - `.homepagetabs-tab`
    - `.homepagetabs-tab-content`
    - `.homepagetabs-product-list`
    - `.homepagetabs-product-item`

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - **`homepagetabs/views/templates/hook/homepagetabs.tpl`**
    - **Hook:** `displayHome`
    - **Purpose:** This is the primary front-office template. It’s responsible for rendering the “Popular Products” tab header and the container for the product list. It will typically iterate over a collection of popular products passed to it by the module’s `hookDisplayHome` method and render each product using a standard PrestaShop product-list partial (or a custom one defined within the module). This template is where the actual HTML structure for the tab and its content is generated.
- **Admin templates (`views/templates/admin/`)**:
  - **`homepagetabs/views/templates/admin/homepagetabs.tpl`**
    - **Purpose:** This template renders the module’s configuration form in the PrestaShop Back Office. It displays the settings for update notifications (`mypresta_updates`) and potentially other module-specific options if they were to be added. It uses PrestaShop’s helper form classes to generate the input fields and save buttons.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: This module does not create any custom database tables. It stores its configuration settings (like `mypresta_updates`) in the standard `ps_configuration` table.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHome` | Renders content on the store’s homepage. | Injects the “Popular Products” tab and its content into the main homepage area. |
| `displayHeader` | Executed in the `<head>` section of every page. | Used to enqueue the module’s CSS (`homepagetabs.css`) and JavaScript (`homepagetabs.js`) files, ensuring they are loaded correctly for the front-office display. |

## 5. Official Support & Updates

For official updates, technical support, and any inquiries regarding the “Homepage tab popular products” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team and resources are available to assist you with installation, configuration, and troubleshooting.
