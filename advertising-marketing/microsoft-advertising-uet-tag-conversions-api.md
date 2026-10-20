---
title: "Microsoft Advertising UET Tag & Conversions API - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Microsoft Advertising UET Tag & Conversions API PrestaShop module by MyPresta.eu."
sidebar:
  label: "Microsoft Advertising UET Tag & Conversions API - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Microsoft Advertising UET Tag & Conversions API Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/microsoft-advertising-uet-tag-conversions-api.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/microsoft-advertising-uet-tag-conversions-api/)
>
> ---


# Microsoft Advertising UET Tag & Conversions API

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions such as cURL, JSON, and OpenSSL are required for the module to function correctly, especially for the Conversions API features. These are typically enabled by default on most modern hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main hub for setting up your Microsoft Advertising tracking. You’ll find a series of tabs and settings designed to guide you through the process.

#### Main Configuration Tab (Initial View)

- **What this setting does:** This tab typically provides an overview and initial setup options, often including a wizard to simplify the first-time configuration.
- **Effect of changing this setting:** Completing the wizard or filling in the initial details will enable the basic tracking functionality and prepare the module for more advanced settings.
- **Recommended value:** Follow the wizard steps carefully.
- **Merchant scenario / example:** When you first install the module, the wizard will ask for your UET Tag ID and guide you through choosing your tracking method (UET Tag, Conversions API, or both).

#### UET Tag ID

- **What this setting does:** This is your unique identifier provided by Microsoft Advertising. It tells Microsoft which account to associate the tracking data with.
- **Effect of changing this setting:**
  - *When entered correctly:* The module will embed the UET Tag on your store, allowing Microsoft Advertising to track user behavior.
  - *When left empty or incorrect:* No UET Tag tracking will occur, and your Microsoft Advertising campaigns will not receive front-office conversion data.
- **Recommended value:** Your exact UET Tag ID from your Microsoft Advertising account.
- **Merchant scenario / example:** You’ve created a Microsoft Advertising account and set up a UET Tag. You copy the ID (e.g., `12345678`) and paste it here.

#### Tracking Mode (UET Tag, Conversions API, or Both)

- **What this setting does:** Determines how conversion data is sent to Microsoft Advertising.
  - **UET Tag Only:** Traditional client-side tracking via JavaScript in the customer’s browser.
  - **Conversions API Only:** Server-side tracking, sending data directly from your PrestaShop server to Microsoft. More resilient to browser privacy settings.
  - **Both (Hybrid):** Uses both UET Tag and Conversions API, with a mechanism to deduplicate events, ensuring accurate counting even if both methods report the same conversion.
- **Effect of changing this setting:**
  - *UET Tag Only:* Relies solely on browser-based tracking, which can be affected by ad blockers or privacy settings.
  - *Conversions API Only:* Provides more robust tracking, but requires server-side setup and may not capture all client-side events (like page views) as easily.
  - *Both (Hybrid):* Offers the most comprehensive and reliable tracking, combining the strengths of both methods while preventing duplicate conversions.
- **Recommended value:** **Both (Hybrid)** is generally recommended for maximum accuracy and resilience.
- **Merchant scenario / example:** You want the most accurate data possible, so you select “Both (Hybrid)” to ensure conversions are tracked even if a customer uses an ad blocker.

#### Conversions API Access Token

- **What this setting does:** This is a secure token generated in your Microsoft Advertising account, authorizing your PrestaShop store to send data directly to Microsoft’s servers via the Conversions API.
- **Effect of changing this setting:**
  - *When entered correctly:* Enables server-side tracking for the Conversions API.
  - *When left empty or incorrect:* The Conversions API will not function, and server-side conversion data will not be sent.
- **Recommended value:** Your exact Conversions API Access Token from your Microsoft Advertising account.
- **Merchant scenario / example:** You’ve generated an Access Token in your Microsoft Advertising account (e.g., under “Tools” > “Conversion Tracking” > “Conversions API”). You paste this long string of characters here.

#### Enable Enhanced Conversions

- **What this setting does:** When enabled, this feature sends hashed customer data (like email addresses) along with conversion events. This helps Microsoft match conversions more accurately, especially when cookies are limited, improving your campaign performance.
- **Effect of changing this setting:**
  - *When enabled:* More accurate conversion matching, potentially leading to better optimization of your ad campaigns.
  - *When disabled:* Conversions rely solely on standard tracking methods, which might be less accurate in certain privacy-focused browser environments.
- **Recommended value:** **YES** (Enabled), as it significantly improves data matching.
- **Merchant scenario / example:** You want to give Microsoft Advertising the best possible data to optimize your campaigns, so you enable Enhanced Conversions.

#### Consent Management Integration

- **What this setting does:** This module can integrate with existing cookie consent modules (like GDPR modules) to ensure the UET Tag only fires after a customer has given their consent.
- **Effect of changing this setting:**
  - *When enabled and integrated:* The UET Tag will respect customer consent choices. If a customer declines tracking cookies, the UET Tag will not load.
  - *When disabled or not integrated:* The UET Tag might load regardless of consent, potentially leading to compliance issues.
- **Recommended value:** **YES** (Enabled) if you use a cookie consent module and need to comply with privacy regulations (e.g., GDPR, CCPA).
- **Merchant scenario / example:** Your store uses a GDPR module. You enable this setting to ensure your Microsoft Advertising tracking is compliant with privacy laws.

#### Debug Mode

- **What this setting does:** Activates a special mode that displays detailed information about the UET Tag and Conversions API events directly on your front-office pages (visible only to you, the administrator, or specific IP addresses). This is invaluable for verifying that tracking is set up correctly.
- **Effect of changing this setting:**
  - *When enabled:* You will see a debug overlay or console messages on your store’s front-office, showing which events are being tracked and what data is being sent.
  - *When disabled:* The module operates silently, with no visible debug information.
- **Recommended value:** **NO** (Disabled) for live production stores. **YES** (Enabled) temporarily during setup and troubleshooting.
- **Merchant scenario / example:** You’ve just installed the module and want to confirm that “Add to Cart” events are being sent correctly. You enable Debug Mode, add a product to your cart, and check the debug output.

#### Event Mapping (Advanced)

- **What this setting does:** Allows you to customize how specific PrestaShop actions (e.g., “Product Added to Cart”) are mapped to Microsoft Advertising event names (e.g., “add\_to\_cart”). You can also define custom parameters to send with each event.
- **Effect of changing this setting:**
  - *When configured:* Ensures that your events are correctly categorized and enriched with relevant data in Microsoft Advertising.
  - *When misconfigured:* Events might not be tracked, or the data sent might be inaccurate, leading to poor campaign optimization.
- **Recommended value:** Use the default mappings unless you have a specific reason to change them based on your Microsoft Advertising setup.
- **Merchant scenario / example:** You want to send the product’s brand as a custom parameter with every “view\_item” event. You would configure this mapping here.

#### Linker Domains (Advanced)

- **What this setting does:** If you have multiple subdomains or related websites that share the same UET Tag, this setting helps ensure that user sessions are correctly linked across these domains.
- **Effect of changing this setting:**
  - *When configured:* Allows for seamless tracking of user journeys across multiple domains under your control.
  - *When not configured (and needed):* User sessions might be broken, leading to inaccurate conversion attribution.
- **Recommended value:** Leave empty unless you operate multiple subdomains or related sites that need cross-domain tracking.
- **Merchant scenario / example:** You have your main store at `shop.example.com` and a blog at `blog.example.com`, both using the same UET Tag. You would add `blog.example.com` to the linker domains list.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Main Config | UET Tag ID | Your Tag ID | Enables UET Tag tracking. Essential for client-side data. |
| Main Config | Tracking Mode | Both (Hybrid) | Selects UET Tag, Conversions API, or both for data transmission. Hybrid is most robust. |
| Main Config | Conversions API Access Token | Your Access Token | Authorizes server-side data sending to Microsoft. |
| Main Config | Enable Enhanced Conversions | YES | Improves conversion matching accuracy by sending hashed customer data. |
| Main Config | Consent Management Integration | YES (if applicable) | Ensures UET Tag respects customer privacy choices (GDPR, CCPA). |
| Main Config | Debug Mode | NO (YES for testing) | Displays tracking data on front-office for verification. |
| Main Config | Event Mapping | Default | Customizes how PrestaShop actions map to Microsoft events. |
| Main Config | Linker Domains | Empty (if not needed) | Enables cross-domain tracking for related websites. |

### 2.2 Dedicated Admin Screens & Controller Views

#### 2.2.1 AdminMybingAjaxController (Back Office > Modules > Microsoft Advertising UET Tag & Conversions API > Live Statistics / Health Score / Doctor / Data Quality)

This controller powers the dynamic, interactive sections of the module’s configuration, providing real-time insights and diagnostic tools. You won’t navigate to a separate menu item for this, but rather interact with specific tabs within the main module configuration.

- **Screen Name & Menu Location:** These are typically sub-tabs within the main module configuration page (e.g., “Live Statistics”, “Health Score”, “Data Quality Coach”, “Catalog Doctor”).
- **Available Actions & Settings:**
  - **Live Statistics:** Displays recent events sent to Microsoft Advertising, showing page views, add-to-carts, purchases, etc., in near real-time. This helps you confirm that events are firing correctly.
  - **Health Score:** Analyzes your tracking setup and provides a score based on best practices, highlighting potential issues or areas for improvement.
  - **Data Quality Coach:** Offers specific recommendations to improve the quality and completeness of the data you’re sending to Microsoft, especially for Enhanced Conversions.
  - **Catalog Doctor:** Helps diagnose issues with your product data that might affect product feed advertising or dynamic remarketing.
- **Effect of changes:** Interacting with these screens primarily provides information and diagnostic feedback. There are no direct “settings” to change here, but the insights gained will inform adjustments you might make in the main configuration or your product catalog.
- **Recommended workflow for daily store management:**
  - Regularly check **Live Statistics** after making changes or launching new campaigns to ensure events are being tracked.
  - Periodically review the **Health Score** and **Data Quality Coach** for recommendations to optimize your tracking setup.
  - If you encounter issues with product-related ads, consult the **Catalog Doctor**.

#### 2.2.2 index.php (Back Office > Modules > Microsoft Advertising UET Tag & Conversions API)

This refers to the main entry point for the module’s back-office interface, which is the configuration page itself. All the settings described in section 4.1 are managed through this main view. There isn’t a separate “index.php” screen to navigate to beyond the initial module configuration.

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My conversions aren’t showing up in Microsoft Advertising. What should I do?**
A:

1. **Check UET Tag ID & Access Token:** Double-check that your UET Tag ID and Conversions API Access Token are correctly entered in the module configuration. Even a single typo can prevent tracking.
2. **Verify Tracking Mode:** Ensure your “Tracking Mode” is set to “Both (Hybrid)” for maximum reliability.
3. **Enable Debug Mode:** Activate “Debug Mode” in the module settings and perform a test purchase on your store. Look for the debug overlay or console messages to see if events are firing.
4. **Clear Cache:** Go to **Advanced Parameters > Performance** in your PrestaShop Back Office and clear the Smarty cache and any other caches. Sometimes old settings can persist.
5. **Check Microsoft Advertising Account:** Log into your Microsoft Advertising account and check the UET Tag status and conversion goal setup. Ensure your conversion goals are correctly configured to match the events sent by the module (e.g., “Purchase”).

**Q: The module says “Consent Management Integration” is enabled, but I don’t have a GDPR module. Is this an issue?**
A: If you don’t have a dedicated cookie consent module installed and configured, this setting won’t have any practical effect. The module will assume consent by default. However, for legal compliance (e.g., GDPR, CCPA), it’s highly recommended to use a proper cookie consent module. If you install one later, this module will automatically integrate with it.

**Q: My custom theme looks a bit off after installing the module, or I see a blank page.**
A: This module primarily works in the background and should not affect your theme’s visual appearance.

1. **Clear Cache:** The most common fix for display issues after module installation is to clear your PrestaShop cache (**Advanced Parameters > Performance**).
2. **Check for Conflicts:** If the issue persists, temporarily disable other recently installed modules to check for conflicts.
3. **PHP Errors:** If you see a blank page, enable PHP error reporting on your server (or check your server’s error logs) to identify any critical errors.
   If the problem continues, contact MyPresta.eu support with details of your theme and any error messages.

**Q: How do I translate the module’s texts into other languages?**
A:

1. Go to **International > Translations** in your PrestaShop Back Office.
2. Select “Installed modules translations” as the type of translation.
3. Choose your theme, the language you want to translate, and then select “Microsoft Advertising UET Tag & Conversions API” from the module list.
4. You can then translate any visible strings used by the module.

**Q: Why is the “Data Quality Coach” or “Health Score” showing warnings?**
A: These tools are designed to help you optimize your tracking. Warnings often indicate:

- **Missing Enhanced Conversion Data:** Ensure customer data (like email) is available and being sent.
- **Product Data Issues:** Your product catalog might have missing GTINs, MPNs, or other identifiers crucial for product feed advertising.
- **Low Event Volume:** If your store has very little traffic, the tools might not have enough data to provide a comprehensive analysis.
  Address the specific recommendations provided by the tools to improve your data quality and tracking health.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The `Microsoft Advertising UET Tag & Conversions API` module (`mybing`) is built following PrestaShop’s MVC (Model-View-Controller) pattern, with a strong emphasis on modularity and extensibility. It utilizes a factory pattern for tracker instantiation (`MybingTrackerFactory`) to support different tracking modes (UET, CAPI, Hybrid) and leverages a robust event system (`MybingEvents`) to capture various e-commerce actions. Data quality and diagnostics are handled by dedicated classes (`MybingHealthScore`, `MybingDataQualityCoach`, `MybingCatalogDoctor`). The module integrates with PrestaShop’s hook system for front-office event injection and uses dedicated admin controllers for its advanced configuration and diagnostic tools.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `mybing/controllers/front/ajax.php`
  - **Class Name:** `MybingAjaxModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** Handles AJAX requests from the front-office, primarily for sending client-side events or data that cannot be directly handled by the UET tag (e.g., for consent management integration, or specific data collection before a page redirect). It might also be used for sending CAPI events that are triggered client-side but need server-side processing.
- `mybing/controllers/front/cron.php`
  - **Class Name:** `MybingCronModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** Provides an endpoint for a cron job. This is typically used for server-side tasks that need to run periodically, such as sending deferred Conversions API events, synchronizing data, or performing maintenance tasks related to the module’s functionality.
- `mybing/controllers/front/index.php`
  - **Class Name:** `MybingIndexModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** A generic front controller, often used as a fallback or for simple, non-AJAX front-office interactions. In this module, it might be used for specific redirects or to handle initial requests related to tracking setup.

#### Back-Office Admin Controllers

- `mybing/controllers/admin/AdminMybingAjaxController.php`
  - **Class Name:** `AdminMybingAjaxController` (extends `AdminController`)
  - **Tab Name:** Not a standalone tab, but an AJAX endpoint for the main module configuration.
  - **Managed Entity:** Handles dynamic data loading and processing for the module’s diagnostic and statistics tabs (Live Statistics, Health Score, Data Quality Coach, Catalog Doctor). It processes requests for event logs, health checks, and data quality reports, returning JSON responses to the admin JavaScript.
- `mybing/controllers/admin/index.php`
  - **Class Name:** `AdminMybingIndexController` (extends `AdminController`)
  - **Tab Name:** Not a standalone tab. This is a placeholder or a generic admin controller that might be used for specific internal redirects or actions within the module’s admin interface, but the primary configuration is handled by the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)

- `mybing/classes/autoload.php`: Standard PrestaShop autoload file, ensuring module classes are loaded correctly.
- `mybing/classes/index.php`: Placeholder file, often to prevent directory listing.
- `mybing/classes/MybingCapiClient.php`: Handles the communication with the Microsoft Advertising Conversions API endpoint. Encapsulates HTTP requests, authentication (Access Token), and data formatting for server-side event submission.
- `mybing/classes/MybingCapiTracker.php`: Implements `MybingTrackerInterface` for server-side (Conversions API) tracking. Responsible for collecting event data, preparing it for the CAPI client, and sending it.
- `mybing/classes/MybingCatalogDoctor.php`: Provides diagnostic logic for analyzing product data quality, identifying issues that might affect product feeds or dynamic remarketing in Microsoft Advertising.
- `mybing/classes/MybingConsent.php`: Manages integration with cookie consent modules. Determines if user consent has been given for tracking and controls the firing of the UET tag accordingly.
- `mybing/classes/MybingCurrencyHelper.php`: Utility class for handling currency conversions and formatting, ensuring event values are sent correctly to Microsoft Advertising.
- `mybing/classes/MybingDataQualityCoach.php`: Analyzes the quality and completeness of data being sent for events, especially for Enhanced Conversions, and provides recommendations for improvement.
- `mybing/classes/MybingEventId.php`: Generates and manages unique event IDs for deduplication, crucial for hybrid tracking (UET + CAPI).
- `mybing/classes/MybingEventMap.php`: Defines the mapping between PrestaShop actions (e.g., `actionCartSave`) and Microsoft Advertising event names (e.g., `add_to_cart`), including custom parameters.
- `mybing/classes/MybingEvents.php`: Central class for defining and triggering all tracked e-commerce events (e.g., `PageView`, `AddToCart`, `Purchase`). It acts as an event dispatcher within the module.
- `mybing/classes/MybingHealthScore.php`: Calculates a “health score” for the overall tracking setup, evaluating configuration, data quality, and event firing.
- `mybing/classes/MybingHybridTracker.php`: Implements `MybingTrackerInterface` for hybrid tracking. Orchestrates both UET Tag and Conversions API tracking, ensuring event deduplication using `event_id`.
- `mybing/classes/MybingLiveStats.php`: Collects and provides real-time statistics on events being tracked, displayed in the admin interface.
- `mybing/classes/MybingProductIdResolver.php`: Helps resolve and format product IDs according to Microsoft Advertising’s requirements (e.g., GTIN, MPN, custom\_label).
- `mybing/classes/MybingPropertyRules.php`: Defines rules and logic for extracting and formatting various event properties (e.g., product price, quantity, category) for Microsoft Advertising.
- `mybing/classes/MybingTrackerFactory.php`: Factory class responsible for creating the appropriate tracker instance (`MybingUetTracker`, `MybingCapiTracker`, or `MybingHybridTracker`) based on the module’s configuration.
- `mybing/classes/MybingTrackerInterface.php`: Defines the contract for all tracker classes, ensuring a consistent interface for event tracking methods.
- `mybing/classes/MybingUetTracker.php`: Implements `MybingTrackerInterface` for client-side (UET Tag) tracking. Responsible for generating the JavaScript code to be injected into the front-office.
- `mybing/classes/MybingUserData.php`: Collects and formats user-specific data (e.g., email, phone, address) for Enhanced Conversions, including hashing.

### 4.4 JavaScript Assets (`views/js/`)

- `mybing/views/js/mybing-admin.js`: Back-office JavaScript for general admin functionality, form interactions, and dynamic updates within the module configuration page.
- `mybing/views/js/mybing-debug.js`: Front-office JavaScript specifically for the debug mode, displaying tracking information and event payloads to the administrator.
- `mybing/views/js/mybing-ghost.js`: Front-office JavaScript, potentially for handling “ghost” events or specific client-side interactions that need to be tracked without direct user action.
- `mybing/views/js/mybing-live.js`: Back-office JavaScript for the “Live Statistics” tab, handling AJAX requests to `AdminMybingAjaxController` and updating the live event feed.
- `mybing/views/js/mybing-tcf.js`: Front-office JavaScript for integration with Transparency and Consent Framework (TCF) or other consent management platforms, ensuring UET Tag fires only with consent.
- `mybing/views/js/mybing-wizard.js`: Back-office JavaScript for the initial setup wizard, guiding the merchant through the configuration steps.
- `mybing/views/js/mybing.js`: Main front-office JavaScript file. Contains the core logic for initializing the UET Tag, capturing client-side events (e.g., `add_to_cart`), and sending data to the UET Tag or the module’s AJAX controller for CAPI processing. It binds to various DOM events and PrestaShop’s `prestashop.on` events.

### 4.5 CSS Stylesheets (`views/css/`)

- `mybing/views/css/mybing-admin.css`: Back-office CSS for styling the module’s configuration page, diagnostic tools, and wizard, ensuring a consistent and user-friendly admin interface.
- `mybing/views/css/mybing-debug.css`: Front-office CSS for styling the debug overlay, making tracking information clearly visible to the administrator without disrupting the store’s design.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `mybing/views/templates/hook/capi-pageview.tpl`: Renders a hidden element or script to trigger a server-side PageView event via CAPI, often used when the UET tag might be blocked.
- `mybing/views/templates/hook/debug.tpl`: Renders the HTML structure for the front-office debug overlay, displaying event data.
- `mybing/views/templates/hook/displayOrderConfirmation.tpl`: Injected into the `displayOrderConfirmation` hook. Renders the UET Tag purchase event script and/or triggers the CAPI purchase event after a successful order.
- `mybing/views/templates/hook/ghost.tpl`: Renders a hidden script or element for “ghost” tracking, potentially for specific background events or data collection.
- `mybing/views/templates/hook/header.tpl`: Injected into the `displayHeader` hook. Renders the main UET Tag base script, consent management integration, and initial PageView events.
- `mybing/views/templates/hook/payment.tpl`: Potentially used for tracking events related to payment method selection or initiation, though `displayOrderConfirmation` is more common for final purchase.
- `mybing/views/templates/hook/product-details.tpl`: Injected into a product page hook (e.g., `displayProductButtons` or `displayProductExtraContent`). Renders scripts for `view_item` events and `add_to_cart` event listeners.

#### Admin templates (`views/templates/admin/`)

- `mybing/views/templates/admin/consent-guide.tpl`: Displays guidance and information regarding consent management integration.
- `mybing/views/templates/admin/doctor.tpl`: Renders the interface for the “Catalog Doctor” diagnostic tool.
- `mybing/views/templates/admin/dq.tpl`: Renders the interface for the “Data Quality Coach” recommendations.
- `mybing/views/templates/admin/health.tpl`: Renders the interface for the “Health Score” overview.
- `mybing/views/templates/admin/linker-domains.tpl`: Renders the input field and explanation for configuring linker domains.
- `mybing/views/templates/admin/live-maintain.tpl`: Renders a maintenance message or status for the live statistics feature.
- `mybing/views/templates/admin/live.tpl`: Renders the interface for “Live Statistics,” displaying recent events.
- `mybing/views/templates/admin/mode-context.tpl`: Provides contextual information about the chosen tracking mode.
- `mybing/views/templates/admin/mode-note-both.tpl`: Displays a specific note or explanation when “Both (Hybrid)” mode is selected.
- `mybing/views/templates/admin/mode-note-capi.tpl`: Displays a specific note or explanation when “Conversions API Only” mode is selected.
- `mybing/views/templates/admin/mode-note-uet.tpl`: Displays a specific note or explanation when “UET Tag Only” mode is selected.
- `mybing/views/templates/admin/mode-picker.tpl`: Renders the radio buttons or dropdown for selecting the tracking mode.
- `mybing/views/templates/admin/properties-list.tpl`: Renders a list or table of event properties and their values for configuration or display.
- `mybing/views/templates/admin/recent-events.tpl`: Renders a table or list of recently tracked events, often part of the “Live Statistics.”
- `mybing/views/templates/admin/tabs.tpl`: Renders the tab navigation structure for the module’s configuration page (e.g., General, Live Stats, Health Score).
- `mybing/views/templates/admin/tag-chips.tpl`: Renders visual “chips” or indicators for configured UET Tag IDs.
- `mybing/views/templates/admin/tag-ids.tpl`: Renders the input field for UET Tag IDs.
- `mybing/views/templates/admin/wizard.tpl`: Renders the step-by-step interface for the initial setup wizard.

#### Front-office templates (`views/templates/front/`)

- No dedicated standalone page templates identified. Front-office rendering is primarily handled via hook templates.

### 4.7 Database Schema & Hooks Map

#### Database Tables

The module does not explicitly create custom SQL tables based on the provided inventory. Configuration records are stored in PrestaShop’s `ps_configuration` table, using keys prefixed with `MYBING_` (e.g., `MYBING_UET_ID`, `MYBING_CAPI_TOKEN`, `MYBING_TRACKING_MODE`).

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Injects the base UET Tag JavaScript, initializes consent management, and triggers `PageView` events. |
| `displayOrderConfirmation` | On the order confirmation page after a successful purchase. | Triggers `Purchase` events for both UET Tag and Conversions API, including order details. |
| `actionFrontControllerSetMedia` | When a front controller sets its media assets. | Injects module-specific JavaScript and CSS into the front-office. |
| `actionCartSave` | When a product is added to or removed from the cart. | Triggers `AddToCart` or `RemoveFromCart` events. |
| `actionProductAdd` | When a product is added to the cart (specific to some themes/modules). | Alternative or supplementary hook for `AddToCart` events. |
| `actionProductUpdate` | When a product is updated in the Back Office. | Potentially used for `Catalog Doctor` to re-evaluate product data quality. |
| `actionObjectProductUpdateAfter` | After a product `ObjectModel` is updated. | Similar to `actionProductUpdate`, for data quality checks or cache invalidation. |
| `actionObjectOrderAddAfter` | After an order `ObjectModel` is added. | Triggers server-side `Purchase` events via Conversions API, ensuring robust tracking. |
| `actionObjectOrderUpdateAfter` | After an order `ObjectModel` is updated. | Potentially for tracking order status changes (e.g., refund, cancellation) if configured in Microsoft Ads. |
| `displayProductExtraContent` | On the product page, often below the main content. | Can be used to inject product-specific tracking scripts or data for `ViewItem` events. |
| `displayFooter` | At the end of the `<body>` section on every front-office page. | Can be used for deferred script loading or additional tracking elements. |
| `actionAdminControllerSetMedia` | When an admin controller sets its media assets. | Injects module-specific JavaScript and CSS into the Back Office for the configuration page. |
| `actionAdminMybingAjaxController` | Custom hook for `AdminMybingAjaxController` to handle specific AJAX actions. | Used internally for dynamic updates and data retrieval in the module’s diagnostic tabs. |
| `actionModuleInstall` | During module installation. | Performs initial setup, creates configuration entries, and registers hooks. |
| `actionModuleUninstall` | During module uninstallation. | Cleans up configuration entries and unregisters hooks. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official developer support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any technical issues or questions regarding the module’s functionality.
