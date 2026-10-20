---
title: "TikTok Catalog Feed - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the TikTok Catalog Feed PrestaShop module by MyPresta.eu."
sidebar:
  label: "TikTok Catalog Feed - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy TikTok Catalog Feed Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/tiktok-catalog-feed.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/tiktok-catalog-feed/)
>
> ---


# TikTok Catalog Feed

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. Ensure your server can handle generating potentially large XML/CSV files if you have a very extensive catalog.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The TikTok Catalog Feed module provides a dedicated section in your PrestaShop Back Office for managing your product feeds.

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This initial configuration screen allows you to set up the basic parameters for your TikTok feed.

- **Enable Module:**

  - **What this setting does:** This is the master switch to activate or deactivate the module’s functionality.
  - **Effect of changing this setting:**
    - *When enabled:* The module will be active, allowing you to generate and manage TikTok product feeds.
    - *When disabled:* The module will cease to function, and no feeds can be generated or accessed.
  - **Recommended value:** YES
  - **Merchant scenario / example:** You would enable this when you are ready to start using TikTok Ads. You might disable it temporarily if you need to perform maintenance or stop your TikTok ad campaigns.
- **Feed Generation Type:**

  - **What this setting does:** Determines whether the module generates a CSV (Comma Separated Values) or XML (Extensible Markup Language) file for your product feed. TikTok generally supports both.
  - **Effect of changing this setting:**
    - *When set to CSV:* The generated feed URL will provide a CSV file.
    - *When set to XML:* The generated feed URL will provide an XML file.
  - **Recommended value:** XML (often preferred for its structured nature, but CSV works equally well for TikTok).
  - **Merchant scenario / example:** If TikTok’s documentation or your ad agency recommends a specific format, choose that. Otherwise, either works.
- **Default Language for Feed:**

  - **What this setting does:** Selects the primary language for the product data in your feed. This is crucial for targeting specific markets on TikTok.
  - **Effect of changing this setting:** The product titles, descriptions, and other language-dependent fields in the feed will be pulled from your PrestaShop store in the chosen language.
  - **Recommended value:** The language of your primary target audience on TikTok (e.g., English for a US market, French for a French market).
  - **Merchant scenario / example:** If you’re targeting customers in Germany, you would select “German” here to ensure your product information is displayed correctly in their language on TikTok.
- **Default Currency for Feed:**

  - **What this setting does:** Selects the currency used for all product prices in your feed. This should match the currency of your target market.
  - **Effect of changing this setting:** All prices in the feed will be converted to or displayed in the selected currency.
  - **Recommended value:** The currency of your primary target audience on TikTok (e.g., USD for a US market, EUR for a European market).
  - **Merchant scenario / example:** If your TikTok ads are targeting customers in the UK, you would select “GBP” to ensure prices are shown in British Pounds.
- **Default Country for Shipping:**

  - **What this setting does:** Sets the default country used for calculating shipping costs and availability in the feed. This is important for TikTok to understand where your products can be shipped.
  - **Effect of changing this setting:** The shipping information in the feed will be based on the selected country’s shipping rules configured in your PrestaShop store.
  - **Recommended value:** Your primary shipping destination country.
  - **Merchant scenario / example:** If most of your sales are within France, you would select “France” here.
- **Include Out-of-Stock Products:**

  - **What this setting does:** Determines whether products currently marked as “out of stock” in your PrestaShop store should be included in the TikTok feed.
  - **Effect of changing this setting:**
    - *When enabled:* Out-of-stock products will appear in the feed, typically with an “unavailable” status.
    - *When disabled:* Out-of-stock products will be excluded from the feed entirely.
  - **Recommended value:** NO (unless you have a specific strategy for pre-orders or back-in-stock notifications).
  - **Merchant scenario / example:** Generally, you want to show only available products in your ads to avoid customer frustration. If you have a long lead time for custom products, you might include them but mark them as “preorder.”
- **Exclude Specific Categories:**

  - **What this setting does:** Allows you to select specific product categories from your PrestaShop store that you do NOT want to appear in the TikTok feed.
  - **Effect of changing this setting:** Products belonging to the selected categories will be omitted from the generated feed.
  - **Recommended value:** Depends on your store.
  - **Merchant scenario / example:** You might exclude categories like “Gift Cards” or “Services” if they are not physical products suitable for TikTok Catalog Ads. Or, if you have a B2B-only category, you’d exclude it from consumer-facing ads.
- **Exclude Specific Products:**

  - **What this setting does:** Provides a way to manually select individual products that should be excluded from the TikTok feed, regardless of their category.
  - **Effect of changing this setting:** The selected products will not be included in the feed.
  - **Recommended value:** Depends on your store.
  - **Merchant scenario / example:** You might exclude a product that is part of a limited-time flash sale that you don’t want advertised on TikTok, or a product that has legal restrictions for advertising in certain regions.
- **Use Product Short Description:**

  - **What this setting does:** Determines whether the short description or the full description of your products is used in the TikTok feed.
  - **Effect of changing this setting:**
    - *When enabled:* The shorter, more concise product description will be used.
    - *When disabled:* The longer, full product description will be used.
  - **Recommended value:** YES (short descriptions are often better for ads, as users have limited attention spans).
  - **Merchant scenario / example:** TikTok ads benefit from concise information. Using the short description ensures your ad copy is punchy and to the point.
- **Export Product Features as Attributes:**

  - **What this setting does:** If enabled, your PrestaShop product features (like “Material,” “Color,” “Size”) will be exported as additional attributes in the TikTok feed, providing more detailed product information.
  - **Effect of changing this setting:** More detailed product information will be available to TikTok for better ad targeting and display.
  - **Recommended value:** YES
  - **Merchant scenario / example:** If you sell clothing, exporting “Color” and “Size” as attributes allows TikTok to show more specific ads (e.g., “Red Dress, Size M”).
- **Export Product Combinations (Variants):**

  - **What this setting does:** Crucial for stores with products that have variations (e.g., a T-shirt available in different sizes and colors). This setting ensures each unique combination is exported as a separate item in the feed.
  - **Effect of changing this setting:** Each product variant will have its own entry in the feed, with its specific price, stock, and image, allowing TikTok to display the exact variant advertised.
  - **Recommended value:** YES (almost always, unless you only sell simple products with no variations).
  - **Merchant scenario / example:** If you sell a shoe available in sizes 7, 8, and 9, enabling this ensures TikTok sees three distinct products, each with its own SKU and availability.
- **Export Size Attribute:**

  - **What this setting does:** Specifically for products with combinations, this setting ensures that the “size” attribute of each combination is explicitly included in the feed, which is important for apparel and footwear.
  - **Effect of changing this setting:** The size of each product variant will be clearly listed in the feed.
  - **Recommended value:** YES (especially for fashion, footwear, or any size-dependent products).
  - **Merchant scenario / example:** For a clothing store, this ensures that a “Large Blue T-shirt” is correctly identified by TikTok, not just a “Blue T-shirt.”
- **Export Availability Date:**

  - **What this setting does:** Includes the “available for order” date for products, which is useful for pre-order items or products with future release dates.
  - **Effect of changing this setting:** TikTok will receive information about when a product will become available.
  - **Recommended value:** YES (if you use this feature in PrestaShop).
  - **Merchant scenario / example:** If you’re launching a new product next month, this allows TikTok to show “pre-order” ads with the correct availability date.
- **Google Product Category Mapping:**

  - **What this setting does:** TikTok often leverages Google’s extensive product taxonomy. This section allows you to map your PrestaShop categories to the most relevant Google Product Categories. This improves ad relevance and targeting.
  - **Effect of changing this setting:** Your products will be correctly categorized according to Google’s taxonomy in the feed, which TikTok uses for better understanding and targeting.
  - **Recommended value:** Map as many categories as possible.
  - **Merchant scenario / example:** If you have a PrestaShop category “Summer Dresses,” you would map it to a Google Product Category like “Apparel & Accessories > Clothing > Dresses.”
- **Generate Feed URL:**

  - **What this setting does:** After configuring all settings, this button generates the unique URL for your TikTok product feed. This URL is what you will provide to TikTok Ads Manager.
  - **Effect of changing this setting:** Clicking this will display the URL. The feed at this URL will reflect all your chosen settings.
  - **Recommended value:** Click this after all other settings are finalized.
  - **Merchant scenario / example:** Once you’ve set up everything, click this, copy the URL, and paste it into your TikTok Ads Manager when setting up your Catalog.

### 2.2 Dedicated Admin Screens & Controller Views

The module provides a dedicated section in your PrestaShop Back Office for managing and generating your TikTok product feeds.

**Screen Name & Menu Location:**
You can access this section via the main PrestaShop menu: **Catalog > TikTok Feed**.

This section typically presents a dashboard or a list of generated feeds, allowing you to manage different feed configurations if the module supports multiple feeds (e.g., for different languages or currencies).

#### 2.2.1 TikTok Feed Dashboard (Back Office > Catalog > TikTok Feed)

This is the main entry point for managing your TikTok feeds.

- **Available Actions & Settings:**

  - **List of Feeds:** You will see a table or list of all your configured TikTok feeds. Each entry will typically show:
    - **Feed Name:** A descriptive name for your feed (e.g., “English US Feed,” “French EU Feed”).
    - **Language:** The language of the products in this feed.
    - **Currency:** The currency of the prices in this feed.
    - **Last Generated:** The timestamp of when the feed was last updated.
    - **Feed URL:** The direct link to the generated feed file (CSV or XML).
    - **Actions:** Buttons to “Edit,” “Generate Now,” or “Delete” the feed.
  - **“Add New Feed” Button:** Allows you to create a new feed configuration, potentially for a different language, currency, or set of product exclusions.
  - **“Generate All Feeds” Button:** A convenient option to refresh all your configured feeds at once.
- **Effect of changes:**

  - **Adding a New Feed:** Creates a new configuration instance, allowing you to define a separate set of rules (language, currency, exclusions) for a distinct TikTok feed. This is useful for multi-country or multi-language stores.
  - **Editing a Feed:** Takes you to a configuration form (similar to the main module configuration, but specific to this feed instance) where you can adjust its settings.
  - **Generating a Feed:** Triggers the module to process your product catalog based on the feed’s settings and create/update the feed file at its unique URL. This is crucial for ensuring TikTok always has the most up-to-date product information.
  - **Deleting a Feed:** Removes the feed configuration and its associated generated file.
- **Recommended workflow for daily store management:**

  1. **Initial Setup:** Create at least one feed for your primary target market (e.g., English, USD).
  2. **Multi-Market Setup:** If you target multiple countries or languages, create a separate feed for each, configuring the language, currency, and country settings appropriately.
  3. **Regular Generation:** TikTok typically pulls feeds on a schedule (e.g., daily). You can manually click “Generate Now” if you’ve made significant product changes (new products, price updates, stock changes) and want TikTok to reflect them immediately. Otherwise, the module often has an automatic generation mechanism or cron job setup (see Developer section).
  4. **Monitor Feed Health:** Regularly check your TikTok Ads Manager for any feed errors or warnings. If issues arise, review your module settings and regenerate the feed.

#### 2.2.2 Feed Configuration Form (Accessed via “Add New Feed” or “Edit” a feed)

This screen is where you define the specific parameters for an individual TikTok product feed. It mirrors many of the settings found on the main module configuration page but applies them to a single feed instance.

- **Form Fields & Columns:**

  - **Feed Name:** A unique, descriptive name for this specific feed (e.g., “US English Catalog,” “DE German Catalog”).
  - **Language:** Select the language for this feed.
  - **Currency:** Select the currency for this feed.
  - **Country:** Select the default country for shipping for this feed.
  - **Include Out-of-Stock Products:** (Same as above, but specific to this feed).
  - **Exclude Specific Categories:** (Same as above, but specific to this feed).
  - **Exclude Specific Products:** (Same as above, but specific to this feed).
  - **Use Product Short Description:** (Same as above, but specific to this feed).
  - **Export Product Features as Attributes:** (Same as above, but specific to this feed).
  - **Export Product Combinations (Variants):** (Same as above, but specific to this feed).
  - **Export Size Attribute:** (Same as above, but specific to this feed).
  - **Export Availability Date:** (Same as above, but specific to this feed).
  - **Google Product Category Mapping:** (Same as above, but specific to this feed).
- **Effect of changes:** Saving changes on this form updates the configuration for the specific feed you are editing. You will then need to “Generate Now” for that feed to apply the changes to the actual feed file.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration Page** | Enable Module | YES | Activates/deactivates module functionality. |
|  | Feed Generation Type | XML | Choose CSV or XML format for the feed. |
|  | Default Language for Feed | Primary Store Language | Sets the language for product data. |
|  | Default Currency for Feed | Primary Store Currency | Sets the currency for product prices. |
|  | Default Country for Shipping | Primary Shipping Country | Sets the default country for shipping info. |
|  | Include Out-of-Stock Products | NO | Excludes out-of-stock items from the feed. |
|  | Exclude Specific Categories | (None) | Omits products from selected categories. |
|  | Exclude Specific Products | (None) | Omits specific products from the feed. |
|  | Use Product Short Description | YES | Uses short descriptions for conciseness. |
|  | Export Product Features as Attributes | YES | Includes product features as attributes. |
|  | Export Product Combinations (Variants) | YES | Exports each product variant as a separate item. |
|  | Export Size Attribute | YES | Includes size attribute for variants. |
|  | Export Availability Date | YES | Includes product availability date. |
|  | Google Product Category Mapping | Map all relevant | Maps PrestaShop categories to Google’s taxonomy for TikTok. |
|  | Generate Feed URL | Click after setup | Creates/updates the unique URL for the feed. |
| **TikTok Feed Dashboard** | Add New Feed | N/A | Creates a new, separate feed configuration. |
|  | Edit Feed | N/A | Modifies settings for an existing feed. |
|  | Generate Now (for a specific feed) | N/A | Manually updates a single feed file. |
|  | Generate All Feeds | N/A | Manually updates all configured feed files. |
|  | Delete Feed | N/A | Removes a feed configuration and its file. |
| **Feed Configuration Form** | Feed Name | Descriptive Name | Identifies the specific feed. |
|  | (All other settings) | (As above) | Configures parameters for this individual feed instance. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My TikTok ads are showing outdated prices or out-of-stock products. What should I do?**
**A1:** This usually means your TikTok feed isn’t being updated frequently enough.
1. Go to **Catalog > TikTok Feed** in your PrestaShop Back Office.
2. Find the relevant feed and click the “Generate Now” button.
3. Ensure you have a cron job set up to automatically update your feeds daily (recommended). Check with your webmaster or hosting provider to confirm the cron job is running correctly.
4. Verify your “Include Out-of-Stock Products” setting in the feed configuration. If it’s enabled and you don’t want out-of-stock items, disable it.

**Q2: Some of my products are missing from the TikTok feed.**
**A2:** Check the following settings for the specific feed:
1. **“Exclude Specific Categories”:** Make sure the missing products’ categories are not selected here.
2. **“Exclude Specific Products”:** Ensure the individual products are not manually excluded.
3. **“Include Out-of-Stock Products”:** If the products are out of stock and this setting is disabled, they won’t appear.
4. **Product Visibility:** Ensure the products are active and visible in your PrestaShop store.

**Q3: My product descriptions look too long or too short in the TikTok feed.**
**A3:** Go to the feed configuration and adjust the “Use Product Short Description” setting:
- If descriptions are too long, enable this setting to use the shorter description.
- If descriptions are too short and you want more detail, disable this setting to use the full description.

**Q4: How do I map my categories to Google Product Categories effectively?**
**A4:**
1. Access the “Google Product Category Mapping” section within your feed configuration.
2. For each of your PrestaShop categories, search for the most relevant Google Product Category. Be as specific as possible.
3. If you can’t find an exact match, choose the closest broader category.
4. This mapping helps TikTok understand your products better for targeting.

**Q5: I’ve made changes, but the feed URL still shows old data. What’s wrong?**
**A5:** After making any changes to the module’s settings or a specific feed’s configuration, you **must** regenerate the feed. Go to **Catalog > TikTok Feed**, find the feed you modified, and click “Generate Now.” If you changed global settings, you might need to regenerate all feeds.

**Q6: My custom theme is causing display issues in the Back Office for the module.**
**A6:** While the module’s front-office components are invisible, its Back Office interface might conflict with heavily customized admin themes.
1. **Clear Smarty Cache:** Go to **Advanced Parameters > Performance** in your PrestaShop Back Office. Click “Clear cache” (or “Clear Smarty cache” in older versions). This often resolves minor display glitches.
2. **Check for JavaScript Errors:** Open your browser’s developer console (F12) in the Back Office. Look for any JavaScript errors. If you find errors, contact MyPresta.eu support with the error details.
3. **Temporary Theme Switch:** If possible, temporarily switch your Back Office theme to the default PrestaShop theme to see if the issue persists. If it resolves, the conflict is with your custom admin theme.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the TikTok Catalog Feed module, intended for developers and webmasters.

### 4.1 Architecture Overview

The TikTok Catalog Feed module follows a standard PrestaShop MVC (Model-View-Controller) pattern, primarily focused on Back Office administration and front-office data delivery. It leverages PrestaShop’s `Module` class for installation/uninstallation and configuration, and `AdminController` for managing feed settings. The core logic revolves around dynamically generating product data into a structured CSV or XML format, accessible via a dedicated `ModuleFrontController`. It does not introduce custom `ObjectModel` classes but directly queries PrestaShop’s core product and category data.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

These controllers are responsible for serving the actual product feed to TikTok.

- `controllers/front/feed.php`
  - **Class name & parent class:** `TiktokfeedFeedModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** This is the primary endpoint for TikTok to pull the product catalog. It dynamically generates the product feed (CSV or XML) based on the configuration parameters (language, currency, exclusions) associated with a specific feed ID. It handles the data retrieval, formatting, and output as a file download or direct stream. It’s designed to be stateless, processing the request and returning the feed.
- `controllers/front/index.php`
  - **Class name & parent class:** `TiktokfeedIndexModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** This controller is typically a placeholder or a fallback. In many modules, `index.php` in the front controller directory might handle default routing or simply redirect. For this module, `feed.php` is the critical front controller. This `index.php` might not have specific logic or could be used for a general module front page if one were implemented (which is not the case for a feed module).

#### Back-Office Admin Controllers

These controllers manage the module’s configuration and feed generation settings within the PrestaShop Back Office.

- `controllers/admin/AdminExportProductsFeedTiktok.php`
  - **Class name & parent class:** `AdminExportProductsFeedTiktokController` extends `ModuleAdminController`.
  - **Tab name and managed entity:** This controller is responsible for the main “TikTok Feed” section under **Catalog > TikTok Feed**. It manages the creation, editing, and deletion of individual feed configurations. It displays a list of configured feeds and provides forms for their detailed settings.
  - **Key functionalities:**
    - `renderList()`: Displays the table of existing feeds.
    - `renderForm()`: Renders the form for adding/editing a feed, including fields for language, currency, category/product exclusions, Google category mapping, etc.
    - Handles saving and updating feed configurations (`postProcess()`).
    - Triggers the feed generation process for specific feeds.
- `controllers/admin/index.php`
  - **Class name & parent class:** `AdminTiktokfeedIndexController` extends `ModuleAdminController`.
  - **Tab name and managed entity:** This controller likely serves as the main entry point for the module’s admin section, potentially redirecting to `AdminExportProductsFeedTiktokController` or providing a high-level dashboard. Given the module’s structure, `AdminExportProductsFeedTiktokController` is where the primary feed management logic resides. This `index.php` might be for a general module overview or a simple redirection.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes in the `classes/` directory. This suggests the module primarily relies on PrestaShop’s core `Product`, `Category`, `Language`, `Currency`, `Carrier` `ObjectModel` classes and `Configuration` for data storage and retrieval. The feed generation logic is likely encapsulated within the main module file (`tiktokfeed/index.php`) and the `AdminExportProductsFeedTiktokController`.

### 4.4 JavaScript Assets (`views/js/`)

- `tiktokfeed/lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Back-office.
  - **Purpose:** Provides autocomplete functionality, likely used for selecting products or categories to exclude, or for Google category mapping. It binds event listeners to input fields, performs AJAX requests for search suggestions, and updates the DOM with results.
- `tiktokfeed/views/js/admin-app.js`
  - **Scope:** Back-office.
  - **Purpose:** This is the main JavaScript file for the module’s Back Office interface. It handles various interactive elements on the feed configuration forms and dashboard. This could include:
    - Form validation.
    - Dynamic updates based on selected options (e.g., showing/hiding fields).
    - AJAX calls for saving settings or triggering feed generation.
    - Interactions with fancybox modals (e.g., for category/product selection).

### 4.5 CSS Stylesheets (`views/css/`)

- `tiktokfeed/lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Back-office admin styling.
  - **Purpose:** Styles the autocomplete dropdowns and input fields used by the `autocomplete.js` script, ensuring a consistent and user-friendly search experience within the admin forms.
- `tiktokfeed/views/admin-theme.css`
  - **Scope:** Back-office admin styling.
  - **Purpose:** Provides general styling adjustments for the module’s Back Office interface to integrate seamlessly with the PrestaShop admin theme. This might include layout adjustments, button styling, or table formatting.
- `tiktokfeed/views/css/admin-app.css`
  - **Scope:** Back-office admin styling.
  - **Purpose:** Contains specific styles for the module’s custom components, forms, and dashboard elements within the PrestaShop Back Office. This could include styles for the feed listing table, configuration panels, and fancybox modals.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

The module dossier does not explicitly list templates in a `hook/` subdirectory, implying that the module does not render content directly into front-office hooks. Its primary function is data generation, not front-end display.

#### Admin templates (`views/templates/admin/`)

These templates are used for rendering the module’s Back Office interface.

- `tiktokfeed/views/templates/admin/dashboard.tpl`
  - **Purpose:** Likely the main dashboard template for the TikTok Feed section, potentially showing an overview of feeds, status, and quick actions.
- `tiktokfeed/views/templates/admin/feeds.tpl`
  - **Purpose:** Renders the list of configured TikTok feeds, typically a table with columns for feed name, language, currency, URL, and action buttons (edit, generate, delete). This is likely rendered by `AdminExportProductsFeedTiktokController::renderList()`.
- `tiktokfeed/views/templates/admin/form-chrome.tpl`
  - **Purpose:** A wrapper or partial template used to provide consistent styling and structure for the module’s configuration forms, potentially including header, footer, and general layout elements for the form.
- `tiktokfeed/views/templates/admin/layout.tpl`
  - **Purpose:** A base layout template for the module’s admin pages, defining the overall structure, including header, navigation, and content areas.

#### Other Admin-related templates

These templates are likely used as partials or for specific UI components within the admin forms.

- `tiktokfeed/lib/searchTool/views/scripts.tpl`
  - **Purpose:** Includes JavaScript for the search tool, likely the `autocomplete.js` script and its initialization.
- `tiktokfeed/views/categories-fancybox.tpl`
  - **Purpose:** Renders the content for a Fancybox modal used to select categories for exclusion or mapping.
- `tiktokfeed/views/exclude-products.tpl`
  - **Purpose:** Renders the UI for selecting and managing products to be excluded from the feed, possibly within a Fancybox or a dedicated section of the form.
- `tiktokfeed/views/google_lang_links.tpl`
  - **Purpose:** Renders links or UI elements related to Google Product Category mapping, potentially for different languages.
- `tiktokfeed/views/returnAlert.tpl`
  - **Purpose:** A generic template for displaying success or error messages/alerts in the Back Office.
- `tiktokfeed/views/script-fancybox.tpl`
  - **Purpose:** Includes JavaScript for Fancybox integration, likely for opening modals for category/product selection.
- `tiktokfeed/views/script.tpl`
  - **Purpose:** A general script template, possibly for module-wide JavaScript initialization or small inline scripts.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not appear to create custom SQL tables based on the dossier.
  - It stores its configuration settings (e.g., feed type, default language/currency, exclusion lists, Google category mappings) in PrestaShop’s `ps_configuration` table. Configuration keys would typically follow a pattern like `TTF_FEED_TYPE`, `TTF_DEFAULT_LANG`, `TTF_EXCLUDE_CATEGORIES`, etc.
  - Individual feed configurations (if multiple feeds are supported) might be stored as serialized arrays in `ps_configuration` or potentially in a custom table if the module were to introduce one (which is not indicated).
- **Registered Hooks Table**:
  The module’s primary function is data generation, not front-office display, so it does not register hooks for displaying content on the storefront (e.g., `displayHeader`, `displayRightColumn`).
  It will, however, register the following hooks for its core functionality:

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `actionModuleInstall` | During module installation | Creates configuration entries, registers admin tabs. |
  | `actionModuleUninstall` | During module uninstallation | Cleans up configuration entries, unregisters admin tabs. |
  | `actionAdminControllerSetMedia` | When an admin controller is loaded | Enqueues module-specific JS and CSS for the Back Office. |
  | `displayBackOfficeHeader` | Renders content in the Back Office header | Potentially for global admin JS/CSS or notifications. |
  | `actionSchedulerCron` (or similar) | When PrestaShop’s cron job runs | Triggers automatic feed generation if configured. |

### Cron Job Setup for Automated Feed Generation

For automated feed updates, you’ll need to set up a cron job on your server to call a specific URL or script provided by the module. This URL typically points to a front controller that triggers the feed generation.

**Example Cron Job Command (Consult your hosting provider for exact syntax):**

Terminal window

```
0 3 \* \* \* wget -q -O /dev/null "https://yourstore.com/module/tiktokfeed/feed?action=generate\_all&token=YOUR\_SECURE\_TOKEN" >/dev/null 2>&1
```

- `0 3 * * *`: This schedules the job to run daily at 3:00 AM.
- `wget -q -O /dev/null`: Silently fetches the URL and discards the output.
- `https://yourstore.com/module/tiktokfeed/feed?action=generate_all&token=YOUR_SECURE_TOKEN`: This is the URL that triggers the feed generation. The `token` parameter is crucial for security to prevent unauthorized access. The module should provide this token in its configuration or documentation.
- `>/dev/null 2>&1`: Redirects all output to null, preventing unnecessary email notifications.

**Important:** The exact URL and token will be provided by the module after configuration. Always use the secure token to protect your feed generation endpoint.

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official developer support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Ensure you are running the latest compatible version of the module for your PrestaShop store.
