---
title: "Product Comments - Reviews rich snippet - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Product Comments - Reviews rich snippet PrestaShop module by MyPresta.eu."
sidebar:
  label: "Product Comments - Reviews rich snippet - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Product Comments - Reviews rich snippet Module on MyPresta.eu](https://mypresta.eu/modules/seo/product-comments-reviews-rich-snippet.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/seo/product-comments-reviews-rich-snippet/)
>
> ---


# Product Comments - Reviews rich snippet

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).
- **Dependency**: This module extends the functionality of the **free PrestaShop Product Comments module**. You must have the official PrestaShop Product Comments module installed and active for this module to function correctly.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This module has a straightforward configuration page, primarily focused on enabling or disabling its core functionality and selecting where the rich snippet data should be injected.

**To access:** Go to **Modules > Module Manager**, search for “Product Comments - Reviews rich snippet”, and click “Configure”.

#### **Enable / Disable Rich Snippets**

- **What this setting does:** This is the main switch to activate or deactivate the module’s core functionality. When enabled, the module will start adding the necessary structured data to your product pages.
- **Effect of changing this setting:**
  - *When enabled:* The module will inject the rich snippet code into your product pages, allowing Google to display star ratings and review counts in search results.
  - *When disabled:* The module will stop injecting the rich snippet code. Your product listings in Google search results will revert to standard text, without stars or review counts.
- **Recommended value:** **YES** (Enabled). The primary purpose of this module is to display rich snippets, so it should almost always be enabled.
- **Merchant scenario / example:** If you’re testing the module or temporarily want to hide review data from search results (e.g., during a major site overhaul), you might disable it. Otherwise, keep it enabled to maximize visibility.

#### **Display Rich Snippets in Hook**

- **What this setting does:** This option allows you to choose *where* on your product page the module should inject the structured data. While the data is invisible to the customer, its placement can sometimes affect compatibility with themes or other modules.
- **Effect of changing this setting:**
  - *When set to ‘Header’:* The rich snippet data will be placed within the `<head>` section of your product page’s HTML. This is generally the most common and recommended location for structured data.
  - *When set to ‘Product’:* The rich snippet data will be placed within the main product content area.
  - *When set to ‘Columns’:* The rich snippet data will be placed within one of your store’s side columns (left or right, depending on your theme’s layout).
  - *When set to ‘Footer’:* The rich snippet data will be placed within the `<footer>` section of your product page’s HTML.
- **Recommended value:** **Header**. This is the most standard and robust location for structured data, as it’s processed early by search engine crawlers and is less likely to conflict with visual elements or other scripts on your page.
- **Merchant scenario / example:** If you experience unexpected issues with your product page layout or other modules after enabling rich snippets, you might try switching this hook to ‘Product’ or ‘Footer’ as a troubleshooting step. However, ‘Header’ is usually the safest bet.

#### **Display Short Rich Snippets (only stars)**

- **What this setting does:** This option allows you to choose between displaying the full rich snippet (stars + review count) or a “short” version that only shows the stars, without the number of reviews.
- **Effect of changing this setting:**
  - *When enabled:* Google will only display the star rating (e.g., ”★★★★★ 4.5”) in search results, omitting the “(X reviews)” part.
  - *When disabled:* Google will display both the star rating and the number of reviews (e.g., ”★★★★★ 4.5 (12 reviews)”).
- **Recommended value:** **NO** (Disabled). Displaying both the stars and the review count provides more complete information and often builds more trust, especially if you have a high number of reviews.
- **Merchant scenario / example:** If you have very few reviews on many products, and you feel that displaying “1 review” might look less impressive than just the stars, you might enable this option. However, for most stores with a healthy number of reviews, showing the count is beneficial.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable / Disable Rich Snippets | YES (Enabled) | Activates/deactivates the rich snippet code injection for Google search results. |
| Module Configuration | Display Rich Snippets in Hook | Header | Determines where the invisible rich snippet code is placed on the product page. ‘Header’ is generally best for compatibility. |
| Module Configuration | Display Short Rich Snippets (only stars) | NO (Disabled) | Controls whether only stars or stars + review count are shown in Google search results. Recommended to show both. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve installed the module, but I don’t see stars in Google search results. What’s wrong?**
A: Several factors could be at play:
1. **Google Crawling Time:** It takes time for Google to re-crawl your website and update its index. This can range from a few days to a few weeks, especially for new pages or significant changes.
2. **Cache:** Clear your PrestaShop cache (Advanced Parameters > Performance > Clear Cache) after configuration.
3. **Google Search Console:** Check your Google Search Console for “Reviews snippets” under “Enhancements.” If there are errors, Google might not display the snippets.
4. **No Reviews:** Ensure the product actually has approved reviews in your store. Google won’t display stars if there are no reviews.
5. **Product Comments Module:** Verify that the official PrestaShop Product Comments module is installed and active. This module relies on it.
6. **Google’s Discretion:** While the module provides the data, Google ultimately decides whether to display rich snippets. They may choose not to display them if they deem the content irrelevant or low quality.

**Q: My product page looks broken after installing the module.**
A: This is highly unlikely as the module only injects invisible structured data. However, if it happens:
1. **Disable the module:** Go to Module Manager and disable “Product Comments - Reviews rich snippet”. If the page returns to normal, then the module might be the cause.
2. **Change the “Display Rich Snippets in Hook” setting:** Try switching the hook from ‘Header’ to ‘Product’ or ‘Footer’. Sometimes, theme conflicts can occur with specific hook placements.
3. **Clear Cache:** Always clear your PrestaShop cache after making changes.

**Q: Does this module affect my website’s loading speed?**
A: No, the impact on loading speed is negligible. The module only adds a small block of text (structured data) to your page’s HTML, which is very lightweight and processed quickly by browsers and search engines.

**Q: Can I customize the appearance of the stars in Google search results?**
A: No, the appearance of the stars and review count in Google search results is entirely controlled by Google’s interface. This module provides the data; Google renders it. You cannot change the color, size, or style of the stars in search results.

**Q: Will this module work with custom themes?**
A: Yes, this module is designed to work independently of your theme’s visual styling. It injects structured data into the HTML, which is a standard practice. As long as your custom theme correctly implements PrestaShop’s hook system, the module should function without issues.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the “Product Comments - Reviews rich snippet” module’s technical architecture, intended for developers, webmasters, and technical agencies.

### 4.1 Architecture Overview

The module `prrs` (Product Reviews Rich Snippet) is a lightweight PrestaShop module designed to inject Schema.org `AggregateRating` structured data into product pages. It leverages existing data from the official `productcomments` module. The module primarily operates by hooking into a display point (configurable by the merchant) and rendering a Smarty template containing the JSON-LD structured data. It follows a standard PrestaShop module structure, with a main module class and a few supporting assets.

### 4.2 Controllers (`controllers/`)

This module does not contain any custom Front-Office or Back-Office controllers. All logic is handled within the main `index.php` module file and its associated templates.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or extend `ObjectModel`. It primarily relies on existing PrestaShop core functionalities and the `productcomments` module’s data.

### 4.4 JavaScript Assets (`views/js/`)

- **`prrs/lib/searchTool/views/js/autocomplete.js`**
  - **Scope:** Back-office (likely for an internal search tool, though not directly used by the main module’s rich snippet functionality).
  - **Responsibility:** This script appears to be part of a generic autocomplete utility. It likely handles AJAX requests for search suggestions, updates input fields, and manages the display of search results in a dropdown. Given the module’s primary function, this might be a leftover or a dependency from a shared library. It’s not directly involved in the rich snippet generation.

### 4.5 CSS Stylesheets (`views/css/`)

- **`prrs/lib/searchTool/views/css/autocomplete.css`**
  - **Scope:** Back-office.
  - **Responsibility:** Provides styling for the autocomplete search tool mentioned above. This would include styles for the search input, dropdown suggestions, highlighted results, etc. Not relevant to front-office display.
- **`prrs/views/css/prrs.css`**
  - **Scope:** Front-office.
  - **Responsibility:** This stylesheet is likely minimal or empty, as the module’s primary function is to inject invisible structured data. If it contains any styles, they would be for very subtle, non-intrusive elements, or potentially for a fallback visual if the structured data itself had a visible component (which it typically does not for rich snippets). Developers should check this file for any unexpected visual output.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`prrs/lib/searchTool/views/scripts.tpl`**
  - **Scope:** Back-office.
  - **Purpose:** This template likely includes the JavaScript for the autocomplete search tool (`autocomplete.js`) and potentially other related scripts or inline script configurations. It would be rendered in an admin context.
- **`prrs/views/templates/prrs-json.tpl`**
  - **Scope:** Front-office (product page).
  - **Purpose:** This is the core template responsible for generating the JSON-LD structured data for the `AggregateRating` rich snippet. It dynamically retrieves the product’s average rating and review count from the `productcomments` module and formats it according to Schema.org specifications. This template is rendered when the “Display Short Rich Snippets” option is disabled.
  - **Key Data Points:** `product.id_product`, `product.name`, `product.link_rewrite`, `product.link`, `product.cover.bySize.home_default.url`, `average_grade`, `nb_comments`.
- **`prrs/views/templates/prrs.tpl`**
  - **Scope:** Front-office (product page).
  - **Purpose:** This template is likely a wrapper or an alternative to `prrs-json.tpl`, potentially used for older PrestaShop versions or specific hook integrations. It also generates the rich snippet data. It’s important to verify which template is actively used based on the module’s `getContent()` logic and hook registration.
- **`prrs/views/templates/shortprrs.tpl`**
  - **Scope:** Front-office (product page).
  - **Purpose:** This template generates a simplified JSON-LD structured data snippet, typically only including the average star rating without the explicit count of reviews. It is rendered when the “Display Short Rich Snippets” option is enabled.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create any custom database tables.
  - It relies on the `ps_configuration` table to store its settings (e.g., `PRRS_ENABLED`, `PRRS_HOOK`, `PRRS_SHORT`).
  - It retrieves review data from the tables created by the official `productcomments` module (e.g., `ps_product_comment`, `ps_product_comment_criterion`).
- **Registered Hooks Table**:

| Hook Name | Execution Timing / Context | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Renders within the `<head>` section of the page. | Injects JSON-LD structured data for rich snippets early in the page load. Configurable via module settings. |
| `displayProductAdditionalInfo` | Renders within the product page, typically below the main product details. | Alternative hook for injecting JSON-LD structured data. Configurable via module settings. |
| `displayLeftColumn` / `displayRightColumn` | Renders within the respective side columns. | Less common, but available as an alternative hook for injecting JSON-LD structured data. Configurable via module settings. |
| `displayFooter` | Renders within the `<footer>` section of the page. | Alternative hook for injecting JSON-LD structured data, typically at the end of the page. Configurable via module settings. |
| `actionFrontControllerSetMedia` | Executed when a front controller sets its media assets. | Used to register CSS and JavaScript files for the front office. |
| `actionAdminControllerSetMedia` | Executed when an admin controller sets its media assets. | Used to register CSS and JavaScript files for the back office (e.g., `autocomplete.js`, `autocomplete.css`). |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions regarding the “Product Comments - Reviews rich snippet” module.
