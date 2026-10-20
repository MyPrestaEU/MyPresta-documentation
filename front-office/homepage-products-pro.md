---
title: "Homepage Products Pro - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Homepage Products Pro PrestaShop module by MyPresta.eu."
sidebar:
  label: "Homepage Products Pro - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Homepage Products Pro Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-products-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/homepage-products-pro/)
>
> ---


# Homepage Products Pro

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” will take you to the main settings page for “Homepage Products Pro.” This is where you’ll control the global behavior and features of your product blocks.

#### General Settings

- **Enable Internal Tabs**

  - **What this setting does:** This controls whether the module can create its own custom tabs on the homepage, similar to PrestaShop’s default “Popular Products” or “New Products” tabs.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* You will be able to create new product blocks that appear as clickable tabs on your homepage, allowing customers to switch between different product collections.
    - *When disabled (No):* The module will only display product blocks as standalone sections (e.g., horizontal carousels or column blocks), without the tabbed interface.
  - **Recommended value:** **Yes** (to leverage the full power of the module for dynamic homepage content).
  - **Merchant scenario / example:** You want to show “New Arrivals,” “Best Sellers,” and “Seasonal Picks” all on your homepage without making it too long. Enabling internal tabs allows you to put each of these into its own tab.
- **Use rich text editor**

  - **What this setting does:** Determines if a visual (WYSIWYG) editor is available when you’re creating or editing product block descriptions or titles, making it easier to format text.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* You’ll get a user-friendly editor (like TinyMCE) with formatting options (bold, italics, links, etc.) for text fields within the module.
    - *When disabled (No):* You’ll have a plain text input field, requiring you to use basic HTML if you want any formatting.
  - **Recommended value:** **Yes** (for easier content creation and better visual control).
  - **Merchant scenario / example:** You want to add a short, styled introduction above a product block, like “Discover our **exclusive** collection!” The rich text editor makes this simple.
- **Load lightslider**

  - **What this setting does:** Controls whether the module loads the LightSlider JavaScript library, which is used for creating responsive content carousels and sliders.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* The LightSlider library will be loaded, allowing your product blocks to display as interactive, touch-enabled carousels. This is typically required for the module’s visual effects.
    - *When disabled (No):* The LightSlider library will not be loaded. If your theme or another module provides similar carousel functionality, you might disable this to avoid conflicts or redundant loading. However, if no other carousel solution is present, your product blocks might display as static grids or lists.
  - **Recommended value:** **Yes** (unless you have a specific reason or conflict, as it’s essential for the module’s carousel features).
  - **Merchant scenario / example:** You want your “New Products” block to be a sleek, horizontally scrolling carousel. This setting ensures the necessary script is loaded for that functionality.
- **Enable analytics**

  - **What this setting does:** Activates or deactivates the module’s internal tracking of product block performance, such as views and clicks.
  - **Effect of changing this setting:**
    - *When enabled (Enabled):* The module will collect data on how often your product blocks are viewed and clicked, providing insights into their effectiveness.
    - *When disabled (Disabled):* No performance data will be collected or displayed within the module’s dashboard.
  - **Recommended value:** **Enabled** (to gain valuable insights into which product blocks are performing best).
  - **Merchant scenario / example:** You want to know if your “Best Sellers” block is getting more engagement than your “On Sale” block. Enabling analytics provides this data.
- **Analytics period**

  - **What this setting does:** Defines the time frame for which the module’s internal analytics data will be displayed.
  - **Effect of changing this setting:** Changes the range of data shown in the analytics reports.
  - **Options:** Last 7 days, Last 30 days, Last 90 days, Last 180 days, Last 365 days.
  - **Recommended value:** **Last 30 days** (a good balance for recent trends, but adjust based on your reporting needs).
  - **Merchant scenario / example:** You want to review the performance of your homepage product blocks over the past month to see if a recent promotion had an impact.
- **Enable block cache**

  - **What this setting does:** Activates a caching mechanism for the product blocks generated by the module. Caching stores a temporary version of the block, so it doesn’t have to be rebuilt every time a customer visits the page.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* Product blocks will load faster for customers, as the server serves a cached version. This can significantly improve page load times and server performance, especially on high-traffic stores.
    - *When disabled (No):* Product blocks will be generated dynamically on every page load, which can be slower but ensures the absolute latest product data is always displayed (e.g., stock levels, prices).
  - **Recommended value:** **Yes** (for performance benefits, unless you have very rapidly changing product data that must be real-time).
  - **Merchant scenario / example:** Your homepage is getting a lot of traffic, and you want to ensure it loads as quickly as possible. Enabling cache will speed up the display of your product blocks.
- **Cache TTL (seconds)**

  - **What this setting does:** Defines how long (in seconds) a cached version of a product block remains valid before it’s refreshed. (TTL stands for “Time To Live”).
  - **Effect of changing this setting:**
    - *Higher value:* Blocks are cached longer, leading to better performance but potentially showing slightly outdated product information (e.g., if a price changes, it might not update on the homepage until the cache expires).
    - *Lower value:* Blocks are refreshed more frequently, ensuring more up-to-date information but with slightly less performance gain.
  - **Recommended value:** **3600** (1 hour) or **7200** (2 hours) is a good starting point. Adjust based on how frequently your product data changes and how critical real-time updates are.
  - **Merchant scenario / example:** You have a flash sale where prices change every hour. You might set the Cache TTL to 3600 seconds (1 hour) to ensure prices update relatively quickly on the homepage.
- **Auto-detect theme**

  - **What this setting does:** Attempts to automatically detect your active PrestaShop theme to apply appropriate styling and template overrides for better visual integration.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* The module tries to adapt its output to match your theme’s structure and styling, potentially using theme-specific templates (e.g., `firezy-products17.tpl`). This often results in a more seamless look.
    - *When disabled (No):* The module will use its default, generic templates and styling, which might not perfectly match your theme’s design. You might need to manually select a theme or apply custom CSS.
  - **Recommended value:** **Yes** (for the best out-of-the-box visual integration).
  - **Merchant scenario / example:** You’ve installed the module, and the product blocks don’t quite look right with your custom theme. Enabling this might automatically fix the styling.

#### Hidden/Advanced Settings (Internal Configuration Keys)

These are typically not exposed directly as user-facing settings but are configuration values the module uses internally. They are listed here for completeness and developer understanding.

- `update_`, `mypresta_updates`: Related to module update checks and notifications from MyPresta.eu.
- `hpp_analytics_enabled`: Corresponds to “Enable analytics” setting.
- `hpp_cache_enabled`: Corresponds to “Enable block cache” setting.
- `hpp_cache_ttl`: Corresponds to “Cache TTL (seconds)” setting.
- `hpp_theme_auto_detect`: Corresponds to “Auto-detect theme” setting.
- `hpp_analytics_period`: Corresponds to “Analytics period” setting.
- `hpp_carousel_native`: Likely an internal flag for carousel type, possibly related to LightSlider.
- `PS_NB_DAYS_NEW_PRODUCT`: PrestaShop’s default setting for how many days a product is considered “new.” The module might use this for “New Products” blocks.
- `PS_CURRENCY_DEFAULT`: PrestaShop’s default currency ID.
- `hpp_internal_tabs`: Corresponds to “Enable Internal Tabs” setting.
- `hpp_bxslider`: An older carousel library, possibly a legacy setting or fallback.
- `PS_LANG_DEFAULT`: PrestaShop’s default language ID.
- `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: PrestaShop’s setting for allowing employees to change form language.
- `hpp_rich_text`: Corresponds to “Use rich text editor” setting.
- `hpp_theme`: Stores the detected or manually selected theme name.
- `hpp_customtplpath`: Allows specifying a custom path for templates, useful for advanced theme integration.

### 2.2 Dedicated Admin Screens & Controller Views

The “Homepage Products Pro” module extends the PrestaShop Back Office by adding a dedicated section for managing your product blocks.

- **Screen Name & Menu Location:**

  - You will find a new menu item, typically under **Modules > Homepage Products Pro** or a similar name, which will lead to the module’s dashboard.
  - This dashboard is where you create, edit, delete, and organize your product blocks.
- **Available Actions & Settings:**

  - **Product Block Listing Table:** This main view will display a list of all product blocks you have created. Each entry will show:
    - **Name:** The internal name you’ve given the block (e.g., “Homepage Best Sellers”).
    - **Title:** The public title displayed to customers (e.g., “Our Top Picks!”).
    - **Hook:** Where the block is displayed (e.g., `displayHome`, `displayHomeTabContent`, `displayLeftColumn`).
    - **Status:** Whether the block is enabled or disabled.
    - **Position:** The order in which blocks appear within the same hook.
    - **Actions:** Buttons to **Edit**, **Duplicate**, or **Delete** the block.
  - **“Add New Block” Button:** Clicking this will open a form to create a brand new product block.
  - **“Edit Block” Form:** When adding or editing a block, you’ll typically configure:
    - **Block Name:** An internal identifier (e.g., “SummerCollection2023”).
    - **Display Title:** The title customers see (e.g., “Summer Collection”).
    - **Description:** A short text that appears above the products (rich text editor available if enabled).
    - **Hook Selection:** Choose where the block appears (e.g., `displayHome`, `displayHomeTabContent` for tabs, `displayLeftColumn`).
    - **Product Selection:** This is crucial. You’ll define *which* products appear in the block. Options typically include:
      - **Specific Products:** Manually select individual products using a search tool.
      - **Products from Category:** Select one or more categories, and the module will display products from them.
      - **New Products:** Automatically display the latest products added to your store.
      - **Best Sellers:** Automatically display your store’s top-selling products.
      - **On Sale Products:** Automatically display products currently on sale.
      - **Featured Products:** Products marked as featured.
    - **Number of Products to Display:** Limit how many products are shown.
    - **Display Type:** Choose between a carousel/slider or a static grid/list.
    - **Carousel Settings:** If using a carousel, settings for items per slide, auto-play, navigation arrows, etc.
    - **Visibility/Audience Picker:** Define who sees the block (e.g., all customers, specific customer groups, specific countries).
    - **Language Specificity:** Configure titles and descriptions for different languages.
    - **Status:** Enable/Disable the individual block.
    - **Position:** Set the display order relative to other blocks in the same hook.
- **Effect of changes:**

  - **Adding a New Block:** A new product display will appear on your front-office in the chosen hook, showcasing the selected products according to your settings.
  - **Editing a Block:** Changes to titles, descriptions, product selection, display type, or settings will be immediately reflected on the front-office (subject to cache TTL if caching is enabled).
  - **Deleting a Block:** The product display will be removed from your front-office.
  - **Changing Position:** The order of blocks within a specific hook will update on the front-office.
  - **Enabling/Disabling:** Toggles the visibility of the block on your store.
- **Recommended workflow for daily store management:**

  1. **Plan your homepage layout:** Decide which product types you want to highlight (new, best sellers, specific categories, promotions).
  2. **Create new blocks:** For each planned section, go to the module’s dashboard and click “Add New Block.”
  3. **Configure each block:**
     - Give it a clear internal name (e.g., “HP\_NewArrivals”).
     - Write an engaging display title and description.
     - Select the appropriate hook (e.g., `displayHome` for main content, `displayHomeTabContent` for tabs).
     - Choose your product selection method (manual, category, new, etc.).
     - Adjust display and carousel settings.
     - Set the position to control its order.
  4. **Review on front-office:** Always check your store’s homepage after making changes to ensure everything looks and functions as expected.
  5. **Monitor analytics:** Regularly check the module’s analytics (if enabled) to understand which blocks are performing well and adjust your strategy accordingly.
  6. **Maintain and update:** As new products arrive or promotions change, update your existing blocks or create new ones to keep your homepage fresh and relevant.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Main Config | Enable Internal Tabs | Yes | Allows creation of product tabs on homepage. |
| Main Config | Use rich text editor | Yes | Provides a visual editor for text fields. |
| Main Config | Load lightslider | Yes | Enables product carousels/sliders. |
| Main Config | Enable analytics | Enabled | Tracks views and clicks for product blocks. |
| Main Config | Analytics period | Last 30 days | Sets the time frame for analytics reports. |
| Main Config | Enable block cache | Yes | Improves page load speed by caching blocks. |
| Main Config | Cache TTL (seconds) | 3600 (1 hour) | How long cached blocks remain valid. |
| Main Config | Auto-detect theme | Yes | Adapts module output to match your theme. |
| Block Management | Block Name | N/A (User Defined) | Internal identifier for your product block. |
| Block Management | Display Title | N/A (User Defined) | Public title shown to customers. |
| Block Management | Description | N/A (User Defined) | Text displayed above the product block. |
| Block Management | Hook Selection | `displayHome` / `displayHomeTabContent` | Determines where the block appears on the store. |
| Block Management | Product Selection | N/A (User Defined) | Defines which products are shown (manual, category, new, best sellers, etc.). |
| Block Management | Number of Products | N/A (User Defined) | Limits the quantity of products displayed. |
| Block Management | Display Type | Carousel / Grid | How products are visually presented. |
| Block Management | Visibility/Audience | All Customers | Restricts block visibility to specific groups/countries. |
| Block Management | Status | Enabled | Toggles the block’s visibility on the front-office. |
| Block Management | Position | N/A (User Defined) | Sets the display order of blocks within a hook. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My product blocks aren’t showing up on the homepage, or they look broken.**

- **A:**
  1. **Check Module Status:** Ensure the “Homepage Products Pro” module is enabled in **Modules > Module Manager**.
  2. **Check Block Status:** Go to the module’s configuration dashboard and verify that the specific product blocks you created are “Enabled.”
  3. **Hook Selection:** Double-check that you’ve assigned the blocks to the correct front-office hooks (e.g., `displayHome` for main content, `displayHomeTabContent` for tabs, `displayLeftColumn` for columns).
  4. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache.” Sometimes, old cached content prevents new module output from appearing.
  5. **Theme Compatibility:** If you have a custom theme, try enabling “Auto-detect theme” in the module’s main configuration. If issues persist, your theme might require minor CSS adjustments (see Q3).

**Q2: My product blocks are showing, but the products aren’t updating (e.g., old prices, out-of-stock items still visible).**

- **A:** This is usually a caching issue.
  1. **Module Cache:** In the module’s main configuration, check “Enable block cache” and “Cache TTL (seconds).” If caching is enabled, the block might be showing an older, cached version. You can temporarily disable caching, save, then re-enable it, or simply wait for the TTL to expire.
  2. **PrestaShop Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache.” This clears all PrestaShop-level caches.
  3. **Browser Cache:** Clear your browser’s cache and cookies, or view your site in an incognito/private window to ensure you’re not seeing a locally cached version.

**Q3: The product blocks appear, but the styling is off (e.g., wrong fonts, misaligned items, broken carousel).**

- **A:**
  1. **Auto-detect Theme:** In the module’s main configuration, ensure “Auto-detect theme” is enabled. This helps the module use theme-specific styling.
  2. **Load LightSlider:** If carousels are broken, ensure “Load lightslider” is enabled in the module’s configuration.
  3. **Theme Conflicts:** Custom themes sometimes have conflicting CSS or JavaScript. If you suspect this, try temporarily switching to a default PrestaShop theme (like Classic) to see if the issue resolves. If it does, your custom theme needs adjustments.
  4. **Custom CSS:** You might need to add custom CSS to your theme’s stylesheet to override the module’s default styles and match your theme. A web developer can help with this.

**Q4: I’ve created a new product block, but it’s not appearing as a tab on the homepage.**

- **A:**
  1. **Enable Internal Tabs:** In the module’s main configuration, ensure “Enable Internal Tabs” is set to “Yes.”
  2. **Correct Hook:** Make sure the product block’s **Hook Selection** is set to `displayHomeTabContent`. Blocks set to `displayHome` or columns will not appear as tabs.
  3. **Positioning:** Check the position of your tabbed blocks. If they are very low in the order, they might not appear if other modules are taking up space.

**Q5: My rich text editor isn’t working, or I can’t format text.**

- **A:**
  1. **Enable Rich Text Editor:** In the module’s main configuration, ensure “Use rich text editor” is set to “Yes.”
  2. **Browser Issues:** Try a different web browser or clear your current browser’s cache.
  3. **JavaScript Conflicts:** Occasionally, other modules or theme scripts can interfere with the rich text editor. If the problem persists, consult a developer.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical architecture and codebase of the “Homepage Products Pro” module, designed for developers, webmasters, and technical agencies.

### 4.1 Architecture Overview

The “Homepage Products Pro” module (`hpp`) follows a standard PrestaShop module architecture, primarily leveraging hooks for front-office display and a `getContent()` method for its back-office configuration. It implements a custom dashboard for managing product blocks, which are stored as configuration values or potentially in custom database tables (though no explicit `ObjectModel` classes were identified in the provided inventory, complex data is often serialized into `ps_configuration` or managed via helper classes). The module heavily relies on Smarty templates for rendering its various product blocks and admin interfaces. It integrates external libraries like LightSlider for carousels and TinyMCE for rich text editing. Analytics and caching mechanisms are built-in for performance and insights.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `hpp/controllers/front/index.php`
  - **Class Name:** `HppIndexModuleFrontController` (likely, based on file name convention)
  - **Parent Class:** `ModuleFrontController`
  - **Responsibility:** This controller likely serves as a general entry point for front-office module actions that don’t fit into specific AJAX or tracking categories. It might handle initial data loading or rendering of specific block types if not entirely hook-driven.
- `hpp/controllers/front/lazyblock.php`
  - **Class Name:** `HppLazyblockModuleFrontController`
  - **Parent Class:** `ModuleFrontController`
  - **Responsibility:** This controller is designed to handle AJAX requests for lazy-loading product blocks. When a user scrolls down or interacts with a tab, this controller would be called to fetch product data and render the HTML for a specific block, improving initial page load times. It likely takes parameters like block ID, page number, or filter criteria.
- `hpp/controllers/front/track.php`
  - **Class Name:** `HppTrackModuleFrontController`
  - **Parent Class:** `ModuleFrontController`
  - **Responsibility:** This controller is responsible for handling analytics tracking requests. When a product block is viewed or a product within a block is clicked, a request is sent to this controller to record the event, contributing to the module’s internal analytics data.

#### Back-Office Admin Controllers

No dedicated `AdminController` files were identified in the provided inventory. This suggests that the module’s back-office management (creating/editing product blocks) is handled directly within the `hpp.php` file’s `getContent()` method, potentially using PrestaShop’s `HelperForm` and `HelperList` classes, or a custom rendering approach within the module’s main configuration page.

### 4.3 Core Classes & Models (`classes/`)

No custom PHP classes extending `ObjectModel` or other core functionalities were explicitly listed in the `classes/` directory. This implies that:

- Complex data (like individual product block configurations) is likely stored as serialized arrays or JSON strings within the `ps_configuration` table, managed directly by the `hpp.php` module file.
- Alternatively, the module might use a more procedural approach or rely on helper classes defined directly within `hpp.php` or its included libraries.
- The `lib/` directory contains various helper classes and external libraries (e.g., `searchTool`, `smartyTemplatesManager`, `src`). These are likely used for specific functionalities like product search, template management, or carousel implementation, rather than defining core business entities.

### 4.4 JavaScript Assets (`views/js/`)

- `hpp/js/script.js`
  - **Scope:** Front-office.
  - **Details:** Likely contains the main front-office logic for initializing product carousels (LightSlider), handling tab switching, and general UI interactions related to the product blocks. It might also contain logic for lazy loading or basic analytics tracking.
- `hpp/js/tinymce16-force-urls.inc.js`
  - **Scope:** Back-office.
  - **Details:** A specific script for the TinyMCE rich text editor, likely to ensure URLs are correctly handled and formatted within the editor, especially in older PrestaShop 1.6 contexts.
- `hpp/lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Back-office.
  - **Details:** Provides the JavaScript functionality for an autocomplete search input, used when selecting specific products for a product block in the back-office configuration. It likely makes AJAX calls to fetch product suggestions.
- `hpp/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`
  - **Scope:** Back-office.
  - **Details:** Manages the dynamic creation, editing, and selection of Smarty templates within the back-office interface, likely for advanced users to customize block layouts.
- `hpp/lib/src/js/lightslider.js`
  - **Scope:** Front-office.
  - **Details:** The core LightSlider library, responsible for creating responsive, touch-enabled content carousels for the product blocks. It handles slide transitions, navigation, and responsiveness.
- `hpp/views/js/admin-audience-picker.js`
  - **Scope:** Back-office.
  - **Details:** Provides the interactive logic for the “Audience Picker” interface in the back-office, allowing administrators to select specific customer groups or countries for block visibility.
- `hpp/views/js/adminHppDashboard.js`
  - **Scope:** Back-office.
  - **Details:** The main JavaScript for the module’s back-office dashboard, handling interactions like adding/editing blocks, drag-and-drop reordering, and general UI management.
- `hpp/views/js/adminHppDashboardDemo.js`
  - **Scope:** Back-office.
  - **Details:** Likely contains demo-specific JavaScript for the back-office dashboard, possibly for initial setup or showcasing features, and might not be active in a production environment.
- `hpp/views/js/hpp-analytics.js`
  - **Scope:** Front-office.
  - **Details:** Handles the front-office side of analytics tracking, sending data (e.g., block views, product clicks) to the `track.php` controller via AJAX.
- `hpp/views/js/hpp-lazyload.js`
  - **Scope:** Front-office.
  - **Details:** Implements lazy loading for product blocks or their content, making AJAX calls to `lazyblock.php` when blocks enter the viewport or tabs are activated.

### 4.5 CSS Stylesheets (`views/css/`)

- `hpp/css/global.css`
  - **Scope:** Front-office.
  - **Details:** Contains general, global styles for the module’s front-office output, ensuring basic visual consistency.
- `hpp/css/homefeaturedslider.css`
  - **Scope:** Front-office.
  - **Details:** Specific styles for the home featured slider component, likely for older PrestaShop versions or specific carousel implementations.
- `hpp/css/hpp.css`
  - **Scope:** Front-office.
  - **Details:** The main front-office stylesheet for the module, defining the look and feel of product blocks, grids, and carousels.
- `hpp/css/internal-tabs.css`
  - **Scope:** Front-office.
  - **Details:** Styles specific to the internal tabbed interface on the homepage, including tab navigation and content areas.
- `hpp/css.css`
  - **Scope:** Front-office.
  - **Details:** Potentially a legacy or additional general stylesheet.
- `hpp/lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Back-office.
  - **Details:** Styles for the autocomplete search input used in the back-office for product selection.
- `hpp/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`
  - **Scope:** Back-office.
  - **Details:** Styles for the Smarty template manager interface in the back-office.
- `hpp/lib/src/css/lightslider.css`
  - **Scope:** Front-office.
  - **Details:** The core CSS for the LightSlider library, providing the base styling for the carousel component.
- `hpp/views/css/admin-audience-picker.css`
  - **Scope:** Back-office.
  - **Details:** Styles for the audience picker interface in the back-office.
- `hpp/views/css/admin-searchtool.css`
  - **Scope:** Back-office.
  - **Details:** Additional styles for the search tool in the admin panel.
- `hpp/views/css/admin_hpp.css`
  - **Scope:** Back-office.
  - **Details:** The primary stylesheet for the module’s back-office configuration and dashboard.
- `hpp/views/templates/admin/css/css.css`
  - **Scope:** Back-office.
  - **Details:** A stylesheet specifically located within the admin templates directory, likely for very specific styling needs within those templates.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

These templates are rendered when the module is hooked into specific positions in the front-office. Many are theme-specific overrides.

- `hpp/views/templates/hook/column17.tpl`
  - **Hook:** `displayLeftColumn`, `displayRightColumn` (PrestaShop 1.7.x+).
  - **Output:** Renders a product block designed for the left or right columns, typically a vertical list or small grid.
- `hpp/views/templates/hook/firezy-column17.tpl`
  - **Hook:** `displayLeftColumn`, `displayRightColumn` (PrestaShop 1.7.x+ for Firezy theme).
  - **Output:** Theme-specific override for column product blocks, tailored for the Firezy theme.
- `hpp/views/templates/hook/firezy-homeTab.tpl`
  - **Hook:** `displayHomeTab` (for Firezy theme).
  - **Output:** Renders the actual tab navigation link (e.g., “Summer Collection”) for the Firezy theme.
- `hpp/views/templates/hook/firezy-homeTabContent.tpl`
  - **Hook:** `displayHomeTabContent` (for Firezy theme).
  - **Output:** Renders the content (the product block itself) that appears when a specific tab is active, tailored for the Firezy theme.
- `hpp/views/templates/hook/firezy-internal-tabs.tpl`
  - **Hook:** `displayHome` (for Firezy theme).
  - **Output:** Renders the entire internal tabbed interface (both navigation and content wrapper) for the Firezy theme.
- `hpp/views/templates/hook/firezy-products17.tpl`
  - **Hook:** `displayHome` (for Firezy theme).
  - **Output:** Renders a general product block (carousel or grid) for the main homepage content area, tailored for the Firezy theme.
- `hpp/views/templates/hook/homeTab.tpl`
  - **Hook:** `displayHomeTab`.
  - **Output:** Renders the generic tab navigation link.
- `hpp/views/templates/hook/homeTabContent.tpl`
  - **Hook:** `displayHomeTabContent`.
  - **Output:** Renders the generic content for a tabbed product block.
- `hpp/views/templates/hook/hummingbird-column17.tpl`, `hummingbird-homeTab.tpl`, `hummingbird-homeTabContent.tpl`, `hummingbird-internal-tabs.tpl`, `hummingbird-products17.tpl`
  - **Hook:** Similar to Firezy, these are theme-specific overrides for the Hummingbird theme, providing tailored layouts for columns, tab navigation, tab content, internal tab wrappers, and general product blocks.
- `hpp/views/templates/hook/internal-tabs.tpl`
  - **Hook:** `displayHome`.
  - **Output:** Renders the generic internal tabbed interface (navigation and content wrapper).
- `hpp/views/templates/hook/products17.tpl`
  - **Hook:** `displayHome`, `displayTopColumn`.
  - **Output:** Renders a generic product block (carousel or grid) for the main homepage or top column content area (PrestaShop 1.7.x+).
- `hpp/views/templates/hook/warehouse-column17.tpl`, `warehouse-homeTab.tpl`, `warehouse-homeTabContent.tpl`, `warehouse-internal-tabs.tpl`, `warehouse-products17.tpl`
  - **Hook:** Similar to Firezy and Hummingbird, these are theme-specific overrides for the Warehouse theme, providing tailored layouts for columns, tab navigation, tab content, internal tab wrappers, and general product blocks.

#### Admin templates (`views/templates/admin/`)

These templates are used for the module’s back-office interface.

- `hpp/views/templates/admin/audience-picker.tpl`
  - **Output:** Renders the HTML for the customer group and country selection interface.
- `hpp/views/templates/admin/country-priority-picker.tpl`
  - **Output:** Renders the HTML for selecting and prioritizing countries.
- `hpp/views/templates/admin/menu.tpl`
  - **Output:** Renders the module’s specific menu or navigation within its back-office dashboard.
- `hpp/views/templates/admin/scripts.tpl`
  - **Output:** Includes JavaScript files or inline scripts specifically for the admin interface.
- `hpp/views/templates/admin/ul-li.tpl`
  - **Output:** A generic list template, possibly used for displaying lists of items or options within the admin forms.

#### Library Templates (`hpp/lib/`)

These templates are part of integrated libraries.

- `hpp/lib/searchTool/views/scripts.tpl`
  - **Output:** Includes JavaScript files or inline scripts for the search tool functionality.
- `hpp/lib/smartyTemplatesManager/tpl/example.tpl`
  - **Output:** An example template for the Smarty Templates Manager, likely for demonstration or as a base.
- `hpp/lib/smartyTemplatesManager/views/buttonManager.tpl`
  - **Output:** Renders buttons or controls for managing templates.
- `hpp/lib/smartyTemplatesManager/views/createTemplateForm.tpl`
  - **Output:** Renders the form for creating new custom templates.
- `hpp/lib/smartyTemplatesManager/views/editTemplateForm.tpl`
  - **Output:** Renders the form for editing existing custom templates.
- `hpp/lib/smartyTemplatesManager/views/mainForm.tpl`
  - **Output:** The main form for the Smarty Templates Manager interface.
- `hpp/lib/smartyTemplatesManager/views/selectInput.tpl`
  - **Output:** Renders a generic select/dropdown input field.

### 4.7 Database Schema & Hooks Map

#### Database Tables

No custom SQL files (`.sql`) were identified, and no `ObjectModel` classes were listed. This strongly suggests that the module stores its configuration data and product block definitions primarily within PrestaShop’s `ps_configuration` table.

- **`ps_configuration`**: This table will contain entries with keys like `HPP_ANALYTICS_ENABLED`, `HPP_CACHE_TTL`, `HPP_BLOCKS_DATA` (or similar, where `HPP_BLOCKS_DATA` would hold a serialized array or JSON string of all product block configurations).

#### Registered Hooks Table

The module registers itself to various PrestaShop hooks to inject its content and functionality.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Inject CSS and JS assets (e.g., LightSlider, `hpp.css`, `script.js`). |
| `actionFrontControllerSetMedia` | Before a front controller renders its output. | Add specific CSS/JS assets conditionally based on the page or controller. |
| `displayHome` | Main content area of the homepage. | Render general product blocks (carousels, grids) directly on the homepage. |
| `displayHomeTab` | Within the homepage tab navigation area. | Render the navigation links for custom product tabs. |
| `displayHomeTabContent` | Within the homepage tab content area. | Render the actual product blocks that appear when a custom tab is active. |
| `displayLeftColumn` | In the left column of pages where it’s active. | Render vertical product blocks in the left sidebar. |
| `displayRightColumn` | In the right column of pages where it’s active. | Render vertical product blocks in the right sidebar. |
| `displayTopColumn` | In the top content area, usually below the header. | Render product blocks in the top section of the homepage. |
| `displayBackOfficeHeader` | In the `<head>` section of every back-office page. | Inject CSS and JS assets for the module’s back-office configuration pages. |
| `actionAdminControllerSetMedia` | Before an admin controller renders its output. | Add specific CSS/JS assets for the module’s admin pages. |
| `actionProductUpdate` | After a product is updated in the back-office. | Potentially clear cache for blocks containing this product, or re-index product data. |
| `actionProductDelete` | After a product is deleted in the back-office. | Potentially clear cache for blocks containing this product, or remove it from block configurations. |
| `actionCategoryUpdate` | After a category is updated in the back-office. | Potentially clear cache for blocks displaying products from this category. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Homepage Products Pro” module, please refer to your customer account at MyPresta.eu. Our dedicated support team is available to assist you with any technical issues or questions you may have.

- **MyPresta.eu Order History & Downloads:** <https://mypresta.eu/my-account/orders/>
- **MyPresta.eu Support Contact:** <https://mypresta.eu/contact>
