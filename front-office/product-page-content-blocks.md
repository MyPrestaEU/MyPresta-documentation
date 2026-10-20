---
title: "Product page content blocks - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Product page content blocks PrestaShop module by MyPresta.eu."
sidebar:
  label: "Product page content blocks - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Product page content blocks Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-content-blocks.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/product-page-content-blocks/)
>
> ---


# Product page content blocks

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for a PrestaShop installation and this module does not introduce additional specific requirements beyond that.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The “Product page content blocks” module primarily operates through a dedicated tab on each product’s edit page, rather than a single global configuration screen. However, there is a main module configuration page for initial setup and an AJAX controller for managing the blocks.

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

When you first install the module and click “Configure,” you will be taken to its main configuration page. This page typically handles initial setup or global settings if any.

- **What this setting does:** This page serves as the entry point for the module. While the core functionality of creating blocks is done on product pages, this screen might offer general settings or a quick overview.
- **Effect of changing this setting:** Any settings here would apply globally to how the module behaves across all product pages, such as enabling/disabling the module entirely or setting default behaviors.
- **Recommended value:** Follow on-screen instructions. If there are no specific settings, this page will simply confirm the module is installed and ready for use.
- **Merchant scenario / example:** You might find a toggle here to “Enable/Disable Module” which would turn off all custom content blocks across your store without uninstalling the module.

### 2.2 Dedicated Admin Screens & Controller Views

The primary interaction with this module happens on the product edit page.

#### 2.2.1 Product Edit Page (Catalog > Products > Edit a Product)

After installing the module, when you edit any product in your PrestaShop back office, you will find a new tab dedicated to “Product page content blocks” (or similar naming).

- **Screen Name & Menu Location:** **Catalog > Products > [Select/Edit a Product] > “Product page content blocks” tab**
- **Available Actions & Settings:**

  - **Adding a New Block:** You’ll typically see a button like “Add New Block” or a similar interface to create a new content block for the current product.
    - **What this setting does:** Allows you to define a new piece of content.
    - **Effect of changing this setting:** A new content block will be created and stored for this specific product.
    - **Merchant scenario / example:** You want to add a video tutorial for a complex product. You click “Add New Block.”
  - **Content Editor:** For each block, you will have a rich text editor (WYSIWYG) where you can input text, images, videos, or even custom HTML.
    - **What this setting does:** Defines the actual content that will be displayed.
    - **Effect of changing this setting:** The content you enter here will be rendered on the front office.
    - **Merchant scenario / example:** You type “Watch our unboxing video!” and embed a YouTube video link.
  - **Hook Selection:** A dropdown or list of available PrestaShop hooks (displayHeader, displayFooterProduct, displayRightColumnProduct, etc.).
    - **What this setting does:** Determines the exact position where your content block will appear on the product page.
    - **Effect of changing this setting:** The block will render in the selected hook’s position.
    - **Recommended value:** Choose the hook that best suits the content’s purpose. For product-specific details, `displayProductAdditionalInfo` or `displayFooterProduct` are common. For trust elements, `displayReassurance`.
    - **Merchant scenario / example:** You want a trust badge to appear near the add-to-cart button, so you select `displayReassurance`.
  - **Block Status (Enabled/Disabled):** A toggle to activate or deactivate the block.
    - **What this setting does:** Controls whether the block is visible on the front office.
    - **Effect of changing this setting:**
      - *When enabled:* The block will appear on the product page.
      - *When disabled:* The block will be hidden but not deleted, allowing you to reactivate it later.
    - **Recommended value:** Enable blocks you want to show, disable those you want to hide temporarily.
    - **Merchant scenario / example:** You have a seasonal promotion block that you want to hide after the season ends, but might reuse next year.
  - **Order/Position:** Often a drag-and-drop interface or an input field to set the display order if multiple blocks are in the same hook.
    - **What this setting does:** Determines the sequence of blocks within a single hook.
    - **Effect of changing this setting:** Blocks will appear in the specified order.
    - **Merchant scenario / example:** You have three trust badges in `displayReassurance` and want the “Free Shipping” badge to appear first.
  - **Editing/Deleting Blocks:** Buttons to modify existing blocks or remove them entirely.
    - **What this setting does:** Allows you to update content, hook, or status, or permanently remove a block.
    - **Effect of changing this setting:** Updates or removes the block from the product page.
    - **Merchant scenario / example:** A product description has changed, so you edit the content of a related block.
- **Recommended workflow for daily store management:**

  1. Navigate to **Catalog > Products** and select the product you wish to enhance.
  2. Click on the “Product page content blocks” tab.
  3. Click “Add New Block” to create a new content section.
  4. Enter your content using the rich text editor.
  5. Select the appropriate hook for where you want the content to appear.
  6. Ensure the block is enabled.
  7. Save your changes for the product.
  8. Repeat for other products as needed. Regularly review your product pages to ensure blocks are displaying as intended.

#### 2.2.2 AdminMegablocksAjaxController (megablocks/controllers/admin/AdminMegablocksAjax.php)

This controller is not directly accessed by merchants via a menu item. Instead, it handles the background operations (AJAX requests) when you interact with the “Product page content blocks” tab on the product edit page. For example, when you save a new block, edit an existing one, or change its order, this controller processes those requests without requiring a full page reload.

- **Screen Name & Menu Location:** Not directly accessible. It operates behind the scenes on the Product Edit Page.
- **Available Actions & Settings:** It manages the creation, updating, deletion, and reordering of content blocks for individual products.
- **Effect of changes:** Ensures that your changes to content blocks on the product edit page are saved to the database and reflected on the front office.
- **Recommended workflow for daily store management:** You interact with this controller implicitly by using the “Product page content blocks” tab on the product edit page. No direct interaction is required.

#### 2.2.3 index.php (megablocks/controllers/admin/index.php)

This file is a standard PrestaShop practice for securing admin controller directories and typically contains only a `die('Access Denied');` statement. It does not represent a functional screen or configuration area for the merchant.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration Page** | (Global settings if any) | (As per module defaults) | Initial setup, global enable/disable, or general module behavior. |
| **Product Edit Page (Tab)** | Add New Block | N/A | Creates a new content block for the current product. |
|  | Content Editor | Empty | Defines the HTML/text content of the block. |
|  | Hook Selection | Varies (e.g., `displayFooterProduct`) | Determines the display position on the product page. |
|  | Block Status | Enabled | Controls block visibility on the front office. |
|  | Order/Position | 1 (or next available) | Sets the display sequence of blocks within a hook. |
|  | Edit/Delete Block | N/A | Modifies or removes existing content blocks. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My new content block isn’t showing up on the product page. What should I do?**
**A1:**

1. **Check Block Status:** Go to the product edit page, navigate to the “Product page content blocks” tab, and ensure the block you created is set to “Enabled.”
2. **Clear Cache:** PrestaShop uses caching to speed up your store. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” if available).
3. **Verify Hook Selection:** Double-check that you’ve selected a hook that is actually rendered by your theme on the product page. Some themes might not use all standard PrestaShop hooks.
4. **Theme Compatibility:** If your theme is heavily customized, it might override standard hook placements. Contact your theme developer or a webmaster to confirm the theme’s hook structure.

**Q2: The content block looks strange or unstyled on my product page.**
**A2:**

1. **Check Your Content:** If you’ve added custom HTML or copied content from another source, it might contain conflicting styles. Try pasting your content into a plain text editor first to remove any hidden formatting, then re-paste it into the module’s editor.
2. **Module CSS:** The module includes some basic CSS. If your theme has very specific styling, it might override or conflict with the module’s styles.
3. **Custom Theme Styling:** For advanced styling, you might need a webmaster to add custom CSS rules to your theme’s stylesheet to make the block match your store’s design. They can target the specific HTML elements generated by the module.

**Q3: Can I use this module for multi-language stores?**
**A3:** Yes, typically content blocks created with this module will support PrestaShop’s multi-language functionality. When editing a block, you should see language tabs (e.g., English, French, Spanish) next to the content editor. You can enter different content for each language, ensuring your blocks are localized for your international customers.

**Q4: I want to display the same block on multiple product pages. Do I have to create it repeatedly?**
**A4:** This module is designed for *product-specific* content. If you need the *exact same* content block on many products, you would currently need to create it for each product. For truly global content that appears on *all* product pages (or all pages of a certain type), a different type of module (e.g., a custom HTML block module that hooks globally) might be more efficient. However, the strength of this module is its ability to tailor content per product.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the “Product page content blocks” module for developers and webmasters.

### 4.1 Architecture Overview

The “Product page content blocks” module (`megablocks`) follows a standard PrestaShop module architecture, primarily leveraging the `Module` class for installation and hook registration. Its core functionality revolves around managing product-specific content blocks, which are stored in a custom database table. The module extends PrestaShop’s back-office functionality by injecting a custom tab into the product edit page, managed by an AJAX controller. Front-office display is achieved by hooking into various `display*` hooks on the product page and rendering specific Smarty templates.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: This module does not contain any dedicated front-office controllers. All front-office content rendering is handled directly via registered hooks within the main `index.php` module file, which then renders specific templates.
- **Back-Office Admin Controllers**:

  - `megablocks/controllers/admin/AdminMegablocksAjax.php`
    - **Class name & parent class**: `AdminMegablocksAjaxController` extending `ModuleAdminController`.
    - **Responsibility**: This controller handles all AJAX requests originating from the “Product page content blocks” tab on the product edit page. It’s responsible for:
      - Creating new content blocks.
      - Updating existing content blocks (content, hook, status, position).
      - Deleting content blocks.
      - Fetching content block data for a specific product.
      - It does not have a direct menu entry but is invoked via JavaScript calls from the product edit page.
  - `megablocks/controllers/admin/index.php`
    - **Class name & parent class**: Not a functional controller.
    - **Responsibility**: This is a security file, standard in PrestaShop admin directories, containing `die('Access Denied');` to prevent direct directory listing or access.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes in the `classes/` directory. This implies that the module’s data handling (e.g., saving and retrieving content blocks) is likely managed directly within the main `megablocks/index.php` file, potentially using `Db::getInstance()` for direct database interactions or a simple array structure for configuration. If a custom database table is used, its schema and interaction methods would be defined within the main module file.

### 4.4 JavaScript Assets (`views/js/`)

- `megablocks/js/script.js`
  - **Scope**: Likely front-office.
  - **Details**: This script would contain any client-side logic required for the front-office display of the content blocks. This could include simple animations, responsive adjustments, or interactions if the blocks contain dynamic elements.
- `megablocks/views/admin/megablocks.js`
  - **Scope**: Back-office (Product Edit Page).
  - **Details**: This is the primary JavaScript file for managing content blocks in the back office. It’s responsible for:
    - Initializing the “Product page content blocks” tab on the product edit page.
    - Handling click events for “Add New Block,” “Edit,” and “Delete” buttons.
    - Managing the rich text editor (e.g., TinyMCE or CKEditor integration) for content input.
    - Sending AJAX requests to `AdminMegablocksAjaxController` for creating, updating, and deleting blocks.
    - Updating the UI dynamically based on AJAX responses (e.g., adding a new block to the list, removing a deleted block).
    - Implementing drag-and-drop functionality for reordering blocks.
- `megablocks/views/fancybox/script.js`
  - **Scope**: Back-office (Product Edit Page).
  - **Details**: This script likely integrates with or implements a “Fancybox” (or similar modal/lightbox library) for displaying the “Add New Block” or “Edit Block” forms in a popup window. It would handle opening/closing the modal, loading content into it, and submitting the form data.

### 4.5 CSS Stylesheets (`views/css/`)

- `megablocks/views/admin/megablocks.css`
  - **Scope**: Back-office admin form styling.
  - **Details**: Contains specific CSS rules for styling the “Product page content blocks” tab, the list of blocks, the add/edit forms, and any custom UI elements within the PrestaShop back office.
  - **Key CSS class selectors**: Developers can inspect the generated HTML on the product edit page to identify specific classes (e.g., `.megablocks-list`, `.megablock-item`, `.megablock-form`) to override or extend in their custom admin theme or module overrides.
- `megablocks/views/css/milligram.css`
  - **Scope**: Potentially both front-office and back-office, or specifically for modal forms.
  - **Details**: Milligram is a minimalist CSS framework. Its inclusion suggests the module might be using it for basic, clean styling of its generated content blocks on the front office, or for the modal forms in the back office (e.g., Fancybox content). It provides a lightweight base for typography, forms, and grid layout.
  - **Key CSS class selectors**: Standard Milligram classes (e.g., `.container`, `.row`, `.column`, `.button`, `.input`) would be present. Developers can override these or add more specific styles in their theme’s CSS.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/front/`)**: These templates are dynamically included by the module when a content block is configured for a specific hook. Each `megablock-*.tpl` file likely serves as a wrapper or a standard template for rendering the content of a single block. The actual content (HTML) defined by the merchant is usually passed as a Smarty variable and rendered directly.

  - `megablocks/views/front/megablock-actionProductOutOfStock.tpl`: Renders content when a product is out of stock.
  - `megablocks/views/front/megablock-displayAfterProductThumbs.tpl`: Renders content after product images/thumbnails.
  - `megablocks/views/front/megablock-displayBeforeBodyClosingTag.tpl`: Renders content just before the `</body>` tag.
  - `megablocks/views/front/megablock-displayFooter.tpl`: Renders content in the general site footer.
  - `megablocks/views/front/megablock-displayFooterBefore.tpl`: Renders content before the general site footer.
  - `megablocks/views/front/megablock-displayFooterProduct.tpl`: Renders content in the product-specific footer area.
  - `megablocks/views/front/megablock-displayHeader.tpl`: Renders content in the general site header.
  - `megablocks/views/front/megablock-displayLeftColumnProduct.tpl`: Renders content in the left column of the product page.
  - `megablocks/views/front/megablock-displayNav1.tpl`: Renders content in the first navigation area.
  - `megablocks/views/front/megablock-displayNav2.tpl`: Renders content in the second navigation area.
  - `megablocks/views/front/megablock-displayProductAdditionalInfo.tpl`: Renders content in the additional product information section.
  - `megablocks/views/front/megablock-displayProductPriceBlock.tpl`: Renders content near the product price block.
  - `megablocks/views/front/megablock-displayReassurance.tpl`: Renders content in the reassurance block (e.g., trust badges).
  - `megablocks/views/front/megablock-displayRightColumnProduct.tpl`: Renders content in the right column of the product page.
  - `megablocks/views/front/megablock-displayTop.tpl`: Renders content in the top section of the page.
- **Admin templates (`views/templates/admin/`)**:

  - `megablocks/views/admin/li_megablock.tpl`: This template is likely used to render a single item in the list of content blocks on the product edit page. It would display the block’s title, selected hook, status, and edit/delete buttons.
  - `megablocks/views/admin/tabs.tpl`: This template probably defines the structure of the “Product page content blocks” tab itself, including the “Add New Block” button and the container for the list of blocks.
- **Fancybox templates (`views/fancybox/`)**: These templates are used for the modal forms (Fancybox) in the back office.

  - `megablocks/views/fancybox/edit.tpl`: The form template for editing an existing content block.
  - `megablocks/views/fancybox/heading.tpl`: A template for the heading or title of the Fancybox modal.
  - `megablocks/views/fancybox/new.tpl`: The form template for creating a new content block.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module likely creates a custom database table, for example, `ps_megablocks` (or similar), to store the content blocks.
  - This table would typically contain fields such as:
    - `id_megablock`: Primary key.
    - `id_product`: Foreign key linking to `ps_product`.
    - `hook_name`: The name of the PrestaShop hook where the block is displayed (e.g., `displayFooterProduct`).
    - `position`: The order of the block within its hook.
    - `active`: Boolean (0 or 1) for block status.
    - `content`: The actual HTML content of the block (likely a `TEXT` or `LONGTEXT` field).
    - `content_lang`: If content is multilingual, this might be a separate table (`ps_megablocks_lang`) or handled via serialized data in `content`.
  - Configuration records are stored in `ps_configuration` for global module settings (e.g., `MEGABLOCKS_ENABLED`).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| :--- | :---
| `displayHeader` | Renders content in the `<head>` section of the HTML document. | N/A | Primarily for including CSS, JavaScript, meta tags, or other elements that affect the page’s technical behavior or global styling. |
| `displayNav1` | Renders content in the first navigation area. | N/A | Typically for displaying elements like currency selectors, language selectors, or quick links. |
| `displayNav2` | Renders content in the second navigation area. | N/A | Often used for customer account links, contact information, or other secondary navigation elements. |
| `displayTop` | Renders content in the top section of the page, usually below the header but above the main content. | N/A | Ideal for banners, search bars, or important announcements. |
| `displayLeftColumnProduct` | Renders content in the left sidebar of the product page. | N/A | Suitable for product filters, related categories, or promotional blocks specific to the product. |
| `displayRightColumnProduct` | Renders content in the right sidebar of the product page. | N/A | Similar to the left column, can be used for cross-sells, customer service info, or trust badges. |
| `displayAfterProductThumbs` | Renders content immediately after the product image thumbnails. | N/A | Good for quick product highlights, short videos, or specific feature callouts. |
| `displayProductAdditionalInfo` | Renders content within the product’s main information block, often near the description or features. | N/A | Excellent for detailed specifications, usage instructions, or unique selling propositions. |
| `displayProductPriceBlock` | Renders content near the product’s price display. | N/A | Useful for displaying financing options, price guarantees, or special discount messages. |
| `displayReassurance` | Renders content in the product reassurance block, typically near the add-to-cart button. | N/A | Perfect for trust badges, delivery information, return policies, or secure payment icons. |
| `displayFooterProduct` | Renders content in the product-specific footer area, usually below the main product details. | N/A | Can be used for extended product details, FAQs, or customer reviews. |
| `actionProductOutOfStock` | Executes when a product goes out of stock. | N/A | Allows displaying specific messages or forms for out-of-stock products. |
| `displayFooterBefore` | Renders content just before the main site footer. | N/A | Suitable for last-minute promotions or calls to action before the footer. |
| `displayFooter` | Renders content in the general site footer. | N/A | For site-wide information, but can be customized per product for unique footer elements. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Product page content blocks” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and integration with your PrestaShop store.
