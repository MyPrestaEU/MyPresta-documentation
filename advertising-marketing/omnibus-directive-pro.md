---
title: "Omnibus Directive Pro - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Omnibus Directive Pro PrestaShop module by MyPresta.eu."
sidebar:
  label: "Omnibus Directive Pro - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Omnibus Directive Pro Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/omnibus-directive-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/omnibus-directive-pro/)
>
> ---


# Omnibus Directive Pro

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Omnibus Directive Pro)

This is the main configuration screen where you control the core behavior and display options of the Omnibus Directive Pro module.

#### General Settings

- **Enable Module:**

  - **What this setting does:** This is the master switch to activate or deactivate the entire module’s functionality.
  - **Effect of changing this setting:**
    - *When enabled:* The module will start tracking prices, displaying lowest price information, and all other configured features will become active.
    - *When disabled:* The module will stop all its operations, including price tracking and front-office display. No lowest price information will be shown.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Enable this after installation to start complying with the directive. Disable it only if you need to temporarily pause its functionality for maintenance or specific testing.
- **Display Lowest Price on Product Page:**

  - **What this setting does:** Controls whether the “lowest price in the last 30 days” badge or text appears on individual product pages when a product is on sale.
  - **Effect of changing this setting:**
    - *When enabled:* The lowest price information will be visible to customers on every product page where a price reduction is active.
    - *When disabled:* The lowest price information will NOT be shown on product pages, even if a product is on sale.
  - **Recommended value:** YES (Highly recommended for compliance).
  - **Merchant scenario / example:** You must enable this to comply with the Omnibus Directive. If you disable it, your product pages will not show the required information during sales.
- **Display Lowest Price on Product Listings (Category, Search, etc.):**

  - **What this setting does:** Determines if the lowest price information is shown on product cards in lists (e.g., category pages, search results, manufacturer pages).
  - **Effect of changing this setting:**
    - *When enabled:* The lowest price badge will appear on product cards in listing views, providing early transparency to customers.
    - *When disabled:* The lowest price information will only appear on the individual product page, not in listings.
  - **Recommended value:** YES (Recommended for maximum transparency and compliance visibility).
  - **Merchant scenario / example:** Enabling this helps customers quickly identify compliant sales directly from category pages, potentially boosting click-through rates to product pages.
- **Enable Price Chart on Product Page:**

  - **What this setting does:** Activates an interactive chart on the product page that visually displays the product’s price history over time.
  - **Effect of changing this setting:**
    - *When enabled:* A chart will be embedded on the product page, allowing customers to see past price fluctuations.
    - *When disabled:* The price chart will not be displayed.
  - **Recommended value:** YES (Enhances transparency and customer trust).
  - **Merchant scenario / example:** Customers who are price-sensitive or want to verify the legitimacy of a sale can use this chart. It adds an extra layer of trust.
- **Price History Cleanup Cron URL:**

  - **What this setting does:** Provides a unique URL that, when accessed, triggers the module’s automated process to clean up old price history data. This keeps your database optimized.
  - **Effect of changing this setting:** This is a read-only field. You need to set up a cron job on your server to regularly visit this URL.
  - **Recommended value:** Copy this URL and set up a cron job.
  - **Merchant scenario / example:** Set up a cron job to run this URL once a day (e.g., at 3 AM) to ensure your price history database remains lean and efficient, preventing it from growing too large over time.
- **Enable CSV Audit Log:**

  - **What this setting does:** If enabled, the module will generate a CSV file containing a detailed log of price changes and lowest price calculations, which can be useful for auditing and compliance verification.
  - **Effect of changing this setting:**
    - *When enabled:* A CSV file will be generated and updated with audit information.
    - *When disabled:* No audit log will be created or maintained.
  - **Recommended value:** NO (Unless specifically required for internal auditing or legal purposes, as it can consume disk space).
  - **Merchant scenario / example:** If your legal team or auditors require a verifiable record of your compliance activities, enable this. Otherwise, it’s generally not needed for day-to-day operation.

#### Badge Studio

This section allows you to customize the visual appearance of the “lowest price” badge displayed on your store.

- **Badge Type:**

  - **What this setting does:** Choose between a “Smart Badge” (highly customizable with icons, colors, and text) or a “Simple Text” display.
  - **Effect of changing this setting:**
    - *Smart Badge:* Unlocks further customization options for a visually rich badge.
    - *Simple Text:* Displays only plain text without advanced styling.
  - **Recommended value:** Smart Badge (Offers more control and better integration with your theme).
  - **Merchant scenario / example:** If you want a prominent, branded badge, choose “Smart Badge.” If you prefer a minimalist approach, “Simple Text” might be better.
- **Badge Position (Product Page):**

  - **What this setting does:** Select where the badge appears on the product page. Options typically include “Near Price,” “Under Price,” “Custom Hook,” etc.
  - **Effect of changing this setting:** Changes the visual placement of the badge on the product page.
  - **Recommended value:** Near Price (Most common and legally clear placement).
  - **Merchant scenario / example:** Test different positions to see what integrates best with your theme and is most visible to customers without being intrusive.
- **Badge Position (Product Listings):**

  - **What this setting does:** Select where the badge appears on product cards in listing pages. Options typically include “Under Product Name,” “Under Price,” “Custom Hook,” etc.
  - **Effect of changing this setting:** Changes the visual placement of the badge on product cards.
  - **Recommended value:** Under Price (Clear and consistent with product page placement).
  - **Merchant scenario / example:** Ensure the badge doesn’t overlap with other elements on your product cards, especially on mobile.
- **Badge Text:**

  - **What this setting does:** Customize the actual text displayed within the badge. You can use placeholders like `{lowest_price}` for the actual lowest price value.
  - **Effect of changing this setting:** Changes the message customers read.
  - **Recommended value:** “Lowest price in last 30 days: {lowest\_price}” (Clear and compliant).
  - **Merchant scenario / example:** You might translate this text for different languages or slightly rephrase it to fit your brand’s tone, as long as the meaning remains clear and compliant.
- **Badge Background Color:**

  - **What this setting does:** Sets the background color of the Smart Badge.
  - **Effect of changing this setting:** Changes the visual background of the badge.
  - **Recommended value:** A color that contrasts well with your text and theme, e.g., a light grey or a brand accent color.
  - **Merchant scenario / example:** Choose a color that makes the badge stand out but still looks professional and integrates with your store’s design.
- **Badge Text Color:**

  - **What this setting does:** Sets the color of the text within the Smart Badge.
  - **Effect of changing this setting:** Changes the visual color of the text.
  - **Recommended value:** A color that is highly readable against your chosen background color, e.g., black or dark grey.
  - **Merchant scenario / example:** Ensure high contrast for accessibility and readability.
- **Badge Icon:**

  - **What this setting does:** Allows you to select an icon to display alongside the text in the Smart Badge.
  - **Effect of changing this setting:** Adds a visual icon to the badge.
  - **Recommended value:** A relevant icon, such as a “tag” or “info” icon.
  - **Merchant scenario / example:** A small, clear icon can draw attention to the badge and make its purpose more intuitive.

#### Analytics Panel

This section provides insights into your module’s performance and compliance status.

- **View Analytics:**
  - **What this setting does:** This button opens a dedicated panel within your Back Office, displaying statistics related to price tracking, products on sale, and compliance status.
  - **Effect of changing this setting:** Clicking this button navigates you to the analytics dashboard.
  - **Recommended value:** Regularly check this.
  - **Merchant scenario / example:** Use the analytics panel to monitor how many products are currently displaying the lowest price, identify any potential issues, or review the overall compliance status of your store.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Enable Module | YES | Activates/deactivates all module features. |
|  | Display Lowest Price on Product Page | YES | Shows lowest 30-day price on product pages during sales. |
|  | Display Lowest Price on Product Listings | YES | Shows lowest 30-day price on category/search pages during sales. |
|  | Enable Price Chart on Product Page | YES | Displays an interactive price history chart on product pages. |
|  | Price History Cleanup Cron URL | (Copy & Setup) | URL for automated database cleanup. Run daily. |
|  | Enable CSV Audit Log | NO | Creates a detailed log of price changes for auditing. |
| **Badge Studio** | Badge Type | Smart Badge | Choose between customizable badge or simple text. |
|  | Badge Position (Product Page) | Near Price | Sets placement of the badge on individual product pages. |
|  | Badge Position (Product Listings) | Under Price | Sets placement of the badge on product cards in listings. |
|  | Badge Text | “Lowest price in last 30 days: {lowest\_price}” | Customizable text for the badge. |
|  | Badge Background Color | (Theme-dependent) | Sets the background color of the Smart Badge. |
|  | Badge Text Color | (Theme-dependent) | Sets the text color of the Smart Badge. |
|  | Badge Icon | (Relevant icon) | Adds a visual icon to the Smart Badge. |
| **Analytics Panel** | View Analytics | (Click button) | Opens a dashboard for compliance and price tracking statistics. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The lowest price badge is not showing up on my product pages, even though I’ve enabled it.**
A:

1. **Check Module Status:** Ensure the “Enable Module” setting is set to YES.
2. **Product on Sale?** The badge only appears for products that are currently on sale (have a specific price or discount applied). Make sure the product you’re testing has an active price reduction.
3. **Clear Cache:** Go to **Advanced Parameters > Performance** in your PrestaShop Back Office and clear the Smarty cache, browser cache, and any other caches (e.g., CDN cache) you might be using.
4. **Theme Compatibility:** While the module is designed for broad compatibility, very heavily customized themes might require minor adjustments. If the issue persists, contact MyPresta.eu support.

**Q2: The price history chart is not showing any data or looks incomplete.**
A:

1. **Module Enabled:** Ensure the “Enable Price Chart on Product Page” is set to YES.
2. **Price Changes:** The chart will only display data if the product has had recorded price changes since the module was installed and active. If a product’s price has never changed, there will be no history to show.
3. **Time to Collect Data:** It takes time for the module to collect price history. If you’ve just installed it, data will accumulate as prices change over days/weeks.

**Q3: How often should I run the Price History Cleanup Cron Job?**
A: We recommend running the cron job once every 24 hours. This frequency is sufficient to keep your database optimized without putting excessive load on your server.

**Q4: My custom theme’s styling clashes with the module’s badge. How can I fix this?**
A: The “Badge Studio” offers extensive customization for colors, text, and icons. Try adjusting these settings first to match your theme. If you still have styling conflicts, you may need a webmaster to apply custom CSS overrides. The module’s CSS files are designed to be easily overridden by your theme’s stylesheet.

**Q5: What happens if I disable the module? Does it delete my price history data?**
A: Disabling the module will stop its front-office display and background processes, but it typically does not delete the collected price history data. If you re-enable it later, the data should still be available. However, for complete data removal, you would need to uninstall the module and choose to delete its data.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical architecture of the Omnibus Directive Pro module, intended for developers, webmasters, and technical agencies.

### 4.1 Architecture Overview

The Omnibus Directive Pro module follows a standard PrestaShop MVC (Model-View-Controller) pattern, with a focus on event-driven hooks for integration. It primarily extends `Module` for its core functionality and configuration, uses `ModuleFrontController` for specific front-office actions (like cron cleanup), and leverages Smarty templates for rendering. Price history is managed through direct database interaction and `Configuration` values. The module integrates a “Badge Studio” and “Analytics Panel” within the Back Office for enhanced merchant control and insights.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `omnipro/controllers/front/cleanupcron.php`
  - **Class name & parent class:** `OmniproCleanupcronModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** This controller is designed to be accessed via a cron job. When invoked, it executes the module’s internal cleanup logic for price history data, typically removing old records to maintain database performance. It does not render any visual output to the browser, usually returning a simple success or error message.
- `omnipro/controllers/front/index.php`
  - **Class name & parent class:** `OmniproIndexModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** This controller likely serves as a fallback or a general entry point for front-office module actions that don’t require specific routing, or it might be a placeholder. Given the module’s primary function, it’s less likely to handle complex user interactions directly but could be used for simple data retrieval or status checks.

#### Back-Office Admin Controllers

No dedicated Admin Controllers (`controllers/admin/`) were identified, suggesting that all Back Office configuration and analytics are handled directly within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

No custom classes extending `ObjectModel` were identified in the `classes/` directory. This indicates that price history data is likely stored directly in `ps_configuration` or a custom table managed by the main module file (`omnipro/index.php`) without a dedicated `ObjectModel` wrapper.

### 4.4 JavaScript Assets (`views/js/`)

- `omnipro/views/js/admin-analytics.js`
  - **Scope:** Back-office.
  - **Description:** This script is responsible for powering the interactive elements and data visualization within the module’s “Analytics Panel” in the Back Office. It likely handles AJAX requests to fetch analytics data, renders charts (e.g., using Chart.js or similar libraries), and updates the UI based on user interactions within the analytics dashboard.
- `omnipro/views/js/admin-badge-studio.js`
  - **Scope:** Back-office.
  - **Description:** This script provides the interactive functionality for the “Badge Studio” configuration screen. It manages real-time previews of the badge as the merchant adjusts colors, text, icons, and positions. It likely handles color pickers, input field updates, and dynamic rendering of a preview badge.
- `omnipro/views/js/admin-config.js`
  - **Scope:** Back-office.
  - **Description:** A general-purpose script for the main module configuration page. It might handle form validation, conditional display of settings based on other selections (e.g., showing badge customization only if “Smart Badge” is selected), and general UI enhancements for the configuration form.
- `omnipro/views/js/front-chart.js`
  - **Scope:** Front-office.
  - **Description:** This script is responsible for rendering the interactive price history chart on the product page. It likely fetches price data via AJAX (possibly from a dedicated front controller or a hook), initializes a charting library (e.g., Chart.js), and displays the price evolution visually to the customer.

### 4.5 CSS Stylesheets (`views/css/`)

- `omnipro/views/css/admin-analytics.css`
  - **Scope:** Back-office admin styling.
  - **Description:** Stylesheets specifically for the layout and appearance of the “Analytics Panel” in the module’s Back Office configuration.
- `omnipro/views/css/admin-badge-studio.css`
  - **Scope:** Back-office admin styling.
  - **Description:** Stylesheets for the “Badge Studio” interface, including styling for color pickers, preview elements, and layout of customization options.
- `omnipro/views/css/admin-config.css`
  - **Scope:** Back-office admin styling.
  - **Description:** General styling for the main module configuration form in the Back Office, ensuring a consistent and user-friendly interface.
- `omnipro/views/css/omnibus-classic.css`
  - **Scope:** Front-office customer styling.
  - **Description:** Provides default styling for the lowest price badge and potentially the price chart, specifically tailored for older PrestaShop “Classic” themes or themes that mimic their structure.
- `omnipro/views/css/omnibus-hummingbird.css`
  - **Scope:** Front-office customer styling.
  - **Description:** Provides default styling for the lowest price badge and potentially the price chart, specifically optimized for the newer PrestaShop “Hummingbird” theme.
- `omnipro/views/css/omnibus.css`
  - **Scope:** Front-office customer styling.
  - **Description:** Core front-office styles for the lowest price badge and price chart, applicable across various themes. This likely contains the fundamental visual rules, with `omnibus-classic.css` and `omnibus-hummingbird.css` providing theme-specific overrides or additions.

### 4.6 Smarty Template Structure (`views/templates/`)

- `omnipro/lib/searchTool/views/scripts.tpl`
  - **Scope:** Unclear without context, but `lib` suggests a third-party library or internal utility. `scripts.tpl` often includes JS or CSS assets.
  - **Description:** This template likely includes JavaScript or CSS files required by an internal search tool or utility used by the module, possibly for data processing or specific UI components within the admin.
- `omnipro/views/templates/admin/analytics-panel.tpl`
  - **Scope:** Admin template.
  - **Description:** Renders the HTML structure for the “Analytics Panel” in the Back Office, including placeholders for charts, statistics, and data tables.
- `omnipro/views/templates/admin/badge-studio.tpl`
  - **Scope:** Admin template.
  - **Description:** Renders the HTML form and preview area for the “Badge Studio” configuration, allowing merchants to customize the appearance of the lowest price badge.
- `omnipro/views/templates/admin/configure.tpl`
  - **Scope:** Admin template.
  - **Description:** The main configuration template for the module, rendered by `getContent()` in `omnipro/index.php`. It includes all the general settings, and likely includes `analytics-panel.tpl` and `badge-studio.tpl` or links to them.
- `omnipro/views/templates/hook/omnibus-badge.tpl`
  - **Scope:** Hook template (Front-office).
  - **Description:** This template is rendered in various front-office hooks (e.g., `displayProductPriceBlock`, `displayProductListFunctionalButtons`) to output the HTML for the lowest price badge on product pages and listings. It receives variables containing the lowest price and other badge customization options.
- `omnipro/views/templates/hook/omnibus.tpl`
  - **Scope:** Hook template (Front-office).
  - **Description:** A more general hook template, potentially used for embedding the price chart (`front-chart.js`) or other module-related content on the product page, or for general module initialization in `displayHeader` or `displayFooter`.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module likely stores its main configuration settings in `ps_configuration` (e.g., `OMNIPRO_ENABLED`, `OMNIPRO_DISPLAY_PRODUCT_PAGE`).
  - Given the “price history” feature and “cron cleanup,” it’s highly probable that the module creates at least one custom database table (e.g., `ps_omnipro_price_history`) to store product price records over time. This table would typically contain `id_product`, `id_product_attribute`, `id_shop`, `id_currency`, `price`, and `date_add` fields.
  - If “CSV Audit Log” is enabled, it might store references to generated CSV files or log entries in a dedicated table.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Inject CSS/JS assets for front-office, initialize module-wide JS variables. |
| `displayProductPriceBlock` | Near the product price on the product page. | Render the lowest price badge (`omnibus-badge.tpl`) on the product page. |
| `displayProductListFunctionalButtons` | Within product listings (category, search, etc.). | Render the lowest price badge (`omnibus-badge.tpl`) on product cards. |
| `displayFooterProduct` | At the bottom of the product page. | Potentially render the price chart (`omnibus.tpl` with `front-chart.js`). |
| `actionProductUpdate` | After a product is updated in the Back Office. | Trigger price history recording for the updated product. |
| `actionProductAdd` | After a new product is added. | Initialize price history recording for the new product. |
| `actionProductDelete` | After a product is deleted. | Clean up associated price history data. |
| `actionUpdateQuantity` | After product quantity changes. | (Less likely for price history, but possible for related logic). |
| `actionUpdateSpecificPrice` | After a specific price (discount) is added/updated. | Crucial for triggering lowest price calculation and display logic. |
| `actionFrontControllerSetMedia` | Before a front controller renders its output. | Conditionally add front-office CSS/JS based on page context. |
| `actionAdminControllerSetMedia` | Before an admin controller renders its output. | Conditionally add back-office CSS/JS for configuration pages. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the Omnibus Directive Pro module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and integration.
