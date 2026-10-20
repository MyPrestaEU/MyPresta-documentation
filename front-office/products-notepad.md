---
title: "Products Notepad - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Products Notepad PrestaShop module by MyPresta.eu."
sidebar:
  label: "Products Notepad - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Products Notepad Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/products-notepad.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/products-notepad/)
>
> ---


# Products Notepad

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for general PrestaShop operation. No specific additional extensions are needed for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Products Notepad” module in the Module Manager. This will take you to the main configuration screen.

#### General Settings

- **What this setting does:** This section controls the core behavior and display of the Products Notepad module on your storefront.

  - **Remember products in notepad:**

    - **What this setting does:** Determines whether the products a customer adds to their notepad are remembered across different browsing sessions or if the notepad is cleared when they close their browser.
    - **Effect of changing this setting:**
      - *When enabled (YES):* Products added to the notepad will persist even if the customer leaves your site and returns later (e.g., the next day). This uses browser cookies to store the notepad contents.
      - *When disabled (NO):* The notepad will be cleared when the customer closes their browser or clears their cookies. Each new session will start with an empty notepad.
    - **Recommended value:** **YES**. This provides a much better customer experience, as it allows customers to build a list over time without losing their progress.
    - **Merchant scenario / example:** A customer adds several items to their notepad on Monday. If “Remember products” is YES, they can return on Wednesday and find their list intact. If NO, the list would be empty.
  - **Limit number of products in notepad:**

    - **What this setting does:** Allows you to set a maximum number of products a customer can save in their notepad.
    - **Effect of changing this setting:**
      - *When enabled (YES):* The notepad will only allow a specified number of products. Once the limit is reached, customers won’t be able to add more products until they remove existing ones.
      - *When disabled (NO):* Customers can add an unlimited number of products to their notepad.
    - **Recommended value:** **NO** (unless you have a specific reason to limit it, like performance concerns with extremely long lists). Allowing unlimited items gives customers maximum flexibility.
    - **Merchant scenario / example:** If you enable this and set the limit to 10, a customer who tries to add an 11th product will receive a message indicating the notepad is full.
  - **Limit value:** (Only appears if “Limit number of products in notepad” is set to YES)

    - **What this setting does:** Specifies the exact maximum number of products allowed in the notepad.
    - **Effect of changing this setting:** Sets the numerical cap for the notepad.
    - **Recommended value:** If you choose to limit, a reasonable number like **20-50** is often sufficient, balancing customer flexibility with potential performance.
    - **Merchant scenario / example:** If “Limit number of products” is YES and “Limit value” is 25, customers can save up to 25 products.

#### Display Settings

- **What this setting does:** This section controls where the Products Notepad block appears on your store’s front office.

  - **Display in left column:**

    - **What this setting does:** Controls whether the notepad summary block is shown in the left column of your store.
    - **Effect of changing this setting:**
      - *When enabled (YES):* The notepad block will appear in the left column on pages that have a left column (e.g., category pages, product pages, CMS pages).
      - *When disabled (NO):* The notepad block will not be shown in the left column.
    - **Recommended value:** **YES** (or right column), as columns are a common place for such utility blocks.
    - **Merchant scenario / example:** A customer browsing a category page will see their notepad summary in the left sidebar, making it easily accessible.
  - **Display in right column:**

    - **What this setting does:** Controls whether the notepad summary block is shown in the right column of your store.
    - **Effect of changing this setting:**
      - *When enabled (YES):* The notepad block will appear in the right column on pages that have a right column.
      - *When disabled (NO):* The notepad block will not be shown in the right column.
    - **Recommended value:** **YES** (or left column). Choose one or both based on your theme’s layout and other modules you have.
    - **Merchant scenario / example:** If your theme uses the right column for promotions, you might place the notepad there to keep the left column clear for navigation.
  - **Display in footer:**

    - **What this setting does:** Controls whether the notepad summary block is shown in the footer section of your store.
    - **Effect of changing this setting:**
      - *When enabled (YES):* The notepad block will appear at the bottom of every page, typically as part of the general footer content.
      - *When disabled (NO):* The notepad block will not be shown in the footer.
    - **Recommended value:** **NO** (unless your theme has a very prominent footer section for utility blocks). Columns are generally more visible for this type of feature.
    - **Merchant scenario / example:** If your footer is already crowded with links and legal information, adding the notepad there might make it less noticeable.
  - **Display in header:**

    - **What this setting does:** Controls whether the notepad summary block is shown in the header section of your store.
    - **Effect of changing this setting:**
      - *When enabled (YES):* The notepad block will appear at the top of every page, often near the cart or account links.
      - *When disabled (NO):* The notepad block will not be shown in the header.
    - **Recommended value:** **NO** (unless your theme has ample space and a specific design for this). Headers are often reserved for critical navigation and cart.
    - **Merchant scenario / example:** A compact icon in the header could work, but a full block might clutter the header.
  - **Display on product page:**

    - **What this setting does:** Controls whether the “Add to Notepad” button and potentially a small notepad summary are displayed directly on individual product pages.
    - **Effect of changing this setting:**
      - *When enabled (YES):* Customers will see the “Add to Notepad” button on every product page, making it easy to save items while browsing.
      - *When disabled (NO):* The “Add to Notepad” button will not appear on product pages, making the feature less accessible.
    - **Recommended value:** **YES**. This is a crucial placement for the feature to be effective.
    - **Merchant scenario / example:** A customer viewing a product can immediately add it to their notepad for later comparison with other products.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Remember products in notepad | YES | Keeps notepad items saved across sessions for better UX. |
| Module Configuration | Limit number of products in notepad | NO | Allows unlimited products in notepad, maximizing customer choice. |
| Module Configuration | Limit value | (N/A if limit is NO) | Sets the maximum number of products if limiting is enabled. |
| Module Configuration | Display in left column | YES | Shows notepad summary in the left sidebar. |
| Module Configuration | Display in right column | YES | Shows notepad summary in the right sidebar. |
| Module Configuration | Display in footer | NO | Avoids cluttering the footer, less visible. |
| Module Configuration | Display in header | NO | Avoids cluttering the header, less visible. |
| Module Configuration | Display on product page | YES | Essential for customers to easily add products to notepad. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The notepad isn’t showing up on my store. What should I do?**
A1: First, check the module configuration in your Back Office (**Modules > Module Manager > Products Notepad > Configure**). Ensure that at least one display option (e.g., “Display in left column” or “Display on product page”) is set to YES. If it’s still not showing, try clearing your PrestaShop cache (**Advanced Parameters > Performance > Clear cache**). Sometimes, theme conflicts can also prevent modules from displaying; temporarily switch to the default PrestaShop theme to rule this out.

**Q2: Products are not being remembered in the notepad after a customer closes their browser.**
A2: Go to the module configuration page (**Modules > Module Manager > Products Notepad > Configure**) and make sure the “Remember products in notepad” setting is set to **YES**. This option uses browser cookies to store the notepad contents, so ensure customers haven’t disabled cookies in their browser.

**Q3: The “Add to Notepad” button looks strange or is not styled correctly on my product pages.**
A3: This is often a CSS conflict with your custom theme. The module provides its own basic styling, but your theme’s styles might be overriding it. You can either:
1. Contact your theme developer for assistance.
2. Use the PrestaShop Live Theme Editor (if available in your version) or browser developer tools (F12) to inspect the button and apply custom CSS overrides in your theme’s `custom.css` file.
3. Reach out to MyPresta.eu support for guidance.

**Q4: Can customers share their notepad with others?**
A4: No, this module is designed for individual customer use and does not include sharing functionality. It’s a personal browsing aid, not a collaborative wishlist.

**Q5: Will the notepad work with multi-language stores?**
A5: Yes, the module is designed to be compatible with PrestaShop’s multi-language features. Any text displayed by the module (like button labels or block titles) can be translated through the PrestaShop translation interface (**International > Translations > Installed modules translations**).

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The Products Notepad module is a standard PrestaShop module following an MVC-like pattern. It primarily uses front controllers for AJAX interactions and rendering, and Smarty templates for its front-office display. It relies on browser cookies for persistence if configured to remember products. The module’s main logic resides in `notepad.php` and its associated front controllers.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `controllers/front/ajaxload.php`
    - **Class name & parent class**: `NotepadAjaxloadModuleFrontController` extending `ModuleFrontController`.
    - **Responsibility**: This controller handles all AJAX requests related to the notepad functionality. It’s responsible for adding products to the notepad, removing them, and potentially updating the notepad display. It processes data sent via POST or GET and returns JSON responses to the front-end JavaScript.
  - `controllers/front/index.php`
    - **Class name & parent class**: `NotepadIndexModuleFrontController` extending `ModuleFrontController`.
    - **Responsibility**: This controller likely serves as a fallback or a dedicated page for the notepad if a full-page view is implemented. Given the module’s primary AJAX nature, this might be a less frequently used entry point, possibly redirecting or rendering a full notepad view.
- **Back-Office Admin Controllers**: None. All configuration is handled via the main module’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

No custom `ObjectModel` classes are defined in this module. Product data is likely stored directly in browser cookies or session variables, retrieved and processed by the module’s main class and front controllers.

### 4.4 JavaScript Assets (`views/js/`)

- `admin.js`
  - **Scope**: Back-office.
  - **Description**: This script likely handles interactions on the module’s configuration page in the PrestaShop Back Office. It might manage the visibility of settings (e.g., `notepad_limit_value` based on `notepad_limit`), form submissions, or validation.
- `jscolor.js`
  - **Scope**: Back-office (likely).
  - **Description**: A third-party JavaScript library for color pickers. If the module had color customization options for the notepad display, this script would provide the UI for selecting colors in the admin panel. (Based on the inventory, it’s present but might be a remnant or for future use if no color settings are currently exposed).
- `lib/searchTool/views/js/autocomplete.js`
  - **Scope**: Front-office (potentially Back-office if used for product selection).
  - **Description**: This script provides autocomplete functionality, likely for searching products. If the notepad had a feature to add products by searching, or if it’s part of a broader “search tool” library included with the module, this would handle the AJAX calls and display of search suggestions.
- `notepad.js`
  - **Scope**: Front-office.
  - **Description**: This is the core front-office JavaScript for the notepad functionality.
    - **Event listeners**: Binds click events to “Add to Notepad” buttons (e.g., on product pages, product listings), “Remove from Notepad” links/buttons within the notepad block, and potentially the notepad block header itself to toggle its visibility or navigate to a full view.
    - **AJAX calls**: Makes asynchronous requests to `controllers/front/ajaxload.php` to add, remove, or retrieve notepad contents.
    - **DOM manipulation**: Updates the notepad display block (e.g., product count, list of products), shows success/error messages, and dynamically renders product entries within the notepad.
    - **Cookie management**: Interacts with browser cookies to store and retrieve notepad product IDs if the “Remember products” option is enabled.

### 4.5 CSS Stylesheets (`views/css/`)

- `css/admincss.css`
  - **Scope**: Back-office admin form styling.
  - **Description**: Styles for the module’s configuration page in the PrestaShop Back Office, ensuring a consistent look and feel with the PrestaShop admin theme.
- `css/css.css`
  - **Scope**: Front-office customer styling.
  - **Description**: Contains the primary styles for the notepad display block, the “Add to Notepad” button, and any associated elements on the storefront.
  - **Key CSS class selectors**: Developers can inspect the generated HTML for classes like `.notepad-block`, `.add-to-notepad`, `.notepad-product-item` to override styles in their theme’s `custom.css` or `theme.css`.
- `lib/searchTool/views/css/autocomplete.css`
  - **Scope**: Front-office (or Back-office if search tool is used there).
  - **Description**: Styles for the autocomplete search results dropdown, if the `autocomplete.js` script is actively used for a product search feature within the module.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `extraleft.tpl`
    - **Hook**: Likely `displayLeftColumn` or similar.
    - **Purpose**: Renders the main notepad summary block that appears in the left column. This typically shows a title, the number of items, and a brief list or link to the full notepad.
  - `notepad.tpl`
    - **Hook**: This might be a general template included by other templates or directly hooked into `displayRightColumn`, `displayFooter`, or `displayHeader` depending on configuration. It likely contains the core structure for the notepad block.
- **Admin templates (`views/templates/admin/`)**: None explicitly listed, configuration is likely handled by `notepad.php` directly rendering form elements.
- **Front-office templates (`views/templates/front/`)**:
  - `views/addToCart.tpl`
    - **Purpose**: This template is rendered on product pages (and potentially product listings) to display the “Add to Notepad” button. It’s likely hooked into `displayProductButtons` or `displayProductActions`.
  - `views/selectedProducts.tpl`
    - **Purpose**: This template is used to display the detailed list of products within the notepad, either in a popup, a dedicated page, or within the expanded column block. It iterates over the products saved in the notepad and displays their image, name, price, and a “remove” option.
  - `lib/searchTool/views/scripts.tpl`
    - **Purpose**: This template likely includes the necessary JavaScript and CSS for the `searchTool` library, such as `autocomplete.js` and `autocomplete.css`, if the module utilizes a search feature. It would be hooked into `displayHeader` or `displayFooter` to load these assets.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: The module does not appear to create any custom SQL tables. Product IDs and related data for the notepad are managed client-side, primarily through browser cookies or session variables. Configuration settings are stored in `ps_configuration` (e.g., `NOTEPAD_REMEMBER`, `NOTEPAD_LIMIT`, `NOTEPAD_LIMIT_VALUE`).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | To load module’s CSS and JS assets (e.g., `notepad.js`, `css.css`) and potentially render a compact notepad summary if configured. |
| `displayLeftColumn` | In the left sidebar of pages that have one. | To display the main notepad summary block (`extraleft.tpl`). |
| `displayRightColumn` | In the right sidebar of pages that have one. | To display the main notepad summary block (`notepad.tpl` or similar). |
| `displayFooter` | In the footer section of every page. | To display the notepad summary block if configured, or to load deferred JS. |
| `displayProductButtons` / `displayProductActions` (or similar product page hook) | On the product page, near the “Add to Cart” button. | To render the “Add to Notepad” button (`views/addToCart.tpl`). |
| `actionFrontControllerSetMedia` | Before the front controller renders its output. | To register module’s CSS and JS files for optimal loading. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the Products Notepad module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
