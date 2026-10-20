---
title: "Related Products Pro - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Related Products Pro PrestaShop module by MyPresta.eu."
sidebar:
  label: "Related Products Pro - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Related Products Pro Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/related-products-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/related-products-pro/)
>
> ---


# Related Products Pro

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required and are usually enabled by default on most hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Module Manager > Related Products Pro > Configure)

This is the main configuration screen where you will manage all aspects of your related product lists. The interface is designed to be intuitive, allowing you to create, edit, and assign related products with ease.

The configuration page will typically present a list of your existing related product lists (if any) and options to create new ones or manage global settings.

#### **Main Interface Elements:**

- **List of Existing Related Product Blocks:** This table will show all the related product lists you have created. For each list, you’ll see details like its name, the products it’s assigned to, and options to edit or delete it.
- **“Add New Related Products Block” Button:** Click this to create a brand new set of related products.
- **Global Settings / Preferences:** (If available) These settings might control general display options or default behaviors for all related product blocks.

#### **When Adding/Editing a Related Products Block:**

When you click to add a new block or edit an existing one, you will typically see a form with the following settings:

1. **Block Name:**

   - **What this setting does:** This is the internal name for your related product list, visible only in the Back Office. It helps you identify different lists.
   - **Effect of changing this setting:** Changes the label for this specific related product block in your admin panel.
   - **Recommended value:** Use a descriptive name, e.g., “Product X - Complementary Items,” “Category Y - Bestsellers.”
   - **Merchant scenario / example:** You might name a list “Summer Dresses - Matching Sandals” to easily find it later.
2. **Display Location (Hook):**

   - **What this setting does:** Determines where on the product page this specific related product block will appear. You select a PrestaShop “hook” which is a designated display area.
   - **Effect of changing this setting:** The related products will move to the chosen location on the front office product page.
   - **Recommended value:** Experiment with different hooks based on your theme. Common choices include `displayProductExtraContent` (often near product description), `displayProductFooter` (at the bottom of the product page), or `displayRightColumnProduct` (if your theme has a right column on product pages).
   - **Merchant scenario / example:** If you want the related products to appear just below the main product image and description, you might choose `displayProductExtraContent`. If you prefer them at the very bottom of the page, `displayProductFooter` would be better.
3. **Products to Display:**

   - **What this setting does:** This is where you define *which* products will be shown in this related product block. You’ll typically have several options:
     - **Specific Products (Manual Selection):**
       - **What this does:** Allows you to manually search for and select individual products to include in the list.
       - **Effect:** Only the products you explicitly choose will appear.
       - **Recommended:** Use for highly curated recommendations.
       - **Scenario:** For a specific camera, you might manually select a tripod, a camera bag, and an extra lens.
     - **Products from Selected Categories:**
       - **What this does:** Displays products from one or more categories you select.
       - **Effect:** The list will dynamically show products from those categories.
       - **Recommended:** Good for showing related items within a product line or department.
       - **Scenario:** For a “Men’s Shirt,” you might select the “Men’s Trousers” and “Men’s Accessories” categories.
     - **New Products:**
       - **What this does:** Automatically displays the newest products added to your store.
       - **Effect:** The list will always show your latest additions.
       - **Recommended:** Great for promoting new arrivals.
       - **Scenario:** Use this block to highlight your latest collection of jewelry.
     - **Bestsellers:**
       - **What this does:** Automatically displays your store’s top-selling products.
       - **Effect:** The list will dynamically update to show your most popular items.
       - **Recommended:** Excellent for social proof and promoting popular items.
       - **Scenario:** Show “Customers Also Bought” items based on overall store popularity.
   - **Number of Products to Display:**
     - **What this does:** Controls how many related products are shown in the block.
     - **Effect:** Limits the visible products.
     - **Recommended:** 4-8 products for a clean look, depending on your layout.
     - **Scenario:** Display 5 related items to keep the section concise.
4. **Assign to Products:**

   - **What this setting does:** This is crucial – it determines *on which product pages* this specific related product block will appear.
   - **Effect of changing this setting:** The related product block will only be visible on the product pages you select here.
   - **Recommended value:** You can assign it to:
     - **All Products:** If this is a general “Bestsellers” or “New Arrivals” block.
     - **Specific Products (Manual Selection):** For highly targeted recommendations.
     - **Products from Selected Categories:** To apply the block to an entire category range.
   - **Merchant scenario / example:** You create a list of “iPhone Accessories.” You would then assign this block only to your iPhone product pages. Or, you create a “Summer Sale Items” block and assign it to all products within your “Summer Collection” category.
5. **Display Type / Template:**

   - **What this setting does:** Allows you to choose the visual layout or template for how the related products are displayed (e.g., grid, carousel, list, table). The module often includes various templates, some of which might be optimized for specific themes (like Panda, Warehouse, Zone themes).
   - **Effect of changing this setting:** Changes the visual presentation of the related products on the front office.
   - **Recommended value:** Experiment to find the best fit for your theme and the chosen hook. A carousel is often good for saving space, while a grid might be better for a dedicated section.
   - **Merchant scenario / example:** If you want a sleek, space-saving display, you might choose a “carousel” template. If you have a lot of space and want to show more details, a “grid” or “table” might be better. Some templates might be specifically named for popular themes (e.g., `panda-blocksProductsCart.tpl`) to ensure better integration.
6. **Carousel Settings (if applicable):**

   - **What this setting does:** If you choose a carousel display type, you might have additional options like:
     - **Autoplay:** Whether the carousel scrolls automatically.
     - **Loop:** Whether the carousel repeats from the beginning after the last item.
     - **Items per view:** How many products are visible at once in the carousel.
     - **Navigation arrows/dots:** Whether to show controls for manual scrolling.
   - **Effect of changing this setting:** Controls the behavior and appearance of the product carousel.
   - **Recommended value:** Autoplay can be engaging but can also be distracting. Consider your audience. 3-5 items per view is a common good balance.
   - **Merchant scenario / example:** You want a subtle carousel that automatically scrolls every 5 seconds, showing 4 products at a time, with navigation arrows for users who want to browse manually.

#### **Saving Your Changes:**

Always remember to click the “Save” or “Update” button after making any changes to a related product block to ensure your settings are applied.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration Page** | **Block Name** | Descriptive (e.g., “Product X - Cross-Sell”) | Internal label for identifying the related product block in the Back Office. |
|  | **Display Location (Hook)** | `displayProductExtraContent` or `displayProductFooter` | Determines where the block appears on the front-office product page. |
|  | **Products to Display: Specific Products** | Manual selection | Shows only hand-picked products. Best for highly curated recommendations. |
|  | **Products to Display: From Selected Categories** | Select relevant categories | Dynamically shows products from chosen categories. Good for related product lines. |
|  | **Products to Display: New Products** | Auto-populated | Automatically shows the latest products in your store. Great for new arrivals. |
|  | **Products to Display: Bestsellers** | Auto-populated | Automatically shows your store’s top-selling products. Excellent for social proof. |
|  | **Number of Products to Display** | 4-8 | Limits the number of products shown in the block for a clean layout. |
|  | **Assign to Products: All Products** | N/A | Displays the block on every product page. Use for general recommendations. |
|  | **Assign to Products: Specific Products** | Manual selection | Displays the block only on selected product pages. For targeted cross-sells. |
|  | **Assign to Products: From Selected Categories** | Select relevant categories | Displays the block on product pages within chosen categories. |
|  | **Display Type / Template** | `accessories.tpl` or theme-specific | Controls the visual layout (grid, carousel, list). Choose based on theme and hook. |
|  | **Carousel Settings (Autoplay, Loop, Items per view, Navigation)** | Varies, often enabled | Controls the behavior of carousel displays. Adjust for user experience. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My related products aren’t showing up on the front office.**

- **A:** First, ensure the module is enabled and configured. Check that you have actually *assigned* the related product block to the specific product(s) or categories you are viewing. Also, verify that the “Display Location (Hook)” you selected is actually rendered by your theme on the product page. Finally, clear your PrestaShop cache (Advanced Parameters > Performance > Clear Cache).

**Q2: The related products look strange or don’t fit my theme’s design.**

- **A:** This is often a styling conflict with your custom theme.
  - **Solution 1:** Try different “Display Type / Template” options in the module configuration. Some templates are designed for specific popular themes (e.g., `panda-blocksProductsCart.tpl`).
  - **Solution 2:** Clear your browser’s cache and PrestaShop’s Smarty cache (Advanced Parameters > Performance).
  - **Solution 3:** If the issue persists, it might require custom CSS adjustments. This is a task for a webmaster or developer (see Section 7.5).

**Q3: Can I have multiple related product blocks on the same product page?**

- **A:** Yes! The module is designed for this. You can create several distinct related product blocks, each with its own products, display type, and assigned location (hook). Just make sure to place them in different hooks to avoid overlapping.

**Q4: How do I translate the module’s text (e.g., “Related Products”) into other languages?**

- **A:** Go to **International > Translations** in your PrestaShop Back Office. Select “Installed modules translations,” choose your theme, and then select “Related Products Pro” from the module dropdown. You can then edit the text strings for each language.

**Q5: The carousel isn’t working or products are stacked vertically.**

- **A:** This usually indicates a JavaScript conflict or missing JS library.
  - **Solution 1:** Ensure your theme is up-to-date.
  - **Solution 2:** Clear your PrestaShop cache and browser cache.
  - **Solution 3:** Check for console errors in your browser’s developer tools (F12). If you see JavaScript errors, it might indicate a conflict with another module or your theme. This would require a developer to investigate.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a technical deep dive into the “Related Products Pro” module for developers, webmasters, and technical agencies.

### 4.1 Architecture Overview

The “Related Products Pro” module (`ppb`) follows a standard PrestaShop module architecture, primarily leveraging the `Module` class for its core functionality. It focuses on extending the front-office product page experience by injecting custom product lists into various display hooks. The module manages its configuration and related product data directly within the `index.php` file’s `getContent()` method, which handles both form rendering and data persistence. It utilizes a custom templating system for flexible front-office display, including specific templates for popular themes. JavaScript and CSS assets are loaded conditionally to enhance the user interface and provide carousel functionality.

### 4.2 Controllers (`controllers/`)

The module does not appear to use dedicated `ModuleFrontController` or `AdminController` classes. All front-office rendering is handled via hooks, and back-office configuration is managed within the main `index.php` file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

The module does not define custom classes extending `ObjectModel` in a dedicated `classes/` directory. Data persistence for related product configurations is likely handled directly through `Configuration::updateValue()` or custom database tables managed within the main `index.php` file.

### 4.4 JavaScript Assets (`views/js/`)

- **`ppb/lib/searchTool/views/js/autocomplete.js`**:
  - **Scope:** Back-office.
  - **Responsibility:** Provides autocomplete functionality for product selection fields within the module’s configuration forms, likely for manually selecting specific products to include or assign to. It listens for user input in text fields and suggests products based on partial matches.
- **`ppb/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`**:
  - **Scope:** Back-office.
  - **Responsibility:** Likely part of a generic utility for managing Smarty templates within the admin interface. It might handle dynamic loading, saving, or previewing of template code, possibly used for custom template creation or modification features within the module.
- **`ppb/lib/src/js/lightslider.js`**:
  - **Scope:** Front-office.
  - **Responsibility:** This is a third-party library for creating responsive content carousels. It binds to specific HTML elements (likely `<ul>` or `<div>` with a designated class) to transform them into a slider. It handles touch/swipe events, navigation, autoplay, and responsive adjustments.
- **`ppb/views/admin/ppb.js`**:
  - **Scope:** Back-office.
  - **Responsibility:** Contains core JavaScript logic for the module’s Back Office configuration page. This would include event listeners for form submissions, dynamic updates to settings based on user choices (e.g., showing/hiding carousel options), AJAX calls for saving data, and potentially managing the list of related product blocks.
- **`ppb/views/admin/ppb8.js`**:
  - **Scope:** Back-office.
  - **Responsibility:** Similar to `ppb.js`, but likely contains specific adaptations or additional functionalities for PrestaShop 8.x environments, addressing API changes or UI differences in newer PrestaShop versions.
- **`ppb/views/js/accessories.js`**:
  - **Scope:** Front-office.
  - **Responsibility:** Contains front-office specific JavaScript for the related product blocks. This might include initialization logic for the `lightslider.js` carousel, handling product clicks, or any dynamic interactions within the displayed related product lists.

### 4.5 CSS Stylesheets (`views/css/`)

- **`ppb/css.css`**:
  - **Scope:** Both Front-office and Back-office.
  - **Responsibility:** General module-wide styling. Could contain base styles for the related product blocks or common elements used across the module.
- **`ppb/lib/searchTool/views/css/autocomplete.css`**:
  - **Scope:** Back-office.
  - **Responsibility:** Styles for the autocomplete dropdowns and input fields used in the admin product selection tool.
- **`ppb/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`**:
  - **Scope:** Back-office.
  - **Responsibility:** Styling for the Smarty template management interface within the module’s configuration.
- **`ppb/lib/src/css/lightslider.css`**:
  - **Scope:** Front-office.
  - **Responsibility:** Core styling for the `lightslider.js` carousel, defining its structure, navigation arrows, dots, and responsive behavior. Developers can override these styles to match their theme.
- **`ppb/views/admin/ppb.css`**:
  - **Scope:** Back-office.
  - **Responsibility:** Specific styling for the module’s configuration page in the PrestaShop admin panel, ensuring it integrates well with the PrestaShop back-office UI.
- **`ppb/views/css/ppb-table.css`**:
  - **Scope:** Front-office.
  - **Responsibility:** Styling for related product lists displayed in a table format, likely used for specific “table-list” templates.
- **`ppb/views/css/ppb.css`**:
  - **Scope:** Front-office.
  - **Responsibility:** Primary front-office styling for the related product blocks, including product card layouts, spacing, and general appearance.
- **`ppb/views/css/ppbcarousell.css`**:
  - **Scope:** Front-office.
  - **Responsibility:** Additional or specific styling for the carousel display of related products, potentially overriding or extending `lightslider.css` for custom module aesthetics.
- **`ppb/views/css/ppb_custom.css`**:
  - **Scope:** Front-office.
  - **Responsibility:** Likely intended for custom user-defined CSS or theme-specific overrides to adjust the appearance of the related product blocks without modifying core module files.

### 4.6 Smarty Template Structure (`views/templates/`)

The module provides a rich set of templates, many of which are tailored for specific hooks and popular PrestaShop themes.

- **`ppb/lib/searchTool/views/scripts.tpl`**:

  - **Scope:** Back-office.
  - **Purpose:** Contains JavaScript initialization or configuration for the autocomplete search tool used in the admin.
- **`ppb/lib/smartyTemplatesManager/tpl/example.tpl`**:

  - **Scope:** Back-office.
  - **Purpose:** An example template, likely used as a reference or for demonstrating the Smarty template manager’s capabilities.
- **`ppb/lib/smartyTemplatesManager/views/buttonManager.tpl`**:

  - **Scope:** Back-office.
  - **Purpose:** Renders buttons or controls for managing templates within the admin interface.
- **`ppb/lib/smartyTemplatesManager/views/createTemplateForm.tpl`**:

  - **Scope:** Back-office.
  - **Purpose:** Renders the form for creating new custom display templates for related products.
- **`ppb/lib/smartyTemplatesManager/views/editTemplateForm.tpl`**:

  - **Scope:** Back-office.
  - **Purpose:** Renders the form for editing existing custom display templates.
- **`ppb/lib/smartyTemplatesManager/views/mainForm.tpl`**:

  - **Scope:** Back-office.
  - **Purpose:** The main form for the Smarty template manager, likely listing templates and providing options.
- **`ppb/lib/smartyTemplatesManager/views/selectInput.tpl`**:

  - **Scope:** Back-office.
  - **Purpose:** Renders a select dropdown input, possibly used for choosing templates or other options.
- **`ppb/views/templates/admin/tabs.tpl`**:

  - **Scope:** Back-office.
  - **Purpose:** Renders the tab navigation structure for the module’s configuration page, if it uses multiple tabs for different settings.
- **Hook templates (`views/templates/hook/`)**: These templates are rendered on the front-office product page via various PrestaShop hooks. Many are theme-specific to ensure optimal integration.

  - **`accessories.tpl`**:
    - **Hook:** Configurable, often `displayProductExtraContent` or `displayProductFooter`.
    - **Output:** A generic template for displaying related products, typically in a grid or carousel.
  - **`blocksProductsCart.tpl`**:
    - **Hook:** Configurable, often `displayProductExtraContent` or `displayProductFooter`.
    - **Output:** A block of products, potentially styled for a cart-like appearance or for general product recommendations.
  - **`blocksProductsOrder.tpl`**:
    - **Hook:** Configurable.
    - **Output:** Similar to `blocksProductsCart.tpl`, but might be styled for a different context or layout.
  - **`custom-pictures-only.tpl`**:
    - **Hook:** Configurable.
    - **Output:** A minimalist display showing only product pictures, ideal for compact spaces or visual browsing.
  - **`panda-blocksProductsCart.tpl`**, **`panda-blocksProductsOrder.tpl`**, **`panda-ProductExtraContent.tpl`**, **`panda-productFooter.tpl`**, **`panda-productTab.tpl`**, **`panda-productTabContent.tpl`**:
    - **Hook:** Configurable, designed for the Panda theme.
    - **Output:** Theme-specific templates ensuring seamless integration and styling with the Panda theme’s design language. They will render related products within the specified Panda theme areas (e.g., product extra content, footer, or dedicated tabs).
  - **`ProductExtraContent.tpl`**:
    - **Hook:** `displayProductExtraContent`.
    - **Output:** Renders related products within the `displayProductExtraContent` hook, typically a prominent area near the main product details.
  - **`productFooter.tpl`**:
    - **Hook:** `displayProductFooter`.
    - **Output:** Renders related products at the bottom of the product page.
  - **`productTab.tpl`**:
    - **Hook:** Configurable, often `displayProductButtons` or `displayProductExtraContent` (to add a new tab).
    - **Output:** Renders the *tab header* for a dedicated “Related Products” tab on the product page.
  - **`productTabContent.tpl`**:
    - **Hook:** Configurable, often `displayProductContent` or `displayProductExtraContent` (to add content for a new tab).
    - **Output:** Renders the *content* for a dedicated “Related Products” tab, appearing when the `productTab.tpl` header is clicked.
  - **`table-list.tpl`**:
    - **Hook:** Configurable.
    - **Output:** Displays related products in a tabular format, potentially useful for comparing features or for a more structured list.
  - **`warehouse-blocksProductsCart.tpl`**, **`warehouse-blocksProductsOrder.tpl`**, etc. (all `warehouse-` prefixed templates):
    - **Hook:** Configurable, designed for the Warehouse theme.
    - **Output:** Theme-specific templates for the Warehouse theme, ensuring proper styling and layout integration.
  - **`zone-blocksProductsCart.tpl`**, **`zone-blocksProductsOrder.tpl`**, etc. (all `zone-` prefixed templates):
    - **Hook:** Configurable, designed for the Zone theme.
    - **Output:** Theme-specific templates for the Zone theme, ensuring proper styling and layout integration.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: The module likely stores its configuration data (related product block definitions, assigned products, display settings) in custom database tables created during installation, or it might heavily rely on `ps_configuration` for simpler settings. Given the complexity of multiple related product lists, custom tables are more probable. Developers would need to inspect the `install()` method in `ppb/index.php` for `Db::getInstance()->execute()` calls to identify table creation.

  - **Likely Tables (Hypothetical based on functionality):**
    - `ps_ppb_blocks`: Stores the main definition of each related product block (ID, name, hook, display type, etc.).
    - `ps_ppb_block_products`: A many-to-many table linking related product blocks to the products they should display.
    - `ps_ppb_block_assignments`: A many-to-many table linking related product blocks to the product pages they should appear on.
    - `ps_ppb_block_categories`: A table to store category assignments for dynamic product selection or assignment.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Used to load CSS and JavaScript assets (e.g., `lightslider.js`, `ppb.css`) conditionally only on product pages or globally. |
| `displayRightColumnProduct` | In the right column of the product page. | Renders related product blocks in the right sidebar. |
| `displayLeftColumnProduct` | In the left column of the product page. | Renders related product blocks in the left sidebar. |
| `displayProductExtraContent` | A flexible hook often found near the product description/image. | A common and highly recommended hook for injecting related product blocks directly into the main content area. |
| `displayProductFooter` | At the bottom of the product page, before the general footer. | Renders related product blocks in a dedicated section at the end of the product page content. |
| `displayProductButtons` | Near the Add to Cart button or product actions. | Could be used to add a “Related Products” tab header. |
| `displayProductContent` | Within the main product content area. | Could be used to render the content of a “Related Products” tab. |
| `displayFooter` | In the store’s global footer. | Less common for related products, but possible for very broad recommendations. |
| `actionProductUpdate` | After a product is updated in the Back Office. | Potentially used to clear cache or re-index related product data if dynamic lists are used. |
| `actionProductDelete` | After a product is deleted. | To clean up any related product assignments involving the deleted product. |
| `actionCategoryUpdate` | After a category is updated. | To re-evaluate related product lists that depend on category selections. |
| `actionCategoryDelete` | After a category is deleted. | To clean up related product assignments involving the deleted category. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please log in to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist you with any issues or questions regarding the “Related Products Pro” module.
