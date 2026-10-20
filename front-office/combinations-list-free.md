---
title: "Combinations List Free - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Combinations List Free PrestaShop module by MyPresta.eu."
sidebar:
  label: "Combinations List Free - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Combinations List Free Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/combinations-list-free.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/combinations-list-free/)
>
> ---


# Combinations List Free

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for a PrestaShop installation, but this module has no specific exotic requirements beyond a standard PrestaShop environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Combinations List Free” module in your Module Manager. This will take you to the main configuration screen.

#### General Settings

- **What this setting does:** This section controls the overall behavior and appearance of the combinations list on your product pages.

  - **Display combinations list on product page:**

    - **What this setting does:** This is the master switch to enable or disable the module’s functionality.
    - **Effect of changing this setting:**
      - *When enabled (YES):* The module will attempt to display the combinations list on product pages according to your other settings.
      - *When disabled (NO):* The module will be inactive, and your product pages will revert to PrestaShop’s default combination selectors (dropdowns).
    - **Recommended value:** YES (to use the module).
    - **Merchant scenario / example:** If you’re testing the module or temporarily want to disable it without uninstalling, set this to NO.
  - **Hook to display the combinations list:**

    - **What this setting does:** Determines where on the product page the combinations list will appear. This is crucial for integrating the list visually with your theme.
    - **Effect of changing this setting:**
      - *When set to `displayProductButtons` (or similar product-related hook):* The list will typically appear near the “Add to Cart” button or product price, often below the main product details.
      - *When set to `displayProductExtraContent` (or similar tab-related hook):* The list will appear within a new or existing product tab, keeping the main product description area cleaner.
      - *When set to `displayFooterProduct` (or similar footer hook):* The list will appear at the very bottom of the product page.
    - **Recommended value:** Experiment with different hooks to find the best visual integration with your specific theme. `displayProductButtons` or `displayProductExtraContent` are common choices.
    - **Merchant scenario / example:** If your product page is already long, placing the list in a `displayProductExtraContent` tab can make the page less cluttered. If you want the list immediately visible, a hook like `displayProductButtons` is better.
  - **Show combination image:**

    - **What this setting does:** Controls whether a small image specific to each combination is displayed in the list.
    - **Effect of changing this setting:**
      - *When enabled (YES):* If you have uploaded specific images for each product combination, they will appear next to their respective combination in the list.
      - *When disabled (NO):* Only the combination name, reference, and price will be shown, without an image.
    - **Recommended value:** YES, if you have unique images for combinations. This significantly helps customers visualize the exact product they are selecting.
    - **Merchant scenario / example:** For clothing, showing a red shirt image for the “Red - Large” combination is much clearer than just text.
  - **Show combination reference:**

    - **What this setting does:** Determines if the internal reference number for each combination is displayed.
    - **Effect of changing this setting:**
      - *When enabled (YES):* The combination’s reference (e.g., SKU) will be visible in the list.
      - *When disabled (NO):* The reference number will be hidden.
    - **Recommended value:** YES, especially for B2B stores or products where customers often order by reference.
    - **Merchant scenario / example:** A customer reordering a specific part might know it by its reference number, making it easier to find.
  - **Show combination quantity input:**

    - **What this setting does:** Allows customers to specify the quantity for each combination directly within the list, rather than just adding one at a time.
    - **Effect of changing this setting:**
      - *When enabled (YES):* A quantity input field (e.g., a number box) will appear next to each combination, allowing customers to enter a desired quantity before clicking “Add to Cart.”
      - *When disabled (NO):* The “Add to Cart” button will typically add one unit of the combination to the cart.
    - **Recommended value:** YES, for most stores, as it improves efficiency for customers buying multiple units of the same combination.
    - **Merchant scenario / example:** A customer buying 5 units of “Blue - Medium” and 3 units of “Green - Large” can do so quickly from the list.
  - **Show combination price:**

    - **What this setting does:** Controls whether the price of each individual combination is displayed in the list.
    - **Effect of changing this setting:**
      - *When enabled (YES):* The price for each specific combination will be shown.
      - *When disabled (NO):* The price will be hidden, and customers might only see the main product price or need to infer it.
    - **Recommended value:** YES. Transparency in pricing is crucial for customer trust and decision-making.
    - **Merchant scenario / example:** If different sizes or colors have different prices, showing the exact price for each combination is essential.
  - **Show combination availability:**

    - **What this setting does:** Displays the stock status (e.g., “In Stock,” “Out of Stock,” “Last items!”) for each combination.
    - **Effect of changing this setting:**
      - *When enabled (YES):* Customers will see the availability status for each combination, helping them make informed purchasing decisions.
      - *When disabled (NO):* Stock status will not be shown in the list.
    - **Recommended value:** YES. This prevents customers from adding out-of-stock items to their cart, reducing frustration and abandoned carts.
    - **Merchant scenario / example:** A customer can immediately see that the “Red - Large” shirt is out of stock and choose “Blue - Large” instead.
  - **Show combination description:**

    - **What this setting does:** If you have specific descriptions for each combination, this setting controls their display.
    - **Effect of changing this setting:**
      - *When enabled (YES):* Any unique description associated with a combination will be shown in the list.
      - *When disabled (NO):* Combination-specific descriptions will be hidden.
    - **Recommended value:** YES, if your combinations have distinct descriptions that add value to the customer’s decision.
    - **Merchant scenario / example:** For a customizable product, a combination description might detail the specific materials used for that variant.
  - **Add to cart button text:**

    - **What this setting does:** Allows you to customize the text displayed on the “Add to Cart” button for each combination.
    - **Effect of changing this setting:**
      - *When changed:* The button text will update to your custom phrase.
      - *When left empty:* The default “Add to Cart” text (or your theme’s default) will be used.
    - **Recommended value:** “Add to Cart” or “Buy Now” for clarity. Keep it concise.
    - **Merchant scenario / example:** You might change it to “Select & Buy” if you want to emphasize selection before purchase.
  - **Display combinations as a table:**

    - **What this setting does:** Switches the visual presentation of the combinations from a simple list to a structured HTML table.
    - **Effect of changing this setting:**
      - *When enabled (YES):* Combinations will be presented in a table format with columns for image, name, reference, price, quantity, and add to cart. This is often more compact and organized for many combinations.
      - *When disabled (NO):* Combinations will be displayed as a less structured list, typically one combination per line.
    - **Recommended value:** YES, for most cases, as a table provides better readability and alignment, especially with many options.
    - **Merchant scenario / example:** If you have 20+ combinations, a table makes it much easier to scan and compare.
  - **Display combinations as a tab:**

    - **What this setting does:** This setting is likely a legacy or a specific implementation detail. Given the `Hook to display the combinations list` setting, this might be redundant or refer to a specific template.
    - **Effect of changing this setting:**
      - *When enabled (YES):* Might force the combinations list into a tab-like structure, potentially overriding the chosen hook if that hook doesn’t naturally create a tab.
      - *When disabled (NO):* The display will follow the chosen hook more directly.
    - **Recommended value:** Generally NO, unless you specifically want a tab and your chosen hook doesn’t provide it. Rely on the “Hook to display the combinations list” setting for placement.
    - **Merchant scenario / example:** If your theme doesn’t automatically create tabs for `displayProductExtraContent`, enabling this might force a tab-like appearance.

#### 2.1.1 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Display combinations list on product page | YES | Master switch to enable/disable the module’s front-office display. |
| Module Configuration | Hook to display the combinations list | `displayProductButtons` or `displayProductExtraContent` | Determines the exact position of the list on the product page. |
| Module Configuration | Show combination image | YES (if images exist) | Displays unique images for each combination. |
| Module Configuration | Show combination reference | YES | Shows the SKU/reference number for each combination. |
| Module Configuration | Show combination quantity input | YES | Allows customers to enter quantities for each combination. |
| Module Configuration | Show combination price | YES | Displays the specific price for each combination. |
| Module Configuration | Show combination availability | YES | Shows stock status (e.g., “In Stock”) for each combination. |
| Module Configuration | Show combination description | YES (if descriptions exist) | Displays unique descriptions for each combination. |
| Module Configuration | Add to cart button text | “Add to Cart” | Customizes the text on the ‘Add to Cart’ buttons. |
| Module Configuration | Display combinations as a table | YES | Presents combinations in a structured table format for better readability. |
| Module Configuration | Display combinations as a tab | NO | (Likely legacy/specific) Controls tab-like display; prefer hook setting. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The combinations list isn’t showing up on my product page.**
**A1:**

- First, check if “Display combinations list on product page” is set to YES in the module configuration.
- Next, verify the “Hook to display the combinations list” setting. Some themes might not render all standard PrestaShop hooks in the same way. Try switching to a different hook (e.g., `displayProductButtons`, `displayProductExtraContent`, `displayFooterProduct`) to see if it appears.
- Ensure the product you are viewing actually has combinations defined.
- Clear your PrestaShop cache (Advanced Parameters > Performance > Clear cache).

**Q2: My combination images aren’t appearing in the list.**
**A2:**

- Make sure “Show combination image” is enabled in the module settings.
- Crucially, you must have uploaded specific images for each combination in your PrestaShop product editor (Product > Combinations tab > Edit each combination > Add image). If no specific image is assigned to a combination, it won’t appear.

**Q3: The list looks messy or doesn’t fit my theme’s design.**
**A3:**

- Try enabling “Display combinations as a table” if it’s not already. This often provides a more structured and visually appealing layout.
- The module uses its own CSS. Your theme’s CSS might be overriding or conflicting with it. You might need a web developer to adjust the module’s CSS (`mycombtabfree.css`) or add custom CSS to your theme to style it to your liking.
- Experiment with different hooks. Some hooks might have better default styling from your theme.

**Q4: Can I translate the “Add to Cart” button text into other languages?**
**A4:** Yes. Go to **International > Translations** in your PrestaShop Back Office. Select “Installed modules translations,” choose your theme, and then select “Combinations List Free” from the module dropdown. You can then translate the button text and any other module-specific phrases.

**Q5: Why are some combinations showing “Out of Stock” even though I have stock?**
**A5:**

- Check your product’s stock settings in the PrestaShop product editor. Ensure that the specific combination has available quantity.
- Verify your global stock management settings (Shop Parameters > Product Settings > Products Stock).
- Clear your PrestaShop cache after making any stock adjustments.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Combinations List Free” module (`mycombtabfree`) is a standard PrestaShop module designed to enhance the front-office product page. It primarily operates by hooking into various display points on the product page to inject its custom HTML structure for product combinations. The module follows a basic MVC-like pattern within the PrestaShop module framework, using a main module class for configuration and hook registration, and Smarty templates for rendering the front-office output. It leverages existing PrestaShop core functionalities for retrieving product and combination data.

### 4.2 Controllers (`controllers/`)

This module does not contain any custom Front-Office or Back-Office Admin Controllers. All configuration is handled via the `getContent()` method of the main module class, and front-office rendering is done directly through hooks.

### 4.3 Core Classes & Models (`classes/`)

This module does not contain any custom classes or `ObjectModel` definitions in the `classes/` directory. It relies entirely on PrestaShop’s core `Product` and `Combination` classes to retrieve and display data.

### 4.4 JavaScript Assets (`views/js/`)

- **`mycombtabfree/js/atc.js`**
  - **Scope:** Front-office.
  - **Purpose:** This script is responsible for handling the “Add to Cart” functionality for the combinations displayed by the module. It likely intercepts click events on the custom “Add to Cart” buttons generated by the module.
  - **Functionality:**
    - Binds event listeners to the “Add to Cart” buttons within the combinations list/table.
    - When a button is clicked, it gathers the `id_product`, `id_product_attribute` (combination ID), and potentially the quantity from the associated input field.
    - It then makes an AJAX request to PrestaShop’s core `cart` controller (or a similar endpoint) to add the selected combination to the cart.
    - It might also update the cart block, display notifications (success/error), or handle other UI feedback after the AJAX call.
    - It likely uses jQuery or PrestaShop’s native `prestashop.on` events for dynamic updates.

### 4.5 CSS Stylesheets (`views/css/`)

- **`mycombtabfree/css/admin.css`**

  - **Scope:** Back-office admin form styling.
  - **Purpose:** Contains styles specifically for the module’s configuration page in the PrestaShop Back Office. This might include styling for form elements, alerts, or layout adjustments to make the configuration interface user-friendly.
  - **Key Selectors:** Likely targets elements within the module’s `getContent()` output, such as `.panel`, `.form-group`, `.alert`, etc., to ensure consistent admin UI.
- **`mycombtabfree/css/mycombtabfree.css`**

  - **Scope:** Front-office customer styling.
  - **Purpose:** Provides the core visual styling for the combinations list/table displayed on the product page. This includes layout, typography, colors, and responsiveness.
  - **Key Selectors:**
    - `.mycombtabfree-container`: Main wrapper for the combinations list.
    - `.mycombtabfree-table`: Styles for the `<table>` element when “Display combinations as a table” is enabled.
    - `.mycombtabfree-row`, `.mycombtabfree-cell`: Styles for table rows and cells.
    - `.mycombtabfree-image`, `.mycombtabfree-name`, `.mycombtabfree-reference`, `.mycombtabfree-price`, `.mycombtabfree-qty`, `.mycombtabfree-atc`: Specific styles for each piece of combination data.
    - Media queries for responsive adjustments on smaller screens.
  - **Developer Override:** Developers can override these styles in their custom theme’s CSS files by using more specific selectors or by modifying this file directly (though the latter is not recommended for update-friendliness).

### 4.6 Smarty Template Structure (`views/templates/`)

- **`mycombtabfree/views/templates/admin/configure.tpl`**

  - **Scope:** Admin configuration panel.
  - **Purpose:** Renders the HTML form for the module’s configuration settings in the PrestaShop Back Office. This template is loaded by the `getContent()` method of the main module class.
  - **Content:** Contains form fields (checkboxes, text inputs, select dropdowns) corresponding to the settings described in Section 4.1.
- **`mycombtabfree/views/templates/admin/pro-upsell.tpl`**

  - **Scope:** Admin configuration panel.
  - **Purpose:** Displays promotional content or an upsell banner for a “Pro” version of the module within the Back Office configuration. This is a common practice for free modules.
- **`mycombtabfree/views/templates/hook/pro-banner.tpl`**

  - **Scope:** Front-office hook.
  - **Purpose:** Renders a promotional banner for the “Pro” version of the module, likely displayed in a less intrusive front-office hook (e.g., `displayFooter` or `displayLeftColumn`).
- **`mycombtabfree/views/templates/hook/tab.tpl`**

  - **Scope:** Front-office hook.
  - **Purpose:** This template is likely used when the “Display combinations as a tab” setting is enabled, or when the module is hooked into a position that naturally creates a tab (e.g., `displayProductExtraContent`). It would contain the structure for a product tab, within which the actual combinations list/table would be rendered.
- **`mycombtabfree/views/templates/hook/table.tpl`**

  - **Scope:** Front-office hook.
  - **Purpose:** This is the primary template responsible for rendering the actual list or table of product combinations on the front office. It iterates through the available combinations for a given product and displays each one according to the module’s configuration settings (e.g., showing image, reference, price, quantity input, add to cart button).
  - **Logic:** Contains Smarty loops (`{foreach}`) to iterate over `$combinations` array, conditional statements (`{if}`) to display elements based on module settings, and variables like `$combination.id_product_attribute`, `$combination.name`, `$combination.price`, etc.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create any custom SQL tables.
  - It stores its configuration settings in PrestaShop’s `ps_configuration` table. The configuration keys would typically follow a pattern like `MYCOMBTABFREE_SETTING_NAME`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Used to register CSS (`mycombtabfree.css`) and JavaScript (`atc.js`) assets for the front-office. |
| `displayProductButtons` | Near the “Add to Cart” button on the product page. | A common hook for displaying the combinations list directly below product details. |
| `displayProductExtraContent` | Within the product tabs area on the product page. | Allows the combinations list to appear in its own dedicated tab. |
| `displayFooterProduct` | At the bottom of the product page content. | Another possible location for the combinations list, often less prominent. |
| `actionFrontControllerSetMedia` | Before the front controller renders its output. | Used to add module-specific CSS and JS files to the page. |
| `moduleRoutes` | During URL rewriting initialization. | (Not explicitly used by this module, but a common hook for modules with custom URLs). |

## 5. Official Support & Updates

For official updates, bug fixes, and dedicated developer support for the “Combinations List Free” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Ensure you download the latest version compatible with your PrestaShop installation from your order history.
