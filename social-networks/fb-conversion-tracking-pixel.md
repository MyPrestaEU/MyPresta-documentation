---
title: "Fb conversion tracking pixel - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Fb conversion tracking pixel PrestaShop module by MyPresta.eu."
sidebar:
  label: "Fb conversion tracking pixel - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Fb conversion tracking pixel Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/fb-conversion-tracking-pixel.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/fb-conversion-tracking-pixel/)
>
> ---


# Fb conversion tracking pixel

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions like cURL, JSON, and OpenSSL are required for the module to function correctly, especially for the Conversions API (CAPI) features. These are typically available on all modern hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, you’ll land on the main configuration page. This is where you’ll connect your store to Facebook and customize how events are tracked.

#### General Settings Tab

- **Pixel ID(s):**

  - **What this setting does:** This is the unique identifier for your Facebook Pixel. You can find this in your Facebook Business Manager or Events Manager. You can enter multiple Pixel IDs separated by commas if you manage several pixels.
  - **Effect of changing this setting:**
    - *When filled:* The module will embed the Facebook Pixel code on your store’s front office, sending data to the specified Pixel ID(s).
    - *When empty:* No Facebook Pixel tracking will occur.
  - **Recommended value:** Your primary Facebook Pixel ID.
  - **Merchant scenario / example:** You have a main pixel for your brand and a secondary pixel for a specific product line. Enter both here: `1234567890,9876543210`.
- **CAPI Access Token:**

  - **What this setting does:** This token enables the Facebook Conversions API (CAPI), which sends conversion data directly from your server to Facebook, bypassing browser limitations (like ad blockers or cookie restrictions). This improves data accuracy.
  - **Effect of changing this setting:**
    - *When filled:* The module will attempt to send server-side events to Facebook using CAPI, in addition to or instead of browser-side pixel events, depending on your other settings.
    - *When empty:* Only browser-side pixel tracking will occur (if Pixel ID is set).
  - **Recommended value:** Highly recommended to use CAPI for better data accuracy. Generate this token in your Facebook Events Manager.
  - **Merchant scenario / example:** You want to ensure maximum data accuracy for your purchase events, even if customers use ad blockers. You generate an access token in Facebook Events Manager and paste it here.
- **Test Event Code:**

  - **What this setting does:** This code is used to test your CAPI setup in Facebook Events Manager. When entered, the module will send test events, allowing you to verify that your server-side tracking is working correctly.
  - **Effect of changing this setting:**
    - *When filled:* CAPI events will include this test code, making them visible in the Facebook Events Manager’s “Test Events” tab.
    - *When empty:* CAPI events will be sent as live events.
  - **Recommended value:** Use only when actively testing your CAPI setup. Remove it once testing is complete.
  - **Merchant scenario / example:** You’ve just set up CAPI and want to confirm it’s sending data. You copy the test code from Facebook Events Manager, paste it here, perform a test purchase on your site, and then check the “Test Events” tab in Facebook.
- **Consent mode:**

  - **What this setting does:** This option integrates with your store’s cookie consent solution (e.g., GDPR modules). It determines whether Facebook Pixel events are fired only after a customer has given consent.
  - **Effect of changing this setting:**
    - *When enabled:* Pixel events will only fire if the customer has accepted cookies.
    - *When disabled:* Pixel events will fire regardless of cookie consent (use with caution, depending on local privacy laws).
  - **Recommended value:** “Yes” if you operate in regions with strict privacy laws (like GDPR in Europe).
  - **Merchant scenario / example:** Your store targets customers in the EU. You enable this setting to comply with GDPR, ensuring pixel data is only collected from users who explicitly agree to cookie usage.
- **Paid statuses:**

  - **What this setting does:** Selects which order statuses in PrestaShop should trigger a “Purchase” event to Facebook. Typically, this includes statuses like “Payment accepted” or “Delivered”.
  - **Effect of changing this setting:**
    - *When selected:* Orders reaching these statuses will send a “Purchase” event to Facebook.
    - *When not selected:* Orders will not send a “Purchase” event when they reach these statuses.
  - **Recommended value:** Select all statuses that genuinely represent a completed and paid order.
  - **Merchant scenario / example:** You consider an order “paid” when it’s “Payment accepted” and “Shipped”. You select both of these statuses.
- **Refund / cancel statuses:**

  - **What this setting does:** Selects which order statuses indicate a refund or cancellation. This allows the module to potentially send a “Refund” or “Cancel” event (if supported by Facebook’s API and the module’s version) or to prevent false positive purchase tracking.
  - **Effect of changing this setting:**
    - *When selected:* The module will recognize these orders as non-purchase or refunded.
    - *When not selected:* These orders might still be counted as purchases if they previously hit a “Paid status.”
  - **Recommended value:** Select statuses like “Canceled,” “Refunded,” “Payment error.”
  - **Merchant scenario / example:** A customer cancels an order. You want to ensure this isn’t counted as a successful purchase. You select “Canceled” and “Refunded” here.

#### Advanced Settings Tab

- **Add to cart CSS selector:**

  - **What this setting does:** This is a technical setting that helps the module identify the “Add to Cart” button on your product pages. If your theme uses a non-standard button, you might need to specify its CSS selector.
  - **Effect of changing this setting:**
    - *When correct:* The “AddToCart” event will fire reliably when a customer clicks the button.
    - *When incorrect or empty (and auto-detection fails):* The “AddToCart” event might not fire, leading to missing data.
  - **Recommended value:** Leave empty first; the module often auto-detects. If “AddToCart” events are missing, consult your theme developer or use your browser’s inspector to find the correct CSS selector (e.g., `.add-to-cart-button`).
  - **Merchant scenario / example:** Your custom theme has a unique “Add to Cart” button. You inspect the button in your browser and find its class is `my-custom-add-button`. You enter `.my-custom-add-button` here.
- **Product price CSS selector:**

  - **What this setting does:** Similar to the Add to Cart selector, this helps the module accurately find the product’s price on the page, especially for dynamic pricing or specific theme layouts.
  - **Effect of changing this setting:**
    - *When correct:* The “value” parameter for events like “ViewContent” and “AddToCart” will accurately reflect the product’s price.
    - *When incorrect or empty (and auto-detection fails):* The “value” parameter might be missing or incorrect, impacting ad optimization.
  - **Recommended value:** Leave empty first. If price values are incorrect in Facebook Events Manager, find the correct CSS selector (e.g., `.current-price span[itemprop="price"]`).
  - **Merchant scenario / example:** Your product page displays prices in a non-standard way. You identify the CSS selector for the price element to ensure Facebook receives the correct value.
- **Product identification:**

  - **What this setting does:** Determines which product identifier (ID) your store sends to Facebook. Options typically include `ID` (PrestaShop’s internal product ID), `Reference` (your product’s SKU), or `EAN13` / `UPC` (barcode numbers). This is crucial for matching products in your Facebook Catalog.
  - **Effect of changing this setting:**
    - *When set:* Facebook will receive the chosen ID type, which should match the IDs in your Facebook Product Catalog for dynamic ads to work.
    - *When mismatched with your catalog:* Dynamic ads might not display the correct products or might fail to show at all.
  - **Recommended value:** Choose the ID that you use consistently in your Facebook Product Catalog. `Reference` (SKU) is often a good choice if unique.
  - **Merchant scenario / example:** Your Facebook Product Catalog uses your product’s SKU as the unique identifier. You select “Reference” here to ensure a perfect match.
- **Separator:**

  - **What this setting does:** If you use a combination of product ID and attribute ID (e.g., for different sizes/colors), this defines the character used to separate them in the Facebook ID.
  - **Effect of changing this setting:**
    - *When set:* The product ID sent to Facebook will be `ProductID` + `Separator` + `AttributeID`.
    - *When empty:* Only the base product ID might be sent, potentially causing issues with tracking specific product variations.
  - **Recommended value:** A common separator like `-` or `_`.
  - **Merchant scenario / example:** You sell a T-shirt (ID 123) in different sizes (attribute ID 10 for S, 11 for M). If you set the separator to `-`, Facebook will receive `123-10` for a small T-shirt.
- **Product ID prefix / Product ID suffix:**

  - **What this setting does:** Allows you to add text before or after the product ID sent to Facebook. This is useful if your Facebook Product Catalog IDs have a specific format that differs from your PrestaShop IDs.
  - **Effect of changing this setting:**
    - *When set:* The final product ID sent to Facebook will be `Prefix` + `ProductID` + `Suffix`.
    - *When empty:* Only the raw product ID (and separator/attribute ID if applicable) is sent.
  - **Recommended value:** Leave empty unless your Facebook Product Catalog requires it.
  - **Merchant scenario / example:** Your Facebook Product Catalog requires all product IDs to start with “PS\_”. You enter `PS_` in the “Product ID prefix” field.
- **Target currency:**

  - **What this setting does:** Specifies the currency in which event values (like purchase amount) are sent to Facebook. This is crucial for accurate reporting and ad optimization, especially for multi-currency stores.
  - **Effect of changing this setting:**
    - *When set:* All event values will be converted and sent in this target currency.
    - *When empty:* The module will attempt to use the currency of the current shop context or the customer’s selected currency.
  - **Recommended value:** Your primary advertising currency (e.g., USD, EUR).
  - **Merchant scenario / example:** Your store sells in EUR, USD, and GBP, but all your Facebook ads are managed in USD. You set “Target currency” to “USD” to ensure all conversion values are reported consistently in USD.

#### Event Tracking Settings Tab

This section allows you to enable or disable specific Facebook Pixel events. Only enable the events you actively want to track.

- **Pageview Event:**

  - **What this setting does:** Tracks when a customer views any page on your website.
  - **Effect of changing this setting:**
    - *When enabled:* A `PageView` event is sent on every page load.
    - *When disabled:* No `PageView` events are sent.
  - **Recommended value:** Yes. This is a fundamental event for all tracking.
- **Purchase Event:**

  - **What this setting does:** Tracks when a customer completes a purchase. This is the most critical conversion event.
  - **Effect of changing this setting:**
    - *When enabled:* A `Purchase` event is sent on the order confirmation page and/or via CAPI when an order reaches a “Paid status.”
    - *When disabled:* No `Purchase` events are sent.
  - **Recommended value:** Yes. Absolutely essential for e-commerce advertising.
- **ViewContent Event:**

  - **What this setting does:** Tracks when a customer views a product page.
  - **Effect of changing this setting:**
    - *When enabled:* A `ViewContent` event is sent when a product page is loaded.
    - *When disabled:* No `ViewContent` events are sent.
  - **Recommended value:** Yes. Important for dynamic product ads and remarketing.
- **AddToCart Event:**

  - **What this setting does:** Tracks when a customer adds an item to their shopping cart.
  - **Effect of changing this setting:**
    - *When enabled:* An `AddToCart` event is sent when an item is added to the cart.
    - *When disabled:* No `AddToCart` events are sent.
  - **Recommended value:** Yes. Crucial for abandoned cart recovery campaigns.
- **RemoveFromCart Event:**

  - **What this setting does:** Tracks when a customer removes an item from their shopping cart.
  - **Effect of changing this setting:**
    - *When enabled:* A `RemoveFromCart` event is sent when an item is removed.
    - *When disabled:* No `RemoveFromCart` events are sent.
  - **Recommended value:** Yes. Can provide insights into customer behavior and product interest.
- **InitiateCheckout Event:**

  - **What this setting does:** Tracks when a customer starts the checkout process.
  - **Effect of changing this setting:**
    - *When enabled:* An `InitiateCheckout` event is sent when the customer enters the first step of checkout.
    - *When disabled:* No `InitiateCheckout` events are sent.
  - **Recommended value:** Yes. Useful for understanding checkout funnel performance.
- **Search Event:**

  - **What this setting does:** Tracks when a customer uses your store’s internal search function.
  - **Effect of changing this setting:**
    - *When enabled:* A `Search` event is sent with the search query.
    - *When disabled:* No `Search` events are sent.
  - **Recommended value:** Yes. Provides valuable data on what customers are looking for.
- **AddToWishlist Event:**

  - **What this setting does:** Tracks when a customer adds a product to their wishlist.
  - **Effect of changing this setting:**
    - *When enabled:* An `AddToWishlist` event is sent.
    - *When disabled:* No `AddToWishlist` events are sent.
  - **Recommended value:** Yes, if your store uses a wishlist feature.
- **AddPaymentInfo Event:**

  - **What this setting does:** Tracks when a customer selects a payment method during checkout.
  - **Effect of changing this setting:**
    - *When enabled:* An `AddPaymentInfo` event is sent.
    - *When disabled:* No `AddPaymentInfo` events are sent.
  - **Recommended value:** Yes. Helps analyze payment method preferences and potential drop-offs.
- **Contact Event:**

  - **What this setting does:** Tracks when a customer visits your contact page.
  - **Effect of changing this setting:**
    - *When enabled:* A `Contact` event is sent.
    - *When disabled:* No `Contact` events are sent.
  - **Recommended value:** Yes. Useful for tracking customer service inquiries.
- **Lead Event:**

  - **What this setting does:** Tracks when a customer performs an action that indicates interest in your products or services, but isn’t a direct purchase (e.g., newsletter signup, account creation).
  - **Effect of changing this setting:**
    - *When enabled:* A `Lead` event is sent on newsletter registration and/or account creation.
    - *When disabled:* No `Lead` events are sent.
  - **Recommended value:** Yes. Important for lead generation campaigns.
- **CompleteRegistration Event:**

  - **What this setting does:** Tracks when a customer successfully creates an account on your store.
  - **Effect of changing this setting:**
    - *When enabled:* A `CompleteRegistration` event is sent.
    - *When disabled:* No `CompleteRegistration` events are sent.
  - **Recommended value:** Yes. Useful for tracking new customer acquisition.

#### Live Stats Tab

This tab provides real-time insights into the events being sent from your store to Facebook, helping you monitor your pixel’s health.

- **Keep events for (days):**

  - **What this setting does:** Determines how long the module stores event data locally for display in the Live Stats tab.
  - **Effect of changing this setting:**
    - *When set:* Event data older than this number of days will be automatically purged.
    - *When set to 0:* Events are not stored locally (and Live Stats won’t show data).
  - **Recommended value:** 7-30 days, depending on how much historical data you want to review.
  - **Merchant scenario / example:** You want to review the last week’s events. You set this to `7`.
- **Live poll interval (seconds):**

  - **What this setting does:** Controls how frequently the Live Stats tab refreshes to show new events.
  - **Effect of changing this setting:**
    - *When set:* The Live Stats table will update every X seconds.
    - *When set to 0:* Live Stats will not auto-refresh.
  - **Recommended value:** 5-10 seconds for active monitoring.
  - **Merchant scenario / example:** You are actively testing your pixel and want to see events appear almost instantly. You set this to `5`.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| General Settings | Pixel ID(s) | Your Facebook Pixel ID | Connects your store to Facebook Pixel for tracking. |
| General Settings | CAPI Access Token | Your CAPI Access Token | Enables server-side tracking for improved data accuracy. |
| General Settings | Test Event Code | Empty (use for testing only) | Sends test events to Facebook Events Manager. |
| General Settings | Consent mode | Yes (for GDPR compliance) | Fires pixel events only after customer consent. |
| General Settings | Paid statuses | Payment accepted, Delivered | Defines which order statuses trigger a “Purchase” event. |
| General Settings | Refund / cancel statuses | Canceled, Refunded | Defines which order statuses are considered non-purchase. |
| Advanced Settings | Add to cart CSS selector | Empty (auto-detect) | Helps identify the “Add to Cart” button for tracking. |
| Advanced Settings | Product price CSS selector | Empty (auto-detect) | Helps identify the product price for event values. |
| Advanced Settings | Product identification | Reference (SKU) | Determines which product ID is sent to Facebook. |
| Advanced Settings | Separator | - (hyphen) | Separator for product ID and attribute ID. |
| Advanced Settings | Product ID prefix | Empty | Adds a prefix to the product ID sent to Facebook. |
| Advanced Settings | Product ID suffix | Empty | Adds a suffix to the product ID sent to Facebook. |
| Advanced Settings | Target currency | Your primary ad currency | Converts event values to a specific currency. |
| Event Tracking | Pageview Event | Yes | Tracks all page views. |
| Event Tracking | Purchase Event | Yes | Tracks completed purchases. |
| Event Tracking | ViewContent Event | Yes | Tracks product page views. |
| Event Tracking | AddToCart Event | Yes | Tracks items added to cart. |
| Event Tracking | RemoveFromCart Event | Yes | Tracks items removed from cart. |
| Event Tracking | InitiateCheckout Event | Yes | Tracks start of checkout. |
| Event Tracking | Search Event | Yes | Tracks internal site searches. |
| Event Tracking | AddToWishlist Event | Yes (if wishlist used) | Tracks items added to wishlist. |
| Event Tracking | AddPaymentInfo Event | Yes | Tracks payment info added during checkout. |
| Event Tracking | Contact Event | Yes | Tracks visits to contact page. |
| Event Tracking | Lead Event | Yes | Tracks newsletter signups/account creations. |
| Event Tracking | CompleteRegistration Event | Yes | Tracks successful account registrations. |
| Live Stats | Keep events for (days) | 7-30 | Retention period for local event data. |
| Live Stats | Live poll interval (seconds) | 5-10 | Refresh rate for Live Stats display. |

### 2.2 Dedicated Admin Screens & Controller Views

#### AdminFbpixelAjaxController (Back Office > Modules > Fb conversion tracking pixel > Live Stats Tab)

This controller powers the “Live Stats” tab within the module’s configuration. It doesn’t have a separate menu item but is an integral part of the module’s configuration interface.

- **Screen Name & Menu Location:** Accessed via **Modules > Module Manager > Fb conversion tracking pixel > Configure**, then click on the **“Live Stats”** tab.
- **Available Actions & Settings:** This screen displays a grid or table of recent Facebook Pixel events that have been fired from your store. It shows details like the event name (e.g., `PageView`, `AddToCart`, `Purchase`), the timestamp, the associated Pixel ID, and often the parameters sent with the event (e.g., product ID, value, currency).
- **Effect of changes:** There are no direct “settings” to change on this screen. It’s a monitoring tool. The data displayed is influenced by the “Keep events for (days)” and “Live poll interval (seconds)” settings on the same configuration page.
- **Recommended workflow for daily store management:** Regularly check this tab, especially after making changes to your store or launching new products, to ensure your Facebook Pixel is firing correctly and sending accurate data. This is your first line of defense for troubleshooting pixel issues before checking Facebook Events Manager.

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My Facebook Pixel Helper Chrome extension shows no pixel or errors. What should I do?**

- **A:** First, ensure you’ve entered your “Pixel ID(s)” correctly in the module configuration.
- **A:** Check if “Consent mode” is enabled. If so, you might need to accept cookies on your storefront for the pixel to fire.
- **A:** Clear your PrestaShop cache (Advanced Parameters > Performance > Clear cache).
- **A:** If you’re using a custom theme, there might be conflicts. Temporarily switch to the default PrestaShop theme to rule this out.
- **A:** Use Facebook’s “Test Events” tool in Events Manager to see if events are being received.

**Q2: My purchase events are not showing up correctly in Facebook Events Manager.**

- **A:** Verify that your “Paid statuses” are correctly selected in the module configuration. Only orders reaching these statuses will trigger a purchase event.
- **A:** If using CAPI, ensure your “CAPI Access Token” is correct and test it using the “Test Event Code” feature.
- **A:** Check if your “Target currency” is set correctly, especially for multi-currency stores.
- **A:** Review the “Live Stats” tab in the module configuration to see if the module is internally logging purchase events.

**Q3: Dynamic Product Ads are not showing the correct products or any products at all.**

- **A:** The most common reason is a mismatch between your “Product identification” setting in the module and the IDs in your Facebook Product Catalog. Ensure they are identical (e.g., if your catalog uses SKU, set the module to “Reference”).
- **A:** Make sure your Facebook Product Catalog is up-to-date and free of errors.
- **A:** Verify that “ViewContent” and “AddToCart” events are firing correctly with the `content_ids` parameter matching your catalog IDs.

**Q4: How do I ensure GDPR or other privacy compliance with this module?**

- **A:** Enable the “Consent mode” setting in the module. This will integrate with your existing cookie consent module (if properly configured) to only fire the pixel after explicit user consent.
- **A:** Ensure your store’s privacy policy clearly states that you use Facebook Pixel for advertising and analytics, and how users can opt-out or manage their cookie preferences.

**Q5: The “Add to Cart” event isn’t firing on my product page.**

- **A:** Your theme might have a custom “Add to Cart” button that the module can’t automatically detect. Try inspecting the “Add to Cart” button on your product page using your browser’s developer tools (right-click > Inspect) to find its CSS class or ID. Then, enter this into the “Add to cart CSS selector” field in the module configuration (e.g., `.my-custom-atc-button` or `#add_to_cart_button`).

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The `Fb conversion tracking pixel` module follows a standard PrestaShop module architecture, leveraging hooks for front-office event injection and an AdminController for back-office AJAX interactions (Live Stats). It heavily relies on a factory pattern (`FbpixelTrackerFactory`) to manage different tracking mechanisms (browser-side pixel, server-side CAPI). Event data is collected and processed by dedicated classes (`FbpixelEvents`, `FbpixelPixelTracker`, `FbpixelCapiTracker`) and then dispatched. Configuration is stored in `ps_configuration`. The module also includes robust tools for debugging and health checks.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `controllers/front/ajax.php`
    - **Class Name:** `FbpixelAjaxModuleFrontController` (extends `ModuleFrontController`)
    - **Responsibility:** Handles AJAX requests from the front-office, primarily for collecting and logging real-time event data for the Live Stats feature. It might also be used for specific event triggers that cannot be handled purely client-side (e.g., `RemoveFromCart` after a cart update).
  - `controllers/front/cron.php`
    - **Class Name:** `FbpixelCronModuleFrontController` (extends `ModuleFrontController`)
    - **Responsibility:** Designed to be called by a cron job. This controller is likely responsible for processing queued CAPI events, performing data cleanup (e.g., purging old Live Stats entries), or other scheduled tasks.
  - `controllers/front/index.php`
    - **Class Name:** `FbpixelIndexModuleFrontController` (extends `ModuleFrontController`)
    - **Responsibility:** A placeholder or fallback controller, often used to prevent directory listing or provide a default response for module-specific routes.
  - `controllers/front/sync.php`
    - **Class Name:** `FbpixelSyncModuleFrontController` (extends `ModuleFrontController`)
    - **Responsibility:** Potentially handles synchronization tasks, such as pushing product catalog updates or other data to Facebook, or receiving data from Facebook.
- **Back-Office Admin Controllers**:

  - `controllers/admin/AdminFbpixelAjaxController.php`
    - **Class Name:** `AdminFbpixelAjaxController` (extends `ModuleAdminController`)
    - **Tab Name:** Not a standalone tab, but integrated into the module configuration.
    - **Managed Entity:** Manages AJAX requests from the module’s back-office configuration page, specifically for fetching and displaying the “Live Stats” event data. It provides the data for the `recent-events.tpl` template.

### 4.3 Core Classes & Models (`classes/`)

- `fbpixel/classes/autoload.php`: Handles custom class loading for the module.
- `fbpixel/classes/FbpixelCapiClient.php`:
  - **Responsibility:** Encapsulates the logic for making HTTP requests to Facebook’s Conversions API. Handles authentication, request formatting, and error handling.
- `fbpixel/classes/FbpixelCapiTracker.php`:
  - **Responsibility:** Implements the `FbpixelTrackerInterface` for server-side event tracking. Formats event data according to CAPI specifications and dispatches it via `FbpixelCapiClient`.
- `fbpixel/classes/FbpixelCatalogDoctor.php`:
  - **Responsibility:** Provides tools and logic for diagnosing issues related to product catalog matching and data consistency between PrestaShop and Facebook.
- `fbpixel/classes/FbpixelConsent.php`:
  - **Responsibility:** Manages and checks user consent status, integrating with PrestaShop’s cookie consent mechanisms (if available) to ensure GDPR compliance.
- `fbpixel/classes/FbpixelCurrencyHelper.php`:
  - **Responsibility:** Utility class for currency conversion and formatting, ensuring event values are sent in the correct target currency.
- `fbpixel/classes/FbpixelEmqCoach.php`:
  - **Responsibility:** Likely provides guidance or recommendations for improving Event Match Quality (EMQ) for Facebook events.
- `fbpixel/classes/FbpixelEventId.php`:
  - **Responsibility:** Generates and manages unique event IDs, crucial for deduplication between browser-side and server-side events.
- `fbpixel/classes/FbpixelEvents.php`:
  - **Responsibility:** A central class for defining and managing the various Facebook Pixel event types (PageView, Purchase, AddToCart, etc.) and their standard parameters.
- `fbpixel/classes/FbpixelHealthScore.php`:
  - **Responsibility:** Calculates and displays a “health score” for the pixel setup, identifying potential issues or areas for improvement.
- `fbpixel/classes/FbpixelLiveStats.php`:
  - **Database Table:** `ps_fbpixel_events` (likely, based on functionality)
  - **Extends:** Likely `ObjectModel`
  - **Responsibility:** Stores and retrieves event data locally for the “Live Stats” feature in the back office. Handles data retention and purging.
- `fbpixel/classes/FbpixelPixelRules.php`:
  - **Responsibility:** Defines rules and conditions for when specific pixel events should fire, potentially based on page type, user actions, or configuration.
- `fbpixel/classes/FbpixelPixelTracker.php`:
  - **Responsibility:** Implements the `FbpixelTrackerInterface` for browser-side event tracking. Generates the JavaScript code for `fbq()` calls and injects it into the front office.
- `fbpixel/classes/FbpixelProductIdResolver.php`:
  - **Responsibility:** Resolves the correct product ID and attribute ID based on module configuration (prefix, suffix, separator, chosen ID type) for sending to Facebook.
- `fbpixel/classes/FbpixelTrackerFactory.php`:
  - **Responsibility:** A factory class that instantiates the appropriate tracker (e.g., `FbpixelPixelTracker` for browser, `FbpixelCapiTracker` for server) based on module configuration and context.
- `fbpixel/classes/FbpixelTrackerInterface.php`:
  - **Responsibility:** Defines a common interface for all tracking classes, ensuring consistent method signatures for event dispatching.
- `fbpixel/classes/FbpixelUserData.php`:
  - **Responsibility:** Collects and formats user data (e.g., email, phone, IP address) for sending with CAPI events, crucial for Event Match Quality.
- `fbpixel/classes/index.php`: Empty file, typically used to prevent directory listing.

### 4.4 JavaScript Assets (`views/js/`)

- `fbpixel/lib/searchTool/views/js/autocomplete.js`:
  - **Scope:** Back-office.
  - **Details:** Provides autocomplete functionality for input fields, likely used in the module’s configuration for selecting products, categories, or other entities.
- `fbpixel/views/js/fbpixel-admin.js`:
  - **Scope:** Back-office.
  - **Details:** Handles general administrative logic for the module’s configuration page, including form submissions, tab switching, and potentially AJAX calls to `AdminFbpixelAjaxController`.
- `fbpixel/views/js/fbpixel-debug.js`:
  - **Scope:** Front-office (conditional).
  - **Details:** Provides debugging information in the browser console or a visual overlay, showing which pixel events are firing and their parameters. Activated by a debug mode setting.
- `fbpixel/views/js/fbpixel-ghost.js`:
  - **Scope:** Front-office.
  - **Details:** Likely a client-side script that helps detect and track events that might otherwise be missed by standard DOM observation, such as dynamic content loading or specific AJAX interactions.
- `fbpixel/views/js/fbpixel-live.js`:
  - **Scope:** Back-office.
  - **Details:** Powers the “Live Stats” tab, making AJAX requests to `AdminFbpixelAjaxController` to fetch and display real-time event data, and handling the polling interval.
- `fbpixel/views/js/fbpixel-wizard.js`:
  - **Scope:** Back-office.
  - **Details:** Manages the step-by-step setup wizard, guiding the merchant through initial configuration.
- `fbpixel/views/js/fbpixel.js`:
  - **Scope:** Front-office.
  - **Details:** The primary client-side JavaScript for the Facebook Pixel. It initializes the `fbq()` function, handles event listeners for `AddToCart`, `RemoveFromCart`, `Search`, `InitiateCheckout`, etc., and dispatches events to Facebook. It also manages the CSS selectors for dynamic elements.
- `fbpixel/views/js/mp-collect.js`:
  - **Scope:** Front-office.
  - **Details:** Likely a utility script for collecting specific data points from the front-office, possibly related to user behavior or environmental factors, to enhance event parameters.
- `fbpixel/views/js/mp-front.js`:
  - **Scope:** Front-office.
  - **Details:** General front-office JavaScript utilities or helper functions used by the module.
- `fbpixel/views/js/mp-inspect.js`:
  - **Scope:** Front-office (conditional).
  - **Details:** Provides an inspection tool, possibly a visual overlay, to help debug and verify pixel events directly on the storefront.

### 4.5 CSS Stylesheets (`views/css/`)

- `fbpixel/lib/searchTool/views/css/autocomplete.css`:
  - **Scope:** Back-office.
  - **Details:** Styles for the autocomplete dropdowns and input fields used in the admin interface.
- `fbpixel/views/css/fbpixel-admin.css`:
  - **Scope:** Back-office admin form styling.
  - **Details:** Styles the module’s configuration page, tabs, input fields, and the Live Stats table.
- `fbpixel/views/css/fbpixel-debug.css`:
  - **Scope:** Front-office (conditional).
  - **Details:** Styles for the debug overlay or console output, making debug information more readable.
- `fbpixel/views/css/mp-inspect.css`:
  - **Scope:** Front-office (conditional).
  - **Details:** Styles for the front-office inspection tool, if enabled.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - `fbpixel/views/templates/hook/capi-pageview.tpl`: Rendered in a hook (likely `displayHeader` or `actionFrontControllerSetMedia`) to trigger a server-side `PageView` event via CAPI.
  - `fbpixel/views/templates/hook/debug.tpl`: Renders the debug overlay or console output for front-office debugging.
  - `fbpixel/views/templates/hook/displayOrderConfirmation.tpl`: Renders the browser-side `Purchase` event on the order confirmation page.
  - `fbpixel/views/templates/hook/ghost.tpl`: Renders a hidden element or script for the `fbpixel-ghost.js` functionality.
  - `fbpixel/views/templates/hook/header.tpl`: Renders the base Facebook Pixel initialization code (`fbq('init', ...)` and `fbq('track', 'PageView')`) within the `<head>` section, typically via `displayHeader` or `actionFrontControllerSetMedia`.
  - `fbpixel/views/templates/hook/payment.tpl`: Potentially used to track `AddPaymentInfo` events or other payment-related interactions.
  - `fbpixel/views/templates/hook/product-details.tpl`: Renders scripts or data specific to product pages, primarily for `ViewContent` and `AddToCart` events, likely injected via `displayProductFooter` or `displayProductAdditionalInfo`.
- **Admin templates (`views/templates/admin/`)**:

  - `fbpixel/lib/searchTool/views/scripts.tpl`: Includes JavaScript for the search tool/autocomplete in the admin.
  - `fbpixel/views/templates/admin/configure.tpl`: The main template for the module’s configuration page, orchestrating all other admin templates.
  - `fbpixel/views/templates/admin/doctor.tpl`: Displays the results of the `FbpixelCatalogDoctor` for diagnosing catalog issues.
  - `fbpixel/views/templates/admin/emq.tpl`: Displays information or recommendations from `FbpixelEmqCoach` regarding Event Match Quality.
  - `fbpixel/views/templates/admin/health.tpl`: Displays the pixel’s health score from `FbpixelHealthScore`.
  - `fbpixel/views/templates/admin/live-maintain.tpl`: Template for managing live stats settings (retention, poll interval).
  - `fbpixel/views/templates/admin/live.tpl`: The container template for the “Live Stats” tab.
  - `fbpixel/views/templates/admin/mode-context.tpl`: Displays context-specific information based on the pixel’s operating mode.
  - `fbpixel/views/templates/admin/mode-note-capi.tpl`: Displays notes or warnings specific to CAPI configuration.
  - `fbpixel/views/templates/admin/mode-note-pixel.tpl`: Displays notes or warnings specific to browser-side pixel configuration.
  - `fbpixel/views/templates/admin/mode-picker.tpl`: Allows the merchant to select the pixel’s operating mode (e.g., standard, debug).
  - `fbpixel/views/templates/admin/pixels-list.tpl`: Displays a list of configured pixel IDs.
  - `fbpixel/views/templates/admin/recent-events.tpl`: Renders the table of recent events for the “Live Stats” tab, populated by `AdminFbpixelAjaxController`.
  - `fbpixel/views/templates/admin/tabs.tpl`: Renders the tab navigation for the module’s configuration page.
  - `fbpixel/views/templates/admin/wizard.tpl`: Renders the step-by-step setup wizard interface.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - `ps_configuration`: Stores all module settings (e.g., `FBPIXEL_ID`, `FBPIXEL_CAPI_TOKEN`, `FBPIXEL_PAID_STATUSES`).
  - `ps_fbpixel_events` (likely): A custom table created by the module to store local event logs for the “Live Stats” feature. Columns would typically include `id_fbpixel_event`, `pixel_id`, `event_name`, `event_data` (JSON), `timestamp`, `ip_address`, `user_agent`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionFrontControllerSetMedia` | Before front controller renders, for adding JS/CSS. | Injects core Facebook Pixel JS, event tracking scripts, and CAPI PageView. |
| `displayContactContent` | On the contact page. | Triggers `Contact` event. |
| `displayOrderConfirmation` | On the order confirmation page. | Triggers browser-side `Purchase` event. |
| `actionNewsletterRegistrationAfter` | After a newsletter signup. | Triggers `Lead` event (and potentially `CompleteRegistration` if combined). |
| `displayProductFooter` | At the bottom of product pages. | Injects product-specific data and `ViewContent` event. |
| `displayHeader` | In the `<head>` section of all front-office pages. | Injects base Facebook Pixel code and `PageView` event. |
| `DisplayProductButtons` | Near product action buttons (e.g., Add to Cart). | May inject JS for `AddToCart` event listener. |
| `ActionObjectProductInCartDeleteBefore` | Before a product is removed from cart. | Potentially triggers `RemoveFromCart` event. |
| `DisplayProductAdditionalInfo` | In the product information block. | Additional product data injection or event triggers. |
| `ActionCronJob` | During a scheduled cron execution. | Triggers CAPI event processing, data cleanup. |
| `ActionObjectProductInCartDeleteAfter` | After a product is removed from cart. | Triggers `RemoveFromCart` event. |
| `ActionValidateOrder` | After an order is successfully validated. | Triggers server-side `Purchase` event via CAPI. |
| `DisplayLeftColumnProduct` | In the left column of product pages. | Less common for pixel, possibly for specific product-related events. |
| `displayExtraLeft` | In the extra left column. | Less common for pixel, possibly for specific product-related events. |
| `ActionCartUpdateQuantityBefore` | Before cart quantity is updated. | Potentially used to track changes that might lead to `RemoveFromCart`. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please log in to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist you with any issues or questions regarding the “Fb conversion tracking pixel” module.
