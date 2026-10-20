---
title: "Product Extra Tabs Pro - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Product Extra Tabs Pro PrestaShop module by MyPresta.eu."
sidebar:
  label: "Product Extra Tabs Pro - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Product Extra Tabs Pro Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-extra-tabs-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/product-extra-tabs-pro/)
>
> ---


# Product Extra Tabs Pro

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and are usually available on any modern hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The “Product Extra Tabs Pro” module is primarily configured directly from the product editing page, allowing you to manage tabs on a per-product basis. The main module configuration screen handles global settings.

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

To access the main configuration, go to **Modules > Module Manager**, search for “Product Extra Tabs Pro”, and click “Configure”.

On this screen, you will find settings that apply globally or define how the module behaves across your store.

- **Setting: Enable TinyMCE Editor for Tab Content**

  - **What this setting does:** This switch determines whether a rich text editor (TinyMCE, the same editor PrestaShop uses for product descriptions) is available when you create or edit tab content.
  - **Effect of changing this setting:**
    - *When enabled:* You will see a user-friendly editor with formatting options (bold, italics, lists, images, links, etc.) when adding content to your extra tabs. This makes it easy to create visually appealing and well-structured content without knowing HTML.
    - *When disabled:* You will only have a plain text area for tab content. You would need to manually write HTML tags to format your text, which is more complex for non-technical users.
  - **Recommended value:** **YES**
  - **Merchant scenario / example:** If you want to add images, videos, or styled text to your tabs (e.g., a “Size Chart” tab with an image, or a “Warranty” tab with bolded key terms), enable this. If you only need plain text, you can disable it for a simpler interface.
- **Setting: Display Tabs Globally (for all products)**

  - **What this setting does:** This option allows you to create “global” tabs that automatically appear on *every* product page in your store. This is useful for information that applies universally, like general shipping policies or brand stories.
  - **Effect of changing this setting:**
    - *When enabled:* Any tabs you create within the module’s configuration interface (not on individual product pages) will be displayed on all product pages. You can then manage these global tabs from the module’s main configuration.
    - *When disabled:* Tabs must be created and managed individually for each product from its respective product editing page. Global tabs will not be displayed.
  - **Recommended value:** **YES** (if you have information that applies to all products, otherwise NO).
  - **Merchant scenario / example:** You want to add a “Returns Policy” tab that is identical for all products. Enable this, create the tab here, and it will appear on every product page. If you only need unique tabs for specific products, keep this disabled.
- **Setting: Tab Display Position**

  - **What this setting does:** This dropdown menu controls where the extra tabs are displayed on the product page.
  - **Effect of changing this setting:**
    - *Option: `displayProductExtraContent` (Default):* Tabs will appear in the standard product content area, usually below the main product details, alongside the default description/data sheet tabs. This is the most common and recommended position.
    - *Option: `displayFooterProduct` (PrestaShop 1.6 only):* Tabs will appear in the footer section of the product page. This might be suitable for less critical, supplementary information.
    - *Option: `displayRightColumnProduct` (PrestaShop 1.6 only):* Tabs will appear in the right column of the product page. This is less common for tabs and might depend heavily on your theme’s layout.
    - *Option: `displayLeftColumnProduct` (PrestaShop 1.6 only):* Tabs will appear in the left column of the product page. Similar to the right column, this is less common for tabs.
  - **Recommended value:** `displayProductExtraContent`
  - **Merchant scenario / example:** For most stores, `displayProductExtraContent` provides the best user experience as it keeps all product-related information grouped together. If your theme has a very specific layout or you want to de-emphasize the tabs, you might experiment with footer or column positions (though these are less common for tabs).

#### 2.1.1 Global Tabs Management (if “Display Tabs Globally” is enabled)

If you enabled “Display Tabs Globally”, this section will appear on the module’s configuration page. Here you can add, edit, or delete tabs that will show on *all* product pages.

- **Add New Tab Button:** Click this to open a form where you can define a new global tab.
  - **Tab Title:** The text that appears on the tab itself (e.g., “Shipping Info”, “Warranty”). This is usually multi-language.
  - **Tab Content:** The actual content that appears when the tab is clicked. Use the TinyMCE editor if enabled. This is also multi-language.
  - **Active:** A switch to enable or disable the tab without deleting it.
  - **Position:** A number to control the order of the tab relative to other global tabs. Lower numbers appear first.
- **Existing Tabs List:** A table showing all your currently configured global tabs.
  - **Edit Icon:** Click to modify an existing tab’s title, content, or settings.
  - **Delete Icon:** Click to permanently remove a global tab.

### 2.2 Dedicated Admin Screens & Controller Views

The primary way to manage product-specific extra tabs is directly from the **product editing page** in your PrestaShop Back Office.

- **Screen Name & Menu Location:**

  1. Navigate to **Catalog > Products**.
  2. Edit an existing product or create a new one.
  3. Within the product editing interface, look for a new tab or section labeled **“Extra Tabs Pro”** (or similar, depending on your PrestaShop version and theme).
- **Available Actions & Settings within the “Extra Tabs Pro” section on a Product Page:**

  - **Add New Tab Button:** Click this to create a new tab *specifically for this product*.
    - **Tab Title:** Enter the title for this product-specific tab (e.g., “Technical Specs for Model X”). This is multi-language.
    - **Tab Content:** Enter the content for this tab. The TinyMCE editor will be available if enabled in the main module configuration. This is multi-language.
    - **Active:** Enable/disable this specific tab for this product.
    - **Position:** Set the display order for this tab relative to other tabs on this product page.
  - **Existing Tabs List:** A table showing all extra tabs you’ve created for *this particular product*.
    - **Edit Icon:** Modify the title, content, or status of an existing product-specific tab.
    - **Delete Icon:** Remove a tab from this product.
- **Effect of changes:**

  - When you add, edit, or delete a tab from a product’s “Extra Tabs Pro” section, those changes *only affect that specific product page*.
  - The content and visibility of these tabs are immediately updated on the front office product page after saving your changes.
- **Recommended workflow for daily store management:**

  1. **Identify universal information:** If you have information that applies to ALL products (e.g., general shipping, returns, brand story), use the **global tabs** feature in the module’s main configuration.
  2. **Identify product-specific information:** For details unique to a product (e.g., specific dimensions, material composition, usage instructions, video reviews), go to the **individual product editing page** and use the “Extra Tabs Pro” section there.
  3. **Use the TinyMCE editor:** Always enable the TinyMCE editor in the main module configuration for easier content creation and formatting.
  4. **Regularly review:** Periodically check your product pages to ensure tabs are displaying correctly and content is up-to-date.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Enable TinyMCE Editor | YES | Provides rich text editor for tab content; easier formatting. |
|  | Display Tabs Globally | NO (or YES if needed) | YES: Global tabs appear on all products. NO: Tabs are product-specific. |
|  | Tab Display Position | `displayProductExtraContent` | Controls where tabs appear on the product page. |
|  | **Global Tabs List** | (N/A) | Add/Edit/Delete tabs that appear on ALL product pages. |
| **Product Edit Page** | **Extra Tabs Pro Section** | (N/A) | Add/Edit/Delete tabs specific to the current product. |
|  | Tab Title | (User Defined) | The visible name of the tab on the product page. |
|  | Tab Content | (User Defined) | The information displayed when the tab is clicked. |
|  | Active | YES | Controls whether the tab is visible or hidden. |
|  | Position | (User Defined) | Determines the order of tabs on the product page. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

- **Q: My new tabs aren’t showing up on the product page.**
  - **A:** First, ensure the tab is marked as “Active” both in the module’s global configuration (if it’s a global tab) and on the individual product page (if it’s product-specific). Second, clear your PrestaShop cache: Go to **Advanced Parameters > Performance**, and click “Clear cache” in the top right. Also, clear your browser’s cache.
- **Q: The TinyMCE editor isn’t appearing when I try to add tab content.**
  - **A:** Go to the module’s main configuration page (**Modules > Module Manager > Product Extra Tabs Pro > Configure**) and ensure the “Enable TinyMCE Editor for Tab Content” setting is set to **YES**. Save changes and clear cache.
- **Q: My tabs look strange or don’t match my theme’s styling.**
  - **A:** The module tries to integrate seamlessly, but custom themes can sometimes override default styling. If the appearance is off, it usually requires minor CSS adjustments in your theme. Contact your webmaster or MyPresta.eu support with screenshots for assistance.
- **Q: Can I have different tabs for different languages?**
  - **A:** Yes! The “Tab Title” and “Tab Content” fields are multi-language. When editing a tab, you’ll see language flags next to these fields. Click the flag to switch to a different language and enter the translated content.
- **Q: I want to display a tab only for certain products, not all of them.**
  - **A:** Ensure the “Display Tabs Globally” setting in the module’s main configuration is set to **NO**. Then, navigate to each specific product you want to add a tab to (**Catalog > Products > Edit Product > Extra Tabs Pro section**) and create the tabs there.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The `Product Extra Tabs Pro` module is designed as a standard PrestaShop module, primarily extending the `Module` class. It leverages PrestaShop’s hook system to inject its content into product pages and uses a custom database table to store tab data. Configuration is handled via `getContent()` in the main module file, and product-specific tab management is integrated directly into the product administration page through a custom tab. It uses AJAX for dynamic content loading and saving.

### 4.2 Controllers (`controllers/`)

This module does not utilize dedicated front-office or back-office controllers in the `controllers/` directory. All front-office rendering is handled via hooks and template files, and back-office configuration is managed within the main module file’s `getContent()` method and AJAX calls.

### 4.3 Core Classes & Models (`classes/`)

The module does not define custom classes in the `classes/` directory. Its primary data handling logic is embedded within the main module file `extratabspro/ajax_extratabspro.php`.

### 4.4 JavaScript Assets (`views/js/`)

- `extratabspro/js/tinymce16.inc.js`:
  - **Scope:** Back-office.
  - **Purpose:** This file likely contains initialization and configuration for the TinyMCE rich text editor, specifically tailored for PrestaShop 1.6 environments. It ensures the editor is loaded and configured correctly for the tab content input fields.
- `extratabspro/lib/searchTool/views/js/autocomplete.js`:
  - **Scope:** Back-office.
  - **Purpose:** This script is part of a search tool library, likely used for autocomplete functionality in a search input field within the module’s admin interface (e.g., searching for products to assign tabs to, though this specific feature isn’t explicitly mentioned in the merchant guide, it’s a common pattern for such a library). It binds event listeners to input fields and handles AJAX requests for search suggestions.
- `extratabspro/views/admin/extratabspro.js`:
  - **Scope:** Back-office (PrestaShop 1.7.x, 8.x, 9.x).
  - **Purpose:** This is the main JavaScript file for the module’s administration interface. It handles:
    - AJAX calls for adding, editing, deleting global tabs.
    - AJAX calls for adding, editing, deleting product-specific tabs on the product edit page.
    - Dynamic updates of the tab list tables.
    - Event listeners for form submissions, button clicks (add/edit/delete), and potentially drag-and-drop reordering of tabs.
    - Integration with TinyMCE for content fields.
- `extratabspro/views/admin/extratabspro8.js`:
  - **Scope:** Back-office (PrestaShop 8.x, 9.x).
  - **Purpose:** Similar to `extratabspro.js`, but likely contains specific adaptations or fixes for PrestaShop 8.x and 9.x environments, addressing changes in the Back Office DOM structure or JavaScript APIs. It performs the same core functions as `extratabspro.js` but ensures compatibility with newer PrestaShop versions.
- `extratabspro/views/js/extratabspro.js`:
  - **Scope:** Front-office.
  - **Purpose:** This script handles the front-end display and interaction of the extra tabs on the product page. It likely:
    - Initializes the tab switching mechanism (e.g., jQuery UI tabs, Bootstrap tabs, or custom logic).
    - Binds click events to tab headers to show/hide corresponding content.
    - Ensures smooth transitions or content loading.
    - May handle responsive behavior for tabs on different screen sizes.
- `extratabspro/views/js/tinymce16.inc.js`: (Duplicate, likely for different contexts or an oversight in packaging)
  - **Scope:** Back-office.
  - **Purpose:** Same as the one in `extratabspro/js/`, likely for TinyMCE initialization.

### 4.5 CSS Stylesheets (`views/css/`)

- `extratabspro/lib/searchTool/views/css/autocomplete.css`:
  - **Scope:** Back-office.
  - **Purpose:** Provides styling for the autocomplete suggestions dropdown and related UI elements of the search tool library.
- `extratabspro/views/admin/extratabspro.css`:
  - **Scope:** Back-office.
  - **Purpose:** Styles the module’s configuration forms, tab listing tables, and any custom UI elements within the PrestaShop Back Office, ensuring a consistent look and feel.
- `extratabspro/views/css/extratabspro.css`:
  - **Scope:** Front-office.
  - **Purpose:** Provides the core styling for the extra tabs on the product page. This includes the appearance of tab headers, active tab states, and the content areas. Developers can override these styles in their theme’s `custom.css` or `theme.css` by targeting classes like `.extratabs-pro-tabs`, `.extratabs-pro-tab-header`, `.extratabs-pro-tab-content`, etc.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - `extratabspro/views/front/footer.tpl`: This template is likely intended for `displayFooter` or `displayFooterProduct` hooks (though the module primarily uses `displayProductExtraContent`). It would output content in the footer area.
  - `extratabspro/views/front/tab.tpl`: This template renders a single tab header (the clickable part). It’s used within a loop to generate all tab headers.
  - `extratabspro/views/front/tab16.tpl`: A version of `tab.tpl` specifically for PrestaShop 1.6, adapting to its different HTML structure or CSS classes.
  - `extratabspro/views/front/tabcontents.tpl`: This template renders the content area for all extra tabs. It typically contains a loop that iterates through each tab’s content, wrapping it in a container that can be shown/hidden by JavaScript.
  - `extratabspro/views/front/tabcontents16.tpl`: A version of `tabcontents.tpl` specifically for PrestaShop 1.6.
- **Admin templates (`views/templates/admin/`)**:

  - `extratabspro/lib/searchTool/views/scripts.tpl`: This template likely includes JavaScript and CSS assets for the search tool library within the admin context.
  - `extratabspro/views/admin/tabs-list.tpl`: This template renders the table that lists all configured tabs (either global tabs on the module config page or product-specific tabs on the product edit page). It includes controls for editing and deleting tabs.
  - `extratabspro/views/admin/tabs17.tpl`: This template is the main configuration form or display for the module within the PrestaShop 1.7.x / 8.x / 9.x Back Office. It likely contains the form fields for global settings and the `tabs-list.tpl` inclusion for managing tabs.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - `ps_extratabspro_tab`: Stores the main information for each extra tab (ID, product ID, position, active status).
  - `ps_extratabspro_tab_lang`: Stores multi-language content for each tab (title, content), linked to `ps_extratabspro_tab` by `id_extratabspro_tab` and `id_lang`.
  - `ps_configuration`: Stores module’s global settings (e.g., `EXTRATABSPRO_TINYMCE_ENABLED`, `EXTRATABSPRO_GLOBAL_TABS_ENABLED`, `EXTRATABSPRO_HOOK_POSITION`).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Injects module’s CSS and JS files for front-office display. |
| `displayBackOfficeHeader` | In the `<head>` section of Back Office pages. | Injects module’s CSS and JS files for Back Office configuration and product page integration. |
| `displayAdminProductsExtra` | On the product editing page in the Back Office. | Injects the “Extra Tabs Pro” section into the product administration interface, allowing per-product tab management. |
| `displayProductExtraContent` | In the main content area of the product page, typically below the product description. | Renders the actual extra tabs and their content on the front-office product page. This is the primary hook for front-end display. |
| `displayFooterProduct` | In the footer section of the product page. | Alternative hook for displaying tabs, if configured by the merchant. |
| `displayRightColumnProduct` | In the right column of the product page. | Alternative hook for displaying tabs, if configured by the merchant. |
| `displayLeftColumnProduct` | In the left column of the product page. | Alternative hook for displaying tabs, if configured by the merchant. |
| `actionProductUpdate` | After a product is updated in the Back Office. | Potentially used to clear cache or perform other actions related to product data changes. |
| `actionProductDelete` | After a product is deleted. | Cleans up product-specific tabs from the database. |
| `actionObjectProductAddAfter` | After a new product is added. | Potentially used for initial setup or default tab creation for new products. |
| `actionObjectProductUpdateAfter` | After a product object is updated. | Similar to `actionProductUpdate`, for object model updates. |

## 5. Official Support & Updates

For official updates, technical support, and any further questions regarding the “Product Extra Tabs Pro” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team and developers are available to assist you.
