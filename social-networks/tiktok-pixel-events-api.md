---
title: "TikTok Pixel / Events API - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the TikTok Pixel / Events API PrestaShop module by MyPresta.eu."
sidebar:
  label: "TikTok Pixel / Events API - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy TikTok Pixel / Events API Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/tiktok-pixel-events-api.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/tiktok-pixel-events-api/)
>
> ---


# TikTok Pixel / Events API

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required for the module to function correctly, especially for the Events API (server-side tracking). These are typically available on most modern hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration area where you’ll set up your TikTok Pixel and Events API. The settings are designed to be intuitive, guiding you through the process of connecting your store to TikTok Ads.

#### **General Settings**

- **TikTok Pixel ID:**

  - **What this setting does:** This is your unique identifier provided by TikTok Ads Manager. It tells TikTok which ad account your website data belongs to.
  - **Effect of changing this setting:**
    - *When entered:* The module will start sending data to your specified TikTok Pixel.
    - *When left empty:* No data will be sent to TikTok via the Pixel, and the module will not function for browser-side tracking.
  - **Recommended value:** Your valid TikTok Pixel ID.
  - **Merchant scenario / example:** You create a TikTok Ad account and set up a Pixel. TikTok provides you with a numerical ID (e.g., `1234567890`). You enter this ID here to link your store to your TikTok account.
- **TikTok Access Token (for Events API):**

  - **What this setting does:** This is a secure token generated in your TikTok Ads Manager that authorizes your PrestaShop store to send data directly to TikTok’s servers via the Events API. It’s crucial for server-side tracking.
  - **Effect of changing this setting:**
    - *When entered:* Enables server-side tracking (Events API), which is more reliable and less affected by ad blockers.
    - *When left empty:* Server-side tracking will be disabled.
  - **Recommended value:** Your valid TikTok Events API Access Token.
  - **Merchant scenario / example:** To improve data accuracy and bypass browser limitations, you decide to use the Events API. You generate an Access Token in TikTok Ads Manager and paste it here.
- **Tracking Mode:**

  - **What this setting does:** Determines how data is sent to TikTok. You can choose between Pixel (browser-side), Events API (server-side), or Dual Mode (both).
  - **Effect of changing this setting:**
    - *Pixel Only:* Only browser-side tracking is active.
    - *Events API Only:* Only server-side tracking is active.
    - *Dual Mode (Recommended):* Both Pixel and Events API are active. The module intelligently uses a shared `event_id` to deduplicate events in TikTok, ensuring accuracy.
  - **Recommended value:** `Dual Mode` for maximum data accuracy and resilience against ad blockers.
  - **Merchant scenario / example:** You want the most reliable tracking possible. You select “Dual Mode” so that if a customer uses an ad blocker, the server-side Events API can still capture the conversion, and TikTok won’t count it twice if both methods succeed.
- **Enable Debug Mode:**

  - **What this setting does:** Activates a special mode that displays detailed information about the TikTok events being sent, directly in your browser’s developer console. This is invaluable for troubleshooting.
  - **Effect of changing this setting:**
    - *When enabled:* Developers and advanced users can see exactly what data is being sent to TikTok in real-time, helping to verify correct setup.
    - *When disabled:* No debug information is displayed.
  - **Recommended value:** `No` for live production stores. Only enable temporarily for testing and debugging.
  - **Merchant scenario / example:** You’ve just installed the module and want to ensure `AddToCart` events are firing correctly. You enable debug mode, add an item to your cart, and check your browser console for the TikTok event data.

#### **Advanced Settings**

- **Consent Management (GDPR/CCPA):**

  - **What this setting does:** Integrates with your store’s cookie consent solution (if available) to ensure TikTok tracking only activates after a customer has given their consent.
  - **Effect of changing this setting:**
    - *When enabled:* The TikTok Pixel/Events API will only load and send data if the customer has accepted cookies.
    - *When disabled:* Tracking will occur regardless of cookie consent, which might not be compliant with privacy regulations like GDPR or CCPA.
  - **Recommended value:** `Yes` if your store operates in regions with strict privacy laws (e.g., EU, California).
  - **Merchant scenario / example:** Your store serves customers in the European Union. To comply with GDPR, you enable this setting, ensuring that TikTok tracking respects user privacy choices.
- **Product ID Type:**

  - **What this setting does:** Determines which product identifier (ID) is sent to TikTok. Options typically include PrestaShop’s internal product ID, EAN13, UPC, or a custom reference. This is crucial for matching products in your TikTok Product Catalog.
  - **Effect of changing this setting:**
    - *Changing the type:* Ensures that the product IDs sent to TikTok match the IDs used in your TikTok Product Catalog, enabling dynamic product ads.
  - **Recommended value:** Choose the ID type that you use in your TikTok Product Catalog. Often, PrestaShop’s `Product ID` or `EAN13` are common choices.
  - **Merchant scenario / example:** You’ve uploaded a product catalog to TikTok using your products’ EAN13 codes. You select `EAN13` here to ensure TikTok can correctly identify which products customers are viewing or purchasing.
- **Linker Domains (for cross-domain tracking):**

  - **What this setting does:** Allows you to specify additional domain names if your customer journey involves multiple domains (e.g., a main store and a separate blog on a different domain). This helps TikTok track users seamlessly across these domains.
  - **Effect of changing this setting:**
    - *When domains are added:* TikTok can maintain user tracking consistency across the listed domains.
    - *When left empty:* Tracking might break if customers navigate between different domains that are part of your business.
  - **Recommended value:** Add any relevant subdomains or linked domains your customers might visit.
  - **Merchant scenario / example:** Your main store is `mystore.com`, but you have a blog at `blog.mystore.com` where you link to products. Adding `blog.mystore.com` here ensures TikTok can track users from the blog to your store.

#### **Data Quality & Health Score**

This section provides insights into the performance and accuracy of your TikTok tracking.

- **Health Score:**

  - **What this does:** Displays a score indicating the overall health and accuracy of your data transmission to TikTok. A higher score means better data quality.
  - **Effect:** Helps you quickly identify if there are issues with your tracking setup that might impact ad performance.
  - **Recommended:** Aim for a high score. The module will provide recommendations if the score is low.
- **Recovery Radar:**

  - **What this does:** Monitors abandoned carts and provides insights into potential lost sales, helping you identify opportunities for retargeting campaigns.
  - **Effect:** Gives you a quick overview of how many carts are initiated versus completed, highlighting areas for improvement in your checkout process or retargeting strategy.
- **Live Statistics:**

  - **What this does:** Shows real-time data on events being sent to TikTok, allowing you to see if events are firing as expected.
  - **Effect:** Provides immediate feedback during testing and ongoing monitoring, confirming that your tracking is active and accurate.

### 2.2 Dedicated Admin Screens & Controller Views

The module extends the PrestaShop Back Office with several dedicated screens to help you manage and monitor your TikTok integration. These are typically accessible from the module’s configuration page via tabs or dedicated menu items.

#### **AdminMytiktokAjaxController (Ajax Operations)**

- **Screen Name & Menu Location:** This controller primarily handles background AJAX requests from the module’s configuration page. You won’t directly navigate to a “screen” for this, but it powers the dynamic updates and data retrieval within the main module configuration tabs (e.g., Live Statistics, Health Score, Event Logs).
- **Available Actions & Settings:** It processes requests for:
  - Fetching live event data.
  - Updating health scores.
  - Retrieving diagnostic information.
  - Saving specific configuration parts without a full page reload.
- **Effect of changes:** Interactions on the main module configuration page (like refreshing live stats or running diagnostics) trigger this controller to fetch and display the relevant data.
- **Recommended workflow for daily store management:** You interact with this indirectly by using the various diagnostic and monitoring tools provided on the main module configuration page.

#### **index.php (Main Module Entry Point)**

- **Screen Name & Menu Location:** This is the primary entry point for the module’s configuration, accessible via **Back Office > Modules > Module Manager > Configure (for TikTok Pixel / Events API)**.
- **Available Actions & Settings:** This screen presents all the general and advanced settings described in section 4.1, organized into logical tabs or sections. It also hosts the various diagnostic tools like Health Score, Live Statistics, and Recovery Radar.
- **Effect of changes:** Any changes saved on this screen directly impact how your TikTok Pixel and Events API function on your storefront.
- **Recommended workflow for daily store management:**
  1. **Initial Setup:** Configure your Pixel ID, Access Token, and Tracking Mode.
  2. **Regular Monitoring:** Periodically check the “Health Score” and “Live Statistics” tabs to ensure data quality and event firing.
  3. **Troubleshooting:** Use the “Debug Mode” (temporarily) and “Live Statistics” to diagnose any tracking issues.
  4. **Optimization:** Review “Recovery Radar” insights to inform your retargeting strategies.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | TikTok Pixel ID | Your Pixel ID | Links your store to your TikTok Ad account for browser tracking. |
| Module Configuration | TikTok Access Token | Your Access Token | Authorizes server-side tracking via Events API. |
| Module Configuration | Tracking Mode | Dual Mode | Determines if Pixel, Events API, or both are used for tracking. Dual mode is recommended for accuracy. |
| Module Configuration | Enable Debug Mode | No (for production) | Shows detailed event data in browser console for troubleshooting. |
| Module Configuration | Consent Management | Yes (for GDPR/CCPA) | Ensures tracking respects user cookie consent. |
| Module Configuration | Product ID Type | Matching your Catalog | Selects the product identifier sent to TikTok for catalog matching. |
| Module Configuration | Linker Domains | Empty (add if needed) | Allows cross-domain tracking for complex site structures. |
| Module Configuration | Health Score | High score | Indicates overall data quality and tracking accuracy. |
| Module Configuration | Recovery Radar | Monitor | Insights into abandoned carts for retargeting. |
| Module Configuration | Live Statistics | Monitor | Real-time view of events sent to TikTok. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve installed the module, but I don’t see any data in my TikTok Ads Manager. What should I do?**

- **A:** First, double-check that your **TikTok Pixel ID** and **Access Token** are correctly entered in the module configuration. Ensure there are no typos.
- Next, verify your **Tracking Mode** is set to “Dual Mode” or “Pixel” (if you’re only using the Pixel).
- Enable **Debug Mode** in the module settings, then visit your store’s front office, perform some actions (like viewing a product, adding to cart), and check your browser’s developer console (usually F12 > Console tab) for TikTok event messages.
- Finally, clear your PrestaShop cache (**Advanced Parameters > Performance > Clear cache**).

**Q2: My TikTok Health Score is low. How can I improve it?**

- **A:** A low Health Score often indicates issues with data quality or event delivery.
- **Check for missing data:** Ensure all required product information (price, currency, name) is complete for your products.
- **Verify consent:** If you have “Consent Management” enabled, make sure your cookie consent banner is working correctly and users are accepting cookies.
- **Review Live Statistics:** Look for any errors or missing events in the “Live Statistics” section of the module.
- The module itself often provides specific recommendations within the Health Score section to guide you.

**Q3: Will this module slow down my website?**

- **A:** The module is designed to be lightweight and efficient. Browser-side Pixel tracking might add a small, negligible load, similar to any other analytics script. The server-side Events API has virtually no impact on front-office loading times as data is sent from your server directly. We recommend using “Dual Mode” for optimal performance and data accuracy.

**Q4: I have a custom theme. Will the module work correctly?**

- **A:** Yes, the module is designed to integrate seamlessly with standard PrestaShop themes and most custom themes. It uses PrestaShop’s official hook system to inject its scripts and tracking code.
- If you encounter any issues with a highly customized theme, especially if it significantly alters core PrestaShop templates for product pages or checkout, you might need to consult with a developer to ensure the hooks are still present and correctly rendered.

**Q5: How does the module handle multi-language and multi-currency stores?**

- **A:** The module is built to be fully compatible with PrestaShop’s multi-language and multi-currency features. It automatically detects the active language and currency on the front office and sends this information to TikTok, ensuring your event data is accurate and localized. Product names and values will be sent in the context of the customer’s selected language and currency.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the TikTok Pixel / Events API module, intended for developers, webmasters, and technical agencies.

### 4.1 Architecture Overview

The `mytiktok` module follows a standard PrestaShop module architecture, leveraging the MVC pattern where appropriate. It primarily functions as an event tracker, injecting JavaScript for client-side (Pixel) tracking and utilizing server-side logic for the Events API. Key components include:

- **Main Module Class (`index.php`):** Handles installation, uninstallation, configuration, and hook registration.
- **Controllers:** Front controllers for AJAX requests and admin controllers for back-office management.
- **Core Classes:** A robust set of classes (`classes/`) for managing API communication, event mapping, data quality, consent, and various tracking strategies (Pixel, CAPI, Hybrid).
- **Templates:** Smarty templates for both front-office hook injection and back-office configuration views.
- **Assets:** Dedicated JS and CSS for admin interfaces and front-office debugging/tracking.

The module implements a `MytiktokTrackerInterface` and uses a `MytiktokTrackerFactory` to abstract different tracking modes (Pixel, CAPI, Hybrid), promoting a clean and extensible design. It also includes sophisticated data quality and health monitoring tools.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `mytiktok/controllers/front/ajax.php`
  - **Class name & parent class:** `MytiktokAjaxModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** Handles asynchronous requests from the front-office, primarily for server-side event tracking (Events API) or data collection that doesn’t require a full page reload. It might process data submitted by JavaScript and forward it to the TikTok Events API.
- `mytiktok/controllers/front/index.php`
  - **Class name & parent class:** `MytiktokIndexModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** This controller might serve as a fallback or a specific endpoint for certain front-office interactions, though `ajax.php` is typically more active for event handling. It could be used for specific redirects or initializations if needed.

#### Back-Office Admin Controllers

- `mytiktok/controllers/admin/AdminMytiktokAjaxController.php`
  - **Class name & parent class:** `AdminMytiktokAjaxController` extends `ModuleAdminController`.
  - **Tab name and managed entity:** This controller is not directly accessible as a menu tab. It handles AJAX requests originating from the module’s main configuration page (`index.php`) in the back office. It’s responsible for dynamic updates, fetching live statistics, health scores, event logs, and other diagnostic data without requiring a full page refresh.
- `mytiktok/controllers/admin/index.php`
  - **Class name & parent class:** `AdminMytiktokController` extends `ModuleAdminController`.
  - **Tab name and managed entity:** This is the primary admin controller for the module’s configuration. It’s the controller that `index.php` (the main module file) dispatches to when the “Configure” button is clicked. It manages the display of all configuration forms, tabs (e.g., General Settings, Data Quality, Live Stats), and handles saving the module’s settings.

### 4.3 Core Classes & Models (`classes/`)

- `mytiktok/classes/autoload.php`: Standard PrestaShop autoload file, ensuring module classes are loaded correctly.
- `mytiktok/classes/index.php`: Empty file, often used to prevent directory listing.
- `mytiktok/classes/MytiktokCapiClient.php`:
  - **Database table:** None directly.
  - **Extends ObjectModel:** No.
  - **Key public methods:** Handles communication with the TikTok Events API (CAPI). Contains methods for sending event data, managing authentication with the Access Token, and handling API responses.
- `mytiktok/classes/MytiktokCapiTracker.php`:
  - **Database table:** None directly.
  - **Extends ObjectModel:** No.
  - **Key public methods:** Implements `MytiktokTrackerInterface`. Responsible for preparing and sending server-side events to TikTok via `MytiktokCapiClient`.
- `mytiktok/classes/MytiktokCatalogDoctor.php`:
  - **Database table:** None directly.
  - **Extends ObjectModel:** No.
  - **Key public methods:** Provides diagnostic tools and recommendations related to product catalog data, ensuring product IDs and attributes are correctly formatted for TikTok.
- `mytiktok/classes/MytiktokConsent.php`:
  - **Database table:** None directly.
  - **Extends ObjectModel:** No.
  - **Key public methods:** Manages cookie consent logic, integrating with PrestaShop’s consent mechanisms or custom consent modules to ensure GDPR/CCPA compliance.
- `mytiktok/classes/MytiktokCurrencyHelper.php`:
  - **Database table:** None directly.
  - **Extends ObjectModel:** No.
  - **Key public methods:** Utility class for handling currency formatting and conversions, ensuring event values are sent to TikTok in the correct format and currency.
- `mytiktok/classes/MytiktokDataQualityCoach.php`:
  - **Database table:** None directly.
  - **Extends ObjectModel:** No.
  - **Key public methods:** Analyzes the quality and completeness of data being sent to TikTok, providing insights and suggestions for improvement.
- `mytiktok/classes/MytiktokEventId.php`:
  - **Database table:** None directly.
  - **Extends ObjectModel:** No.
  - **Key public methods:** Generates and manages unique `event_id` values for events, crucial for deduplication in dual-mode tracking.
- `mytiktok/classes/MytiktokEventMap.php`:
  - **Database table:** None directly.
  - **Extends ObjectModel:** No.
  - **Key public methods:** Maps PrestaShop actions and data to standard TikTok event names and properties (e.g., `ViewContent`, `AddToCart`, `CompletePayment`).
- `mytiktok/classes/MytiktokEvents.php`:
  - **Database table:** None directly.
  - **Extends ObjectModel:** No.
  - **Key public methods:** Central class for triggering and managing various TikTok events based on user actions in PrestaShop.
- `mytiktok/classes/MytiktokHealthScore.php`:
  - **Database table:** None directly.
  - **Extends ObjectModel:** No.
  - **Key public methods:** Calculates and displays the overall health score of the TikTok integration based on data quality, event delivery, and configuration.
- `mytiktok/classes/MytiktokHybridTracker.php`:
  - **Database table:** None directly.
  - **Extends ObjectModel:** No.
  - **Key public methods:** Implements `MytiktokTrackerInterface`. Orchestrates dual-mode tracking, sending events via both Pixel and CAPI with `event_id` deduplication.
- `mytiktok/classes/MytiktokLiveStats.php`:
  - **Database table:** None directly.
  - **Extends ObjectModel:** No.
  - **Key public methods:** Collects and displays real-time statistics of events being sent to TikTok for monitoring purposes.
- `mytiktok/classes/MytiktokPixelTracker.php`:
  - **Database table:** None directly.
  - **Extends ObjectModel:** No.
  - **Key public methods:** Implements `MytiktokTrackerInterface`. Responsible for injecting and managing browser-side TikTok Pixel events.
- `mytiktok/classes/MytiktokProductIdResolver.php`:
  - **Database table:** None directly.
  - **Extends ObjectModel:** No.
  - **Key public methods:** Resolves the correct product ID based on the module’s configuration (e.g., PrestaShop ID, EAN13, UPC) for sending to TikTok.
- `mytiktok/classes/MytiktokPropertyRules.php`:
  - **Database table:** None directly.
  - **Extends ObjectModel:** No.
  - **Key public methods:** Defines and enforces rules for event properties, ensuring data sent to TikTok adheres to its specifications.
- `mytiktok/classes/MytiktokTrackerFactory.php`:
  - **Database table:** None directly.
  - **Extends ObjectModel:** No.
  - **Key public methods:** Factory pattern to instantiate the correct tracker class (`MytiktokPixelTracker`, `MytiktokCapiTracker`, or `MytiktokHybridTracker`) based on the module’s “Tracking Mode” configuration.
- `mytiktok/classes/MytiktokTrackerInterface.php`:
  - **Database table:** None directly.
  - **Extends ObjectModel:** No.
  - **Key public methods:** Defines the contract for all tracker classes, ensuring a consistent interface for sending events.
- `mytiktok/classes/MytiktokTrans.php`:
  - **Database table:** None directly.
  - **Extends ObjectModel:** No.
  - **Key public methods:** Utility class for handling module translations.
- `mytiktok/classes/MytiktokUserData.php`:
  - **Database table:** None directly.
  - **Extends ObjectModel:** No.
  - **Key public methods:** Collects and formats user data (e.g., email, phone, IP address) for enhanced matching in TikTok Events API.

### 4.4 JavaScript Assets (`views/js/`)

- `mytiktok/views/js/mytiktok-admin.js`:
  - **Scope:** Back-office.
  - **Description:** Handles interactive elements and AJAX calls within the module’s administration pages. This includes managing tabs, updating live statistics, handling form submissions, and wizard steps.
- `mytiktok/views/js/mytiktok-debug.js`:
  - **Scope:** Front-office (when debug mode is enabled).
  - **Description:** Injects debugging information into the browser console, logging TikTok events, their properties, and potential issues. Essential for verifying correct event firing.
- `mytiktok/views/js/mytiktok-ghost.js`:
  - **Scope:** Front-office.
  - **Description:** Potentially handles “ghost” or hidden tracking mechanisms, possibly related to server-side event initiation or specific user interactions that need to be captured without direct pixel interaction.
- `mytiktok/views/js/mytiktok-live.js`:
  - **Scope:** Back-office.
  - **Description:** Powers the “Live Statistics” feature in the admin panel, periodically fetching and displaying real-time event data.
- `mytiktok/views/js/mytiktok-tcf.js`:
  - **Scope:** Front-office.
  - **Description:** Integrates with Transparency and Consent Framework (TCF) or other cookie consent solutions to manage user consent before initializing TikTok Pixel.
- `mytiktok/views/js/mytiktok-wizard.js`:
  - **Scope:** Back-office.
  - **Description:** Manages the step-by-step setup wizard for initial module configuration, guiding the merchant through essential settings.
- `mytiktok/views/js/mytiktok.js`:
  - **Scope:** Front-office.
  - **Description:** The main front-office JavaScript file. It initializes the TikTok Pixel, triggers standard events (PageView, ViewContent, AddToCart, InitiateCheckout), and collects necessary data from the DOM to send to TikTok. It also handles the `event_id` generation for deduplication.

### 4.5 CSS Stylesheets (`views/css/`)

- `mytiktok/views/css/mytiktok-admin.css`:
  - **Scope:** Back-office admin form styling.
  - **Description:** Styles the module’s configuration page, including tabs, input fields, buttons, and diagnostic displays (Health Score, Live Statistics, etc.) to ensure a consistent and user-friendly interface within the PrestaShop back office.
- `mytiktok/views/css/mytiktok-debug.css`:
  - **Scope:** Front-office customer styling (only when debug mode is active).
  - **Description:** Provides minimal styling for any visual debugging elements that might appear on the front office when debug mode is enabled (e.g., a small overlay or banner indicating debug status).

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `mytiktok/views/templates/hook/capi-pageview.tpl`:
  - **Hook:** Potentially `displayHeader` or `displayBeforeBodyClosingTag`.
  - **Output:** Renders the server-side `PageView` event for the Events API. This template might contain hidden fields or data structures used by the server-side logic to initiate the CAPI PageView event.
- `mytiktok/views/templates/hook/debug.tpl`:
  - **Hook:** `displayHeader` or `displayBeforeBodyClosingTag`.
  - **Output:** Renders a small HTML block or script tag for debugging purposes, often including `mytiktok-debug.js` and initial debug data.
- `mytiktok/views/templates/hook/displayOrderConfirmation.tpl`:
  - **Hook:** `displayOrderConfirmation`.
  - **Output:** Renders the `CompletePayment` event data, including order value, currency, and product details, to be sent to TikTok Pixel and/or Events API after a successful purchase.
- `mytiktok/views/templates/hook/ghost.tpl`:
  - **Hook:** Various front-office hooks.
  - **Output:** Renders hidden elements or scripts for “ghost” tracking, potentially related to server-side event triggers or advanced data collection.
- `mytiktok/views/templates/hook/header.tpl`:
  - **Hook:** `displayHeader`.
  - **Output:** Injects the main TikTok Pixel base code, `mytiktok.js`, and initial configuration variables into the `<head>` section of all front-office pages. This is where the Pixel is initialized.
- `mytiktok/views/templates/hook/payment.tpl`:
  - **Hook:** Potentially `displayPaymentTop` or `displayPaymentOptions`.
  - **Output:** May render `InitiateCheckout` event data or related scripts when a customer reaches the payment selection step during checkout.
- `mytiktok/views/templates/hook/product-details.tpl`:
  - **Hook:** `displayProductAdditionalInfo` or similar product page hook.
  - **Output:** Renders the `ViewContent` event data, including product ID, name, price, and category, for the currently viewed product.

#### Admin templates (`views/templates/admin/`)

- `mytiktok/views/templates/admin/consent-guide.tpl`: Displays guidance on setting up cookie consent.
- `mytiktok/views/templates/admin/doctor.tpl`: Renders the “Catalog Doctor” diagnostic interface.
- `mytiktok/views/templates/admin/dq.tpl`: Displays data quality insights and recommendations.
- `mytiktok/views/templates/admin/health.tpl`: Renders the “Health Score” dashboard.
- `mytiktok/views/templates/admin/linker-domains.tpl`: Form field for configuring linker domains.
- `mytiktok/views/templates/admin/live-maintain.tpl`: Placeholder or maintenance view for live statistics.
- `mytiktok/views/templates/admin/live.tpl`: Displays the “Live Statistics” dashboard.
- `mytiktok/views/templates/admin/mode-context.tpl`: Contextual information about the selected tracking mode.
- `mytiktok/views/templates/admin/mode-note-both.tpl`: Note/explanation for “Dual Mode” tracking.
- `mytiktok/views/templates/admin/mode-note-capi.tpl`: Note/explanation for “Events API Only” tracking.
- `mytiktok/views/templates/admin/mode-note-pixel.tpl`: Note/explanation for “Pixel Only” tracking.
- `mytiktok/views/templates/admin/mode-picker.tpl`: The interface for selecting the tracking mode (Pixel, CAPI, Dual).
- `mytiktok/views/templates/admin/properties-list.tpl`: Displays a list of event properties.
- `mytiktok/views/templates/admin/recent-events.tpl`: Shows a log of recent events sent.
- `mytiktok/views/templates/admin/tabs.tpl`: Structure for the tabbed interface on the module configuration page.
- `mytiktok/views/templates/admin/tag-chips.tpl`: Visual components for displaying tags or IDs.
- `mytiktok/views/templates/admin/tag-ids.tpl`: Input fields for TikTok Pixel ID and Access Token.
- `mytiktok/views/templates/admin/wizard.tpl`: The step-by-step setup wizard interface.

#### Front-office templates (`views/templates/front/`)

- No dedicated standalone page templates are listed, as the module primarily injects scripts and data via hooks.

### 4.7 Database Schema & Hooks Map

#### Database Tables

The module primarily stores its configuration settings in PrestaShop’s `ps_configuration` table.

- `ps_configuration`: Stores key-value pairs for module settings, such as `MYTIKTOK_PIXEL_ID`, `MYTIKTOK_ACCESS_TOKEN`, `MYTIKTOK_TRACKING_MODE`, etc.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Initializes the TikTok Pixel base code, loads `mytiktok.js`, and sets up global configuration variables. |
| `displayBeforeBodyClosingTag` | Just before the `</body>` tag. | May inject additional scripts or data that needs to be executed after the DOM is loaded, or for CAPI PageView events. |
| `displayProductAdditionalInfo` | On the product page, typically near the product details. | Triggers the `ViewContent` event, passing product-specific data to TikTok. |
| `displayShoppingCartFooter` | On the cart page, usually below the cart summary. | Triggers the `AddToCart` event (if not already handled by AJAX) and potentially `InitiateCheckout`. |
| `displayPaymentTop` | At the top of the payment selection page during checkout. | Triggers the `InitiateCheckout` event. |
| `displayOrderConfirmation` | On the order confirmation page after a successful purchase. | Triggers the crucial `CompletePayment` event, sending full order details (value, products, currency) to TikTok. |
| `actionFrontControllerSetMedia` | When a front controller sets its media assets. | Injects module-specific JS/CSS files into the front office. |
| `actionAdminControllerSetMedia` | When an admin controller sets its media assets. | Injects module-specific JS/CSS files into the back office. |
| `actionValidateOrder` | After an order has been successfully validated. | Server-side trigger for the `CompletePayment` event via Events API, ensuring reliable conversion tracking. |
| `actionCartSave` | When the cart is updated (e.g., add/remove product). | Server-side trigger for `AddToCart` or `RemoveFromCart` events via Events API. |
| `actionProductUpdate` | When a product is updated in the back office. | Potentially used for catalog synchronization or data quality checks. |
| `actionObjectProductAddAfter` | After a new product is added. | Potentially used for catalog synchronization or data quality checks. |
| `actionObjectProductUpdateAfter` | After a product is updated. | Potentially used for catalog synchronization or data quality checks. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “TikTok Pixel / Events API” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our dedicated support team is available to assist you with any technical issues or questions regarding the module’s functionality.
