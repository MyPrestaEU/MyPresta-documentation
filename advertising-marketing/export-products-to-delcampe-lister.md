---
title: "Export products to Delcampe Lister - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Export products to Delcampe Lister PrestaShop module by MyPresta.eu."
sidebar:
  label: "Export products to Delcampe Lister - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Export products to Delcampe Lister Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/export-products-to-delcampe-lister.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/export-products-to-delcampe-lister/)
>
> ---


# Export products to Delcampe Lister

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop to function correctly and should be available on most hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

You can access this screen by navigating to **Modules > Module Manager** and clicking “Configure” next to “Export products to Delcampe Lister”.

This screen primarily handles the general settings for the module, including update checks.

- **MyPresta.eu Live Update Check:**
  - **What this setting does:** This option controls whether the module automatically checks for new versions and updates available from MyPresta.eu.
  - **Effect of changing this setting:**
    - *When enabled:* The module will periodically connect to MyPresta.eu to see if a newer version is available. This helps you stay up-to-date with bug fixes and new features.
    - *When disabled:* The module will not check for updates automatically. You would need to manually check for updates in your MyPresta.eu account.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Keeping this enabled ensures you’re always running the most stable and feature-rich version of the module without needing to remember to check manually.

### 2.2 Dedicated Admin Screens & Controller Views

#### 2.2.1 Delcampe Products Management (Back Office > Catalog > Delcampe Products)

This is the main management screen for your Delcampe product exports. You can access it by navigating to **Catalog > Delcampe Products** in your PrestaShop Back Office menu.

This screen provides a grid view of your products and allows you to manage their export settings for Delcampe. You can add new products to the export list, edit existing ones, and generate the export file.

**Available Actions & Settings:**

- **Product Listing Table:** This table displays all products that are either already configured for Delcampe export or available to be configured. You’ll see columns like product ID, name, and potentially their Delcampe-specific settings.
- **Add New Product / Edit Product:**
  - Clicking “Add New” or editing an existing product will open a form where you can define specific Delcampe listing parameters for that product.
  - **`category_id` (Delcampe Category ID):**
    - **What this setting does:** This is the specific category ID on Delcampe where your product will be listed. Delcampe has its own category structure, which may differ from PrestaShop’s.
    - **Effect of changing this setting:** Incorrect category IDs will result in your product being listed in the wrong section on Delcampe, or potentially failing to list.
    - **Recommended value:** The exact numerical ID of the target Delcampe category.
    - **Merchant scenario / example:** If you’re selling a rare stamp, you’d find the appropriate “Stamps” category ID on Delcampe and enter it here.
  - **`title` (Delcampe Listing Title):**
    - **What this setting does:** The title that will appear for your product on Delcampe. This can be different from your PrestaShop product name.
    - **Effect of changing this setting:** A compelling and keyword-rich title can significantly improve visibility on Delcampe.
    - **Recommended value:** A descriptive, concise title optimized for Delcampe searches.
    - **Merchant scenario / example:** Instead of “Old Stamp,” you might use “Rare 1920 French Stamp - Unused - Excellent Condition.”
  - **`description` (Delcampe Listing Description):**
    - **What this setting does:** The detailed product description that will be displayed on your Delcampe listing.
    - **Effect of changing this setting:** A thorough description with all relevant details helps buyers make informed decisions and builds trust.
    - **Recommended value:** A comprehensive description, potentially including historical context, condition, and dimensions.
    - **Merchant scenario / example:** Copy your PrestaShop description, but consider adding Delcampe-specific details or formatting.
  - **`personal_reference` (Your Internal Reference):**
    - **What this setting does:** An optional field for your own internal tracking or reference number for the product on Delcampe.
    - **Effect of changing this setting:** Helps you match Delcampe sales back to your internal inventory system.
    - **Recommended value:** Your PrestaShop product reference or SKU.
    - **Merchant scenario / example:** Using your PrestaShop SKU here allows you to quickly identify the product in your store when a Delcampe order comes in.
  - **`currency` (Listing Currency):**
    - **What this setting does:** The currency in which the product will be listed on Delcampe.
    - **Effect of changing this setting:** Must match a currency supported by Delcampe.
    - **Recommended value:** Your primary selling currency (e.g., EUR, USD).
    - **Merchant scenario / example:** If you primarily sell in Euros, set this to EUR.
  - **`selling_type` (Delcampe Selling Type):**
    - **What this setting does:** Defines how the product is sold on Delcampe (e.g., auction, fixed price).
    - **Effect of changing this setting:** Determines the buying process for customers on Delcampe.
    - **Recommended value:** Choose the type that best suits your product and sales strategy (e.g., “Fixed Price” for standard items, “Auction” for rare items).
    - **Merchant scenario / example:** For a common collectible, “Fixed Price” might be suitable. For a truly unique item, an “Auction” could drive higher bids.
  - **`price` (Starting Price / Fixed Price):**
    - **What this setting does:** The initial price for an auction or the fixed price for a direct sale.
    - **Effect of changing this setting:** Directly impacts the cost for the buyer.
    - **Recommended value:** Your desired selling price.
    - **Merchant scenario / example:** For a fixed-price item, this would be your retail price. For an auction, it’s the minimum bid.
  - **`initial_quantity` (Quantity Available):**
    - **What this setting does:** The number of units of this product you are making available on Delcampe.
    - **Effect of changing this setting:** Determines how many items a buyer can purchase.
    - **Recommended value:** Your current stock level for the product.
    - **Merchant scenario / example:** If you have 5 of a particular stamp, set this to 5.
  - **`minimum_bid_step` (Auction Bid Increment):**
    - **What this setting does:** For auction-style listings, this defines the minimum amount by which a bid must increase.
    - **Effect of changing this setting:** Influences bidding behavior.
    - **Recommended value:** A reasonable increment (e.g., 0.50, 1.00).
    - **Merchant scenario / example:** If set to 1.00, a bid of 10.00 would require the next bid to be at least 11.00.
  - **`renew_duration` (Auto-Renew Duration):**
    - **What this setting does:** If enabled, this specifies how long an unsold listing will be automatically renewed for.
    - **Effect of changing this setting:** Keeps your product listed on Delcampe without manual intervention.
    - **Recommended value:** A duration that aligns with your sales cycle (e.g., 7 days, 14 days).
    - **Merchant scenario / example:** If an item doesn’t sell in 7 days, it will automatically relist for another 7 days.
  - **`renew_total_count` (Auto-Renew Limit):**
    - **What this setting does:** The maximum number of times an unsold listing will be automatically renewed.
    - **Effect of changing this setting:** Prevents indefinite relisting of unpopular items.
    - **Recommended value:** A reasonable limit (e.g., 3, 5).
    - **Merchant scenario / example:** If an item fails to sell after 3 renewals, it will be removed from Delcampe.
  - **`shipping_model` (Delcampe Shipping Model):**
    - **What this setting does:** The shipping method or model you use on Delcampe. This needs to correspond to your pre-configured shipping settings on Delcampe.
    - **Effect of changing this setting:** Determines how shipping costs are calculated and presented to the buyer.
    - **Recommended value:** The ID or name of your preferred Delcampe shipping model.
    - **Merchant scenario / example:** If you have a “Standard International Shipping” model set up on Delcampe, you’d enter its identifier here.
  - **`weight` (Product Weight):**
    - **What this setting does:** The weight of the product, used for shipping calculations on Delcampe.
    - **Effect of changing this setting:** Crucial for accurate shipping cost estimation.
    - **Recommended value:** The actual weight of the product.
    - **Merchant scenario / example:** Enter “0.1” for a lightweight stamp.
  - **`lister_sale_end_time` (Sale End Time):**
    - **What this setting does:** The specific time of day when the listing will end.
    - **Effect of changing this setting:** Allows you to schedule the end of your listings.
    - **Recommended value:** A time when your target audience is most likely to be online (e.g., 20:00).
    - **Merchant scenario / example:** Ending an auction at 8 PM on a Sunday might attract more last-minute bids.
  - **`lister_sale_end_day` (Sale End Day):**
    - **What this setting does:** The specific day of the week when the listing will end.
    - **Effect of changing this setting:** Allows you to schedule the end of your listings.
    - **Recommended value:** A day when your target audience is most likely to be online (e.g., Sunday).
    - **Merchant scenario / example:** Ending an auction on a Sunday might attract more last-minute bids.
  - **`option_last_minute_extension` (Last Minute Extension):**
    - **What this setting does:** If enabled, extends the auction duration if a bid is placed in the final minutes.
    - **Effect of changing this setting:** Prevents “sniping” and encourages higher bids.
    - **Recommended value:** YES (for auctions).
    - **Merchant scenario / example:** A bid placed 30 seconds before an auction ends will extend the auction by a few minutes, giving others a chance to counter.
  - **`option_anonymous_buyer` (Anonymous Buyer):**
    - **What this setting does:** Hides the buyer’s identity from other bidders in an auction.
    - **Effect of changing this setting:** Can increase privacy for bidders.
    - **Recommended value:** NO (unless specific privacy concerns are paramount).
    - **Merchant scenario / example:** If you want to protect buyer privacy, enable this.
  - **`option_strong_title` (Strong Title / Bold Title):**
    - **What this setting does:** Makes your listing title bold on Delcampe, increasing its visibility.
    - **Effect of changing this setting:** Your listing stands out more in search results.
    - **Recommended value:** YES.
    - **Merchant scenario / example:** Using a bold title helps your rare stamp listing catch the eye of collectors browsing many similar items.
  - **`option_background_color` (Background Color):**
    - **What this setting does:** Sets a custom background color for your listing on Delcampe.
    - **Effect of changing this setting:** Can make your listing more visually appealing or match your brand.
    - **Recommended value:** Leave empty or use a subtle color.
    - **Merchant scenario / example:** Using a light blue background might make your listing pop without being distracting.
  - **`option_border_color` (Border Color):**
    - **What this setting does:** Sets a custom border color for your listing on Delcampe.
    - **Effect of changing this setting:** Can make your listing more visually appealing or match your brand.
    - **Recommended value:** Leave empty or use a subtle color.
    - **Merchant scenario / example:** A thin, dark border can give your listing a more professional look.

**Recommended workflow for daily store management:**

1. **Identify Products for Delcampe:** Decide which of your PrestaShop products are suitable for the Delcampe marketplace.
2. **Add/Edit Products:** Go to **Catalog > Delcampe Products**. Use the “Add New” button or edit existing entries to configure the Delcampe-specific settings for each product. Pay close attention to Delcampe category IDs, pricing, and selling type.
3. **Generate Export:** Once your products are configured, the module will allow you to generate the export file. This file will contain all the necessary data in a format that Delcampe Lister can import.
4. **Import to Delcampe Lister:** Download the generated file and import it into your Delcampe Lister tool.
5. **Monitor & Update:** Keep an eye on your Delcampe listings and update product configurations in PrestaShop as needed (e.g., for price changes, stock updates).

#### 2.2.2 AdminDelcampeProductsController (delcampeproducts/controllers/admin/AdminDelcampeProducts.php)

This controller is responsible for managing the Delcampe product listings within the PrestaShop back office. It handles the display of the product list, as well as the creation, editing, and deletion of individual Delcampe product configurations.

#### 2.2.3 index.php (delcampeproducts/controllers/admin/index.php)

This file likely serves as a placeholder or a simple redirect within the admin controller structure, ensuring that the module’s admin section is properly initialized or routed. It typically doesn’t contain direct configuration options for the merchant.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | MyPresta.eu Live Update Check | YES | Controls automatic checks for module updates. |
| Delcampe Products Management | Delcampe Category ID (`category_id`) | (Specific Delcampe ID) | Maps PrestaShop product to a Delcampe category. |
| Delcampe Products Management | Delcampe Listing Title (`title`) | (Custom) | Product title displayed on Delcampe. |
| Delcampe Products Management | Delcampe Listing Description (`description`) | (Custom) | Detailed product description for Delcampe. |
| Delcampe Products Management | Your Internal Reference (`personal_reference`) | (PrestaShop SKU) | Internal tracking for your products. |
| Delcampe Products Management | Listing Currency (`currency`) | (Your primary currency) | Currency for the Delcampe listing. |
| Delcampe Products Management | Delcampe Selling Type (`selling_type`) | (Fixed Price / Auction) | How the product is sold on Delcampe. |
| Delcampe Products Management | Starting Price / Fixed Price (`price`) | (Your desired price) | Price for direct sale or auction start. |
| Delcampe Products Management | Quantity Available (`initial_quantity`) | (Your stock level) | Number of units available on Delcampe. |
| Delcampe Products Management | Auction Bid Increment (`minimum_bid_step`) | (e.g., 0.50, 1.00) | Minimum amount bids must increase by. |
| Delcampe Products Management | Auto-Renew Duration (`renew_duration`) | (e.g., 7 days) | How long an unsold listing renews for. |
| Delcampe Products Management | Auto-Renew Limit (`renew_total_count`) | (e.g., 3, 5) | Max times an unsold listing will auto-renew. |
| Delcampe Products Management | Delcampe Shipping Model (`shipping_model`) | (Delcampe Model ID/Name) | Shipping method used on Delcampe. |
| Delcampe Products Management | Product Weight (`weight`) | (Actual product weight) | Product weight for shipping calculations. |
| Delcampe Products Management | Sale End Time (`lister_sale_end_time`) | (e.g., 20:00) | Specific time of day for listing end. |
| Delcampe Products Management | Sale End Day (`lister_sale_end_day`) | (e.g., Sunday) | Specific day of the week for listing end. |
| Delcampe Products Management | Last Minute Extension (`option_last_minute_extension`) | YES (for auctions) | Extends auction if bid placed in final minutes. |
| Delcampe Products Management | Anonymous Buyer (`option_anonymous_buyer`) | NO | Hides buyer identity in auctions. |
| Delcampe Products Management | Strong Title / Bold Title (`option_strong_title`) | YES | Makes listing title bold on Delcampe. |
| Delcampe Products Management | Background Color (`option_background_color`) | (Leave empty or subtle) | Custom background color for listing. |
| Delcampe Products Management | Border Color (`option_border_color`) | (Leave empty or subtle) | Custom border color for listing. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My products aren’t showing up on Delcampe after export. What should I check?**
A:

1. **Did you complete the import on Delcampe Lister?** This module only *exports* the data. You still need to download the generated file and *import* it into your Delcampe Lister tool.
2. **Check Delcampe Category IDs:** Ensure the `category_id` you entered for each product is correct and exists on Delcampe. Incorrect IDs can cause import failures.
3. **Review Delcampe Lister Errors:** When you import the file into Delcampe Lister, it usually provides feedback or error messages if something went wrong. Check these messages for clues.
4. **Product Status:** Ensure the products are active and in stock in your PrestaShop store if you’ve configured the module to only export active/in-stock items.

**Q: How do I handle product updates (price changes, stock changes) on Delcampe?**
A: You will need to re-export and re-import the updated product data into Delcampe Lister. The module generates a fresh export file based on your current PrestaShop product data and the Delcampe-specific settings you’ve configured. Delcampe Lister typically handles updates to existing listings when you import a file with matching product identifiers.

**Q: The export file seems empty or incomplete.**
A:

1. **Product Configuration:** Double-check that you have actually configured products for Delcampe export under **Catalog > Delcampe Products**. If no products are configured, the export will be empty.
2. **Module Settings:** Review any general module settings (if present) that might filter products, such as “export only active products” or “export only in-stock products.”
3. **PrestaShop Cache:** Sometimes, clearing your PrestaShop cache (**Advanced Parameters > Performance > Clear cache**) can resolve unexpected behavior with data generation.

**Q: My custom theme is causing display issues in the module’s back-office configuration.**
A: This module’s back-office interface uses standard PrestaShop components, so it should generally be compatible. If you encounter styling issues, it’s likely a conflict with your custom theme’s back-office overrides.

1. **Check for Overrides:** If your theme has an `admin` folder with template overrides, temporarily rename it to see if the issue resolves.
2. **Contact Theme Developer:** If the issue persists, contact your theme developer for assistance, as they may need to adjust their CSS to accommodate standard module interfaces.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Export products to Delcampe Lister” module follows a standard PrestaShop module architecture, primarily leveraging Admin Controllers for its back-office interface and data management. It does not heavily rely on front-office components for direct customer interaction but uses hooks to integrate into the PrestaShop lifecycle. The core functionality revolves around managing product-specific Delcampe export settings and generating a data feed for the Delcampe Lister tool.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `controllers/front/feed.php`
    - **Class name & parent class**: `DelcampeproductsFeedModuleFrontController` extending `ModuleFrontController`.
    - **Responsibility**: This controller is likely responsible for generating the actual Delcampe product feed (e.g., XML, CSV) that the merchant would download. It would query the configured products and format their data according to Delcampe’s specifications. It responds to a specific front-office route, though it’s not directly visible to the end-user browsing the shop.
  - `controllers/front/index.php`
    - **Class name & parent class**: `DelcampeproductsIndexModuleFrontController` extending `ModuleFrontController`.
    - **Responsibility**: This might serve as a default or fallback front controller, or it could be used for simple redirection. In many modules, if `feed.php` handles the primary front-office interaction (generating the feed), `index.php` might be minimal or unused.
- **Back-Office Admin Controllers**:

  - `controllers/admin/AdminDelcampeProducts.php`
    - **Class name & parent class**: `AdminDelcampeProductsController` extending `ModuleAdminController`.
    - **Tab name and managed entity**: This controller manages the “Delcampe Products” section under the “Catalog” menu in the PrestaShop Back Office. It’s responsible for listing, adding, editing, and deleting the Delcampe-specific configuration for each product. It uses PrestaShop’s `HelperList` and `HelperForm` to display the product grid and the detailed configuration form.
  - `controllers/admin/index.php`
    - **Class name & parent class**: Not a full controller class, typically a simple `index.php` file to prevent directory listing or to include the main module file for context. It does not define a distinct Admin Controller class.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes in the `classes/` directory. This suggests that the module might store its custom product export settings directly in the `ps_configuration` table or extend existing PrestaShop `ObjectModel` classes (like `Product`) dynamically, or use a more direct database interaction within the controller. Given the detailed form fields, it’s highly probable that product-specific Delcampe settings are stored in `ps_configuration` with keys like `dp_export_categories` or directly within the `AdminDelcampeProductsController`’s logic.

### 4.4 JavaScript Assets (`views/js/`)

- `delcampeproducts/lib/js/admin/delcampeproducts.js`
  - **Scope**: Back-office.
  - **Details**: This script is loaded in the PrestaShop Back Office, specifically for the `AdminDelcampeProducts` controller. It likely handles:
    - Dynamic form behavior (e.g., showing/hiding fields based on `selling_type`).
    - AJAX calls for saving settings or generating the export file.
    - Input validation or formatting for fields like `category_id`, `price`, `weight`.
    - Any interactive elements within the product configuration forms or the listing grid.
    - Potentially uses jQuery for DOM manipulation and event handling.

### 4.5 CSS Stylesheets (`views/css/`)

The module dossier indicates no custom CSS files. This implies that the module relies entirely on PrestaShop’s default Back Office styling for its configuration forms and lists, ensuring a consistent look and feel with the rest of the admin panel. Developers looking to style the module’s admin interface would need to target existing PrestaShop CSS classes or inject custom CSS via `actionAdminControllerSetMedia` hook.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**: None explicitly listed, but modules often use `displayAdminProductsExtra` or similar for product page tabs.
- **Admin templates (`views/templates/admin/`)**:
  - `delcampeproducts/script.tpl`
    - **Scope**: Back-office.
    - **Details**: This template is likely used to output JavaScript variables or inline scripts that are needed by `delcampeproducts.js`. It might pass configuration values from PHP to JavaScript, or define global JS objects. It’s often rendered via the `actionAdminControllerSetMedia` hook.
- **Front-office templates (`views/templates/front/`)**: None explicitly listed, which aligns with the module’s background export nature.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module likely stores its configuration settings in the `ps_configuration` table using keys such as `dp_export_categories`, `dp_remember_settings`, `dp_option_homepage_promotion`, `dp_lister_status`, `dp_lister_creation_date`, `dp_lister_sending_date`, `dp_llister_sending_date`, `dp_lister_edit_date`, `dp_export_format`, `dp_export_active`, `dp_export_instock`, `dp_export_identification`, `dp_export_category`, `dp_export_manufacturers_default`.
  - For product-specific Delcampe settings (like `category_id`, `title`, `price`, etc.), given no custom `ObjectModel` is listed, these are likely stored either as serialized data within `ps_configuration` (less ideal for per-product settings) or, more likely, the `AdminDelcampeProductsController` directly manages a custom database table (e.g., `ps_delcampe_product_settings`) which was not explicitly identified in the dossier but would be a standard approach for such detailed per-product data. If no custom table exists, it might be using `Product::addFeature` or `Product::addCustomization` in a non-standard way, or storing data in `ps_product_lang` or `ps_product_shop` through overrides. **(Developer Note: Investigate database for `ps_delcampe_product_settings` or similar table upon installation.)**
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionProductUpdate` | After a product is updated in the Back Office. | Allows the module to react to product changes (e.g., update its internal Delcampe export data, mark a product for re-export). |
| `actionAdminControllerSetMedia` | When an admin controller is loaded and its media (JS/CSS) are being set. | Used to inject the module’s custom JavaScript (`delcampeproducts.js`) and potentially inline scripts (`script.tpl`) into the Back Office pages, especially for the `AdminDelcampeProducts` controller. |
| `displayAdminProductsExtra` | (Implicit, often used for product tabs) | If the module adds a tab to the product edit page for Delcampe settings, this hook would be used. (Not explicitly listed as a hook, but common for such functionality). |
| `displayBackOfficeHeader` | In the header of every Back Office page. | Can be used for global admin-side JS/CSS or for displaying notifications. |
| `moduleRoutes` | During route generation for the module. | Used to define custom front-office URLs for controllers like `feed.php`. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and comprehensive support for the “Export products to Delcampe Lister” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our dedicated support team is available to assist you with any technical issues or questions regarding the module’s functionality.
