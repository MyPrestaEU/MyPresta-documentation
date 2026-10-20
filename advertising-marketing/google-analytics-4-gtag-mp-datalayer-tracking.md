---
title: "Google Analytics 4 - gtag, MP & dataLayer tracking - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Google Analytics 4 - gtag, MP & dataLayer tracking PrestaShop module by MyPresta.eu."
sidebar:
  label: "Google Analytics 4 - gtag, MP & dataLayer tracking - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Google Analytics 4 - gtag, MP & dataLayer tracking Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/google-analytics-4-gtag-mp-datalayer-tracking.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/google-analytics-4-gtag-mp-datalayer-tracking/)
>
> ---


# Google Analytics 4 - gtag, MP & dataLayer tracking

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions such as cURL, JSON, and OpenSSL are required for the module to function correctly, especially for server-side Measurement Protocol tracking.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The “Google Analytics 4 - gtag, MP & dataLayer tracking” module offers a comprehensive set of configuration options, accessible through its main configuration page and dedicated admin screens.

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the primary screen where you’ll set up your GA4 tracking. The module uses a wizard-like interface to guide you through the initial setup, but you can always revisit and adjust settings.

#### **Initial Setup Wizard**

Upon first configuration, you’ll likely be greeted by a wizard. Follow its steps to quickly set up your primary GA4 property.

- **Step 1: Choose Tracking Mode**

  - **What this setting does:** Determines how your store sends data to Google Analytics 4. This is a crucial decision based on your technical setup and privacy requirements.
  - **Effect of changing this setting:**
    - *`gtag.js` (Recommended for most):* This is the standard Google Analytics 4 web tag. It loads a JavaScript library (`gtag.js`) directly on your store pages, which then sends data to GA4. It’s easy to implement but relies on client-side browser execution and cookie consent.
    - *`dataLayer` (For Google Tag Manager users):* This mode pushes all GA4 event data into the `dataLayer` object, which your Google Tag Manager (GTM) container then reads and sends to GA4. Choose this if you already use GTM for other tags and want centralized tag management.
    - *`Measurement Protocol` (Advanced, for maximum data recovery):* This mode sends data directly from your PrestaShop server to Google Analytics 4, bypassing the browser entirely. This is ideal for recovering data when `gtag.js` or `dataLayer` tracking is blocked by ad-blockers, browser settings, or denied cookie consent. It’s more complex but provides the most robust data collection.
  - **Recommended value:** `gtag.js` for simplicity, `dataLayer` if you use GTM, `Measurement Protocol` if data accuracy is paramount and you’re comfortable with advanced setup.
  - **Merchant scenario / example:** If you want to get started quickly and don’t use GTM, `gtag.js` is perfect. If you have a dedicated marketing team managing GTM, `dataLayer` integrates seamlessly. If you’re seeing significant discrepancies between your sales and GA4 data, `Measurement Protocol` can help close that gap.
- **Step 2: Enter Your GA4 Measurement ID(s)**

  - **What this setting does:** This is your unique identifier for your Google Analytics 4 property (e.g., `G-XXXXXXXXXX`). The module needs this to know where to send your data. You can add multiple IDs if you track different parts of your store in separate GA4 properties.
  - **Effect of changing this setting:** Data will be sent to the specified GA4 property. Incorrect IDs mean no data or data sent to the wrong place.
  - **Recommended value:** Your primary GA4 Measurement ID.
  - **Merchant scenario / example:** You have a main GA4 property `G-ABCDEF1234`. Enter this ID. If you also want to send specific product data to a separate property `G-XYZW5678`, you can add that too.
- **Step 3: Configure Consent Management (if applicable)**

  - **What this setting does:** Integrates with your store’s cookie consent solution to ensure GA4 tracking respects user privacy choices.
  - **Effect of changing this setting:**
    - *Enabled:* GA4 tags will only fire if the user has granted consent for analytics cookies.
    - *Disabled:* GA4 tags will fire regardless of consent (not recommended for GDPR/CCPA compliance).
  - **Recommended value:** Enabled, and ensure you have a robust cookie consent module installed and configured.
  - **Merchant scenario / example:** A customer visits your store and declines analytics cookies. With consent management enabled, the `gtag.js` or `dataLayer` scripts won’t load, preventing client-side tracking. If you’re using Measurement Protocol, you might still send anonymized purchase data server-side.

#### **General Settings (After Wizard)**

Once the wizard is complete, you’ll see a more detailed configuration interface, often organized into tabs.

- **Measurement IDs Management**

  - **What this setting does:** Allows you to add, edit, or remove multiple GA4 Measurement IDs (`G-XXXXXXXXXX`) and associate them with specific tracking modes.
  - **Effect of changing this setting:** Determines which GA4 properties receive data from your store.
  - **Recommended value:** Keep only the necessary GA4 properties.
  - **Merchant scenario / example:** You’ve created a new GA4 property for a specific marketing campaign. You can add its ID here to track campaign-specific performance.
- **Linker Domains (for cross-domain tracking)**

  - **What this setting does:** If your store operates across multiple domains (e.g., `shop.example.com` and `blog.example.com`), this setting helps Google Analytics understand that these are part of the same user journey, preventing new sessions from being started when a user navigates between them.
  - **Effect of changing this setting:** Ensures accurate user journey tracking across related domains. Without it, users moving between your domains might be counted as new users or new sessions.
  - **Recommended value:** Add all related domains that a user might visit as part of their journey on your site.
  - **Merchant scenario / example:** Your main store is `mystore.com` and your blog is `blog.mystore.com`. Add `blog.mystore.com` to the linker domains list.
- **Debug Mode**

  - **What this setting does:** Activates a special debug view in the front office and sends debug events to GA4, allowing you to verify that your tracking is working correctly.
  - **Effect of changing this setting:**
    - *Enabled:* A small debug panel appears on your store’s front office, showing which GA4 events are being sent. Events also appear in the GA4 DebugView.
    - *Disabled:* No debug panel, normal tracking.
  - **Recommended value:** Enable only during testing and troubleshooting. Disable for live production stores.
  - **Merchant scenario / example:** You’ve just installed the module and want to confirm that `add_to_cart` events are firing correctly. Enable debug mode, add a product to your cart, and check the debug panel and GA4 DebugView.
- **Data Quality Coach**

  - **What this setting does:** Provides insights and recommendations to improve the quality and completeness of your GA4 data. It checks for common issues like missing product IDs, incorrect currency formats, etc.
  - **Effect of changing this setting:** This is a diagnostic tool; it doesn’t directly change front-office behavior but helps you identify and fix issues that could lead to inaccurate analytics.
  - **Recommended value:** Regularly review the recommendations.
  - **Merchant scenario / example:** The coach might tell you that some products are missing EAN/UPC codes, which are valuable for GA4 product data. You can then update your product catalog.
- **Catalog Doctor**

  - **What this setting does:** Analyzes your product catalog for potential issues that could affect GA4 tracking, such as products without prices, images, or valid categories.
  - **Effect of changing this setting:** Similar to the Data Quality Coach, this is a diagnostic tool to ensure your product data is robust for GA4.
  - **Recommended value:** Periodically run this check.
  - **Merchant scenario / example:** The doctor might flag products that are out of stock but still visible, which could confuse GA4 tracking of product views.
- **Live Statistics**

  - **What this setting does:** Displays real-time event data being sent from your store to GA4, directly within your PrestaShop back office.
  - **Effect of changing this setting:** Provides an immediate overview of recent user interactions and events.
  - **Recommended value:** Useful for monitoring, especially after making changes or during peak traffic.
  - **Merchant scenario / example:** You’ve just launched a new product. You can watch the live stats to see `view_item` and `add_to_cart` events in real-time.
- **Event Mapping & Customization**

  - **What this setting does:** Allows you to customize how PrestaShop actions map to GA4 events and their parameters. For example, you might want to send a custom parameter with the `purchase` event.
  - **Effect of changing this setting:** Fine-tunes the data sent to GA4, enabling more specific reporting and audience creation.
  - **Recommended value:** Only modify if you have specific GA4 reporting needs.
  - **Merchant scenario / example:** You want to include a custom `loyalty_program_status` parameter with every `purchase` event. You can configure this mapping here.
- **Multi-Property Rules**

  - **What this setting does:** Defines rules for sending specific events or data to different GA4 properties. For instance, you might send all events to your main property but only “purchase” events for a specific category to a separate property.
  - **Effect of changing this setting:** Enables advanced segmentation of your analytics data across multiple GA4 properties.
  - **Recommended value:** Use if you have complex tracking requirements involving multiple GA4 properties.
  - **Merchant scenario / example:** You have a main GA4 property for your entire store, but you also have a separate property for your “Premium Products” line. You can set a rule to send `purchase` events for products in the “Premium Products” category to both properties.

### 2.2 Dedicated Admin Screens & Controller Views

The module also provides dedicated screens for more advanced management and diagnostics.

#### **AdminMyanalyticsAjaxController (Back Office > Modules > Google Analytics 4 > [Various Tabs])**

This controller handles many of the interactive elements and data displays within the module’s configuration, particularly for the diagnostic tools and live statistics. You won’t directly navigate to this controller; it powers the dynamic content on the main configuration page.

- **Screen Name & Menu Location:** This controller is not a standalone menu item. It serves the AJAX requests for the various tabs and sections within the main module configuration page (e.g., “Data Quality Coach”, “Catalog Doctor”, “Live Statistics”).
- **Available Actions & Settings:**
  - **Data Quality Coach Grid:** Displays a table of detected data quality issues, often with suggestions for resolution.
  - **Catalog Doctor Report:** Shows a report on product data integrity.
  - **Live Events Stream:** A real-time feed of events being sent to GA4.
  - **Wizard Steps:** Handles the progression and data submission for the initial setup wizard.
- **Effect of changes:** Interacting with these elements (e.g., clicking “Run Check” for the Data Quality Coach) triggers background processes that analyze your store data and update the displayed information. It helps you diagnose and fix issues, but doesn’t directly change front-office behavior.
- **Recommended workflow for daily store management:** Regularly check the “Data Quality Coach” and “Catalog Doctor” tabs to ensure your GA4 data remains accurate. Monitor “Live Statistics” during critical periods or after major store changes.

#### **index.php (Back Office > Modules > Google Analytics 4)**

This is the main entry point for the module’s configuration in the back office. While it’s named `index.php`, it’s the core of the `getContent()` method that renders the entire configuration interface, including all the tabs and settings described in section 4.1.

- **Screen Name & Menu Location:** **Modules > Module Manager > Google Analytics 4 - gtag, MP & dataLayer tracking > Configure**.
- **Available Actions & Settings:** All the settings, tabs, and wizard steps mentioned in section 4.1 are rendered and managed through this main configuration view.
- **Effect of changes:** Any changes saved on this screen directly impact how your GA4 tracking is implemented and what data is sent to Google Analytics.
- **Recommended workflow for daily store management:** This is where you’ll initially set up the module and return for any major changes to your GA4 properties, tracking modes, or advanced rules.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Main Config | **Tracking Mode** | `gtag.js` | Defines how data is sent (client-side, GTM, or server-side). Crucial for data accuracy and privacy. |
| Main Config | **Measurement ID(s)** | Your GA4 ID (`G-XXXXXXXXXX`) | Specifies which GA4 property receives data. Incorrect IDs mean no data. |
| Main Config | **Consent Management** | Enabled (if using consent module) | Ensures GA4 tracking respects user privacy choices. |
| Main Config | **Linker Domains** | Empty (add if cross-domain) | Enables accurate user tracking across multiple related domains. |
| Main Config | **Debug Mode** | Disabled (enable for testing) | Shows a front-office debug panel and sends debug events to GA4. |
| Main Config | **Data Quality Coach** | N/A (diagnostic tool) | Identifies and suggests fixes for GA4 data quality issues. |
| Main Config | **Catalog Doctor** | N/A (diagnostic tool) | Analyzes product catalog for GA4 tracking readiness. |
| Main Config | **Live Statistics** | N/A (monitoring tool) | Displays real-time GA4 events in the back office. |
| Main Config | **Event Mapping** | Default (modify for custom needs) | Customizes how PrestaShop actions map to GA4 events and parameters. |
| Main Config | **Multi-Property Rules** | None (add for advanced tracking) | Defines rules for sending specific data to different GA4 properties. |
| AdminMyanalyticsAjaxController | (Various AJAX-driven views) | N/A | Powers dynamic content for diagnostic tools and live stats. |
| index.php | (Main configuration page) | N/A | Renders the entire module configuration interface. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve installed the module, but I don’t see any data in my Google Analytics 4 property.**

- **A:** First, ensure you’ve entered the correct GA4 Measurement ID (starting with `G-`) in the module’s configuration.
- **A:** Check your GA4 property’s “DebugView” (in Google Analytics, go to Admin > DebugView) while browsing your store. If you see events there, data is being sent.
- **A:** Clear your PrestaShop Smarty cache (Advanced Parameters > Performance > Clear cache).
- **A:** If you’re using `gtag.js` or `dataLayer`, check your browser’s developer console (F12) for any JavaScript errors. Also, ensure you’ve accepted analytics cookies if you have a consent module.
- **A:** If using Measurement Protocol, ensure your server has `cURL` enabled and there are no firewall rules blocking outbound connections to Google’s servers.

**Q2: My GA4 purchase data doesn’t match my PrestaShop order data.**

- **A:** This is a common issue, often due to ad-blockers, browser privacy settings, or users declining cookie consent.
- **A:** **Strongly consider enabling Measurement Protocol for purchase events.** This sends purchase data directly from your server, bypassing client-side browser issues.
- **A:** Use the module’s “Data Quality Coach” and “Catalog Doctor” to identify any data inconsistencies that might be causing issues.
- **A:** Ensure your order confirmation page is always reached by customers after a successful purchase. If customers are redirected elsewhere or close the browser too soon, client-side purchase events might not fire.

**Q3: The module’s debug panel isn’t showing up, or I don’t see events in GA4 DebugView.**

- **A:** Make sure “Debug Mode” is explicitly enabled in the module’s configuration.
- **A:** Clear your browser cache and PrestaShop Smarty cache.
- **A:** Ensure you are logged in as an administrator in your PrestaShop back office and are browsing the front office in the same browser session.
- **A:** Check your browser’s developer console for any JavaScript errors that might prevent the debug panel from loading.

**Q4: How do I ensure the module respects my cookie consent module?**

- **A:** The module is designed to integrate with standard cookie consent mechanisms. In the module’s configuration, there should be a setting for “Consent Management.” Ensure this is enabled.
- **A:** Verify that your cookie consent module is correctly categorizing analytics cookies and that users’ choices are being stored and respected. The GA4 module will then only load client-side tags (`gtag.js`, `dataLayer`) if consent is given.
- **A:** For maximum data recovery, consider using Measurement Protocol for critical events like `purchase`, as it can often bypass client-side consent issues (though you should still inform users about data processing).

**Q5: I want to track custom events or parameters not covered by the default setup.**

- **A:** The module includes an “Event Mapping & Customization” section. Here, you can define how PrestaShop actions map to GA4 events and add custom parameters.
- **A:** For highly complex custom tracking, especially with `dataLayer`, you might need to combine this module’s capabilities with custom scripts in your Google Tag Manager container.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The `myanalytics` module for PrestaShop is designed to provide robust and flexible Google Analytics 4 integration. It follows a modular, object-oriented approach, leveraging PrestaShop’s MVC pattern and hook system.

Key architectural components:

- **Main Module Class (`Myanalytics`):** Handles installation, uninstallation, hook registration, and the primary `getContent()` method for back-office configuration.
- **Tracker Factory (`MyanalyticsTrackerFactory`):** Dynamically instantiates the appropriate tracking mechanism (`gtag.js`, `dataLayer`, or `Measurement Protocol`) based on module configuration.
- **Dedicated Tracker Classes:** Each tracking method (`MyanalyticsGtagTracker`, `MyanalyticsDataLayerTracker`, `MyanalyticsMpTracker`) implements `MyanalyticsTrackerInterface` and encapsulates the logic for sending GA4 events via its specific method.
- **Event Mapping & Data Layer Management:** Classes like `MyanalyticsEvents` and `MyanalyticsDataLayerTracker` are responsible for translating PrestaShop actions (e.g., product view, add to cart) into GA4-compliant event names and parameters.
- **Diagnostic Tools:** Classes like `MyanalyticsDataQualityCoach`, `MyanalyticsCatalogDoctor`, and `MyanalyticsHealthScore` provide back-office insights into data integrity and tracking health.
- **Admin Controllers:** Handle AJAX requests for dynamic content in the back office (e.g., live stats, diagnostic reports).
- **Front Controllers:** Primarily used for AJAX endpoints, especially for Measurement Protocol fallback or consent-related actions.
- **Smarty Templates:** Used for rendering both back-office configuration views and front-office tracking scripts injected via hooks.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `controllers/front/ajax.php`
  - **Class name & parent class:** `MyanalyticsAjaxModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** Handles AJAX requests from the front office. This might include sending Measurement Protocol events in specific scenarios (e.g., when client-side tracking is blocked), updating consent status, or other dynamic interactions that don’t require a full page reload. It typically returns JSON responses.
- `controllers/front/index.php`
  - **Class name & parent class:** `MyanalyticsIndexModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** This controller might serve as a fallback or a specific endpoint for certain module functionalities, though often the main module class handles most front-office script injection via hooks. It could be used for specific redirects or data processing if needed.

#### Back-Office Admin Controllers

- `controllers/admin/AdminMyanalyticsAjaxController.php`
  - **Class name & parent class:** `AdminMyanalyticsAjaxController` extends `AdminController`.
  - **Tab name and managed entity:** This controller is not directly accessible as a menu tab. It serves AJAX requests from the module’s main configuration page (`getContent()`). It handles dynamic updates for sections like the Data Quality Coach, Catalog Doctor, Live Statistics, and the setup wizard steps.
  - **Responsibility:** Processes requests for diagnostic reports, live event data, and wizard step submissions, returning JSON data to update the back-office UI.
- `controllers/admin/index.php`
  - **Class name & parent class:** `AdminMyanalyticsIndexController` extends `AdminController`.
  - **Tab name and managed entity:** Similar to `AdminMyanalyticsAjaxController`, this is likely an internal controller or a placeholder. The primary back-office configuration is handled by the `getContent()` method of the main `Myanalytics` module class.

### 4.3 Core Classes & Models (`classes/`)

- `classes/autoload.php`: Standard PrestaShop autoload file for module classes.
- `classes/index.php`: Empty file, common practice to prevent directory listing.
- `classes/MyanalyticsCatalogDoctor.php`
  - **What it does:** Analyzes the PrestaShop product catalog for data quality issues relevant to GA4 tracking (e.g., missing prices, images, invalid categories).
  - **Key public methods:** Methods to run checks and retrieve reports on catalog health.
- `classes/MyanalyticsConsent.php`
  - **What it does:** Manages and interacts with cookie consent mechanisms, determining if analytics tracking is permitted based on user choices.
  - **Key public methods:** Methods to check consent status, set consent, and potentially integrate with third-party consent modules.
- `classes/MyanalyticsCurrencyHelper.php`
  - **What it does:** Provides utility functions for handling currency formatting and conversion, ensuring GA4 receives currency data in the correct format.
- `classes/MyanalyticsDataLayerTracker.php`
  - **What it does:** Implements `MyanalyticsTrackerInterface` for `dataLayer` tracking. It pushes GA4 event data into the JavaScript `dataLayer` array, making it available for Google Tag Manager.
  - **Key public methods:** Methods to add events to the dataLayer, handle specific e-commerce events (e.g., `add_to_cart`, `purchase`).
- `classes/MyanalyticsDataQualityCoach.php`
  - **What it does:** Provides a diagnostic tool to identify and report on potential data quality issues in the GA4 event stream or configuration.
  - **Key public methods:** Methods to run data quality checks and generate reports.
- `classes/MyanalyticsEventId.php`
  - **What it does:** Likely a utility class for generating unique event IDs, which can be useful for deduplication in GA4, especially with Measurement Protocol.
- `classes/MyanalyticsEventMap.php`
  - **What it does:** Defines the mapping between PrestaShop actions/data and standard GA4 event names and parameters.
  - **Key public methods:** Methods to retrieve event definitions and parameter mappings.
- `classes/MyanalyticsEvents.php`
  - **What it does:** A central class for triggering and managing GA4 events within the module. It orchestrates which tracker (gtag, datalayer, MP) should handle which event.
  - **Key public methods:** Methods like `trackPageView()`, `trackAddToCart()`, `trackPurchase()`, etc.
- `classes/MyanalyticsGtagTracker.php`
  - **What it does:** Implements `MyanalyticsTrackerInterface` for `gtag.js` tracking. It generates and injects the necessary JavaScript code to send events directly to GA4 via `gtag()`.
  - **Key public methods:** Methods to generate `gtag()` calls for various GA4 events.
- `classes/MyanalyticsHealthScore.php`
  - **What it does:** Calculates and displays a “health score” for the GA4 integration, based on various checks and best practices.
- `classes/MyanalyticsLiveStats.php`
  - **What it does:** Collects and provides real-time statistics on events being sent to GA4, displayed in the back office.
- `classes/MyanalyticsMpClient.php`
  - **What it does:** Handles the actual HTTP requests for sending data to Google Analytics 4 via the Measurement Protocol.
  - **Key public methods:** Methods to construct and send Measurement Protocol payloads.
- `classes/MyanalyticsMpTracker.php`
  - **What it does:** Implements `MyanalyticsTrackerInterface` for `Measurement Protocol` tracking. It prepares event data and uses `MyanalyticsMpClient` to send it server-side.
  - **Key public methods:** Methods to format and send server-side events.
- `classes/MyanalyticsProductIdResolver.php`
  - **What it does:** Resolves various product identifiers (ID, reference, EAN, UPC) to ensure consistent product data is sent to GA4.
- `classes/MyanalyticsPropertyRules.php`
  - **What it does:** Manages the logic for multi-property tracking, defining rules for which events go to which GA4 properties.
- `classes/MyanalyticsTrackerFactory.php`
  - **What it does:** A factory pattern class responsible for creating and returning the correct `MyanalyticsTrackerInterface` implementation based on the module’s configuration (gtag, datalayer, or MP).
- `classes/MyanalyticsTrackerInterface.php`
  - **What it does:** Defines the common interface that all GA4 tracker classes must implement, ensuring consistency in how events are handled.
- `classes/MyanalyticsUserData.php`
  - **What it does:** Collects and formats user-specific data (e.g., user ID, demographics) for GA4 tracking, respecting privacy settings.

### 4.4 JavaScript Assets (`views/js/`)

- `myanalytics/views/js/myanalytics-admin.js`
  - **Scope:** Back-office.
  - **What it does:** Provides interactive functionality for the module’s back-office configuration pages. This includes handling form submissions, AJAX calls for diagnostic tools (Data Quality Coach, Catalog Doctor), updating live statistics, and managing multi-property rules.
- `myanalytics/views/js/myanalytics-debug.js`
  - **Scope:** Front-office (when debug mode is enabled).
  - **What it does:** Injects a debug panel into the front office, displaying GA4 events as they are triggered. It listens for `gtag()` calls or `dataLayer.push()` events and renders them for easy verification.
- `myanalytics/views/js/myanalytics-ghost.js`
  - **Scope:** Front-office.
  - **What it does:** This script might be related to “ghost” or “shadow” tracking, potentially for Measurement Protocol fallback or to capture events that might otherwise be missed. It could involve listening for specific DOM events and triggering server-side calls.
- `myanalytics/views/js/myanalytics-live.js`
  - **Scope:** Back-office.
  - **What it does:** Powers the “Live Statistics” feature in the back office. It likely uses AJAX to periodically fetch recent GA4 events from the server and updates the display in real-time.
- `myanalytics/views/js/myanalytics-wizard.js`
  - **Scope:** Back-office.
  - **What it does:** Provides the interactive logic for the module’s setup wizard, guiding the user through initial configuration steps, validating inputs, and submitting data via AJAX.
- `myanalytics/views/js/myanalytics.js`
  - **Scope:** Front-office.
  - **What it does:** The main front-office JavaScript file. It handles the core client-side GA4 tracking logic, including:
    - Initializing `gtag.js` or `dataLayer`.
    - Listening for DOM events (e.g., clicks on “Add to Cart” buttons, product image views).
    - Collecting relevant product and user data.
    - Pushing events to `dataLayer` or calling `gtag()` commands.
    - Potentially handling cookie consent integration.

### 4.5 CSS Stylesheets (`views/css/`)

- `myanalytics/views/css/myanalytics-admin.css`
  - **Scope:** Back-office admin form styling.
  - **What it does:** Styles the module’s configuration page, including tabs, input fields, buttons, diagnostic reports, and live statistics displays, ensuring a consistent and user-friendly interface within the PrestaShop back office.
- `myanalytics/views/css/myanalytics-debug.css`
  - **Scope:** Front-office customer styling (when debug mode is enabled).
  - **What it does:** Styles the front-office debug panel, making it visually distinct and readable for developers and administrators.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `myanalytics/views/templates/hook/debug.tpl`
  - **Hook:** Likely injected via `displayHeader` or `displayFooter` conditionally when debug mode is active.
  - **Outputs:** The HTML structure for the front-office debug panel.
- `myanalytics/views/templates/hook/displayOrderConfirmation.tpl`
  - **Hook:** `displayOrderConfirmation`.
  - **Outputs:** The necessary JavaScript code or `dataLayer` pushes for the `purchase` event, typically including transaction details, product information, and potentially Measurement Protocol parameters.
- `myanalytics/views/templates/hook/ghost.tpl`
  - **Hook:** Could be `displayHeader` or `displayFooter`.
  - **Outputs:** JavaScript code related to “ghost” tracking, potentially for Measurement Protocol fallback or advanced event capture.
- `myanalytics/views/templates/hook/header.tpl`
  - **Hook:** `displayHeader`.
  - **Outputs:** The primary `gtag.js` or `dataLayer` initialization script, including the GA4 Measurement ID(s) and any global configuration settings. This is crucial for initial page view tracking.
- `myanalytics/views/templates/hook/mp-pageview.tpl`
  - **Hook:** Likely `displayHeader` or `displayFooter` (conditionally for Measurement Protocol).
  - **Outputs:** Server-side rendered code to send a `page_view` event via Measurement Protocol, especially useful when client-side tracking is blocked or consent is denied.
- `myanalytics/views/templates/hook/payment.tpl`
  - **Hook:** `displayPaymentTop` or similar payment-related hooks.
  - **Outputs:** JavaScript or `dataLayer` pushes for `add_payment_info` or `begin_checkout` events, capturing payment method selection.
- `myanalytics/views/templates/hook/product-details.tpl`
  - **Hook:** `displayProductButtons`, `displayProductExtraContent`, or similar product page hooks.
  - **Outputs:** JavaScript or `dataLayer` pushes for `view_item` and `add_to_cart` events, including detailed product information.

#### Admin templates (`views/templates/admin/`)

- `myanalytics/views/templates/admin/doctor.tpl`: Renders the interface for the Catalog Doctor, displaying reports and recommendations.
- `myanalytics/views/templates/admin/dq.tpl`: Renders the interface for the Data Quality Coach, showing data quality issues.
- `myanalytics/views/templates/admin/health.tpl`: Displays the overall health score and related metrics for the GA4 integration.
- `myanalytics/views/templates/admin/linker-domains.tpl`: Renders the input field and list for managing cross-domain linker domains.
- `myanalytics/views/templates/admin/live-maintain.tpl`: Likely a sub-template for the live statistics, possibly for maintenance messages or controls.
- `myanalytics/views/templates/admin/live.tpl`: Renders the main interface for the Live Statistics feature, showing real-time event data.
- `myanalytics/views/templates/admin/measurement-ids.tpl`: Renders the section for managing multiple GA4 Measurement IDs.
- `myanalytics/views/templates/admin/mode-context.tpl`: Provides contextual information or explanations for the chosen tracking mode.
- `myanalytics/views/templates/admin/mode-note-datalayer.tpl`: Specific notes or instructions for `dataLayer` tracking mode.
- `myanalytics/views/templates/admin/mode-note-gtag.tpl`: Specific notes or instructions for `gtag.js` tracking mode.
- `myanalytics/views/templates/admin/mode-note-mp.tpl`: Specific notes or instructions for `Measurement Protocol` tracking mode.
- `myanalytics/views/templates/admin/mode-picker.tpl`: Renders the radio buttons or dropdown for selecting the GA4 tracking mode.
- `myanalytics/views/templates/admin/properties-list.tpl`: Displays a list of configured GA4 properties.
- `myanalytics/views/templates/admin/recent-events.tpl`: A sub-template for displaying a list of recent events, often used in live stats or debug views.
- `myanalytics/views/templates/admin/tabs.tpl`: Renders the tab navigation structure for the module’s configuration page.
- `myanalytics/views/templates/admin/tag-chips.tpl`: Displays visual “chips” or labels for configured GA4 tags/properties.
- `myanalytics/views/templates/admin/wizard.tpl`: Renders the overall structure and steps of the module’s setup wizard.

#### Front-office templates (`views/templates/front/`)

The module does not appear to have dedicated standalone front-office page templates, relying instead on injecting scripts and data via hooks.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module primarily stores its configuration in PrestaShop’s `ps_configuration` table.
  - It might also create custom tables for:
    - `ps_myanalytics_events`: To log Measurement Protocol events or other internal event data for debugging/live stats.
    - `ps_myanalytics_properties`: To store details about multiple GA4 properties and their associated rules.
    - `ps_myanalytics_consent`: To store consent status or integrate with consent modules.
    - `ps_myanalytics_health_log`: To store results from health checks and data quality reports.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Inject `gtag.js` or `dataLayer` initialization scripts, global GA4 configuration, and potentially `page_view` events. |
| `displayFooter` | Before the closing `</body>` tag of every page. | Inject additional tracking scripts, debug panels, or fallback Measurement Protocol calls. |
| `displayOrderConfirmation` | On the order confirmation page after a successful purchase. | Send the crucial `purchase` event to GA4, including transaction details and product data. This is often where Measurement Protocol is leveraged. |
| `displayProductButtons` | Near product action buttons (e.g., “Add to Cart”) on the product page. | Inject JavaScript to capture `add_to_cart` events. |
| `displayProductExtraContent` | In the extra content section of the product page. | Inject JavaScript for `view_item` events or other product detail interactions. |
| `displayPaymentTop` | Before the payment options on the checkout page. | Capture `begin_checkout` and `add_payment_info` events. |
| `actionFrontControllerSetMedia` | When a front controller is setting its media assets. | Enqueue module-specific JS/CSS files for the front office. |
| `actionAdminControllerSetMedia` | When an admin controller is setting its media assets. | Enqueue module-specific JS/CSS files for the back office. |
| `actionValidateOrder` | After an order has been successfully validated. | Trigger server-side Measurement Protocol `purchase` events, ensuring data capture even if client-side fails. |
| `actionObjectProductAddAfter` | After a new product is added. | Potentially trigger catalog doctor checks or update internal product data caches. |
| `actionObjectProductUpdateAfter` | After an existing product is updated. | Similar to `actionObjectProductAddAfter`. |
| `actionObjectProductDeleteAfter` | After a product is deleted. | Clean up any associated tracking data or caches. |

## 5. Official Support & Updates

For official updates, technical support, and to ensure you are running the latest, most compatible version of the “Google Analytics 4 - gtag, MP & dataLayer tracking” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/).

MyPresta.eu provides dedicated support for all its modules, ensuring your store’s analytics integration remains robust and up-to-date with the latest GA4 standards and PrestaShop versions.
