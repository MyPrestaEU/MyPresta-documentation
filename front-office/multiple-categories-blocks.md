---
title: "Multiple Categories Blocks - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Multiple Categories Blocks PrestaShop module by MyPresta.eu."
sidebar:
  label: "Multiple Categories Blocks - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Multiple Categories Blocks Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/multiple-categories-blocks.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/multiple-categories-blocks/)
>
> ---


# Multiple Categories Blocks

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Multiple Categories Blocks)

This is the main configuration screen where you will create and manage all your custom category blocks.

Upon entering the configuration page, you will see a list of existing category blocks (if any) and options to add new ones.

#### **Adding / Editing a Category Block**

When you click “Add new block” or edit an existing one, you’ll be presented with the following settings:

- **Block Name:**

  - **What this setting does:** This is an internal name for your reference in the Back Office. It helps you identify different blocks.
  - **Effect of changing this setting:** Only affects how you see the block in the admin panel. It is not visible to customers.
  - **Recommended value:** A descriptive name (e.g., “Homepage Electronics Categories”, “Left Column Apparel”).
  - **Merchant scenario / example:** If you have a block for “Men’s Fashion” in the left column, name it “Left Column - Men’s Fashion”.
- **Display Block Title:**

  - **What this setting does:** Determines if a title (e.g., “Categories”) is displayed above the category list in the front office.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* A title will appear above the category block. You can define this title in the “Block Title” field.
    - *When disabled (No):* No title will be displayed, only the category list.
  - **Recommended value:** “Yes” for most blocks, as it provides context to the customer.
  - **Merchant scenario / example:** If you want your block to simply blend into the design without an explicit title, set it to “No”.
- **Block Title:** (Appears only if “Display Block Title” is Yes)

  - **What this setting does:** The actual text that will be displayed as the title of the block in the front office. This is multi-language.
  - **Effect of changing this setting:** Changes the visible title for customers.
  - **Recommended value:** A clear, concise title (e.g., “Shop by Category”, “Our Products”, “Departments”).
  - **Merchant scenario / example:** For a block showing only “Electronics” categories, you might set the title to “Electronics”.
- **Hook to display block:**

  - **What this setting does:** Selects where in your store this category block will appear. Hooks are specific display points in your PrestaShop theme.
  - **Effect of changing this setting:** Determines the physical location of the block on your website.
  - **Recommended value:** Depends on your design. Common choices are `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayHome`.
  - **Merchant scenario / example:** To show a block in the left sidebar, select `displayLeftColumn`. To show it in the footer, select `displayFooter`.
- **Root Category:**

  - **What this setting does:** This is the starting point (the “parent”) for the categories displayed in this specific block. Only this category and its sub-categories will be shown.
  - **Effect of changing this setting:**
    - *Selecting “Home”:* The block will display all categories starting from the very top of your category tree.
    - *Selecting a specific category (e.g., “Electronics”):* The block will only show “Electronics” and all its sub-categories.
  - **Recommended value:** Choose the highest-level category that defines the scope of this block.
  - **Merchant scenario / example:** If you want a block specifically for “Clothing,” select your “Clothing” category here.
- **Maximum Depth:**

  - **What this setting does:** Controls how many levels of sub-categories are displayed within this block, starting from the Root Category.
  - **Effect of changing this setting:**
    - *Setting to 1:* Only the Root Category itself will be shown (if “Display Root Category” is Yes).
    - *Setting to 2:* The Root Category and its immediate sub-categories will be shown.
    - *Setting to 0 (or empty):* All sub-categories, regardless of depth, will be displayed.
  - **Recommended value:** 2 or 3 for most column blocks to keep them manageable. 0 for footer blocks if you want a full sitemap.
  - **Merchant scenario / example:** If your “Electronics” category has sub-categories like “Cameras” and “Laptops,” and “Cameras” has “DSLRs” and “Mirrorless,” setting depth to 2 would show “Electronics > Cameras, Laptops”. Setting to 3 would show “Electronics > Cameras > DSLRs, Mirrorless, Laptops”.
- **Dynamic (open current category tree):**

  - **What this setting does:** When a customer navigates to a category page, this option determines if the category block automatically expands to show the current category and its sub-categories.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* If a customer is on the “DSLRs” page, the category block will automatically expand “Electronics > Cameras > DSLRs” to show the path.
    - *When disabled (No):* The category block will remain in its default collapsed state, regardless of the current page.
  - **Recommended value:** “Yes” for a better user experience, as it helps customers understand their current location in the category tree.
  - **Merchant scenario / example:** This is particularly useful in side columns to keep the navigation relevant to the user’s current browsing context.
- **Display Root Category:**

  - **What this setting does:** Controls whether the “Root Category” itself (the one you selected above) is displayed as the top item in the block.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* The Root Category will be the first clickable item in the block.
    - *When disabled (No):* The block will start displaying from the immediate sub-categories of the Root Category.
  - **Recommended value:** “Yes” if the Root Category is a broad category like “Shop by Department”. “No” if the Root Category is just a logical grouping and you want to start directly with its sub-categories (e.g., a “Brands” block where “Brands” itself isn’t a product category).
  - **Merchant scenario / example:** If your Root Category is “Men’s Clothing” and you want that to be the top link, set to “Yes”. If you want the block to start directly with “Shirts,” “Pants,” etc., set to “No”.
- **Display Number of Products:**

  - **What this setting does:** Shows the count of products available within each category next to its name in the block.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* Categories will appear as “Category Name (X)”.
    - *When disabled (No):* Only the category name will be displayed.
  - **Recommended value:** “Yes” can be helpful for customers to gauge the size of a category, but “No” can lead to a cleaner look. Test both to see what fits your design.
  - **Merchant scenario / example:** If you want to show “T-Shirts (125)” next to the category name, enable this.
- **Display Categories with no products:**

  - **What this setting does:** Determines if categories that currently have zero products assigned to them are still shown in the block.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* Empty categories will still appear.
    - *When disabled (No):* Empty categories will be hidden from the block.
  - **Recommended value:** “No” to avoid dead ends for customers and keep your navigation clean. Only enable “Yes” if you have a specific reason to show upcoming categories.
  - **Merchant scenario / example:** If you’re building out a new product line and have created categories but haven’t added products yet, you might temporarily enable “Yes” for internal testing, but generally “No” for live stores.
- **Order by:**

  - **What this setting does:** Defines the sorting order of categories within the block.
  - **Effect of changing this setting:** Changes the sequence in which categories are listed.
  - **Recommended value:** “Position” (default PrestaShop order) or “Name” (alphabetical).
  - **Merchant scenario / example:** If you want your categories to appear alphabetically, select “Name”. If you prefer to manually sort them in the PrestaShop Categories section, select “Position”.
- **Order Way:**

  - **What this setting does:** Specifies ascending or descending order for the “Order by” setting.
  - **Effect of changing this setting:**
    - *ASC:* Ascending (A-Z, 1-9).
    - *DESC:* Descending (Z-A, 9-1).
  - **Recommended value:** “ASC” for most cases.
  - **Merchant scenario / example:** If you ordered by “Name” and want A-Z, select “ASC”.

#### **Managing Existing Blocks**

After creating blocks, you will see a list with options to:

- **Edit:** Modify the settings of an existing block.
- **Delete:** Remove a block from your store.
- **Toggle Status (Enable/Disable):** Quickly turn a block on or off without deleting its configuration.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | **Block Name** | Descriptive | Internal identifier for the block. |
|  | **Display Block Title** | Yes | Shows/hides the block’s title to customers. |
|  | **Block Title** | “Categories” (example) | The visible title for the block (multi-language). |
|  | **Hook to display block** | `displayLeftColumn` | Determines where the block appears in your theme. |
|  | **Root Category** | Home | Sets the starting point for categories in this block. |
|  | **Maximum Depth** | 0 (All) | Limits the number of sub-category levels displayed. |
|  | **Dynamic (open current category tree)** | Yes | Automatically expands the tree to the current category. |
|  | **Display Root Category** | Yes | Shows/hides the selected Root Category itself. |
|  | **Display Number of Products** | No | Shows/hides product counts next to category names. |
|  | **Display Categories with no products** | No | Shows/hides categories that have no products. |
|  | **Order by** | Position | Sorts categories by position or name. |
|  | **Order Way** | ASC | Sorts categories in ascending or descending order. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My new category block isn’t showing up on the front office.**
A1:

- **Check Hook:** Ensure you’ve selected the correct “Hook to display block” in the module configuration.
- **Module Position:** Go to **Design > Positions** (or **Modules > Positions** in older versions). Search for `Multiple Categories Blocks` and ensure it’s hooked to the position you selected and is not disabled. You might need to move its position up or down if other modules are overlapping.
- **Module Status:** In the module configuration, ensure the block is “Enabled” (green checkmark).
- **Cache:** Clear your PrestaShop cache (**Advanced Parameters > Performance > Clear cache**).

**Q2: The categories in my block are not expanding or showing correctly.**
A2:

- **Root Category & Max Depth:** Double-check your “Root Category” and “Maximum Depth” settings. If Max Depth is too low, sub-categories won’t appear. If the Root Category is incorrect, you’ll see the wrong tree.
- **Dynamic Option:** If you expect the tree to expand automatically when navigating, ensure “Dynamic (open current category tree)” is set to “Yes”.
- **Categories with no products:** If categories are missing, check “Display Categories with no products”. If it’s “No”, categories without products will be hidden.

**Q3: The styling of the category block doesn’t match my theme.**
A3:

- The module tries to inherit styles from your active PrestaShop theme. However, custom themes might require minor CSS adjustments.
- You can often override the module’s default CSS by adding rules to your theme’s `custom.css` or `theme.css` file. (See Section 7.5 for developer details on module CSS).
- For PrestaShop 1.7/8/9, ensure you’re using the `multicatblock-prestashop17.css` file if your theme requires it (this is handled automatically by the module).

**Q4: How do I translate the block title into other languages?**
A4:

- When editing a block, the “Block Title” field will have language flags next to it. Click on each flag to enter the title for that specific language.
- Save your changes after entering all translations.

**Q5: Why are some categories missing from the block, even though they have products?**
A5:

- **Root Category Scope:** Ensure the missing categories are actually descendants (sub-categories) of the “Root Category” you selected for that specific block. If they are outside that branch, they won’t appear.
- **Category Status:** Check in **Catalog > Categories** that the missing categories are “Enabled” and “Displayed” (visible).
- **Product Association:** Double-check that products are correctly associated with the categories in question.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The Multiple Categories Blocks module (`multicatblocks`) follows a standard PrestaShop module architecture, primarily leveraging the `Module` class for its core functionality and configuration. It integrates into the front-office via various display hooks and uses Smarty templates for rendering. The module stores its configuration settings in the `ps_configuration` table, allowing for multiple, distinct category blocks to be defined. It utilizes a custom tree-rendering logic to build the category navigation.

### 4.2 Controllers (`controllers/`)

This module does not use dedicated front-office or back-office controllers. All configuration and front-office rendering logic are handled within the main `index.php` module file and its associated templates and hooks.

### 4.3 Core Classes & Models (`classes/`)

This module does not define custom `ObjectModel` classes. All data manipulation for categories relies on PrestaShop’s native `Category` class.

The main logic resides in `multicatblocks/index.php`:

- **`Multicatblocks` class:** Extends `Module`.
  - **`__construct()`:** Initializes module details, sets up tabs, and registers hooks.
  - **`install()`:** Registers necessary hooks (`displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayHome`, `displayProductButtons` - though the latter might be for legacy/internal use as it’s not exposed in config), creates default configuration entries.
  - **`uninstall()`:** Cleans up configuration entries.
  - **`getContent()`:** Handles the Back Office configuration form submission and display. It manages the creation, editing, and deletion of category blocks, storing their settings in `Configuration::updateValue()`.
  - **`hookDisplayHeader()`:** Injects CSS and JavaScript assets into the `<head>` section of the front office.
  - **`hookDisplayLeftColumn()`, `hookDisplayRightColumn()`, `hookDisplayFooter()`, `hookDisplayHome()`, `hookDisplayProductButtons()`:** These methods are responsible for retrieving the configured blocks for their respective hooks, fetching category data, preparing Smarty variables, and rendering the `multicatblock.tpl` or `multicatblock-footer.tpl` template.
  - **`getCategoryTree()`:** A crucial internal method that recursively fetches and structures the category data based on the block’s configuration (root category, max depth, product count, etc.).

### 4.4 JavaScript Assets (`views/js/`)

- **`multicatblocks/js/script.js`**:

  - **Scope:** Front-office.
  - **Purpose:** Handles the core interactive behavior of the category tree, such as expanding/collapsing sub-categories. It likely binds click events to category links or expand/collapse icons.
  - **Details:** This script is responsible for the “dynamic” behavior, ensuring that when a category is clicked, its sub-categories are revealed or hidden, and potentially highlighting the active category path.
- **`multicatblocks/js/tree.js`**:

  - **Scope:** Front-office.
  - **Purpose:** Likely a dependency or an older version of the tree functionality, or specifically handles the initial state and rendering of the tree structure.
  - **Details:** Could contain logic for initializing the tree, handling AJAX calls for category data (if applicable, though the module seems to render the full tree on page load), or managing the tree’s state.
- **`multicatblocks/lib/searchTool/views/js/autocomplete.js`**:

  - **Scope:** Back-office (admin configuration).
  - **Purpose:** Provides an autocomplete functionality for selecting categories in the module’s configuration form, specifically for the “Root Category” setting.
  - **Details:** Binds to an input field, makes AJAX requests to a PrestaShop admin controller (likely `AdminCategories` or a custom one if present, though none are listed) to search for categories, and displays suggestions.

### 4.5 CSS Stylesheets (`views/css/`)

- **`multicatblocks/css.css`**:

  - **Scope:** Front-office.
  - **Purpose:** General styling for the category blocks.
  - **Details:** Contains basic rules for list items, links, and potentially expand/collapse icons. Key selectors might include `.multicatblock`, `.multicatblock_list`, `.multicatblock_item`.
- **`multicatblocks/lib/searchTool/views/css/autocomplete.css`**:

  - **Scope:** Back-office (admin configuration).
  - **Purpose:** Styles for the autocomplete search input and its suggestion dropdown.
  - **Details:** Ensures the category search tool in the admin panel is visually consistent and user-friendly.
- **`multicatblocks/multicatblock-prestashop17.css`**:

  - **Scope:** Front-office.
  - **Purpose:** Specific overrides or additional styles tailored for PrestaShop 1.7.x, 8.x, and 9.x themes (e.g., Classic theme).
  - **Details:** Addresses potential layout or styling inconsistencies that might arise between older PrestaShop versions and the newer theme structures. This is conditionally loaded based on PS version.
- **`multicatblocks/multicatblock.css`**:

  - **Scope:** Front-office.
  - **Purpose:** Core styling for the category blocks, likely for older PrestaShop versions (1.5.x, 1.6.x) or as a fallback.
  - **Details:** Similar to `css.css`, but might contain more specific rules for older theme structures.
- **`multicatblocks/views/css/mcb-admin.css`**:

  - **Scope:** Back-office (admin configuration).
  - **Purpose:** Styling for the module’s configuration page in the PrestaShop Back Office.
  - **Details:** Ensures the module’s settings form, list of blocks, and other admin UI elements are well-presented and consistent with the PrestaShop admin theme.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/` - though files are directly in `multicatblocks/`):**

  - **`multicatblocks/multicatblock.tpl`**:
    - **Hooked in:** `displayLeftColumn`, `displayRightColumn`, `displayHome`, `displayProductButtons`.
    - **Outputs:** The main category block structure, including the title (if enabled) and the recursive category tree generated by `category-tree-branch.tpl`.
  - **`multicatblocks/multicatblock-footer.tpl`**:
    - **Hooked in:** `displayFooter`.
    - **Outputs:** A variation of the category block specifically for the footer, potentially with different styling or structural elements. It also uses `category-tree-branch-footer.tpl`.
  - **`multicatblocks/category-tree-branch.tpl`**:
    - **Hooked in:** Included by `multicatblock.tpl`.
    - **Outputs:** Recursively renders a single branch of the category tree. It iterates through sub-categories, handles depth limits, and displays product counts.
  - **`multicatblocks/category-tree-branch-footer.tpl`**:
    - **Hooked in:** Included by `multicatblock-footer.tpl`.
    - **Outputs:** Similar to `category-tree-branch.tpl` but tailored for the footer block’s structure.
- **Admin templates (`views/templates/admin/` - though `shell.tpl` is in `multicatblocks/views/templates/admin/`):**

  - **`multicatblocks/views/templates/admin/shell.tpl`**:
    - **Purpose:** The main template for the module’s configuration page in the Back Office.
    - **Outputs:** The form for adding/editing blocks, the list of existing blocks, and potentially includes other admin-specific elements.
- **Library templates:**

  - **`multicatblocks/lib/searchTool/views/scripts.tpl`**:
    - **Purpose:** Likely includes JavaScript necessary for the autocomplete search tool used in the admin configuration.
    - **Outputs:** `<script>` tags or inline JavaScript for the autocomplete functionality.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create custom SQL tables.
  - All configuration for each category block is stored in the `ps_configuration` table. Each block’s settings are serialized and stored under a unique configuration key (e.g., `MULTICATBLOCKS_BLOCKS`).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Injects module’s CSS and JavaScript files. |
| `displayLeftColumn` | In the left sidebar of the front office. | Renders a configured category block in the left column. |
| `displayRightColumn` | In the right sidebar of the front office. | Renders a configured category block in the right column. |
| `displayFooter` | In the footer section of the front office. | Renders a configured category block in the footer. |
| `displayHome` | On the homepage (if theme supports `displayHome` hook). | Renders a configured category block on the homepage. |
| `displayProductButtons` | On the product page, near the add-to-cart button. | Renders a configured category block on product pages (less common for this module, but available). |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Multiple Categories Blocks” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any technical issues or questions you may have.
