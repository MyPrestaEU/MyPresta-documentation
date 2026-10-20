---
title: "Pinterest Tag & Conversions API - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Pinterest Tag & Conversions API PrestaShop module by MyPresta.eu."
sidebar:
  label: "Pinterest Tag & Conversions API - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Pinterest Tag & Conversions API Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/pinterest-tag-conversions-api.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/pinterest-tag-conversions-api/)
>
> ---


# Pinterest Tag & Conversions API

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL). Your server must be able to make outgoing HTTP requests to Pinterest’s API endpoints.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main hub for setting up your Pinterest tracking. You’ll find various sections and tabs to manage your Pinterest Tag, Conversions API, and data quality.

#### General Settings & Tracking Mode

- **Pinterest Tag ID (Required)**

  - **What this setting does:** This is your unique identifier provided by Pinterest. It tells Pinterest which ad account your website data belongs to.
  - **Effect of changing this setting:**
    - *When entered:* Enables the module to send data to your Pinterest ad account. Without it, no tracking can occur.
    - *When empty:* The module cannot send any data to Pinterest.
  - **Recommended value:** Your Pinterest Tag ID. You can find this in your Pinterest Ads Manager under “Ads” > “Conversions” > “Pinterest Tag”.
  - **Merchant scenario / example:** You’ve just created a Pinterest Ads account and need to link your store to it. Copy the Tag ID from Pinterest and paste it here.
- **Tracking Mode**

  - **What this setting does:** Determines how your store sends data to Pinterest. You can choose between the traditional Pinterest Tag (browser-side), the more robust Conversions API (server-side), or a combination of both.
  - **Effect of changing this setting:**
    - *Pinterest Tag (Browser-side):* Data is sent directly from the customer’s browser. This is simpler but can be affected by ad blockers or browser privacy settings.
    - *Conversions API (Server-side):* Data is sent directly from your PrestaShop server to Pinterest. This is more reliable and less prone to blocking, offering better data accuracy.
    - *Both (Hybrid with Deduplication):* Data is sent via both methods. The module automatically adds a unique `event_id` to each event, allowing Pinterest to identify and ignore duplicate events, ensuring maximum data coverage without overcounting.
  - **Recommended value:** **Both (Hybrid with Deduplication)** for the most reliable and comprehensive tracking.
  - **Merchant scenario / example:** You want to ensure your Pinterest campaigns are as accurate as possible, even with increasing privacy measures. Choosing “Both” provides the best of both worlds.

#### Conversions API (CAPI) Settings (Visible if CAPI or Both mode is selected)

- **Conversions API Access Token (Required for CAPI)**

  - **What this setting does:** This is a secure token that authenticates your server when sending data directly to Pinterest’s Conversions API. It’s like a password for your server to talk to Pinterest.
  - **Effect of changing this setting:**
    - *When entered:* Enables your server to send data via the Conversions API.
    - *When empty:* Conversions API tracking will not work, even if selected as the tracking mode.
  - **Recommended value:** Your Pinterest Conversions API Access Token. Generate this in your Pinterest Ads Manager under “Ads” > “Conversions” > “Conversions API”.
  - **Merchant scenario / example:** You’ve decided to use the Conversions API for more reliable tracking. You’ll generate this token in Pinterest and paste it here.
- **Enable Enhanced Match for CAPI**

  - **What this setting does:** When enabled, the module sends additional customer information (like email, phone number, name, address – all hashed for privacy) with Conversions API events. This helps Pinterest match events to specific users more accurately, even if they’re not logged into Pinterest.
  - **Effect of changing this setting:**
    - *When enabled:* Improves the accuracy of event matching on Pinterest, leading to better audience targeting and campaign optimization.
    - *When disabled:* Only basic event data is sent, potentially reducing matching accuracy.
  - **Recommended value:** **YES**. This significantly improves data quality and ad performance.
  - **Merchant scenario / example:** You want to make sure Pinterest can accurately attribute sales to your ads, even if customers use different devices or browsers. Enhanced Match helps bridge these gaps.

#### Data Privacy & Consent

- **Integrate with Cookie Consent Module**
  - **What this setting does:** If you use a separate cookie consent module (e.g., GDPR compliance module), enabling this ensures that Pinterest tracking only fires after the customer has given their consent.
  - **Effect of changing this setting:**
    - *When enabled:* Pinterest tracking will respect the customer’s consent choices from your cookie module. If consent is denied, no Pinterest data is sent.
    - *When disabled:* Pinterest tracking will fire regardless of other cookie consent settings, potentially leading to compliance issues.
  - **Recommended value:** **YES** if you use a cookie consent module. **NO** if you don’t use one or handle consent manually.
  - **Merchant scenario / example:** Your store needs to be GDPR compliant. By enabling this, you ensure Pinterest tracking adheres to your customers’ privacy preferences.

#### Advanced Settings & Debugging

- **Enable Debug Mode**

  - **What this setting does:** Activates a special mode that displays detailed information about the Pinterest events being sent, directly in your browser’s developer console. This is useful for verifying that your tracking is working correctly.
  - **Effect of changing this setting:**
    - *When enabled:* Developers and webmasters can see real-time Pinterest event data in the browser console. This should **never** be enabled on a live production store for general public viewing.
    - *When disabled:* No debug information is shown.
  - **Recommended value:** **NO** for a live production store. **YES** only during setup and testing.
  - **Merchant scenario / example:** You’ve just installed the module and want to confirm that “Add to Cart” events are firing correctly. You enable debug mode, add a product to your cart, and check the browser console for the event data.
- **Linker Domains (for cross-domain tracking)**

  - **What this setting does:** If your store uses multiple subdomains or redirects to another domain during the checkout process (e.g., a separate payment gateway domain), you can list those domains here. This helps Pinterest correctly attribute actions across different domains.
  - **Effect of changing this setting:**
    - *When domains are listed:* Pinterest can maintain tracking continuity across these domains, preventing data loss.
    - *When empty:* Tracking might break if customers navigate between different domains during their journey, leading to incomplete data.
  - **Recommended value:** Leave empty unless you have specific cross-domain tracking needs. If so, enter each domain on a new line.
  - **Merchant scenario / example:** Your main store is `shop.example.com`, but your blog is `blog.example.com` and you want to track users who visit both. You would add `blog.example.com` here.

#### Data Quality & Health Score (Informational Sections)

These sections provide insights into your tracking setup and are not direct configuration settings, but rather reports generated by the module.

- **Health Score**: Shows an overall score indicating the quality and completeness of your Pinterest tracking setup. A higher score means more reliable data.
- **Catalog Doctor**: Helps identify potential issues with your product catalog data that might affect Pinterest’s ability to match products for dynamic ads.
- **Data Quality Coach**: Provides recommendations and warnings about your event data, such as missing parameters or incorrect formatting, to help you improve accuracy.
- **Live Statistics**: Displays recent events sent to Pinterest, allowing you to monitor activity in real-time.
- **Recent Events**: A log of the most recent events processed by the module.

### 2.2 Dedicated Admin Screens & Controller Views

#### 2.2.1 AdminMypinterestAjaxController (Back Office > Modules > Pinterest Tag & Conversions API > Live Statistics / Health Score / Data Quality Coach)

This controller powers the dynamic, interactive sections within the module’s main configuration page, specifically for features like Live Statistics, Health Score, and Data Quality Coach.

- **Screen Name & Menu Location:** These are not standalone menu items but rather interactive panels within the main module configuration page (Back Office > Modules > Module Manager > Configure “Pinterest Tag & Conversions API”).
- **Available Actions & Settings:** This controller handles AJAX requests to fetch and display real-time data and reports.
  - **Live Statistics**: Shows a real-time feed of events (e.g., PageView, AddToCart, Purchase) as they are sent to Pinterest, including whether they were sent via Tag, CAPI, or both. This allows you to quickly verify that events are firing.
  - **Health Score**: Displays a summary of your tracking setup’s health, highlighting areas for improvement (e.g., missing CAPI token, low event match quality).
  - **Data Quality Coach**: Offers specific recommendations to improve the quality of the data sent to Pinterest, such as ensuring all required parameters are included for each event type.
  - **Catalog Doctor**: Analyzes your product catalog feed (if you use one for Pinterest) and points out potential issues that could hinder dynamic product ads.
- **Effect of changes:** Interacting with these panels (e.g., refreshing the Live Statistics) triggers AJAX calls that fetch the latest data from your server or Pinterest’s API, providing up-to-date insights without reloading the entire page.
- **Recommended workflow for daily store management:** Regularly check the Health Score and Data Quality Coach to ensure your tracking remains optimal. Use Live Statistics during testing or after making changes to verify events are firing correctly.

#### 2.2.2 index.php (mypinterest/controllers/admin/index.php)

This file is a placeholder and typically serves as a security measure to prevent direct directory listing in PrestaShop admin folders. It doesn’t represent a configurable screen or a managed entity itself.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Pinterest Tag ID | Your Tag ID | Links your store to your Pinterest ad account for tracking. |
| Module Configuration | Tracking Mode | Both (Hybrid) | Sends data via browser (Tag) and server (CAPI) for maximum reliability. |
| Module Configuration | Conversions API Access Token | Your CAPI Token | Authenticates server-side data sending to Pinterest. |
| Module Configuration | Enable Enhanced Match for CAPI | YES | Improves event matching accuracy on Pinterest for better targeting. |
| Module Configuration | Integrate with Cookie Consent Module | YES (if applicable) | Ensures Pinterest tracking respects customer privacy choices. |
| Module Configuration | Enable Debug Mode | NO (on live store) | Shows detailed tracking info in browser console for testing. |
| Module Configuration | Linker Domains | Empty (unless needed) | Maintains tracking continuity across multiple related domains. |
| Live Statistics Panel | N/A | N/A | Displays real-time Pinterest events for verification. |
| Health Score Panel | N/A | N/A | Provides an overall assessment of your tracking setup’s quality. |
| Data Quality Coach Panel | N/A | N/A | Offers recommendations to improve event data accuracy. |
| Catalog Doctor Panel | N/A | N/A | Identifies issues in your product catalog for Pinterest ads. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve installed the module, but I don’t see any data in my Pinterest Ads Manager. What should I do?**
A1: First, double-check that your **Pinterest Tag ID** and **Conversions API Access Token** (if using CAPI) are correctly entered in the module configuration. Ensure there are no typos. Next, clear your PrestaShop cache (**Advanced Parameters > Performance > Clear cache**). Then, visit your store’s front office and perform some actions (view a product, add to cart, complete a test purchase). If you have “Debug Mode” enabled in the module, check your browser’s developer console for Pinterest events. If still no data, verify your Pinterest Ads Manager setup and ensure your account is active.

**Q2: My Pinterest Tag seems to be blocked by ad blockers. How can I ensure my data is still collected?**
A2: This is precisely why the Conversions API (CAPI) is so important! Ensure your “Tracking Mode” is set to **“Both (Hybrid with Deduplication)”**. This way, even if the browser-side Pinterest Tag is blocked, your PrestaShop server will still send the event data directly to Pinterest via the Conversions API, ensuring your tracking remains robust.

**Q3: How does this module handle customer privacy and GDPR/CCPA?**
A3: The module includes an option to **“Integrate with Cookie Consent Module”**. If you have a separate cookie consent module installed (which is highly recommended for privacy compliance), enable this setting. The Pinterest tracking will then only activate once the customer has given their consent via your existing consent solution. The module also hashes sensitive customer data before sending it via Enhanced Match for CAPI, adding another layer of privacy.

**Q4: I’m seeing a low “Health Score” or warnings in the “Data Quality Coach.” What do these mean?**
A4: These sections are designed to help you optimize your tracking. A low Health Score or warnings usually indicate that some data parameters might be missing or incorrectly formatted, or that your setup isn’t fully optimized (e.g., CAPI not enabled). Review the specific recommendations provided in the “Data Quality Coach” and “Catalog Doctor” panels. They will guide you on how to improve your data quality, which directly impacts the effectiveness of your Pinterest ads.

**Q5: Will this module slow down my website?**
A5: The module is designed to be highly optimized. The browser-side Pinterest Tag is loaded asynchronously, meaning it doesn’t block your page from loading. The server-side Conversions API calls happen in the background and do not impact front-office page load times. You should not experience any noticeable slowdowns due to this module.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The `Pinterest Tag & Conversions API` module (`mypinterest`) implements a hybrid tracking strategy for Pinterest, combining the traditional browser-side Pinterest Tag with the server-side Conversions API (CAPI). It follows PrestaShop’s MVC pattern where applicable, leveraging hooks for front-office event injection and dedicated admin controllers for configuration and data reporting. Key architectural components include:

- **Tracker Factory**: Dynamically instantiates the appropriate tracking mechanism (Tag, CAPI, or Hybrid) based on module configuration.
- **Event Mapping**: Translates PrestaShop’s internal events (e.g., `actionCartSave`, `actionValidateOrder`) into Pinterest’s standard event names and parameters.
- **Data Quality Tools**: Dedicated classes for health scoring, catalog diagnostics, and data quality coaching, providing actionable insights in the back office.
- **Consent Management**: Integration with third-party cookie consent modules to ensure GDPR/CCPA compliance.
- **Live Statistics**: Real-time event monitoring via AJAX for debugging and verification.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `controllers/front/ajax.php`
  - **Class name & parent class**: `MypinterestAjaxModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility**: Handles AJAX requests from the front office, primarily for sending server-side events (CAPI) that are triggered by client-side actions but need to be processed securely on the server. This can include events that are difficult to track purely client-side or for deduplication purposes. It likely receives event data from `mypinterest.js` and dispatches it to the CAPI client.
- `controllers/front/cron.php`
  - **Class name & parent class**: `MypinterestCronModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility**: Provides an endpoint for a cron job. This could be used for tasks like sending deferred CAPI events, synchronizing product catalogs, or performing periodic data quality checks without direct user interaction.
- `controllers/front/index.php`
  - **Class name & parent class**: `MypinterestIndexModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility**: A placeholder front controller, typically used to prevent direct directory listing or as a fallback for module-specific routes that don’t fit other controllers. In this module, it likely serves a minimal purpose or redirects.

#### Back-Office Admin Controllers

- `controllers/admin/AdminMypinterestAjaxController.php`
  - **Class name & parent class**: `AdminMypinterestAjaxController` extends `ModuleAdminController`.
  - **Tab name and managed entity**: This controller is not directly exposed as a menu tab but serves as an AJAX endpoint for the module’s configuration page. It handles requests for dynamic data displayed in the “Live Statistics,” “Health Score,” “Data Quality Coach,” and “Catalog Doctor” panels within the module’s main configuration. It fetches real-time event logs, health metrics, and diagnostic reports.
- `controllers/admin/index.php`
  - **Class name & parent class**: Not a functional controller.
  - **Tab name and managed entity**: This is a security placeholder, preventing directory listing.

### 4.3 Core Classes & Models (`classes/`)

- `classes/autoload.php`: Standard PrestaShop autoload file, ensuring module classes are loaded correctly.
- `classes/MypinterestCapiClient.php`:
  - **Database table**: None directly.
  - **Extends**: No `ObjectModel`.
  - **Key public methods**: Handles the actual HTTP requests to Pinterest’s Conversions API endpoint. Encapsulates logic for building CAPI payloads, including event data, user data, and access tokens.
- `classes/MypinterestCapiTracker.php`:
  - **Database table**: None.
  - **Extends**: Implements `MypinterestTrackerInterface`.
  - **Key public methods**: Manages the logic for tracking events specifically via the Conversions API. Formats data for CAPI, handles event deduplication (`event_id`), and delegates sending to `MypinterestCapiClient`.
- `classes/MypinterestCatalogDoctor.php`:
  - **Database table**: None.
  - **Extends**: No `ObjectModel`.
  - **Key public methods**: Contains logic to analyze product data (e.g., from product feeds or `Product` objects) and identify potential issues that could affect Pinterest’s ability to match products for dynamic ads. Provides diagnostic reports.
- `classes/MypinterestConsent.php`:
  - **Database table**: None.
  - **Extends**: No `ObjectModel`.
  - **Key public methods**: Manages integration with third-party cookie consent modules. Checks for user consent status and determines if Pinterest tracking should be enabled or disabled based on consent.
- `classes/MypinterestCurrencyHelper.php`:
  - **Database table**: None.
  - **Extends**: No `ObjectModel`.
  - **Key public methods**: Utility class for handling currency formatting and conversion, ensuring Pinterest events send currency values in the correct format.
- `classes/MypinterestDataQualityCoach.php`:
  - **Database table**: None.
  - **Extends**: No `ObjectModel`.
  - **Key public methods**: Analyzes the quality of event data being sent (e.g., presence of required parameters, correct data types) and provides recommendations for improvement.
- `classes/MypinterestEventId.php`:
  - **Database table**: None.
  - **Extends**: No `ObjectModel`.
  - **Key public methods**: Generates and manages unique `event_id` values for event deduplication, crucial for hybrid tracking.
- `classes/MypinterestEventMap.php`:
  - **Database table**: None.
  - **Extends**: No `ObjectModel`.
  - **Key public methods**: Defines the mapping between PrestaShop actions/data and Pinterest’s standard event names and their required/recommended parameters.
- `classes/MypinterestEvents.php`:
  - **Database table**: None.
  - **Extends**: No `ObjectModel`.
  - **Key public methods**: Centralizes the logic for triggering and managing various Pinterest events (PageView, AddToCart, Purchase, etc.) across the module.
- `classes/MypinterestHealthScore.php`:
  - **Database table**: None.
  - **Extends**: No `ObjectModel`.
  - **Key public methods**: Calculates an overall “health score” for the Pinterest tracking setup based on various factors like CAPI token presence, tracking mode, and data quality.
- `classes/MypinterestHybridTracker.php`:
  - **Database table**: None.
  - **Extends**: Implements `MypinterestTrackerInterface`.
  - **Key public methods**: Orchestrates tracking when “Both” mode is selected. Calls both `MypinterestTagTracker` and `MypinterestCapiTracker`, ensuring `event_id` is consistent for deduplication.
- `classes/MypinterestLiveStats.php`:
  - **Database table**: Stores recent event logs (e.g., in `ps_configuration` or a custom table).
  - **Extends**: No `ObjectModel`.
  - **Key public methods**: Records and retrieves recent Pinterest events for display in the “Live Statistics” panel in the back office.
- `classes/MypinterestProductIdResolver.php`:
  - **Database table**: None.
  - **Extends**: No `ObjectModel`.
  - **Key public methods**: Helps resolve and format product IDs to match Pinterest’s catalog requirements, ensuring accurate product matching for dynamic ads.
- `classes/MypinterestPropertyRules.php`:
  - **Database table**: None.
  - **Extends**: No `ObjectModel`.
  - **Key public methods**: Defines rules and validations for Pinterest event properties, ensuring data sent to Pinterest adheres to their specifications.
- `classes/MypinterestTagTracker.php`:
  - **Database table**: None.
  - **Extends**: Implements `MypinterestTrackerInterface`.
  - **Key public methods**: Manages the logic for injecting the browser-side Pinterest Tag script and firing events via `pintrk()` calls.
- `classes/MypinterestTrackerFactory.php`:
  - **Database table**: None.
  - **Extends**: No `ObjectModel`.
  - **Key public methods**: A factory pattern class responsible for creating and returning the correct tracker instance (`MypinterestTagTracker`, `MypinterestCapiTracker`, or `MypinterestHybridTracker`) based on the module’s configuration.
- `classes/MypinterestTrackerInterface.php`:
  - **Database table**: None.
  - **Extends**: No `ObjectModel`.
  - **Key public methods**: Defines the common interface for all Pinterest trackers, ensuring consistency in how events are handled regardless of the underlying tracking method.
- `classes/MypinterestUserData.php`:
  - **Database table**: None.
  - **Extends**: No `ObjectModel`.
  - **Key public methods**: Collects and formats customer data (email, phone, address, etc.) for “Enhanced Match,” ensuring it’s hashed and compliant with Pinterest’s requirements.

### 4.4 JavaScript Assets (`views/js/`)

- `mypinterest/views/js/mypinterest-admin.js`:
  - **Scope**: Back-office.
  - **Description**: Contains JavaScript for the module’s administration interface. Handles AJAX calls to `AdminMypinterestAjaxController` for fetching live stats, health scores, and other dynamic content. Manages UI interactions on the configuration page.
- `mypinterest/views/js/mypinterest-debug.js`:
  - **Scope**: Front-office.
  - **Description**: Loaded when “Debug Mode” is enabled. Provides console logging and visual overlays to display Pinterest event data as it’s being sent, aiding in troubleshooting and verification.
- `mypinterest/views/js/mypinterest-ghost.js`:
  - **Scope**: Front-office.
  - **Description**: Potentially related to “ghost” or deferred tracking, or a fallback mechanism for events that might not fire immediately. Could be used for specific event types or consent-related delays.
- `mypinterest/views/js/mypinterest-live.js`:
  - **Scope**: Back-office.
  - **Description**: Specifically for the “Live Statistics” panel. Manages the real-time update of event logs, polling the server via AJAX to display recent Pinterest events.
- `mypinterest/views/js/mypinterest-tcf.js`:
  - **Scope**: Front-office.
  - **Description**: Handles integration with Transparency and Consent Framework (TCF) compatible cookie consent modules. Listens for consent events and enables/disables Pinterest tracking accordingly.
- `mypinterest/views/js/mypinterest-wizard.js`:
  - **Scope**: Back-office.
  - **Description**: Powers the setup wizard functionality within the module configuration. Guides the merchant through initial setup steps, validating inputs and providing feedback.
- `mypinterest/views/js/mypinterest.js`:
  - **Scope**: Front-office.
  - **Description**: The main front-office JavaScript for the Pinterest Tag. Injects the `pintrk()` library, initializes the Pinterest Tag, and triggers standard events (PageView, AddToCart, Checkout, Purchase) based on DOM events or PrestaShop’s JavaScript hooks. Also responsible for generating `event_id` for deduplication and potentially sending AJAX calls to `controllers/front/ajax.php` for CAPI events.

### 4.5 CSS Stylesheets (`views/css/`)

- `mypinterest/views/css/mypinterest-admin.css`:
  - **Scope**: Back-office admin form styling.
  - **Description**: Styles for the module’s configuration page, including layout of tabs, input fields, buttons, and the dynamic panels for Live Statistics, Health Score, etc.
  - **Key CSS class selectors**: `.mypinterest-config`, `.mypinterest-tab-content`, `.mypinterest-health-score`, `.mypinterest-live-stats`.
- `mypinterest/views/css/mypinterest-debug.css`:
  - **Scope**: Front-office customer styling (only when debug mode is active).
  - **Description**: Provides styling for the debug overlay or console output, making debug information more readable for developers.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `mypinterest/views/templates/hook/capi-pageview.tpl`:
  - **Hook**: Likely `displayHeader` or `displayFooter`.
  - **Output**: Renders a hidden element or a small script to trigger a server-side PageView event via CAPI, often used for initial page load tracking or as a fallback.
- `mypinterest/views/templates/hook/debug.tpl`:
  - **Hook**: `displayHeader` or `displayFooter` (conditionally rendered).
  - **Output**: Injects the `mypinterest-debug.js` script and potentially a debug overlay HTML structure when debug mode is active.
- `mypinterest/views/templates/hook/displayOrderConfirmation.tpl`:
  - **Hook**: `displayOrderConfirmation`.
  - **Output**: Renders the Pinterest “Purchase” event script, including order details (value, currency, order ID, products) for both Pinterest Tag and CAPI (via AJAX call).
- `mypinterest/views/templates/hook/ghost.tpl`:
  - **Hook**: `displayHeader` or `displayFooter`.
  - **Output**: Potentially related to the `mypinterest-ghost.js` script, used for specific, possibly deferred or background, tracking mechanisms.
- `mypinterest/views/templates/hook/header.tpl`:
  - **Hook**: `displayHeader`.
  - **Output**: Injects the main Pinterest Tag base code (`pintrk()`) and `mypinterest.js` script. Initializes the Pinterest Tag with the Tag ID and potentially fires the initial “PageView” event.
- `mypinterest/views/templates/hook/payment.tpl`:
  - **Hook**: `displayPayment` or `displayPaymentTop`.
  - **Output**: Might be used to track the initiation of the checkout process or selection of a payment method, potentially firing a “Checkout” or “InitiateCheckout” event.
- `mypinterest/views/templates/hook/product-details.tpl`:
  - **Hook**: `displayProductButtons` or `displayFooterProduct`.
  - **Output**: Renders JavaScript to track “ViewContent” events when a product page is loaded, including product ID, name, price, and category. Also likely includes logic for “Add To Cart” events.

#### Admin templates (`views/templates/admin/`)

- `mypinterest/views/templates/admin/consent-guide.tpl`: Displays information and guidance on integrating with cookie consent modules.
- `mypinterest/views/templates/admin/doctor.tpl`: Renders the “Catalog Doctor” panel, showing diagnostics for product catalog data.
- `mypinterest/views/templates/admin/dq.tpl`: Renders the “Data Quality Coach” panel, providing recommendations for improving event data.
- `mypinterest/views/templates/admin/health.tpl`: Renders the “Health Score” panel, displaying the overall tracking health.
- `mypinterest/views/templates/admin/linker-domains.tpl`: Template for the “Linker Domains” input field.
- `mypinterest/views/templates/admin/live-maintain.tpl`: Possibly a maintenance or status message for the live statistics feature.
- `mypinterest/views/templates/admin/live.tpl`: Renders the “Live Statistics” panel, displaying real-time event logs.
- `mypinterest/views/templates/admin/mode-context.tpl`: Provides contextual information about the selected tracking mode.
- `mypinterest/views/templates/admin/mode-note-both.tpl`: Specific note/explanation for “Both (Hybrid)” tracking mode.
- `mypinterest/views/templates/admin/mode-note-capi.tpl`: Specific note/explanation for “Conversions API” tracking mode.
- `mypinterest/views/templates/admin/mode-note-tag.tpl`: Specific note/explanation for “Pinterest Tag” tracking mode.
- `mypinterest/views/templates/admin/mode-picker.tpl`: Renders the radio buttons or dropdown for selecting the “Tracking Mode.”
- `mypinterest/views/templates/admin/properties-list.tpl`: Displays a list of event properties and their status (e.g., required, recommended).
- `mypinterest/views/templates/admin/recent-events.tpl`: Renders a table or list of recent events for the “Live Statistics” panel.
- `mypinterest/views/templates/admin/tabs.tpl`: Renders the tab navigation structure for the module’s configuration page.
- `mypinterest/views/templates/admin/tag-chips.tpl`: Likely for displaying Pinterest Tag IDs in a visually appealing “chip” format.
- `mypinterest/views/templates/admin/tag-ids.tpl`: Renders input fields for Pinterest Tag ID and CAPI Access Token.
- `mypinterest/views/templates/admin/wizard.tpl`: Renders the step-by-step setup wizard interface.

#### Front-office templates (`views/templates/front/`)

- `mypinterest/views/templates/front/index.tpl`: A placeholder template, likely not used for direct rendering but as a default for the `MypinterestIndexModuleFrontController`.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module primarily uses `ps_configuration` for storing its settings (e.g., `MYPINTEREST_TAG_ID`, `MYPINTEREST_TRACKING_MODE`, `MYPINTEREST_CAPI_TOKEN`).
  - It may also use a custom table (e.g., `ps_mypinterest_events_log`) to store recent event data for the “Live Statistics” feature, though this could also be stored in `ps_configuration` as serialized data. (No explicit SQL files found, so likely `ps_configuration` or dynamic table creation).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Injects the base Pinterest Tag JavaScript, `mypinterest.js`, and potentially initial PageView events. |
| `displayOrderConfirmation` | On the order confirmation page after a successful purchase. | Triggers the “Purchase” event, sending detailed order and product data to Pinterest. |
| `displayProductButtons` | On the product page, near the “Add to Cart” button. | Injects JavaScript to track “ViewContent” events and “Add To Cart” events. |
| `displayFooter` | At the end of the `<body>` section of every page. | Can be used as an alternative or additional location for injecting scripts, especially for events that don’t need to block page rendering. |
| `actionCartSave` | When a cart is updated (e.g., product added/removed). | Triggers “AddToCart” or “RemoveFromCart” events, often handled server-side via CAPI or client-side via AJAX. |
| `actionValidateOrder` | After an order has been successfully validated. | Triggers the server-side “Purchase” event via CAPI for maximum reliability, complementing the client-side `displayOrderConfirmation` event. |
| `actionFrontControllerSetMedia` | When a front controller is setting its media (JS/CSS). | Allows the module to register its front-office JavaScript and CSS files. |
| `actionAdminControllerSetMedia` | When an admin controller is setting its media (JS/CSS). | Allows the module to register its back-office JavaScript and CSS files. |
| `actionObjectProductUpdateAfter` / `actionObjectProductAddAfter` | After a product is updated or added. | Potentially used for updating product catalog data or triggering catalog diagnostics. |
| `actionObjectProductDeleteAfter` | After a product is deleted. | Potentially used for updating product catalog data. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the Pinterest Tag & Conversions API module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist you with any technical issues or questions regarding the module’s functionality.
