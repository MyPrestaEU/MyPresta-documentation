---
title: "Recently sold products slider - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Recently sold products slider PrestaShop module by MyPresta.eu."
sidebar:
  label: "Recently sold products slider - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Recently sold products slider Module on MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/recently-sold-products-slider.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/sliders-slideshows/recently-sold-products-slider/)
>
> ---


# Recently sold products slider

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for a PrestaShop installation and are sufficient for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the “Recently sold products slider” module. Here you can customize the appearance, behavior, and content of your product slider.

#### **Background Color (rsps\_c\_bg)**

- **What this setting does:** This controls the background color of the entire slider block.
- **Effect of changing this setting:**
  - *When set to a color (e.g., #FFFFFF for white):* The slider’s background will display in that specific color, helping it blend with or stand out from your theme.
  - *When left empty or invalid:* The slider might inherit background styles from your theme, or default to a transparent background.
- **Recommended value:** Choose a color that complements your store’s design. Often, a subtle color or one that matches your header/footer is best.
- **Merchant scenario / example:** If your store has a dark header, setting this to a dark grey or black could make the slider look integrated. If you want it to pop, a contrasting color might work.

#### **Border Color (rsps\_c\_border)**

- **What this setting does:** Defines the color of the border around the entire slider block.
- **Effect of changing this setting:**
  - *When set to a color (e.g., #CCCCCC for light grey):* A border of that color will appear around the slider.
  - *When left empty or invalid:* No explicit border will be applied by the module, though your theme might still add one.
- **Recommended value:** Often, a subtle border that matches your theme’s other borders or a transparent border is best.
- **Merchant scenario / example:** If your site uses thin grey borders for other elements, setting this to the same grey will maintain consistency.

#### **Font Color (rsps\_c\_font)**

- **What this setting does:** Sets the color of the text (product names) displayed within the slider.
- **Effect of changing this setting:**
  - *When set to a color (e.g., #333333 for dark grey):* The product names will appear in the chosen color.
  - *When left empty or invalid:* The text color might default to your theme’s general font color.
- **Recommended value:** Choose a color that provides good contrast with the slider’s background color for readability.
- **Merchant scenario / example:** If your slider background is dark, a light font color (like white or light grey) will be necessary for readability.

#### **Slider Padding (rsps\_s\_padding)**

- **What this setting does:** Controls the internal spacing (padding) between the content (text) and the edges of the slider block.
- **Effect of changing this setting:**
  - *When set to a value (e.g., “10px”):* The text will have 10 pixels of space on all sides from the slider’s border.
  - *When set to “0px” or empty:* The text will sit directly against the slider’s edges.
- **Recommended value:** “5px” or “10px” to give the text some breathing room and improve aesthetics.
- **Merchant scenario / example:** If your text looks too cramped, increasing the padding will add more space around it, making it look cleaner.

#### **Slider Font Size (rsps\_s\_font)**

- **What this setting does:** Determines the size of the font used for the product names in the slider.
- **Effect of changing this setting:**
  - *When set to a value (e.g., “14px”):* The text will be displayed at that specific pixel size.
  - *When left empty or invalid:* The font size might default to your theme’s general font size.
- **Recommended value:** “14px” or “16px” for good readability without being too large or too small.
- **Merchant scenario / example:** If the slider is in a prominent location like the header, a slightly larger font might be appropriate. For a sidebar, a smaller font might fit better.

#### **Slider Border (rsps\_s\_border)**

- **What this setting does:** Defines the thickness and style of the border around the *inner content* of the slider (the scrolling text area itself), distinct from the overall block border.
- **Effect of changing this setting:**
  - *When set to a value (e.g., “1px solid #CCCCCC”):* A 1-pixel solid light grey border will appear around the scrolling text.
  - *When left empty or invalid:* No explicit inner border will be applied.
- **Recommended value:** “0px” or “none” if you only want the outer block border. If you want a subtle separation, “1px solid #EEEEEE” can work.
- **Merchant scenario / example:** You might use this to create a distinct visual box for the scrolling text within the larger slider area.

#### **Movement Direction (rsps\_m\_dir)**

- **What this setting does:** Controls the direction in which the product names scroll within the slider.
- **Effect of changing this setting:**
  - *When set to “left”:* The text will scroll from right to left.
  - *When set to “right”:* The text will scroll from left to right.
- **Recommended value:** “left” is a common and natural reading direction for scrolling text.
- **Merchant scenario / example:** Most users are accustomed to left-scrolling text, so sticking to “left” often provides the best user experience.

#### **Movement Delay (rsps\_m\_delay)**

- **What this setting does:** Determines the speed of the scrolling animation. This is typically measured in milliseconds.
- **Effect of changing this setting:**
  - *When set to a lower value (e.g., “50”):* The text will scroll faster.
  - *When set to a higher value (e.g., “100”):* The text will scroll slower.
- **Recommended value:** “70” to “100” provides a smooth, readable speed without being too fast or too slow.
- **Merchant scenario / example:** If the text is too fast, customers can’t read it. If it’s too slow, it might not grab attention. Experiment to find a balance.

#### **Slider Position (rsps\_position)**

- **What this setting does:** Allows you to select the PrestaShop hook where the slider will be displayed in your store.
- **Effect of changing this setting:**
  - *When set to `displayHome`:* The slider will appear on your store’s homepage.
  - *When set to `displayHeader`:* The slider will appear in the header section of all pages.
  - *When set to `displayFooter`:* The slider will appear in the footer section of all pages.
  - *Other options (e.g., `displayLeftColumn`, `displayRightColumn`, `displayTop`):* The slider will appear in the respective column or top section.
- **Recommended value:** `displayHeader` or `displayHome` for maximum visibility, or `displayFooter` for a more subtle approach.
- **Merchant scenario / example:** If you want every visitor to see the recent sales immediately, choose `displayHeader`. If you want it to be part of your homepage content, choose `displayHome`.

#### **Number of Products (rsps\_nb)**

- **What this setting does:** Specifies how many recently sold products should be retrieved and displayed in the slider.
- **Effect of changing this setting:**
  - *When set to a lower number (e.g., “5”):* Only the 5 most recent sales will be shown.
  - *When set to a higher number (e.g., “20”):* Up to 20 recent sales will be included in the scrolling list.
- **Recommended value:** “10” to “15” to ensure a good variety of products without making the list excessively long.
- **Merchant scenario / example:** If your store has many sales, a higher number provides more social proof. If sales are less frequent, a lower number might be sufficient.

#### **Order By (rsps\_order)**

- **What this setting does:** Determines the sorting criteria for the products displayed in the slider.
- **Effect of changing this setting:**
  - *When set to “date\_add”:* Products will be ordered by the date they were added to the order (most recent first).
  - *When set to “product\_name”:* Products will be ordered alphabetically by name.
  - *When set to “price”:* Products will be ordered by price.
- **Recommended value:** “date\_add” to truly show “recently sold” items.
- **Merchant scenario / example:** To accurately reflect recent purchases, ordering by `date_add` is the most logical choice.

#### **Diversity (rsps\_diversity)**

- **What this setting does:** This setting controls whether the slider should show unique products or allow the same product to appear multiple times if it was sold recently.
- **Effect of changing this setting:**
  - *When enabled (e.g., “Yes” or “1”):* If the same product was sold multiple times, it will only appear once in the list of products to be displayed, ensuring a greater variety of items.
  - *When disabled (e.g., “No” or “0”):* The same product might appear multiple times in the slider if it was part of several recent orders.
- **Recommended value:** “Yes” (or “1”) to showcase a wider range of your catalog and prevent the slider from becoming repetitive.
- **Merchant scenario / example:** If you sell a very popular item, disabling diversity might mean the slider only shows that one item repeatedly. Enabling it ensures other products get a chance to be seen.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | **Background Color** (rsps\_c\_bg) | `#FFFFFF` (White) | Sets the background color of the slider block. |
| Module Configuration | **Border Color** (rsps\_c\_border) | `#CCCCCC` (Light Grey) | Sets the border color around the slider block. |
| Module Configuration | **Font Color** (rsps\_c\_font) | `#333333` (Dark Grey) | Sets the color of the product names text. |
| Module Configuration | **Slider Padding** (rsps\_s\_padding) | `10px` | Internal spacing around the text within the slider. |
| Module Configuration | **Slider Font Size** (rsps\_s\_font) | `14px` | Size of the font for product names. |
| Module Configuration | **Slider Border** (rsps\_s\_border) | `0px` | Border around the scrolling text area itself. |
| Module Configuration | **Movement Direction** (rsps\_m\_dir) | `left` | Direction of the scrolling animation (left or right). |
| Module Configuration | **Movement Delay** (rsps\_m\_delay) | `70` | Speed of the scrolling animation (lower = faster). |
| Module Configuration | **Slider Position** (rsps\_position) | `displayHeader` | PrestaShop hook where the slider will be displayed. |
| Module Configuration | **Number of Products** (rsps\_nb) | `10` | Maximum number of recently sold products to show. |
| Module Configuration | **Order By** (rsps\_order) | `date_add` | Sorting criteria for the displayed products. |
| Module Configuration | **Diversity** (rsps\_diversity) | `Yes` (1) | Ensures unique products are shown (prevents repetition). |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve configured the module, but the slider isn’t showing up on my store.**
**A1:**

- **Check Hook Position:** Go to **Design > Positions** in your PrestaShop Back Office. Search for the hook you selected in the module’s “Slider Position” setting (e.g., `displayHeader`, `displayHome`). Ensure the “Recently sold products slider” module is listed and enabled in that hook. If not, you might need to “Transplant a module” to the correct hook.
- **Clear Cache:** PrestaShop often caches content. Go to **Advanced Parameters > Performance** and click “Clear cache” at the top right.
- **Module Enabled:** Double-check that the module is enabled in **Modules > Module Manager**.
- **Recent Sales:** Ensure you actually have recent sales in your store. The module relies on existing order data.

**Q2: The slider is showing, but the colors or font sizes aren’t what I set.**
**A2:**

- **Clear Cache:** This is the most common reason for styling issues. Clear your PrestaShop cache (**Advanced Parameters > Performance**) and your browser’s cache (Ctrl+F5 or Cmd+R).
- **Theme Overrides:** Your PrestaShop theme might have its own CSS that is overriding the module’s styles. You may need to inspect the element using your browser’s developer tools (F12) to see which CSS rules are being applied. If it’s a theme conflict, you might need to add custom CSS to your theme to force the module’s styles.
- **Correct Input:** Ensure you’re using valid CSS color codes (e.g., `#RRGGBB` or `rgba(R,G,B,A)`) and pixel values (e.g., `14px`) in the module configuration.

**Q3: The text is scrolling too fast/slow, or it’s hard to read.**
**A3:**

- **Movement Delay:** Adjust the “Movement Delay” setting. A higher number makes it slower, a lower number makes it faster. Experiment until you find a comfortable reading speed.
- **Font Size & Contrast:** Ensure your “Slider Font Size” is adequate and that your “Font Color” has good contrast against your “Background Color.”
- **Number of Products:** If you have too many products and a very fast speed, it might be overwhelming. Reduce the “Number of Products” or slow down the “Movement Delay.”

**Q4: Can I translate the “Someone just bought…” text into other languages?**
**A4:** Yes, PrestaShop modules are typically translatable.

- Go to **International > Translations** in your Back Office.
- Select “Installed modules translations” for the “Type of translation.”
- Choose your theme.
- Select the language you want to translate.
- Find the “Recently sold products slider” module in the list and you should be able to edit the translatable strings.

**Q5: The slider looks fine on desktop but is broken or poorly formatted on mobile.**
**A5:**

- **Clear Cache:** Always start by clearing PrestaShop and browser cache.
- **Theme Responsiveness:** While the module itself is designed to be responsive, conflicts with your specific theme’s responsive CSS can occur.
- **Check Padding/Borders:** Excessive padding or borders might push content out of view on smaller screens. Try reducing “Slider Padding” or “Slider Border” temporarily to see if it resolves the issue.
- **Inspect on Mobile:** Use your browser’s developer tools (F12) and switch to mobile view, or test directly on a mobile device, to diagnose specific layout problems. Custom CSS might be needed in your theme to adjust for mobile if a conflict exists.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview of the “Recently sold products slider” module for developers, webmasters, and technical agencies.

### 4.1 Architecture Overview

The “Recently sold products slider” module (`recentlysoldproducts`) follows a standard PrestaShop module architecture. It’s a single-file module (`recentlysoldproducts.php`) that extends `Module`, handling its own installation, uninstallation, configuration (`getContent()`), and front-office display via hooks. It leverages PrestaShop’s `Configuration` class for settings storage and Smarty for templating. The front-office functionality is primarily driven by JavaScript for the scrolling animation and styling.

### 4.2 Controllers (`controllers/`)

This module does **not** contain any dedicated Front-Office or Back-Office Admin Controllers. All configuration is handled within the `getContent()` method of the main module file, and front-office rendering is managed directly through PrestaShop hooks.

### 4.3 Core Classes & Models (`classes/`)

This module does **not** contain any custom classes or `ObjectModel` definitions in a `classes/` directory. It directly queries the PrestaShop database for order and product information within the main module file.

### 4.4 JavaScript Assets (`views/js/`)

- **`recentlysoldproducts/jscolor/jscolor.js`**

  - **Scope:** Back-office (used in `getContent()` for color pickers).
  - **Description:** This is a third-party JavaScript library that provides a user-friendly color picker interface for input fields. It’s integrated into the module’s configuration form to allow merchants to easily select colors for the slider’s background, border, and font. It typically works by adding a class (e.g., `jscolor`) to an input field, which then transforms it into a color picker.
- **`recentlysoldproducts/js/script.js`**

  - **Scope:** Front-office.
  - **Description:** This file likely contains the core logic for the scrolling slider animation. It would typically:
    - Select the slider container element (e.g., by ID or class).
    - Initialize variables for movement direction, speed, and content.
    - Implement a continuous scrolling animation loop, potentially using `setInterval` or `requestAnimationFrame`.
    - Handle cloning elements to create an infinite loop effect.
    - Adjust for responsiveness or pauses on hover.
- **`recentlysoldproducts/recentlysoldproducts.js`**

  - **Scope:** Front-office.
  - **Description:** This file might contain additional front-office JavaScript specific to the module’s initialization or interaction. It could be responsible for:
    - Loading the slider content dynamically (though in this module, it’s likely rendered by Smarty).
    - Setting up event listeners (e.g., for pausing the slider on mouse hover).
    - Ensuring the slider initializes correctly after the DOM is ready.
    - Potentially handling AJAX if the module were to fetch data asynchronously (though not explicitly indicated by the module structure).

### 4.5 CSS Stylesheets (`views/css/`)

- **`recentlysoldproducts/css.css`**

  - **Scope:** Front-office.
  - **Description:** This is likely the primary stylesheet for the front-office display of the slider. It would define:
    - Layout and positioning of the slider container.
    - Basic styling for the scrolling text elements (e.g., `font-size`, `color`, `padding`).
    - Styles for the background and borders based on module configuration.
    - Potentially responsive adjustments for different screen sizes.
    - Key selectors: `.recentlysoldproducts_block`, `.recentlysoldproducts_item`, etc.
- **`recentlysoldproducts/recentlysoldproducts.css`**

  - **Scope:** Front-office.
  - **Description:** This file might contain additional or specific styling rules, potentially for more advanced visual effects or to override default theme styles. Given the naming, it could also be a redundant or legacy file, or contain more specific styling for the scrolling mechanism itself, distinct from the general block styling in `css.css`. Developers should check for overlapping rules and potential conflicts.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`recentlysoldproducts/views/front/rsps.tpl`**
  - **Scope:** Front-office (hook template).
  - **Description:** This is the main template file responsible for rendering the HTML structure of the recently sold products slider.
  - **Rendered in hooks:** `rightColumn`, `displayrightColumn`, `home`, `top`, `displayleftColumn`, `footer`, `displayhome`, `displayheader`, `displaytop`, `displayfooter`, `header`, `leftColumn`.
  - **Content:** It receives data (e.g., a list of recently sold products, module configuration settings) from the `hookDisplay*` methods in `recentlysoldproducts.php`. It then iterates through the product list to generate the scrolling text, applying inline styles or classes based on the module’s configuration settings (colors, font sizes, padding, etc.). It will contain the main HTML wrapper for the slider and the individual product entries.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create any custom database tables.
  - It stores its configuration settings in PrestaShop’s `ps_configuration` table. The keys used are:
    - `RSPS_C_BG`
    - `RSPS_C_BORDER`
    - `RSPS_C_FONT`
    - `RSPS_S_PADDING`
    - `RSPS_S_FONT`
    - `RSPS_S_BORDER`
    - `RSPS_M_DIR`
    - `RSPS_M_DELAY`
    - `RSPS_POSITION`
    - `RSPS_NB`
    - `RSPS_ORDER`
    - `RSPS_DIVERSITY`
  - It queries existing PrestaShop tables, primarily `ps_orders`, `ps_order_detail`, `ps_product_lang`, and `ps_product` to retrieve recently sold product information.
- **Registered Hooks Table**:

| Hook Name | Execution Timing & Location | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Registers CSS/JS assets and potentially renders a hidden element for JS initialization. |
| `header` | Alias for `displayHeader` in older PrestaShop versions. | Same as `displayHeader`. |
| `displayHome` | On the homepage, usually in the main content area. | Renders the slider block on the store’s homepage. |
| `home` | Alias for `displayHome` in older PrestaShop versions. | Same as `displayHome`. |
| `displayTop` | In the top section of the page, often below the header. | Renders the slider block in the top content area. |
| `top` | Alias for `displayTop` in older PrestaShop versions. | Same as `displayTop`. |
| `displayLeftColumn` | In the left sidebar of applicable pages. | Renders the slider block in the left column. |
| `leftColumn` | Alias for `displayLeftColumn` in older PrestaShop versions. | Same as `displayLeftColumn`. |
| `displayRightColumn` | In the right sidebar of applicable pages. | Renders the slider block in the right column. |
| `rightColumn` | Alias for `displayRightColumn` in older PrestaShop versions. | Same as `displayRightColumn`. |
| `displayFooter` | In the footer section of every page. | Renders the slider block in the footer. |
| `footer` | Alias for `displayFooter` in older PrestaShop versions. | Same as `displayFooter`. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Recently sold products slider” module, please refer to your customer account at MyPresta.eu. Our support team is available to assist with any issues or questions you may have.
