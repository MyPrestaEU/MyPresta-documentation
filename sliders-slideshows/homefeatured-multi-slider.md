---
title: "Homefeatured multi slider - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Homefeatured multi slider PrestaShop module by MyPresta.eu."
sidebar:
  label: "Homefeatured multi slider - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Homefeatured multi slider Module on MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/homefeatured-multi-slider.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/sliders-slideshows/homefeatured-multi-slider/)
>
> ---


# Homefeatured multi slider

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for a PrestaShop store to function correctly. This module does not have unusual or specific hosting requirements beyond a standard PrestaShop environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The “Homefeatured multi slider” module provides two main areas for configuration: the main module configuration page for general settings and a dedicated administration screen for managing your product sliders and categories.

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the primary screen where you’ll set up the general behavior and appearance of your multi-featured product slider. To access it, go to **Modules > Module Manager**, find “Homefeatured multi slider,” and click “Configure.”

#### General Settings Tab

| Setting / Option | What this setting does | Effect of changing this setting | Recommended value | Merchant scenario / example |
| --- | --- | --- | --- | --- |
| **Display in Hook** | Determines where the slider will appear on your website. | *When set to `displayHome` (or similar main content hook):* The slider will be a prominent feature on your homepage. *When set to `displayLeftColumn` or `displayRightColumn`:* The slider will appear in the sidebars, usually smaller. *When set to `displayFooter`:* The slider will be at the bottom of your pages. | `displayHome` for a prominent homepage slider. | You want your main featured products to be the first thing customers see on your homepage. |
| **Number of products to display** | Controls how many products are visible in the slider at any given time. | *When set to `4`:* Four products will be shown side-by-side (if space allows). *When set to `1`:* Only one product will be visible, often with larger images. | `4` or `5` for most themes, depending on your product image sizes and design. | You have large product images and want to show fewer items at once for better detail, or you have small images and want to show more. |
| **Slider Speed (ms)** | Sets how fast the slider transitions between products or slides. Measured in milliseconds (1000ms = 1 second). | *When set to `500`:* Transitions are very fast. *When set to `5000`:* Transitions are slow, giving customers more time to view each product. | `3000` (3 seconds) to `5000` (5 seconds) for a comfortable viewing experience. | You want a dynamic, fast-paced display of products, or a more relaxed, contemplative browsing experience. |
| **Autoplay Slider** | Determines if the slider automatically rotates through products without user interaction. | *When enabled (YES):* The slider will automatically move to the next product after the set “Slider Speed.” *When disabled (NO):* The slider will only change slides when the customer clicks navigation arrows. | `YES` to keep the content dynamic and engaging. | You want to ensure all featured products get visibility even if customers don’t actively click through. |
| **Show Navigation Arrows** | Controls the visibility of “next” and “previous” arrows on the slider. | *When enabled (YES):* Arrows appear on the sides of the slider, allowing manual navigation. *When disabled (NO):* Customers must rely on autoplay or other navigation methods (if available). | `YES` for better user control and accessibility. | You want customers to easily browse through products at their own pace. |
| **Show Pagination Dots** | Controls the visibility of small dots or indicators, usually at the bottom of the slider, representing each slide. | *When enabled (YES):* Dots appear, showing the current slide position and allowing direct jumping to specific slides. *When disabled (NO):* Dots are hidden. | `YES` for better user orientation and direct access to slides. | You want customers to know how many slides there are and jump directly to a specific one. |
| **Product Image Width (px)** | Sets the width of product images within the slider. | *When set to `200`:* Images will be 200 pixels wide. *When set to `300`:* Images will be 300 pixels wide. This affects the overall size and layout of the slider. | `250` to `350` pixels, depending on your theme’s design and “Number of products to display.” | Your product images are high resolution, and you want them to appear larger, or you need them smaller to fit more products. |
| **Product Image Height (px)** | Sets the height of product images within the slider. | *When set to `200`:* Images will be 200 pixels high. *When set to `300`:* Images will be 300 pixels high. This works in conjunction with width to maintain aspect ratio or crop. | `250` to `350` pixels, matching your chosen width for square images, or adjusted for portrait/landscape. | You have product images with varying aspect ratios and want to standardize their display height. |
| **Background Color** | Allows you to set a custom background color for the entire slider block. | *When set to `#FFFFFF` (white):* The slider background will be white. *When set to `#F0F0F0` (light grey):* The background will be light grey. | Leave empty for transparent or use a color that matches your theme. | You want the slider to stand out with a distinct background color, or blend seamlessly with your page background. |
| **Text Color** | Sets the color for product names and other text within the slider. | *When set to `#000000` (black):* Text will be black. *When set to `#333333` (dark grey):* Text will be dark grey. | A color that provides good contrast against your chosen background color. | You need to ensure product names are easily readable against the slider’s background. |
| **Price Color** | Sets the color for product prices displayed in the slider. | *When set to `#FF0000` (red):* Prices will be red, often used for sales. *When set to `#008000` (green):* Prices will be green. | A color that makes prices stand out, often your brand’s accent color or a standard price color. | You want prices to be highly visible and attract attention. |

### 2.2 Dedicated Admin Screens & Controller Views

This module includes a dedicated section in your PrestaShop Back Office to manage the categories of your featured products and assign products to them.

#### Screen Name & Menu Location: “Multi Featured Slider”

You can find this section by navigating to:
**Modules > Module Manager > Homefeatured multi slider > Configure**
On the configuration page, you will see a tab or a link that leads to the “Multi Featured Slider” management interface. In PrestaShop 1.7+, this might appear as a new menu item under “Catalog” or “Modules” if the module registers its own tab.

This screen is managed by the `AdminprosliderController` (located at `multihomefeatured/controllers/admin/adminproslider.php`).

**Available Actions & Settings:**

This screen typically presents a list of your created “featured product categories” (referred to as “opinion” in the underlying code, but functionally acting as categories for your slider).

- **Listing Table:** You will see a table listing all the custom categories you’ve created for your featured products. Each row will likely show:

  - **# (ID):** A unique identifier for the category.
  - **Category Name:** The name you’ve given to this group of featured products (e.g., “Bestsellers,” “New Arrivals”).
  - **Status:** Whether the category is active (visible in the slider) or inactive.
  - **Actions:** Buttons to “Edit” (modify the category name, status, and assign products) or “Delete” the category.
- **Add New Category:** There will be a button (e.g., “Add New Category” or “Add New”) to create a new group of featured products. When adding or editing a category, you’ll typically find:

  - **Category Name:** An input field to define the name of your featured product category (e.g., “Seasonal Deals,” “Customer Favorites”).
  - **Active/Inactive Switch:** A toggle to enable or disable the display of this specific category in the front-office slider.
  - **Product Assignment:** This is the core functionality. You will likely see a search bar or a list of available products. You can search for products and add them to this specific featured category. Products can usually be reordered within the category.

**Effect of changes:**

- **Adding a New Category:** Creates a new tab or section in your front-office slider. You can then populate it with specific products.
- **Editing a Category:**
  - Changing the **Category Name** updates the label displayed to customers in the slider.
  - Toggling **Active/Inactive** immediately shows or hides that entire category and its products from the front-office slider.
  - **Adding/Removing Products:** Directly updates which products appear in that specific slider category.
  - **Reordering Products:** Changes the sequence in which products appear within that category’s slider.
- **Deleting a Category:** Permanently removes the category and all its assigned products from the slider. The products themselves are not deleted from your store.

**Recommended workflow for daily store management:**

1. **Plan your categories:** Before creating, decide on the logical groups for your featured products (e.g., “New Arrivals,” “On Sale,” “Best Sellers,” “Seasonal Picks”).
2. **Create Categories:** Use the “Add New” button to create each category, giving it a clear, descriptive name.
3. **Assign Products:** For each category, use the product assignment interface to search for and add the relevant products. Make sure to save your changes.
4. **Order Products:** Arrange the products within each category in the order you want them to appear.
5. **Review & Activate:** Once satisfied, ensure the category is set to “Active.”
6. **Check Front-Office:** Always verify the changes on your live store to ensure the slider looks and functions as expected.
7. **Regular Updates:** Periodically update your featured categories with new products, seasonal items, or items you want to promote. Remove older or out-of-stock items to keep the slider fresh and relevant.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Config Page** | Display in Hook | `displayHome` | Controls where the slider appears (homepage, columns, footer). |
|  | Number of products to display | `4` | How many products are visible at once in the slider. |
|  | Slider Speed (ms) | `3000` - `5000` | Speed of automatic slide transitions. |
|  | Autoplay Slider | `YES` | Slider automatically rotates products. |
|  | Show Navigation Arrows | `YES` | Displays arrows for manual navigation. |
|  | Show Pagination Dots | `YES` | Displays dots for slide indication and direct access. |
|  | Product Image Width (px) | `250` - `350` | Sets the width of product images in the slider. |
|  | Product Image Height (px) | `250` - `350` | Sets the height of product images in the slider. |
|  | Background Color | Leave empty / Theme-matching | Sets the background color of the slider block. |
|  | Text Color | Theme-matching / `#333333` | Sets the color for product names and descriptions. |
|  | Price Color | Theme-matching / Accent color | Sets the color for product prices. |
| **“Multi Featured Slider” Admin Screen** | Add/Edit Category Name | Descriptive name (e.g., “Bestsellers”) | Creates/modifies a tab/section in the slider. |
|  | Category Status (Active/Inactive) | `Active` | Shows or hides an entire featured product category. |
|  | Assign Products to Category | N/A | Selects which products appear in a specific slider category. |
|  | Reorder Products | N/A | Changes the display order of products within a category. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My slider isn’t showing up on the homepage after configuration.**

- **A:** First, check if the module is enabled and configured to display in the correct hook (e.g., `displayHome`) on the module’s main configuration page. Second, ensure you have created at least one “Multi Featured Slider” category and assigned products to it, and that the category is set to “Active” in the dedicated admin screen. Finally, clear your PrestaShop cache (**Advanced Parameters > Performance > Clear cache**).

**Q2: The slider looks broken or misaligned on my store.**

- **A:** This is often a CSS conflict with your theme.
  1. **Check Image Dimensions:** Go to the module’s configuration page and verify the “Product Image Width” and “Product Image Height” settings. Ensure they are appropriate for your theme and the number of products you want to display.
  2. **Theme Overrides:** Your theme might have conflicting styles. Try temporarily switching to the default PrestaShop theme to see if the issue persists. If it resolves, your theme’s CSS is likely overriding the module’s styles. You may need a web developer to create a custom CSS override in your theme’s `custom.css` file.
  3. **Clear Cache:** Always clear your browser cache and PrestaShop Smarty cache after making design-related changes.

**Q3: How do I change the order of products within a slider category?**

- **A:** Go to the dedicated “Multi Featured Slider” admin screen. Edit the specific category you want to reorder. Within the product assignment interface, you should be able to drag and drop products to change their order, or there might be up/down arrows next to each product. Remember to save your changes.

**Q4: Can I translate the category names for different languages?**

- **A:** Yes, PrestaShop modules typically support multi-language input for fields like category names. When you are editing a category name in the “Multi Featured Slider” admin screen, look for a language selector (usually a flag icon) next to the input field. Click it to enter the name for each installed language.

**Q5: The slider is too fast/slow, or the autoplay isn’t working.**

- **A:** Adjust the “Slider Speed (ms)” setting on the module’s main configuration page. A higher number means a slower transition. Ensure “Autoplay Slider” is set to `YES` if you want it to rotate automatically. Remember to save and clear your cache.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview of the “Homefeatured multi slider” module for developers and webmasters.

### 4.1 Architecture Overview

The `Homefeatured multi slider` module (internal name `multihomefeatured`) follows a standard PrestaShop module architecture, leveraging the MVC pattern. It primarily consists of:

- A main module file (`ajax_multihomefeatured.php`) handling installation, uninstallation, and the primary configuration form (`getContent()`).
- A front controller (`default.php`) for potential AJAX interactions or specific front-office rendering logic.
- An admin controller (`AdminprosliderController.php`) to manage the custom “featured product categories” (referred to as `opinion` in the database context, but functionally acting as categories).
- Smarty templates for rendering both the back-office configuration and front-office slider elements.
- JavaScript for slider functionality and CSS for styling.

The module does not appear to use custom `ObjectModel` classes based on the provided inventory, suggesting it might store its custom category and product assignments directly in `ps_configuration` or a custom table managed by the `AdminprosliderController`.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `multihomefeatured/controllers/front/default.php`
  - **Class name & parent class**: `MultihomefeaturedDefaultModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility**: This controller is likely used for handling specific front-office requests, potentially for AJAX calls related to slider content, or for rendering a standalone page if the module offered one. Given the module’s primary function as a slider, it might handle dynamic content loading or specific product data retrieval for the slider.

#### Back-Office Admin Controllers

- `multihomefeatured/controllers/admin/adminproslider.php`
  - **Tab name and managed entity**: This controller manages the custom “Multi Featured Slider” categories and their associated products. It likely appears as a sub-tab or a dedicated entry within the PrestaShop Back Office menu, often under “Catalog” or “Modules.” The managed entity is conceptually a “featured product category,” which the module internally refers to as `opinion` in its database interactions.
  - **Responsibility**: This controller provides the CRUD (Create, Read, Update, Delete) interface for these custom categories. It handles:
    - Listing existing categories.
    - Displaying forms to add new categories.
    - Displaying forms to edit existing categories (including assigning and reordering products).
    - Processing form submissions for category creation/updates.
    - Handling deletion of categories.
    - Managing the association between categories and specific PrestaShop products.

### 4.3 Core Classes & Models (`classes/`)

Based on the provided inventory, there are no custom PHP classes explicitly listed in the `classes/` directory. This suggests that:

1. The module might be older and directly manipulates database tables without a dedicated `ObjectModel`.
2. The `AdminprosliderController` might directly handle database interactions for its `opinion` entity.
3. The main module file (`ajax_multihomefeatured.php`) might contain all necessary logic for configuration and basic data handling.

If custom data (like the “featured product categories” and their product assignments) is stored, it’s either in `ps_configuration` (for simple key-value pairs) or a custom database table that is managed directly by the `AdminprosliderController` without a formal `ObjectModel` definition in `classes/`.

### 4.4 JavaScript Assets (`views/js/`)

- `multihomefeatured/js/jquery.catslider.16.js`
  - **Scope**: Front-office.
  - **Description**: Likely a version of a “category slider” or “content slider” jQuery plugin, specifically adapted or intended for PrestaShop 1.6.x. It would handle the core slider animation, navigation, and responsiveness.
- `multihomefeatured/js/jquery.catslider.js`
  - **Scope**: Front-office.
  - **Description**: Similar to the above, potentially a more generic version or for other PrestaShop versions. This script would initialize the slider, manage transitions, autoplay, and user interaction (clicks, swipes).
- `multihomefeatured/js/jscolor/jscolor.js`
  - **Scope**: Back-office.
  - **Description**: This is a JavaScript library for a color picker. It’s used in the module’s back-office configuration form to provide a user-friendly interface for selecting colors (e.g., for background, text, price colors). It binds to specific input fields to display the color picker.
- `multihomefeatured/js/modernizr.custom.63321.js`
  - **Scope**: Front-office.
  - **Description**: Modernizr is a JavaScript library that detects HTML5 and CSS3 features in the user’s browser. It’s often used to provide feature detection and fallback mechanisms, ensuring the slider works correctly across different browsers, especially older ones that might lack certain CSS3 transition or animation capabilities.
- `multihomefeatured/js/script.js`
  - **Scope**: Front-office and/or Back-office.
  - **Description**: This is likely the main custom JavaScript file for the module. It would contain:
    - Initialization logic for the `jquery.catslider` plugin, passing configuration options from the module’s settings.
    - Event listeners for navigation arrows, pagination dots, or custom interactions.
    - Potentially AJAX calls to the `default.php` front controller for dynamic content loading.
    - Any specific DOM manipulation or UI enhancements related to the slider.
    - In the back-office, it might contain scripts for product search and assignment within the `AdminprosliderController`’s forms.

### 4.5 CSS Stylesheets (`views/css/`)

- `multihomefeatured/css/style.css`
  - **Scope**: Front-office.
  - **Description**: This is the primary stylesheet for the front-office slider. It defines the visual appearance of the slider container, product items, navigation arrows, pagination dots, product titles, prices, and any other elements displayed within the slider.
  - **Key CSS class selectors**: Developers can expect classes like `.multihomefeatured-slider`, `.slider-item`, `.product-image`, `.product-title`, `.product-price`, `.slider-nav-arrow`, `.slider-pagination` etc., which can be overridden in a custom theme’s `custom.css` or via PrestaShop’s theme override mechanism.
- `multihomefeatured/js/css/ui-lightness/jquery-ui-1.10.2.custom.css`
  - **Scope**: Back-office.
  - **Description**: This stylesheet is part of the jQuery UI library, specifically the “UI-lightness” theme. It’s likely used in the back-office for styling elements like date pickers, dialogs, or other interactive components that might be part of the `AdminprosliderController`’s forms (e.g., for product search autocomplete, if implemented using jQuery UI).

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `multihomefeatured/header.tpl`
    - **Hook**: Likely `displayHeader` or `actionFrontControllerSetMedia`.
    - **Output**: Includes module-specific CSS and JavaScript files (`jquery.catslider.js`, `modernizr.custom.63321.js`, `style.css`, `script.js`) into the `<head>` section of the front-office, ensuring they are loaded before the slider is rendered.
  - `multihomefeatured/home.tpl`
    - **Hook**: Configurable (e.g., `displayHome`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`).
    - **Output**: This is the main template for the slider’s front-office display. It contains the HTML structure for the entire multi-category slider, including the tabs for different categories and the container for the product slides. It iterates through the configured categories and products to build the slider.
  - `multihomefeatured/homeTab.tpl`
    - **Hook**: Rendered internally by `home.tpl`.
    - **Output**: This template likely renders a single tab or navigation element for one of the featured product categories (e.g., “Bestsellers,” “New Arrivals”). It’s part of the navigation for switching between different product sliders.
  - `multihomefeatured/homeTabContents.tpl`
    - **Hook**: Rendered internally by `home.tpl`.
    - **Output**: This template renders the actual product list for a single featured product category. It contains the loop that displays individual product images, names, prices, and potentially “Add to Cart” buttons, all wrapped in the structure required by the `jquery.catslider` plugin.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not explicitly define custom `ObjectModel` classes, but the `AdminprosliderController` manages an entity referred to as `opinion`. This strongly suggests the module creates at least one custom table, likely named `ps_multihomefeatured_opinion` (or similar, following PrestaShop’s `ps_` prefix convention) to store:
    - `id_multihomefeatured_opinion` (Primary Key)
    - `name` (for the category name, potentially multi-language)
    - `active` (boolean for category status)
    - Other fields related to category configuration.
  - Additionally, there would be a linking table, e.g., `ps_multihomefeatured_opinion_product`, to store the many-to-many relationship between these categories and `ps_product` entries, including a `position` field for ordering.
  - Module configuration settings (like slider speed, image dimensions, colors) are typically stored in the `ps_configuration` table with keys prefixed by the module’s name (e.g., `MULTIHOMEFEATURED_SLIDER_SPEED`).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Injects module’s CSS and JavaScript files for front-office functionality. |
| `displayHome` | Main content area of the homepage. | Renders the primary multi-category product slider on the homepage. |
| `displayLeftColumn` | Left sidebar of front-office pages. | Renders a smaller version of the slider in the left column. |
| `displayRightColumn` | Right sidebar of front-office pages. | Renders a smaller version of the slider in the right column. |
| `displayFooter` | Bottom section of every front-office page. | Renders the slider in the footer area. |
| `displayProductExtraContent` (or similar product page hook) | On the product page, below product details. | Potentially used to display related products in a slider on product pages. |
| `actionFrontControllerSetMedia` | Before a front controller renders its output. | A more robust way to register assets (CSS/JS) for specific pages or globally. |
| `actionModuleInstall` | During module installation. | Creates database tables, sets default configuration values, registers hooks. |
| `actionModuleUninstall` | During module uninstallation. | Cleans up database tables, removes configuration values, unregisters hooks. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Homefeatured multi slider” module, please refer to your customer account at MyPresta.eu. You can download the most recent versions of the module from your order history. For technical assistance or specific inquiries, please contact MyPresta.eu support directly through your customer account.
