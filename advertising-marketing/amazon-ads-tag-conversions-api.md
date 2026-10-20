---
title: "Amazon Ads Tag Conversions API - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Amazon Ads Tag Conversions API PrestaShop module by MyPresta.eu."
sidebar:
  label: "Amazon Ads Tag Conversions API - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Amazon Ads Tag Conversions API Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/amazon-ads-tag-conversions-api.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/amazon-ads-tag-conversions-api/)
>
> ---


# Amazon Ads Tag Conversions API

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required for the module to function correctly, especially for the Conversions API (CAPI) which relies on secure server-to-server communication. Your hosting environment should also allow outbound connections to Amazon’s API endpoints.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

This section guides you through every setting of the “Amazon Ads Tag Conversions API” module.

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen where you’ll set up your Amazon Ads tracking.

**Access:** Navigate to **Modules > Module Manager**, then find “Amazon Ads Tag Conversions API” and click **Configure**.

#### **Tracking Mode Selection**

This section determines how your store sends data to Amazon.

- **What this setting does:** Allows you to choose between three primary methods for sending conversion data to Amazon: Amazon Ads Tag (client-side), Conversions API (server-side), or a combination of both.
- **Effect of changing this setting:**
  - *When set to “Amazon Ads Tag (Client-Side)”:* The module will primarily rely on the JavaScript tag placed in the customer’s browser to send data. This is susceptible to ad blockers.
  - *When set to “Conversions API (Server-Side)”:* The module will send data directly from your PrestaShop server to Amazon’s servers. This is more reliable and bypasses ad blockers.
  - *When set to “Dual Mode (Hybrid)”:* The module will send data using both the Amazon Ads Tag and the Conversions API. This provides maximum data resilience and accuracy.
- **Recommended value:** **“Dual Mode (Hybrid)”** for the most robust and accurate tracking. If you are highly concerned about privacy and want to minimize client-side scripts, “Conversions API (Server-Side)” is a strong alternative.
- **Merchant scenario / example:** If you’ve noticed a discrepancy between your Amazon Ads reported conversions and your actual PrestaShop sales, switching to “Dual Mode” or “Conversions API” can significantly improve accuracy by recovering conversions lost to ad blockers.

#### **Amazon Ads Tag ID**

- **What this setting does:** This is your unique identifier provided by Amazon Ads for your tracking tag. It tells Amazon which account to attribute the conversion data to.
- **Effect of changing this setting:**
  - *When a valid ID is entered:* The Amazon Ads Tag (if enabled in your tracking mode) will correctly send data to your Amazon Ads account.
  - *When left empty or an invalid ID is entered:* Client-side tracking will not function, and data will not be sent to your Amazon Ads account via the tag.
- **Recommended value:** Your specific Amazon Ads Tag ID. You can find this in your Amazon Ads account under “Events Manager” or “Audiences.”
- **Merchant scenario / example:** You’ve just set up a new Amazon Ads campaign. Entering the correct Tag ID here is the first step to ensuring your campaign performance is tracked.

#### **Amazon Conversions API Access Token**

- **What this setting does:** This is a secure token provided by Amazon Ads that authenticates your server when sending data via the Conversions API. It ensures that only authorized sources can send data to your Amazon Ads account.
- **Effect of changing this setting:**
  - *When a valid token is entered:* Your PrestaShop server can securely send conversion data directly to Amazon via the Conversions API (if enabled in your tracking mode).
  - *When left empty or an invalid token is entered:* Server-side tracking via the Conversions API will not function, and data will not be sent to your Amazon Ads account via CAPI.
- **Recommended value:** Your specific Amazon Conversions API Access Token. This is generated in your Amazon Ads account, typically under “Events Manager” or “Data Sources.” Treat this token like a password; keep it secure.
- **Merchant scenario / example:** You want to improve the reliability of your conversion tracking by using the Conversions API. After generating the token in Amazon Ads, paste it here to enable server-side data transmission.

#### **Enable Debug Mode**

- **What this setting does:** Activates a special mode that displays detailed information about the data being sent to Amazon, visible only to you (or anyone with developer tools open) in the browser console. This is invaluable for troubleshooting.
- **Effect of changing this setting:**
  - *When enabled:* You will see console logs and potentially on-screen overlays (depending on the specific debug implementation) showing what events are being triggered and what data is being sent to Amazon. This is not visible to regular customers.
  - *When disabled:* No debug information will be displayed.
- **Recommended value:** **“NO”** for live production stores. Only enable temporarily when setting up or troubleshooting.
- **Merchant scenario / example:** You’ve configured the module, but conversions aren’t showing up in your Amazon Ads account. Enabling debug mode can help you see if the events are firing correctly on your website and if the data payload looks accurate.

#### **Consent Management Integration**

- **What this setting does:** Allows the module to integrate with your store’s cookie consent solution. This ensures that Amazon Ads tracking only activates after a customer has given their explicit consent, complying with privacy regulations like GDPR or CCPA.
- **Effect of changing this setting:**
  - *When enabled and integrated with a consent module:* The Amazon Ads Tag (client-side) will only load and fire events if the customer has accepted tracking cookies. Server-side CAPI might still send anonymized data or wait for consent depending on your specific setup and privacy policies.
  - *When disabled:* The module will attempt to track events without explicit consent checks, which might not be compliant with privacy laws in certain regions.
- **Recommended value:** **“YES”** if your store operates in regions with strict privacy laws (e.g., EU, California) and you use a cookie consent module.
- **Merchant scenario / example:** Your store serves customers in Europe, and you use a GDPR-compliant cookie banner. Enabling this setting ensures your Amazon Ads tracking respects customer privacy choices.

#### **Advanced Settings (e.g., Data Layer, Event Mapping, Product ID Resolution)**

The module may include advanced settings that allow fine-tuning of data collection and transmission. These are typically for more technical users or specific scenarios.

- **Data Layer Tracking:**
  - **What this setting does:** Determines if the module should use a standardized “data layer” to collect information from your store. This is often used for compatibility with other tracking tools or custom implementations.
  - **Effect of changing this setting:**
    - *When enabled:* The module will look for and push data to a `dataLayer` JavaScript object, which can be useful for debugging or integrating with Google Tag Manager.
    - *When disabled:* The module will collect data directly from PrestaShop’s internal variables.
  - **Recommended value:** **“YES”** if you are using Google Tag Manager or other tools that rely on a data layer. Otherwise, “NO” is usually fine.
- **Event Mapping:**
  - **What this setting does:** Allows you to customize how specific PrestaShop actions (e.g., “add to cart”) are mapped to Amazon Ads event names.
  - **Effect of changing this setting:**
    - *When customized:* You can send different event names to Amazon than the module’s default, which might be useful for specific Amazon Ads campaign setups.
    - *When default:* The module uses its predefined mapping.
  - **Recommended value:** Leave at default unless you have a specific reason to change it based on Amazon Ads documentation.
- **Product ID Resolution:**
  - **What this setting does:** Defines which product identifier (e.g., Product ID, EAN, UPC, SKU) the module should send to Amazon for product-related events.
  - **Effect of changing this setting:**
    - *When set to Product ID:* Amazon will receive PrestaShop’s internal product ID.
    - *When set to EAN/UPC/SKU:* Amazon will receive the corresponding product identifier. This is crucial for matching products in your Amazon product catalog.
  - **Recommended value:** Choose the identifier that most consistently matches the product IDs you use in your Amazon product feeds or catalog. **EAN/UPC** is often preferred for retail products.
- **Linker Domains:**
  - **What this setting does:** Specifies additional domains that should be included in cross-domain tracking. This is important if your checkout process or other parts of your customer journey involve multiple domains (e.g., a separate subdomain for a blog or a payment gateway that redirects).
  - **Effect of changing this setting:**
    - *When configured:* The Amazon Ads Tag can maintain tracking continuity across different domains, preventing loss of attribution.
    - *When not configured for multiple domains:* Conversions might be misattributed or lost if the customer navigates between domains during their journey.
  - **Recommended value:** Add any domains or subdomains that are part of your customer’s journey.
- **Currency Helper:**
  - **What this setting does:** Ensures that currency values sent to Amazon are correctly formatted and match the currency used in your Amazon Ads account.
  - **Effect of changing this setting:**
    - *When correctly configured:* Amazon receives accurate currency values.
    - *When misconfigured:* Currency values might be misinterpreted by Amazon, leading to incorrect reporting.
  - **Recommended value:** Ensure this aligns with your store’s primary currency and your Amazon Ads account currency.

### 2.2 Dedicated Admin Screens & Controller Views

The module provides several dedicated screens to help you monitor and optimize your Amazon Ads tracking. These are typically accessible via tabs or sub-sections within the main module configuration.

#### **4.2.1 Live Statistics**

- **Screen Name & Menu Location:** Usually a tab within the main module configuration (e.g., “Live Statistics”).
- **Available Actions & Settings:** This screen displays real-time or near real-time data about the events being sent to Amazon. It might show:
  - Recent events (e.g., PageView, AddToCart, Purchase) with timestamps.
  - Event types and their frequency.
  - Data quality scores.
  - Visualizations of tracking activity.
- **Effect of changes:** This is a reporting screen; there are no direct settings to change here. It reflects the data being sent based on your main configuration.
- **Recommended workflow for daily store management:** Regularly check this screen to ensure events are firing as expected, especially after making changes to your store or launching new campaigns. It’s your first line of defense for identifying tracking issues.

#### **4.2.2 Health Score & Recovery Radar**

- **Screen Name & Menu Location:** Often a tab within the main module configuration (e.g., “Health Score” or “Diagnostics”).
- **Available Actions & Settings:** This section provides an overall health score for your Amazon Ads tracking and identifies potential issues or “lost” conversions. It might include:
  - A percentage score indicating tracking health.
  - Recommendations for improving data quality.
  - A “Recovery Radar” showing estimated conversions that might have been missed due to ad blockers or other issues, and how CAPI is helping to recover them.
  - Warnings about missing Tag IDs, Access Tokens, or consent issues.
- **Effect of changes:** Like Live Statistics, this is primarily a reporting and diagnostic screen. Actions you take based on its recommendations (e.g., updating a missing Tag ID) will improve your tracking.
- **Recommended workflow for daily store management:** Periodically review your Health Score. A low score or active “Recovery Radar” indicates areas where your tracking could be improved, potentially leading to better ad performance.

#### **4.2.3 Data Quality Coach / Catalog Doctor**

- **Screen Name & Menu Location:** Potentially a tab within the main module configuration (e.g., “Data Quality” or “Catalog Doctor”).
- **Available Actions & Settings:** These tools help you ensure the data you’re sending to Amazon is high quality and correctly formatted. They might:
  - Check for common data issues (e.g., missing product IDs, incorrect currency formats).
  - Provide suggestions for improving your product catalog data to better match Amazon’s requirements.
  - Highlight discrepancies between client-side and server-side data.
- **Effect of changes:** This screen provides actionable insights. Addressing the issues highlighted here (e.g., updating product EANs in your PrestaShop catalog) will directly improve the quality and matching capabilities of your conversion data in Amazon Ads.
- **Recommended workflow for daily store management:** If you’re experiencing issues with product matching in Amazon Ads or seeing warnings in your Health Score, consult these tools to refine your data.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Main Config | **Tracking Mode** | Dual Mode (Hybrid) | Determines if tracking is client-side, server-side, or both. Dual Mode offers maximum resilience. |
| Main Config | **Amazon Ads Tag ID** | Your Amazon Tag ID | Essential for client-side tracking. Links data to your Amazon Ads account. |
| Main Config | **Amazon Conversions API Access Token** | Your CAPI Access Token | Essential for server-side tracking. Authenticates your server with Amazon. |
| Main Config | **Enable Debug Mode** | NO | Displays tracking data in browser console for troubleshooting. Disable on live stores. |
| Main Config | **Consent Management Integration** | YES (if applicable) | Ensures tracking respects customer privacy and cookie consent. |
| Main Config | **Data Layer Tracking** | YES (if using GTM) | Uses a data layer for event collection, useful for GTM or custom integrations. |
| Main Config | **Product ID Resolution** | EAN/UPC | Defines which product identifier is sent to Amazon for matching. Crucial for catalog matching. |
| Main Config | **Linker Domains** | Empty (add if needed) | Maintains tracking across multiple domains in your customer journey. |
| Live Statistics | (Reporting Only) | N/A | Shows real-time event data, helping you verify tracking is active. |
| Health Score | (Reporting Only) | N/A | Provides an overall health assessment of your tracking and identifies issues. |
| Data Quality | (Reporting Only) | N/A | Helps identify and fix data quality issues in your product catalog for better Amazon matching. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My Amazon Ads conversions don’t match my PrestaShop sales. What should I do?**
A1: This is a common issue, often due to ad blockers.
\* **Check Tracking Mode:** Ensure you are using “Dual Mode (Hybrid)” or “Conversions API (Server-Side)” in the module settings. This is the most effective way to recover lost conversions.
\* **Verify IDs/Tokens:** Double-check that your Amazon Ads Tag ID and Conversions API Access Token are correctly entered in the module configuration.
\* **Use Debug Mode:** Temporarily enable “Debug Mode” and perform a test purchase. Check your browser console and the module’s “Live Statistics” to see if events are firing.
\* **Clear Cache:** Go to **Advanced Parameters > Performance** in your PrestaShop back office and clear the Smarty cache and other caches. Sometimes old module code can persist.

**Q2: I’m seeing warnings about “Data Quality” or “Missing Product IDs” in the module’s Health Score. How do I fix this?**
A2: Amazon relies on high-quality product data for accurate matching.
\* **Product ID Resolution:** In the module’s configuration, ensure your “Product ID Resolution” setting (e.g., EAN, UPC, SKU) matches the primary identifier used in your Amazon product feed.
\* **Update Product Data:** Go to **Catalog > Products** in your PrestaShop back office. Edit the products flagged by the “Data Quality Coach” and ensure they have complete and accurate EANs, UPCs, or SKUs as required.
\* **Consistency:** Make sure the product identifiers in your PrestaShop store are consistent with what you provide to Amazon in your product feeds.

**Q3: My website uses a cookie consent banner. Will this module respect customer choices?**
A3: Yes, if configured correctly.
\* **Enable Consent Integration:** In the module’s configuration, ensure “Consent Management Integration” is enabled.
\* **Cookie Module Compatibility:** This module is designed to integrate with standard PrestaShop cookie consent modules. If you use a custom solution, you might need to ensure it correctly triggers the `prestashop.on('updateProduct', ...)` or similar events that modules listen to for consent changes.
\* **CAPI vs. Tag:** Remember that the Conversions API (server-side) is less affected by client-side consent banners than the Amazon Ads Tag (client-side), as it sends data directly from your server. However, it’s still best practice to only send personally identifiable information (PII) via CAPI after consent.

**Q4: The module seems to be slowing down my site. What can I do?**
A4: This module is optimized for performance, but here are some checks:
\* **Disable Debug Mode:** Ensure “Debug Mode” is disabled on your live store, as it adds extra console logging.
\* **Server Performance:** The Conversions API (CAPI) makes server-to-server calls. While generally fast, ensure your hosting server has adequate resources and a stable internet connection.
\* **Other Modules:** Check if other heavy tracking or advertising modules are also running simultaneously. Too many client-side scripts can impact performance.
\* **Clear Cache:** Always clear PrestaShop’s cache after making configuration changes.

**Q5: I’m getting an error message when trying to save the module configuration.**
A5:
\* **Check Permissions:** Ensure the module’s folder (`/modules/myamazon/`) and its subfolders have correct write permissions (usually 755 for folders, 644 for files).
\* **Server Logs:** Check your server’s PHP error logs for more detailed information about the error. This can often be found in your hosting control panel or by contacting your host.
\* **PrestaShop Debug Mode:** Temporarily enable PrestaShop’s debug mode (in `config/defines.inc.php`, change `define('_PS_MODE_DEV_', false);` to `define('_PS_MODE_DEV_', true);`) to see more detailed error messages on screen.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the “Amazon Ads Tag Conversions API” module, intended for developers and webmasters.

### 4.1 Architecture Overview

The `myamazon` module is built following PrestaShop’s MVC (Model-View-Controller) pattern, with a strong emphasis on modularity and event-driven tracking. It leverages both client-side (Amazon Ads Tag) and server-side (Conversions API) mechanisms, often in a hybrid approach.

Key architectural components:

- **Main Module Class (`myamazon/index.php`):** Handles installation, uninstallation, hook registration, and the primary `getContent()` method for the back-office configuration.
- **Controllers:** Dedicated front controllers for AJAX interactions and admin controllers for managing module settings and diagnostic views.
- **Core Classes (`classes/`):** A robust set of classes manage various aspects:
  - **Tracking Logic:** `MyamazonAatTracker.php` (client-side), `MyamazonCapiTracker.php` (server-side), `MyamazonHybridTracker.php` (dual mode), `MyamazonTrackerFactory.php` (instantiates trackers).
  - **Data Handling:** `MyamazonUserData.php` (customer data), `MyamazonEventMap.php` (event translation), `MyamazonProductIdResolver.php` (product ID logic), `MyamazonCurrencyHelper.php`.
  - **API Client:** `MyamazonCapiClient.php` (handles communication with Amazon CAPI).
  - **Diagnostics & Health:** `MyamazonHealthScore.php`, `MyamazonCatalogDoctor.php`, `MyamazonDataQualityCoach.php`, `MyamazonLiveStats.php`.
  - **Consent:** `MyamazonConsent.php` (integrates with consent mechanisms).
- **Hooks:** Extensive use of PrestaShop hooks to inject JavaScript, capture events, and send data at critical points in the customer journey.
- **Smarty Templates:** Used for rendering both back-office configuration views and front-office tracking scripts.
- **JavaScript:** Manages client-side tag injection, event listening, and data layer interactions.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `controllers/front/ajax.php`
  - **Class Name:** `MyamazonAjaxModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** Handles asynchronous (AJAX) requests from the front-office. This is typically used for server-side event sending via CAPI that cannot be done directly in the browser (e.g., post-purchase events where the browser might be closed, or events requiring server-side data processing). It receives data from client-side JavaScript and dispatches it to the `MyamazonCapiTracker`.
- `controllers/front/index.php`
  - **Class Name:** `MyamazonIndexModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** This controller might serve as a fallback or a simple entry point, though its primary use case might be minimal if `ajax.php` handles most front-end interactions. It could be used for specific redirects or simple data displays if needed, but often serves as a placeholder.

#### Back-Office Admin Controllers

- `controllers/admin/AdminMyamazonAjaxController.php`
  - **Class Name:** `AdminMyamazonAjaxController` (extends `ModuleAdminController`)
  - **Tab Name:** Not directly a menu tab, but an AJAX endpoint for the admin interface.
  - **Responsibility:** Handles AJAX requests originating from the module’s back-office configuration pages. This includes fetching data for live statistics, health scores, or performing background checks (e.g., API token validation) without reloading the entire page. It interacts with classes like `MyamazonLiveStats`, `MyamazonHealthScore`, and `MyamazonCapiClient`.
- `controllers/admin/index.php`
  - **Class Name:** `AdminMyamazonIndexController` (extends `ModuleAdminController`)
  - **Tab Name:** Not a direct menu tab.
  - **Responsibility:** Similar to the front-office `index.php`, this might be a placeholder or handle very specific, non-AJAX admin interactions. The primary configuration logic resides in the main module’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

- `classes/autoload.php`: Standard PrestaShop autoload file.
- `classes/index.php`: Placeholder file, common in empty directories.
- `classes/MyamazonAatTracker.php`:
  - **Responsibility:** Implements the logic for client-side Amazon Ads Tag tracking. Generates the necessary JavaScript for `aa.js` and pushes events to the browser’s data layer or directly to the Amazon Ads Tag.
- `classes/MyamazonCapiClient.php`:
  - **Responsibility:** Handles the actual HTTP requests to Amazon’s Conversions API endpoints. Encapsulates cURL or Guzzle (if used) logic, authentication with the access token, and error handling for server-to-server communication.
- `classes/MyamazonCapiTracker.php`:
  - **Responsibility:** Implements the logic for server-side Conversions API tracking. Formats event data according to Amazon’s CAPI specifications and uses `MyamazonCapiClient` to send it.
- `classes/MyamazonCatalogDoctor.php`:
  - **Responsibility:** Analyzes the store’s product catalog data for potential issues that could affect Amazon product matching (e.g., missing EANs, incorrect SKUs). Provides diagnostic feedback for the admin interface.
- `classes/MyamazonConsent.php`:
  - **Responsibility:** Manages cookie consent integration. Checks for customer consent status and conditionally enables/disables client-side tracking scripts. Integrates with PrestaShop’s `prestashop.on('updateProduct', ...)` event for consent changes.
- `classes/MyamazonCurrencyHelper.php`:
  - **Responsibility:** Provides utility methods for formatting currency values correctly for Amazon Ads, handling decimals, and currency codes.
- `classes/MyamazonDataLayerTracker.php`:
  - **Responsibility:** Manages pushing event data to a JavaScript `dataLayer` object, often used for compatibility with Google Tag Manager or other data layer consumers.
- `classes/MyamazonDataQualityCoach.php`:
  - **Responsibility:** Provides insights and recommendations for improving the overall quality of data sent to Amazon, covering aspects beyond just product IDs.
- `classes/MyamazonEventId.php`:
  - **Responsibility:** Generates unique event IDs for each event, crucial for deduplication when using dual-mode tracking (ensuring Amazon doesn’t count the same event twice from client-side and server-side).
- `classes/MyamazonEventMap.php`:
  - **Responsibility:** Defines the mapping between PrestaShop’s internal events (e.g., `actionCartSave`) and Amazon Ads standard event names (e.g., `AddToCart`). Allows for customization of these mappings.
- `classes/MyamazonEvents.php`:
  - **Responsibility:** A central class or collection of methods for triggering and managing various Amazon Ads events (e.g., `PageView`, `ViewContent`, `AddToCart`, `Purchase`).
- `classes/MyamazonHealthScore.php`:
  - **Responsibility:** Calculates and presents an overall “health score” for the module’s tracking, identifying configuration issues, missing data, or potential tracking gaps.
- `classes/MyamazonHybridTracker.php`:
  - **Responsibility:** Orchestrates dual-mode tracking, combining `MyamazonAatTracker` and `MyamazonCapiTracker` to send events via both client-side and server-side methods, handling deduplication.
- `classes/MyamazonLiveStats.php`:
  - **Responsibility:** Collects and processes real-time or near real-time event data for display in the “Live Statistics” back-office view.
- `classes/MyamazonProductIdResolver.php`:
  - **Responsibility:** Determines which product identifier (ID, EAN, UPC, SKU) should be used when sending product data to Amazon, based on module configuration.
- `classes/MyamazonPropertyRules.php`:
  - **Responsibility:** Defines rules and validations for event properties, ensuring that data sent to Amazon adheres to their API specifications.
- `classes/MyamazonTrackerFactory.php`:
  - **Responsibility:** A factory pattern class responsible for instantiating the correct tracker (`AatTracker`, `CapiTracker`, or `HybridTracker`) based on the module’s configuration.
- `classes/MyamazonTrackerInterface.php`:
  - **Responsibility:** Defines a common interface for all tracker classes (`AatTracker`, `CapiTracker`, `HybridTracker`), ensuring they implement a consistent set of methods for event tracking.
- `classes/MyamazonUserData.php`:
  - **Responsibility:** Collects and formats customer-related data (e.g., email, phone, address) for inclusion in Amazon Ads events, especially for Conversions API where PII can be hashed and sent.

### 4.4 JavaScript Assets (`views/js/`)

- `views/js/myamazon-admin.js`:
  - **Scope:** Back-office.
  - **Details:** Handles interactive elements on the module’s configuration pages, such as tab switching, AJAX calls for live statistics, form validation, and dynamic updates to diagnostic tools.
- `views/js/myamazon-debug.js`:
  - **Scope:** Front-office (conditionally loaded when debug mode is active).
  - **Details:** Provides verbose logging to the browser console, displaying the events being triggered, the data payloads, and the status of Amazon Ads Tag and CAPI calls. May include visual overlays for quick debugging.
- `views/js/myamazon-ghost.js`:
  - **Scope:** Front-office.
  - **Details:** Likely related to “ghost” or background tracking mechanisms, potentially for capturing events that might otherwise be missed or for specific consent-related deferrals.
- `views/js/myamazon-live.js`:
  - **Scope:** Back-office.
  - **Details:** Powers the “Live Statistics” dashboard, making AJAX requests to `AdminMyamazonAjaxController` to fetch and display real-time event data.
- `views/js/myamazon-tcf.js`:
  - **Scope:** Front-office.
  - **Details:** Integrates with Transparency and Consent Framework (TCF) compliant cookie consent solutions, ensuring client-side tracking adheres to user consent preferences.
- `views/js/myamazon-wizard.js`:
  - **Scope:** Back-office.
  - **Details:** Provides interactive steps for the initial setup wizard, guiding the merchant through essential configuration.
- `views/js/myamazon.js`:
  - **Scope:** Front-office.
  - **Details:** The main client-side JavaScript for the module. It injects the Amazon Ads Tag (`aa.js`), listens for various DOM events (e.g., `click` on add-to-cart buttons), captures data from the page, pushes events to the data layer, and potentially makes AJAX calls to `MyamazonAjaxModuleFrontController` for server-side processing. It also handles event deduplication logic.

### 4.5 CSS Stylesheets (`views/css/`)

- `myamazon/opis/sugestie/style1.css`, `myamazon/opis/sugestie/style2.css`, `myamazon/opis/sugestie/sugestie/style1.css`, `myamazon/opis/sugestie/sugestie/style2.css`, `myamazon/opis/sugestie/sugestie/tailwind-new-7.css`, `myamazon/opis/sugestie/tailwind-new-7.css`:
  - **Scope:** Back-office.
  - **Details:** These files appear to be related to a custom UI framework or styling for suggestions/hints within the back-office configuration, possibly for a guided setup or diagnostic feedback. `tailwind-new-7.css` suggests the use of Tailwind CSS for utility-first styling.
- `views/css/myamazon-admin.css`:
  - **Scope:** Back-office admin form styling.
  - **Details:** Provides specific styling for the module’s configuration forms, tabs, diagnostic panels, and other custom UI elements within the PrestaShop back office.
- `views/css/myamazon-debug.css`:
  - **Scope:** Front-office (conditionally loaded).
  - **Details:** Styles for the debug overlay or console messages, ensuring they are readable and distinct when debug mode is active.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `views/templates/hook/capi-pageview.tpl`:
  - **Hook:** `displayHeader` (or similar).
  - **Output:** Injects server-side (CAPI) PageView event data, potentially as a hidden input or JavaScript variable, to be picked up by the `ajax.php` controller for server-side sending.
- `views/templates/hook/debug.tpl`:
  - **Hook:** `displayHeader` (conditionally).
  - **Output:** Injects the `myamazon-debug.js` script and any necessary initial debug variables when debug mode is enabled.
- `views/templates/hook/displayOrderConfirmation.tpl`:
  - **Hook:** `displayOrderConfirmation`.
  - **Output:** Renders the critical “Purchase” event data, including order details, products, and customer information, for both client-side tag and server-side CAPI transmission. This is where the conversion value is captured.
- `views/templates/hook/ghost.tpl`:
  - **Hook:** `displayHeader` (or similar).
  - **Output:** Related to the “ghost” tracking mechanism, potentially for deferred loading or specific consent-related logic.
- `views/templates/hook/header.tpl`:
  - **Hook:** `displayHeader`.
  - **Output:** The primary template for injecting the Amazon Ads Tag (`aa.js` script), `myamazon.js`, and initial configuration variables into the `<head>` section of every page.
- `views/templates/hook/payment.tpl`:
  - **Hook:** `displayPaymentTop` (or similar).
  - **Output:** May be used to track “InitiateCheckout” or other payment-related events before the final order confirmation.
- `views/templates/hook/product-details.tpl`:
  - **Hook:** `displayProductButtons` or `displayProductExtraContent`.
  - **Output:** Injects JavaScript to track “ViewContent” events when a product page is loaded, capturing product-specific data.

#### Admin templates (`views/templates/admin/`)

- `views/templates/admin/consent-guide.tpl`: Displays guidance on how to integrate with cookie consent modules.
- `views/templates/admin/doctor.tpl`: Renders the “Catalog Doctor” diagnostic view, showing product data issues.
- `views/templates/admin/dq.tpl`: Renders the “Data Quality Coach” view, providing data quality insights.
- `views/templates/admin/health.tpl`: Displays the overall “Health Score” and related diagnostics.
- `views/templates/admin/linker-domains.tpl`: Renders the input field for configuring linker domains.
- `views/templates/admin/live-maintain.tpl`: Possibly a maintenance view for live statistics.
- `views/templates/admin/live.tpl`: Renders the “Live Statistics” dashboard.
- `views/templates/admin/mode-context.tpl`, `views/templates/admin/mode-note-aat.tpl`, `views/templates/admin/mode-note-both.tpl`, `views/templates/admin/mode-note-capi.tpl`, `views/templates/admin/mode-note-datalayer.tpl`, `views/templates/admin/mode-picker.tpl`: These templates are used for the “Tracking Mode Selection” section, providing explanations and the radio button/dropdown for choosing the tracking method.
- `views/templates/admin/properties-list.tpl`: Displays a list of event properties and their values, possibly for debugging or configuration.
- `views/templates/admin/recent-events.tpl`: Renders a table or list of recently tracked events, part of “Live Statistics.”
- `views/templates/admin/tabs.tpl`: Renders the tab navigation structure for the module’s back-office configuration.
- `views/templates/admin/tag-chips.tpl`: Displays visual “chips” or labels for configured tags/tokens.
- `views/templates/admin/tag-ids.tpl`: Renders input fields for Amazon Ads Tag ID and CAPI Access Token.
- `views/templates/admin/wizard.tpl`: Renders the initial setup wizard interface.

### 4.7 Database Schema & Hooks Map

#### Database Tables

The module primarily stores its configuration in PrestaShop’s `ps_configuration` table.

- `ps_configuration`: Stores key-value pairs for module settings (e.g., `MYAMAZON_TAG_ID`, `MYAMAZON_CAPI_TOKEN`, `MYAMAZON_TRACKING_MODE`).
  No custom SQL tables are explicitly created by this module based on the provided inventory.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Injects the Amazon Ads Tag script (`aa.js`), `myamazon.js`, and initial configuration variables. Also used for `capi-pageview.tpl` and `debug.tpl`. |
| `displayOrderConfirmation` | On the order confirmation page after a successful purchase. | Captures and sends “Purchase” event data, including order details and products, to Amazon via both client-side and server-side methods. |
| `actionCartSave` | When a product is added to or removed from the cart, or cart quantity changes. | Triggers “AddToCart” or “RemoveFromCart” events. |
| `actionProductAdd` | When a new product is added to the catalog. | Potentially used by `MyamazonCatalogDoctor` for data quality checks. |
| `actionProductUpdate` | When an existing product is updated in the catalog. | Potentially used by `MyamazonCatalogDoctor` for data quality checks. |
| `actionFrontControllerSetMedia` | Before a front controller renders its template, allowing addition of JS/CSS. | Injects module-specific JS/CSS files (`myamazon.js`, `myamazon-debug.js`, etc.) into the front office. |
| `actionAdminControllerSetMedia` | Before an admin controller renders its template. | Injects module-specific JS/CSS files (`myamazon-admin.js`, `myamazon-admin.css`, etc.) into the back office. |
| `actionValidateOrder` | After an order has been successfully validated and saved to the database. | Crucial for server-side “Purchase” event sending via CAPI, ensuring data is sent even if the customer closes the browser before reaching the confirmation page. |
| `displayProductButtons` / `displayProductExtraContent` | On the product page, near the add-to-cart button or product description. | Injects JavaScript to track “ViewContent” events. |
| `displayPaymentTop` | At the top of the payment selection page during checkout. | Potentially used to track “InitiateCheckout” events. |
| `displayFooter` | In the footer section of every page. | Less common for core tracking, but could be used for deferred script loading or specific consent popups. |
| `actionObjectCustomerAddAfter` | After a new customer account is created. | Potentially used to send “SignUp” or “Lead” events to Amazon. |
| `actionObjectCustomerUpdateAfter` | After a customer’s details are updated. | Could be used to update customer data for CAPI. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please refer to your customer account at MyPresta.eu.

- **Module Updates:** Log in to your account at [MyPresta.eu Order History & Downloads](https://mypresta.eu/my-account/orders/) to download the newest versions of the “Amazon Ads Tag Conversions API” module.
- **Technical Support:** If you encounter any issues or have questions regarding the module’s functionality, configuration, or integration, please open a support ticket through your MyPresta.eu customer account. Our team of experts is ready to assist you.
