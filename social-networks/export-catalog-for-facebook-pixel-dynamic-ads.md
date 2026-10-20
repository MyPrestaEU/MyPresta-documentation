---
title: "Export catalog for facebook pixel dynamic ads - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Export catalog for facebook pixel dynamic ads PrestaShop module by MyPresta.eu."
sidebar:
  label: "Export catalog for facebook pixel dynamic ads - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Export catalog for facebook pixel dynamic ads Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/export-catalog-for-facebook-pixel-dynamic-ads.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/export-catalog-for-facebook-pixel-dynamic-ads/)
>
> ---


# Export catalog for facebook pixel dynamic ads

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. Ensure your server has enough memory and execution time to generate large product feeds if you have many products.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The module’s configuration is primarily handled through a dedicated administration screen, which allows you to define how your product catalog is exported.

### 2.1 Module Main Configuration Screen (Back Office > Modules > Module Manager > Configure)

This screen provides the main settings for the module, allowing you to generate and manage your product feeds.

**Menu Location:** Back Office > Modules > Module Manager > Search for “Export catalog for facebook pixel dynamic ads” > Click “Configure”.

#### General Settings & Feed Generation

This section is where you define the core parameters for your product feed.

- **Select Language for Export:**

  - **What this setting does:** Determines which language’s product names, descriptions, and other text fields will be included in the exported feed.
  - **Effect of changing this setting:**
    - *When set to English:* Your feed will contain product details in English.
    - *When set to French:* Your feed will contain product details in French.
  - **Recommended value:** The primary language of your target audience for Facebook Ads. If you run ads in multiple languages, you’ll need to generate separate feeds for each language.
  - **Merchant scenario / example:** If you primarily target customers in the USA, you would select “English”. If you also target customers in France, you would generate a separate feed with “French” selected.
- **Select Currency for Export:**

  - **What this setting does:** Determines which currency’s prices will be included in the exported feed.
  - **Effect of changing this setting:**
    - *When set to USD:* All product prices in the feed will be in US Dollars.
    - *When set to EUR:* All product prices in the feed will be in Euros.
  - **Recommended value:** The primary currency of your target audience for Facebook Ads. Like language, if you target multiple currencies, you’ll need separate feeds.
  - **Merchant scenario / example:** If your store sells in both USD and CAD, and you want to run Facebook Ads for your Canadian customers, you would select “Canadian Dollar” for that specific feed.
- **Export only active products:**

  - **What this setting does:** Controls whether only products currently enabled and visible in your store are included in the feed.
  - **Effect of changing this setting:**
    - *When enabled (YES):* Only products that are active in your PrestaShop store will be exported. This prevents showing ads for out-of-stock or discontinued items.
    - *When disabled (NO):* All products, including inactive ones, might be exported. This is generally not recommended for live ad campaigns.
  - **Recommended value:** **YES**. This ensures your ads are always relevant and link to available products.
  - **Merchant scenario / example:** You have seasonal products that are currently inactive. Enabling this ensures they don’t appear in your Facebook Ads until you reactivate them.
- **Export only in-stock products:**

  - **What this setting does:** Determines if only products with available stock are included in the feed.
  - **Effect of changing this setting:**
    - *When enabled (YES):* Only products that are currently in stock will be exported.
    - *When disabled (NO):* Products that are out of stock might be exported, potentially leading to a poor customer experience if they click an ad for an unavailable item.
  - **Recommended value:** **YES**. This prevents customers from clicking ads for products they cannot buy, reducing frustration and wasted ad spend.
  - **Merchant scenario / example:** A popular item just went out of stock. With this enabled, it will automatically be removed from your Facebook feed until it’s restocked.
- **Export product combinations (variations):**

  - **What this setting does:** Controls whether individual product combinations (e.g., a T-shirt in different sizes and colors) are exported as separate items in the feed.
  - **Effect of changing this setting:**
    - *When enabled (YES):* Each combination (e.g., “Red T-shirt - Small”, “Red T-shirt - Medium”) will appear as a unique item in the feed, with its own image, price, and link. This is crucial for dynamic ads to show the exact variant a customer viewed.
    - *When disabled (NO):* Only the main product will be exported, without individual combinations. This limits the granularity of your dynamic ads.
  - **Recommended value:** **YES**. This is highly recommended for most stores, especially those selling apparel, electronics, or any product with variations, to ensure the most accurate and personalized ad experience.
  - **Merchant scenario / example:** A customer views a “Blue Dress - Large” on your site. If combinations are exported, Facebook can show them an ad specifically for that “Blue Dress - Large.”
- **Product Identification (ID field):**

  - **What this setting does:** Specifies which PrestaShop ID field should be used as the unique identifier for products in the Facebook feed (`id` field).
  - **Effect of changing this setting:**
    - *Product ID:* Uses the standard `id_product` from PrestaShop.
    - *EAN13:* Uses the EAN13 barcode.
    - *UPC:* Uses the UPC barcode.
    - *Reference:* Uses the product’s internal reference code.
  - **Recommended value:** **Product ID** is generally the safest and most reliable option as it’s always unique and internal to PrestaShop. If you consistently use EAN13/UPC for all products and combinations, those can also work.
  - **Merchant scenario / example:** You have a custom integration that relies on `id_product` for tracking. Using “Product ID” here ensures consistency.
- **Product Category Field:**

  - **What this setting does:** Determines which category information is sent to Facebook.
  - **Effect of changing this setting:**
    - *Default PrestaShop Category:* Uses the product’s primary category name.
    - *Google Product Category:* Uses the Google Product Category (if assigned). This is often preferred by Facebook for better matching.
  - **Recommended value:** **Google Product Category** if you have them assigned. Otherwise, “Default PrestaShop Category.”
  - **Merchant scenario / example:** You sell “T-Shirts” in PrestaShop, but the Google Product Category is “Apparel & Accessories > Clothing > Shirts & Tops > T-Shirts.” Using the Google category provides more specific data to Facebook.
- **Product Brand Field:**

  - **What this setting does:** Selects which field from your product data should be used for the `brand` attribute in the Facebook feed.
  - **Effect of changing this setting:**
    - *Manufacturer Name:* Uses the manufacturer assigned to the product in PrestaShop.
    - *Supplier Name:* Uses the supplier assigned to the product.
  - **Recommended value:** **Manufacturer Name**. This is the most common and logical field for “brand.”
  - **Merchant scenario / example:** You sell Nike shoes. Selecting “Manufacturer Name” will correctly populate “Nike” as the brand in your feed.
- **Product Type Field:**

  - **What this setting does:** Specifies what information should be used for the `product_type` field in the Facebook feed.
  - **Effect of changing this setting:**
    - *Default PrestaShop Category:* Uses the product’s primary category name.
    - *Google Product Category:* Uses the Google Product Category (if assigned).
  - **Recommended value:** **Google Product Category** if available, otherwise “Default PrestaShop Category.” This helps Facebook understand the type of product.
  - **Merchant scenario / example:** For a product in “Electronics > Smartphones,” the Google Product Category might be “Electronics > Communications > Telephony > Mobile Phones.”
- **Product Image Field:**

  - **What this setting does:** Determines which image URL is used for the `image_link` in the feed.
  - **Effect of changing this setting:**
    - *Default Product Image:* Uses the main image associated with the product.
    - *Combination Image (if available):* If exporting combinations, this will use the specific image assigned to that combination, otherwise the default product image.
  - **Recommended value:** **Combination Image (if available)**. This ensures that if a customer views a red shirt, the ad shows a red shirt, not just the generic product image.
  - **Merchant scenario / example:** You have a product with multiple color combinations, each with its own image. This setting ensures the correct color image is displayed in the ad.
- **Product Description Field:**

  - **What this setting does:** Selects which description field from PrestaShop (`description` or `short_description`) is used for the `description` attribute in the Facebook feed.
  - **Effect of changing this setting:**
    - *Description:* Exports the full, detailed product description.
    - *Short Description:* Exports the brief product summary.
  - **Recommended value:** **Description**. Facebook typically prefers a more detailed description for better ad context.
  - **Merchant scenario / example:** You want to provide as much information as possible in your ads. Using the full description ensures this.
- **Product Short Description Field:**

  - **What this setting does:** Selects which description field from PrestaShop (`description` or `short_description`) is used for the `short_description` attribute in the Facebook feed.
  - **Effect of changing this setting:**
    - *Description:* Exports the full, detailed product description.
    - *Short Description:* Exports the brief product summary.
  - **Recommended value:** **Short Description**. This is useful if Facebook’s feed requires both a long and short description, or if you prefer a concise summary for certain ad formats.
  - **Merchant scenario / example:** You want a concise summary for the `short_description` field in your feed.
- **CSV Delimiter:**

  - **What this setting does:** Specifies the character used to separate values in the generated CSV file (e.g., comma, semicolon).
  - **Effect of changing this setting:**
    - *Comma (,):* Standard CSV format.
    - *Semicolon (;):* Common in some European locales.
  - **Recommended value:** **Comma (,)**. This is the most widely accepted delimiter for CSV files, including by Facebook.
  - **Merchant scenario / example:** If Facebook’s import tool specifies a semicolon delimiter, you would change it here. Otherwise, stick to comma.
- **Delete images from feed:**

  - **What this setting does:** If enabled, the module will remove image links from the generated feed.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The `image_link` and `additional_image_link` columns in the feed will be empty. This is generally NOT recommended as images are crucial for dynamic ads.
    - *When disabled (NO):* Image links will be included in the feed.
  - **Recommended value:** **NO**. Images are fundamental for visual ads.
  - **Merchant scenario / example:** This setting is rarely useful unless you have a very specific, advanced setup where images are handled entirely separately.

#### Exclude Products

This section allows you to prevent specific products from being included in your Facebook feed.

- **Exclude Products by ID:**
  - **What this setting does:** Allows you to enter a comma-separated list of product IDs that you do not want to appear in your Facebook product catalog.
  - **Effect of changing this setting:**
    - *Products listed here:* Will be completely omitted from the generated feed.
  - **Recommended value:** Leave empty unless you have specific products you never want to advertise (e.g., internal test products, services not suitable for dynamic ads).
  - **Merchant scenario / example:** You sell both physical products and digital services. You might exclude the digital service products from the feed as they don’t fit the dynamic ad format.

#### Generate Feed Button

- **What this button does:** Initiates the process of generating the product catalog CSV file based on all the settings you’ve configured above.
- **Effect of clicking this button:** The module will process your products and create a downloadable CSV file. Depending on the number of products, this might take some time.
- **Recommended action:** Click this button after you’ve reviewed and saved all your desired settings.
- **Merchant scenario / example:** After making changes to your product descriptions or adding new products, you would click this to generate an updated feed for Facebook.

#### Download Feed Button

- **What this button does:** Allows you to download the most recently generated product catalog CSV file to your computer.
- **Effect of clicking this button:** Your browser will download the `facebook_products.csv` file.
- **Recommended action:** Download the file after generation and then upload it to your Facebook Business Manager.
- **Merchant scenario / example:** Once the feed is generated, you download it and then navigate to your Facebook Business Manager > Catalogs > Data Sources to upload the CSV.

### 2.2 Dedicated Admin Screen: AdminExportProductsFeedController

This is the core administration screen where you manage the actual product feed generation and review the data that will be exported.

**Menu Location:** Back Office > Modules > Module Manager > Configure “Export catalog for facebook pixel dynamic ads” > (This screen is the main configuration interface itself, often accessed directly after clicking “Configure”).

This screen presents a grid-like interface or a form with various options to control the output of your product feed. The fields listed below represent the data points that can be included in your Facebook product catalog.

- **ID:** The unique identifier for the product (based on your “Product Identification” setting).
- **item\_group\_id:** Used for product combinations to group them under a single parent product.
- **Title:** The product’s name.
- **Short description:** The product’s brief summary.
- **Description:** The product’s full description.
- **Override:** (Likely an internal module setting, not directly exported to Facebook).
- **Availability:** Indicates if the product is in stock (`in stock`, `out of stock`).
- **Inventory:** The current stock quantity.
- **Condition:** The product’s condition (e.g., `new`, `used`, `refurbished`).
- **Image link:** The URL of the main product image.
- **Additional\_image\_link:** URLs of additional product images.
- **Price:** The product’s current price.
- **sale\_price:** The product’s sale price (if applicable).
- **Brand:** The product’s brand (manufacturer).
- **Link:** The direct URL to the product page on your store.
- **Google product category:** The Google Product Category assigned to the product.
- **product\_type:** The product’s type (e.g., category name).
- **gender:** For apparel, the target gender (e.g., `male`, `female`, `unisex`).
- **size:** For apparel, the product size.
- **age\_group:** For apparel, the target age group (e.g., `newborn`, `infant`, `toddler`, `kids`, `adult`).

**Available Actions & Settings:**
On this screen, you will find the various configuration options detailed in section 4.1. The “Managed Table / Entity” here refers to the virtual table of product data that the module constructs before exporting. There isn’t a direct database table managed by this specific controller, but rather it processes and prepares data from your existing PrestaShop product tables.

**Effect of changes:**
Any changes made to the settings on this screen (e.g., selecting a different language, enabling/disabling combination export) will directly alter the content and format of the CSV file generated when you click the “Generate Feed” button.

**Recommended workflow for daily store management:**

1. Periodically (e.g., daily or weekly, depending on how often your product catalog changes) visit this configuration page.
2. Ensure your language, currency, and stock/active product settings are correct.
3. Click “Generate Feed” to create an updated CSV.
4. Download the generated CSV.
5. Upload this new CSV to your Facebook Business Manager to refresh your product catalog. Facebook also offers options to schedule automatic fetches from a URL, which can be configured once you have a stable feed URL (often provided by the module or your server setup).

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Select Language for Export | Your Primary Language | Determines language of product names/descriptions in feed. |
|  | Select Currency for Export | Your Primary Currency | Determines currency of prices in feed. |
|  | Export only active products | YES | Includes only active products, preventing ads for unavailable items. |
|  | Export only in-stock products | YES | Includes only in-stock products, preventing ads for out-of-stock items. |
|  | Export product combinations | YES | Exports each product variation (size, color) as a unique item for granular ads. |
|  | Product Identification (ID field) | Product ID | Defines the unique identifier for products in the feed. |
|  | Product Category Field | Google Product Category (if available) | Specifies category data for Facebook. |
|  | Product Brand Field | Manufacturer Name | Specifies brand data for Facebook. |
|  | Product Type Field | Google Product Category (if available) | Specifies product type data for Facebook. |
|  | Product Image Field | Combination Image (if available) | Ensures correct image for product variations. |
|  | Product Description Field | Description | Uses full product description for the feed. |
|  | Product Short Description Field | Short Description | Uses short product description for the feed. |
|  | CSV Delimiter | Comma (,) | Character separating values in the CSV file. |
|  | Delete images from feed | NO | Includes image links in the feed (essential for ads). |
|  | Exclude Products by ID | Empty | Comma-separated list of product IDs to exclude from the feed. |
|  | Generate Feed Button | Click after settings are finalized | Creates the CSV product catalog file. |
|  | Download Feed Button | Click after generation | Downloads the CSV file to your computer. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My generated feed file is empty or contains very few products.**
A:

- **Check “Export only active products” and “Export only in-stock products”:** Ensure these are not overly restrictive if you expect many products.
- **Check selected Language and Currency:** Make sure products exist for the selected language and have prices in the selected currency.
- **Verify product visibility:** Are your products actually visible in the selected shop context (if you have multi-store enabled)?
- **Clear Smarty Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache.” Sometimes old data can interfere.

**Q: Facebook is rejecting my feed or showing errors.**
A:

- **Check the CSV Delimiter:** Ensure it matches what Facebook expects (usually a comma).
- **Review Facebook’s error messages:** Facebook Business Manager provides detailed error reports. Pay close attention to which fields are causing issues (e.g., missing image links, invalid prices).
- **Verify Image Links:** Ensure your product images are publicly accessible and the URLs are correct. If you have SSL (HTTPS), ensure image links are also HTTPS.
- **Check for special characters:** Sometimes unusual characters in product names or descriptions can cause parsing issues.
- **Ensure unique IDs:** The “Product Identification” setting is crucial. Each item in the feed (especially combinations) needs a unique `id`.

**Q: My product images aren’t showing in the Facebook feed.**
A:

- **Check “Delete images from feed” setting:** Make sure this is set to **NO**.
- **Verify image URLs:** Open a few image links from the generated CSV in your browser. Do they load correctly? Are they accessible from outside your network?
- **Combination Images:** If you’re using combination images, ensure they are correctly assigned to your product combinations in PrestaShop.

**Q: How often should I generate and upload a new feed?**
A:

- It depends on how frequently your product catalog changes.
- **Daily:** Recommended for most stores, especially if you have frequent stock changes, price updates, or new product additions.
- **Weekly:** Acceptable for stores with a very stable catalog.
- **Automated Fetch:** The best practice is to set up Facebook to automatically fetch the feed from a URL. This module generates the feed on demand, so you might need a cron job to trigger the generation and make the file available at a consistent URL for Facebook to fetch.

**Q: The module is not appearing in my Modules list or I can’t configure it.**
A:

- **Re-upload:** Try re-uploading the module ZIP file via the Module Manager.
- **Check permissions:** Ensure the module folder (`/modules/pixelfeed/`) and its contents have correct file permissions (usually 755 for folders, 644 for files).
- **Error Logs:** Check your PrestaShop debug mode and server error logs for any PHP errors during installation or configuration.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview of the “Export catalog for facebook pixel dynamic ads” module for developers and webmasters.

### 4.1 Architecture Overview

The module follows a standard PrestaShop MVC (Model-View-Controller) pattern, primarily focusing on administrative functionality to generate a product feed. It leverages PrestaShop’s core `Product` and `Combination` classes to extract data, then formats this data into a CSV file compatible with Facebook’s Dynamic Ads catalog specification. The main module file (`index.php`) acts as the entry point for configuration, while dedicated admin controllers handle the complex logic of data extraction and feed generation. Front controllers are present, likely for serving the generated feed or for specific AJAX requests.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `controllers/front/feed.php`
  - **Class Name:** `PixelfeedFeedModuleFrontController` (or similar, extending `ModuleFrontController`)
  - **Responsibility:** This controller is likely responsible for serving the generated CSV feed file via a public URL. It would handle requests to a specific route (e.g., `yourstore.com/module/pixelfeed/feed`) and output the CSV content directly. This is crucial for Facebook’s scheduled fetches.
- `controllers/front/index.php`
  - **Class Name:** `PixelfeedIndexModuleFrontController` (or similar, extending `ModuleFrontController`)
  - **Responsibility:** This might be a placeholder or a controller for a very specific, non-feed-related front-office action, though the module’s primary function is back-office feed generation. It could potentially handle AJAX requests related to feed status or other minor interactions.

#### Back-Office Admin Controllers

- `controllers/admin/AdminExportProductsFeed.php`
  - **Class Name:** `AdminExportProductsFeedController` (extending `ModuleAdminController`)
  - **Tab Name:** This controller is the heart of the module’s administrative interface. It’s the main configuration screen where merchants interact with settings and trigger feed generation.
  - **Managed Entity:** It doesn’t directly manage a single `ObjectModel` entity but rather orchestrates the retrieval and processing of `Product` and `Combination` data from PrestaShop’s core.
  - **Key Functionality:**
    - Handles the display of the configuration form (`renderForm`).
    - Processes form submissions (`postProcess`) to save module settings (e.g., language, currency, export options).
    - Triggers the data extraction and CSV generation logic.
    - Manages the exclusion of products.
    - The form fields and columns listed in the module dossier (`ID`, `item_group_id`, `Title`, etc.) represent the *output structure* of the feed, not necessarily direct input fields on the admin form, though many settings influence these output columns.
    - Associated Config Keys: `pf_tree`, `PS_LANG_DEFAULT`, `PS_CURRENCY_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`, `pf_pixelfeed_products`, `pf_remember_settings`, `pf_export_not_group_combinations`, `pf_export_active`, `pf_export_instock`, `pf_export_identification`, `pf_export_category`, `pf_export_manufacturers_default`, `pf_export_type`, `pf_export_img`, `pf_export_manufacturers`, `pf_export_description_what`, `pf_export_short_description_what`, `pf_export_suppliers`, `pf_export_delimiter`, `pf_delete_images`. These are the `Configuration` keys used to store the module’s settings.
- `controllers/admin/index.php`
  - **Class Name:** `PixelfeedAdminIndexController` (or similar, extending `ModuleAdminController`)
  - **Tab Name:** This might be a secondary admin controller, potentially for a dashboard or a simpler management view, or it could be a legacy file. Given the `AdminExportProductsFeedController` handles the main logic, this `index.php` might be a redirect or a very basic landing page within the admin section.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes in the `classes/` directory. This implies that the core logic for data extraction and feed generation is likely contained within the main module file (`pixelfeed/index.php`) and the `AdminExportProductsFeedController`. It directly utilizes PrestaShop’s core `Product`, `Combination`, `Category`, `Manufacturer`, `Image`, and `Tools` classes.

### 4.4 JavaScript Assets (`views/js/`)

- `pixelfeed/lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Back-office.
  - **Functionality:** Likely provides autocomplete functionality for input fields within the admin configuration, such as the “Exclude Products by ID” field. It would bind to input elements, make AJAX calls to search for products, and display suggestions.
- `pixelfeed/views/js/admin-app.js`
  - **Scope:** Back-office.
  - **Functionality:** This is the main JavaScript file for the module’s admin interface. It would handle:
    - Form validation and submission.
    - AJAX requests for generating the feed (to `AdminExportProductsFeedController`).
    - Displaying loading indicators or success/error messages.
    - Potentially dynamic updates to the UI based on selected options.
    - Interactions with Fancybox (if used for category selection or similar).

### 4.5 CSS Stylesheets (`views/css/`)

- `pixelfeed/lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Back-office admin styling.
  - **Functionality:** Styles the autocomplete dropdown and input fields, ensuring a consistent look and feel within the PrestaShop back office.
- `pixelfeed/views/admin-theme.css`
  - **Scope:** Back-office admin styling.
  - **Functionality:** Provides general styling for the module’s configuration page, ensuring it integrates well with the PrestaShop back office theme. This might include layout, button styles, and form element styling.
- `pixelfeed/views/css/admin-app.css`
  - **Scope:** Back-office admin styling.
  - **Functionality:** Specific styling for the module’s custom UI elements, such as the feed generation progress, alerts, or any custom widgets on the configuration page.

### 4.6 Smarty Template Structure (`views/templates/`)

The module primarily uses Smarty templates for its Back Office interface.

#### Admin templates (`views/templates/admin/`)

- `pixelfeed/views/templates/admin/dashboard.tpl`
  - **Purpose:** Could be a dashboard-like overview for the module, potentially showing feed status, last generation date, or quick links.
- `pixelfeed/views/templates/admin/feeds.tpl`
  - **Purpose:** Likely the main template for displaying the feed generation options and results, possibly including a list of generated feeds or a log.
- `pixelfeed/views/templates/admin/form-chrome.tpl`
  - **Purpose:** A generic wrapper or structural template for forms within the admin interface, ensuring consistent layout and styling.
- `pixelfeed/views/templates/admin/layout.tpl`
  - **Purpose:** The overarching layout template for the module’s admin pages, defining the overall structure, header, and footer.

#### Other templates (`views/`)

- `pixelfeed/lib/searchTool/views/scripts.tpl`
  - **Purpose:** Includes JavaScript for the search tool, likely rendered at the end of the HTML body or within a specific section.
- `pixelfeed/views/categories-fancybox.tpl`
  - **Purpose:** Template for a Fancybox modal, possibly used for selecting categories to include/exclude from the feed, or for displaying category trees.
- `pixelfeed/views/exclude-products.tpl`
  - **Purpose:** Template for the section where products can be excluded by ID, potentially including the autocomplete input field.
- `pixelfeed/views/google_lang_links.tpl`
  - **Purpose:** Might be related to displaying language-specific links or information, possibly for Google Product Categories.
- `pixelfeed/views/returnAlert.tpl`
  - **Purpose:** A template for displaying success, error, or warning messages to the user in the admin interface.
- `pixelfeed/views/script-fancybox.tpl`
  - **Purpose:** Includes JavaScript for Fancybox integration, often for modal popups.
- `pixelfeed/views/script.tpl`
  - **Purpose:** General JavaScript inclusions for the module’s admin pages, potentially for global variables or initializations.

### 4.7 Database Schema & Hooks Map

#### Database Tables

The module dossier indicates no custom SQL files, suggesting it does not create its own dedicated database tables. All configuration settings are stored in PrestaShop’s `ps_configuration` table using keys prefixed with `pf_` (e.g., `pf_export_active`, `pf_export_delimiter`).

#### Registered Hooks Table

The module’s primary function is data export, not front-office display. The listed front-office hooks (Header, Columns, Product, Footer) are likely *not* used for direct visual output by this module. Instead, they might be registered for:

- **`displayHeader`**: To include necessary JavaScript or CSS assets for the module’s front-office feed controller (if it serves the feed directly).
- **`action*` hooks**: The module likely uses `action` hooks (e.g., `actionProductUpdate`, `actionProductAdd`) internally to clear caches or trigger re-generation prompts in the back office when product data changes, though these are not explicitly listed in the dossier. The module’s core logic for generating the feed is typically triggered manually or via a cron job, not directly by a front-office hook.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of front-office pages. | Potentially to load JS/CSS for front-office feed serving, or for very specific, non-visual integrations. |
| `displayRightColumn` / `displayLeftColumn` | In the side columns of front-office pages. | Unlikely to be used for this module’s core function; possibly for a debug block or a very niche feature not central to feed generation. |
| `displayProductAdditionalInfo` / `displayProductButtons` (Product page) | On product pages. | Unlikely to be used for this module’s core function. |
| `displayFooter` | In the footer of front-office pages. | Unlikely to be used for this module’s core function. |
| (Implicit) `actionProductUpdate` / `actionProductAdd` / `actionProductDelete` | After product data changes in BO. | To invalidate cached feed data or prompt admin for feed re-generation. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Export catalog for facebook pixel dynamic ads” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and integration.
