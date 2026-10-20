---
title: "Snapchat Pixel & Conversions API - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Snapchat Pixel & Conversions API PrestaShop module by MyPresta.eu."
sidebar:
  label: "Snapchat Pixel & Conversions API - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Snapchat Pixel & Conversions API Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/snapchat-pixel-conversions-api.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/snapchat-pixel-conversions-api/)
>
> ---


# Snapchat Pixel & Conversions API

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required. These are typically enabled by default on most modern hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen where you’ll set up your Snapchat Pixel and Conversions API. The module provides a user-friendly interface with various sections to guide you through the setup.

#### **1. General Settings & Tracking Mode**

- **Tracking Mode:**

  - **What this setting does:** Determines how your store sends data to Snapchat. You can choose between client-side (Pixel), server-side (Conversions API), or a hybrid approach.
  - **Effect of changing this setting:**
    - *Pixel Only:* Only the Snap Pixel (JavaScript code in the browser) will track events. This is simpler but more susceptible to ad blockers and browser restrictions.
    - *Conversions API Only:* Only server-side tracking will be used. This is more reliable for data privacy and accuracy but requires a robust server setup.
    - *Hybrid (Recommended):* Both Pixel and CAPI will track events. The module automatically deduplicates events using a shared `event_id`, ensuring accurate reporting while maximizing data capture. This is generally the most robust and recommended option.
  - **Recommended value:** `Hybrid`
  - **Merchant scenario / example:** If you’re just starting out, “Pixel Only” is quick. For serious advertising, “Hybrid” gives you the best of both worlds, ensuring you capture as much accurate data as possible for campaign optimization.
- **Snap Pixel ID:**

  - **What this setting does:** This is your unique identifier for your Snapchat Pixel. It tells Snapchat which ad account to associate the tracked events with.
  - **Effect of changing this setting:** If incorrect or empty, no client-side tracking will occur, and your Snapchat ads won’t be able to track website visitors or conversions.
  - **Recommended value:** Your Snap Pixel ID (e.g., `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`). You can find this in your Snapchat Ads Manager.
  - **Merchant scenario / example:** You’ve created an ad account on Snapchat and need to link your store to it. Enter the Pixel ID provided by Snapchat here.
- **Conversions API Token:**

  - **What this setting does:** This is a secure token that allows your server to send data directly to Snapchat’s Conversions API. It authenticates your server-side requests.
  - **Effect of changing this setting:** If incorrect or empty, no server-side tracking will occur. This means you lose out on the enhanced reliability and privacy benefits of CAPI.
  - **Recommended value:** Your Conversions API Token. You generate this in your Snapchat Ads Manager.
  - **Merchant scenario / example:** To ensure your purchase data is reliably sent to Snapchat even if a customer uses an ad blocker, you’ll need to set up and enter your CAPI token here.

#### **2. Event Tracking & Data Quality**

- **Enable Advanced Matching:**

  - **What this setting does:** Allows the module to send additional customer data (like email, phone number, name) to Snapchat, securely hashed, to improve event matching and audience building.
  - **Effect of changing this setting:**
    - *Enabled:* Snapchat can more accurately match website visitors to their Snapchat profiles, improving audience targeting and ad attribution.
    - *Disabled:* Less data is sent, potentially reducing the accuracy of audience matching and campaign optimization.
  - **Recommended value:** `YES` (unless you have strict privacy concerns that override the benefits).
  - **Merchant scenario / example:** You want Snapchat to be as effective as possible at finding customers similar to your existing ones. Enabling this helps Snapchat identify users more precisely.
- **Consent Management Integration:**

  - **What this setting does:** Integrates with popular cookie consent modules (e.g., GDPR modules) to ensure that Snapchat tracking only occurs after a customer has given their explicit consent.
  - **Effect of changing this setting:**
    - *Enabled:* The module will wait for consent before initializing the Snap Pixel or sending CAPI events that require user data.
    - *Disabled:* Tracking will occur regardless of user consent, which might lead to privacy compliance issues in some regions.
  - **Recommended value:** `YES` (highly recommended for GDPR, CCPA, and other privacy regulations).
  - **Merchant scenario / example:** Your store operates in the EU and needs to comply with GDPR. Enabling this ensures you only track users who have agreed to your cookie policy.
- **Product ID Type for Catalog Matching:**

  - **What this setting does:** Specifies which product identifier (e.g., Product ID, Product Reference, EAN/UPC) the module should send to Snapchat for product catalog matching. This is crucial for dynamic product ads.
  - **Effect of changing this setting:** If the ID type sent by the module doesn’t match the IDs in your Snapchat Product Catalog, your dynamic ads won’t display the correct products.
  - **Recommended value:** Choose the ID type that you use consistently in your Snapchat Product Catalog. Often, `Product ID` or `Product Reference` are good choices.
  - **Merchant scenario / example:** You’re running dynamic retargeting ads on Snapchat. If your product catalog uses the “Product Reference” as the unique identifier, you must select “Product Reference” here for the ads to show the right products to customers.
- **Enable Debug Mode:**

  - **What this setting does:** Activates a special mode that displays detailed information about the events being sent to Snapchat directly in your browser’s developer console.
  - **Effect of changing this setting:**
    - *Enabled:* You’ll see real-time feedback on what data is being sent, helping you troubleshoot and verify your setup. This is visible only to you (or anyone with developer tools open).
    - *Disabled:* No debug information is displayed.
  - **Recommended value:** `NO` for live stores. `YES` during initial setup and troubleshooting.
  - **Merchant scenario / example:** After installing the module, you want to confirm that “Add to Cart” events are firing correctly. You enable debug mode, add a product to your cart, and check the console for the event details.

#### **3. Advanced Features**

- **Ghost Collector (ScCid Matching):**

  - **What this setting does:** Improves the accuracy of matching users across different sessions and devices by creating a unique, anonymous identifier (ScCid) and storing it in a first-party cookie.
  - **Effect of changing this setting:**
    - *Enabled:* Better attribution and audience building, especially in scenarios where third-party cookies are restricted.
    - *Disabled:* Snapchat’s ability to track users across sessions might be less accurate.
  - **Recommended value:** `YES`
  - **Merchant scenario / example:** A customer visits your store, leaves, and comes back later from a different device. Ghost Collector helps Snapchat recognize them as the same user, improving your retargeting efforts.
- **Linker Domains (Cross-Domain Tracking):**

  - **What this setting does:** Allows you to specify additional domains (e.g., a separate blog, a subdomain for specific products) where you also want to track Snapchat events and link user sessions.
  - **Effect of changing this setting:**
    - *Configured:* Snapchat can track a user’s journey seamlessly across your main store and specified linked domains.
    - *Empty:* Tracking is limited to your main store domain only.
  - **Recommended value:** Leave empty unless you have multiple domains/subdomains that need cross-tracking.
  - **Merchant scenario / example:** You have your main store at `mystore.com` and a separate blog at `blog.mystore.com`. You want to track users who visit both. You would add `blog.mystore.com` to this setting.
- **Cron Job URL for CAPI Sync:**

  - **What this setting does:** Provides a unique URL that you can set up as a cron job on your server. This cron job periodically sends any queued server-side events to Snapchat, ensuring data is delivered even if there are temporary network issues.
  - **Effect of changing this setting:** This is a read-only field. Setting up the cron job ensures reliable, asynchronous delivery of CAPI events. If not set up, CAPI events might only be sent in real-time or upon specific user actions, potentially missing some data if the real-time send fails.
  - **Recommended value:** Set up a cron job on your server to run this URL every 5-15 minutes.
  - **Merchant scenario / example:** To ensure all your purchase data is sent to Snapchat, even if a customer closes their browser immediately after purchase, you set up a cron job to regularly process any pending CAPI events.

#### **4. Data Quality & Health Score**

This section typically provides read-only insights and recommendations based on your current configuration and tracked events.

- **Health Score:**

  - **What this setting does:** Displays an overall score indicating the quality and completeness of your Snapchat tracking setup. A higher score means better data.
  - **Effect of changing this setting:** This is a diagnostic tool. Improving your configuration (e.g., enabling CAPI, advanced matching) will increase this score.
  - **Recommended value:** Aim for the highest possible score.
  - **Merchant scenario / example:** Your health score is 60%. The module might suggest enabling Advanced Matching to improve it, indicating a potential area for better data quality.
- **Data Quality Coach:**

  - **What this setting does:** Offers specific recommendations and warnings about your tracking setup, such as missing CAPI tokens, unconfigured product ID types, or potential consent issues.
  - **Effect of changing this setting:** This is a diagnostic tool. Addressing the recommendations will improve your tracking accuracy.
  - **Recommended value:** Review and act on all recommendations.
  - **Merchant scenario / example:** The coach tells you that your “Product ID Type” doesn’t match your catalog. You then go back to the settings and adjust it.
- **Catalog Doctor:**

  - **What this setting does:** Helps you diagnose issues related to your product catalog and how it’s being matched with Snapchat events. It checks for consistency in product identifiers.
  - **Effect of changing this setting:** This is a diagnostic tool. Resolving issues here ensures your dynamic product ads work correctly.
  - **Recommended value:** Use this tool if you experience problems with dynamic product ads showing incorrect items.
  - **Merchant scenario / example:** Your dynamic ads are showing generic products instead of the ones customers viewed. The Catalog Doctor might reveal that your product IDs are inconsistent.

#### **5. Live Statistics & Recent Events**

- **Live Statistics:**

  - **What this setting does:** Provides a real-time overview of events being sent to Snapchat (e.g., Page Views, Add to Carts, Purchases).
  - **Effect of changing this setting:** This is a monitoring tool. It helps you quickly verify if events are firing as expected.
  - **Recommended value:** Regularly check this section to ensure your tracking is active.
  - **Merchant scenario / example:** You launch a new product and want to see if “View Content” events are being tracked immediately. You check the live statistics.
- **Recent Events Log:**

  - **What this setting does:** Shows a log of the most recent events sent to Snapchat, including details like event type, timestamp, and whether it was sent via Pixel or CAPI.
  - **Effect of changing this setting:** This is a detailed logging tool for verification and troubleshooting.
  - **Recommended value:** Use this to drill down into specific events if you suspect an issue.
  - **Merchant scenario / example:** A customer reports an issue with a purchase, and you want to confirm if the “Purchase” event was successfully sent to Snapchat for that order.

### 2.2 Dedicated Admin Screens & Controller Views

#### **AdminMysnapapiAjaxController (Back Office > Modules > Snapchat Pixel & Conversions API > [Internal AJAX Calls])**

This controller is not directly accessible via a menu item but handles background AJAX requests from the module’s configuration page. It’s responsible for:

- **Screen Name & Menu Location:** Not directly visible in the menu. It processes requests initiated from the main module configuration page.
- **Available Actions & Settings:** It manages the dynamic loading of data for the “Live Statistics,” “Recent Events,” “Health Score,” “Data Quality Coach,” and “Catalog Doctor” sections. It also handles saving specific configuration settings without a full page reload.
- **Effect of changes:** When you interact with dynamic elements on the main configuration page (e.g., refreshing live stats, saving a specific sub-setting), this controller processes the request and updates the displayed information or saves the data.
- **Recommended workflow for daily store management:** Merchants do not directly interact with this controller. Its functionality is embedded within the main module configuration page.

#### **index.php (mysnapapi/controllers/admin/index.php)**

This file is a placeholder and typically doesn’t contain direct functionality or a user interface. In PrestaShop, `index.php` files within controller directories often serve to prevent directory listing rather than providing specific controller logic.

- **Screen Name & Menu Location:** Not a direct screen.
- **Available Actions & Settings:** None.
- **Effect of changes:** No direct merchant interaction or effect.
- **Recommended workflow for daily store management:** No interaction required.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration Page** | Tracking Mode | Hybrid | Defines how data is sent (Pixel, CAPI, or both). Hybrid is most robust. |
|  | Snap Pixel ID | Your Pixel ID | Unique ID for client-side tracking. Essential for Pixel. |
|  | Conversions API Token | Your CAPI Token | Secure token for server-side tracking. Essential for CAPI. |
|  | Enable Advanced Matching | YES | Improves user matching for better ad targeting. |
|  | Consent Management Integration | YES | Ensures privacy compliance by respecting user consent. |
|  | Product ID Type for Catalog Matching | Product ID / Reference | Matches product identifiers for dynamic ads. |
|  | Enable Debug Mode | NO (YES for setup) | Displays tracking info in browser console for troubleshooting. |
|  | Ghost Collector (ScCid Matching) | YES | Enhances cross-session/device user matching. |
|  | Linker Domains | Empty (or your domains) | Enables cross-domain tracking for multiple related sites. |
|  | Cron Job URL for CAPI Sync | (Read-only) | URL for server-side event delivery, set up as a cron job. |
|  | Health Score | (Diagnostic) | Overall quality of your tracking setup. Aim for high score. |
|  | Data Quality Coach | (Diagnostic) | Specific recommendations to improve data quality. |
|  | Catalog Doctor | (Diagnostic) | Diagnoses issues with product catalog matching. |
|  | Live Statistics | (Monitoring) | Real-time overview of tracked events. |
|  | Recent Events Log | (Monitoring) | Detailed log of recent events for verification. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My Snapchat ads aren’t showing any conversions, but I know I’m getting sales. What’s wrong?**
A1:

- **Check Pixel ID & CAPI Token:** Double-check that your Snap Pixel ID and Conversions API Token are correctly entered in the module configuration. Even a single typo will prevent tracking.
- **Tracking Mode:** Ensure you’re using “Hybrid” or at least “Pixel Only” if you expect client-side tracking.
- **Debug Mode:** Enable “Debug Mode” in the module settings and open your browser’s developer console (F12). Navigate your store and perform actions (view product, add to cart, complete a test purchase). Look for Snapchat events being logged in the console. If you don’t see them, there’s a fundamental setup issue.
- **Clear Cache:** Always clear your PrestaShop cache (Advanced Parameters > Performance) after making any module configuration changes.
- **Ad Blockers:** Test with an incognito/private browser window without any ad blockers enabled, as they can interfere with pixel tracking.

**Q2: I’ve enabled the module, but I’m worried about GDPR/CCPA compliance. How does this module help?**
A2:

- The module includes a **“Consent Management Integration”** setting. When enabled, it will integrate with your existing cookie consent solution (e.g., a GDPR module). This means Snapchat tracking will only activate *after* a user has given their explicit consent through your store’s consent banner.
- **Action:** Ensure this setting is enabled and that you have a functional cookie consent module on your PrestaShop store.

**Q3: My dynamic product ads on Snapchat are showing the wrong products or not working at all.**
A3:

- **Product ID Type:** Go to the module configuration and verify the **“Product ID Type for Catalog Matching”** setting. This must exactly match the unique identifier you’re using in your Snapchat Product Catalog (e.g., if your catalog uses `reference`, select `Product Reference` here).
- **Catalog Sync:** Ensure your product catalog is correctly synced and up-to-date in your Snapchat Ads Manager. The module sends the correct IDs, but Snapchat needs to have those IDs in its catalog.
- **Catalog Doctor:** Use the “Catalog Doctor” tool within the module’s configuration to diagnose potential inconsistencies between your store’s product data and what Snapchat expects.

**Q4: I’m seeing duplicate events in my Snapchat Ads Manager (e.g., two “Purchase” events for one order).**
A4:

- This usually happens if you’re using both Pixel and CAPI without proper deduplication.
- **Action:** Ensure your “Tracking Mode” is set to **“Hybrid”**. This module is designed to automatically handle event deduplication when running in Hybrid mode by generating a shared `event_id` for both client-side and server-side events. If you’re seeing duplicates, verify the module is correctly configured for Hybrid mode and that no other Snapchat tracking code is present on your site.

**Q5: The “Live Statistics” or “Health Score” sections on the module configuration page aren’t updating or showing data.**
A5:

- **AJAX Issues:** This usually indicates an issue with your server’s ability to process AJAX requests or a JavaScript error in your back office.
- **Browser Console:** Open your browser’s developer console (F12) while on the module configuration page and check for any red error messages in the “Console” tab.
- **Server Logs:** Check your server’s PHP error logs for any related errors.
- **PrestaShop Debug Mode:** Temporarily enable PrestaShop’s debug mode (Advanced Parameters > Performance > Debug mode: YES) to see if more detailed errors appear.
- **Contact Support:** If you can’t resolve it, gather any error messages and contact MyPresta.eu support.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The `Snapchat Pixel & Conversions API` module (`mysnapapi`) implements a robust tracking solution leveraging both client-side (Snap Pixel) and server-side (Conversions API - CAPI) event tracking. It follows a modular, object-oriented approach, adhering to PrestaShop’s MVC pattern where applicable.

Key architectural components:

- **Hybrid Tracking:** The module supports Pixel-only, CAPI-only, and a recommended Hybrid mode. In Hybrid mode, it generates a unique `event_id` for each event, shared between the Pixel and CAPI payloads to ensure deduplication on Snapchat’s side.
- **Event Mapping:** A comprehensive mapping of PrestaShop actions (e.g., `actionCartSave`, `actionValidateOrder`) to standard Snapchat events (`ADD_CART`, `PURCHASE`, `VIEW_CONTENT`, `PAGE_VIEW`).
- **Consent Management:** Integration points for popular consent modules to ensure GDPR/CCPA compliance.
- **Data Quality Tools:** Built-in diagnostics like Health Score, Data Quality Coach, and Catalog Doctor to assist in setup and troubleshooting.
- **Asynchronous CAPI:** CAPI events are often queued and sent asynchronously, either in real-time or via a cron job, to improve performance and reliability.
- **First-Party Data:** Utilizes a “Ghost Collector” to create first-party cookies for `ScCid` matching, enhancing user identification in a privacy-centric environment.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `mysnapapi/controllers/front/ajax.php`
  - **Class name & parent class:** `MysnapapiAjaxModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** Handles various AJAX requests from the front-office, primarily for the “Ghost Collector” (ScCid) functionality. It might collect anonymous user data or update first-party cookies without a full page reload.
- `mysnapapi/controllers/front/cron.php`
  - **Class name & parent class:** `MysnapapiCronModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** This controller is designed to be called by an external cron job. Its primary role is to process any queued server-side (CAPI) events that were not sent in real-time. It ensures that all CAPI data is eventually delivered to Snapchat, improving reliability.
- `mysnapapi/controllers/front/index.php`
  - **Class name & parent class:** `MysnapapiIndexModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** Typically a placeholder or a default entry point. It might handle basic module initialization or redirect if accessed directly. Often, `index.php` in a controller directory prevents directory listing.
- `mysnapapi/controllers/front/sync.php`
  - **Class name & parent class:** `MysnapapiSyncModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** Likely handles specific data synchronization tasks, potentially related to product catalog updates or other data exchange with Snapchat’s API, separate from the main event tracking.

#### Back-Office Admin Controllers

- `mysnapapi/controllers/admin/AdminMysnapapiAjaxController.php`
  - **Class name & parent class:** `AdminMysnapapiAjaxController` extends `AdminController`.
  - **Tab name and managed entity:** Not a direct menu tab. This controller handles AJAX requests originating from the module’s main configuration page (`getContent()` method of `mysnapapi.php`). It’s responsible for dynamically loading data for the various diagnostic tools (Live Stats, Health Score, etc.) and saving specific configuration settings without a full page reload.
- `mysnapapi/controllers/admin/index.php`
  - **Class name & parent class:** Not a functional controller.
  - **Tab name and managed entity:** Placeholder. Prevents directory listing.

### 4.3 Core Classes & Models (`classes/`)

- `mysnapapi/classes/autoload.php`: Standard PrestaShop autoload file.
- `mysnapapi/classes/index.php`: Placeholder to prevent directory listing.
- `mysnapapi/classes/MysnapapiCapiClient.php`:
  - **Interacts with:** Snapchat Conversions API endpoint.
  - **Extends ObjectModel:** No.
  - **Key methods:** Handles sending server-side events to Snapchat. Encapsulates API request logic, authentication (using CAPI token), and error handling.
- `mysnapapi/classes/MysnapapiCapiTracker.php`:
  - **Interacts with:** `ps_configuration` (for CAPI token), `MysnapapiCapiClient`.
  - **Extends ObjectModel:** No.
  - **Key methods:** Responsible for preparing and sending event data specifically for the Conversions API. It formats event payloads according to Snapchat’s CAPI specifications.
- `mysnapapi/classes/MysnapapiCatalogDoctor.php`:
  - **Interacts with:** Product data (from `Product` and `ProductSupplier` ObjectModels).
  - **Extends ObjectModel:** No.
  - **Key methods:** Provides diagnostic logic to check for consistency and issues related to product identifiers used for catalog matching (e.g., `id_product`, `reference`, `ean13`).
- `mysnapapi/classes/MysnapapiConsent.php`:
  - **Interacts with:** `ps_configuration` (for consent settings), potentially other consent modules.
  - **Extends ObjectModel:** No.
  - **Key methods:** Manages consent state. Checks if user consent is required and if it has been granted before allowing tracking scripts or CAPI events to fire.
- `mysnapapi/classes/MysnapapiCurrencyHelper.php`:
  - **Interacts with:** PrestaShop’s `Currency` class.
  - **Extends ObjectModel:** No.
  - **Key methods:** Provides utility functions for handling currency formatting and conversion, ensuring event values are sent in the correct format and currency code to Snapchat.
- `mysnapapi/classes/MysnapapiDataQualityCoach.php`:
  - **Interacts with:** Module configuration settings.
  - **Extends ObjectModel:** No.
  - **Key methods:** Analyzes the module’s configuration and provides recommendations or warnings to improve data quality and tracking effectiveness.
- `mysnapapi/classes/MysnapapiEventId.php`:
  - **Interacts with:** Session, cookies.
  - **Extends ObjectModel:** No.
  - **Key methods:** Generates and manages unique `event_id` values for each tracked event. Crucial for deduplication when using Hybrid tracking mode.
- `mysnapapi/classes/MysnapapiEventMap.php`:
  - **Interacts with:** N/A.
  - **Extends ObjectModel:** No.
  - **Key methods:** Defines the mapping between PrestaShop’s internal events/data and Snapchat’s standard event names and parameters.
- `mysnapapi/classes/MysnapapiEvents.php`:
  - **Interacts with:** Various PrestaShop core classes (e.g., `Cart`, `Product`, `Order`).
  - **Extends ObjectModel:** No.
  - **Key methods:** Centralized class for collecting and formatting event data (e.g., `PageView`, `ViewContent`, `AddToCart`, `Purchase`) from PrestaShop’s context into a Snapchat-compatible structure.
- `mysnapapi/classes/MysnapapiHealthScore.php`:
  - **Interacts with:** Module configuration, potentially live event data.
  - **Extends ObjectModel:** No.
  - **Key methods:** Calculates an overall “health score” for the tracking setup based on configured options and detected issues.
- `mysnapapi/classes/MysnapapiHybridTracker.php`:
  - **Interacts with:** `MysnapapiPixelTracker`, `MysnapapiCapiTracker`, `MysnapapiEventId`.
  - **Extends ObjectModel:** No.
  - **Key methods:** Orchestrates tracking in “Hybrid” mode, ensuring both Pixel and CAPI events are sent with the same `event_id` for deduplication.
- `mysnapapi/classes/MysnapapiLiveStats.php`:
  - **Interacts with:** Potentially a temporary log of recent events or real-time data.
  - **Extends ObjectModel:** No.
  - **Key methods:** Collects and presents real-time statistics on tracked events for the admin panel.
- `mysnapapi/classes/MysnapapiPixelTracker.php`:
  - **Interacts with:** `ps_configuration` (for Pixel ID).
  - **Extends ObjectModel:** No.
  - **Key methods:** Responsible for generating the JavaScript code for the Snap Pixel and embedding it into the front-office, including event data.
- `mysnapapi/classes/MysnapapiProductIdResolver.php`:
  - **Interacts with:** Product data.
  - **Extends ObjectModel:** No.
  - **Key methods:** Determines the correct product identifier (e.g., `id_product`, `reference`, `ean13`) to use based on module configuration for catalog matching.
- `mysnapapi/classes/MysnapapiPropertyRules.php`:
  - **Interacts with:** N/A.
  - **Extends ObjectModel:** No.
  - **Key methods:** Defines rules and validations for event properties, ensuring data sent to Snapchat adheres to their API specifications.
- `mysnapapi/classes/MysnapapiTrackerFactory.php`:
  - **Interacts with:** Module configuration (tracking mode).
  - **Extends ObjectModel:** No.
  - **Key methods:** Factory pattern to instantiate the correct tracker class (`MysnapapiPixelTracker`, `MysnapapiCapiTracker`, or `MysnapapiHybridTracker`) based on the module’s configured tracking mode.
- `mysnapapi/classes/MysnapapiTrackerInterface.php`:
  - **Interacts with:** N/A.
  - **Extends ObjectModel:** No.
  - **Key methods:** Defines a common interface for all tracker classes, ensuring consistent method signatures for event tracking.
- `mysnapapi/classes/MysnapapiUserData.php`:
  - **Interacts with:** Customer data (from `Customer` ObjectModel), session, cookies.
  - **Extends ObjectModel:** No.
  - **Key methods:** Collects and formats user-specific data (e.g., email, phone, IP address, user agent) for advanced matching, ensuring data is hashed and compliant.

### 4.4 JavaScript Assets (`views/js/`)

- `mysnapapi/tools/console-simulate-bo-ui.js`:
  - **Scope:** Back-office (developer tool).
  - **Description:** A utility script, likely for development/debugging, to simulate or interact with the Back Office UI from the browser console.
- `mysnapapi/views/js/mp-collect.js`:
  - **Scope:** Front-office.
  - **Description:** Core client-side data collection script. It might listen for specific DOM events or user interactions to trigger Snapchat Pixel events.
- `mysnapapi/views/js/mp-consent.js`:
  - **Scope:** Front-office.
  - **Description:** Handles the integration with cookie consent mechanisms. It checks for consent status and conditionally loads/initializes the Snapchat Pixel or related tracking. May interact with `prestashop.on('updateConsent')`.
- `mysnapapi/views/js/mp-front.js`:
  - **Scope:** Front-office.
  - **Description:** General front-office JavaScript for the module. This likely contains the main logic for initializing the Snap Pixel, pushing events to the `snap` object, and handling client-side event triggers.
- `mysnapapi/views/js/mp-inspect.js`:
  - **Scope:** Front-office (debug mode).
  - **Description:** Used when debug mode is enabled. It intercepts and displays Snapchat events in the browser console, providing detailed insights into the data being sent.
- `mysnapapi/views/js/mysnapapi-admin.js`:
  - **Scope:** Back-office.
  - **Description:** JavaScript for the module’s administration interface. Handles form interactions, AJAX calls to `AdminMysnapapiAjaxController`, dynamic updates of diagnostic sections (Live Stats, Health Score), and wizard steps.
- `mysnapapi/views/js/mysnapapi-debug.js`:
  - **Scope:** Front-office (debug mode).
  - **Description:** Similar to `mp-inspect.js`, provides additional debugging utilities or visual overlays for developers to verify tracking.
- `mysnapapi/views/js/mysnapapi-ghost.js`:
  - **Scope:** Front-office.
  - **Description:** Implements the “Ghost Collector” functionality. It manages the creation and reading of first-party cookies for `ScCid` (Snapchat Click ID) matching, enhancing user identification.
- `mysnapapi/views/js/mysnapapi-live.js`:
  - **Scope:** Back-office.
  - **Description:** Powers the “Live Statistics” section in the admin panel, making AJAX calls to fetch and display real-time event data.
- `mysnapapi/views/js/mysnapapi-tcf.js`:
  - **Scope:** Front-office.
  - **Description:** Specifically for integration with Transparency and Consent Framework (TCF) compliant consent solutions, ensuring Snapchat tracking adheres to TCF signals.
- `mysnapapi/views/js/mysnapapi-wizard.js`:
  - **Scope:** Back-office.
  - **Description:** Provides interactive logic for the module’s setup wizard, guiding the merchant through initial configuration steps.
- `mysnapapi/views/js/mysnapapi.js`:
  - **Scope:** Front-office.
  - **Description:** Main entry point or general utility JavaScript for the front-office, potentially loading other scripts or containing global module-specific functions.

### 4.5 CSS Stylesheets (`views/css/`)

- `mysnapapi/views/css/mp-inspect.css`:
  - **Scope:** Front-office (debug mode).
  - **Description:** Styles for the debug overlay or console output when `mp-inspect.js` is active.
- `mysnapapi/views/css/mysnapapi-admin.css`:
  - **Scope:** Back-office admin form styling.
  - **Description:** Styles for the module’s configuration page, including layout, buttons, diagnostic sections (Health Score, Data Quality Coach), and wizard steps.
- `mysnapapi/views/css/mysnapapi-debug.css`:
  - **Scope:** Front-office (debug mode).
  - **Description:** Additional styling for debug elements, potentially visual indicators or borders for tracked elements.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `mysnapapi/views/templates/hook/capi-pageview.tpl`:
  - **Hook:** Potentially `displayHeader` or `displayFooter` (server-side context).
  - **Output:** Renders a hidden element or a server-side call to trigger a CAPI `PAGE_VIEW` event, often used as a fallback or for initial page load.
- `mysnapapi/views/templates/hook/debug.tpl`:
  - **Hook:** `displayHeader` or `displayFooter` (conditional on debug mode).
  - **Output:** Renders debug information or initializes debug scripts in the front-office.
- `mysnapapi/views/templates/hook/displayOrderConfirmation.tpl`:
  - **Hook:** `displayOrderConfirmation`.
  - **Output:** Renders the Snap Pixel `PURCHASE` event and/or triggers the CAPI `PURCHASE` event on the order confirmation page, passing order details.
- `mysnapapi/views/templates/hook/ghost.tpl`:
  - **Hook:** `displayHeader` or `displayFooter`.
  - **Output:** Renders the JavaScript for the “Ghost Collector” to manage `ScCid` cookies.
- `mysnapapi/views/templates/hook/header.tpl`:
  - **Hook:** `displayHeader`.
  - **Output:** The primary template for initializing the Snap Pixel base code, `snap` object, and potentially `PAGE_VIEW` events. It loads necessary JavaScript files.
- `mysnapapi/views/templates/hook/payment.tpl`:
  - **Hook:** `displayPayment` or `displayPaymentTop`.
  - **Output:** Renders `INITIATE_CHECKOUT` or other relevant events during the payment selection phase of checkout.
- `mysnapapi/views/templates/hook/product-details.tpl`:
  - **Hook:** `displayProductButtons` or `displayFooterProduct`.
  - **Output:** Renders the Snap Pixel `VIEW_CONTENT` event and `ADD_CART` event (or related JS) on the product page, passing product-specific data.

#### Admin templates (`views/templates/admin/`)

- `mysnapapi/views/templates/admin/consent-guide.tpl`: Displays guidance on integrating with consent management.
- `mysnapapi/views/templates/admin/doctor.tpl`: Renders the interface for the “Catalog Doctor” diagnostic tool.
- `mysnapapi/views/templates/admin/dq.tpl`: Renders the “Data Quality Coach” recommendations.
- `mysnapapi/views/templates/admin/health.tpl`: Displays the “Health Score” and related insights.
- `mysnapapi/views/templates/admin/linker-domains.tpl`: Input field and explanation for cross-domain tracking.
- `mysnapapi/views/templates/admin/live-maintain.tpl`: Interface for maintaining or clearing live statistics.
- `mysnapapi/views/templates/admin/live.tpl`: Displays the “Live Statistics” dashboard.
- `mysnapapi/views/templates/admin/mode-context.tpl`: Provides context or explanation for the chosen tracking mode.
- `mysnapapi/views/templates/admin/mode-note-both.tpl`: Specific note for “Hybrid” tracking mode.
- `mysnapapi/views/templates/admin/mode-note-capi.tpl`: Specific note for “Conversions API Only” tracking mode.
- `mysnapapi/views/templates/admin/mode-note-pixel.tpl`: Specific note for “Pixel Only” tracking mode.
- `mysnapapi/views/templates/admin/mode-picker.tpl`: The selection interface for choosing the tracking mode.
- `mysnapapi/views/templates/admin/properties-list.tpl`: Displays a list of event properties and their rules.
- `mysnapapi/views/templates/admin/recent-events.tpl`: Table or list displaying the most recent tracked events.
- `mysnapapi/views/templates/admin/tabs.tpl`: Renders the tab navigation structure for the module’s configuration page.
- `mysnapapi/views/templates/admin/tag-chips.tpl`: Visual components for displaying tags or identifiers.
- `mysnapapi/views/templates/admin/tag-ids.tpl`: Input fields for Pixel ID and CAPI Token.
- `mysnapapi/views/templates/admin/wizard.tpl`: The template for the step-by-step setup wizard.

#### Front-office templates (`views/templates/front/`)

(No dedicated standalone page templates, all front-office templates are hook-based.)

### 4.7 Database Schema & Hooks Map

#### Database Tables

The module primarily uses PrestaShop’s `ps_configuration` table to store its settings.

- `ps_configuration`: Stores key-value pairs for module settings (e.g., `MYSNAPAPI_PIXEL_ID`, `MYSNAPAPI_CAPI_TOKEN`, `MYSNAPAPI_TRACKING_MODE`).
- No custom SQL tables are explicitly created by the module based on the provided inventory. CAPI events might be temporarily queued in memory or a file-based system before being sent, rather than a dedicated database table.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Renders in the `<head>` section of every front-office page. | Initializes Snap Pixel base code, loads JS assets, triggers `PAGE_VIEW` events, and sets up `ScCid` (Ghost Collector). |
| `displayFooter` | Renders at the end of the `<body>` section of every front-office page. | May include deferred script loading, additional event triggers, or `ScCid` management. |
| `displayProductButtons` | On the product page, near the “Add to Cart” button. | Triggers `VIEW_CONTENT` and potentially `ADD_CART` events with product details. |
| `displayFooterProduct` | On the product page, in the footer area. | Alternative or additional location for `VIEW_CONTENT` and `ADD_CART` events. |
| `actionCartSave` | Executed whenever a cart is modified (add, update, remove product). | Triggers `ADD_CART` or `REMOVE_FROM_CART` events. |
| `actionValidateOrder` | Executed after a successful order is placed. | Triggers the crucial `PURCHASE` event, sending complete order details (value, currency, products). |
| `displayOrderConfirmation` | On the order confirmation page after a successful purchase. | Renders client-side `PURCHASE` event for the Snap Pixel. |
| `displayPayment` | Before the payment method selection. | Triggers `INITIATE_CHECKOUT` event. |
| `displayPaymentTop` | At the top of the payment selection page. | Alternative or additional location for `INITIATE_CHECKOUT` event. |
| `actionFrontControllerSetMedia` | Executed when a front controller is setting its media assets. | Injects module-specific CSS and JavaScript files into the front-office. |
| `actionAdminControllerSetMedia` | Executed when an admin controller is setting its media assets. | Injects module-specific CSS and JavaScript files into the back-office configuration page. |
| `actionModuleInstall` | Executed when the module is installed. | Sets default configuration values in `ps_configuration`. |
| `actionModuleUninstall` | Executed when the module is uninstalled. | Cleans up configuration values from `ps_configuration`. |

## 5. Official Support & Updates

For official updates, technical support, and the latest versions of the Snapchat Pixel & Conversions API module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and integration.
