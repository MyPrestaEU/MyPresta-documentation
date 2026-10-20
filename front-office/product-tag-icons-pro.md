---
title: "Product Tag Icons Pro - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Product Tag Icons Pro PrestaShop module by MyPresta.eu."
sidebar:
  label: "Product Tag Icons Pro - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Product Tag Icons Pro Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-tag-icons-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/product-tag-icons-pro/)
>
> ---


# Product Tag Icons Pro

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required and are present on most modern hosting environments. No special server setup is needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The “Product Tag Icons Pro” module provides a comprehensive set of configuration options spread across several dedicated screens in your PrestaShop back office.

### 2.1 Module Configuration Page (Back Office > Modules > Module Manager > Configure Product Tag Icons Pro)

This is the main configuration screen for general module settings.

- **What this setting does:** Controls the overall behavior and default display options for your product icons.
- **Effect of changing this setting:** These settings impact how icons are displayed across your entire store, or how the module interacts with other parts of PrestaShop.
- **Recommended value:** Varies based on your store’s design and desired functionality.

**Configuration Quick Reference Table (Main Module Configuration)**

| Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- |
| **Enable Module** | YES | **Purpose:** Turns the module’s functionality on or off.   **Impact:** If disabled, no icons will appear on your front office, and the module’s features will be inactive. Keep enabled to use the module. |
| **Icon Size (px)** | 32 | **Purpose:** Sets the default size (width and height) for all icons displayed on the front office.   **Impact:** All icons will be rendered at this specified pixel size. Choose a size that fits well with your product images and overall design without being too small to see or too large to be intrusive. |
| **Icon Position (Hook)** | `displayProductAdditionalInfo` (or similar product page hook) | **Purpose:** Determines where on the product page the icons will be displayed by default. You can choose from a list of available PrestaShop hooks.   **Impact:** Icons will appear in the selected section of the product page. Experiment with different hooks to find the best visual placement for your theme. Common choices include `displayProductAdditionalInfo`, `displayProductPriceBlock`, or `displayAfterProductThumbs`. |
| **Show Icons on Product List** | YES | **Purpose:** Controls whether icons are visible on product listing pages (categories, search results, homepage featured products).   **Impact:** If enabled, icons assigned to products will appear on their respective product cards/thumbnails in lists. If disabled, icons will only show on individual product pages. Recommended to enable for maximum impact. |
| **Tooltip Type** | Light | **Purpose:** Selects the visual theme for the tooltip that appears when a customer hovers over an icon. Options usually include Light, Noir, Punk, Shadow.   **Impact:** Changes the appearance of the tooltip box (background, text color, border) that displays the icon’s description. Choose one that matches your store’s aesthetic. |
| **Tooltip Position** | Top | **Purpose:** Determines where the tooltip appears relative to the icon when hovered over (e.g., Top, Bottom, Left, Right).   **Impact:** Affects the user experience when interacting with icons. Choose a position that doesn’t obscure other important information on the page. |
| **Enable Tooltip Animations** | YES | **Purpose:** Adds subtle animations (fade, slide) when tooltips appear and disappear.   **Impact:** Makes the tooltip interaction feel more modern and engaging. If you prefer a static, instant appearance, disable this. |
| **Custom CSS** | (Empty) | **Purpose:** Allows you to add custom CSS rules to further style your icons or tooltips without modifying module files.   **Impact:** Any CSS rules entered here will be applied to the module’s elements, overriding default styles. Use this for fine-tuning colors, margins, or specific icon behaviors. |

### 2.2 Dedicated Admin Screen: Manage All Icons (Back Office > Product Tag Icons Pro > Manage All Icons)

This screen allows you to create, edit, and delete the actual icon definitions that you will later associate with your products.

- **Screen Name & Menu Location:** You’ll find this under **Product Tag Icons Pro > Manage All Icons** in your PrestaShop back office menu.
- **Available Actions & Settings:**
  - **Add New Icon:** Click the “Add new icon” button to create a new icon.
    - **Icon Name:** A descriptive name for your icon (e.g., “Free Shipping,” “New Arrival”). This is for your internal reference.
    - **Icon Image:** Upload the image file for your icon. This should be a small, clear image (e.g., PNG, JPG, SVG).
    - **Icon Description:** A short text that will appear as a tooltip when customers hover over the icon on the front office. Explain what the icon signifies.
    - **Active:** Toggle whether this icon is currently available for use and display.
    - **Language-specific fields:** If your store is multi-language, you can provide different names and descriptions for each language.
  - **Edit Icon:** Click the “Edit” button next to an existing icon in the list to modify its details.
  - **Delete Icon:** Click the “Delete” button to remove an icon. Be careful, as this will also remove its associations with any products.
  - **Grid / Management View:** A table listing all your created icons, showing their name, image, description, and active status. You can sort and filter this list.
- **Effect of changes:**
  - **Adding an icon:** Makes a new icon available for association with products.
  - **Editing an icon:** Updates the image, name, or description for all instances of that icon across your store.
  - **Deleting an icon:** Removes the icon entirely and it will no longer appear on any products it was previously assigned to.
- **Recommended workflow for daily store management:**
  1. Plan your icons: Decide on the key features or promotions you want to highlight.
  2. Create high-quality, small icon images (e.g., 32x32px or 64x64px) that match your brand.
  3. Go to “Manage All Icons” and add each icon, providing a clear name and a helpful tooltip description.
  4. Ensure all icons are “Active” if you intend to use them.

### 2.3 Dedicated Admin Screen: Manage Icon Associations (Back Office > Product Tag Icons Pro > Manage Icon Associations)

This screen is where you link your created icons to specific products in your catalog.

- **Screen Name & Menu Location:** You’ll find this under **Product Tag Icons Pro > Manage Icon Associations** in your PrestaShop back office menu.
- **Available Actions & Settings:**
  - **Product Search:** Use the search bar to find products by name, ID, or reference.
  - **Product List:** Once you’ve searched for products, they will appear in a list.
  - **Assign Icons:** For each product, you’ll see a section where you can select which of your created icons should be displayed for that specific product. This is usually a multi-select dropdown or a list of checkboxes.
  - **Save Changes:** After assigning or unassigning icons for a product, remember to save your changes.
  - **Grid / Management View:** A table showing products and their currently associated icons.
- **Effect of changes:**
  - **Assigning an icon to a product:** The selected icon will now appear on the front office for that specific product (on its product page and in product lists, depending on your main module settings).
  - **Unassigning an icon from a product:** The icon will no longer be displayed for that product.
- **Recommended workflow for daily store management:**
  1. After creating your icons (in “Manage All Icons”), come to this screen.
  2. Search for the product you want to tag.
  3. Select the relevant icons from the list for that product.
  4. Repeat for all products you wish to tag.
  5. Periodically review your product tags, especially when launching new products or promotions.

### 2.4 Configuration Quick Reference Table (All Screens)

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|
| **Module Configuration** | Enable Module | YES | Turns module on/off. |
| | Icon Size (px) | 32 | Sets default icon display size. |
| | Icon Position (Hook) | `displayProductAdditionalInfo` | Default placement on product page. |
| | Show Icons on Product List | YES | Display icons on category/search pages. |
| | Tooltip Type | Light | Visual theme for icon descriptions. |
| | Tooltip Position | Top | Where tooltip appears relative to icon. |
| | Enable Tooltip Animations | YES | Smooth animations for tooltips. |
| | Custom CSS | (Empty) | Add custom styling for icons/tooltips. |
| **Manage All Icons** | Add New Icon | N/A | Create a new icon definition. |
| | Icon Name | (Descriptive) | Internal name for the icon. |
| | Icon Image | (Upload file) | Visual representation of the icon. |
| | Icon Description | (Tooltip text) | Text shown on hover. |
| | Active | YES | Enable/disable icon for use. |
| | Edit Icon | N/A | Modify existing icon details. |
| | Delete Icon | N/A | Remove an icon definition. |
| **Manage Icon Associations** | Product Search | N/A | Find products to tag. |
| | Assign Icons | N/A | Link created icons to specific products. |
| | Save Changes | N/A | Apply icon assignments to products. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My icons are not showing up on the front office, what should I do?**
A:

1. **Check Module Status:** Go to **Modules > Module Manager** and ensure “Product Tag Icons Pro” is enabled.
2. **Check Icon Status:** Go to **Product Tag Icons Pro > Manage All Icons** and verify that the specific icons you’re trying to display are marked as “Active.”
3. **Check Product Associations:** Go to **Product Tag Icons Pro > Manage Icon Associations** and confirm that the icons are correctly assigned to the products you expect them to appear on.
4. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear Smarty cache” and “Clear cache” (if available). Sometimes, old cached data prevents new module changes from appearing.
5. **Check Hook Position:** In the main module configuration, ensure you’ve selected a valid and appropriate hook for icon display (e.g., `displayProductAdditionalInfo`). Some themes might have custom hooks or might not render certain standard hooks.

**Q2: The icons look too big/small or don’t fit my theme’s design.**
A:

1. **Adjust Icon Size:** In the main module configuration, change the “Icon Size (px)” setting to your desired dimensions.
2. **Custom CSS:** If simple size adjustment isn’t enough, use the “Custom CSS” field in the main module configuration to fine-tune styling. You can target specific icon classes (e.g., `.ticon-image`) to adjust margins, padding, or even apply filters.
3. **Theme Compatibility:** While the module is designed to be compatible, some highly customized themes might require minor CSS adjustments. If you’re comfortable with CSS, inspect the elements using your browser’s developer tools to identify the relevant selectors.

**Q3: The tooltips are not appearing or look strange.**
A:

1. **Enable Tooltips:** Ensure the tooltip feature is enabled in the main module configuration.
2. **Check Tooltip Content:** Verify that you’ve entered a “Description” for each icon in **Product Tag Icons Pro > Manage All Icons**. This description is what appears in the tooltip.
3. **Tooltip Theme/Position:** Experiment with different “Tooltip Type” and “Tooltip Position” settings in the main module configuration to see if a different option resolves the issue or looks better with your theme.
4. **JavaScript Conflicts:** In rare cases, another module’s JavaScript might conflict. Check your browser’s developer console for any JavaScript errors. If you find errors, try temporarily disabling other modules one by one to isolate the conflict.

**Q4: Can I translate the icon names and descriptions for different languages?**
A: Yes! When you create or edit an icon in **Product Tag Icons Pro > Manage All Icons**, you will see language tabs (e.g., “English,” “French,” “Spanish”) next to the “Icon Name” and “Icon Description” fields. Simply switch to the desired language tab and enter the translation for that specific language. The module will automatically display the correct translation based on the customer’s selected language.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the “Product Tag Icons Pro” module, intended for developers, webmasters, and technical agencies.

### 4.1 Architecture Overview

The “Product Tag Icons Pro” module (`ticons`) follows a standard PrestaShop module architecture, primarily leveraging the MVC pattern. It extends `Module` for its core functionality and uses dedicated `AdminController` instances for managing icons and their associations. Data is stored in custom database tables, and front-office display is achieved through various PrestaShop hooks and Smarty templates. The module also integrates third-party libraries for enhanced UI (e.g., Tooltipster for tooltips, a custom autocomplete for product search).

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

This module does not explicitly define custom front-office controllers. All front-office rendering is handled via `hook` methods within the main module class (`ajax_ticons.php`) and associated Smarty templates.

#### Back-Office Admin Controllers

- **`ticons/controllers/admin/AdminTiconsAllController.php`**

  - **Class Name:** `AdminTiconsAllController` (extends `ModuleAdminController`)
  - **Tab Name:** “Manage All Icons”
  - **Responsibility:** Manages the creation, editing, and deletion of individual icon definitions. It handles the CRUD operations for the `ticon` entity. This controller uses `HelperList` for displaying the list of icons and `HelperForm` for the add/edit form. It manages icon image uploads.
- **`ticons/controllers/admin/AdminTiconsAssociationsController.php`**

  - **Class Name:** `AdminTiconsAssociationsController` (extends `ModuleAdminController`)
  - **Tab Name:** “Manage Icon Associations”
  - **Responsibility:** Manages the association of created icons with specific products. It provides an interface to search for products and then assign/unassign multiple icons to them. This controller also uses `HelperList` for product display and a custom form for icon selection. It handles AJAX requests for product search autocomplete.
- **`ticons/controllers/admin/index.php`**

  - **Responsibility:** This is a standard empty `index.php` file, typically present in PrestaShop directories to prevent directory listing. It does not contain any functional controller logic.

### 4.3 Core Classes & Models (`classes/`)

The module does not explicitly define separate PHP files in a `classes/` directory. Instead, the main module file `ajax_ticons.php` likely contains the `ObjectModel` definitions for `Ticon` and `TiconProduct` (or similar entities) directly within its scope, or they are implicitly handled via database interactions.

- **`Ticon` (Implicit ObjectModel):**

  - **Database Table:** `ps_ticons` (or similar, based on module’s `install()` method).
  - **Fields:** Likely includes `id_ticon`, `name` (multilang), `description` (multilang), `image`, `active`.
  - **Purpose:** Represents an individual icon definition, including its image, name, and tooltip description.
- **`TiconProduct` (Implicit ObjectModel):**

  - **Database Table:** `ps_ticon_products` (or similar, based on module’s `install()` method).
  - **Fields:** Likely includes `id_ticon_product`, `id_ticon`, `id_product`.
  - **Purpose:** Represents the many-to-many relationship between icons and products.

### 4.4 JavaScript Assets (`views/js/`)

- **`ticons/lib/searchTool/views/js/autocomplete.js`**

  - **Scope:** Back-office (AdminTiconsAssociationsController).
  - **Functionality:** Provides an autocomplete search functionality for products within the “Manage Icon Associations” screen. It likely sends AJAX requests to the admin controller to fetch product suggestions as the user types.
- **`ticons/lib/tooltipster/js/jquery.tooltipster.js`**

  - **Scope:** Front-office.
  - **Functionality:** This is the core library for the Tooltipster plugin. It handles the creation, positioning, and styling of the interactive tooltips that appear when users hover over product icons. It binds hover events to elements with specific classes (e.g., `.tooltipster`).
- **`ticons/views/js/ticons-front.js`**

  - **Scope:** Front-office.
  - **Functionality:** Contains custom JavaScript specific to the front-office display of icons. This script likely initializes the Tooltipster plugin on the relevant icon elements, passing configuration options (theme, position, animation) based on the module’s back-office settings. It ensures icons are correctly rendered and interactive.
- **`ticons/views/js/ticons.js`**

  - **Scope:** Back-office.
  - **Functionality:** Contains general JavaScript for the module’s back-office configuration and management screens. This might include form validation, dynamic element manipulation, or other UI enhancements for the admin interface.

### 4.5 CSS Stylesheets (`views/css/`)

- **`ticons/lib/searchTool/views/css/autocomplete.css`**

  - **Scope:** Back-office.
  - **Functionality:** Styles the autocomplete dropdown and input field used in the “Manage Icon Associations” screen.
- **`ticons/lib/tooltipster/css/themes/tooltipster-light.css`**

  - **Scope:** Front-office.
  - **Functionality:** Defines the styles for the “Light” theme of the Tooltipster plugin.
- **`ticons/lib/tooltipster/css/themes/tooltipster-noir.css`**

  - **Scope:** Front-office.
  - **Functionality:** Defines the styles for the “Noir” theme of the Tooltipster plugin.
- **`ticons/lib/tooltipster/css/themes/tooltipster-punk.css`**

  - **Scope:** Front-office.
  - **Functionality:** Defines the styles for the “Punk” theme of the Tooltipster plugin.
- **`ticons/lib/tooltipster/css/themes/tooltipster-shadow.css`**

  - **Scope:** Front-office.
  - **Functionality:** Defines the styles for the “Shadow” theme of the Tooltipster plugin.
- **`ticons/lib/tooltipster/css/tooltipster.css`**

  - **Scope:** Front-office.
  - **Functionality:** The core CSS for the Tooltipster plugin, providing base styles for all tooltips.
- **`ticons/views/css/ticons-admin.css`**

  - **Scope:** Back-office.
  - **Functionality:** Contains custom CSS specifically for the module’s back-office interfaces (e.g., styling for icon lists, forms, and custom elements in the admin controllers).
- **`ticons/views/css/ticons-fontawesome.css`**

  - **Scope:** Front-office.
  - **Functionality:** Likely includes or imports Font Awesome icons, which might be used as fallback icons or for specific UI elements within the module’s display.
- **`ticons/views/css/ticons-front-24.css`**, **`ticons/views/css/ticons-front-32.css`**, **`ticons/views/css/ticons-front-48.css`**, **`ticons/views/css/ticons-front-64.css`**, **`ticons/views/css/ticons-front-74.css`**

  - **Scope:** Front-office.
  - **Functionality:** These stylesheets likely contain specific rules for different icon sizes. When the merchant selects an “Icon Size” in the configuration, the module dynamically loads the corresponding CSS file to ensure icons are rendered at the correct dimensions and potentially with optimized spacing. They define classes like `.ticon-24`, `.ticon-32`, etc.
- **`ticons/views/css/ticons.css`**

  - **Scope:** Front-office.
  - **Functionality:** General front-office CSS for the module, including base styles for the icon containers, images, and overall layout. This file might contain common rules applied regardless of the selected icon size.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/front/`)

These templates are rendered when the module is hooked into various front-office positions. They typically receive an array of icon data from the module’s `hook` methods.

- **`ticons/views/templates/front/deliveryTime.tpl`**

  - **Hook:** Potentially `displayProductDeliveryTime` or similar.
  - **Output:** Renders icons related to delivery information.
- **`ticons/views/templates/front/displayActions.tpl`**

  - **Hook:** `displayProductActions` or similar.
  - **Output:** Renders icons near product action buttons (e.g., “Add to Cart”).
- **`ticons/views/templates/front/displayAfterProductThumbs.tpl`**

  - **Hook:** `displayAfterProductThumbs` (PrestaShop 1.7+).
  - **Output:** Renders icons directly below the product thumbnail images on the product page.
- **`ticons/views/templates/front/displayColumns.tpl`**

  - **Hook:** `displayLeftColumn`, `displayRightColumn`.
  - **Output:** Renders icons within the left or right column modules.
- **`ticons/views/templates/front/displayLeftColumn.tpl`**

  - **Hook:** `displayLeftColumn`.
  - **Output:** Renders icons specifically in the left column.
- **`ticons/views/templates/front/displayProductAdditionalInfo.tpl`**

  - **Hook:** `displayProductAdditionalInfo` (PrestaShop 1.7+).
  - **Output:** Renders icons in the “Additional Info” section of the product page, a common and recommended placement.
- **`ticons/views/templates/front/displayProductPriceBlock.tpl`**

  - **Hook:** `displayProductPriceBlock`.
  - **Output:** Renders icons near the product’s price block.
- **`ticons/views/templates/front/displayTop.tpl`**

  - **Hook:** `displayTop` (header).
  - **Output:** Renders icons in the header section of the store.
- **`ticons/views/templates/front/listReviews.tpl`**

  - **Hook:** Potentially `displayProductListReviews` or similar.
  - **Output:** Renders icons related to product reviews or ratings.
- **`ticons/views/templates/front/productFooter.tpl`**

  - **Hook:** `displayFooterProduct` or similar.
  - **Output:** Renders icons in the footer section of the product page.
- **`ticons/views/templates/front/showIcons.tpl`**

  - **Hook:** This is likely a generic template included by other hook templates to render the actual icon HTML structure (e.g., `<img>` tags with `tooltipster` classes). It iterates over the `$icons` variable passed to it.

#### Admin templates (`views/templates/admin/`)

These templates are used for the module’s back-office configuration and management screens.

- **`ticons/lib/searchTool/views/scripts.tpl`**

  - **Scope:** Back-office.
  - **Output:** Contains JavaScript for the search tool, likely including jQuery UI autocomplete initialization or similar.
- **`ticons/views/templates/admin/customHook.tpl`**

  - **Scope:** Back-office.
  - **Output:** A generic template that might be used to render content for custom hooks defined within the module’s admin interface, or for displaying specific messages.
- **`ticons/views/templates/admin/tabs.tpl`**

  - **Scope:** Back-office.
  - **Output:** Renders the navigation tabs (e.g., “Manage All Icons,” “Manage Icon Associations”) for the module’s configuration pages.
- **`ticons/views/templates/admin/ticonsSelection.tpl`**

  - **Scope:** Back-office (AdminTiconsAssociationsController).
  - **Output:** Renders the interface for selecting and assigning icons to a product, typically a multi-select dropdown or a list of checkboxes within the product association form.
- **`ticons/views/templates/admin/ticons_all/helpers/list/list_content.tpl`**

  - **Scope:** Back-office (AdminTiconsAllController).
  - **Output:** Customizes the content of the `HelperList` table for displaying the list of all created icons. It might include custom columns for icon images or active status.
- **`ticons/views/templates/admin/ticons_associations/helpers/form/form.tpl`**

  - **Scope:** Back-office (AdminTiconsAssociationsController).
  - **Output:** Customizes the `HelperForm` for the product association screen. This template likely includes the product search input and the `ticonsSelection.tpl` for icon assignment.
- **`ticons/views/templates/admin/ticons_associations/helpers/list/list_content.tpl`**

  - **Scope:** Back-office (AdminTiconsAssociationsController).
  - **Output:** Customizes the content of the `HelperList` table for displaying the list of products and their associated icons.

### 4.7 Database Schema & Hooks Map

#### Database Tables

The module creates custom tables during its `install()` method to store icon definitions and their associations:

- **`ps_ticons`**: Stores the main icon definitions.
  - `id_ticon` (PK, INT)
  - `image` (VARCHAR): Filename of the icon image.
  - `active` (TINYINT): 1 if active, 0 if inactive.
- **`ps_ticons_lang`**: Stores multi-language fields for icons.
  - `id_ticon` (PK, INT)
  - `id_lang` (PK, INT)
  - `name` (VARCHAR): Icon name for internal use.
  - `description` (TEXT): Tooltip text for the icon.
- **`ps_ticon_products`**: Stores the many-to-many relationship between icons and products.
  - `id_ticon_product` (PK, INT)
  - `id_ticon` (FK, INT)
  - `id_product` (FK, INT)

Configuration settings are stored in `ps_configuration` with keys like `TICONS_ICON_SIZE`, `TICONS_HOOK_POSITION`, `TICONS_SHOW_IN_LIST`, etc.

#### Registered Hooks Table

The module registers several hooks to display icons in the front office. The exact hooks used depend on the PrestaShop version and the merchant’s configuration.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Enqueues CSS and JS assets (Tooltipster, custom JS/CSS). |
| `displayProductAdditionalInfo` | On the product page, within the “Additional Info” block (PS 1.7+). | Renders icons associated with the current product. |
| `displayProductPriceBlock` | On the product page, near the price. | Renders icons associated with the current product. |
| `displayAfterProductThumbs` | On the product page, below product images (PS 1.7+). | Renders icons associated with the current product. |
| `displayProductListFunctionalButtons` | On product list items (e.g., category pages). | Renders icons on product cards/thumbnails. |
| `displayProductListReviews` | On product list items, near reviews. | Renders icons on product cards/thumbnails. |
| `displayProductDeliveryTime` | On the product page, near delivery info. | Renders icons associated with the current product. |
| `displayLeftColumn` | In the left column of pages. | Renders icons if configured for general display. |
| `displayRightColumn` | In the right column of pages. | Renders icons if configured for general display. |
| `displayFooterProduct` | At the bottom of the product page. | Renders icons associated with the current product. |
| `actionProductUpdate` | After a product is updated in the back office. | Potentially clears cache or updates icon associations. |
| `actionProductDelete` | After a product is deleted. | Cleans up associated icon entries from `ps_ticon_products`. |
| `actionObjectLanguageAddAfter` | After a new language is added. | Ensures language-specific fields for icons are handled. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the “Product Tag Icons Pro” module.
