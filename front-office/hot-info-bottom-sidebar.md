---
title: "Hot Info - bottom sidebar - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Hot Info - bottom sidebar PrestaShop module by MyPresta.eu."
sidebar:
  label: "Hot Info - bottom sidebar - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Hot Info - bottom sidebar Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/hot-info-bottom-sidebar.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/hot-info-bottom-sidebar/)
>
> ---


# Hot Info - bottom sidebar

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and are usually available on any modern hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installing the module, click “Configure” to access its settings. This is where you’ll define the content and appearance of your “Hot Info” sidebar.

#### **Content for Hot Info Block**

- **What this setting does:** This is the main area where you will enter the actual content that customers will see in the bottom sidebar. It’s a rich text editor (WYSIWYG - What You See Is What You Get), similar to what you might use for product descriptions or blog posts.
- **Effect of changing this setting:**
  - *When content is added:* The text, images, links, or HTML you enter here will be displayed in the “Hot Info” block on your storefront.
  - *When left empty:* The “Hot Info” block might still appear, but it will be empty, or the module might not display at all (depending on other settings and theme behavior). It’s crucial to add content here for the module to be useful.
- **Recommended value:** Enter your desired “hot information” here. Use clear, concise language and strong calls to action.
- **Merchant scenario / example:** You could add “FLASH SALE! Get 20% off all summer items with code SUMMER20! [Shop Now]” with a link to your summer collection. Or “Free Shipping on all orders over $50!”

#### **Background Color**

- **What this setting does:** This controls the background color of the “Hot Info” block. You can select a color using a color picker tool.
- **Effect of changing this setting:**
  - *When set to a specific color (e.g., #FF0000 for red):* The background of the “Hot Info” block will display in that chosen color.
  - *When left default or transparent:* It will typically inherit the background color from your theme or be transparent, which might make it blend in too much or be hard to read.
- **Recommended value:** Choose a color that either complements your store’s branding or stands out to draw attention, depending on your goal. A contrasting color can be very effective.
- **Merchant scenario / example:** If your store uses a lot of blue, you might choose a vibrant orange or yellow to make a sale announcement pop.

#### **Border Color**

- **What this setting does:** This controls the color of the border around the “Hot Info” block.
- **Effect of changing this setting:**
  - *When set to a specific color (e.g., #000000 for black):* The border of the “Hot Info” block will display in that chosen color.
  - *When left default or transparent:* The block might appear without a visible border, or it might inherit a border color from your theme.
- **Recommended value:** Often, a border color that matches your text color or a slightly darker shade of your background color works well.
- **Merchant scenario / example:** If your background is light blue, a darker blue border can give it a clean, defined look.

#### **Border Size (in pixels)**

- **What this setting does:** This determines the thickness of the border around the “Hot Info” block, measured in pixels.
- **Effect of changing this setting:**
  - *When set to a value like ‘2’:* The block will have a 2-pixel thick border.
  - *When set to ‘0’:* No border will be displayed.
- **Recommended value:** Start with a small value like ‘1’ or ‘2’ for a subtle border. Increase it if you want a more pronounced frame.
- **Merchant scenario / example:** A 2px border can subtly frame your message, making it look more like a distinct element on the page.

#### **Height (in pixels)**

- **What this setting does:** This controls the fixed height of the “Hot Info” block, measured in pixels.
- **Effect of changing this setting:**
  - *When set to a value like ‘50’:* The block will be 50 pixels tall.
  - *When content exceeds height:* If your content is taller than the specified height, a scrollbar will appear within the block, allowing customers to scroll through the content.
- **Recommended value:** Keep this value relatively small (e.g., 40-60px) to avoid taking up too much screen space, especially on mobile. Adjust based on the amount of content you have.
- **Merchant scenario / example:** If you have a short, single-line message, a height of 40px might be perfect. If you have a few lines of text, you might need 60-80px.

#### **Default Language (PS\_LANG\_DEFAULT)**

- **What this setting does:** This is a standard PrestaShop setting that defines the default language for your store. While not directly configured by this module, the module’s content field will typically show the content for the currently selected language in the back office, defaulting to this one.
- **Effect of changing this setting:** This affects the default language of your entire PrestaShop store and how multi-language content is managed. For this module, it means the content you enter will be associated with the language you are currently editing in the back office.
- **Recommended value:** This should be set to your primary store language.
- **Merchant scenario / example:** If your primary market is the USA, this would be set to English. When you enter content for the “Hot Info” block, ensure you’re editing in the correct language if your store supports multiple languages.

#### **MyPresta.eu Updates (mypresta\_updates, update\_, updatev\_)**

- **What these settings do:** These are internal settings used by MyPresta.eu modules to check for and manage updates. They typically store information about the module’s version and when it last checked for updates.
- **Effect of changing these settings:**
  - *When enabled/active:* The module can communicate with MyPresta.eu servers to notify you of new versions or security patches.
  - *When disabled/inactive:* The module will not check for updates automatically.
- **Recommended value:** Leave these settings as they are. They are essential for keeping your module up-to-date and secure.
- **Merchant scenario / example:** You don’t typically interact with these directly. They ensure you’re prompted in your PrestaShop back office when a new version of the module is available for download from your MyPresta.eu account.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | **Content for Hot Info Block** | Your custom message | The actual text, images, links displayed in the bottom sidebar. |
| Module Configuration | **Background Color** | Choose to match/contrast theme | Sets the background color of the info block. |
| Module Configuration | **Border Color** | Choose to match/contrast theme | Sets the color of the border around the info block. |
| Module Configuration | **Border Size (in pixels)** | 1 or 2 | Defines the thickness of the border. Set to 0 for no border. |
| Module Configuration | **Height (in pixels)** | 40-60 | Sets the fixed height of the info block. Content exceeding this will scroll. |
| Module Configuration | **PS\_LANG\_DEFAULT** | Your store’s primary language | PrestaShop’s default language setting, affects content editing. |
| Module Configuration | **MyPresta.eu Updates** | Enabled | Internal settings for module update checks. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My “Hot Info” block isn’t showing up on the front office.**

- **A:** First, ensure the module is installed and enabled in **Modules > Module Manager**. Second, check if you’ve actually added content in the “Content for Hot Info Block” field in the module’s configuration. An empty block might not render. Finally, clear your PrestaShop cache (**Advanced Parameters > Performance > Clear Cache**) and your browser cache.

**Q2: The “Hot Info” block looks strange or doesn’t match my theme’s styling.**

- **A:** The module provides basic styling options (background, border color/size, height). If it still clashes with your theme, your theme’s CSS might be overriding the module’s styles.
  - **Solution for Merchants:** Try adjusting the background and border colors in the module’s settings to see if you can find a better match. If not, you might need a webmaster to add custom CSS to your theme to specifically target and style the module’s block.
  - **Solution for Webmasters:** Inspect the element in the browser developer tools to identify conflicting CSS rules and apply more specific or `!important` rules in your theme’s custom CSS file.

**Q3: How do I add images or links to the “Hot Info” content?**

- **A:** Use the rich text editor provided for the “Content for Hot Info Block” setting. It has buttons for inserting images, creating links, formatting text (bold, italic), and more, just like a standard word processor. Click the “Image” icon to upload and insert an image, or select text and click the “Link” icon to add a hyperlink.

**Q4: Can I make the “Hot Info” block appear only on certain pages?**

- **A:** This module, in its current version, is designed to appear globally on all pages where the `displayHeader` hook is executed. If you need page-specific visibility, you would require custom development to modify the module’s display logic or use a separate module designed for conditional content display.

**Q5: The color picker isn’t working or showing up.**

- **A:** Ensure your browser’s JavaScript is enabled. Sometimes, conflicts with other modules or theme JavaScript can prevent the color picker from loading correctly. Try clearing your browser cache and cookies. If the issue persists, it might indicate a more complex JavaScript conflict, which a webmaster would need to investigate.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview of the “Hot Info - bottom sidebar” module for developers and webmasters.

### 4.1 Architecture Overview

The `hotinfo` module is a standard PrestaShop module following the MVC pattern where applicable. It primarily functions as a display module, injecting content into the `displayHeader` hook. Configuration is handled via the main module class’s `getContent()` method, storing settings directly in `ps_configuration`. It leverages a rich text editor (TinyMCE) for content input and a JavaScript color picker for styling options.

### 4.2 Controllers (`controllers/`)

This module does not utilize custom front-office or back-office controllers. All configuration is handled within the `hotinfo.php` main module file via the `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or extend `ObjectModel`. All data (configuration) is stored directly in the `ps_configuration` table.

### 4.4 JavaScript Assets (`views/js/`)

- **`hotinfo/jscolor/jscolor.js`**

  - **Scope:** Back-office (module configuration page).
  - **Description:** This is a third-party JavaScript library that provides a user-friendly color picker interface. It’s typically initialized on input fields with a specific class (e.g., `jscolor`) to allow administrators to visually select colors for the background and border of the “Hot Info” block. It binds to input fields and updates their values based on user color selection.
- **`hotinfo/tinymce16.js`**

  - **Scope:** Back-office (module configuration page).
  - **Description:** This script likely initializes and configures a version of the TinyMCE rich text editor for the “Content for Hot Info Block” textarea. It transforms a standard HTML `<textarea>` into a feature-rich editor, allowing administrators to format text, insert images, create links, and manage HTML content without direct coding. This script would bind to the relevant textarea element and provide the editor interface.

### 4.5 CSS Stylesheets (`views/css/`)

- **`hotinfo/css/hotinfo.css`**
  - **Scope:** Front-office (customer-facing store).
  - **Description:** This stylesheet contains the primary CSS rules for the “Hot Info” bottom sidebar. It defines the fixed positioning, dimensions, background, border, and text styling for the block.
  - **Key Selectors (developers can override):**
    - `#hotinfo_block`: The main container for the entire “Hot Info” block. This is where `position: fixed; bottom: 0; width: 100%;` and other global styles are applied.
    - `#hotinfo_block .hotinfo_content`: The inner container for the actual content, where `overflow-y: auto;` might be applied if content exceeds the defined height.
    - Styles for `p`, `a`, `img` within `#hotinfo_block` to ensure content looks good.
  - **Override Strategy:** Developers can override these styles by adding more specific CSS rules in their theme’s `custom.css` or `theme.css` file, or by creating a child theme and modifying the module’s CSS directly if necessary.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`hotinfo/hotinfo.tpl`**

  - **Scope:** Back-office (module configuration page).
  - **Description:** This template is used to render the configuration form within the PrestaShop back office when accessing the module’s configuration page. It contains the HTML structure for the rich text editor, color pickers, and input fields for height and border settings. It uses Smarty variables to pre-fill form fields with current configuration values.
- **`hotinfo/views/templates/hook/hotinfo.tpl`**

  - **Scope:** Front-office (customer-facing store).
  - **Description:** This template is responsible for rendering the “Hot Info” block on the storefront. It’s hooked into `displayHeader`. It retrieves the configured content, background color, border color, border size, and height from Smarty variables passed by the module and applies them to the HTML structure.
  - **Key Elements:**
    - A main `div` with an ID like `hotinfo_block` for fixed positioning.
    - An inner `div` for the content, potentially with `overflow: auto;` for scrolling.
    - The actual content is rendered using `{html_entity_decode($hotinfo_body)}` to display the HTML from the rich text editor.
  - **Hook:** `displayHeader` (though visually it appears at the bottom, the hook is in the header to ensure it loads early).

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  The module does not create any custom SQL tables. All configuration settings are stored in the standard PrestaShop `ps_configuration` table.

  - `PS_CONFIGURATION` entries:
    - `HOTINFO_BODY`: Stores the HTML content for the “Hot Info” block (multi-language).
    - `HOTINFO_BG_COLOR`: Stores the hexadecimal background color value.
    - `HOTINFO_BR_COLOR`: Stores the hexadecimal border color value.
    - `HOTINFO_BR_SIZE`: Stores the integer value for border thickness.
    - `HOTINFO_HEIGHT`: Stores the integer value for the block height.
    - `MYPRESTA_UPDATES`, `UPDATE_`, `UPDATEV_`: Internal keys for MyPresta.eu update mechanism.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Executed in the `<head>` section of every page. | The module uses this hook to inject its CSS and JavaScript files, and to render the main HTML structure of the “Hot Info” block. Although the block is visually positioned at the bottom, rendering it via `displayHeader` ensures it’s available early in the page load and can be styled with `position: fixed;` effectively. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Hot Info - bottom sidebar” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). You can download the most recent version of the module from your order history. For any technical assistance or inquiries, please contact MyPresta.eu support directly.
