---
title: "Block Search Pro - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Block Search Pro PrestaShop module by MyPresta.eu."
sidebar:
  label: "Block Search Pro - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Block Search Pro Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/block-search-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/block-search-pro/)
>
> ---


# Block Search Pro

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Block Search Pro)

This is the main configuration screen where you control how the Block Search Pro module behaves and appears on your storefront.

#### 2.1.1 General Settings

**1. Enable AJAX search**

- **What this setting does:** This controls whether search results appear instantly as the customer types (AJAX) or if they have to press Enter/click the search button to see results.
- **Effect of changing this setting:**
  - *When enabled (YES):* As customers type in the search bar, a dropdown list of matching products will appear in real-time below the search field. This provides immediate feedback and speeds up the search process.
  - *When disabled (NO):* Customers must type their full search query and then press Enter or click the search button to be redirected to the search results page.
- **Recommended value:** YES. This significantly improves the user experience by offering instant gratification and reducing the steps to find a product.
- **Merchant scenario / example:** A customer types “dress” and immediately sees suggestions like “Red Party Dress,” “Summer Maxi Dress,” and “Black Cocktail Dress” appear, allowing them to click directly to a product page without waiting.

**2. Instant search**

- **What this setting does:** Similar to AJAX search, this specifically refers to the “instant” display of search results on the search results page itself, updating as the user refines their query. (Note: In many modern PrestaShop versions, “AJAX search” often encompasses the instant dropdown, while “Instant search” might refer to the behavior on the actual search results page).
- **Effect of changing this setting:**
  - *When enabled (YES):* If a customer is on the search results page and modifies their search query in the search bar, the results on that page will update instantly without a full page reload.
  - *When disabled (NO):* The customer would need to submit the modified search query again for the results page to refresh.
- **Recommended value:** YES. This provides a more dynamic and responsive search experience.
- **Merchant scenario / example:** A customer searches for “shoes,” lands on the search results page, then types “red” into the search bar on that page. With instant search, the results immediately filter to show only red shoes.

**3. Allow to submit search with empty search keyword input**

- **What this setting does:** Determines if a customer can click the search button or press Enter without typing any keywords.
- **Effect of changing this setting:**
  - *When enabled (YES):* If a customer clicks search with an empty input, they will be taken to the general search results page, which might display all products or a default message depending on your theme. This can sometimes be used to browse all products.
  - *When disabled (NO):* The search button will be inactive or display an error message if the input field is empty, forcing the customer to type a keyword before searching.
- **Recommended value:** NO. Generally, it’s better to guide customers to input a query to avoid confusion or empty search results pages.
- **Merchant scenario / example:** If a customer accidentally clicks search without typing, disabling this prevents them from landing on a potentially confusing empty page.

**4. Minimum word length (in characters)**

- **What this setting does:** Sets the minimum number of characters a customer must type before the search function (including AJAX/instant search) starts looking for results.
- **Effect of changing this setting:**
  - *Set to 3:* Customers must type at least three characters (e.g., “red”) before any search suggestions appear or a search can be submitted.
  - *Set to 1:* Even a single character (e.g., “a”) will trigger the search.
- **Recommended value:** 3. This balances responsiveness with relevance. Too low (e.g., 1-2 characters) can generate too many irrelevant suggestions, while too high might frustrate users.
- **Merchant scenario / example:** If set to 3, typing “sh” won’t show results, but typing “sho” will start displaying suggestions for “shoes,” “shorts,” etc.

#### 2.1.2 Search Filtering Options

**5. Select categories**

- **What this setting does:** Allows you to restrict the search to specific product categories only. The module will only return results from the categories you select here.
- **Effect of changing this setting:**
  - *When specific categories are selected:* The search will only look for products within those chosen categories. Products in unselected categories will not appear in search results, even if they match the keyword.
  - *When no categories are selected:* The search will default to searching across all categories in your store.
- **Recommended value:** Select categories if you want to guide customers to specific product types, or leave empty if you want a broad search.
- **Merchant scenario / example:** If you sell both clothing and electronics, but you only want the search bar in the header to find clothing, you would select only your clothing categories here.

**6. Search in subcategories**

- **What this setting does:** This option works in conjunction with “Select categories.” It determines whether the search should also include products within the subcategories of the selected parent categories.
- **Effect of changing this setting:**
  - *When enabled (YES):* If you select “Electronics” as a category, the search will also look inside “Laptops,” “Smartphones,” and any other subcategories of “Electronics.”
  - *When disabled (NO):* The search will only look for products directly assigned to the selected parent categories, ignoring their subcategories.
- **Recommended value:** YES. Most merchants want searches to be comprehensive within a chosen category tree.
- **Merchant scenario / example:** If you select “Apparel” and enable “Search in subcategories,” a search for “shirt” will find shirts in “Men’s T-Shirts,” “Women’s Blouses,” etc.

**7. Manufacturers**

- **What this setting does:** Allows you to restrict the search to products from specific manufacturers only.
- **Effect of changing this setting:**
  - *When specific manufacturers are selected:* The search will only return products made by the chosen manufacturers. Products from unselected manufacturers will not appear.
  - *When no manufacturers are selected:* The search will default to searching across all manufacturers in your store.
- **Recommended value:** Select manufacturers if you want to offer a brand-specific search, or leave empty for a general search.
- **Merchant scenario / example:** If you have a dedicated search block for “Premium Brands,” you might select only high-end manufacturers here.

#### 2.1.3 Display Settings

**8. Search block size**

- **What this setting does:** Controls the visual width of the search input field in pixels.
- **Effect of changing this setting:**
  - *Set to 280px:* The search bar will be 280 pixels wide.
  - *Set to 100% (or leave empty for auto-detect):* The search bar will adapt to the available space, often filling its container.
- **Recommended value:** Leave empty for auto-detect or set to a percentage (e.g., 100%) to ensure responsiveness. If you need a fixed width for design reasons, specify a pixel value.
- **Merchant scenario / example:** If your theme has a very narrow header, you might need to adjust this to ensure the search bar fits without breaking the layout. For most modern themes, letting the theme handle the width is best.

#### 2.1.4 Other Settings

**9. MyPresta.eu Live Update Settings (mypresta\_updates, update\_, updatev\_)**

- **What this setting does:** These are internal settings related to MyPresta.eu’s module update system. They allow the module to check for and notify you about new versions.
- **Effect of changing this setting:** These are not user-configurable directly through the interface but are managed by the module itself. Ensuring your store has outbound internet access allows these checks to function.
- **Recommended value:** These are internal and should not be manually changed.
- **Merchant scenario / example:** You will receive a notification in your PrestaShop back office if a new version of Block Search Pro is available, ensuring you can keep your module up-to-date with the latest features and security fixes.

**10. PS\_LANG\_DEFAULT, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG**

- **What this setting does:** These are standard PrestaShop configuration variables related to the default language of your store and whether employees can change the language of forms in the back office. The module uses these to ensure it displays correctly in the active back office language.
- **Effect of changing this setting:** These are global PrestaShop settings and are not directly controlled by Block Search Pro. The module simply reads them to adapt its display.
- **Recommended value:** Managed by your general PrestaShop configuration.
- **Merchant scenario / example:** If your back office is set to French, the module’s configuration labels will appear in French (if translations are available).

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable AJAX search | YES | Shows instant product suggestions as customer types. |
| Module Configuration | Instant search | YES | Updates search results page instantly on query change. |
| Module Configuration | Allow to submit search with empty search keyword input | NO | Prevents searching with an empty input field. |
| Module Configuration | Minimum word length (in characters) | 3 | Minimum characters required to trigger search. |
| Module Configuration | Select categories | Leave empty (searches all) | Restricts search to chosen categories. |
| Module Configuration | Search in subcategories | YES | Includes subcategories when parent categories are selected. |
| Module Configuration | Manufacturers | Leave empty (searches all) | Restricts search to chosen manufacturers. |
| Module Configuration | Search block size | Leave empty (auto-detect) | Visual width of the search input field. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My search results are not showing products I know exist. What’s wrong?**
A1: Check your “Select categories” and “Manufacturers” settings in the module configuration. If you’ve restricted the search to certain categories or manufacturers, products outside those selections will not appear. Also, ensure your products are active and visible in the selected categories.

**Q2: The instant search (AJAX) is not working, or the dropdown suggestions don’t appear.**
A2:
\* **Enable AJAX search:** Make sure “Enable AJAX search” is set to YES in the module configuration.
\* **Minimum word length:** Check “Minimum word length.” If it’s set too high, suggestions won’t appear until enough characters are typed.
\* **Clear Cache:** Go to **Advanced Parameters > Performance** and clear your PrestaShop cache (Smarty cache, filesystem cache).
\* **Theme Conflicts:** Sometimes, custom themes or other modules can conflict with AJAX functionality. Temporarily disable other modules or switch to the default PrestaShop theme to diagnose.
\* **JavaScript Errors:** Open your browser’s developer console (F12) and check for any JavaScript errors. If you see errors, contact MyPresta.eu support.

**Q3: The search block looks strange or doesn’t fit my theme.**
A3:
\* **Search block size:** Adjust the “Search block size” setting in the module configuration. Try leaving it empty for auto-detection or setting it to a percentage (e.g., 100%).
\* **CSS Conflicts:** Your theme’s CSS might be overriding the module’s styles. This usually requires a webmaster to inspect the CSS.
\* **Hook Placement:** Ensure the module is hooked into an appropriate position (e.g., `displayTop`) that has enough space in your theme. You can manage module positions under **Design > Positions**.

**Q4: How do I translate the search block text (e.g., “Search our catalog”)?**
A4:
\* Go to **International > Translations** in your PrestaShop back office.
\* Select “Installed modules translations,” choose your theme, and then select your language.
\* Find the “Block Search Pro” module in the list and you can edit the text strings there.

**Q5: I want to place the search block in a different location on my site.**
A5:
\* Navigate to **Design > Positions** (or **Modules > Positions** in older PS versions).
\* Find the “Block Search Pro” module in the list of modules.
\* You can “transplant” (hook) the module to different available hooks like `displayHeader`, `displayTop`, `displayLeftColumn`, `displayRightColumn`, or `displayNav`. Drag and drop to change the order within a hook.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview of the Block Search Pro module for developers and webmasters.

### 4.1 Architecture Overview

The Block Search Pro module extends PrestaShop’s core search functionality by overriding the `Search` class, allowing it to inject custom filtering logic (categories, manufacturers) into the search query. It leverages standard PrestaShop MVC patterns for its front-office display (hooks, templates) and back-office configuration (`getContent()` method in the main module file). AJAX functionality is handled via a dedicated JavaScript file that interacts with the core PrestaShop search mechanism.

### 4.2 Controllers (`controllers/`)

This module does not introduce custom Front-Office or Back-Office Admin Controllers. Its front-office functionality is primarily handled by the overridden `Search` class and its display via module hooks. The back-office configuration is managed directly within the `blocksearchpro.php` module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

- **`blocksearchpro/override/classes/index.php`**:

  - This is a standard empty `index.php` file, typically placed in directories to prevent directory listing. It has no functional impact on the module’s logic.
- **`blocksearchpro/override/classes/Search.php`**:

  - **Class name**: `Search` (overrides the core `Search` class)
  - **Parent class**: `SearchCore`
  - **Responsibility**: This is the most critical file. It overrides the default PrestaShop `Search` class, specifically modifying the `find()` method (or similar search-related methods) to incorporate the module’s custom filtering logic.
    - It reads configuration values (`bsp_cat_exc`, `bsp_subcat`, `bsp_cat`, `bsp_man`) from `ps_configuration`.
    - It modifies the SQL query used for product search to include `WHERE` clauses that filter by selected categories and/or manufacturers.
    - It ensures that the search respects the “Search in subcategories” setting when category filters are applied.
    - This override is what allows the module to inject its filtering capabilities directly into PrestaShop’s core search mechanism.

### 4.4 JavaScript Assets (`views/js/`)

- **`blocksearchpro/blocksearchpro.js`**:
  - **Scope**: Front-office.
  - **Responsibility**: This script enhances the user experience for the search block.
    - It likely binds event listeners to the search input field (e.g., `keyup`, `focus`, `blur`).
    - It handles the AJAX requests for instant search suggestions, sending the current input value to PrestaShop’s core search AJAX endpoint.
    - It processes the JSON response from the AJAX call and dynamically populates the dropdown list of product suggestions below the search bar.
    - It manages the display and hiding of the suggestion list, keyboard navigation within suggestions, and click events on suggestions to redirect to product pages.
    - It may also handle the “Allow to submit search with empty search keyword input” logic on the client side.

### 4.5 CSS Stylesheets (`views/css/`)

- **`blocksearchpro/blocksearchpro.css`**:
  - **Scope**: Front-office customer styling.
  - **Main UI components and containers it styles**:
    - The search input field itself (`#search_query_top`, `.search_query`).
    - The search button (`#search_button`, `.button-search`).
    - The container for AJAX search suggestions (`.ac_results`, `.block_search_pro_results`).
    - Individual suggestion items within the dropdown.
    - Ensures responsiveness for various screen sizes.
  - **Key CSS class selectors developers can override**:
    - `.block_search_pro` (main container)
    - `.search_query` (input field)
    - `.button-search` (submit button)
    - `.ac_results` (AJAX results container)
    - `.ac_odd`, `.ac_even`, `.ac_over` (styling for suggestion items and hover states)
    - Developers can override these styles in their theme’s `custom.css` or by creating a child theme.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - **`blocksearchpro/blocksearchpro-top.tpl`**:
    - **Hook**: `displayTop`, `displayNav` (and potentially `displayHeader` depending on theme).
    - **Purpose**: Renders the search input field and button, typically for the main header search bar. It includes the necessary HTML structure for the search form and the container for AJAX results.
  - **`blocksearchpro/blocksearchpro.tpl`**:
    - **Hook**: `displayLeftColumn`, `displayRightColumn`.
    - **Purpose**: Renders a search block for side columns. This template might have a slightly different layout or styling compared to the top search bar, optimized for narrower column spaces. It also includes the search form and AJAX result container.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create custom SQL tables.
  - It stores its configuration settings in the standard PrestaShop `ps_configuration` table.
  - Configuration keys used: `mypresta_updates`, `update_`, `updatev_`, `PS_SEARCH_AJAX`, `bsp_cat_exc`, `PS_INSTANT_SEARCH`, `bsp_empty`, `PS_SEARCH_MINWORDLEN`, `bsp_subcat`, `bsp_cat`, `bsp_man`, `bsp_size`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Injects CSS (`blocksearchpro.css`) and JavaScript (`blocksearchpro.js`) assets for front-office functionality. |
| `displayTop` | Typically in the main header area of the store. | Renders the search block using `blocksearchpro-top.tpl`. |
| `displayNav` | Often in the very top navigation bar (above `displayTop`). | Renders the search block using `blocksearchpro-top.tpl`. |
| `displayLeftColumn` | In the left sidebar of pages that have one. | Renders the search block using `blocksearchpro.tpl`. |
| `displayRightColumn` | In the right sidebar of pages that have one. | Renders the search block using `blocksearchpro.tpl`. |
| `actionValidateOrder` | After an order has been successfully validated. | (Not directly used by this module for its core search functionality, but a common hook for other modules. No specific action here for Block Search Pro.) |

## 5. Official Support & Updates

For official updates, technical support, and further assistance with the Block Search Pro module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is ready to help with any issues or questions you may have.
