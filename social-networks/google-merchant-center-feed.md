---
title: "Google merchant center feed - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Google merchant center feed PrestaShop module by MyPresta.eu."
sidebar:
  label: "Google merchant center feed - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Google merchant center feed Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/google-merchant-center-feed/)
>
> ---


# Google merchant center feed

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL). Sufficient server resources (CPU, RAM) may be required for generating very large product feeds, especially for stores with tens of thousands of products.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the module, accessed immediately after installation or by clicking “Configure” from the Module Manager.

- **What this setting does:** This option controls whether a category tree selector is displayed on the product export screen, allowing you to include or exclude products based on their category.
- **Effect of changing this setting:**
  - *When enabled (checked):* On the product export screen (AdminExportProductsFeedGoogle), you will see a visual tree of your store’s categories. This allows you to easily select which categories of products should be included or excluded from your Google Merchant Center feed. This is crucial for filtering your feed to only include relevant products or to exclude specific categories you don’t want to advertise on Google.
  - *When disabled (unchecked):* The category tree selector will not appear on the export screen. This means you won’t be able to filter products by category directly within the module’s interface. You would then export all products, or rely on other filtering options if available (e.g., product-specific exclusions).
- **Recommended value:** **YES (checked)**.
- **Merchant scenario / example:** You sell both clothing and digital downloads. You only want to advertise your clothing products on Google Shopping. By enabling “Show categories tree,” you can easily select only your “Clothing” categories for inclusion in the feed, excluding your “Digital Downloads” category.

### 2.2 Dedicated Admin Screens & Controller Views

#### AdminExportProductsFeedGoogleController (Back Office > Modules > Google merchant center feed > Export Products Feed)

This is the primary screen where you will generate and manage your Google Merchant Center product feeds. You access it by navigating to **Modules > Module Manager**, finding “Google merchant center feed”, and then clicking on the “Export Products Feed” link (or similar, depending on PrestaShop version, it might be a sub-menu item under the module’s main entry).

This screen allows you to define the content and format of your product feed.

**Available Actions & Settings:**

The screen presents a form with various fields corresponding to the attributes required by Google Merchant Center. You will fill these out to customize your feed.

- **ID:**
  - **Purpose:** This is the unique identifier for each product in your feed. Google uses this to match your product with its data.
  - **Effect of changes:** Ensures each product has a distinct ID, which is critical for Google to correctly process your feed.
  - **Recommended value:** Usually maps to your product’s internal ID or reference.
- **GTIN (Global Trade Item Number):**
  - **Purpose:** Global Trade Item Numbers (like EAN, UPC, ISBN) are unique product identifiers used globally. Google requires these for most products.
  - **Effect of changes:** Including correct GTINs helps Google identify your products accurately, improving visibility and trust. Missing or incorrect GTINs can lead to product disapprovals.
  - **Recommended value:** Map to your product’s EAN/UPC field.
- **Identifier\_exists:**
  - **Purpose:** Indicates whether a unique product identifier (like GTIN, Brand, MPN) exists for the product.
  - **Effect of changes:** If you sell custom products or products without standard identifiers, setting this to ‘no’ (or ‘false’) can prevent disapprovals. For most standard products, it should be ‘yes’.
  - **Recommended value:** Usually ‘yes’ if GTINs are provided.
- **Title:**
  - **Purpose:** The name of your product as it will appear on Google Shopping. This is a crucial field for attracting clicks.
  - **Effect of changes:** A clear, descriptive title with relevant keywords improves search visibility and click-through rates.
  - **Recommended value:** Your product’s name, potentially enhanced with key attributes (e.g., “Red T-shirt - Size M - Cotton”).
- **Availability:**
  - **Purpose:** Indicates whether the product is in stock, out of stock, or available for pre-order.
  - **Effect of changes:** Accurate availability prevents customers from clicking on out-of-stock items, improving user experience and reducing wasted ad spend.
  - **Recommended value:** Automatically pulled from your product’s stock status.
- **Availability\_date:**
  - **Purpose:** The date when a pre-ordered product will become available.
  - **Effect of changes:** Provides transparency for customers interested in pre-order items.
  - **Recommended value:** Set if you offer pre-orders.
- **Inventory:**
  - **Purpose:** The quantity of the product currently in stock.
  - **Effect of changes:** Keeps your Google listings synchronized with your actual stock levels, preventing overselling.
  - **Recommended value:** Automatically pulled from your product’s stock quantity.
- **Brand:**
  - **Purpose:** The brand name of your product.
  - **Effect of changes:** Helps customers identify familiar brands and improves product categorization on Google.
  - **Recommended value:** Your product’s brand/manufacturer.
- **Link:**
  - **Purpose:** The direct URL to your product page on your store.
  - **Effect of changes:** Essential for directing customers from Google to your website.
  - **Recommended value:** Your product’s canonical URL.
- **Image link:**
  - **Purpose:** The URL of the main image for your product.
  - **Effect of changes:** High-quality, clear images are critical for attracting clicks on Google Shopping.
  - **Recommended value:** Your product’s main image URL.
- **Additional\_image\_link:**
  - **Purpose:** URLs for additional images of your product.
  - **Effect of changes:** Provides more visual information to potential customers, helping them make purchasing decisions.
  - **Recommended value:** URLs of secondary product images.
- **Item subtitle:**
  - **Purpose:** An optional, shorter description or additional detail for the product.
  - **Effect of changes:** Can be used to highlight key features or promotions.
  - **Recommended value:** Optional, use for short, impactful details.
- **Description:**
  - **Purpose:** A detailed description of your product.
  - **Effect of changes:** Provides comprehensive information to customers and helps Google understand your product’s relevance.
  - **Recommended value:** Your product’s full description.
- **Product\_type:**
  - **Purpose:** Your own categorization of the product within your store.
  - **Effect of changes:** Helps Google understand your product hierarchy and can be used for campaign targeting.
  - **Recommended value:** Your internal category path (e.g., “Apparel > T-Shirts > Men’s T-Shirts”).
- **Condition:**
  - **Purpose:** The condition of the product (e.g., new, used, refurbished).
  - **Effect of changes:** Accurate condition information is vital for customer trust and Google’s policies.
  - **Recommended value:** Usually ‘new’ for most e-commerce stores.
- **Price:**
  - **Purpose:** The current selling price of your product.
  - **Effect of changes:** Accurate pricing is paramount. Mismatches between your feed and your website can lead to disapprovals.
  - **Recommended value:** Your product’s current price.
- **Sale Price:**
  - **Purpose:** The discounted price of your product if it’s on sale.
  - **Effect of changes:** Highlights promotions and attracts customers looking for deals.
  - **Recommended value:** Your product’s specific price.
- **Tax rate:**
  - **Purpose:** The tax rate applicable to the product.
  - **Effect of changes:** Ensures accurate pricing information, especially for regions where tax is calculated at checkout.
  - **Recommended value:** Your store’s applicable tax rate.
- **Contextual keywords:**
  - **Purpose:** Additional keywords to help Google understand your product.
  - **Effect of changes:** Can improve the relevance of your product in search results.
  - **Recommended value:** Relevant search terms not already in the title or description.
- **Google product category:**
  - **Purpose:** Google’s standardized categorization for products. This is a critical field for Google to understand what you’re selling.
  - **Effect of changes:** Correctly categorizing your products according to Google’s taxonomy improves visibility and ensures your products appear in relevant searches. Incorrect categories can lead to disapprovals.
  - **Recommended value:** Select the most specific Google Product Category that applies to your product.

**Other Settings & Options:**

- **Export Size Attribute:**
  - **Purpose:** Determines if product size attributes should be included in the feed, which is important for apparel and other size-dependent products.
  - **Effect of changes:**
    - *When enabled:* Product sizes (e.g., S, M, L) will be exported, allowing Google to display size information and filter options.
    - *When disabled:* Size information will not be included.
  - **Recommended value:** **YES** for clothing/apparel stores, **NO** for other types of products.
- **Export Exclude Categories:**
  - **Purpose:** Allows you to select specific categories whose products should be *excluded* from the feed. This works in conjunction with the “Show categories tree” setting from the main configuration.
  - **Effect of changes:** Products belonging to the selected categories will not appear in the generated feed.
  - **Recommended value:** Use this to filter out products you don’t want to advertise on Google (e.g., out-of-stock categories, services, or products with low margins).
- **Export Availability Date:**
  - **Purpose:** Controls whether the `availability_date` attribute is included in the feed.
  - **Effect of changes:**
    - *When enabled:* The date when a product becomes available (for pre-orders) will be included.
    - *When disabled:* This information will be omitted.
  - **Recommended value:** **YES** if you use PrestaShop’s pre-order functionality and want to communicate availability dates to Google.
- **Generate Feed Button:**
  - **Purpose:** Initiates the process of generating the XML/CSV product feed based on all your selected options.
  - **Effect of changes:** Creates the feed file, which you can then download or provide the URL to Google Merchant Center for scheduled fetches.

**Recommended workflow for daily store management:**

1. **Initial Setup:** Carefully map all Google Merchant Center attributes to your PrestaShop product fields. Pay special attention to GTIN, Brand, and Google Product Category.
2. **Category Filtering:** Use the “Export Exclude Categories” option to fine-tune which products are sent to Google.
3. **Generate & Test:** Generate a feed and upload it to Google Merchant Center. Monitor for any errors or warnings in your Google Merchant Center account.
4. **Scheduled Fetches:** Once your feed is approved, set up a scheduled fetch in Google Merchant Center using the URL provided by the module. This ensures Google always has the latest product data.
5. **Regular Review:** Periodically review your Google Merchant Center diagnostics for any disapprovals or warnings, and adjust your module settings or product data in PrestaShop accordingly.

#### index.php (gmfeed/controllers/admin/index.php)

This file likely serves as a placeholder or a redirect within the module’s admin controller structure and does not represent a distinct, configurable screen for the merchant. The primary configuration and management happens through `AdminExportProductsFeedGoogleController`.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration Page** | Show categories tree | YES | Enables category filtering on the export screen for precise product selection. |
| **AdminExportProductsFeedGoogle** | ID | Product ID | Unique identifier for each product in the feed. |
|  | GTIN | Product EAN/UPC | Global Trade Item Number for product identification. |
|  | Identifier\_exists | Yes | Indicates if unique identifiers are present. |
|  | Title | Product Name | Product title for Google Shopping. |
|  | Availability | Auto-detected | Product stock status (in stock, out of stock). |
|  | Availability\_date | Auto-detected | Date for pre-order availability. |
|  | Inventory | Auto-detected | Current stock quantity. |
|  | Brand | Product Manufacturer | Brand name of the product. |
|  | Link | Product URL | Direct link to the product page. |
|  | Image link | Main Product Image URL | URL of the main product image. |
|  | Additional\_image\_link | Secondary Product Image URLs | URLs of additional product images. |
|  | Item subtitle | Optional | Short, additional product detail. |
|  | Description | Product Description | Detailed product description. |
|  | Product\_type | Your Category Path | Your internal product categorization. |
|  | Condition | New | Condition of the product (new, used, refurbished). |
|  | Price | Product Price | Current selling price. |
|  | Sale Price | Product Specific Price | Discounted price if on sale. |
|  | Tax rate | Store Tax Rate | Applicable tax rate. |
|  | Contextual keywords | Optional | Additional keywords for product relevance. |
|  | Google product category | Select from Google Taxonomy | Google’s standardized product category. |
|  | Export Size Attribute | YES (for apparel) | Includes product size attributes in the feed. |
|  | Export Exclude Categories | Select as needed | Excludes products from selected categories. |
|  | Export Availability Date | YES (for pre-orders) | Includes `availability_date` attribute. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My products are not appearing on Google Shopping, or I’m getting disapprovals. What should I check first?**
A1:

- **Google Merchant Center (GMC) Account:** Log into your GMC account and check the “Diagnostics” section. This is where Google reports specific errors or warnings for your products and feed.
- **Feed Processing:** Ensure your feed has been successfully processed by Google. Check the “Feeds” section in GMC.
- **Required Attributes:** Verify that all mandatory Google attributes (ID, Title, Link, Image Link, Price, Description, GTIN/Brand/MPN, Availability, Google Product Category) are correctly mapped and populated in the module’s export settings.
- **Data Mismatches:** Google is very strict about price and availability matching between your feed and your website. Make sure your PrestaShop product data is accurate and that Google is fetching the latest feed.
- **Google Product Category:** Ensure you’ve selected the most accurate Google Product Category for your products.

**Q2: I’ve made changes to my products in PrestaShop, but they’re not updating on Google Shopping.**
A2:

- **Generate New Feed:** After making changes in PrestaShop, you need to generate a new feed using the module’s “Generate Feed” button.
- **Google Scheduled Fetch:** Google Merchant Center needs to fetch this updated feed. If you have a scheduled fetch set up, it will update automatically at the next scheduled time. You can also manually trigger a fetch in your Google Merchant Center account under “Feeds” > “Fetch now”.
- **Caching:** Clear your PrestaShop Smarty cache (Advanced Parameters > Performance) and browser cache to ensure you’re seeing the latest version of the module’s configuration and generated feed.

**Q3: How do I exclude certain products or categories from the Google feed?**
A3:

- On the module’s main configuration screen, ensure “Show categories tree” is enabled.
- Then, on the `AdminExportProductsFeedGoogle` screen, use the “Export Exclude Categories” option. You’ll see a tree of your categories. Select the categories whose products you wish to exclude from the feed.
- Generate a new feed after making these selections.

**Q4: The feed generation process takes a very long time or times out for my large store.**
A4:

- **Server Resources:** Generating large feeds can be resource-intensive. Contact your hosting provider to ensure your server has sufficient PHP memory limit, execution time, and CPU resources.
- **PHP Settings:** Increase `max_execution_time` and `memory_limit` in your `php.ini` file (or via your hosting control panel).
- **Filter Products:** If possible, try to segment your feed by excluding less important categories or products to reduce the feed size.
- **Module Updates:** Ensure you are running the latest version of the module, as performance improvements are often included in updates.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The `Google merchant center feed` module follows a standard PrestaShop module architecture, primarily leveraging Back-Office controllers for configuration and feed generation. It uses a front controller to expose the generated feed URL for Google’s scheduled fetches. The module does not extend `ObjectModel` for custom database tables but relies on PrestaShop’s `Configuration` class for settings. It integrates a third-party search tool library for autocomplete functionality.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `controllers/front/feed.php`
  - **Class Name:** `GmfeedFeedModuleFrontController`
  - **Parent Class:** `ModuleFrontController`
  - **Responsibility:** This controller is responsible for serving the generated XML/CSV product feed to Google Merchant Center. When Google performs a scheduled fetch, it hits a URL handled by this controller. The controller retrieves the latest generated feed data and outputs it, typically with appropriate headers for file download or direct display.
- `controllers/front/index.php`
  - **Class Name:** `GmfeedIndexModuleFrontController`
  - **Parent Class:** `ModuleFrontController`
  - **Responsibility:** This is likely a placeholder or a default front controller that might redirect or simply display a blank page. It doesn’t appear to have a direct functional role in the feed generation or display based on the provided information.

#### Back-Office Admin Controllers

- `controllers/admin/AdminExportProductsFeedGoogle.php`
  - **Class Name:** `AdminExportProductsFeedGoogleController`
  - **Parent Class:** `ModuleAdminController`
  - **Tab Name:** “Export Products Feed” (or similar, linked from the main module config)
  - **Managed Entity:** Product feed generation.
  - **Responsibility:** This is the core admin controller for managing and generating the Google Merchant Center feed. It handles the display of the configuration form for feed attributes (GTIN, Title, Price, etc.), processes form submissions, and triggers the feed generation logic. It interacts with PrestaShop’s product, category, and attribute data to compile the feed. It also manages the exclusion of categories (`gm_export_exclude_categories`) and other feed-specific settings.
- `controllers/admin/index.php`
  - **Class Name:** `GmfeedIndexModuleAdminController`
  - **Parent Class:** `ModuleAdminController`
  - **Tab Name:** (Likely not a direct tab, but part of the module’s internal routing)
  - **Responsibility:** Similar to its front-office counterpart, this is likely a placeholder or a default admin controller. It doesn’t appear to manage a specific entity or provide a distinct UI.

### 4.3 Core Classes & Models (`classes/`)

The provided information indicates no custom classes or models within the `classes/` directory. The module likely performs its operations directly within the main module file (`gmfeed.php`) and its controllers, leveraging existing PrestaShop `ObjectModel` classes (like `Product`, `Category`, `Manufacturer`, `AttributeGroup`, `Attribute`) and the `Configuration` class for settings.

### 4.4 JavaScript Assets (`views/js/`)

- `gmfeed/lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Likely Back-office.
  - **Details:** This script is part of a search tool library, probably used for autocomplete functionality within the admin configuration forms, such as selecting Google Product Categories or excluding specific products/categories. It would bind to input fields, make AJAX requests to a backend endpoint (possibly handled by one of the admin controllers) to fetch suggestions, and display them to the user.

### 4.5 CSS Stylesheets (`views/css/`)

- `gmfeed/lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Back-office admin form styling.
  - **Details:** Provides styling for the autocomplete suggestions and input fields, ensuring a consistent and user-friendly appearance for the search tool within the module’s admin interface.
  - **Key CSS selectors:** Likely includes classes for the autocomplete container, suggestion list, active suggestion, and input field.
- `gmfeed/views/admin-theme.css`
  - **Scope:** Back-office admin form styling.
  - **Details:** Contains general styling rules specific to the module’s configuration pages in the PrestaShop Back Office. This might include layout adjustments, button styling, form element styling, or specific visual cues for the module’s interface.
  - **Key CSS selectors:** Module-specific container IDs or classes, form element classes.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

The module dossier indicates `actionAdminControllerSetMedia` as a front-office hook, which is unusual as it’s an admin hook. It’s more likely that the module uses `actionAdminControllerSetMedia` to load its JS/CSS assets in the back office, and the templates listed below are rendered within the admin context.

#### Admin templates (`views/templates/admin/`)

- `gmfeed/lib/searchTool/views/scripts.tpl`
  - **Purpose:** Likely includes JavaScript code or initializes the autocomplete functionality. This template would be rendered in the Back Office to set up the search tool.
- `gmfeed/views/categories-fancybox.tpl`
  - **Purpose:** This template is used to display the category tree for selection/exclusion, likely within a Fancybox (or similar modal) popup. It would render the hierarchical list of categories.
- `gmfeed/views/exclude-products.tpl`
  - **Purpose:** This template would display the interface for selecting products to exclude from the feed, potentially using the search tool and category tree.
- `gmfeed/views/google_lang_links.tpl`
  - **Purpose:** This template might be used to display links or information related to Google Merchant Center for different languages, possibly guiding the merchant to set up feeds for various store languages.
- `gmfeed/views/returnAlert.tpl`
  - **Purpose:** A generic template for displaying alerts or messages to the user in the Back Office, such as success messages after feed generation or error notifications.
- `gmfeed/views/script-fancybox.tpl`
  - **Purpose:** This template likely contains JavaScript code to initialize and configure the Fancybox (or similar modal) library, used for displaying popups like the category tree.
- `gmfeed/views/script.tpl`
  - **Purpose:** A general script template for the module’s Back Office, potentially containing various JavaScript functionalities, event listeners, or AJAX calls related to the configuration and feed generation process.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not appear to create custom SQL tables based on the provided information (no `classes/` with `ObjectModel` or `install/uninstall` SQL files).
  - Configuration settings (e.g., `pf_tree`, `gm_export_size_attribute`, `gm_export_exclude_categories`, `gm_export_availability_date`) are stored in the `ps_configuration` table. The `gm_export_exclude_categories` value would likely be a serialized array of category IDs.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Executed when an Admin Controller is initialized and its media (JS/CSS) are being set. | Used by the module to load its specific JavaScript and CSS files (e.g., `autocomplete.js`, `admin-theme.css`) into the Back Office for its configuration screens. |

## 5. Official Support & Updates

For official updates, technical support, and the latest versions of the “Google merchant center feed” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and integration with your PrestaShop store.
