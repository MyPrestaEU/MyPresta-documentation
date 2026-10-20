---
title: "Presta Speed Cache - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Presta Speed Cache PrestaShop module by MyPresta.eu."
sidebar:
  label: "Presta Speed Cache - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Presta Speed Cache Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/presta-speed-cache.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/presta-speed-cache/)
>
> ---


# Presta Speed Cache

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5 (The module is designed to work across this range, ensuring broad compatibility while supporting the latest stable PHP versions.)
- **Hosting Requirements**: Standard PHP extensions like cURL, JSON, and OpenSSL are required, which are typically available on most modern hosting environments. For advanced caching methods like Redis or Memcached, these services must be installed and configured on your server.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration area for Presta Speed Cache. You’ll find various settings to fine-tune how your store’s cache operates.

#### General Settings Tab

- **Enable Cache:**

  - **What this setting does:** This is the master switch for the module. It turns the caching functionality on or off for your entire store.
  - **Effect of changing this setting:**
    - *When enabled:* The module will start caching pages and serving them quickly. Your store’s performance will significantly improve.
    - *When disabled:* The module will stop caching, and your store will revert to its default PrestaShop speed, which is typically slower.
  - **Recommended value:** **YES**. This is the core function of the module.
  - **Merchant scenario / example:** You’ve just installed the module and want to activate the speed benefits. Set this to YES. If you’re troubleshooting another module and suspect caching might be interfering, you might temporarily disable it.
- **Cache Lifetime (minutes):**

  - **What this setting does:** Determines how long a cached page remains valid before the module considers it “stale” and rebuilds it.
  - **Effect of changing this setting:**
    - *Higher value (e.g., 1440 for 24 hours):* Pages are served from cache for longer, reducing server load but potentially showing slightly outdated content if you make frequent changes (e.g., price updates).
    - *Lower value (e.g., 60 for 1 hour):* Pages are rebuilt more often, ensuring fresher content but slightly increasing server load.
  - **Recommended value:** Start with **1440** (24 hours). Adjust based on how frequently your product data changes.
  - **Merchant scenario / example:** If you update product prices or descriptions daily, a 24-hour lifetime is fine. If you run flash sales with hourly price changes, you might reduce this to 60 or 120 minutes, or rely on the automatic invalidation features.
- **Cache Storage Method:**

  - **What this setting does:** Selects where the cached pages are stored. Different methods offer varying levels of performance and require specific server setups.
  - **Effect of changing this setting:**
    - *File System (default):* Caches pages as files on your server’s disk. Easiest to set up, good for most stores.
    - *Redis:* Stores cache in memory using the Redis server. Much faster than file system, ideal for high-traffic stores. Requires Redis to be installed and configured on your server.
    - *Memcached:* Stores cache in memory using the Memcached server. Similar to Redis in performance benefits, also requires server setup.
  - **Recommended value:** Start with **File System**. If you have a high-traffic store and your hosting supports it, consider **Redis** or **Memcached** for maximum performance.
  - **Merchant scenario / example:** Your store is growing rapidly, and you’re experiencing occasional slowdowns. Your host offers Redis. Switching to Redis can dramatically improve performance.
- **Exclude URLs from Cache:**

  - **What this setting does:** Allows you to specify certain pages or sections of your store that should *never* be cached. This is useful for pages with highly dynamic or sensitive content.
  - **Effect of changing this setting:**
    - *Adding URLs:* Those pages will always be generated fresh by PrestaShop, ensuring their content is always up-to-the-minute but sacrificing speed for those specific pages.
    - *Leaving empty:* All eligible pages will be cached.
  - **Recommended value:** Leave empty unless you have specific needs. Use with caution.
  - **Merchant scenario / example:** You have a custom “Quote Request” page that generates unique forms based on user input, or a page with real-time stock updates from an external API. You would add `/module/yourmodule/quotepage` or `/stock-updates` to this list.
- **Warm-up Cache:**

  - **What this setting does:** Automatically “visits” your store’s pages in the background to pre-fill the cache, ensuring that even the first visitor to a page experiences the speed benefits.
  - **Effect of changing this setting:**
    - *When enabled:* Your cache will be populated proactively, leading to faster load times for all visitors, even those visiting a page for the first time after cache invalidation. This can slightly increase server load during the warm-up process.
    - *When disabled:* Pages will only be cached after the first customer visit.
  - **Recommended value:** **YES**. This ensures maximum speed benefits for all users.
  - **Merchant scenario / example:** You’ve just cleared your cache or updated many products. Enabling warm-up will ensure your store is fast for customers immediately, rather than waiting for them to visit each page first.
- **HTML Optimization:**

  - **What this setting does:** Minifies the HTML output of your pages by removing unnecessary spaces, comments, and line breaks. This makes the page file size smaller, leading to faster downloads.
  - **Effect of changing this setting:**
    - *When enabled:* Your page’s HTML code will be more compact, reducing bandwidth usage and slightly speeding up page rendering. This is generally safe.
    - *When disabled:* HTML will be served as generated by PrestaShop, without minification.
  - **Recommended value:** **YES**. It’s a simple, safe performance boost.
  - **Merchant scenario / example:** You want to squeeze every bit of performance out of your store. Enabling this will make your HTML leaner.

#### Dynamic Blocks Tab

This section allows you to define parts of your page that should *not* be cached, but instead loaded dynamically after the main page has loaded. This is crucial for personalized content like the shopping cart, login status, or specific module outputs.

- **Enable Dynamic Blocks:**

  - **What this setting does:** Activates the ability to define specific areas of your page that will be loaded separately and dynamically, even when the rest of the page is served from cache.
  - **Effect of changing this setting:**
    - *When enabled:* You can configure specific modules or content areas to remain dynamic, ensuring personalized content is always fresh.
    - *When disabled:* All content will be cached, potentially leading to stale dynamic content (e.g., an empty cart displayed even if items were added).
  - **Recommended value:** **YES**. This is essential for a functional cached store.
  - **Merchant scenario / example:** You want your customer’s cart to always show the correct number of items, even if the product page itself is cached.
- **Dynamic Modules List:**

  - **What this setting does:** This is a list where you select which modules should *always* be rendered dynamically, even if they are hooked into a cached page.
  - **Effect of changing this setting:**
    - *Adding a module:* That module’s output will be fetched fresh for every user, ensuring its content is always up-to-date (e.g., cart block, user info block).
    - *Removing a module:* The module’s output will be cached along with the rest of the page, potentially showing stale data.
  - **Recommended value:** Include modules like `ps_shoppingcart`, `ps_customeraccountlinks`, `ps_languageselector`, `ps_currencyselector`, and any other module that displays user-specific or real-time information.
  - **Merchant scenario / example:** You install a new “Live Chat” module that needs to display real-time availability. You would add it to this list to ensure it’s always dynamic.

#### Invalidation & Purge Tab

This section manages how and when the cache is cleared or updated, ensuring your customers always see the latest product information.

- **Automatic Cache Invalidation:**

  - **What this setting does:** When enabled, the module automatically clears relevant cached pages whenever you make changes in your PrestaShop back office (e.g., updating a product, category, or CMS page).
  - **Effect of changing this setting:**
    - *When enabled:* You don’t have to manually clear the cache after every change. The module intelligently clears only the affected pages, ensuring customers see updates quickly.
    - *When disabled:* You would need to manually clear the entire cache after every significant change, or customers might see outdated content until the cache lifetime expires.
  - **Recommended value:** **YES**. This is a crucial “set it and forget it” feature for data freshness.
  - **Merchant scenario / example:** You update the price of a product. With automatic invalidation, the cached version of that product page (and potentially its category pages) is cleared, so customers immediately see the new price.
- **Purge Cache on Product Update:**

  - **What this setting does:** Specifically controls whether the cache related to a product is cleared when that product is updated.
  - **Effect of changing this setting:**
    - *When enabled:* Ensures that any page displaying the updated product (product page, category page, search results) is refreshed in the cache.
    - *When disabled:* Product updates might not reflect on cached pages until the cache lifetime expires or you manually clear it.
  - **Recommended value:** **YES**. Essential for accurate product information.
  - **Merchant scenario / example:** You change a product’s image. This setting ensures the new image appears on the product page immediately.
- **Purge Cache on Category Update:**

  - **What this setting does:** Controls whether the cache related to a category is cleared when that category is updated.
  - **Effect of changing this setting:**
    - *When enabled:* Ensures that category pages and potentially product pages within that category are refreshed.
    - *When disabled:* Category updates (e.g., name, description, products assigned) might not reflect on cached pages.
  - **Recommended value:** **YES**. Important for navigation and category content accuracy.
  - **Merchant scenario / example:** You rename a category. This ensures the new name appears in your navigation and on the category page.
- **Purge Cache on CMS Page Update:**

  - **What this setting does:** Controls whether the cache related to a CMS page is cleared when that page is updated.
  - **Effect of changing this setting:**
    - *When enabled:* Ensures that updated CMS pages (e.g., “About Us,” “Terms and Conditions”) are immediately refreshed.
    - *When disabled:* Updates to CMS pages might not be visible to customers until the cache expires.
  - **Recommended value:** **YES**. Important for static content accuracy.
  - **Merchant scenario / example:** You update your “Shipping Policy” page. This ensures customers see the latest version.

#### Advanced Settings Tab

- **Enable Debug Mode:**

  - **What this setting does:** Activates a special mode that displays information about the cache status directly on your front-office pages (visible only to you as an administrator).
  - **Effect of changing this setting:**
    - *When enabled:* You’ll see a small overlay on your store pages indicating if the page was served from cache, when it was cached, and other diagnostic details. This is invaluable for troubleshooting.
    - *When disabled:* No debug information is shown.
  - **Recommended value:** **NO** for live production stores. **YES** when setting up or troubleshooting.
  - **Merchant scenario / example:** You’ve just configured the module and want to verify that pages are indeed being cached correctly. Enable debug mode, browse your store, and check the overlay.
- **Enable Live Debug:**

  - **What this setting does:** Provides a real-time dashboard in the back office to monitor cache hits, misses, and other performance metrics.
  - **Effect of changing this setting:**
    - *When enabled:* You gain access to a powerful monitoring tool to see how effectively your cache is working.
    - *When disabled:* No live cache statistics are collected or displayed.
  - **Recommended value:** **YES** if you want to actively monitor performance. Can be disabled if you prefer minimal overhead.
  - **Merchant scenario / example:** You want to see the impact of your caching strategy over time, observing how many requests are served from cache versus being generated fresh.
- **Enable SWR (Stale-While-Revalidate):**

  - **What this setting does:** An advanced caching strategy where, if a cached page is expired, the module immediately serves the *stale* (expired) version to the user while simultaneously rebuilding a fresh version in the background.
  - **Effect of changing this setting:**
    - *When enabled:* Users almost always get an instant page load, even if the cache is expired. The page might be slightly outdated for a moment, but it’s incredibly fast. The fresh version replaces the stale one for subsequent visitors.
    - *When disabled:* When a cached page expires, the next visitor will wait for the page to be rebuilt, which can cause a slight delay.
  - **Recommended value:** **YES**. This offers the best balance of speed and freshness for most stores.
  - **Merchant scenario / example:** You want to ensure your customers never experience a slow load, even if the cache needs to be updated. SWR provides this “always fast” experience.
- **Cache for Logged-in Users:**

  - **What this setting does:** Determines whether pages should be cached even for customers who are logged into their accounts.
  - **Effect of changing this setting:**
    - *When enabled:* Logged-in users will also benefit from cached pages, but the module must be very intelligent about dynamic blocks to ensure personalized content (like “My Account” links, order history) remains correct.
    - *When disabled:* Logged-in users will always receive fresh, uncached pages. This ensures perfect personalization but sacrifices speed for these users.
  - **Recommended value:** **YES**, but ensure your dynamic blocks are correctly configured for modules like `ps_customeraccountlinks`.
  - **Merchant scenario / example:** You want your returning, logged-in customers to also enjoy a super-fast experience, not just guests.
- **Cache for Mobile Devices:**

  - **What this setting does:** Controls whether separate cached versions of pages are generated and served for mobile devices.
  - **Effect of changing this setting:**
    - *When enabled:* The module will create and serve optimized cached pages specifically for mobile users, which is crucial if your theme has significant differences between desktop and mobile layouts.
    - *When disabled:* Mobile users will either receive the desktop cached version (if applicable) or uncached pages, potentially leading to slower or incorrectly rendered content.
  - **Recommended value:** **YES** if your theme is responsive and renders differently for mobile.
  - **Merchant scenario / example:** Your theme uses different templates or CSS for mobile. Caching for mobile ensures they get the correct, fast version.
- **Enable Edge Purge (Varnish/CDN):**

  - **What this setting does:** Integrates with external caching systems like Varnish or Content Delivery Networks (CDNs) to send purge requests when your PrestaShop cache is invalidated. This ensures that the CDN also clears its old content.
  - **Effect of changing this setting:**
    - *When enabled:* Your CDN will always serve the freshest content after you make updates, preventing customers from seeing old versions stored by the CDN.
    - *When disabled:* Your CDN might continue serving old content even after your PrestaShop cache is cleared, leading to inconsistencies.
  - **Recommended value:** **YES** if you are using Varnish or a CDN (like Cloudflare, Akamai, etc.) that supports cache purging via API.
  - **Merchant scenario / example:** You use Cloudflare for performance. When you update a product, this setting tells Cloudflare to clear its cache for that product, so all users see the update immediately.

#### Tools Tab

This tab provides manual actions for managing your cache.

- **Clear All Cache:**

  - **What this setting does:** This button immediately deletes all cached pages generated by Presta Speed Cache.
  - **Effect of changing this setting:** All cached content is removed. The next time a page is visited, it will be generated fresh by PrestaShop and then re-cached. This will temporarily slow down your site until the cache rebuilds.
  - **Recommended value:** Use only when necessary (e.g., after a major theme update, module installation, or if you suspect cache issues).
  - **Merchant scenario / example:** You’ve made extensive changes to your theme’s CSS and want to ensure all visitors see the new design immediately. Click “Clear All Cache.”
- **Run Cache Warm-up:**

  - **What this setting does:** Manually triggers the cache warm-up process, which visits your store’s pages to pre-populate the cache.
  - **Effect of changing this setting:** The module will start generating cached versions of your pages in the background. This can take some time depending on your store size and may consume server resources during the process.
  - **Recommended value:** Use after clearing the cache or after major product/category imports to quickly rebuild the cache.
  - **Merchant scenario / example:** You’ve just cleared the cache and want your store to be fast for customers as quickly as possible.

### 2.2 Dedicated Admin Screens & Controller Views

#### 2.2.1 Cache Management (Back Office > Presta Speed Cache > Cache Management)

This screen provides a detailed overview and management interface for your cached pages.

- **Screen Name & Menu Location:** You can find this by navigating to **Presta Speed Cache** in your main PrestaShop back office menu, then selecting **Cache Management**.
- **Available Actions & Settings:**
  - **Cache List Grid:** This table displays a list of currently cached pages, including details like the URL, when it was last cached, its size, and its current status (e.g., active, expired).
  - **Filter and Search:** You can filter the list by URL, status, or other criteria to find specific cached entries.
  - **Clear Selected Cache:** Allows you to select specific cached pages from the list and clear them individually.
  - **Clear All Cache (button):** A prominent button to clear the entire cache, similar to the one on the main configuration page.
  - **Run Warm-up (button):** A prominent button to manually initiate the cache warm-up process.
- **Effect of changes:**
  - *Clearing individual entries:* Only the selected pages will be removed from the cache, allowing them to be rebuilt on the next visit. This is useful for targeted updates without affecting the entire store.
  - *Clearing all cache:* Resets the entire cache, forcing all pages to be rebuilt.
  - *Running warm-up:* Proactively fills the cache, ensuring faster loading for subsequent visitors.
- **Recommended workflow for daily store management:** Use this screen to monitor your cache, identify any pages that might not be caching correctly, or to perform targeted cache purges if you’ve made a very specific update that automatic invalidation might have missed.

#### 2.2.2 Dashboard (Back Office > Presta Speed Cache > Dashboard)

This screen provides a visual overview of your cache performance and statistics.

- **Screen Name & Menu Location:** You can find this by navigating to **Presta Speed Cache** in your main PrestaShop back office menu, then selecting **Dashboard**.
- **Available Actions & Settings:**
  - **Performance Metrics:** Displays graphs and statistics on cache hits, cache misses, average page load times (with and without cache), and other relevant performance indicators.
  - **Cache Health Status:** Provides a quick overview of the cache system’s health, indicating if there are any issues or if it’s operating optimally.
  - **Recent Invalidation Events:** Shows a log of recent cache invalidations, helping you track when and why parts of your cache were cleared.
- **Effect of changes:** This screen is primarily for monitoring and reporting. No direct changes to the cache configuration are made here, but it helps you understand the impact of your settings.
- **Recommended workflow for daily store management:** Regularly check the dashboard to ensure your cache is performing as expected. Look for high cache hit rates and low load times. If you see a sudden drop in cache hits or an increase in load times, it might indicate a configuration issue or a problem with your server.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Enable Cache | YES | Master switch for caching. YES = faster store. |
|  | Cache Lifetime (minutes) | 1440 (24 hours) | How long a page stays cached. Higher = less server load, potentially older content. |
|  | Cache Storage Method | File System | Where cache is stored. File System (easy), Redis/Memcached (faster, requires server setup). |
|  | Exclude URLs from Cache | Empty | URLs that should never be cached (e.g., highly dynamic pages). |
|  | Warm-up Cache | YES | Proactively builds cache in background. YES = faster for first visitors. |
|  | HTML Optimization | YES | Minifies HTML for smaller page sizes. YES = slight speed boost. |
|  | Enable Dynamic Blocks | YES | Allows specific content (cart, login) to remain dynamic. YES = essential for personalized content. |
|  | Dynamic Modules List | `ps_shoppingcart`, `ps_customeraccountlinks`, etc. | Modules that should always be dynamic. |
|  | Automatic Cache Invalidation | YES | Clears relevant cache on back office changes. YES = fresh content without manual intervention. |
|  | Purge Cache on Product Update | YES | Clears product-related cache when products are updated. |
|  | Purge Cache on Category Update | YES | Clears category-related cache when categories are updated. |
|  | Purge Cache on CMS Page Update | YES | Clears CMS page-related cache when CMS pages are updated. |
|  | Enable Debug Mode | NO (YES for troubleshooting) | Shows cache info on front office. |
|  | Enable Live Debug | YES | Provides real-time cache statistics in BO. |
|  | Enable SWR (Stale-While-Revalidate) | YES | Serves stale cache while rebuilding fresh. YES = always fast. |
|  | Cache for Logged-in Users | YES | Caches pages for logged-in users. |
|  | Cache for Mobile Devices | YES | Caches separate versions for mobile. |
|  | Enable Edge Purge (Varnish/CDN) | NO (YES if using CDN) | Integrates with external CDN/Varnish for cache purging. |
|  | Clear All Cache (button) | Use when needed | Manually clears entire cache. |
|  | Run Cache Warm-up (button) | Use when needed | Manually triggers cache pre-population. |
| **Cache Management Screen** | Cache List Grid | N/A | Displays and allows management of individual cached pages. |
|  | Clear Selected Cache | N/A | Clears specific cached entries. |
| **Dashboard Screen** | Performance Metrics | N/A | Visualizes cache hits, misses, and load times. |
|  | Cache Health Status | N/A | Shows overall health of the caching system. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My store looks broken or shows old content after enabling the cache. What should I do?**
A: First, try clearing your entire cache using the “Clear All Cache” button in the module’s configuration or the “Cache Management” screen. Also, clear your browser’s cache. If the issue persists, check your “Dynamic Modules List” to ensure all modules displaying personalized or real-time content are included. Temporarily disable “HTML Optimization” to see if it’s causing conflicts.

**Q: My shopping cart isn’t updating correctly, or users appear logged out sometimes.**
A: This is almost always due to dynamic content not being properly excluded from caching. Go to the “Dynamic Blocks” tab and ensure modules like `ps_shoppingcart`, `ps_customeraccountlinks`, `ps_languageselector`, and `ps_currencyselector` are added to the “Dynamic Modules List.” If you have other custom modules that display user-specific data, add them too.

**Q: My website is still slow, even with the module enabled.**
A:

1. **Check Debug Mode:** Enable “Debug Mode” (in Advanced Settings) and browse your front office. Does it show that pages are being served from cache (“Cache HIT”)? If you see “Cache MISS,” the pages aren’t being cached.
2. **Verify Cache Hit Rate:** Check the “Dashboard” for your cache hit rate. If it’s low, review your “Cache Lifetime” and “Exclude URLs” settings.
3. **Server Resources:** While caching reduces load, your server still needs adequate resources. Check your hosting plan and server logs for other bottlenecks.
4. **Other Optimizations:** Caching is one part of speed. Ensure your images are optimized, your theme is efficient, and you’re not running too many heavy, unoptimized modules.

**Q: How do I make sure my multi-language or multi-currency store works correctly with caching?**
A: Presta Speed Cache is designed to handle multi-language and multi-currency stores by generating separate cache entries for each combination. Ensure your language and currency selector modules are added to the “Dynamic Modules List.” If you notice issues, enable “Cache for Logged-in Users” and “Cache for Mobile Devices” if applicable, as these can also affect how different versions of pages are cached.

**Q: I’ve updated a product, but the old information is still showing on the front office.**
A:

1. **Automatic Invalidation:** Ensure “Automatic Cache Invalidation” and “Purge Cache on Product Update” are enabled in the “Invalidation & Purge” tab.
2. **Manual Clear:** If the settings are correct, try manually clearing the cache for that specific product page from the “Cache Management” screen, or clear the entire cache.
3. **CDN/Varnish:** If you use a CDN or Varnish, ensure “Enable Edge Purge” is configured correctly, as your CDN might be serving an old version.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

Presta Speed Cache is a highly optimized caching solution for PrestaShop, employing a sophisticated architecture to deliver speed without compromising dynamic content. It leverages PrestaShop’s MVC pattern by overriding core classes (`Controller`, `FrontController`, `Dispatcher`, `Hook`) to intercept requests and responses, serving cached HTML when available. It uses a flexible storage engine (File, Redis, Memcached) and implements advanced features like SWR (Stale-While-Revalidate), dynamic block rendering via AJAX, and intelligent cache invalidation. The module’s design focuses on minimal overhead and maximum compatibility, providing a robust and extensible caching layer.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

These controllers handle specific AJAX requests or background tasks related to caching.

- `prestaspeedcache/controllers/front/api.php`
  - **Class name & parent class:** `PrestaSpeedCacheApiModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** Handles API requests, primarily for dynamic content fetching. When a cached page is served, and it contains dynamic blocks, this controller is responsible for delivering the fresh HTML for those blocks via AJAX. It receives parameters identifying the module and hook, renders the module, and returns the HTML.
- `prestaspeedcache/controllers/front/cron.php`
  - **Class name & parent class:** `PrestaSpeedCacheCronModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** Designed to be called by a server-side cron job. It triggers background tasks such as cache warm-up, processing of the invalidation queue, and other maintenance operations. This offloads heavy processing from user requests.
- `prestaspeedcache/controllers/front/dynamic.php`
  - **Class name & parent class:** `PrestaSpeedCacheDynamicModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** Similar to `api.php`, this controller specifically handles requests for dynamic content blocks that are loaded asynchronously into cached pages. It ensures that personalized elements like the cart or user info are always up-to-date.
- `prestaspeedcache/controllers/front/index.php`
  - **Class name & parent class:** `PrestaSpeedCacheIndexModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** A placeholder or fallback front controller. In many modules, `index.php` in `controllers/front` serves as a default entry point if no other specific controller is matched. It might handle basic module-level routing or simply redirect.

#### Back-Office Admin Controllers

These controllers manage the module’s configuration and data within the PrestaShop Back Office.

- `prestaspeedcache/controllers/admin/AdminPrestaSpeedCacheController.php`
  - **Class name & parent class:** `AdminPrestaSpeedCacheController` extends `ModuleAdminController`.
  - **Tab name and managed entity:** This is the primary administrative controller for the module, managing the cache entries and providing the “Cache Management” and “Dashboard” views. It handles listing, filtering, and deleting cache entries. It does not manage a specific `ObjectModel` entity directly but rather interacts with the `PscCacheRepository` for cache operations.
- `prestaspeedcache/controllers/admin/index.php`
  - **Class name & parent class:** `AdminPrestaSpeedCacheIndexController` extends `ModuleAdminController`.
  - **Tab name and managed entity:** Similar to the front-office `index.php`, this is likely a placeholder or default controller for the module’s admin section, ensuring a valid entry point if no specific action is requested.

### 4.3 Core Classes & Models (`classes/`)

The module’s `classes/` directory contains the core logic, services, and data structures.

- `prestaspeedcache/classes/PscAdminChips.php`: Manages UI components for admin interface.
- `prestaspeedcache/classes/PscAfterDefaults.php`: Handles default settings or post-installation configurations.
- `prestaspeedcache/classes/PscAutoload.php`: Custom autoloader for module classes.
- `prestaspeedcache/classes/PscCacheEngine.php`: The main caching engine, orchestrating cache operations.
- `prestaspeedcache/classes/PscCacheInvalidator.php`: Manages the logic for invalidating cached pages based on back office actions.
- `prestaspeedcache/classes/PscCacheKey.php`: Generates unique keys for cached entries based on URL, context, etc.
- `prestaspeedcache/classes/PscCacheLock.php`: Implements locking mechanisms to prevent race conditions during cache generation.
- `prestaspeedcache/classes/PscCacheRepository.php`: Manages interaction with the cache storage, providing an abstraction layer.
- `prestaspeedcache/classes/PscCacheStorage.php`: Abstract base class or interface for cache storage implementations.
- `prestaspeedcache/classes/PscCacheTags.php`: Manages cache tags for granular invalidation (e.g., all pages related to product ID 123).
- `prestaspeedcache/classes/PscConfig.php`: Handles module configuration settings (reads and writes to `ps_configuration`).
- `prestaspeedcache/classes/PscDynamicBlocks.php`: Logic for identifying and handling dynamic content blocks.
- `prestaspeedcache/classes/PscDynamicModules.php`: Manages the list of modules whose output should always be dynamic.
- `prestaspeedcache/classes/PscEdgePurge.php`: Handles integration with external caching systems (Varnish, CDN) for purging.
- `prestaspeedcache/classes/PscFrontAssign.php`: Manages Smarty variable assignments for front-office templates.
- `prestaspeedcache/classes/PscFrontDebug.php`: Logic for displaying debug information on the front office.
- `prestaspeedcache/classes/PscHealth.php`: Provides methods for checking the health and status of the caching system.
- `prestaspeedcache/classes/PscHtmlOptimizer.php`: Implements HTML minification logic.
- `prestaspeedcache/classes/PscHttpProbe.php`: Used for internal HTTP requests, e.g., for cache warm-up.
- `prestaspeedcache/classes/PscInstaller.php`: Handles module installation and uninstallation routines (database tables, hooks, configuration defaults).
- `prestaspeedcache/classes/PscInvalidationQueue.php`: Manages a queue of pages to be invalidated, often processed by cron.
- `prestaspeedcache/classes/PscLiveDebug.php`: Provides real-time debugging and monitoring capabilities.
- `prestaspeedcache/classes/PscMetrics.php`: Collects and reports performance metrics for the dashboard.
- `prestaspeedcache/classes/PscOps.php`: General operational utility methods.
- `prestaspeedcache/classes/PscPresets.php`: Manages predefined caching configurations or presets.
- `prestaspeedcache/classes/PscRequestGuard.php`: Protects against malicious requests or ensures proper request handling.
- `prestaspeedcache/classes/PscTiming.php`: Utility for measuring execution times.
- `prestaspeedcache/classes/PscTranslate.php`: Handles module translations.
- `prestaspeedcache/classes/PscWarmup.php`: Implements the cache warm-up logic.
- `prestaspeedcache/classes/PscWizard.php`: Guides users through initial setup.
- `prestaspeedcache/classes/storage/PscFileStorage.php`: Concrete implementation for file-based cache storage.
- `prestaspeedcache/classes/storage/PscMemcachedStorage.php`: Concrete implementation for Memcached cache storage.
- `prestaspeedcache/classes/storage/PscRedisStorage.php`: Concrete implementation for Redis cache storage.
- `prestaspeedcache/classes/storage/PscStorageFactory.php`: Factory pattern for creating appropriate cache storage instances.
- `prestaspeedcache/classes/storage/PscStorageInterface.php`: Interface defining methods for cache storage implementations.

#### Overrides

The module uses overrides to deeply integrate with PrestaShop’s core behavior.

- `prestaspeedcache/override/classes/controller/Controller.php`: Overrides the base `Controller` class, allowing the module to intercept the rendering process for both front and back office, potentially injecting caching logic or dynamic block markers.
- `prestaspeedcache/override/classes/controller/FrontController.php`: Overrides `FrontController` to specifically handle front-office page requests, enabling the module to serve cached content or prepare pages for caching.
- `prestaspeedcache/override/classes/Dispatcher.php`: Overrides the `Dispatcher` to control how URLs are routed and processed, potentially redirecting to cached content or triggering cache generation.
- `prestaspeedcache/override/classes/Hook.php`: Overrides the `Hook` class to allow for dynamic module rendering within cached pages, ensuring that specific hooks are always executed fresh.

### 4.4 JavaScript Assets (`views/js/`)

These scripts enhance the user experience in both the front and back office.

- `prestaspeedcache/views/js/admin.js`:
  - **Scope:** Back-office.
  - **Details:** Handles interactive elements in the module’s admin configuration, such as tab switching, form submissions, AJAX calls for clearing cache, running warm-up, and dynamic updates to the dashboard or cache list.
- `prestaspeedcache/views/js/after/lang-currency.js`:
  - **Scope:** Front-office.
  - **Details:** Likely a small script executed after the main page load, specifically designed to ensure language and currency selectors (which are often dynamic) function correctly within a cached page context. It might re-initialize their behavior or ensure their state is consistent.
- `prestaspeedcache/views/js/dynamic.js`:
  - **Scope:** Front-office.
  - **Details:** This is a critical script for dynamic blocks. It identifies placeholders for dynamic content within a cached page, makes AJAX requests (to `api.php` or `dynamic.php` controllers) to fetch the fresh HTML for those blocks, and then injects the content back into the DOM. It ensures elements like the cart, login status, etc., are always up-to-date.
- `prestaspeedcache/views/js/fo_debug.js`:
  - **Scope:** Front-office (admin-only when debug mode is enabled).
  - **Details:** Displays the cache debug overlay on the front office. It fetches cache status information (hit/miss, timestamp, etc.) and renders it in a visible, non-intrusive element for administrators.
- `prestaspeedcache/views/js/psc-dom-mock.js`:
  - **Scope:** Front-office.
  - **Details:** Potentially a utility script that provides a lightweight DOM manipulation or mocking layer, possibly used during the dynamic block injection process to ensure compatibility or optimize rendering.

### 4.5 CSS Stylesheets (`views/css/`)

- `prestaspeedcache/views/css/admin.css`:
  - **Scope:** Back-office admin form styling.
  - **Details:** Styles the module’s configuration pages, dashboard, and cache management grids. It ensures a consistent and user-friendly interface within the PrestaShop back office.
  - **Key CSS class selectors:** `prestaspeedcache-dashboard`, `prestaspeedcache-config-form`, `prestaspeedcache-table`, `psc-debug-overlay`.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Admin templates (`views/templates/admin/`)

These templates are used for the module’s back-office interface.

- `prestaspeedcache/views/templates/admin/cache_list.tpl`: Renders the table and interface for listing and managing cached pages.
- `prestaspeedcache/views/templates/admin/configure.tpl`: The main configuration form for the module, containing all the settings described in Section 4.1.
- `prestaspeedcache/views/templates/admin/dashboard.tpl`: Displays the performance metrics, graphs, and cache health status.
- `prestaspeedcache/views/templates/admin/dynamic_modules.tpl`: The interface for selecting and managing modules that should be rendered dynamically.
- `prestaspeedcache/views/templates/admin/live_debug.tpl`: Renders the real-time debug information panel in the back office.
- `prestaspeedcache/views/templates/admin/ops.tpl`: Likely contains templates for operational tools or actions (e.g., manual cache clear, warm-up).
- `prestaspeedcache/views/templates/admin/tabs.tpl`: Renders the tab navigation structure for the module’s configuration pages.
- `prestaspeedcache/views/templates/admin/wizard.tpl`: Template for the initial setup wizard, guiding users through basic configuration.

### 4.7 Database Schema & Hooks Map

#### Database Tables

The module primarily uses PrestaShop’s `ps_configuration` table for its settings. For cache storage, it either uses the file system or external services (Redis/Memcached). It may create custom tables for:

- `ps_prestaspeedcache_cache_tags`: Stores relationships between cached pages and their associated tags (e.g., product IDs, category IDs) for efficient invalidation.
- `ps_prestaspeedcache_invalidation_queue`: Stores a list of pages or tags that need to be invalidated, processed asynchronously.
- `ps_prestaspeedcache_metrics`: Stores performance metrics for the dashboard.

#### Registered Hooks Table

The module registers various hooks to integrate with PrestaShop’s lifecycle.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Before page content is rendered in the header. | Injecting front-office JavaScript (e.g., `dynamic.js`, `fo_debug.js`), setting up initial cache context. |
| `displayFooter` | Before the closing `</body>` tag. | Injecting additional scripts, debug information, or finalizing cache operations. |
| `displayLeftColumn` | In the left column of the theme. | Potentially used for dynamic module rendering if a module in the left column is marked as dynamic. |
| `displayRightColumn` | In the right column of the theme. | Potentially used for dynamic module rendering if a module in the right column is marked as dynamic. |
| `displayProductAdditionalInfo` | On the product page, below product description. | If a module hooked here is dynamic, its content will be fetched separately. |
| `actionFrontControllerSetMedia` | After media (JS/CSS) has been set by the front controller. | Adding module-specific JS/CSS to the page. |
| `actionFrontControllerInit` | At the beginning of a front controller’s execution. | Intercepting requests to check for cached content or prepare for caching. |
| `actionDispatcherBefore` | Before the dispatcher processes the request. | Early interception to serve cached content or bypass dispatching. |
| `actionDispatcherAfter` | After the dispatcher has processed the request. | Finalizing cache generation for the current page. |
| `actionObjectUpdate` | When any `ObjectModel` is updated (e.g., Product, Category, CMS). | Triggering cache invalidation for affected pages. |
| `actionObjectAdd` | When any `ObjectModel` is added. | Triggering cache invalidation for potentially affected pages. |
| `actionObjectDelete` | When any `ObjectModel` is deleted. | Triggering cache invalidation for affected pages. |
| `actionProductUpdate` | Specific to product updates. | Granular cache invalidation for product pages. |
| `actionCategoryUpdate` | Specific to category updates. | Granular cache invalidation for category pages. |
| `actionCmsUpdate` | Specific to CMS page updates. | Granular cache invalidation for CMS pages. |
| `actionClearCache` | When PrestaShop’s native cache is cleared. | Synchronizing module’s cache clearing with PrestaShop’s. |
| `actionModuleInstall` | When a module is installed. | Potentially clearing cache or updating dynamic module list. |
| `actionModuleUninstall` | When a module is uninstalled. | Clearing cache or removing module from dynamic list. |
| `actionAdminControllerSetMedia` | In admin controllers, after media is set. | Injecting admin-specific JS/CSS. |
| `actionAdminControllerPreProcess` | Before an admin controller processes its request. | Setting up admin context for module. |
| `actionAdminControllerPostProcess` | After an admin controller processes its request. | Handling post-processing for admin actions. |
| `actionOutputHTMLBefore` | Before the final HTML output is sent to the browser. | Performing HTML optimization (minification). |
| `actionOutputHTMLAfter` | After the final HTML output is sent. | Finalizing cache storage. |
| `actionAjaxDie` | When an AJAX request calls `die()`. | Ensuring proper cache handling for AJAX responses. |
| `actionGetContent` | For the module’s main configuration page. | Rendering the module’s configuration form. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to providing comprehensive assistance to ensure your Presta Speed Cache module performs optimally.
