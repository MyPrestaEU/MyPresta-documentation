---
title: "Product page popup - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Product page popup PrestaShop module by MyPresta.eu."
sidebar:
  label: "Product page popup - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Product page popup Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-popup.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/product-page-popup/)
>
> ---


# Product page popup

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, you will be directed to the module’s main configuration page. Here you can manage all your product page popups.

The configuration page is divided into two main sections:

1. **“Add new popup”** tab: For creating new popup windows.
2. **“List of popups”** tab: To view, edit, or delete existing popups.

#### 2.1.1 “Add new popup” Tab

This tab allows you to define a new popup window and its associated settings.

- **Popup Name:**

  - **What this setting does:** This is an internal name for your popup, visible only in your PrestaShop back office. It helps you identify and manage different popups.
  - **Effect of changing this setting:** Changing this name only affects how you see it in the back office; it has no impact on the front office or customer experience.
  - **Recommended value:** Use a descriptive name, e.g., “Summer Sale on T-Shirts,” “Sizing Guide for Jeans,” “Video Tutorial for Product X.”
  - **Merchant scenario / example:** If you have a popup for a specific product, name it after that product to easily find it later.
- **Popup Content:**

  - **What this setting does:** This is the main content that will be displayed inside the popup window. It’s a rich text editor (TinyMCE) where you can add text, images, videos, links, and even custom HTML.
  - **Effect of changing this setting:** This directly changes what your customers see when the popup appears. You can make it informative, promotional, or interactive.
  - **Recommended value:** Keep it concise and visually appealing. Use headings, bullet points, and relevant images.
  - **Merchant scenario / example:** You could add a discount code, an embedded YouTube video demonstrating the product, or a detailed sizing chart.
- **Popup Width (px):**

  - **What this setting does:** Defines the width of the popup window in pixels.
  - **Effect of changing this setting:** A larger width will make the popup wider, potentially accommodating more content horizontally. A smaller width will make it narrower.
  - **Recommended value:** Start with `600px` and adjust based on your content. Ensure it looks good on various screen sizes.
  - **Merchant scenario / example:** If your popup contains a wide image or a table, you might need a larger width. For simple text, a narrower width might be sufficient.
- **Popup Height (px):**

  - **What this setting does:** Defines the height of the popup window in pixels.
  - **Effect of changing this setting:** A larger height will make the popup taller, allowing more vertical content without scrolling. A smaller height will make it shorter, potentially requiring scrolling if content exceeds the height.
  - **Recommended value:** Start with `400px` and adjust based on your content.
  - **Merchant scenario / example:** If you have a long text description or a tall image, increase the height. If the content is short, a smaller height looks cleaner.
- **Popup Background Color:**

  - **What this setting does:** Allows you to choose the background color of the popup window itself. This uses a color picker tool.
  - **Effect of changing this setting:** Changes the visual appearance of the popup, helping it match your store’s branding or stand out.
  - **Recommended value:** Choose a color that complements your store’s design and ensures good readability of your content.
  - **Merchant scenario / example:** Use your brand’s primary color for the background, or a neutral white/light grey for maximum readability.
- **Popup Border Color:**

  - **What this setting does:** Allows you to choose the color of the border around the popup window.
  - **Effect of changing this setting:** Adds a visual frame to the popup, defining its edges.
  - **Recommended value:** Often, a subtle border color that matches your store’s aesthetic or a contrasting color to make the popup pop.
  - **Merchant scenario / example:** A light grey border for a clean look, or a vibrant color if the popup is meant to be very attention-grabbing.
- **Popup Border Width (px):**

  - **What this setting does:** Defines the thickness of the popup’s border in pixels.
  - **Effect of changing this setting:** A higher value makes the border thicker and more prominent.
  - **Recommended value:** `1px` or `2px` for a subtle border.
  - **Merchant scenario / example:** A `5px` border might be used for a very bold, urgent message, while `1px` is more common for general information.
- **Popup Border Radius (px):**

  - **What this setting does:** Controls the roundness of the popup’s corners. A value of `0` means sharp, square corners. Higher values create more rounded corners.
  - **Effect of changing this setting:** Affects the overall aesthetic of the popup, making it look softer or more modern.
  - **Recommended value:** `0px` for sharp corners, `5px` to `10px` for slightly rounded corners.
  - **Merchant scenario / example:** If your store design uses rounded elements, a `10px` border radius would make the popup fit in better.
- **Popup Overlay Color:**

  - **What this setting does:** This is the color of the semi-transparent layer that appears behind the popup, dimming the rest of the product page.
  - **Effect of changing this setting:** Changes the visual contrast between the popup and the background. A darker overlay makes the popup stand out more.
  - **Recommended value:** A semi-transparent black (`#000000` with some transparency) is standard.
  - **Merchant scenario / example:** A slightly lighter overlay might be used if you want the background product information to still be somewhat visible.
- **Popup Overlay Opacity (0-100):**

  - **What this setting does:** Controls the transparency of the overlay color. `0` is fully transparent (invisible), `100` is fully opaque (solid color, completely hides background).
  - **Effect of changing this setting:** Determines how much of the underlying product page is visible through the overlay.
  - **Recommended value:** `70` to `80` is a good balance, making the popup prominent without completely obscuring the page.
  - **Merchant scenario / example:** If you want the customer to still faintly see the product image behind the popup, use a lower opacity like `50`.
- **Products for this popup:**

  - **What this setting does:** This is the crucial part where you select which specific products will trigger this popup. You can search for products by name.
  - **Effect of changing this setting:** The popup will *only* appear on the product pages you select here. If no products are selected, the popup will not appear anywhere.
  - **Recommended value:** Select all relevant products for this specific message.
  - **Merchant scenario / example:** If you’ve created a popup with a sizing guide for “Men’s T-Shirts,” you would select all your men’s t-shirt products here.

After configuring all settings, click the **“Save”** button to create your new popup.

#### 2.1.2 “List of popups” Tab

This tab displays a table of all the popups you have created.

- **Table Columns:**
  - **ID:** Unique identifier for the popup.
  - **Name:** The internal name you gave the popup.
  - **Products:** Lists the number of products associated with this popup.
  - **Actions:**
    - **Edit:** Click the pencil icon to go back to the “Add new popup” tab with all the current popup’s settings pre-filled, allowing you to modify them.
    - **Delete:** Click the trash can icon to permanently remove the popup. A confirmation prompt will appear.
- **Effect of changes:**
  - **Editing:** Allows you to update content, styling, or product associations for an existing popup without creating a new one.
  - **Deleting:** Permanently removes the popup from your store. It will no longer appear on any product pages.
- **Recommended workflow:** Regularly review this list to ensure all your popups are up-to-date and relevant. Delete any outdated promotions or information.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Add new popup** | Popup Name | Descriptive name | Internal identification for back office. |
|  | Popup Content | Custom HTML/Text | Main message displayed to customer. |
|  | Popup Width (px) | 600px | Horizontal size of the popup. |
|  | Popup Height (px) | 400px | Vertical size of the popup. |
|  | Popup Background Color | White / Brand color | Background color of the popup content area. |
|  | Popup Border Color | Subtle / Brand color | Color of the frame around the popup. |
|  | Popup Border Width (px) | 1px - 2px | Thickness of the popup border. |
|  | Popup Border Radius (px) | 0px - 10px | Roundness of popup corners. |
|  | Popup Overlay Color | Semi-transparent black | Color of the dimmed background. |
|  | Popup Overlay Opacity (0-100) | 70 - 80 | Transparency of the background overlay. |
|  | Products for this popup | Select relevant products | Determines on which product pages the popup appears. |
| **List of popups** | Edit Action | N/A | Modify an existing popup’s settings. |
|  | Delete Action | N/A | Remove a popup permanently. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My popup isn’t appearing on the product page. What should I check?**
A:

1. **Is the popup associated with the correct product?** Go to the module configuration, edit your popup, and ensure the specific product you’re testing on is selected in the “Products for this popup” field.
2. **Is the module enabled?** In **Modules > Module Manager**, ensure “Product page popup” is installed and enabled.
3. **Clear your PrestaShop cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Your browser cache might also need clearing (Ctrl+F5 or Cmd+R).
4. **Check for JavaScript errors:** Open your browser’s developer console (F12) and look for any errors in the “Console” tab. If you see errors, it might indicate a conflict with another module or your theme.

**Q: The popup looks strange or doesn’t match my theme’s styling.**
A:

1. **Review popup styling settings:** Double-check the “Popup Background Color,” “Popup Border Color,” “Popup Border Width,” and “Popup Border Radius” settings in the module configuration.
2. **Theme conflicts:** Your theme’s CSS might be overriding the module’s styles. If you’re comfortable with CSS, you can inspect the popup elements using your browser’s developer tools to identify conflicting styles. For complex styling issues, you might need a web developer to assist.

**Q: Can I have multiple popups on the same product page?**
A: No, the module is designed to display one specific popup per product page. If a product is associated with multiple popups, only one will be displayed (typically the first one found or the one with the lowest ID, though this behavior isn’t explicitly guaranteed and should be avoided). It’s best practice to create one comprehensive popup per product or group of products.

**Q: How do I translate the popup content into different languages?**
A: The “Popup Content” field in the module configuration should offer language tabs if your PrestaShop store has multiple languages enabled. Simply switch to the desired language tab and enter the translated content for that language.

**Q: The popup content is too long and requires scrolling. How can I fix this?**
A:

1. **Increase Popup Height:** In the module configuration, increase the “Popup Height (px)” value.
2. **Condense Content:** Try to make your popup content more concise. Use bullet points, shorter paragraphs, and link to external pages for very detailed information if possible.
3. **Optimize Images/Videos:** Ensure any media in your popup is optimized for web use to prevent excessive loading times and improve display.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The `Product page popup` module for PrestaShop 1.5.x and 1.6.x follows a straightforward, monolithic design pattern typical of older PrestaShop modules. It primarily uses the `Module` class for its core functionality, handling installation, uninstallation, and configuration. Front-office display is managed by hooking into standard display points, while configuration is handled via the `getContent()` method within the main module file. Data is stored directly in `ps_configuration` and managed through standard PrestaShop database interactions. There are no custom `ObjectModel` classes or dedicated front/admin controllers beyond the main module file.

### 4.2 Controllers (`controllers/`)

This module does not utilize dedicated front-office or back-office controllers in the `controllers/` directory. All front-office logic is handled directly within the main module file via hooks, and all back-office configuration is managed by the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)

This module does not contain any custom PHP classes or models in the `classes/` directory. All data handling and business logic are encapsulated within the main `ajax_productpopup.php` module file.

### 4.4 JavaScript Assets (`views/js/`)

- **`productpopup/js/jscolor/jscolor.js`**
  - **Scope:** Back-office.
  - **Description:** This is a third-party JavaScript library for providing a color picker functionality. It’s used in the module’s configuration form to allow merchants to easily select colors for the popup background, border, and overlay. It typically works by attaching itself to input fields with a specific class (e.g., `jscolor`).
- **`productpopup/js/script.js`**
  - **Scope:** Front-office.
  - **Description:** This script contains the core logic for displaying the popup on the front office.
    - **Event Listeners:** It likely listens for the `DOMContentLoaded` event or similar to ensure the page is fully loaded.
    - **DOM Manipulation:** It’s responsible for:
      - Checking if the current product ID has an associated popup.
      - Dynamically creating the popup HTML structure (overlay, popup container, content area, close button).
      - Injecting the popup content (retrieved from the module’s configuration).
      - Applying the configured styles (width, height, colors, border, opacity).
      - Displaying the popup with an animation (e.g., fade-in).
      - Binding events to close the popup (click on close button, click on overlay, ESC key press).
- **`productpopup/js/tinymce16.inc.js`**
  - **Scope:** Back-office.
  - **Description:** This file is an integration script for the TinyMCE rich text editor, specifically tailored for PrestaShop 1.6.x environments. It initializes the TinyMCE editor for the “Popup Content” textarea in the module’s configuration form, providing the merchant with a WYSIWYG interface to create rich HTML content for the popups. It configures TinyMCE options such as available buttons, plugins, and language settings.

### 4.5 CSS Stylesheets (`views/css/`)

- **`productpopup/css/productpopup.css`**
  - **Scope:** Front-office.
  - **Description:** This stylesheet defines the default visual appearance and layout of the product page popup and its overlay.
    - **Main UI Components:** Styles for the `.productpopup-overlay` (the dimmed background) and `.productpopup-container` (the actual popup box).
    - **Key CSS Class Selectors:**
      - `.productpopup-overlay`: Controls `position`, `top`, `left`, `width`, `height`, `background-color`, `opacity`, `z-index`.
      - `.productpopup-container`: Controls `position`, `top`, `left`, `transform` (for centering), `background-color`, `border`, `border-radius`, `box-shadow`, `z-index`, `overflow`.
      - `.productpopup-content`: Styles for the inner content area, including `padding`, `font-size`, `line-height`.
      - `.productpopup-close`: Styles for the close button (e.g., `position`, `top`, `right`, `font-size`, `color`, `cursor`).
    - **Developer Override:** Developers can override these styles in their theme’s `global.css` or by creating a custom stylesheet loaded after this one, targeting these specific classes.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**: This module does not explicitly define templates for specific hooks in this directory. The front-office popup HTML is likely generated dynamically by `script.js` based on configuration.
- **Admin templates (`views/templates/admin/`)**:
  - **`productpopup/views/templates/admin/tabs-no-product.tpl`**
    - **Description:** This template is likely used within the module’s `getContent()` method to render the “Add new popup” form when no specific popup is being edited, or perhaps a simplified version of the form. It contains the input fields for popup name, content, dimensions, colors, and the product selection interface.
  - **`productpopup/views/templates/admin/tabs.tpl`**
    - **Description:** This is the main template for the module’s back-office configuration page. It typically renders the tab structure (e.g., “Add new popup” and “List of popups”) and includes the content of other admin templates (like `tabs-no-product.tpl`) within its tab panes. It also renders the table for listing existing popups.
- **Front-office templates (`views/templates/front/`)**:
  - **`productpopup/views/templates/front/footer.tpl`**
    - **Description:** This template is likely used to output a small, hidden HTML container or a JavaScript variable that holds the popup data (content, styles, product IDs) for the front-office `script.js` to pick up and render the popup dynamically. It’s typically hooked into `displayFooter` or `displayHeader` to ensure the data is available on every page load.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create custom SQL tables. All configuration settings and popup data are stored in the standard PrestaShop configuration table: `ps_configuration`.
  - **Configuration Keys**:
    - `PRODUCTPOPUP_DATA`: Stores serialized data for all created popups, including their content, styling, and associated product IDs. This key holds a complex array structure.
    - Other keys might exist for global module settings if any, but the primary data is in `PRODUCTPOPUP_DATA`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Executed in the `<head>` section of every page. | Likely used to include CSS and JavaScript files (`productpopup.css`, `script.js`) for the front-office popup functionality. |
| `displayFooter` | Executed at the end of the `<body>` section of every page. | Could be used to output the hidden data for `script.js` or to ensure the popup’s HTML structure is appended to the DOM after all other content. |
| `displayProductTab` (PrestaShop 1.6.x) / `displayProductExtraContent` (PrestaShop 1.7+) | Executed on the product page, typically within the product tabs or extra content area. | While the module’s description implies a modal, it might use this hook to inject a trigger for the popup, or to ensure its JS is loaded specifically on product pages. |
| `displayRightColumn` / `displayLeftColumn` | Executed in the side columns of the store. | Less likely for a product page popup, but could be used to inject a global trigger or a small script if needed. |
| `actionProductUpdate` / `actionProductAdd` / `actionProductDelete` | Executed when a product is added, updated, or deleted. | Could be used to update or clean up the `PRODUCTPOPUP_DATA` in `ps_configuration` if a product associated with a popup is removed. |

## 5. Official Support & Updates

For official updates, bug fixes, and dedicated developer support, please refer to your customer account at MyPresta.eu. Ensure you download the latest version of the “Product page popup” module compatible with your PrestaShop installation. Our support team is available to assist with any issues or questions regarding the module’s functionality and integration.
