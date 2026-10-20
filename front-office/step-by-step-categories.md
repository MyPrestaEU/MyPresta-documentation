---
title: "Step by step - categories - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Step by step - categories PrestaShop module by MyPresta.eu."
sidebar:
  label: "Step by step - categories - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Step by step - categories Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/step-by-step-categories.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/step-by-step-categories/)
>
> ---


# Step by step - categories

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server requirements beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” will take you to the main configuration screen for “Step by step - categories.” This is where you control how the module behaves and appears on your storefront.

| Setting / Option | What this setting does | Effect of changing this setting | Recommended value | Merchant scenario / example |
| --- | --- | --- | --- | --- |
| **Display block in header** | Controls whether the step-by-step category navigation appears in your store’s header section. | *When enabled:* The category dropdowns will be visible at the top of your website, often near the logo or main navigation. This provides immediate access to category filtering. *When disabled:* The block will not appear in the header. | **YES** (if you want prominent navigation) | You want customers to easily find products from any page, so placing it in the header makes it always accessible. |
| **Display block in left column** | Controls whether the step-by-step category navigation appears in your store’s left sidebar. | *When enabled:* The category dropdowns will be visible in the left column of your website (if your theme supports a left column). This is a traditional placement for category filters. *When disabled:* The block will not appear in the left column. | **YES** (if your theme has a left column and you want sidebar navigation) | Your theme has a left sidebar, and you prefer to keep navigation elements organized there, similar to a standard category tree. |
| **Display block in right column** | Controls whether the step-by-step category navigation appears in your store’s right sidebar. | *When enabled:* The category dropdowns will be visible in the right column of your website (if your theme supports a right column). *When disabled:* The block will not appear in the right column. | **NO** (unless your theme specifically uses a right column for navigation) | Your theme uses the right column for supplementary information, and you want to place the category navigation there instead of the left. |
| **Display block in footer** | Controls whether the step-by-step category navigation appears in your store’s footer section. | *When enabled:* The category dropdowns will be visible at the bottom of your website. This is less common for primary navigation but can be useful for secondary access. *When disabled:* The block will not appear in the footer. | **NO** (unless for specific design reasons) | You have a very minimalist header and columns, and you want to offer category navigation in the footer as an alternative for users who scroll down. |
| **Display block on product page** | Controls whether the step-by-step category navigation appears on individual product pages. | *When enabled:* The category dropdowns will be visible on product detail pages. This can help customers explore other categories or related products. *When disabled:* The block will not appear on product pages. | **NO** (unless you have a specific need for it there) | You want to encourage customers viewing a product to easily jump to other categories without leaving the product page, perhaps to compare items. |
| **Show “Go” button** | Determines if a “Go” or “Search” button is displayed next to the last category dropdown. | *When enabled:* A button will appear. Customers must click this button to be redirected to the selected category page. *When disabled:* Customers are automatically redirected to the selected category page as soon as they make the final selection in the last dropdown. | **YES** (for more control) | You want customers to confirm their category selection before being redirected, giving them a chance to review their choice. |
| **Number of dropdowns** | Sets the maximum number of category levels (depth) that will be displayed as dropdowns. | *When set to 1:* Only the top-level categories will appear in one dropdown. *When set to 3:* Up to three levels of categories (e.g., Main Category > Subcategory 1 > Subcategory 2) will be displayed in separate dropdowns. | **3** (or based on your category depth) | Your store has categories nested up to 3 or 4 levels deep, and you want customers to be able to drill down efficiently. |
| **Root category** | Specifies the starting point for the category navigation. Only categories within this root will be displayed. | *When set to “Home”:* All categories starting from the very top of your catalog will be available. *When set to “Electronics”:* Only categories under “Electronics” (e.g., “Laptops,” “Smartphones”) will be shown in the dropdowns. | **Home** (unless you want to restrict navigation) | You only want to offer step-by-step navigation for a specific part of your catalog, like “Apparel,” and exclude other sections like “Home & Garden.” |

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Display block in header | YES | Shows category dropdowns in the store header for prominent navigation. |
| Module Configuration | Display block in left column | YES | Shows category dropdowns in the left sidebar for traditional navigation. |
| Module Configuration | Display block in right column | NO | Shows category dropdowns in the right sidebar. |
| Module Configuration | Display block in footer | NO | Shows category dropdowns in the store footer. |
| Module Configuration | Display block on product page | NO | Shows category dropdowns on product detail pages. |
| Module Configuration | Show “Go” button | YES | Requires customers to click a button to navigate to the selected category. |
| Module Configuration | Number of dropdowns | 3 | Sets the maximum depth of category levels displayed. |
| Module Configuration | Root category | Home | Defines the starting point for category navigation. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The module is installed, but I don’t see the dropdowns on my store.**
A1:

- **Check Configuration:** Go to **Modules > Module Manager > Step by step - categories > Configure**. Ensure that at least one “Display block in…” option (e.g., “Display block in header,” “Display block in left column”) is set to **YES**.
- **Clear Cache:** PrestaShop often caches content. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions).
- **Theme Compatibility:** Some highly customized themes might require minor adjustments. If clearing cache doesn’t help, try temporarily switching to the default PrestaShop theme to see if the module appears. If it does, your theme might be overriding the standard hook positions.

**Q2: The dropdowns appear, but they don’t update when I select a category.**
A2:

- **AJAX Issues:** This usually indicates a JavaScript error. Open your browser’s developer console (F12) and check for any errors in the “Console” tab.
- **Conflicting JavaScript:** Another module or your theme’s JavaScript might be interfering. Try disabling other front-office modules one by one to identify conflicts.
- **Module Files:** Ensure all module files were uploaded correctly and are not corrupted. Re-uploading the module might resolve this.

**Q3: How do I change the styling (colors, fonts, size) of the dropdowns?**
A3:

- The module uses standard CSS. You’ll need basic CSS knowledge or a webmaster.
- The module’s CSS files (e.g., `sbs-block.css`, `sbs-header.css`) define the default styles.
- **Best Practice:** Do NOT modify the module’s CSS files directly, as your changes will be lost during updates. Instead, use your theme’s custom CSS file (often found in `themes/yourtheme/assets/css/custom.css` or similar) to override the module’s styles. Use your browser’s inspector (F12) to identify the CSS classes used by the dropdowns.

**Q4: My categories are very deep, but I only see a few dropdowns.**
A4:

- **“Number of dropdowns” Setting:** Go to **Modules > Module Manager > Step by step - categories > Configure** and adjust the “Number of dropdowns” setting. Increase this value to match the maximum depth of categories you want to display. Remember that displaying too many dropdowns might clutter the interface.

**Q5: The module is showing categories I don’t want to include in the step-by-step navigation.**
A5:

- **“Root category” Setting:** In the module’s configuration, use the “Root category” setting. Select a specific parent category from which you want the step-by-step navigation to begin. Only categories and subcategories under your chosen root will be displayed.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Step by step - categories” module is primarily a front-office feature leveraging PrestaShop’s module architecture. It uses a standard `Module` class for installation and configuration, and `ModuleFrontController` classes to handle AJAX requests for dynamic category loading. It does not introduce custom `ObjectModel` classes or database tables, relying on PrestaShop’s native `Category` object for data. The module heavily utilizes Smarty templates for rendering and JavaScript for interactive AJAX functionality.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:
  - `controllers/front/ajaxload.php`
    - Class name: `StepbystepAjaxloadModuleFrontController`
    - Parent class: `ModuleFrontController`
    - Responsibility: This controller is the core of the AJAX functionality. It responds to requests from the front-office JavaScript to fetch subcategories based on a parent category ID. It typically returns JSON data containing category names and IDs for populating subsequent dropdowns.
  - `controllers/front/index.php`
    - Class name: `StepbystepIndexModuleFrontController`
    - Parent class: `ModuleFrontController`
    - Responsibility: This controller likely serves as a default entry point or fallback for the module’s front-office routing, though its primary function might be minimal given the AJAX-driven nature. It might handle initial display logic or redirection if the module were to have a dedicated page.
  - `controllers/front/tree.php`
    - Class name: `StepbystepTreeModuleFrontController`
    - Parent class: `ModuleFrontController`
    - Responsibility: This controller might be responsible for rendering a full category tree structure, potentially for debugging or an alternative display method, though the module’s main feature is the dropdowns. It could also be used to generate the initial data for the first dropdown.

### 4.3 Core Classes & Models (`classes/`)

The module does not contain any custom classes in the `classes/` directory. It directly utilizes PrestaShop’s core `Category` class and other helper functions to retrieve category data.

### 4.4 JavaScript Assets (`views/js/`)

- `stepbystep/js/advajax.js`
  - Scope: Front-office
  - This is the primary JavaScript file responsible for the module’s interactive behavior.
  - It binds event listeners to the category dropdown `<select>` elements.
  - When a selection is made in a dropdown, it triggers an AJAX request (likely to `ajaxload.php`) to fetch the next level of subcategories.
  - It dynamically creates and populates subsequent dropdowns with the received data.
  - It handles the redirection to the final category page when a selection is made or the “Go” button is clicked.
  - It manages the visibility and state of the dropdowns based on user interaction and module configuration (e.g., “Number of dropdowns”).

### 4.5 CSS Stylesheets (`views/css/`)

- `stepbystep/css/sbs-block.css`
  - Scope: Front-office customer styling
  - Styles the general appearance of the step-by-step category block, including padding, margins, and overall layout when placed in columns or other block-like positions.
  - Key selectors: `.sbs-block`, `.sbs-category-select-wrapper`
- `stepbystep/css/sbs-header.css`
  - Scope: Front-office customer styling
  - Specifically styles the module when it is hooked into the `displayHeader` position, potentially adjusting for header layouts (e.g., inline display, specific widths).
  - Key selectors: `.sbs-header-container`
- `stepbystep/css/sbs-top.css`
  - Scope: Front-office customer styling
  - Likely styles the module when it is hooked into `displayTop` or similar top-of-page positions, similar to `sbs-header.css` but for different visual contexts.
  - Key selectors: `.sbs-top-container`
- `stepbystep/css.css`
  - Scope: Front-office customer styling
  - A general stylesheet that might contain common styles applicable across all placements or fallback styles.
  - Key selectors: `.sbs-select`, `.sbs-go-button`

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - `block.tpl`: This template is likely used when the module is hooked into `displayLeftColumn` or `displayRightColumn`. It renders the step-by-step dropdowns within a standard PrestaShop block structure.
  - `blockSbs.tpl`: This might be an alternative or a more generic block template, potentially used for other column hooks or specific custom placements.
  - `displaySearch.tpl`: This template might be intended for integration near a search bar or as part of a search-related hook, providing the dropdowns as a search refinement tool.
  - `header.tpl`: This template is used when the module is hooked into `displayHeader`. It renders the dropdowns within the header section of the store.
  - `top.tpl`: This template is used when the module is hooked into `displayTop`. Similar to `header.tpl`, but for the `displayTop` hook, which is often used for the main navigation bar.
- **Admin templates (`views/templates/admin/`)**: None identified. Configuration is handled directly in `getContent()`.
- **Front-office templates (`views/templates/front/`)**: None identified as standalone pages.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: The module does not create any custom SQL tables. It stores its configuration settings in PrestaShop’s `ps_configuration` table using keys like `STEPMYSTEP_HEADER`, `STEPMYSTEP_LEFT`, `STEPMYSTEP_RIGHT`, `STEPMYSTEP_FOOTER`, `STEPMYSTEP_PRODUCT`, `STEPMYSTEP_GO_BUTTON`, `STEPMYSTEP_DROPDOWNS`, `STEPMYSTEP_ROOT_CATEGORY`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Renders content within the `<head>` section of the HTML, or at the very top of the `<body>` before other content. | Injects CSS/JS assets and potentially the module’s HTML structure if configured for header display. |
| `displayLeftColumn` | Renders content in the left sidebar of the store. | Displays the step-by-step category dropdowns in the left column. |
| `displayRightColumn` | Renders content in the right sidebar of the store. | Displays the step-by-step category dropdowns in the right column. |
| `displayFooter` | Renders content in the footer section of the store. | Displays the step-by-step category dropdowns in the footer. |
| `displayProductAdditionalInfo` (or similar product page hook) | Renders content on the product page, often below the product description or in a specific block. | Displays the step-by-step category dropdowns on product pages. |
| `displayTop` | Renders content in the top section of the page, typically above or within the main navigation. | Displays the step-by-step category dropdowns in the top bar. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Step by step - categories” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have.
